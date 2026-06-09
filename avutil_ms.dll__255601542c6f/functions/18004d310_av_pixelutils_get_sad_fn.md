# av_pixelutils_get_sad_fn

- ea: `0x18004d310`
- end: `0x18004d32f`
- name: `av_pixelutils_get_sad_fn`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180042ad0`

## string_xrefs

- `0x18004d314`: `pixelutils support is required but libavutil is not compiled with it\n`

## pseudocode

```c
__int64 __fastcall av_pixelutils_get_sad_fn(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  av_log(a4, 16, "pixelutils support is required but libavutil is not compiled with it\n");
  return 0;
}

```

## disassembly

```asm
0x18004d310  sub     rsp, 28h
0x18004d314  lea     r8, aPixelutilsSupp; "pixelutils support is required but liba"...
0x18004d31b  mov     edx, 10h
0x18004d320  mov     rcx, r9
0x18004d323  call    av_log
0x18004d328  xor     eax, eax
0x18004d32a  add     rsp, 28h
0x18004d32e  retn
```
