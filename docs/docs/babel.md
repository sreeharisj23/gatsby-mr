---
title: Babel
---


जुन्या ब्राऊजरला समर्थन देत असताना- गॅटस्बी [babel](https://babeljs.io/) आधुनिक Javascript लिहिण्यास समर्थन देण्यासाठी वापरतो 

## कोणत्या ब्राउझरचे समर्थन करावे हे निर्दिष्ट कसे कराल 

गॅटस्बी मुख्य ब्राउझरच्या शेवटच्या दोन आवृत्त्यांना डीफॉल्टनुसार समर्थन देते, IE 9+, तसेच कोणताही ब्राउझर ज्यात अद्याप 1% + ब्राउझर सामायिक आहे.

याचा अर्थ असा आहे की आपली Javascript जुन्या ब्राउझरवर कार्य करते हे सुनिश्चित करण्यासाठी स्वयंचलितपणे संकलित केली आहे. पॉलीफिल देखील स्वयंचलितपणे जोडली जातात- जुन्या ब्राउझरवर रहस्यमयपणे खंडित करणारा कोणताही शिपिंग कोड नाही!

आपण केवळ नवीन ब्राउझरवर लक्ष केंद्रित केले असल्यास, कोणत्या ब्राउझरवर समर्थित आहात यावर गॅटस्बीला कसे शिकवायचे यासाठी [Browser Support](/docs/browser-support/) दस्तऐवज पेज पहा आणि नंतर babel केवळ या ब्राउझरसाठी कंपाईल करणे प्रारंभ करेल.

## कस्टम babelrc फाईल कशी वापरावी

डिफॉल्ट .babelrc सेटअप फाईल बरोबर येते आणि ते बहुतेक साइट्ससाठी कार्य करतात. आपण कस्टम बाबेल प्रीसेट किंवा प्लगइन जोडू इच्छित असल्यास, आपण आपल्या साइटच्या रूट्स आपले स्वतःचे `.babrcrc` तयार करू शकता. इम्पोर्ट करा [`babel-preset-gatsby`](https://github.com/gatsbyjs/gatsby/tree/master/packages/babel-preset-gatsby),आणि अतिरिक्त प्लगइन जोडा, प्रीसेट आणि options बेबल- वर पर्याय पास करा `babel-preset-gatsby`, उदा. `targets`.

```shell
npm install --save-dev babel-preset-gatsby
```

<!-- prettier-ignore-start -->
```json:title=.babelrc
{
  "plugins": ["@babel/plugin-proposal-optional-chaining"],
  "presets": [
    [
      "babel-preset-gatsby",
      {
        "targets": {
          "browsers": [">0.25%", "not dead"]
        }
      }
    ]
  ]
}
```
<!-- prettier-ignore-end -->

अधिक प्रगत कॉन्फिगरेशनसाठी, आपण डीफॉल्टची कॉपी देखील येथे तयार करु शकता [`babel-preset-gatsby`](https://github.com/gatsbyjs/gatsby/tree/master/packages/babel-preset-gatsby)आणि आपल्या गरजा भागवण्यासाठी त्यांना कस्टमाइझ करू शकता.
