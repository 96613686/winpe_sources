# System.Web.Http.UriQueryUtility::UrlDecode

- ea: `0xb520`
- end: `0xb531`
- name: `System.Web.Http.UriQueryUtility::UrlDecode`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xd870`
- `0xd8b0`

## callees

- `0xb520`
- `0xb640`

## pseudocode

```c

```

## disassembly

```asm
0xb520  ldarg.0
0xb521  brtrue.s loc_B525
0xb523  ldnull
0xb524  ret
0xb525  ldarg.0
0xb526  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xb52b  call     string System.Web.Http.UriQueryUtility::UrlDecodeInternal(string value, class [mscorlib]System.Text.Encoding encoding)
0xb530  ret
```
