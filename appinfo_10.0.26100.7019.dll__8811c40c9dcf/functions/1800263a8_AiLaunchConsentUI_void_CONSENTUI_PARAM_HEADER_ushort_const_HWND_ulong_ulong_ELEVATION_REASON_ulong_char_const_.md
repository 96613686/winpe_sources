# AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)

- ea: `0x1800263a8`
- end: `0x180026789`
- name: `?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z`
- size: `993`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180016c54`
- `0x18001e424`
- `0x1800249f0`
- `0x18003adb0`

## callees

- `0x18000d9a0`
- `0x18000dac0`
- `0x18000ea70`
- `0x180010590`
- `0x180012600`
- `0x180014bb0`
- `0x180014d40`
- `0x18002444c`
- `0x1800263a8`
- `0x180026964`
- `0x18003ef30`
- `0x1800402e4`
- `0x180041e64`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180026556`
- `msvcrt!swprintf_s` at `0x180026556`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026621`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026650`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002660b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002660b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002671b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002671b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180026640`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180026640`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002652e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002652e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002672b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002672b`
- `ntdll!NtClose` at `0x180026671`
- `ntdll!NtClose` at `0x180026742`
- `ntdll!NtClose` at `0x180026671`
- `ntdll!NtClose` at `0x180026742`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800266a1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800266a1`

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
  unsigned __int16 *v10; // r15
  _QWORD *v11; // r13
  void *v12; // rbx
  int v13; // r12d
  struct _SESSION_LOCK *v14; // r14
  DWORD result; // eax
  unsigned int v16; // edi
  __int64 v17; // rax
  void *v18; // r14
  int *v19; // r15
  int v20; // ebx
  DWORD CurrentProcessId; // eax
  HANDLE v22; // rcx
  HANDLE v23; // rax
  NTSTATUS v24; // eax
  DWORD v25; // eax
  HANDLE hProcess; // rcx
  unsigned __int16 *v27; // [rsp+20h] [rbp-F0h]
  unsigned __int16 *v28; // [rsp+38h] [rbp-D8h]
  DWORD ExitCode; // [rsp+90h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp-78h] BYREF
  int v31; // [rsp+A0h] [rbp-70h] BYREF
  void *v32; // [rsp+A8h] [rbp-68h] BYREF
  struct _PROCESS_INFORMATION hThread; // [rsp+B0h] [rbp-60h] BYREF
  struct _SESSION_LOCK *v34; // [rsp+C8h] [rbp-48h] BYREF
  void *v35; // [rsp+D0h] [rbp-40h]
  __int64 v36; // [rsp+D8h] [rbp-38h]
  int *v37; // [rsp+E0h] [rbp-30h]
  unsigned __int16 *v38; // [rsp+E8h] [rbp-28h]
  wchar_t Buffer[64]; // [rsp+F0h] [rbp-20h] BYREF

  v10 = a9;
  v11 = a10;
  v12 = 0;
  Handle = 0;
  v38 = a3;
  v13 = 0;
  v37 = a2;
  v14 = 0;
  v35 = a1;
  v36 = a4;
  v32 = 0;
  memset(&hThread, 0, sizeof(hThread));
  v31 = 0;
  v34 = 0;
  memset_0(Buffer, 0, 0x7Au);
  *v11 = 0;
  if ( a7 == 9 )
  {
    v16 = a6;
  }
  else
  {
    if ( !a5 )
    {
      result = 1459;
LABEL_4:
      ExitCode = result;
      goto LABEL_39;
    }
    if ( (a6 & 0x10) == 0 )
    {
      result = AipGetElevationPromptType(&a6, (enum _CONSENTUI_PROMPT_TYPE *)&v31);
      ExitCode = result;
      if ( result )
        goto LABEL_39;
      v13 = v31;
    }
    result = AipCheckLegacySecureDesktopPolicy(a5, &a6);
    ExitCode = result;
    if ( result )
      goto LABEL_39;
    if ( v10
      && (!g_pConsentExeTelemetryRateLimiter
       || !(unsigned int)RateLimiter::RequestPermission(g_pConsentExeTelemetryRateLimiter)) )
    {
      v10 = 0;
    }
    v16 = a6;
    if ( (a6 & 0x110) == 0x100 )
    {
      result = AipGetSessionLock(a5, 0, &v34);
      ExitCode = result;
      if ( result )
        goto LABEL_39;
      v14 = v34;
    }
  }
  if ( v14 )
    v17 = *(_QWORD *)v14;
  else
    v17 = 0;
  v18 = v35;
  v28 = v10;
  v19 = v37;
  AipSetFixedParams(v37, a7, v36, v35, a5, v13, v17, v28, v16, &Handle);
  v20 = *v19;
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(v27) = v20;
  swprintf_s(Buffer, 0x3Du, L"consent.exe %u %u %p", CurrentProcessId, v27, v19);
  result = AipBuildConsentToken(a5, &v32);
  v12 = v32;
  ExitCode = result;
  if ( !result )
  {
    result = AiLaunchProcess(0, v32, 0, 0x1000080u, 0, Buffer, 0x400u, 0, v38, 0, a5, 0, 0, 0, 0, 0, &hThread);
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
            v22 = Handle;
            if ( !Handle )
              goto LABEL_39;
            goto LABEL_28;
          }
          if ( (v16 & 0x10000) != 0 )
          {
            v23 = Handle;
            if ( !Handle )
            {
LABEL_34:
              *v11 = v23;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
                && (unsigned int)LUAIsShadowAdminEnabled()
                && Handle )
              {
                AiSettingsSync(v18, Handle);
              }
              goto LABEL_38;
            }
            v24 = AipMarkAutoApprovedToken(Handle);
            if ( v24 < 0 )
            {
              v25 = RtlNtStatusToDosErrorNoTeb(v24);
              v22 = Handle;
              ExitCode = v25;
LABEL_28:
              NtClose(v22);
              Handle = 0;
LABEL_38:
              result = ExitCode;
              goto LABEL_39;
            }
          }
          v23 = Handle;
          goto LABEL_34;
        }
      }
    }
  }
LABEL_39:
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
0x1800263a8  mov     [rsp-8+arg_18], rbx
0x1800263ad  push    rbp
0x1800263ae  push    rsi
0x1800263af  push    rdi
0x1800263b0  push    r12
0x1800263b2  push    r13
0x1800263b4  push    r14
0x1800263b6  push    r15
0x1800263b8  lea     rbp, [rsp-70h]
0x1800263bd  sub     rsp, 180h
0x1800263c4  mov     rax, cs:__security_cookie
0x1800263cb  xor     rax, rsp
0x1800263ce  mov     [rbp+0A0h+var_40], rax
0x1800263d2  mov     r15, [rbp+0A0h+arg_40]
0x1800263d9  xor     eax, eax
0x1800263db  mov     r13, [rbp+0A0h+arg_48]
0x1800263e2  xor     ebx, ebx
0x1800263e4  and     [rbp+0A0h+Handle], rax
0x1800263e8  xorps   xmm0, xmm0
0x1800263eb  mov     [rbp+0A0h+var_C8], r8
0x1800263ef  xor     r12d, r12d
0x1800263f2  mov     [rbp+0A0h+var_D0], rdx
0x1800263f6  xor     r14d, r14d
0x1800263f9  mov     [rbp+0A0h+var_E0], rcx
0x1800263fd  lea     r8d, [rbx+7Ah]; Size
0x180026401  xor     edx, edx; Val
0x180026403  mov     [rbp+0A0h+var_D8], r9
0x180026407  lea     rcx, [rbp+0A0h+Buffer]; void *
0x18002640b  mov     [rbp+0A0h+var_108], rbx
0x18002640f  movups  xmmword ptr [rbp+0A0h+hThread], xmm0
0x180026413  mov     [rbp+0A0h+var_F0], rax
0x180026417  mov     [rbp+0A0h+var_110], r12d
0x18002641b  mov     [rbp+0A0h+var_E8], r14
0x18002641f  call    memset_0
0x180026424  and     [r13+0], rbx
0x180026428  cmp     [rbp+0A0h+arg_30], 9
0x18002642f  mov     esi, [rbp+0A0h+arg_20]
0x180026435  jz      loc_1800264DC
0x18002643b  test    esi, esi
0x18002643d  jnz     short loc_18002644C
0x18002643f  mov     eax, 5B3h
0x180026444  mov     [rbp+0A0h+ExitCode], eax
0x180026447  jmp     loc_1800266EB
0x18002644c  test    byte ptr [rbp+0A0h+arg_28], 10h
0x180026453  jnz     short loc_180026474
0x180026455  lea     rdx, [rbp+0A0h+var_110]; enum _CONSENTUI_PROMPT_TYPE *
0x180026459  lea     rcx, [rbp+0A0h+arg_28]; unsigned int *
0x180026460  call    ?AipGetElevationPromptType@@YAKPEAKPEAW4_CONSENTUI_PROMPT_TYPE@@@Z; AipGetElevationPromptType(ulong *,_CONSENTUI_PROMPT_TYPE *)
0x180026465  mov     [rbp+0A0h+ExitCode], eax
0x180026468  test    eax, eax
0x18002646a  jnz     loc_1800266EB
0x180026470  mov     r12d, [rbp+0A0h+var_110]
0x180026474  lea     rdx, [rbp+0A0h+arg_28]; unsigned int *
0x18002647b  mov     ecx, esi; unsigned int
0x18002647d  call    ?AipCheckLegacySecureDesktopPolicy@@YAKKPEAK@Z; AipCheckLegacySecureDesktopPolicy(ulong,ulong *)
0x180026482  mov     [rbp+0A0h+ExitCode], eax
0x180026485  test    eax, eax
0x180026487  jnz     loc_1800266EB
0x18002648d  test    r15, r15
0x180026490  jz      short loc_1800264AA
0x180026492  mov     rcx, cs:?g_pConsentExeTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x180026499  test    rcx, rcx
0x18002649c  jz      short loc_1800264A7
0x18002649e  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x1800264a3  test    eax, eax
0x1800264a5  jnz     short loc_1800264AA
0x1800264a7  xor     r15d, r15d
0x1800264aa  mov     edi, [rbp+0A0h+arg_28]
0x1800264b0  mov     eax, edi
0x1800264b2  and     eax, 110h
0x1800264b7  cmp     eax, 100h
0x1800264bc  jnz     short loc_1800264E2
0x1800264be  lea     r8, [rbp+0A0h+var_E8]; struct _SESSION_LOCK **
0x1800264c2  xor     edx, edx; int
0x1800264c4  mov     ecx, esi; unsigned int
0x1800264c6  call    ?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z; AipGetSessionLock(ulong,int,_SESSION_LOCK * *)
0x1800264cb  mov     [rbp+0A0h+ExitCode], eax
0x1800264ce  test    eax, eax
0x1800264d0  jnz     loc_1800266EB
0x1800264d6  mov     r14, [rbp+0A0h+var_E8]
0x1800264da  jmp     short loc_1800264E2
0x1800264dc  mov     edi, [rbp+0A0h+arg_28]
0x1800264e2  test    r14, r14
0x1800264e5  jz      short loc_1800264EC
0x1800264e7  mov     rax, [r14]
0x1800264ea  jmp     short loc_1800264EE
0x1800264ec  xor     eax, eax
0x1800264ee  mov     r14, [rbp+0A0h+var_E0]
0x1800264f2  lea     rcx, [rbp+0A0h+Handle]
0x1800264f6  mov     r8, [rbp+0A0h+var_D8]
0x1800264fa  mov     r9, r14
0x1800264fd  mov     edx, [rbp+0A0h+arg_30]
0x180026503  mov     [rsp+1B0h+var_168], rcx; struct _APPINFO_STARTUPINFO *
0x180026508  mov     dword ptr [rsp+1B0h+var_170], edi
0x18002650c  mov     [rsp+1B0h+var_178], r15; unsigned __int16 *
0x180026511  mov     r15, [rbp+0A0h+var_D0]
0x180026515  mov     qword ptr [rsp+1B0h+var_180], rax
0x18002651a  mov     rcx, r15
0x18002651d  mov     dword ptr [rsp+1B0h+var_188], r12d
0x180026522  mov     dword ptr [rsp+1B0h+var_190], esi
0x180026526  call    ?AipSetFixedParams@@YAXPEAU_CONSENTUI_PARAM_HEADER@@W4ELEVATION_REASON@@PEAUHWND__@@PEAXKW4_CONSENTUI_PROMPT_TYPE@@3PEBDKPEAU_CONSENTUI_RETURN_PARAM@@@Z; AipSetFixedParams(_CONSENTUI_PARAM_HEADER *,ELEVATION_REASON,HWND__ *,void *,ulong,_CONSENTUI_PROMPT_TYPE,void *,char const *,ulong,_CONSENTUI_RETURN_PARAM *)
0x18002652b  mov     ebx, [r15]
0x18002652e  call    cs:__imp_GetCurrentProcessId
0x180026535  nop     dword ptr [rax+rax+00h]
0x18002653a  mov     [rsp+1B0h+var_188], r15
0x18002653f  lea     r8, aConsentExeUUP; "consent.exe %u %u %p"
0x180026546  mov     r9d, eax
0x180026549  mov     dword ptr [rsp+1B0h+var_190], ebx; unsigned __int16 *
0x18002654d  mov     edx, 3Dh ; '='; BufferCount
0x180026552  lea     rcx, [rbp+0A0h+Buffer]; Buffer
0x180026556  call    cs:__imp_swprintf_s
0x18002655d  nop     dword ptr [rax+rax+00h]
0x180026562  lea     rdx, [rbp+0A0h+var_108]; void **
0x180026566  mov     ecx, esi; unsigned int
0x180026568  call    ?AipBuildConsentToken@@YAKKPEAPEAX@Z; AipBuildConsentToken(ulong,void * *)
0x18002656d  mov     rbx, [rbp+0A0h+var_108]
0x180026571  mov     [rbp+0A0h+ExitCode], eax
0x180026574  test    eax, eax
0x180026576  jnz     loc_1800266EB
0x18002657c  lea     rax, [rbp+0A0h+hThread]
0x180026580  mov     r9d, 1000080h; unsigned int
0x180026586  mov     [rsp+1B0h+var_130], rax; struct _PROCESS_INFORMATION *
0x18002658e  xor     r8d, r8d; void *
0x180026591  and     [rsp+1B0h+var_138], 0
0x180026597  mov     rdx, rbx; void *
0x18002659a  and     [rsp+1B0h+var_140], 0
0x1800265a0  xor     ecx, ecx; void *
0x1800265a2  and     [rsp+1B0h+var_148], 0
0x1800265a8  and     [rsp+1B0h+var_150], 0
0x1800265ad  and     [rsp+1B0h+var_158], 0
0x1800265b3  mov     rax, [rbp+0A0h+var_C8]
0x1800265b7  mov     [rsp+1B0h+var_160], esi; unsigned int
0x1800265bb  and     [rsp+1B0h+var_168], 0
0x1800265c1  mov     [rsp+1B0h+var_170], rax; unsigned __int16 *
0x1800265c6  lea     rax, [rbp+0A0h+Buffer]
0x1800265ca  and     [rsp+1B0h+var_178], 0
0x1800265d0  mov     [rsp+1B0h+var_180], 400h; unsigned int
0x1800265d8  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x1800265dd  and     [rsp+1B0h+var_190], 0
0x1800265e3  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)
0x1800265e8  mov     [rbp+0A0h+ExitCode], eax
0x1800265eb  test    eax, eax
0x1800265ed  jnz     loc_1800266EB
0x1800265f3  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x1800265f7  call    ?AipVerifyConsent@@YAKPEAX@Z; AipVerifyConsent(void *)
0x1800265fc  mov     [rbp+0A0h+ExitCode], eax
0x1800265ff  test    eax, eax
0x180026601  jnz     loc_1800266EB
0x180026607  mov     rcx, [rbp+0A0h+hThread+8]; hThread
0x18002660b  call    cs:__imp_ResumeThread
0x180026612  nop     dword ptr [rax+rax+00h]
0x180026617  mov     edx, [rbp+0A0h+dwMilliseconds]; dwMilliseconds
0x18002661d  mov     rcx, [rbp+0A0h+hThread]; hHandle
0x180026621  call    cs:__imp_WaitForSingleObject
0x180026628  nop     dword ptr [rax+rax+00h]
0x18002662d  mov     [rbp+0A0h+ExitCode], eax
0x180026630  test    eax, eax
0x180026632  jnz     loc_1800266EB
0x180026638  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x18002663c  lea     rdx, [rbp+0A0h+ExitCode]; lpExitCode
0x180026640  call    cs:__imp_GetExitCodeProcess
0x180026647  nop     dword ptr [rax+rax+00h]
0x18002664c  test    eax, eax
0x18002664e  jnz     short loc_180026661
0x180026650  call    cs:__imp_GetLastError
0x180026657  nop     dword ptr [rax+rax+00h]
0x18002665c  jmp     loc_180026444
0x180026661  mov     eax, [rbp+0A0h+ExitCode]
0x180026664  test    eax, eax
0x180026666  jz      short loc_180026684
0x180026668  mov     rcx, [rbp+0A0h+Handle]; Handle
0x18002666c  test    rcx, rcx
0x18002666f  jz      short loc_1800266EB
0x180026671  call    cs:__imp_NtClose
0x180026678  nop     dword ptr [rax+rax+00h]
0x18002667d  and     [rbp+0A0h+Handle], 0
0x180026682  jmp     short loc_1800266E8
0x180026684  bt      edi, 10h
0x180026688  jnb     short loc_1800266B6
0x18002668a  mov     rax, [rbp+0A0h+Handle]
0x18002668e  test    rax, rax
0x180026691  jz      short loc_1800266BA
0x180026693  mov     rcx, rax; TokenHandle
0x180026696  call    ?AipMarkAutoApprovedToken@@YAJPEAX@Z; AipMarkAutoApprovedToken(void *)
0x18002669b  test    eax, eax
0x18002669d  jns     short loc_1800266B6
0x18002669f  mov     ecx, eax; Status
0x1800266a1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800266a8  nop     dword ptr [rax+rax+00h]
0x1800266ad  mov     rcx, [rbp+0A0h+Handle]
0x1800266b1  mov     [rbp+0A0h+ExitCode], eax
0x1800266b4  jmp     short loc_180026671
0x1800266b6  mov     rax, [rbp+0A0h+Handle]
0x1800266ba  mov     [r13+0], rax
0x1800266be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800266c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1800266ca  test    al, al
0x1800266cc  jz      short loc_1800266E8
0x1800266ce  call    LUAIsShadowAdminEnabled
0x1800266d3  test    eax, eax
0x1800266d5  jz      short loc_1800266E8
0x1800266d7  mov     rdx, [rbp+0A0h+Handle]; void *
0x1800266db  test    rdx, rdx
0x1800266de  jz      short loc_1800266E8
0x1800266e0  mov     rcx, r14; void *
0x1800266e3  call    ?AiSettingsSync@@YAJPEAX0@Z; AiSettingsSync(void *,void *)
0x1800266e8  mov     eax, [rbp+0A0h+ExitCode]
0x1800266eb  mov     rcx, [rbp+0A0h+hThread+8]; hObject
0x1800266ef  test    rcx, rcx
0x1800266f2  jz      short loc_180026703
0x1800266f4  call    cs:__imp_CloseHandle
0x1800266fb  nop     dword ptr [rax+rax+00h]
0x180026700  mov     eax, [rbp+0A0h+ExitCode]
0x180026703  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x180026707  mov     edi, 42Bh
0x18002670c  test    rcx, rcx
0x18002670f  jz      short loc_18002673A
0x180026711  test    eax, eax
0x180026713  jz      short loc_18002672B
0x180026715  cmp     eax, edi
0x180026717  jz      short loc_18002672B
0x180026719  mov     edx, eax; uExitCode
0x18002671b  call    cs:__imp_TerminateProcess
0x180026722  nop     dword ptr [rax+rax+00h]
0x180026727  mov     rcx, [rbp+0A0h+hThread]; hObject
0x18002672b  call    cs:__imp_CloseHandle
0x180026732  nop     dword ptr [rax+rax+00h]
0x180026737  mov     eax, [rbp+0A0h+ExitCode]
0x18002673a  test    rbx, rbx
0x18002673d  jz      short loc_180026751
0x18002673f  mov     rcx, rbx; Handle
0x180026742  call    cs:__imp_NtClose
0x180026749  nop     dword ptr [rax+rax+00h]
0x18002674e  mov     eax, [rbp+0A0h+ExitCode]
0x180026751  cmp     eax, 102h
0x180026756  jz      short loc_18002675C
0x180026758  cmp     eax, edi
0x18002675a  jnz     short loc_180026761
0x18002675c  mov     eax, 4C7h
0x180026761  mov     rcx, [rbp+0A0h+var_40]
0x180026765  xor     rcx, rsp; StackCookie
0x180026768  call    __security_check_cookie
0x18002676d  mov     rbx, [rsp+1B0h+arg_18]
0x180026775  add     rsp, 180h
0x18002677c  pop     r15
0x18002677e  pop     r14
0x180026780  pop     r13
0x180026782  pop     r12
0x180026784  pop     rdi
0x180026785  pop     rsi
0x180026786  pop     rbp
0x180026787  retn
```
