# System.Web.UI.Design.WebControls.AutoFormatSchemes::.cctor

- ea: `0x14b80`
- end: `0x15160`
- name: `System.Web.UI.Design.WebControls.AutoFormatSchemes::.cctor`
- size: `1504`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1502d`: `CreateUserWizardScheme_Empty`
- `0x15035`: `CreateUserWizardScheme_Elegant`
- `0x1503d`: `CreateUserWizardScheme_Professional`
- `0x15045`: `CreateUserWizardScheme_Simple`
- `0x1504d`: `CreateUserWizardScheme_Classic`
- `0x15055`: `CreateUserWizardScheme_Colorful`
- `0x15068`: `SiteMapPathAFmt_Scheme_Default`
- `0x15070`: `SiteMapPathAFmt_Scheme_Colorful`
- `0x15078`: `SiteMapPathAFmt_Scheme_Simple`
- `0x15080`: `SiteMapPathAFmt_Scheme_Professional`
- `0x15088`: `SiteMapPathAFmt_Scheme_Classic`

## pseudocode

```c

```

## disassembly

```asm
0x14b80  ldc.i4.s 0x12
0x14b82  newarr   [mscorlib]System.String
0x14b87  dup
0x14b88  ldc.i4.0
0x14b89  ldstr    aBdlschemeEmpty// "BDLScheme_Empty"
0x14b8e  stelem.ref
0x14b8f  dup
0x14b90  ldc.i4.1
0x14b91  ldstr    aBdlschemeConsi// "BDLScheme_Consistent1"
0x14b96  stelem.ref
0x14b97  dup
0x14b98  ldc.i4.2
0x14b99  ldstr    aBdlschemeConsi_0// "BDLScheme_Consistent2"
0x14b9e  stelem.ref
0x14b9f  dup
0x14ba0  ldc.i4.3
0x14ba1  ldstr    aBdlschemeConsi_1// "BDLScheme_Consistent3"
0x14ba6  stelem.ref
0x14ba7  dup
0x14ba8  ldc.i4.4
0x14ba9  ldstr    aBdlschemeConsi_2// "BDLScheme_Consistent4"
0x14bae  stelem.ref
0x14baf  dup
0x14bb0  ldc.i4.5
0x14bb1  ldstr    aBdlschemeColor// "BDLScheme_Colorful1"
0x14bb6  stelem.ref
0x14bb7  dup
0x14bb8  ldc.i4.6
0x14bb9  ldstr    aBdlschemeColor_0// "BDLScheme_Colorful2"
0x14bbe  stelem.ref
0x14bbf  dup
0x14bc0  ldc.i4.7
0x14bc1  ldstr    aBdlschemeColor_1// "BDLScheme_Colorful3"
0x14bc6  stelem.ref
0x14bc7  dup
0x14bc8  ldc.i4.8
0x14bc9  ldstr    aBdlschemeColor_2// "BDLScheme_Colorful4"
0x14bce  stelem.ref
0x14bcf  dup
0x14bd0  ldc.i4.s 9
0x14bd2  ldstr    aBdlschemeColor_3// "BDLScheme_Colorful5"
0x14bd7  stelem.ref
0x14bd8  dup
0x14bd9  ldc.i4.s 0xA
0x14bdb  ldstr    aBdlschemeProfe// "BDLScheme_Professional1"
0x14be0  stelem.ref
0x14be1  dup
0x14be2  ldc.i4.s 0xB
0x14be4  ldstr    aBdlschemeProfe_0// "BDLScheme_Professional2"
0x14be9  stelem.ref
0x14bea  dup
0x14beb  ldc.i4.s 0xC
0x14bed  ldstr    aBdlschemeProfe_1// "BDLScheme_Professional3"
0x14bf2  stelem.ref
0x14bf3  dup
0x14bf4  ldc.i4.s 0xD
0x14bf6  ldstr    aBdlschemeSimpl// "BDLScheme_Simple1"
0x14bfb  stelem.ref
0x14bfc  dup
0x14bfd  ldc.i4.s 0xE
0x14bff  ldstr    aBdlschemeSimpl_0// "BDLScheme_Simple2"
0x14c04  stelem.ref
0x14c05  dup
0x14c06  ldc.i4.s 0xF
0x14c08  ldstr    aBdlschemeSimpl_1// "BDLScheme_Simple3"
0x14c0d  stelem.ref
0x14c0e  dup
0x14c0f  ldc.i4.s 0x10
0x14c11  ldstr    aBdlschemeClass// "BDLScheme_Classic1"
0x14c16  stelem.ref
0x14c17  dup
0x14c18  ldc.i4.s 0x11
0x14c1a  ldstr    aBdlschemeClass_0// "BDLScheme_Classic2"
0x14c1f  stelem.ref
0x14c20  stsfld   string[] System.Web.UI.Design.WebControls.AutoFormatSchemes::BDL_SCHEME_NAMES
0x14c25  ldc.i4.s 0x12
0x14c27  newarr   [mscorlib]System.String
0x14c2c  dup
0x14c2d  ldc.i4.0
0x14c2e  ldstr    aBdlschemeEmpty// "BDLScheme_Empty"
0x14c33  stelem.ref
0x14c34  dup
0x14c35  ldc.i4.1
0x14c36  ldstr    aBdlschemeConsi// "BDLScheme_Consistent1"
0x14c3b  stelem.ref
0x14c3c  dup
0x14c3d  ldc.i4.2
0x14c3e  ldstr    aBdlschemeConsi_0// "BDLScheme_Consistent2"
0x14c43  stelem.ref
0x14c44  dup
0x14c45  ldc.i4.3
0x14c46  ldstr    aBdlschemeConsi_1// "BDLScheme_Consistent3"
0x14c4b  stelem.ref
0x14c4c  dup
0x14c4d  ldc.i4.4
0x14c4e  ldstr    aBdlschemeConsi_2// "BDLScheme_Consistent4"
0x14c53  stelem.ref
0x14c54  dup
0x14c55  ldc.i4.5
0x14c56  ldstr    aBdlschemeColor// "BDLScheme_Colorful1"
0x14c5b  stelem.ref
0x14c5c  dup
0x14c5d  ldc.i4.6
0x14c5e  ldstr    aBdlschemeColor_0// "BDLScheme_Colorful2"
0x14c63  stelem.ref
0x14c64  dup
0x14c65  ldc.i4.7
0x14c66  ldstr    aBdlschemeColor_1// "BDLScheme_Colorful3"
0x14c6b  stelem.ref
0x14c6c  dup
0x14c6d  ldc.i4.8
0x14c6e  ldstr    aBdlschemeColor_2// "BDLScheme_Colorful4"
0x14c73  stelem.ref
0x14c74  dup
0x14c75  ldc.i4.s 9
0x14c77  ldstr    aBdlschemeColor_3// "BDLScheme_Colorful5"
0x14c7c  stelem.ref
0x14c7d  dup
0x14c7e  ldc.i4.s 0xA
0x14c80  ldstr    aBdlschemeProfe// "BDLScheme_Professional1"
0x14c85  stelem.ref
0x14c86  dup
0x14c87  ldc.i4.s 0xB
0x14c89  ldstr    aBdlschemeProfe_0// "BDLScheme_Professional2"
0x14c8e  stelem.ref
0x14c8f  dup
0x14c90  ldc.i4.s 0xC
0x14c92  ldstr    aBdlschemeProfe_1// "BDLScheme_Professional3"
0x14c97  stelem.ref
0x14c98  dup
0x14c99  ldc.i4.s 0xD
0x14c9b  ldstr    aBdlschemeSimpl// "BDLScheme_Simple1"
0x14ca0  stelem.ref
0x14ca1  dup
0x14ca2  ldc.i4.s 0xE
0x14ca4  ldstr    aBdlschemeSimpl_0// "BDLScheme_Simple2"
0x14ca9  stelem.ref
0x14caa  dup
0x14cab  ldc.i4.s 0xF
0x14cad  ldstr    aBdlschemeSimpl_1// "BDLScheme_Simple3"
0x14cb2  stelem.ref
0x14cb3  dup
0x14cb4  ldc.i4.s 0x10
0x14cb6  ldstr    aBdlschemeClass// "BDLScheme_Classic1"
0x14cbb  stelem.ref
0x14cbc  dup
0x14cbd  ldc.i4.s 0x11
0x14cbf  ldstr    aBdlschemeClass_0// "BDLScheme_Classic2"
0x14cc4  stelem.ref
0x14cc5  stsfld   string[] System.Web.UI.Design.WebControls.AutoFormatSchemes::GRIDVIEW_SCHEME_NAMES
0x14cca  ldc.i4.s 0x14
0x14ccc  newarr   [mscorlib]System.String
0x14cd1  dup
0x14cd2  ldc.i4.0
0x14cd3  ldstr    aTvschemeEmpty// "TVScheme_Empty"
0x14cd8  stelem.ref
0x14cd9  dup
0x14cda  ldc.i4.1
0x14cdb  ldstr    aTvschemeArrows// "TVScheme_Arrows"
0x14ce0  stelem.ref
0x14ce1  dup
0x14ce2  ldc.i4.2
0x14ce3  ldstr    aTvschemeArrows_0// "TVScheme_Arrows2"
0x14ce8  stelem.ref
0x14ce9  dup
0x14cea  ldc.i4.3
0x14ceb  ldstr    aTvschemeBullet// "TVScheme_BulletedList"
0x14cf0  stelem.ref
0x14cf1  dup
0x14cf2  ldc.i4.4
0x14cf3  ldstr    aTvschemeBullet_0// "TVScheme_BulletedList2"
0x14cf8  stelem.ref
0x14cf9  dup
0x14cfa  ldc.i4.5
0x14cfb  ldstr    aTvschemeBullet_1// "TVScheme_BulletedList3"
0x14d00  stelem.ref
0x14d01  dup
0x14d02  ldc.i4.6
0x14d03  ldstr    aTvschemeBullet_2// "TVScheme_BulletedList4"
0x14d08  stelem.ref
0x14d09  dup
0x14d0a  ldc.i4.7
0x14d0b  ldstr    aTvschemeBullet_3// "TVScheme_BulletedList5"
0x14d10  stelem.ref
0x14d11  dup
0x14d12  ldc.i4.8
0x14d13  ldstr    aTvschemeBullet_4// "TVScheme_BulletedList6"
0x14d18  stelem.ref
0x14d19  dup
0x14d1a  ldc.i4.s 9
0x14d1c  ldstr    aTvschemeContac// "TVScheme_Contacts"
0x14d21  stelem.ref
0x14d22  dup
0x14d23  ldc.i4.s 0xA
0x14d25  ldstr    aTvschemeEvents// "TVScheme_Events"
0x14d2a  stelem.ref
0x14d2b  dup
0x14d2c  ldc.i4.s 0xB
0x14d2e  ldstr    aTvschemeFaq// "TVScheme_FAQ"
0x14d33  stelem.ref
0x14d34  dup
0x14d35  ldc.i4.s 0xC
0x14d37  ldstr    aTvschemeInbox// "TVScheme_Inbox"
0x14d3c  stelem.ref
0x14d3d  dup
0x14d3e  ldc.i4.s 0xD
0x14d40  ldstr    aTvschemeMsdn// "TVScheme_MSDN"
0x14d45  stelem.ref
0x14d46  dup
0x14d47  ldc.i4.s 0xE
0x14d49  ldstr    aTvschemeNews// "TVScheme_News"
0x14d4e  stelem.ref
0x14d4f  dup
0x14d50  ldc.i4.s 0xF
0x14d52  ldstr    aTvschemeSimple// "TVScheme_Simple"
0x14d57  stelem.ref
0x14d58  dup
0x14d59  ldc.i4.s 0x10
0x14d5b  ldstr    aTvschemeSimple_0// "TVScheme_Simple2"
0x14d60  stelem.ref
0x14d61  dup
0x14d62  ldc.i4.s 0x11
0x14d64  ldstr    aTvschemeToc// "TVScheme_TOC"
0x14d69  stelem.ref
0x14d6a  dup
0x14d6b  ldc.i4.s 0x12
0x14d6d  ldstr    aTvschemeWindow// "TVScheme_Windows_Help"
0x14d72  stelem.ref
0x14d73  dup
0x14d74  ldc.i4.s 0x13
0x14d76  ldstr    aTvschemeXpFile// "TVScheme_XP_File_Explorer"
0x14d7b  stelem.ref
0x14d7c  stsfld   string[] System.Web.UI.Design.WebControls.AutoFormatSchemes::TREEVIEW_SCHEME_NAMES
0x14d81  ldc.i4.6
0x14d82  newarr   [mscorlib]System.String
0x14d87  dup
0x14d88  ldc.i4.0
0x14d89  ldstr    aLoginschemeEmp// "LoginScheme_Empty"
0x14d8e  stelem.ref
0x14d8f  dup
0x14d90  ldc.i4.1
0x14d91  ldstr    aLoginschemeEle// "LoginScheme_Elegant"
0x14d96  stelem.ref
0x14d97  dup
0x14d98  ldc.i4.2
0x14d99  ldstr    aLoginschemePro// "LoginScheme_Professional"
0x14d9e  stelem.ref
0x14d9f  dup
0x14da0  ldc.i4.3
0x14da1  ldstr    aLoginschemeSim// "LoginScheme_Simple"
0x14da6  stelem.ref
0x14da7  dup
0x14da8  ldc.i4.4
0x14da9  ldstr    aLoginschemeCla// "LoginScheme_Classic"
0x14dae  stelem.ref
0x14daf  dup
0x14db0  ldc.i4.5
0x14db1  ldstr    aLoginschemeCol// "LoginScheme_Colorful"
0x14db6  stelem.ref
0x14db7  stsfld   string[] System.Web.UI.Design.WebControls.AutoFormatSchemes::LOGIN_SCHEME_NAMES
0x14dbc  ldc.i4.5
0x14dbd  newarr   [mscorlib]System.String
0x14dc2  dup
0x14dc3  ldc.i4.0
0x14dc4  ldstr    aMenuschemeEmpt// "MenuScheme_Empty"
0x14dc9  stelem.ref
0x14dca  dup
0x14dcb  ldc.i4.1
0x14dcc  ldstr    aMenuschemeClas// "MenuScheme_Classic"
0x14dd1  stelem.ref
0x14dd2  dup
0x14dd3  ldc.i4.2
0x14dd4  ldstr    aMenuschemeColo// "MenuScheme_Colorful"
0x14dd9  stelem.ref
0x14dda  dup
0x14ddb  ldc.i4.3
0x14ddc  ldstr    aMenuschemeProf// "MenuScheme_Professional"
0x14de1  stelem.ref
0x14de2  dup
0x14de3  ldc.i4.4
0x14de4  ldstr    aMenuschemeSimp// "MenuScheme_Simple"
0x14de9  stelem.ref
0x14dea  stsfld   string[] System.Web.UI.Design.WebControls.AutoFormatSchemes::MENU_SCHEME_NAMES
0x14def  ldc.i4.6
0x14df0  newarr   [mscorlib]System.String
0x14df5  dup
0x14df6  ldc.i4.0
0x14df7  ldstr    aChangepassword// "ChangePasswordScheme_Empty"
0x14dfc  stelem.ref
0x14dfd  dup
0x14dfe  ldc.i4.1
0x14dff  ldstr    aChangepassword_0// "ChangePasswordScheme_Elegant"
0x14e04  stelem.ref
0x14e05  dup
0x14e06  ldc.i4.2
0x14e07  ldstr    aChangepassword_1// "ChangePasswordScheme_Professional"
0x14e0c  stelem.ref
0x14e0d  dup
0x14e0e  ldc.i4.3
0x14e0f  ldstr    aChangepassword_2// "ChangePasswordScheme_Simple"
  ... truncated ...
```
