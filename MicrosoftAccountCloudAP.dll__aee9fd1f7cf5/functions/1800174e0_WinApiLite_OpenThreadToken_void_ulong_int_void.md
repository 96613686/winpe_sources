# WinApiLite::OpenThreadToken(void *,ulong,int,void * *)

- ea: `0x1800174e0`
- end: `0x1800174fb`
- name: `?OpenThreadToken@WinApiLite@@UEAAHPEAXKHPEAPEAX@Z`
- size: `27`
- prototype: `__int64 __fastcall(WinApiLite *__hidden this, void *, unsigned int, int, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800174f4`

## pseudocode

```c
BOOL __fastcall WinApiLite::OpenThreadToken(WinApiLite *this, void *a2, DWORD a3, BOOL a4, void **a5)
{
  return OpenThreadToken(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800174e0  mov     eax, r9d
0x1800174e3  mov     r10d, r8d
0x1800174e6  mov     r9, [rsp+arg_20]
0x1800174eb  mov     rcx, rdx
0x1800174ee  mov     r8d, eax
0x1800174f1  mov     edx, r10d
0x1800174f4  jmp     cs:__imp_OpenThreadToken
```
