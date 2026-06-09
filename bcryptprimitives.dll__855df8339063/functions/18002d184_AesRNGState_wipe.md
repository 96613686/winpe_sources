# AesRNGState_wipe

- ea: `0x18002d184`
- end: `0x18002d1ae`
- name: `AesRNGState_wipe`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d100`
- `0x18002eb90`
- `0x18002f010`

## callees

- `0x18002d264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d1a2`

## pseudocode

```c
void __fastcall AesRNGState_wipe(__int64 a1)
{
  SymCryptRngAesUninstantiate(a1 + 16);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
}

```

## disassembly

```asm
0x18002d184  push    rbx
0x18002d186  sub     rsp, 20h
0x18002d18a  mov     rbx, rcx
0x18002d18d  add     rcx, 10h
0x18002d191  call    SymCryptRngAesUninstantiate
0x18002d196  lea     rcx, [rbx+80h]
0x18002d19d  add     rsp, 20h
0x18002d1a1  pop     rbx
0x18002d1a2  jmp     cs:__imp_DeleteCriticalSection
```
