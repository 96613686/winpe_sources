# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000bc2d`
- end: `0x18000bc4d`
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
0x18000bc2d  push    rbp
0x18000bc2f  sub     rsp, 20h
0x18000bc33  mov     rbp, rdx
0x18000bc36  mov     rax, [rcx]
0x18000bc39  xor     ecx, ecx
0x18000bc3b  cmp     dword ptr [rax], 0C0000017h
0x18000bc41  setz    cl
0x18000bc44  mov     eax, ecx
0x18000bc46  add     rsp, 20h
0x18000bc4a  pop     rbp
0x18000bc4b  retn
```
