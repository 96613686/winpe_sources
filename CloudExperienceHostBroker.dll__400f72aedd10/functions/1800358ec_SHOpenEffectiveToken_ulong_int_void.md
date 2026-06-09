# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800358ec`
- end: `0x180035953`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180035794`

## callees

- `0x180035768`
- `0x1800358ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800358fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800358fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003590f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003590f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035936`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035925`

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
0x1800358ec  push    rbx
0x1800358ee  sub     rsp, 20h
0x1800358f2  mov     rbx, r8
0x1800358f5  mov     qword ptr [r8], 0
0x1800358fc  call    cs:__imp_GetCurrentThread
0x180035902  xor     r8d, r8d; OpenAsSelf
0x180035905  mov     r9, rbx; TokenHandle
0x180035908  mov     rcx, rax; ThreadHandle
0x18003590b  lea     edx, [r8+8]; DesiredAccess
0x18003590f  call    cs:__imp_OpenThreadToken
0x180035915  test    eax, eax
0x180035917  jnz     short loc_180035940
0x180035919  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003591e  cmp     eax, 800703F0h
0x180035923  jnz     short loc_18003594D
0x180035925  call    cs:__imp_GetCurrentProcess
0x18003592b  mov     r8, rbx; TokenHandle
0x18003592e  mov     edx, 8; DesiredAccess
0x180035933  mov     rcx, rax; ProcessHandle
0x180035936  call    cs:__imp_OpenProcessToken
0x18003593c  test    eax, eax
0x18003593e  jz      short loc_180035948
0x180035940  xor     eax, eax
0x180035942  add     rsp, 20h
0x180035946  pop     rbx
0x180035947  retn
0x180035948  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003594d  add     rsp, 20h
0x180035951  pop     rbx
0x180035952  retn
```
