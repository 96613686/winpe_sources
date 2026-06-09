# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180011221`
- end: `0x180011241`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: `_BOOL8 __fastcall(_DWORD **)`
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
0x180011221  push    rbp
0x180011223  sub     rsp, 20h
0x180011227  mov     rbp, rdx
0x18001122a  mov     rax, [rcx]
0x18001122d  xor     ecx, ecx
0x18001122f  cmp     dword ptr [rax], 0C0000017h
0x180011235  setz    cl
0x180011238  mov     eax, ecx
0x18001123a  add     rsp, 20h
0x18001123e  pop     rbp
0x18001123f  retn
```
