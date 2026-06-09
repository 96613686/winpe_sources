# TelemetryOperationWatchdog::CreateDump(void)

- ea: `0x180023aac`
- end: `0x180023dce`
- name: `?CreateDump@TelemetryOperationWatchdog@@IEAAJXZ`
- size: `802`
- prototype: `__int64 __fastcall(TelemetryOperationWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180034240`

## callees

- `0x180005654`
- `0x1800056a0`
- `0x1800056ac`
- `0x180023aac`
- `0x18002c580`
- `0x18008d95a`
- `0x18008d9b0`

## import_xrefs

- `msvcrt!_itow_s` at `0x180023b29`
- `msvcrt!_itow_s` at `0x180023b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023af8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023c4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023af8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023c4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023c41`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023c19`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023cdd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023c19`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180023cdd`
- `wer!WerReportAddDump` at `0x180023c7d`
- `wer!WerReportAddDump` at `0x180023c7d`
- `wer!WerReportCreate` at `0x180023b4f`
- `wer!WerReportCreate` at `0x180023b4f`
- `wer!WerReportSubmit` at `0x180023d71`
- `wer!WerReportSubmit` at `0x180023d71`
- `wer!WerReportSetParameter` at `0x180023ba4`
- `wer!WerReportSetParameter` at `0x180023bd2`
- `wer!WerReportSetParameter` at `0x180023d07`
- `wer!WerReportSetParameter` at `0x180023ba4`
- `wer!WerReportSetParameter` at `0x180023bd2`
- `wer!WerReportSetParameter` at `0x180023d07`
- `wer!WerReportCloseHandle` at `0x180023b80`
- `wer!WerReportCloseHandle` at `0x180023d49`
- `wer!WerReportCloseHandle` at `0x180023d9e`
- `wer!WerReportCloseHandle` at `0x180023b80`
- `wer!WerReportCloseHandle` at `0x180023d49`
- `wer!WerReportCloseHandle` at `0x180023d9e`

## string_xrefs

- `0x180023b48`: `CommsNonFatalSuspectedDeadlock`

## pseudocode

```c
__int64 __fastcall TelemetryOperationWatchdog::CreateDump(TelemetryOperationWatchdog *this)
{
  HANDLE CurrentProcess; // rax
  int v3; // ecx
  HRESULT v4; // ebx
  __int64 v5; // r9
  const CHAR *v7; // rdi
  int v8; // eax
  int cchWideChar; // r14d
  WCHAR *v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rcx
  HANDLE CurrentThread; // rdi
  HANDLE v14; // rax
  HRESULT v15; // edi
  __int64 v16; // r9
  WCHAR *lpWideCharStr; // rax
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+8E0h] [rbp+7E0h] BYREF
  _WER_SUBMIT_RESULT pSubmitResult; // [rsp+8E8h] [rbp+7E8h] BYREF
  wchar_t Buffer[8]; // [rsp+8F0h] [rbp+7F0h] BYREF
  __int128 v22; // [rsp+900h] [rbp+800h]

  memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
  pReportInformation.dwSize = 2208;
  CurrentProcess = GetCurrentProcess();
  v3 = *((_DWORD *)this + 6);
  pReportInformation.hProcess = CurrentProcess;
  *(_OWORD *)Buffer = 0;
  v22 = 0;
  _itow_s(v3, Buffer, 0x10u, 10);
  phReportHandle = 0;
  v4 = WerReportCreate(L"CommsNonFatalSuspectedDeadlock", WerReportNonCritical, &pReportInformation, &phReportHandle);
  if ( v4 < 0 )
  {
    v5 = 163;
LABEL_3:
    Log_HREvent_7((unsigned int)v4, 1, "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h", v5);
    if ( phReportHandle )
      WerReportCloseHandle(phReportHandle);
    return (unsigned int)v4;
  }
  v4 = WerReportSetParameter(phReportHandle, 0, L"Version", L"1");
  if ( v4 < 0 )
  {
    v5 = 165;
    goto LABEL_3;
  }
  v4 = WerReportSetParameter(phReportHandle, 1u, L"DeadlockTimeoutMs", Buffer);
  if ( v4 < 0 )
  {
    v5 = 166;
    goto LABEL_3;
  }
  v7 = (const CHAR *)&byte_18009A505;
  if ( *((_QWORD *)this + 4) )
    v7 = (const CHAR *)*((_QWORD *)this + 4);
  v8 = MultiByteToWideChar(0, 0, v7, -1, 0, 0);
  cchWideChar = v8;
  if ( !v8 )
  {
    v10 = 0;
    v11 = 140;
    v12 = 2147942487LL;
LABEL_14:
    Log_HREvent_7(v12, 0, "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h", v11);
    goto LABEL_15;
  }
  lpWideCharStr = (WCHAR *)operator new[](saturated_mul(v8, 2u));
  v10 = lpWideCharStr;
  if ( !lpWideCharStr )
  {
    v11 = 143;
    v12 = 2147942414LL;
    goto LABEL_14;
  }
  if ( !MultiByteToWideChar(0, 0, v7, -1, lpWideCharStr, cchWideChar) )
  {
    operator delete(v10);
    v10 = 0;
  }
  v15 = WerReportSetParameter(phReportHandle, 2u, L"OperationContext", v10);
  if ( v15 < 0 )
  {
    v16 = 171;
    goto LABEL_23;
  }
LABEL_15:
  CurrentThread = GetCurrentThread();
  v14 = GetCurrentProcess();
  v15 = WerReportAddDump(phReportHandle, v14, CurrentThread, WerDumpTypeMiniDump, 0, 0, 0);
  if ( v15 < 0 )
  {
    v16 = 174;
LABEL_23:
    Log_HREvent_7((unsigned int)v15, 1, "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h", v16);
    if ( v10 )
      operator delete(v10);
    if ( phReportHandle )
      WerReportCloseHandle(phReportHandle);
    return (unsigned int)v15;
  }
  pSubmitResult = 0;
  v15 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x824u, &pSubmitResult);
  if ( v15 < 0 )
  {
    v16 = 178;
    goto LABEL_23;
  }
  if ( v10 )
    operator delete(v10);
  if ( phReportHandle )
    WerReportCloseHandle(phReportHandle);
  return 0;
}

```

## disassembly

```asm
0x180023aac  mov     [rsp-8+arg_8], rbx
0x180023ab1  mov     [rsp-8+arg_10], rdi
0x180023ab6  push    rbp
0x180023ab7  push    r12
0x180023ab9  push    r14
0x180023abb  lea     rbp, [rsp-820h]
0x180023ac3  sub     rsp, 920h
0x180023aca  mov     rax, cs:__security_cookie
0x180023ad1  xor     rax, rsp
0x180023ad4  mov     [rbp+830h+var_20], rax
0x180023adb  mov     r14, rcx
0x180023ade  xor     edx, edx; Val
0x180023ae0  lea     rcx, [rsp+930h+pReportInformation+4]; void *
0x180023ae5  mov     r8d, 89Ch; Size
0x180023aeb  call    memset_0
0x180023af0  mov     [rsp+930h+pReportInformation.dwSize], 8A0h
0x180023af8  call    cs:__imp_GetCurrentProcess
0x180023afe  mov     ecx, [r14+18h]; Value
0x180023b02  lea     rdx, [rbp+830h+Buffer]; Buffer
0x180023b09  xorps   xmm0, xmm0
0x180023b0c  mov     [rsp+930h+pReportInformation.hProcess], rax
0x180023b11  mov     r9d, 0Ah; Radix
0x180023b17  movups  xmmword ptr [rbp+830h+Buffer], xmm0
0x180023b1e  movups  [rbp+830h+var_30], xmm0
0x180023b25  lea     r8d, [r9+6]; BufferCount
0x180023b29  call    cs:__imp__itow_s
0x180023b2f  lea     r9, [rbp+830h+phReportHandle]; phReportHandle
0x180023b36  mov     [rbp+830h+phReportHandle], 0
0x180023b41  lea     r8, [rsp+930h+pReportInformation]; pReportInformation
0x180023b46  xor     edx, edx; repType
0x180023b48  lea     rcx, pwzEventType; "CommsNonFatalSuspectedDeadlock"
0x180023b4f  call    cs:__imp_WerReportCreate
0x180023b55  mov     ebx, eax
0x180023b57  test    eax, eax
0x180023b59  jns     short loc_180023B8D
0x180023b5b  mov     r9d, 0A3h
0x180023b61  mov     edx, 1
0x180023b66  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x180023b6d  mov     ecx, ebx
0x180023b6f  call    Log_HREvent_7
0x180023b74  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023b7b  test    rcx, rcx
0x180023b7e  jz      short loc_180023B86
0x180023b80  call    cs:__imp_WerReportCloseHandle
0x180023b86  mov     eax, ebx
0x180023b88  jmp     loc_180023DA6
0x180023b8d  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023b94  lea     r9, pwzValue; "1"
0x180023b9b  lea     r8, pwzName; "Version"
0x180023ba2  xor     edx, edx; dwparamID
0x180023ba4  call    cs:__imp_WerReportSetParameter
0x180023baa  mov     ebx, eax
0x180023bac  mov     edx, 1; dwparamID
0x180023bb1  test    eax, eax
0x180023bb3  jns     short loc_180023BBD
0x180023bb5  mov     r9d, 0A5h
0x180023bbb  jmp     short loc_180023B66
0x180023bbd  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023bc4  lea     r9, [rbp+830h+Buffer]; pwzValue
0x180023bcb  lea     r8, aDeadlocktimeou; "DeadlockTimeoutMs"
0x180023bd2  call    cs:__imp_WerReportSetParameter
0x180023bd8  mov     ebx, eax
0x180023bda  test    eax, eax
0x180023bdc  jns     short loc_180023BE9
0x180023bde  mov     r9d, 0A6h
0x180023be4  jmp     loc_180023B61
0x180023be9  cmp     qword ptr [r14+20h], 0
0x180023bee  lea     rdi, byte_18009A505
0x180023bf5  mov     [rsp+930h+cchWideChar], 0; cchWideChar
0x180023bfd  cmovnz  rdi, [r14+20h]
0x180023c02  or      r12, 0FFFFFFFFFFFFFFFFh
0x180023c06  mov     r9d, r12d; cbMultiByte
0x180023c09  mov     [rsp+930h+lpWideCharStr], 0; lpWideCharStr
0x180023c12  mov     r8, rdi; lpMultiByteStr
0x180023c15  xor     edx, edx; dwFlags
0x180023c17  xor     ecx, ecx; CodePage
0x180023c19  call    cs:__imp_MultiByteToWideChar
0x180023c1f  movsxd  r14, eax
0x180023c22  test    eax, eax
0x180023c24  jnz     short loc_180023C9D
0x180023c26  xor     ebx, ebx
0x180023c28  mov     r9d, 8Ch
0x180023c2e  xor     edx, edx
0x180023c30  mov     ecx, 80070057h
0x180023c35  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x180023c3c  call    Log_HREvent_7
0x180023c41  call    cs:__imp_GetCurrentThread
0x180023c47  mov     rdi, rax
0x180023c4a  call    cs:__imp_GetCurrentProcess
0x180023c50  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023c57  mov     r9d, 2; dumpType
0x180023c5d  mov     [rsp+930h+dwFlags], 0; dwFlags
0x180023c65  mov     rdx, rax; hProcess
0x180023c68  mov     qword ptr [rsp+930h+cchWideChar], 0; pDumpCustomOptions
0x180023c71  mov     r8, rdi; hThread
0x180023c74  mov     [rsp+930h+lpWideCharStr], 0; pExceptionParam
0x180023c7d  call    cs:__imp_WerReportAddDump
0x180023c83  mov     edi, eax
0x180023c85  mov     edx, 1; consent
0x180023c8a  test    eax, eax
0x180023c8c  jns     loc_180023D53
0x180023c92  mov     r9d, 0AEh
0x180023c98  jmp     loc_180023D22
0x180023c9d  mov     eax, 2
0x180023ca2  mul     r14
0x180023ca5  cmovb   rax, r12
0x180023ca9  mov     rcx, rax; unsigned __int64
0x180023cac  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180023cb1  xor     edx, edx; dwFlags
0x180023cb3  mov     rbx, rax
0x180023cb6  test    rax, rax
0x180023cb9  jnz     short loc_180023CCB
0x180023cbb  mov     r9d, 8Fh
0x180023cc1  mov     ecx, 8007000Eh
0x180023cc6  jmp     loc_180023C35
0x180023ccb  mov     [rsp+930h+cchWideChar], r14d; cchWideChar
0x180023cd0  mov     r9d, r12d; cbMultiByte
0x180023cd3  mov     r8, rdi; lpMultiByteStr
0x180023cd6  mov     [rsp+930h+lpWideCharStr], rbx; lpWideCharStr
0x180023cdb  xor     ecx, ecx; CodePage
0x180023cdd  call    cs:__imp_MultiByteToWideChar
0x180023ce3  test    eax, eax
0x180023ce5  jnz     short loc_180023CF1
0x180023ce7  mov     rcx, rbx; Block
0x180023cea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023cef  xor     ebx, ebx
0x180023cf1  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023cf8  lea     r8, aOperationconte; "OperationContext"
0x180023cff  mov     r9, rbx; pwzValue
0x180023d02  mov     edx, 2; dwparamID
0x180023d07  call    cs:__imp_WerReportSetParameter
0x180023d0d  mov     edi, eax
0x180023d0f  test    eax, eax
0x180023d11  jns     loc_180023C41
0x180023d17  mov     r9d, 0ABh
0x180023d1d  mov     edx, 1
0x180023d22  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x180023d29  mov     ecx, edi
0x180023d2b  call    Log_HREvent_7
0x180023d30  test    rbx, rbx
0x180023d33  jz      short loc_180023D3D
0x180023d35  mov     rcx, rbx; Block
0x180023d38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023d3d  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023d44  test    rcx, rcx
0x180023d47  jz      short loc_180023D4F
0x180023d49  call    cs:__imp_WerReportCloseHandle
0x180023d4f  mov     eax, edi
0x180023d51  jmp     short loc_180023DA6
0x180023d53  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023d5a  lea     r9, [rbp+830h+pSubmitResult]; pSubmitResult
0x180023d61  mov     r8d, 824h; dwFlags
0x180023d67  mov     [rbp+830h+pSubmitResult], 0
0x180023d71  call    cs:__imp_WerReportSubmit
0x180023d77  mov     edi, eax
0x180023d79  test    eax, eax
0x180023d7b  jns     short loc_180023D85
0x180023d7d  mov     r9d, 0B2h
0x180023d83  jmp     short loc_180023D1D
0x180023d85  test    rbx, rbx
0x180023d88  jz      short loc_180023D92
0x180023d8a  mov     rcx, rbx; Block
0x180023d8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023d92  mov     rcx, [rbp+830h+phReportHandle]; hReportHandle
0x180023d99  test    rcx, rcx
0x180023d9c  jz      short loc_180023DA4
0x180023d9e  call    cs:__imp_WerReportCloseHandle
0x180023da4  xor     eax, eax
0x180023da6  mov     rcx, [rbp+830h+var_20]
0x180023dad  xor     rcx, rsp; StackCookie
0x180023db0  call    __security_check_cookie
0x180023db5  lea     r11, [rsp+930h+var_10]
0x180023dbd  mov     rbx, [r11+28h]
0x180023dc1  mov     rdi, [r11+30h]
0x180023dc5  mov     rsp, r11
0x180023dc8  pop     r14
0x180023dca  pop     r12
0x180023dcc  pop     rbp
0x180023dcd  retn
```
