# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x180021c94`
- end: `0x180021cfb`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180021b34`

## callees

- `0x180021c68`
- `0x180021c94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021cb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021ca4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021ca4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021ccd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021cde`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021cde`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x180021c94  push    rbx
0x180021c96  sub     rsp, 20h
0x180021c9a  mov     rbx, r8
0x180021c9d  mov     qword ptr [r8], 0
0x180021ca4  call    cs:__imp_GetCurrentThread
0x180021caa  xor     r8d, r8d; OpenAsSelf
0x180021cad  mov     r9, rbx; TokenHandle
0x180021cb0  mov     rcx, rax; ThreadHandle
0x180021cb3  lea     edx, [r8+8]; DesiredAccess
0x180021cb7  call    cs:__imp_OpenThreadToken
0x180021cbd  test    eax, eax
0x180021cbf  jnz     short loc_180021CE8
0x180021cc1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021cc6  cmp     eax, 800703F0h
0x180021ccb  jnz     short loc_180021CF5
0x180021ccd  call    cs:__imp_GetCurrentProcess
0x180021cd3  mov     r8, rbx; TokenHandle
0x180021cd6  mov     edx, 8; DesiredAccess
0x180021cdb  mov     rcx, rax; ProcessHandle
0x180021cde  call    cs:__imp_OpenProcessToken
0x180021ce4  test    eax, eax
0x180021ce6  jz      short loc_180021CF0
0x180021ce8  xor     eax, eax
0x180021cea  add     rsp, 20h
0x180021cee  pop     rbx
0x180021cef  retn
0x180021cf0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021cf5  add     rsp, 20h
0x180021cf9  pop     rbx
0x180021cfa  retn
```
