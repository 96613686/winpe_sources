# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::GetMapPointSite

- ea: `0xbfb0`
- end: `0xc015`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::GetMapPointSite`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xc4b0`

## callees

- `0x7bc0`
- `0xbfb0`

## string_xrefs

- `0xc00d`: `maps.msn.com`

## pseudocode

```c

```

## disassembly

```asm
0xbfb0  ldnull
0xbfb1  stloc.0
0xbfb2  ldstr    aLocationcontro_6// "LocationControl.MapPointSite."
0xbfb7  ldarg.0
0xbfb8  call     string [mscorlib]System.String::Concat(string, string)
0xbfbd  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbfc2  stloc.0
0xbfc3  leave.s  loc_BFC8
0xbfc5  pop
0xbfc6  leave.s  loc_BFC8
0xbfc8  ldloc.0
0xbfc9  brfalse.s loc_BFD3
0xbfcb  ldloc.0
0xbfcc  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbfd1  brtrue.s loc_C002
0xbfd3  ldarg.0
0xbfd4  ldc.i4.s 0x2D
0xbfd6  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xbfdb  ldc.i4.m1
0xbfdc  beq.s    loc_C002
0xbfde  ldstr    aLocationcontro_6// "LocationControl.MapPointSite."
0xbfe3  ldarg.0
0xbfe4  ldc.i4.0
0xbfe5  ldarg.0
0xbfe6  ldc.i4.s 0x2D
0xbfe8  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xbfed  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xbff2  call     string [mscorlib]System.String::Concat(string, string)
0xbff7  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0xbffc  stloc.0
0xbffd  leave.s  loc_C002
0xbfff  pop
0xc000  leave.s  loc_C002
0xc002  ldloc.0
0xc003  brfalse.s loc_C00D
0xc005  ldloc.0
0xc006  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc00b  brtrue.s loc_C013
0xc00d  ldstr    aMapsMsnCom// "maps.msn.com"
0xc012  stloc.0
0xc013  ldloc.0
0xc014  ret
```
