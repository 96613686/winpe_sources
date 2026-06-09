# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18001234c`
- end: `0x18001236c`
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
0x18001234c  push    rbp
0x18001234e  sub     rsp, 20h
0x180012352  mov     rbp, rdx
0x180012355  mov     rax, [rcx]
0x180012358  xor     ecx, ecx
0x18001235a  cmp     dword ptr [rax], 0C0000017h
0x180012360  setz    cl
0x180012363  mov     eax, ecx
0x180012365  add     rsp, 20h
0x180012369  pop     rbp
0x18001236a  retn
```
