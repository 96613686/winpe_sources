# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x140012038`
- end: `0x140012058`
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
0x140012038  push    rbp
0x14001203a  sub     rsp, 20h
0x14001203e  mov     rbp, rdx
0x140012041  mov     rax, [rcx]
0x140012044  xor     ecx, ecx
0x140012046  cmp     dword ptr [rax], 0C0000017h
0x14001204c  setz    cl
0x14001204f  mov     eax, ecx
0x140012051  add     rsp, 20h
0x140012055  pop     rbp
0x140012056  retn
```
