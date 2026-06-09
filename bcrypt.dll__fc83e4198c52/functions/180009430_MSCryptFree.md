# MSCryptFree

- ea: `0x180009430`
- end: `0x180009449`
- name: `MSCryptFree`
- size: `25`
- prototype: `BOOLEAN __fastcall(void *)`
- caller_count: `36`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001590`
- `0x180004390`
- `0x1800050b0`
- `0x180005bc0`
- `0x180006020`
- `0x180006bd0`
- `0x180006da0`
- `0x1800070d0`
- `0x180008890`
- `0x1800090a0`
- `0x180009570`
- `0x180009764`
- `0x18000a070`
- `0x18000a230`
- `0x18000a3e8`
- `0x18000acc0`
- `0x18000b1d0`
- `0x18000b680`
- `0x18000ccf0`
- `0x18000e368`
- `0x18000e628`
- `0x18000edac`
- `0x18000f1fc`
- `0x18001267c`
- `0x180012a70`
- `0x180012cc4`
- `0x180014320`
- `0x180014f98`
- `0x1800164bc`
- `0x180016564`
- `0x1800168c8`
- `0x180016b60`
- `0x180016efc`
- `0x1800171b4`
- `0x180017420`
- `0x18001a3cc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180009442`

## pseudocode

```c
BOOLEAN __fastcall MSCryptFree(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180009430  mov     rax, gs:60h
0x180009439  mov     r8, rcx
0x18000943c  xor     edx, edx
0x18000943e  mov     rcx, [rax+30h]
0x180009442  jmp     cs:__imp_RtlFreeHeap
```
