# av_rescale_q

- ea: `0x18001bc66`
- end: `0x18001bc6c`
- name: `av_rescale_q`
- size: `6`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180006390`
- `0x180009cfc`
- `0x18000bc10`
- `0x18000bf38`
- `0x18000c39c`
- `0x180012f60`
- `0x180013214`
- `0x180013be0`
- `0x180013ec8`
- `0x180014004`
- `0x180019d40`

## import_xrefs

- `avutil_ms!av_rescale_q` at `0x18001bc66`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_rescale_q(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_av_rescale_q(a1, a2, a3);
}

```

## disassembly

```asm
0x18001bc66  jmp     cs:__imp_av_rescale_q
```
