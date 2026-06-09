# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180019a20`
- end: `0x180019a40`
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
0x180019a20  push    rbp
0x180019a22  sub     rsp, 20h
0x180019a26  mov     rbp, rdx
0x180019a29  mov     rax, [rcx]
0x180019a2c  xor     ecx, ecx
0x180019a2e  cmp     dword ptr [rax], 0C0000017h
0x180019a34  setz    cl
0x180019a37  mov     eax, ecx
0x180019a39  add     rsp, 20h
0x180019a3d  pop     rbp
0x180019a3e  retn
```
