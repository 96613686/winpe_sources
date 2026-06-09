# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180023107`
- end: `0x180023127`
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
0x180023107  push    rbp
0x180023109  sub     rsp, 20h
0x18002310d  mov     rbp, rdx
0x180023110  mov     rax, [rcx]
0x180023113  xor     ecx, ecx
0x180023115  cmp     dword ptr [rax], 0C0000017h
0x18002311b  setz    cl
0x18002311e  mov     eax, ecx
0x180023120  add     rsp, 20h
0x180023124  pop     rbp
0x180023125  retn
```
