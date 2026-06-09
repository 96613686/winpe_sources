# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x1800269f8`
- end: `0x180026a99`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `161`
- prototype: `int(unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800268d0`

## callees

- `0x1800269f8`
- `0x18003aa84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026a21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026a54`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026a21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180026a54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026a0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026a0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026a3f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180026a7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180026a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026a6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026a6a`

## pseudocode

```c
__int64 __fastcall SHOpenEffectiveToken(__int64 a1, int a2, void **a3)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE v7; // rax
  HANDLE CurrentProcess; // rax

  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, a3) )
    return 0;
  result = ResultFromKnownLastError();
  if ( (int)result >= 0 )
    return result;
  if ( a2 && (_DWORD)result == -2147024891 )
  {
    v7 = GetCurrentThread();
    if ( !OpenThreadToken(v7, 8u, 1, a3) )
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
  if ( OpenProcessToken(CurrentProcess, 8u, a3) )
    return 0;
  return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1800269f8  mov     [rsp+arg_0], rbx
0x1800269fd  push    rdi
0x1800269fe  sub     rsp, 20h
0x180026a02  mov     rbx, r8
0x180026a05  mov     qword ptr [r8], 0
0x180026a0c  mov     edi, edx
0x180026a0e  call    cs:__imp_GetCurrentThread
0x180026a14  xor     r8d, r8d; OpenAsSelf
0x180026a17  mov     r9, rbx; TokenHandle
0x180026a1a  mov     rcx, rax; ThreadHandle
0x180026a1d  lea     edx, [r8+8]; DesiredAccess
0x180026a21  call    cs:__imp_OpenThreadToken
0x180026a27  test    eax, eax
0x180026a29  jnz     short loc_180026A85
0x180026a2b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180026a30  test    eax, eax
0x180026a32  jns     short loc_180026A8E
0x180026a34  test    edi, edi
0x180026a36  jz      short loc_180026A63
0x180026a38  cmp     eax, 80070005h
0x180026a3d  jnz     short loc_180026A63
0x180026a3f  call    cs:__imp_GetCurrentThread
0x180026a45  mov     edx, 8; DesiredAccess
0x180026a4a  mov     r9, rbx; TokenHandle
0x180026a4d  mov     rcx, rax; ThreadHandle
0x180026a50  lea     r8d, [rdx-7]; OpenAsSelf
0x180026a54  call    cs:__imp_OpenThreadToken
0x180026a5a  test    eax, eax
0x180026a5c  jnz     short loc_180026A85
0x180026a5e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180026a63  cmp     eax, 800703F0h
0x180026a68  jnz     short loc_180026A8E
0x180026a6a  call    cs:__imp_GetCurrentProcess
0x180026a70  mov     r8, rbx; TokenHandle
0x180026a73  mov     edx, 8; DesiredAccess
0x180026a78  mov     rcx, rax; ProcessHandle
0x180026a7b  call    cs:__imp_OpenProcessToken
0x180026a81  test    eax, eax
0x180026a83  jz      short loc_180026A89
0x180026a85  xor     eax, eax
0x180026a87  jmp     short loc_180026A8E
0x180026a89  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180026a8e  mov     rbx, [rsp+28h+arg_0]
0x180026a93  add     rsp, 20h
0x180026a97  pop     rdi
0x180026a98  retn
```
