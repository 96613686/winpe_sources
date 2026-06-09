# System.Web.Http.UriQueryUtility::UrlEncode

- ea: `0xb4f0`
- end: `0xb517`
- name: `System.Web.Http.UriQueryUtility::UrlEncode`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb130`

## callees

- `0xb4f0`
- `0xb540`

## pseudocode

```c

```

## disassembly

```asm
0xb4f0  ldarg.0
0xb4f1  brtrue.s loc_B4F5
0xb4f3  ldnull
0xb4f4  ret
0xb4f5  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xb4fa  ldarg.0
0xb4fb  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xb500  stloc.0
0xb501  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0xb506  ldloc.0
0xb507  ldc.i4.0
0xb508  ldloc.0
0xb509  ldlen
0xb50a  conv.i4
0xb50b  ldc.i4.0
0xb50c  call     unsigned int8[] System.Web.Http.UriQueryUtility::UrlEncode(unsigned int8[] bytes, int32 offset, int32 count, bool alwaysCreateNewReturnValue)
0xb511  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0xb516  ret
```
