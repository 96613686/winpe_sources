# DeleteTempFileOnShutdownEx

- ea: `0x18000ae00`
- end: `0x18000ae15`
- name: `DeleteTempFileOnShutdownEx`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a420`

## pseudocode

```c
__int64 __fastcall DeleteTempFileOnShutdownEx(const unsigned __int16 *a1)
{
  return AppendTempFileList((void **)&g_pTempFileHead, a1, 1);
}

```

## disassembly

```asm
0x18000ae00  mov     rdx, rcx
0x18000ae03  mov     r8d, 1
0x18000ae09  lea     rcx, ?g_pTempFileHead@@3PEAVTEMPFILELIST@@EA; TEMPFILELIST * g_pTempFileHead
0x18000ae10  jmp     AppendTempFileList
```
