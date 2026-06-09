# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000e681`
- end: `0x18000e6a1`
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
0x18000e681  push    rbp
0x18000e683  sub     rsp, 20h
0x18000e687  mov     rbp, rdx
0x18000e68a  mov     rax, [rcx]
0x18000e68d  xor     ecx, ecx
0x18000e68f  cmp     dword ptr [rax], 0C0000017h
0x18000e695  setz    cl
0x18000e698  mov     eax, ecx
0x18000e69a  add     rsp, 20h
0x18000e69e  pop     rbp
0x18000e69f  retn
```
