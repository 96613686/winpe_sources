# System.Web.UI.Design.WebControls.RegexEditorDialog::.cctor

- ea: `0x33d70`
- end: `0x33e58`
- name: `System.Web.UI.Design.WebControls.RegexEditorDialog::.cctor`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xfce30`

## string_xrefs

- `0x33d79`: `RegexCanned_SocialSecurity`
- `0x33d7e`: `RegexCanned_SocialSecurity_Format`
- `0x33e42`: `RegexCanned_PrcSocialSecurity`
- `0x33e47`: `RegexCanned_PrcSocialSecurity_Format`

## pseudocode

```c

```

## disassembly

```asm
0x33d70  ldc.i4.s 0xC
0x33d72  newarr   RegExpEntry
0x33d77  dup
0x33d78  ldc.i4.0
0x33d79  ldstr    aRegexcannedSoc// "RegexCanned_SocialSecurity"
0x33d7e  ldstr    aRegexcannedSoc_0// "RegexCanned_SocialSecurity_Format"
0x33d83  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33d88  stelem.ref
0x33d89  dup
0x33d8a  ldc.i4.1
0x33d8b  ldstr    aRegexcannedUsp// "RegexCanned_USPhone"
0x33d90  ldstr    aRegexcannedUsp_0// "RegexCanned_USPhone_Format"
0x33d95  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33d9a  stelem.ref
0x33d9b  dup
0x33d9c  ldc.i4.2
0x33d9d  ldstr    aRegexcannedZip// "RegexCanned_Zip"
0x33da2  ldstr    aRegexcannedZip_0// "RegexCanned_Zip_Format"
0x33da7  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33dac  stelem.ref
0x33dad  dup
0x33dae  ldc.i4.3
0x33daf  ldstr    aRegexcannedFrz// "RegexCanned_FrZip"
0x33db4  ldstr    aRegexcannedFrz_0// "RegexCanned_FrZip_Format"
0x33db9  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33dbe  stelem.ref
0x33dbf  dup
0x33dc0  ldc.i4.4
0x33dc1  ldstr    aRegexcannedFrp// "RegexCanned_FrPhone"
0x33dc6  ldstr    aRegexcannedFrp_0// "RegexCanned_FrPhone_Format"
0x33dcb  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33dd0  stelem.ref
0x33dd1  dup
0x33dd2  ldc.i4.5
0x33dd3  ldstr    aRegexcannedDez// "RegexCanned_DeZip"
0x33dd8  ldstr    aRegexcannedDez_0// "RegexCanned_DeZip_Format"
0x33ddd  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33de2  stelem.ref
0x33de3  dup
0x33de4  ldc.i4.6
0x33de5  ldstr    aRegexcannedDep// "RegexCanned_DePhone"
0x33dea  ldstr    aRegexcannedDep_0// "RegexCanned_DePhone_Format"
0x33def  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33df4  stelem.ref
0x33df5  dup
0x33df6  ldc.i4.7
0x33df7  ldstr    aRegexcannedJpn// "RegexCanned_JpnZip"
0x33dfc  ldstr    aRegexcannedJpn_0// "RegexCanned_JpnZip_Format"
0x33e01  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33e06  stelem.ref
0x33e07  dup
0x33e08  ldc.i4.8
0x33e09  ldstr    aRegexcannedJpn_1// "RegexCanned_JpnPhone"
0x33e0e  ldstr    aRegexcannedJpn_2// "RegexCanned_JpnPhone_Format"
0x33e13  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33e18  stelem.ref
0x33e19  dup
0x33e1a  ldc.i4.s 9
0x33e1c  ldstr    aRegexcannedPrc// "RegexCanned_PrcZip"
0x33e21  ldstr    aRegexcannedPrc_0// "RegexCanned_PrcZip_Format"
0x33e26  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33e2b  stelem.ref
0x33e2c  dup
0x33e2d  ldc.i4.s 0xA
0x33e2f  ldstr    aRegexcannedPrc_1// "RegexCanned_PrcPhone"
0x33e34  ldstr    aRegexcannedPrc_2// "RegexCanned_PrcPhone_Format"
0x33e39  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33e3e  stelem.ref
0x33e3f  dup
0x33e40  ldc.i4.s 0xB
0x33e42  ldstr    aRegexcannedPrc_3// "RegexCanned_PrcSocialSecurity"
0x33e47  ldstr    aRegexcannedPrc_4// "RegexCanned_PrcSocialSecurity_Format"
0x33e4c  newobj   instance void RegExpEntry::.ctor(string name, string format)
0x33e51  stelem.ref
0x33e52  stsfld   class RegExpEntry[] System.Web.UI.Design.WebControls.RegexEditorDialog::_entries
0x33e57  ret
```
