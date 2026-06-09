# WinApiLite::OpenProcessToken(void *,ulong,void * *)

- ea: `0x1800174a0`
- end: `0x1800174b2`
- name: `?OpenProcessToken@WinApiLite@@UEAAHPEAXKPEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(WinApiLite *__hidden this, void *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800174ab`

## pseudocode

```c
BOOL __fastcall WinApiLite::OpenProcessToken(WinApiLite *this, void *a2, DWORD a3, void **a4)
{
  return OpenProcessToken(a2, a3, a4);
}

```

## disassembly

```asm
0x1800174a0  mov     eax, r8d
0x1800174a3  mov     rcx, rdx
0x1800174a6  mov     edx, eax
0x1800174a8  mov     r8, r9
0x1800174ab  jmp     cs:__imp_OpenProcessToken
```
