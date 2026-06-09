# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000989f`
- end: `0x1800098bf`
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
0x18000989f  push    rbp
0x1800098a1  sub     rsp, 20h
0x1800098a5  mov     rbp, rdx
0x1800098a8  mov     rax, [rcx]
0x1800098ab  xor     ecx, ecx
0x1800098ad  cmp     dword ptr [rax], 0C0000017h
0x1800098b3  setz    cl
0x1800098b6  mov     eax, ecx
0x1800098b8  add     rsp, 20h
0x1800098bc  pop     rbp
0x1800098bd  retn
```
