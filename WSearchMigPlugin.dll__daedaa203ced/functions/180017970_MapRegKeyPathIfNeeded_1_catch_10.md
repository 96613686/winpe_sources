# _MapRegKeyPathIfNeeded_::_1_::catch$10

- ea: `0x180017970`
- end: `0x1800179bf`
- name: `_MapRegKeyPathIfNeeded_::_1_::catch$10`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800091e4`
- `0x180011220`
- `0x180013c50`

## string_xrefs

- `0x180017988`: `WSMIG - Exception in MapRegKeyPathIfNeeded, HRESULT=%08x`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall MapRegKeyPathIfNeeded_::_1_::catch_10(__int64 a1, __int64 a2)
{
  StringCchPrintfW(
    (wchar_t *)(a2 + 176),
    0x208u,
    L"WSMIG - Exception in MapRegKeyPathIfNeeded, HRESULT=%08x",
    *(unsigned int *)(*(_QWORD *)(a2 + 160) + 8LL));
  WSMigLog(*(_QWORD *)(a2 + 96), a2 + 176);
  return &loc_18001150D;
}

```

## disassembly

```asm
0x180017970  mov     [rsp+arg_8], rdx
0x180017975  push    rbp
0x180017976  sub     rsp, 40h
0x18001797a  mov     rbp, rdx
0x18001797d  mov     r9, [rbp+0A0h]
0x180017984  mov     r9d, [r9+8]
0x180017988  lea     r8, aWsmigException; "WSMIG - Exception in MapRegKeyPathIfNee"...
0x18001798f  mov     edx, 208h; unsigned __int64
0x180017994  lea     rcx, [rbp+0B0h]; wchar_t *
0x18001799b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800179a0  lea     rdx, [rbp+0B0h]
0x1800179a7  mov     rcx, [rbp+60h]
0x1800179ab  call    WSMigLog
0x1800179b0  nop
0x1800179b1  lea     rax, loc_18001150D
0x1800179b8  add     rsp, 40h
0x1800179bc  pop     rbp
0x1800179bd  retn
```
