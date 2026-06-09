# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18000bea8`
- end: `0x18000bf3f`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `151`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000bd80`

## callees

- `0x18000bea8`
- `0x18000c668`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bf05`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bf05`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000becb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bf2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000becb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bf2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bef4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bef4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000beb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bf19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000beb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bf19`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, __int64 a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v7; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -2147024891 )
    {
      v7 = GetCurrentThread();
      if ( OpenThreadToken(v7, 8u, 1, a3) )
        return 0;
      result = ResultFromKnownLastError();
    }
    if ( (_DWORD)result == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, a3) )
        return ResultFromKnownLastError();
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bea8  push    rbx
0x18000beaa  sub     rsp, 20h
0x18000beae  mov     rbx, r8
0x18000beb1  mov     qword ptr [r8], 0
0x18000beb8  call    cs:__imp_GetCurrentThread
0x18000bebe  xor     r8d, r8d; OpenAsSelf
0x18000bec1  mov     r9, rbx; TokenHandle
0x18000bec4  mov     rcx, rax; ThreadHandle
0x18000bec7  lea     edx, [r8+8]; DesiredAccess
0x18000becb  call    cs:__imp_OpenThreadToken
0x18000bed1  test    eax, eax
0x18000bed3  jz      short loc_18000BEDD
0x18000bed5  xor     eax, eax
0x18000bed7  add     rsp, 20h
0x18000bedb  pop     rbx
0x18000bedc  retn
0x18000bedd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bee2  test    eax, eax
0x18000bee4  jns     short loc_18000BED7
0x18000bee6  cmp     eax, 80070005h
0x18000beeb  jz      short loc_18000BF19
0x18000beed  cmp     eax, 800703F0h
0x18000bef2  jnz     short loc_18000BED7
0x18000bef4  call    cs:__imp_GetCurrentProcess
0x18000befa  mov     r8, rbx; TokenHandle
0x18000befd  mov     edx, 8; DesiredAccess
0x18000bf02  mov     rcx, rax; ProcessHandle
0x18000bf05  call    cs:__imp_OpenProcessToken
0x18000bf0b  test    eax, eax
0x18000bf0d  jnz     short loc_18000BED5
0x18000bf0f  add     rsp, 20h
0x18000bf13  pop     rbx
0x18000bf14  jmp     ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bf19  call    cs:__imp_GetCurrentThread
0x18000bf1f  mov     edx, 8; DesiredAccess
0x18000bf24  mov     r9, rbx; TokenHandle
0x18000bf27  mov     rcx, rax; ThreadHandle
0x18000bf2a  lea     r8d, [rdx-7]; OpenAsSelf
0x18000bf2e  call    cs:__imp_OpenThreadToken
0x18000bf34  test    eax, eax
0x18000bf36  jnz     short loc_18000BED5
0x18000bf38  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bf3d  jmp     short loc_18000BEED
```
