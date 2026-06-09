# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1400698d8`
- end: `0x14006997f`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, int, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14006977c`
- `0x140069988`

## callees

- `0x14003d630`
- `0x1400698d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14006995c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14006995c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140069906`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140069938`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140069906`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140069938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400698f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140069924`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400698f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140069924`
- `KERNEL32!GetCurrentProcess` at `0x14006994e`
- `KERNEL32!GetCurrentProcess` at `0x14006994e`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(DWORD DesiredAccess, int a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE v8; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, DesiredAccess, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return result;
  if ( a2 && (_DWORD)result == -2147024891 )
  {
    v8 = GetCurrentThread();
    if ( !OpenThreadToken(v8, DesiredAccess, 1, a3) )
    {
      result = ResultFromKnownLastError();
      goto LABEL_7;
    }
    return 0;
  }
LABEL_7:
  if ( (_DWORD)result != -2147023888 )
    return result;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, DesiredAccess, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1400698d8  mov     [rsp+arg_0], rbx
0x1400698dd  mov     [rsp+arg_8], rsi
0x1400698e2  push    rdi
0x1400698e3  sub     rsp, 20h
0x1400698e7  mov     rbx, r8
0x1400698ea  mov     qword ptr [r8], 0
0x1400698f1  mov     esi, edx
0x1400698f3  mov     edi, ecx
0x1400698f5  call    cs:__imp_GetCurrentThread
0x1400698fb  mov     r9, rbx; TokenHandle
0x1400698fe  xor     r8d, r8d; OpenAsSelf
0x140069901  mov     rcx, rax; ThreadHandle
0x140069904  mov     edx, edi; DesiredAccess
0x140069906  call    cs:__imp_OpenThreadToken
0x14006990c  test    eax, eax
0x14006990e  jnz     short loc_140069966
0x140069910  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140069915  test    eax, eax
0x140069917  jns     short loc_14006996F
0x140069919  test    esi, esi
0x14006991b  jz      short loc_140069947
0x14006991d  cmp     eax, 80070005h
0x140069922  jnz     short loc_140069947
0x140069924  call    cs:__imp_GetCurrentThread
0x14006992a  mov     r9, rbx; TokenHandle
0x14006992d  mov     r8d, 1; OpenAsSelf
0x140069933  mov     rcx, rax; ThreadHandle
0x140069936  mov     edx, edi; DesiredAccess
0x140069938  call    cs:__imp_OpenThreadToken
0x14006993e  test    eax, eax
0x140069940  jnz     short loc_140069966
0x140069942  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140069947  cmp     eax, 800703F0h
0x14006994c  jnz     short loc_14006996F
0x14006994e  call    cs:__imp_GetCurrentProcess
0x140069954  mov     r8, rbx; TokenHandle
0x140069957  mov     edx, edi; DesiredAccess
0x140069959  mov     rcx, rax; ProcessHandle
0x14006995c  call    cs:__imp_OpenProcessToken
0x140069962  test    eax, eax
0x140069964  jz      short loc_14006996A
0x140069966  xor     eax, eax
0x140069968  jmp     short loc_14006996F
0x14006996a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14006996f  mov     rbx, [rsp+28h+arg_0]
0x140069974  mov     rsi, [rsp+28h+arg_8]
0x140069979  add     rsp, 20h
0x14006997d  pop     rdi
0x14006997e  retn
```
