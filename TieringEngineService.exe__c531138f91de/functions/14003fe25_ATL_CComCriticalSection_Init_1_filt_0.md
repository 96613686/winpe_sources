# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x14003fe25`
- end: `0x14003fe45`
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
0x14003fe25  push    rbp
0x14003fe27  sub     rsp, 20h
0x14003fe2b  mov     rbp, rdx
0x14003fe2e  mov     rax, [rcx]
0x14003fe31  xor     ecx, ecx
0x14003fe33  cmp     dword ptr [rax], 0C0000017h
0x14003fe39  setz    cl
0x14003fe3c  mov     eax, ecx
0x14003fe3e  add     rsp, 20h
0x14003fe42  pop     rbp
0x14003fe43  retn
```
