# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000edb2`
- end: `0x18000edd2`
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
0x18000edb2  push    rbp
0x18000edb4  sub     rsp, 20h
0x18000edb8  mov     rbp, rdx
0x18000edbb  mov     rax, [rcx]
0x18000edbe  xor     ecx, ecx
0x18000edc0  cmp     dword ptr [rax], 0C0000017h
0x18000edc6  setz    cl
0x18000edc9  mov     eax, ecx
0x18000edcb  add     rsp, 20h
0x18000edcf  pop     rbp
0x18000edd0  retn
```
