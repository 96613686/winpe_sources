# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000a1a2`
- end: `0x18000a1c2`
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
0x18000a1a2  push    rbp
0x18000a1a4  sub     rsp, 20h
0x18000a1a8  mov     rbp, rdx
0x18000a1ab  mov     rax, [rcx]
0x18000a1ae  xor     ecx, ecx
0x18000a1b0  cmp     dword ptr [rax], 0C0000017h
0x18000a1b6  setz    cl
0x18000a1b9  mov     eax, ecx
0x18000a1bb  add     rsp, 20h
0x18000a1bf  pop     rbp
0x18000a1c0  retn
```
