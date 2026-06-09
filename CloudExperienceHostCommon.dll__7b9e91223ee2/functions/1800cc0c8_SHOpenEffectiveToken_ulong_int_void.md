# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800cc0c8`
- end: `0x1800cc15e`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `150`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800cc164`

## callees

- `0x1800cbce4`
- `0x1800cc0c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cc0d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cc105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cc0d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cc105`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cc141`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cc141`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cc0eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cc11a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cc0eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cc11a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cc130`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cc130`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE v6; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return result;
  if ( (_DWORD)result == -2147024891 )
  {
    v6 = GetCurrentThread();
    if ( !OpenThreadToken(v6, 0x28u, 1, a3) )
    {
      result = ResultFromKnownLastError();
      goto LABEL_6;
    }
    return 0;
  }
LABEL_6:
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1800cc0c8  push    rbx
0x1800cc0ca  sub     rsp, 20h
0x1800cc0ce  mov     rbx, r8
0x1800cc0d1  mov     qword ptr [r8], 0
0x1800cc0d8  call    cs:__imp_GetCurrentThread
0x1800cc0de  xor     r8d, r8d; OpenAsSelf
0x1800cc0e1  mov     r9, rbx; TokenHandle
0x1800cc0e4  mov     rcx, rax; ThreadHandle
0x1800cc0e7  lea     edx, [r8+28h]; DesiredAccess
0x1800cc0eb  call    cs:__imp_OpenThreadToken
0x1800cc0f1  test    eax, eax
0x1800cc0f3  jnz     short loc_1800CC14B
0x1800cc0f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800cc0fa  test    eax, eax
0x1800cc0fc  jns     short loc_1800CC158
0x1800cc0fe  cmp     eax, 80070005h
0x1800cc103  jnz     short loc_1800CC129
0x1800cc105  call    cs:__imp_GetCurrentThread
0x1800cc10b  mov     edx, 28h ; '('; DesiredAccess
0x1800cc110  mov     r9, rbx; TokenHandle
0x1800cc113  mov     rcx, rax; ThreadHandle
0x1800cc116  lea     r8d, [rdx-27h]; OpenAsSelf
0x1800cc11a  call    cs:__imp_OpenThreadToken
0x1800cc120  test    eax, eax
0x1800cc122  jnz     short loc_1800CC14B
0x1800cc124  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800cc129  cmp     eax, 800703F0h
0x1800cc12e  jnz     short loc_1800CC158
0x1800cc130  call    cs:__imp_GetCurrentProcess
0x1800cc136  mov     r8, rbx; TokenHandle
0x1800cc139  mov     edx, 28h ; '('; DesiredAccess
0x1800cc13e  mov     rcx, rax; ProcessHandle
0x1800cc141  call    cs:__imp_OpenProcessToken
0x1800cc147  test    eax, eax
0x1800cc149  jz      short loc_1800CC153
0x1800cc14b  xor     eax, eax
0x1800cc14d  add     rsp, 20h
0x1800cc151  pop     rbx
0x1800cc152  retn
0x1800cc153  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800cc158  add     rsp, 20h
0x1800cc15c  pop     rbx
0x1800cc15d  retn
```
