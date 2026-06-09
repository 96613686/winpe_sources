# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18001428a`
- end: `0x1800142aa`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall ATL::CComCriticalSection::Init_::_1_::filt_0(_DWORD **a1)
{
  return **a1 == -1073741801;
}

```

## disassembly

```asm
0x18001428a  push    rbp
0x18001428c  sub     rsp, 20h
0x180014290  mov     rbp, rdx
0x180014293  mov     rax, [rcx]
0x180014296  xor     ecx, ecx
0x180014298  cmp     dword ptr [rax], 0C0000017h
0x18001429e  setz    cl
0x1800142a1  mov     eax, ecx
0x1800142a3  add     rsp, 20h
0x1800142a7  pop     rbp
0x1800142a8  retn
```
