# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000cb30`
- end: `0x18000cb50`
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
0x18000cb30  push    rbp
0x18000cb32  sub     rsp, 20h
0x18000cb36  mov     rbp, rdx
0x18000cb39  mov     rax, [rcx]
0x18000cb3c  xor     ecx, ecx
0x18000cb3e  cmp     dword ptr [rax], 0C0000017h
0x18000cb44  setz    cl
0x18000cb47  mov     eax, ecx
0x18000cb49  add     rsp, 20h
0x18000cb4d  pop     rbp
0x18000cb4e  retn
```
