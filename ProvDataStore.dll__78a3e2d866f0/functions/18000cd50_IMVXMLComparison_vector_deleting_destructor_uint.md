# IMVXMLComparison::`vector deleting destructor'(uint)

- ea: `0x18000cd50`
- end: `0x18000cd77`
- name: `??_EIMVXMLComparison@@UEAAPEAXI@Z`
- size: `39`
- prototype: `IMVXMLComparison *__fastcall(IMVXMLComparison *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000cd50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd68`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd68`

## pseudocode

```c
IMVXMLComparison *__fastcall IMVXMLComparison::`vector deleting destructor'(IMVXMLComparison *this, char a2)
{
  *(_QWORD *)this = &IMVXMLComparison::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000cd50  push    rbx
0x18000cd52  sub     rsp, 20h
0x18000cd56  lea     rax, ??_7IMVXMLComparison@@6B@; const IMVXMLComparison::`vftable'
0x18000cd5d  mov     rbx, rcx
0x18000cd60  mov     [rcx], rax
0x18000cd63  test    dl, 1
0x18000cd66  jz      short loc_18000CD6E
0x18000cd68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd6e  mov     rax, rbx
0x18000cd71  add     rsp, 20h
0x18000cd75  pop     rbx
0x18000cd76  retn
```
