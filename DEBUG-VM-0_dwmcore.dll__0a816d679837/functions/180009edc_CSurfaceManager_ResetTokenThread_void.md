# CSurfaceManager::ResetTokenThread(void)

- ea: `0x180009edc`
- end: `0x180009f93`
- name: `?ResetTokenThread@CSurfaceManager@@QEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(CSurfaceManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c60`
- `0x1801e4f00`

## callees

- `0x180009edc`
- `0x180042de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009f3a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f18`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180009f10`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180009f10`

## pseudocode

```c
__int64 __fastcall CSurfaceManager::ResetTokenThread(CSurfaceManager *this)
{
  signed int v2; // edi
  char *v3; // rcx
  DWORD ThreadId; // ebx
  signed int LastError; // eax

  v2 = 0;
  v3 = (char *)*((_QWORD *)this + 15);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ThreadId = GetThreadId(v3);
    if ( GetCurrentThreadId() != ThreadId )
    {
      if ( *((_BYTE *)this + 144) )
      {
        return (unsigned int)-2147467260;
      }
      else
      {
        SetLastError(0);
        if ( !SetEvent(*((HANDLE *)this + 16)) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          if ( v2 >= 0 )
            v2 = -2003304445;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x61u, 0);
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009edc  mov     [rsp+arg_0], rbx
0x180009ee1  mov     [rsp+arg_8], rsi
0x180009ee6  push    rdi
0x180009ee7  sub     rsp, 30h
0x180009eeb  mov     rsi, rcx
0x180009eee  xor     edi, edi
0x180009ef0  mov     rcx, [rcx+78h]; Thread
0x180009ef4  lea     rax, [rcx-1]
0x180009ef8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009efc  jbe     short loc_180009F10
0x180009efe  mov     rbx, [rsp+38h+arg_0]
0x180009f03  mov     eax, edi
0x180009f05  mov     rsi, [rsp+38h+arg_8]
0x180009f0a  add     rsp, 30h
0x180009f0e  pop     rdi
0x180009f0f  retn
0x180009f10  call    cs:__imp_GetThreadId
0x180009f16  mov     ebx, eax
0x180009f18  call    cs:__imp_GetCurrentThreadId
0x180009f1e  cmp     eax, ebx
0x180009f20  jz      short loc_180009EFE
0x180009f22  cmp     [rsi+90h], dil
0x180009f29  jnz     short loc_180009F89
0x180009f2b  xor     ecx, ecx; dwErrCode
0x180009f2d  call    cs:__imp_SetLastError
0x180009f33  mov     rcx, [rsi+80h]; hEvent
0x180009f3a  call    cs:__imp_SetEvent
0x180009f40  test    eax, eax
0x180009f42  jnz     short loc_180009EFE
0x180009f44  call    cs:__imp_GetLastError
0x180009f4a  mov     edi, eax
0x180009f4c  test    eax, eax
0x180009f4e  jle     short loc_180009F59
0x180009f50  movzx   edi, ax
0x180009f53  or      edi, 80070000h
0x180009f59  test    edi, edi
0x180009f5b  mov     [rsp+38h+var_10], 0; void *
0x180009f64  mov     eax, 88980003h
0x180009f69  mov     [rsp+38h+var_18], 61h ; 'a'; unsigned int
0x180009f71  cmovns  edi, eax
0x180009f74  xor     edx, edx; int *
0x180009f76  mov     r9d, edi; int
0x180009f79  xor     r8d, r8d; unsigned int
0x180009f7c  lea     ecx, [rdx+14h]; unsigned int
0x180009f7f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180009f84  jmp     loc_180009EFE
0x180009f89  mov     edi, 80004004h
0x180009f8e  jmp     loc_180009EFE
```
