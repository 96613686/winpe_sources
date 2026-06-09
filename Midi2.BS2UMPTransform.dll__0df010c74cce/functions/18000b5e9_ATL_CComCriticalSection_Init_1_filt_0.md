# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000b5e9`
- end: `0x18000b609`
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
0x18000b5e9  push    rbp
0x18000b5eb  sub     rsp, 20h
0x18000b5ef  mov     rbp, rdx
0x18000b5f2  mov     rax, [rcx]
0x18000b5f5  xor     ecx, ecx
0x18000b5f7  cmp     dword ptr [rax], 0C0000017h
0x18000b5fd  setz    cl
0x18000b600  mov     eax, ecx
0x18000b602  add     rsp, 20h
0x18000b606  pop     rbp
0x18000b607  retn
```
