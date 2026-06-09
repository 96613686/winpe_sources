# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800beef4`
- end: `0x1800bef5b`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `103`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800bedc8`

## callees

- `0x18006c6bc`
- `0x1800beef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bef3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800bef3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bef04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bef04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bef2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bef2d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bef17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bef17`

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
0x1800beef4  push    rbx
0x1800beef6  sub     rsp, 20h
0x1800beefa  mov     rbx, r8
0x1800beefd  mov     qword ptr [r8], 0
0x1800bef04  call    cs:__imp_GetCurrentThread
0x1800bef0a  xor     r8d, r8d; OpenAsSelf
0x1800bef0d  mov     r9, rbx; TokenHandle
0x1800bef10  mov     rcx, rax; ThreadHandle
0x1800bef13  lea     edx, [r8+8]; DesiredAccess
0x1800bef17  call    cs:__imp_OpenThreadToken
0x1800bef1d  test    eax, eax
0x1800bef1f  jnz     short loc_1800BEF48
0x1800bef21  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bef26  cmp     eax, 800703F0h
0x1800bef2b  jnz     short loc_1800BEF55
0x1800bef2d  call    cs:__imp_GetCurrentProcess
0x1800bef33  mov     r8, rbx; TokenHandle
0x1800bef36  mov     edx, 8; DesiredAccess
0x1800bef3b  mov     rcx, rax; ProcessHandle
0x1800bef3e  call    cs:__imp_OpenProcessToken
0x1800bef44  test    eax, eax
0x1800bef46  jz      short loc_1800BEF50
0x1800bef48  xor     eax, eax
0x1800bef4a  add     rsp, 20h
0x1800bef4e  pop     rbx
0x1800bef4f  retn
0x1800bef50  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bef55  add     rsp, 20h
0x1800bef59  pop     rbx
0x1800bef5a  retn
```
