# operator delete(void *)

- ea: `0x180001d78`
- end: `0x180001d8b`
- name: `??3@YAXPEAX@Z`
- size: `19`
- prototype: `void __fastcall(void *)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800015f0`
- `0x18002e77c`
- `0x18002e932`
- `0x18002e944`
- `0x18002e956`
- `0x18002ea68`
- `0x18002ec37`
- `0x18002eeda`

## callees

- `0x180001d78`
- `0x180001dd8`

## pseudocode

```c
void __fastcall operator delete(unsigned __int8 *a1)
{
  if ( a1 )
    MMMFree(a1);
}

```

## disassembly

```asm
0x180001d78  sub     rsp, 28h
0x180001d7c  test    rcx, rcx
0x180001d7f  jz      short loc_180001D86
0x180001d81  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180001d86  add     rsp, 28h
0x180001d8a  retn
```
