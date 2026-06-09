# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x1800121c9`
- end: `0x1800121e9`
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
0x1800121c9  push    rbp
0x1800121cb  sub     rsp, 20h
0x1800121cf  mov     rbp, rdx
0x1800121d2  mov     rax, [rcx]
0x1800121d5  xor     ecx, ecx
0x1800121d7  cmp     dword ptr [rax], 0C0000017h
0x1800121dd  setz    cl
0x1800121e0  mov     eax, ecx
0x1800121e2  add     rsp, 20h
0x1800121e6  pop     rbp
0x1800121e7  retn
```
