# _anonymous_namespace_::create_process_in_job

- ea: `0x1400f312c`
- end: `0x1400f336d`
- name: `_anonymous_namespace_::create_process_in_job`
- size: `577`
- prototype: `__int64 __fastcall(__int64, void *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400f2e40`

## callees

- `0x14003a130`
- `0x14003a5c0`
- `0x14003aa6c`
- `0x14005d250`
- `0x1400f2b68`
- `0x1400f312c`
- `0x140166990`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x1400f3294`
- `KERNEL32!CreateProcessW` at `0x1400f3294`
- `KERNEL32!TerminateProcess` at `0x1400f330c`
- `KERNEL32!TerminateProcess` at `0x1400f330c`
- `KERNEL32!AssignProcessToJobObject` at `0x1400f32b2`
- `KERNEL32!AssignProcessToJobObject` at `0x1400f32b2`
- `KERNEL32!CloseHandle` at `0x1400f32e1`
- `KERNEL32!CloseHandle` at `0x1400f331a`
- `KERNEL32!CloseHandle` at `0x1400f3328`
- `KERNEL32!CloseHandle` at `0x1400f32e1`
- `KERNEL32!CloseHandle` at `0x1400f331a`
- `KERNEL32!CloseHandle` at `0x1400f3328`
- `KERNEL32!SetLastError` at `0x1400f32ee`
- `KERNEL32!SetLastError` at `0x1400f333d`
- `KERNEL32!SetLastError` at `0x1400f32ee`
- `KERNEL32!SetLastError` at `0x1400f333d`
- `KERNEL32!GetModuleFileNameW` at `0x1400f3190`
- `KERNEL32!GetModuleFileNameW` at `0x1400f3190`
- `KERNEL32!ResumeThread` at `0x1400f32bf`
- `KERNEL32!ResumeThread` at `0x1400f32bf`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::create_process_in_job(__int64 a1, void *a2, __int64 *a3, __int64 *a4)
{
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  DWORD *v10; // r15
  DWORD ModuleFileNameW; // eax
  const struct std::nothrow_t *v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // rsi
  unsigned __int64 v15; // rdx
  const wchar_t *v16; // r8
  unsigned __int64 v17; // rdx
  HANDLE hProcess; // rsi
  HANDLE hThread; // rdi
  const struct std::nothrow_t *v20; // rdx
  DWORD dwProcessId; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-D8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-B8h] BYREF

  v8 = (wchar_t *)operator new[](0x8000u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    SetLastError(0xEu);
    goto LABEL_32;
  }
  v10 = (DWORD *)(a3 + 2);
  if ( a3[2] )
  {
    if ( (unsigned __int64)a3[3] > 7 )
      a3 = (__int64 *)*a3;
    wcsncpy(v8, (const wchar_t *)a3, 0x4000u);
    ModuleFileNameW = *v10;
    if ( *v10 >= 0x4000 )
    {
      ModuleFileNameW = 0x4000;
      goto LABEL_10;
    }
  }
  else
  {
    ModuleFileNameW = GetModuleFileNameW(0, v8, 0x4000u);
  }
  if ( ModuleFileNameW )
  {
LABEL_10:
    if ( ModuleFileNameW < 0x4000 )
    {
      _mm_lfence();
      v13 = *a4;
      v14 = a4[1];
      while ( v13 != v14 )
      {
        if ( (unsigned int)StringCchCatW(v9, (unsigned __int64)v12, L" \"") )
          goto LABEL_24;
        v16 = (const wchar_t *)v13;
        if ( *(_QWORD *)(v13 + 24) > 7u )
          v16 = *(const wchar_t **)v13;
        if ( (unsigned int)StringCchCatW(v9, v15, v16) || (unsigned int)StringCchCatW(v9, v17, L"\"") )
        {
LABEL_24:
          SetLastError(0x7Au);
          *(_BYTE *)(a1 + 16) = 0;
LABEL_25:
          _mm_lfence();
          operator delete(v9, v20);
          return a1;
        }
        v13 += 32;
      }
      _mm_lfence();
      memset(&StartupInfo, 0, sizeof(StartupInfo));
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      if ( !CreateProcessW(0, v9, 0, 0, 0, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
        goto LABEL_30;
      hProcess = ProcessInformation.hProcess;
      hThread = ProcessInformation.hThread;
      if ( AssignProcessToJobObject(a2, ProcessInformation.hProcess) && ResumeThread(hThread) )
      {
        dwProcessId = ProcessInformation.dwProcessId;
        *(_QWORD *)a1 = hProcess;
        *(_DWORD *)(a1 + 8) = dwProcessId;
        *(_BYTE *)(a1 + 16) = 1;
        if ( hThread )
          CloseHandle(hThread);
        goto LABEL_25;
      }
      TerminateProcess(hProcess, 0xFFFFFFFF);
      if ( hProcess )
        CloseHandle(hProcess);
      if ( hThread )
        CloseHandle(hThread);
    }
  }
LABEL_30:
  operator delete(v9, v12);
LABEL_32:
  *(_BYTE *)(a1 + 16) = 0;
  return a1;
}

```

## disassembly

```asm
0x1400f312c  push    rbx
0x1400f312e  push    rbp
0x1400f312f  push    rsi
0x1400f3130  push    rdi
0x1400f3131  push    r12
0x1400f3133  push    r14
0x1400f3135  push    r15
0x1400f3137  sub     rsp, 0F0h
0x1400f313e  mov     rax, cs:__security_cookie
0x1400f3145  xor     rax, rsp
0x1400f3148  mov     [rsp+128h+var_48], rax
0x1400f3150  mov     r12, rdx
0x1400f3153  mov     r14, rcx
0x1400f3156  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400f315d  mov     ecx, 8000h; unsigned __int64
0x1400f3162  mov     rbp, r9
0x1400f3165  mov     rsi, r8
0x1400f3168  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400f316d  mov     rbx, rax
0x1400f3170  test    rax, rax
0x1400f3173  jz      loc_1400F3338
0x1400f3179  lea     r15, [rsi+10h]
0x1400f317d  cmp     qword ptr [r15], 0
0x1400f3181  jnz     short loc_1400F3198
0x1400f3183  mov     edi, 4000h
0x1400f3188  mov     rdx, rax; lpFilename
0x1400f318b  mov     r8d, edi; nSize
0x1400f318e  xor     ecx, ecx; hModule
0x1400f3190  call    cs:__imp_GetModuleFileNameW
0x1400f3196  jmp     short loc_1400F31BC
0x1400f3198  cmp     qword ptr [rsi+18h], 7
0x1400f319d  jbe     short loc_1400F31A2
0x1400f319f  mov     rsi, [rsi]
0x1400f31a2  mov     edi, 4000h
0x1400f31a7  mov     rdx, rsi; Source
0x1400f31aa  mov     r8d, edi; Count
0x1400f31ad  mov     rcx, rbx; Destination
0x1400f31b0  call    wcsncpy
0x1400f31b5  mov     eax, [r15]
0x1400f31b8  cmp     eax, edi
0x1400f31ba  jnb     short loc_1400F31C6
0x1400f31bc  test    eax, eax
0x1400f31be  jz      loc_1400F332E
0x1400f31c4  jmp     short loc_1400F31C8
0x1400f31c6  mov     eax, edi
0x1400f31c8  cmp     eax, edi
0x1400f31ca  jnb     loc_1400F332E
0x1400f31d0  lfence
0x1400f31d3  mov     rdi, [rbp+0]
0x1400f31d7  mov     rsi, [rbp+8]
0x1400f31db  jmp     short loc_1400F322C
0x1400f31dd  lea     r8, asc_14019DE40; " \""
0x1400f31e4  mov     rcx, rbx; wchar_t *
0x1400f31e7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400f31ec  test    eax, eax
0x1400f31ee  jnz     loc_1400F32E9
0x1400f31f4  cmp     qword ptr [rdi+18h], 7
0x1400f31f9  mov     r8, rdi
0x1400f31fc  jbe     short loc_1400F3201
0x1400f31fe  mov     r8, [rdi]; wchar_t *
0x1400f3201  mov     rcx, rbx; wchar_t *
0x1400f3204  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400f3209  test    eax, eax
0x1400f320b  jnz     loc_1400F32E9
0x1400f3211  lea     r8, asc_14019A818; "\""
0x1400f3218  mov     rcx, rbx; wchar_t *
0x1400f321b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400f3220  test    eax, eax
0x1400f3222  jnz     loc_1400F32E9
0x1400f3228  add     rdi, 20h ; ' '
0x1400f322c  cmp     rdi, rsi
0x1400f322f  jnz     short loc_1400F31DD
0x1400f3231  lfence
0x1400f3234  xor     edx, edx; Val
0x1400f3236  lea     rcx, [rsp+128h+StartupInfo]; void *
0x1400f323b  lea     r8d, [rdx+68h]; Size
0x1400f323f  call    memset
0x1400f3244  xor     eax, eax
0x1400f3246  xorps   xmm0, xmm0
0x1400f3249  mov     qword ptr [rsp+128h+ProcessInformation.dwProcessId], rax
0x1400f324e  xor     r9d, r9d; lpThreadAttributes
0x1400f3251  lea     rax, [rsp+128h+ProcessInformation]
0x1400f3256  xor     r8d, r8d; lpProcessAttributes
0x1400f3259  mov     [rsp+128h+lpProcessInformation], rax; lpProcessInformation
0x1400f325e  mov     rdx, rbx; lpCommandLine
0x1400f3261  lea     rax, [rsp+128h+StartupInfo]
0x1400f3266  xor     ecx, ecx; lpApplicationName
0x1400f3268  mov     [rsp+128h+lpStartupInfo], rax; lpStartupInfo
0x1400f326d  mov     [rsp+128h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1400f3276  mov     [rsp+128h+lpEnvironment], 0; lpEnvironment
0x1400f327f  mov     [rsp+128h+dwCreationFlags], 4; dwCreationFlags
0x1400f3287  mov     [rsp+128h+bInheritHandles], 0; bInheritHandles
0x1400f328f  movups  xmmword ptr [rsp+128h+ProcessInformation.hProcess], xmm0
0x1400f3294  call    cs:__imp_CreateProcessW
0x1400f329a  test    eax, eax
0x1400f329c  jz      loc_1400F332E
0x1400f32a2  mov     rsi, [rsp+128h+ProcessInformation.hProcess]
0x1400f32a7  mov     rcx, r12; hJob
0x1400f32aa  mov     rdi, [rsp+128h+ProcessInformation.hThread]
0x1400f32af  mov     rdx, rsi; hProcess
0x1400f32b2  call    cs:__imp_AssignProcessToJobObject
0x1400f32b8  test    eax, eax
0x1400f32ba  jz      short loc_1400F3306
0x1400f32bc  mov     rcx, rdi; hThread
0x1400f32bf  call    cs:__imp_ResumeThread
0x1400f32c5  test    eax, eax
0x1400f32c7  jz      short loc_1400F3306
0x1400f32c9  mov     eax, [rsp+128h+ProcessInformation.dwProcessId]
0x1400f32cd  mov     [r14], rsi
0x1400f32d0  mov     [r14+8], eax
0x1400f32d4  mov     byte ptr [r14+10h], 1
0x1400f32d9  test    rdi, rdi
0x1400f32dc  jz      short loc_1400F32F9
0x1400f32de  mov     rcx, rdi; hObject
0x1400f32e1  call    cs:__imp_CloseHandle
0x1400f32e7  jmp     short loc_1400F32F9
0x1400f32e9  mov     ecx, 7Ah ; 'z'; dwErrCode
0x1400f32ee  call    cs:__imp_SetLastError
0x1400f32f4  mov     byte ptr [r14+10h], 0
0x1400f32f9  lfence
0x1400f32fc  mov     rcx, rbx; void *
0x1400f32ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f3304  jmp     short loc_1400F3348
0x1400f3306  or      edx, 0FFFFFFFFh; uExitCode
0x1400f3309  mov     rcx, rsi; hProcess
0x1400f330c  call    cs:__imp_TerminateProcess
0x1400f3312  test    rsi, rsi
0x1400f3315  jz      short loc_1400F3320
0x1400f3317  mov     rcx, rsi; hObject
0x1400f331a  call    cs:__imp_CloseHandle
0x1400f3320  test    rdi, rdi
0x1400f3323  jz      short loc_1400F332E
0x1400f3325  mov     rcx, rdi; hObject
0x1400f3328  call    cs:__imp_CloseHandle
0x1400f332e  mov     rcx, rbx; void *
0x1400f3331  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f3336  jmp     short loc_1400F3343
0x1400f3338  mov     ecx, 0Eh; dwErrCode
0x1400f333d  call    cs:__imp_SetLastError
0x1400f3343  mov     byte ptr [r14+10h], 0
0x1400f3348  mov     rax, r14
0x1400f334b  mov     rcx, [rsp+128h+var_48]
0x1400f3353  xor     rcx, rsp; StackCookie
0x1400f3356  call    __security_check_cookie
0x1400f335b  add     rsp, 0F0h
0x1400f3362  pop     r15
0x1400f3364  pop     r14
0x1400f3366  pop     r12
0x1400f3368  pop     rdi
0x1400f3369  pop     rsi
0x1400f336a  pop     rbp
0x1400f336b  pop     rbx
0x1400f336c  retn
```
