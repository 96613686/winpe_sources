# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x1400094d1`
- end: `0x1400094f1`
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
0x1400094d1  push    rbp
0x1400094d3  sub     rsp, 20h
0x1400094d7  mov     rbp, rdx
0x1400094da  mov     rax, [rcx]
0x1400094dd  xor     ecx, ecx
0x1400094df  cmp     dword ptr [rax], 0C0000017h
0x1400094e5  setz    cl
0x1400094e8  mov     eax, ecx
0x1400094ea  add     rsp, 20h
0x1400094ee  pop     rbp
0x1400094ef  retn
```
