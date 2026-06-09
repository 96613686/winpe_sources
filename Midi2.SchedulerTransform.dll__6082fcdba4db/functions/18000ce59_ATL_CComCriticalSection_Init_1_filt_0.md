# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000ce59`
- end: `0x18000ce79`
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
0x18000ce59  push    rbp
0x18000ce5b  sub     rsp, 20h
0x18000ce5f  mov     rbp, rdx
0x18000ce62  mov     rax, [rcx]
0x18000ce65  xor     ecx, ecx
0x18000ce67  cmp     dword ptr [rax], 0C0000017h
0x18000ce6d  setz    cl
0x18000ce70  mov     eax, ecx
0x18000ce72  add     rsp, 20h
0x18000ce76  pop     rbp
0x18000ce77  retn
```
