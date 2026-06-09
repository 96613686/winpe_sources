# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000ae76`
- end: `0x18000ae96`
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
0x18000ae76  push    rbp
0x18000ae78  sub     rsp, 20h
0x18000ae7c  mov     rbp, rdx
0x18000ae7f  mov     rax, [rcx]
0x18000ae82  xor     ecx, ecx
0x18000ae84  cmp     dword ptr [rax], 0C0000017h
0x18000ae8a  setz    cl
0x18000ae8d  mov     eax, ecx
0x18000ae8f  add     rsp, 20h
0x18000ae93  pop     rbp
0x18000ae94  retn
```
