# SrpDeleteEnterpriseContext

- ea: `0x140005544`
- end: `0x140005561`
- name: `SrpDeleteEnterpriseContext`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c8c`
- `0x140004940`
- `0x14002b5e0`
- `0x14002c338`
- `0x14002c524`

## callees

- `0x140005544`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000554f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000554f`

## pseudocode

```c
void __fastcall SrpDeleteEnterpriseContext(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x140005544  sub     rsp, 28h
0x140005548  test    rcx, rcx
0x14000554b  jz      short loc_14000555B
0x14000554d  xor     edx, edx; Tag
0x14000554f  call    cs:__imp_ExFreePoolWithTag
0x140005556  nop     dword ptr [rax+rax+00h]
0x14000555b  add     rsp, 28h
0x14000555f  retn
```
