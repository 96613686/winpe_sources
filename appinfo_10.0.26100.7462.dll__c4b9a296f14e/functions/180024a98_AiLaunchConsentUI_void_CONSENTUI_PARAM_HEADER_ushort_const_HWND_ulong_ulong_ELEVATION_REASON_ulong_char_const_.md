# AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)

- ea: `0x180024a98`
- end: `0x180024e95`
- name: `?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z`
- size: `1021`
- prototype: `unsigned int __high(void *, struct _CONSENTUI_PARAM_HEADER *, const unsigned __int16 *, HWND, unsigned int, unsigned int, enum ELEVATION_REASON, unsigned int, const char *, void **)`
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180016da4`
- `0x18001e804`
- `0x1800230e0`
- `0x18003bf30`

## callees

- `0x18000d8e0`
- `0x18000da00`
- `0x18000e9b0`
- `0x1800106d0`
- `0x180012740`
- `0x180014c10`
- `0x180014da0`
- `0x180022bb0`
- `0x180024a98`
- `0x180025070`
- `0x180025880`
- `0x180041040`
- `0x1800423f4`
- `0x180043f6c`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180024c48`
- `msvcrt!swprintf_s` at `0x180024c48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024d21`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d50`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180024d0b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180024d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180024d40`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180024d40`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180024e27`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180024e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024c20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e37`
- `ntdll!NtClose` at `0x180024d75`
- `ntdll!NtClose` at `0x180024e4e`
- `ntdll!NtClose` at `0x180024d75`
- `ntdll!NtClose` at `0x180024e4e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180024da7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180024da7`

## pseudocode

```c
DWORD __fastcall AiLaunchConsentUI(
        void *a1,
        int *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        DWORD dwMilliseconds,
        unsigned __int16 *a9,
        _QWORD *a10)
{
  _QWORD *v10; // rdi
  unsigned __int16 *v11; // r15
  void *v12; // rbx
  int v14; // r12d
  struct _SESSION_LOCK *v15; // r14
  DWORD result; // eax
  unsigned int v17; // esi
  __int64 v18; // rax
  void *v19; // r14
  int *v20; // r15
  int v21; // ebx
  DWORD CurrentProcessId; // eax
  char IsEnabled; // al
  int v24; // r9d
  HANDLE v25; // rcx
  HANDLE v26; // rax
  NTSTATUS v27; // eax
  DWORD v28; // eax
  HANDLE hProcess; // rcx
  unsigned __int16 *v30; // [rsp+20h] [rbp-F0h]
  unsigned __int16 *v31; // [rsp+38h] [rbp-D8h]
  DWORD ExitCode; // [rsp+90h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp-78h] BYREF
  int v34; // [rsp+A0h] [rbp-70h] BYREF
  void *v35; // [rsp+A8h] [rbp-68h] BYREF
  struct _PROCESS_INFORMATION hThread; // [rsp+B0h] [rbp-60h] BYREF
  struct _SESSION_LOCK *v37; // [rsp+C8h] [rbp-48h] BYREF
  void *v38; // [rsp+D0h] [rbp-40h]
  __int64 v39; // [rsp+D8h] [rbp-38h]
  int *v40; // [rsp+E0h] [rbp-30h]
  _QWORD *v41; // [rsp+E8h] [rbp-28h]
  wchar_t Buffer[64]; // [rsp+F0h] [rbp-20h] BYREF

  v10 = a10;
  v11 = a9;
  v12 = 0;
  Handle = 0;
  v40 = a2;
  v38 = a1;
  v14 = 0;
  v15 = 0;
  v39 = a4;
  v41 = a10;
  v35 = 0;
  memset(&hThread, 0, sizeof(hThread));
  v34 = 0;
  v37 = 0;
  memset_0(Buffer, 0, 0x7Au);
  *v10 = 0;
  if ( a7 == 9 )
  {
    v17 = a6;
  }
  else
  {
    if ( !a5 )
    {
      result = 1459;
LABEL_4:
      ExitCode = result;
      goto LABEL_42;
    }
    if ( (a6 & 0x10) == 0 )
    {
      result = AipGetElevationPromptType(&a6, (enum _CONSENTUI_PROMPT_TYPE *)&v34);
      ExitCode = result;
      if ( result )
        goto LABEL_42;
      v14 = v34;
    }
    result = AipCheckLegacySecureDesktopPolicy(a5, &a6);
    ExitCode = result;
    if ( result )
      goto LABEL_42;
    if ( v11
      && (!g_pConsentExeTelemetryRateLimiter
       || !(unsigned int)RateLimiter::RequestPermission(g_pConsentExeTelemetryRateLimiter)) )
    {
      v11 = 0;
    }
    v17 = a6;
    if ( (a6 & 0x110) == 0x100 )
    {
      result = AipGetSessionLock(a5, 0, &v37);
      ExitCode = result;
      if ( result )
        goto LABEL_42;
      v15 = v37;
    }
  }
  if ( v15 )
    v18 = *(_QWORD *)v15;
  else
    v18 = 0;
  v19 = v38;
  v31 = v11;
  v20 = v40;
  AipSetFixedParams(v40, a7, v39, v38, a5, v14, v18, v31, v17, &Handle);
  v21 = *v20;
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(v30) = v21;
  swprintf_s(Buffer, 0x3Du, L"consent.exe %u %u %p", CurrentProcessId, v30, v20);
  result = AipBuildConsentToken(a5, &v35);
  ExitCode = result;
  if ( result )
  {
    v12 = v35;
  }
  else
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl'::`2'::impl);
    v12 = v35;
    v24 = 553648256;
    if ( !IsEnabled )
      v24 = 16777344;
    result = AiLaunchProcess(0, v35, 0, v24, 0, Buffer, 0x400u, 0, a3, 0, a5, 0, 0, 0, 0, 0, &hThread);
    ExitCode = result;
    if ( !result )
    {
      result = AipVerifyConsent(hThread.hProcess);
      ExitCode = result;
      if ( !result )
      {
        ResumeThread(hThread.hThread);
        result = WaitForSingleObject(hThread.hProcess, dwMilliseconds);
        ExitCode = result;
        if ( !result )
        {
          if ( !GetExitCodeProcess(hThread.hProcess, &ExitCode) )
          {
            result = GetLastError();
            goto LABEL_4;
          }
          result = ExitCode;
          if ( ExitCode )
          {
            v25 = Handle;
            if ( !Handle )
              goto LABEL_42;
            goto LABEL_30;
          }
          if ( (v17 & 0x10000) != 0 )
          {
            v26 = Handle;
            if ( !Handle )
            {
LABEL_37:
              *v41 = v26;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
                && (unsigned int)LUAIsShadowAdminEnabled()
                && Handle )
              {
                AiSettingsSync(v19, Handle);
              }
              goto LABEL_31;
            }
            v27 = AipMarkAutoApprovedToken(Handle);
            if ( v27 < 0 )
            {
              v28 = RtlNtStatusToDosErrorNoTeb(v27);
              v25 = Handle;
              ExitCode = v28;
LABEL_30:
              NtClose(v25);
              Handle = 0;
LABEL_31:
              result = ExitCode;
              goto LABEL_42;
            }
          }
          v26 = Handle;
          goto LABEL_37;
        }
      }
    }
  }
LABEL_42:
  if ( hThread.hThread )
  {
    CloseHandle(hThread.hThread);
    result = ExitCode;
  }
  hProcess = hThread.hProcess;
  if ( hThread.hProcess )
  {
    if ( result && result != 1067 )
    {
      TerminateProcess(hThread.hProcess, result);
      hProcess = hThread.hProcess;
    }
    CloseHandle(hProcess);
    result = ExitCode;
  }
  if ( v12 )
  {
    NtClose(v12);
    result = ExitCode;
  }
  if ( result == 258 || result == 1067 )
    return 1223;
  return result;
}

```

## disassembly

```asm
0x180024a98  mov     [rsp-8+arg_18], rbx
0x180024a9d  push    rbp
0x180024a9e  push    rsi
0x180024a9f  push    rdi
0x180024aa0  push    r12
0x180024aa2  push    r13
0x180024aa4  push    r14
0x180024aa6  push    r15
0x180024aa8  lea     rbp, [rsp-70h]
0x180024aad  sub     rsp, 180h
0x180024ab4  mov     rax, cs:__security_cookie
0x180024abb  xor     rax, rsp
0x180024abe  mov     [rbp+0A0h+var_40], rax
0x180024ac2  mov     rdi, [rbp+0A0h+arg_48]
0x180024ac9  xor     eax, eax
0x180024acb  mov     r15, [rbp+0A0h+arg_40]
0x180024ad2  xor     ebx, ebx
0x180024ad4  and     [rbp+0A0h+Handle], rax
0x180024ad8  mov     r13, r8
0x180024adb  mov     [rbp+0A0h+var_D0], rdx
0x180024adf  xorps   xmm0, xmm0
0x180024ae2  mov     [rbp+0A0h+var_E0], rcx
0x180024ae6  xor     r12d, r12d
0x180024ae9  xor     r14d, r14d
0x180024aec  mov     [rbp+0A0h+var_D8], r9
0x180024af0  lea     r8d, [rbx+7Ah]; Size
0x180024af4  mov     [rbp+0A0h+var_C8], rdi
0x180024af8  xor     edx, edx; Val
0x180024afa  mov     [rbp+0A0h+var_108], rbx
0x180024afe  lea     rcx, [rbp+0A0h+Buffer]; void *
0x180024b02  mov     [rbp+0A0h+var_F0], rax
0x180024b06  movups  xmmword ptr [rbp+0A0h+hThread], xmm0
0x180024b0a  mov     [rbp+0A0h+var_110], r12d
0x180024b0e  mov     [rbp+0A0h+var_E8], r14
0x180024b12  call    memset_0
0x180024b17  and     [rdi], rbx
0x180024b1a  cmp     [rbp+0A0h+arg_30], 9
0x180024b21  mov     edi, [rbp+0A0h+arg_20]
0x180024b27  jz      loc_180024BCE
0x180024b2d  test    edi, edi
0x180024b2f  jnz     short loc_180024B3E
0x180024b31  mov     eax, 5B3h
0x180024b36  mov     [rbp+0A0h+ExitCode], eax
0x180024b39  jmp     loc_180024DF7
0x180024b3e  test    byte ptr [rbp+0A0h+arg_28], 10h
0x180024b45  jnz     short loc_180024B66
0x180024b47  lea     rdx, [rbp+0A0h+var_110]; enum _CONSENTUI_PROMPT_TYPE *
0x180024b4b  lea     rcx, [rbp+0A0h+arg_28]; unsigned int *
0x180024b52  call    ?AipGetElevationPromptType@@YAKPEAKPEAW4_CONSENTUI_PROMPT_TYPE@@@Z; AipGetElevationPromptType(ulong *,_CONSENTUI_PROMPT_TYPE *)
0x180024b57  mov     [rbp+0A0h+ExitCode], eax
0x180024b5a  test    eax, eax
0x180024b5c  jnz     loc_180024DF7
0x180024b62  mov     r12d, [rbp+0A0h+var_110]
0x180024b66  lea     rdx, [rbp+0A0h+arg_28]; unsigned int *
0x180024b6d  mov     ecx, edi; unsigned int
0x180024b6f  call    ?AipCheckLegacySecureDesktopPolicy@@YAKKPEAK@Z; AipCheckLegacySecureDesktopPolicy(ulong,ulong *)
0x180024b74  mov     [rbp+0A0h+ExitCode], eax
0x180024b77  test    eax, eax
0x180024b79  jnz     loc_180024DF7
0x180024b7f  test    r15, r15
0x180024b82  jz      short loc_180024B9C
0x180024b84  mov     rcx, cs:?g_pConsentExeTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x180024b8b  test    rcx, rcx
0x180024b8e  jz      short loc_180024B99
0x180024b90  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x180024b95  test    eax, eax
0x180024b97  jnz     short loc_180024B9C
0x180024b99  xor     r15d, r15d
0x180024b9c  mov     esi, [rbp+0A0h+arg_28]
0x180024ba2  mov     eax, esi
0x180024ba4  and     eax, 110h
0x180024ba9  cmp     eax, 100h
0x180024bae  jnz     short loc_180024BD4
0x180024bb0  lea     r8, [rbp+0A0h+var_E8]; struct _SESSION_LOCK **
0x180024bb4  xor     edx, edx; int
0x180024bb6  mov     ecx, edi; unsigned int
0x180024bb8  call    ?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z; AipGetSessionLock(ulong,int,_SESSION_LOCK * *)
0x180024bbd  mov     [rbp+0A0h+ExitCode], eax
0x180024bc0  test    eax, eax
0x180024bc2  jnz     loc_180024DF7
0x180024bc8  mov     r14, [rbp+0A0h+var_E8]
0x180024bcc  jmp     short loc_180024BD4
0x180024bce  mov     esi, [rbp+0A0h+arg_28]
0x180024bd4  test    r14, r14
0x180024bd7  jz      short loc_180024BDE
0x180024bd9  mov     rax, [r14]
0x180024bdc  jmp     short loc_180024BE0
0x180024bde  xor     eax, eax
0x180024be0  mov     r14, [rbp+0A0h+var_E0]
0x180024be4  lea     rcx, [rbp+0A0h+Handle]
0x180024be8  mov     r8, [rbp+0A0h+var_D8]
0x180024bec  mov     r9, r14
0x180024bef  mov     edx, [rbp+0A0h+arg_30]
0x180024bf5  mov     [rsp+1B0h+var_168], rcx
0x180024bfa  mov     dword ptr [rsp+1B0h+var_170], esi
0x180024bfe  mov     [rsp+1B0h+var_178], r15
0x180024c03  mov     r15, [rbp+0A0h+var_D0]
0x180024c07  mov     qword ptr [rsp+1B0h+var_180], rax
0x180024c0c  mov     rcx, r15
0x180024c0f  mov     dword ptr [rsp+1B0h+var_188], r12d
0x180024c14  mov     dword ptr [rsp+1B0h+var_190], edi
0x180024c18  call    ?AipSetFixedParams@@YAXPEAU_CONSENTUI_PARAM_HEADER@@W4ELEVATION_REASON@@PEAUHWND__@@PEAXKW4_CONSENTUI_PROMPT_TYPE@@3PEBDKPEAU_CONSENTUI_RETURN_PARAM@@@Z; AipSetFixedParams(_CONSENTUI_PARAM_HEADER *,ELEVATION_REASON,HWND__ *,void *,ulong,_CONSENTUI_PROMPT_TYPE,void *,char const *,ulong,_CONSENTUI_RETURN_PARAM *)
0x180024c1d  mov     ebx, [r15]
0x180024c20  call    cs:__imp_GetCurrentProcessId
0x180024c27  nop     dword ptr [rax+rax+00h]
0x180024c2c  mov     [rsp+1B0h+var_188], r15
0x180024c31  lea     r8, aConsentExeUUP; "consent.exe %u %u %p"
0x180024c38  mov     r9d, eax
0x180024c3b  mov     dword ptr [rsp+1B0h+var_190], ebx
0x180024c3f  mov     edx, 3Dh ; '='; BufferCount
0x180024c44  lea     rcx, [rbp+0A0h+Buffer]; Buffer
0x180024c48  call    cs:__imp_swprintf_s
0x180024c4f  nop     dword ptr [rax+rax+00h]
0x180024c54  lea     rdx, [rbp+0A0h+var_108]; void **
0x180024c58  mov     ecx, edi; unsigned int
0x180024c5a  call    ?AipBuildConsentToken@@YAKKPEAPEAX@Z; AipBuildConsentToken(ulong,void * *)
0x180024c5f  xor     r15d, r15d
0x180024c62  mov     [rbp+0A0h+ExitCode], eax
0x180024c65  test    eax, eax
0x180024c67  jnz     loc_180024DF3
0x180024c6d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_1200131385@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_1200131385@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385> `wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl(void)'::`2'::impl
0x180024c74  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_1200131385@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(void)
0x180024c79  mov     rbx, [rbp+0A0h+var_108]
0x180024c7d  xor     r8d, r8d; void *
0x180024c80  xor     ecx, ecx; void *
0x180024c82  mov     rdx, rbx; void *
0x180024c85  test    al, al
0x180024c87  mov     r9d, 21000080h
0x180024c8d  lea     rax, [rbp+0A0h+hThread]
0x180024c91  mov     [rsp+1B0h+var_130], rax; struct _PROCESS_INFORMATION *
0x180024c99  lea     rax, [rbp+0A0h+Buffer]
0x180024c9d  mov     [rsp+1B0h+Src], r15; Src
0x180024ca2  mov     [rsp+1B0h+var_140], r15; unsigned __int64
0x180024ca7  mov     [rsp+1B0h+var_148], r15; void *
0x180024cac  mov     [rsp+1B0h+var_150], r15d; unsigned int
0x180024cb1  mov     [rsp+1B0h+lpValue], r15; lpValue
0x180024cb6  mov     [rsp+1B0h+var_160], edi; unsigned int
0x180024cba  mov     [rsp+1B0h+var_168], r15; struct _APPINFO_STARTUPINFO *
0x180024cbf  mov     [rsp+1B0h+var_170], r13; unsigned __int16 *
0x180024cc4  mov     [rsp+1B0h+var_178], r15; unsigned __int16 *
0x180024cc9  mov     [rsp+1B0h+var_180], 400h; unsigned int
0x180024cd1  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x180024cd6  mov     [rsp+1B0h+var_190], r15; unsigned __int16 *
0x180024cdb  jnz     short loc_180024CE3
0x180024cdd  mov     r9d, 1000080h; unsigned int
0x180024ce3  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)
0x180024ce8  mov     [rbp+0A0h+ExitCode], eax
0x180024ceb  test    eax, eax
0x180024ced  jnz     loc_180024DF7
0x180024cf3  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x180024cf7  call    ?AipVerifyConsent@@YAKPEAX@Z; AipVerifyConsent(void *)
0x180024cfc  mov     [rbp+0A0h+ExitCode], eax
0x180024cff  test    eax, eax
0x180024d01  jnz     loc_180024DF7
0x180024d07  mov     rcx, [rbp+0A0h+hThread+8]; hThread
0x180024d0b  call    cs:__imp_ResumeThread
0x180024d12  nop     dword ptr [rax+rax+00h]
0x180024d17  mov     edx, [rbp+0A0h+dwMilliseconds]; dwMilliseconds
0x180024d1d  mov     rcx, [rbp+0A0h+hThread]; hHandle
0x180024d21  call    cs:__imp_WaitForSingleObject
0x180024d28  nop     dword ptr [rax+rax+00h]
0x180024d2d  mov     [rbp+0A0h+ExitCode], eax
0x180024d30  test    eax, eax
0x180024d32  jnz     loc_180024DF7
0x180024d38  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x180024d3c  lea     rdx, [rbp+0A0h+ExitCode]; lpExitCode
0x180024d40  call    cs:__imp_GetExitCodeProcess
0x180024d47  nop     dword ptr [rax+rax+00h]
0x180024d4c  test    eax, eax
0x180024d4e  jnz     short loc_180024D61
0x180024d50  call    cs:__imp_GetLastError
0x180024d57  nop     dword ptr [rax+rax+00h]
0x180024d5c  jmp     loc_180024B36
0x180024d61  mov     eax, [rbp+0A0h+ExitCode]
0x180024d64  test    eax, eax
0x180024d66  jz      short loc_180024D8A
0x180024d68  mov     rcx, [rbp+0A0h+Handle]; Handle
0x180024d6c  test    rcx, rcx
0x180024d6f  jz      loc_180024DF7
0x180024d75  call    cs:__imp_NtClose
0x180024d7c  nop     dword ptr [rax+rax+00h]
0x180024d81  mov     [rbp+0A0h+Handle], r15
0x180024d85  mov     eax, [rbp+0A0h+ExitCode]
0x180024d88  jmp     short loc_180024DF7
0x180024d8a  bt      esi, 10h
0x180024d8e  jnb     short loc_180024DBC
0x180024d90  mov     rax, [rbp+0A0h+Handle]
0x180024d94  test    rax, rax
0x180024d97  jz      short loc_180024DC0
0x180024d99  mov     rcx, rax; TokenHandle
0x180024d9c  call    ?AipMarkAutoApprovedToken@@YAJPEAX@Z; AipMarkAutoApprovedToken(void *)
0x180024da1  test    eax, eax
0x180024da3  jns     short loc_180024DBC
0x180024da5  mov     ecx, eax; Status
0x180024da7  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180024dae  nop     dword ptr [rax+rax+00h]
0x180024db3  mov     rcx, [rbp+0A0h+Handle]
0x180024db7  mov     [rbp+0A0h+ExitCode], eax
0x180024dba  jmp     short loc_180024D75
0x180024dbc  mov     rax, [rbp+0A0h+Handle]
0x180024dc0  mov     rcx, [rbp+0A0h+var_C8]
0x180024dc4  mov     [rcx], rax
0x180024dc7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180024dce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180024dd3  test    al, al
0x180024dd5  jz      short loc_180024D85
0x180024dd7  call    LUAIsShadowAdminEnabled
0x180024ddc  test    eax, eax
0x180024dde  jz      short loc_180024D85
0x180024de0  mov     rdx, [rbp+0A0h+Handle]; void *
0x180024de4  test    rdx, rdx
0x180024de7  jz      short loc_180024D85
0x180024de9  mov     rcx, r14; void *
0x180024dec  call    ?AiSettingsSync@@YAJPEAX0@Z; AiSettingsSync(void *,void *)
0x180024df1  jmp     short loc_180024D85
0x180024df3  mov     rbx, [rbp+0A0h+var_108]
0x180024df7  mov     rcx, [rbp+0A0h+hThread+8]; hObject
0x180024dfb  test    rcx, rcx
0x180024dfe  jz      short loc_180024E0F
0x180024e00  call    cs:__imp_CloseHandle
0x180024e07  nop     dword ptr [rax+rax+00h]
0x180024e0c  mov     eax, [rbp+0A0h+ExitCode]
0x180024e0f  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x180024e13  mov     edi, 42Bh
0x180024e18  test    rcx, rcx
0x180024e1b  jz      short loc_180024E46
0x180024e1d  test    eax, eax
0x180024e1f  jz      short loc_180024E37
0x180024e21  cmp     eax, edi
0x180024e23  jz      short loc_180024E37
0x180024e25  mov     edx, eax; uExitCode
0x180024e27  call    cs:__imp_TerminateProcess
0x180024e2e  nop     dword ptr [rax+rax+00h]
0x180024e33  mov     rcx, [rbp+0A0h+hThread]; hObject
0x180024e37  call    cs:__imp_CloseHandle
0x180024e3e  nop     dword ptr [rax+rax+00h]
0x180024e43  mov     eax, [rbp+0A0h+ExitCode]
0x180024e46  test    rbx, rbx
0x180024e49  jz      short loc_180024E5D
0x180024e4b  mov     rcx, rbx; Handle
0x180024e4e  call    cs:__imp_NtClose
0x180024e55  nop     dword ptr [rax+rax+00h]
0x180024e5a  mov     eax, [rbp+0A0h+ExitCode]
0x180024e5d  cmp     eax, 102h
0x180024e62  jz      short loc_180024E68
0x180024e64  cmp     eax, edi
0x180024e66  jnz     short loc_180024E6D
0x180024e68  mov     eax, 4C7h
0x180024e6d  mov     rcx, [rbp+0A0h+var_40]
0x180024e71  xor     rcx, rsp; StackCookie
0x180024e74  call    __security_check_cookie
0x180024e79  mov     rbx, [rsp+1B0h+arg_18]
0x180024e81  add     rsp, 180h
0x180024e88  pop     r15
0x180024e8a  pop     r14
0x180024e8c  pop     r13
0x180024e8e  pop     r12
0x180024e90  pop     rdi
0x180024e91  pop     rsi
0x180024e92  pop     rbp
0x180024e93  retn
```
