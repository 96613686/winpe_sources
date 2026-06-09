# operator delete(void *)

- ea: `0x180002220`
- end: `0x180002234`
- name: `??3@YAXPEAX@Z`
- size: `20`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800014a4`
- `0x180001580`

## callees

- `0x180002220`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002229`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002229`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    free(a1);
}

```

## disassembly

```asm
0x180002220  sub     rsp, 28h
0x180002224  test    rcx, rcx
0x180002227  jz      short loc_18000222F
0x180002229  call    cs:__imp_free
0x18000222f  add     rsp, 28h
0x180002233  retn
```
