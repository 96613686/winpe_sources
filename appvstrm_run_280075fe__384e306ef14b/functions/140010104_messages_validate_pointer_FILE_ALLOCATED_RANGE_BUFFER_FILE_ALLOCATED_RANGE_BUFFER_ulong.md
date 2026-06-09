# messages::validate_pointer<_FILE_ALLOCATED_RANGE_BUFFER>(_FILE_ALLOCATED_RANGE_BUFFER *,ulong)

- ea: `0x140010104`
- end: `0x140010128`
- name: `??$validate_pointer@U_FILE_ALLOCATED_RANGE_BUFFER@@@messages@@YA_NPEAU_FILE_ALLOCATED_RANGE_BUFFER@@K@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001104c`
- `0x140011928`

## callees

- `0x140010104`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140010110`
- `ntoskrnl!ProbeForRead` at `0x140010110`

## pseudocode

```c
char __fastcall messages::validate_pointer<_FILE_ALLOCATED_RANGE_BUFFER>(volatile void *a1, unsigned int a2)
{
  ProbeForRead(a1, a2, 1u);
  return 1;
}

```

## disassembly

```asm
0x140010104  sub     rsp, 28h
0x140010108  mov     edx, edx; Length
0x14001010a  mov     r8d, 1; Alignment
0x140010110  call    cs:__imp_ProbeForRead
0x140010117  nop     dword ptr [rax+rax+00h]
0x14001011c  mov     al, 1
0x14001011e  jmp     short loc_140010122
0x140010120  xor     al, al
0x140010122  add     rsp, 28h
0x140010126  retn
```
