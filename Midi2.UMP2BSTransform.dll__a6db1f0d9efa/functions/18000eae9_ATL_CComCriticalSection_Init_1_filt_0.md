# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000eae9`
- end: `0x18000eb09`
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
0x18000eae9  push    rbp
0x18000eaeb  sub     rsp, 20h
0x18000eaef  mov     rbp, rdx
0x18000eaf2  mov     rax, [rcx]
0x18000eaf5  xor     ecx, ecx
0x18000eaf7  cmp     dword ptr [rax], 0C0000017h
0x18000eafd  setz    cl
0x18000eb00  mov     eax, ecx
0x18000eb02  add     rsp, 20h
0x18000eb06  pop     rbp
0x18000eb07  retn
```
