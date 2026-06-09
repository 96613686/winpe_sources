# __FlushThread_::_1_::catch$3

- ea: `0x180013995`
- end: `0x1800139dd`
- name: `__FlushThread_::_1_::catch$3`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006dd8`
- `0x18000dc8c`
- `0x18001280a`

## string_xrefs

- `0x1800139be`: `The FlushThread hit the exception (%d). The process will be terminated`

## pseudocode

```c
void __fastcall __noreturn _FlushThread_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = 0;
  memset_0((void *)(a2 + 52), 0, 0x3FCu);
  TracedStringCchPrintfW(
    (unsigned __int16 *)(a2 + 48),
    0x200u,
    L"The FlushThread hit the exception (%d). The process will be terminated",
    *(unsigned int *)(a2 + 44));
  DtcInternalErrorW((const unsigned __int16 *)(a2 + 48));
}

```

## disassembly

```asm
0x180013995  mov     [rsp+arg_8], rdx
0x18001399a  push    rbp
0x18001399b  sub     rsp, 20h
0x18001399f  mov     rbp, rdx
0x1800139a2  mov     dword ptr [rbp+30h], 0
0x1800139a9  xor     edx, edx; Val
0x1800139ab  mov     r8d, 3FCh; Size
0x1800139b1  lea     rcx, [rbp+34h]; void *
0x1800139b5  call    memset_0
0x1800139ba  mov     r9d, [rbp+2Ch]
0x1800139be  lea     r8, aTheFlushthread; "The FlushThread hit the exception (%d)."...
0x1800139c5  mov     edx, 200h; unsigned __int64
0x1800139ca  lea     rcx, [rbp+30h]; unsigned __int16 *
0x1800139ce  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800139d3  lea     rcx, [rbp+30h]; unsigned __int16 *
0x1800139d7  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
