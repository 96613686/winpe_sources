# WinApiLite::OpenThread(ulong,int,ulong)

- ea: `0x1800174c0`
- end: `0x1800174d1`
- name: `?OpenThread@WinApiLite@@UEAAPEAXKHK@Z`
- size: `17`
- prototype: `void *__fastcall(WinApiLite *__hidden this, unsigned int, int, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800174ca`

## pseudocode

```c
HANDLE __fastcall WinApiLite::OpenThread(WinApiLite *this, DWORD a2, BOOL a3, DWORD a4)
{
  return OpenThread(a2, a3, a4);
}

```

## disassembly

```asm
0x1800174c0  mov     eax, r8d
0x1800174c3  mov     ecx, edx
0x1800174c5  mov     edx, eax
0x1800174c7  mov     r8d, r9d
0x1800174ca  jmp     cs:__imp_OpenThread
```
