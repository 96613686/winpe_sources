# SHOpenEffectiveToken(ulong,int,void * *)

- ea: `0x18001e7e0`
- end: `0x18001e887`
- name: `?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, int, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001d73c`
- `0x18002d838`

## callees

- `0x18001e7b4`
- `0x18001e7e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e856`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e856`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e80e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e840`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e80e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e7fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e82c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e7fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e82c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e864`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e864`

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
0x18001e7e0  mov     [rsp+arg_0], rbx
0x18001e7e5  mov     [rsp+arg_8], rsi
0x18001e7ea  push    rdi
0x18001e7eb  sub     rsp, 20h
0x18001e7ef  mov     rbx, r8
0x18001e7f2  mov     qword ptr [r8], 0
0x18001e7f9  mov     esi, edx
0x18001e7fb  mov     edi, ecx
0x18001e7fd  call    cs:__imp_GetCurrentThread
0x18001e803  mov     r9, rbx; TokenHandle
0x18001e806  xor     r8d, r8d; OpenAsSelf
0x18001e809  mov     rcx, rax; ThreadHandle
0x18001e80c  mov     edx, edi; DesiredAccess
0x18001e80e  call    cs:__imp_OpenThreadToken
0x18001e814  test    eax, eax
0x18001e816  jnz     short loc_18001E86E
0x18001e818  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e81d  test    eax, eax
0x18001e81f  jns     short loc_18001E877
0x18001e821  test    esi, esi
0x18001e823  jz      short loc_18001E84F
0x18001e825  cmp     eax, 80070005h
0x18001e82a  jnz     short loc_18001E84F
0x18001e82c  call    cs:__imp_GetCurrentThread
0x18001e832  mov     r9, rbx; TokenHandle
0x18001e835  mov     r8d, 1; OpenAsSelf
0x18001e83b  mov     rcx, rax; ThreadHandle
0x18001e83e  mov     edx, edi; DesiredAccess
0x18001e840  call    cs:__imp_OpenThreadToken
0x18001e846  test    eax, eax
0x18001e848  jnz     short loc_18001E86E
0x18001e84a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e84f  cmp     eax, 800703F0h
0x18001e854  jnz     short loc_18001E877
0x18001e856  call    cs:__imp_GetCurrentProcess
0x18001e85c  mov     r8, rbx; TokenHandle
0x18001e85f  mov     edx, edi; DesiredAccess
0x18001e861  mov     rcx, rax; ProcessHandle
0x18001e864  call    cs:__imp_OpenProcessToken
0x18001e86a  test    eax, eax
0x18001e86c  jz      short loc_18001E872
0x18001e86e  xor     eax, eax
0x18001e870  jmp     short loc_18001E877
0x18001e872  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e877  mov     rbx, [rsp+28h+arg_0]
0x18001e87c  mov     rsi, [rsp+28h+arg_8]
0x18001e881  add     rsp, 20h
0x18001e885  pop     rdi
0x18001e886  retn
```
