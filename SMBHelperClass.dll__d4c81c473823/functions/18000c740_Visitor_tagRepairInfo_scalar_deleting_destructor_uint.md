# Visitor<tagRepairInfo *>::`scalar deleting destructor'(uint)

- ea: `0x18000c740`
- end: `0x18000c767`
- name: `??_G?$Visitor@PEAUtagRepairInfo@@@@UEAAPEAXI@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callees

- `0x18000c740`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c758`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c758`

## pseudocode

```c
_QWORD *__fastcall Visitor<tagRepairInfo *>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &Visitor<tagRepairInfo *>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000c740  push    rbx
0x18000c742  sub     rsp, 20h
0x18000c746  lea     rax, ??_7?$Visitor@PEAUtagRepairInfo@@@@6B@; const Visitor<tagRepairInfo *>::`vftable'
0x18000c74d  mov     rbx, rcx
0x18000c750  mov     [rcx], rax
0x18000c753  test    dl, 1
0x18000c756  jz      short loc_18000C75E
0x18000c758  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c75e  mov     rax, rbx
0x18000c761  add     rsp, 20h
0x18000c765  pop     rbx
0x18000c766  retn
```
