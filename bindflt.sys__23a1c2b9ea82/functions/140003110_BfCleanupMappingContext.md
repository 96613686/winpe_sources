# BfCleanupMappingContext

- ea: `0x140003110`
- end: `0x140003135`
- name: `BfCleanupMappingContext`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f8c0`
- `0x140024260`

## callees

- `0x140020280`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140003122`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003122`

## pseudocode

```c
NTSTATUS __fastcall BfCleanupMappingContext(__int64 a1)
{
  BfClearMappingTable();
  return ExDeleteResourceLite((PERESOURCE)(a1 + 16));
}

```

## disassembly

```asm
0x140003110  push    rbx
0x140003112  sub     rsp, 20h
0x140003116  mov     rbx, rcx
0x140003119  call    BfClearMappingTable
0x14000311e  lea     rcx, [rbx+10h]; Resource
0x140003122  call    cs:__imp_ExDeleteResourceLite
0x140003129  nop     dword ptr [rax+rax+00h]
0x14000312e  add     rsp, 20h
0x140003132  pop     rbx
0x140003133  retn
```
