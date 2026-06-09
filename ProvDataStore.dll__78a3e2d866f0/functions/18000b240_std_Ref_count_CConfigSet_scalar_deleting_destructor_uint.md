# std::_Ref_count<CConfigSet>::`scalar deleting destructor'(uint)

- ea: `0x18000b240`
- end: `0x18000b267`
- name: `??_G?$_Ref_count@VCConfigSet@@@std@@UEAAPEAXI@Z`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18000b240`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b258`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b258`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count<CConfigSet>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &std::_Ref_count_base::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b240  push    rbx
0x18000b242  sub     rsp, 20h
0x18000b246  lea     rax, ??_7_Ref_count_base@std@@6B@; const std::_Ref_count_base::`vftable'
0x18000b24d  mov     rbx, rcx
0x18000b250  mov     [rcx], rax
0x18000b253  test    dl, 1
0x18000b256  jz      short loc_18000B25E
0x18000b258  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b25e  mov     rax, rbx
0x18000b261  add     rsp, 20h
0x18000b265  pop     rbx
0x18000b266  retn
```
