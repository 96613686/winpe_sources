# operator delete(void *)

- ea: `0x180009a30`
- end: `0x180009a44`
- name: `??3@YAXPEAX@Z`
- size: `20`
- prototype: `void __fastcall(void *)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800017e0`
- `0x18000bb9d`
- `0x18000bbaf`
- `0x18000bc1b`
- `0x18000bc53`
- `0x18000be06`
- `0x18000bede`
- `0x18000c076`

## callees

- `0x180009a30`

## import_xrefs

- `msvcrt!free` at `0x180009a39`
- `msvcrt!free` at `0x180009a39`

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
0x180009a30  sub     rsp, 28h
0x180009a34  test    rcx, rcx
0x180009a37  jz      short loc_180009A3F
0x180009a39  call    cs:__imp_free
0x180009a3f  add     rsp, 28h
0x180009a43  retn
```
