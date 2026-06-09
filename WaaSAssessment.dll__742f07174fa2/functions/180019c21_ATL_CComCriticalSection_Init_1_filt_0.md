# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180019c21`
- end: `0x180019c41`
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
0x180019c21  push    rbp
0x180019c23  sub     rsp, 20h
0x180019c27  mov     rbp, rdx
0x180019c2a  mov     rax, [rcx]
0x180019c2d  xor     ecx, ecx
0x180019c2f  cmp     dword ptr [rax], 0C0000017h
0x180019c35  setz    cl
0x180019c38  mov     eax, ecx
0x180019c3a  add     rsp, 20h
0x180019c3e  pop     rbp
0x180019c3f  retn
```
