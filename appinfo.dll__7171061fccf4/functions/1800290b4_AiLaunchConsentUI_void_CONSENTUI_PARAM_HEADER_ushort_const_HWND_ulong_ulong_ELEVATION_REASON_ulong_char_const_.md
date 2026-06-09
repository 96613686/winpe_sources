# AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)

- ea: `0x1800290b4`
- end: `0x180029467`
- name: `?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z`
- size: `947`
- prototype: `DWORD __fastcall(void *, int *, WCHAR *, __int64, unsigned int, unsigned int, unsigned int, DWORD dwMilliseconds, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180021968`
- `0x180026ba0`
- `0x18003e220`
- `0x18003f14c`

## callees

- `0x18000ccf0`
- `0x18000ce00`
- `0x18000df30`
- `0x1800102d0`
- `0x180011220`
- `0x18001aee4`
- `0x180026630`
- `0x1800290b4`
- `0x180029470`
- `0x18002967c`
- `0x18002d8fc`
- `0x1800436a8`
- `0x1800461e8`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180029256`
- `msvcrt!swprintf_s` at `0x180029256`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029331`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029354`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002934a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002934a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180029321`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180029321`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002940c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002940c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029234`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800293eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800293eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029416`
- `ntdll!NtClose` at `0x18002936f`
- `ntdll!NtClose` at `0x180029427`
- `ntdll!NtClose` at `0x18002936f`
- `ntdll!NtClose` at `0x180029427`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002939b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002939b`

## pseudocode

```c
DWORD __fastcall AiLaunchConsentUI(
        void *a1,
        int *a2,
        WCHAR *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        DWORD dwMilliseconds,
        __int64 a9,
        _QWORD *a10)
{
  __int64 v10; // r14
  _QWORD *v11; // r12
  void *v13; // rbx
  int v14; // r15d
  bool v15; // zf
  DWORD result; // eax
  unsigned int v17; // edi
  __int64 v18; // rcx
  int *v19; // r14
  int v20; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v22; // rdx
  HANDLE v23; // rcx
  HANDLE v24; // rax
  NTSTATUS v25; // eax
  DWORD v26; // eax
  __int64 v27; // rcx
  HANDLE v28; // rcx
  __int64 v29; // [rsp+20h] [rbp-110h]
  __int64 v30; // [rsp+38h] [rbp-F8h]
  DWORD ExitCode; // [rsp+B0h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-78h] BYREF
  int v33; // [rsp+C0h] [rbp-70h] BYREF
  void *v34; // [rsp+C8h] [rbp-68h] BYREF
  HANDLE hThread[2]; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v36; // [rsp+E0h] [rbp-50h]
  struct _SESSION_LOCK *v37; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-40h]
  int *v39; // [rsp+F8h] [rbp-38h]
  WCHAR *v40; // [rsp+100h] [rbp-30h]
  wchar_t Buffer[64]; // [rsp+110h] [rbp-20h] BYREF

  v10 = a9;
  v11 = a10;
  v40 = a3;
  v39 = a2;
  v38 = a4;
  v13 = 0;
  ExitCode = 0;
  v34 = 0;
  v36 = 0;
  *(_OWORD *)hThread = 0;
  v14 = 0;
  v33 = 0;
  Handle = 0;
  v37 = 0;
  memset_0(Buffer, 0, 0x7Au);
  v15 = a7 == 9;
  *v11 = 0;
  if ( v15 )
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
      goto LABEL_39;
    }
    if ( (a6 & 0x10) == 0 )
    {
      result = AipGetElevationPromptType(&a6, (enum _CONSENTUI_PROMPT_TYPE *)&v33);
      ExitCode = result;
      if ( result )
        goto LABEL_39;
      v14 = v33;
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
    v17 = a6;
    if ( (a6 & 0x110) == 0x100 )
    {
      result = AipGetSessionLock(a5, 0, &v37);
      ExitCode = result;
      if ( result )
        goto LABEL_39;
      if ( v37 )
      {
        v18 = *(_QWORD *)v37;
        goto LABEL_19;
      }
    }
  }
  v18 = 0;
LABEL_19:
  v30 = v10;
  v19 = v39;
  AipSetFixedParams(v39, a7, v38, a1, a5, v14, v18, v30, v17, &Handle);
  v20 = *v19;
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(v29) = v20;
  swprintf_s(Buffer, 0x3Du, L"consent.exe %u %u %p", CurrentProcessId, v29, v19);
  result = AipBuildConsentToken(a5, &v34);
  ExitCode = result;
  if ( result )
  {
    v13 = v34;
  }
  else
  {
    v13 = v34;
    result = AiLaunchProcess(
               0,
               v34,
               0,
               0x21000080u,
               0,
               Buffer,
               0x400u,
               0,
               v40,
               0,
               0,
               0,
               a5,
               0,
               0,
               0,
               0,
               0,
               0,
               hThread,
               0);
    ExitCode = result;
    if ( !result )
    {
      result = AipVerifyConsent(hThread[0]);
      ExitCode = result;
      if ( !result )
      {
        ResumeThread(hThread[1]);
        result = WaitForSingleObject(hThread[0], dwMilliseconds);
        ExitCode = result;
        if ( !result )
        {
          if ( !GetExitCodeProcess(hThread[0], &ExitCode) )
          {
            result = GetLastError();
            goto LABEL_4;
          }
          result = ExitCode;
          if ( ExitCode )
          {
            v23 = Handle;
            if ( !Handle )
              goto LABEL_39;
            goto LABEL_27;
          }
          if ( (v17 & 0x10000) != 0 )
          {
            v24 = Handle;
            if ( !Handle )
            {
LABEL_34:
              *v11 = v24;
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                      `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                      v22)
                && (unsigned int)LUAIsShadowAdminEnabled(v27)
                && Handle )
              {
                AiSettingsSync(a1, Handle);
              }
              goto LABEL_28;
            }
            v25 = AipMarkAutoApprovedToken(Handle);
            if ( v25 < 0 )
            {
              v26 = RtlNtStatusToDosErrorNoTeb(v25);
              v23 = Handle;
              ExitCode = v26;
LABEL_27:
              NtClose(v23);
              Handle = 0;
LABEL_28:
              result = ExitCode;
              goto LABEL_39;
            }
          }
          v24 = Handle;
          goto LABEL_34;
        }
      }
    }
  }
LABEL_39:
  if ( hThread[1] )
  {
    CloseHandle(hThread[1]);
    result = ExitCode;
  }
  v28 = hThread[0];
  if ( hThread[0] )
  {
    if ( result && result != 1067 )
    {
      TerminateProcess(hThread[0], result);
      v28 = hThread[0];
    }
    CloseHandle(v28);
    result = ExitCode;
  }
  if ( v13 )
  {
    NtClose(v13);
    result = ExitCode;
  }
  if ( result == 258 || result == 1067 )
    return 1223;
  return result;
}

```

## disassembly

```asm
0x1800290b4  mov     [rsp-8+arg_18], rbx
0x1800290b9  push    rbp
0x1800290ba  push    rsi
0x1800290bb  push    rdi
0x1800290bc  push    r12
0x1800290be  push    r13
0x1800290c0  push    r14
0x1800290c2  push    r15
0x1800290c4  lea     rbp, [rsp-70h]
0x1800290c9  sub     rsp, 1A0h
0x1800290d0  mov     rax, cs:__security_cookie
0x1800290d7  xor     rax, rsp
0x1800290da  mov     [rbp+0A0h+var_40], rax
0x1800290de  mov     r14, [rbp+0A0h+arg_40]
0x1800290e5  xor     edi, edi
0x1800290e7  mov     r12, [rbp+0A0h+arg_48]
0x1800290ee  mov     r13, rcx
0x1800290f1  mov     [rbp+0A0h+var_D0], r8
0x1800290f5  lea     rcx, [rbp+0A0h+Buffer]; void *
0x1800290f9  mov     [rbp+0A0h+var_D8], rdx
0x1800290fd  xorps   xmm0, xmm0
0x180029100  xor     eax, eax
0x180029102  mov     [rbp+0A0h+var_E0], r9
0x180029106  mov     ebx, edi
0x180029108  mov     [rbp+0A0h+ExitCode], edi
0x18002910b  lea     r8d, [rdi+7Ah]; Size
0x18002910f  mov     [rbp+0A0h+var_108], rbx
0x180029113  xor     edx, edx; Val
0x180029115  mov     [rbp+0A0h+var_F0], rax
0x180029119  movups  xmmword ptr [rbp+0A0h+hThread], xmm0
0x18002911d  mov     r15d, edi
0x180029120  mov     [rbp+0A0h+var_110], edi
0x180029123  mov     [rbp+0A0h+Handle], rdi
0x180029127  mov     [rbp+0A0h+var_E8], rdi
0x18002912b  call    memset_0
0x180029130  cmp     [rbp+0A0h+arg_30], 9
0x180029137  mov     esi, [rbp+0A0h+arg_20]
0x18002913d  mov     [r12], rdi
0x180029141  jz      loc_1800291F0
0x180029147  test    esi, esi
0x180029149  jnz     short loc_180029158
0x18002914b  mov     eax, 5B3h
0x180029150  mov     [rbp+0A0h+ExitCode], eax
0x180029153  jmp     loc_1800293E2
0x180029158  test    byte ptr [rbp+0A0h+arg_28], 10h
0x18002915f  jnz     short loc_180029180
0x180029161  lea     rdx, [rbp+0A0h+var_110]; enum _CONSENTUI_PROMPT_TYPE *
0x180029165  lea     rcx, [rbp+0A0h+arg_28]; unsigned int *
0x18002916c  call    ?AipGetElevationPromptType@@YAKPEAKPEAW4_CONSENTUI_PROMPT_TYPE@@@Z; AipGetElevationPromptType(ulong *,_CONSENTUI_PROMPT_TYPE *)
0x180029171  mov     [rbp+0A0h+ExitCode], eax
0x180029174  test    eax, eax
0x180029176  jnz     loc_1800293E2
0x18002917c  mov     r15d, [rbp+0A0h+var_110]
0x180029180  lea     rdx, [rbp+0A0h+arg_28]; unsigned int *
0x180029187  mov     ecx, esi; unsigned int
0x180029189  call    ?AipCheckLegacySecureDesktopPolicy@@YAKKPEAK@Z; AipCheckLegacySecureDesktopPolicy(ulong,ulong *)
0x18002918e  mov     [rbp+0A0h+ExitCode], eax
0x180029191  test    eax, eax
0x180029193  jnz     loc_1800293E2
0x180029199  test    r14, r14
0x18002919c  jz      short loc_1800291B6
0x18002919e  mov     rcx, cs:?g_pConsentExeTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x1800291a5  test    rcx, rcx
0x1800291a8  jz      short loc_1800291B3
0x1800291aa  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x1800291af  test    eax, eax
0x1800291b1  jnz     short loc_1800291B6
0x1800291b3  mov     r14, rdi
0x1800291b6  mov     edi, [rbp+0A0h+arg_28]
0x1800291bc  mov     eax, edi
0x1800291be  and     eax, 110h
0x1800291c3  cmp     eax, 100h
0x1800291c8  jnz     short loc_1800291F6
0x1800291ca  lea     r8, [rbp+0A0h+var_E8]; struct _SESSION_LOCK **
0x1800291ce  xor     edx, edx; int
0x1800291d0  mov     ecx, esi; unsigned int
0x1800291d2  call    ?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z; AipGetSessionLock(ulong,int,_SESSION_LOCK * *)
0x1800291d7  mov     [rbp+0A0h+ExitCode], eax
0x1800291da  test    eax, eax
0x1800291dc  jnz     loc_1800293E2
0x1800291e2  mov     rax, [rbp+0A0h+var_E8]
0x1800291e6  test    rax, rax
0x1800291e9  jz      short loc_1800291F6
0x1800291eb  mov     rcx, [rax]
0x1800291ee  jmp     short loc_1800291F8
0x1800291f0  mov     edi, [rbp+0A0h+arg_28]
0x1800291f6  xor     ecx, ecx
0x1800291f8  mov     r8, [rbp+0A0h+var_E0]
0x1800291fc  lea     rax, [rbp+0A0h+Handle]
0x180029200  mov     edx, [rbp+0A0h+arg_30]
0x180029206  mov     r9, r13
0x180029209  mov     [rsp+1D0h+var_188], rax
0x18002920e  mov     dword ptr [rsp+1D0h+var_190], edi
0x180029212  mov     [rsp+1D0h+var_198], r14
0x180029217  mov     r14, [rbp+0A0h+var_D8]
0x18002921b  mov     [rsp+1D0h+var_1A0], rcx
0x180029220  mov     rcx, r14
0x180029223  mov     dword ptr [rsp+1D0h+var_1A8], r15d
0x180029228  mov     dword ptr [rsp+1D0h+var_1B0], esi
0x18002922c  call    ?AipSetFixedParams@@YAXPEAU_CONSENTUI_PARAM_HEADER@@W4ELEVATION_REASON@@PEAUHWND__@@PEAXKW4_CONSENTUI_PROMPT_TYPE@@3PEBDKPEAU_CONSENTUI_RETURN_PARAM@@@Z; AipSetFixedParams(_CONSENTUI_PARAM_HEADER *,ELEVATION_REASON,HWND__ *,void *,ulong,_CONSENTUI_PROMPT_TYPE,void *,char const *,ulong,_CONSENTUI_RETURN_PARAM *)
0x180029231  mov     ebx, [r14]
0x180029234  call    cs:__imp_GetCurrentProcessId
0x18002923a  mov     [rsp+1D0h+var_1A8], r14
0x18002923f  lea     r8, aConsentExeUUP; "consent.exe %u %u %p"
0x180029246  mov     r9d, eax
0x180029249  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x18002924d  mov     edx, 3Dh ; '='; BufferCount
0x180029252  lea     rcx, [rbp+0A0h+Buffer]; Buffer
0x180029256  call    cs:__imp_swprintf_s
0x18002925c  lea     rdx, [rbp+0A0h+var_108]; void **
0x180029260  mov     ecx, esi; unsigned int
0x180029262  call    ?AipBuildConsentToken@@YAKKPEAPEAX@Z; AipBuildConsentToken(ulong,void * *)
0x180029267  xor     r14d, r14d
0x18002926a  mov     [rbp+0A0h+ExitCode], eax
0x18002926d  test    eax, eax
0x18002926f  jnz     loc_1800293DE
0x180029275  mov     rbx, [rbp+0A0h+var_108]
0x180029279  lea     rax, [rbp+0A0h+hThread]
0x18002927d  mov     [rsp+1D0h+var_130], r14
0x180029285  mov     r9d, 21000080h
0x18002928b  mov     [rsp+1D0h+var_138], rax
0x180029293  xor     r8d, r8d
0x180029296  mov     rax, [rbp+0A0h+var_D0]
0x18002929a  mov     rdx, rbx
0x18002929d  mov     [rsp+1D0h+var_140], r14
0x1800292a5  xor     ecx, ecx
0x1800292a7  mov     [rsp+1D0h+var_148], r14
0x1800292af  mov     [rsp+1D0h+var_150], r14
0x1800292b7  mov     [rsp+1D0h+var_158], r14d
0x1800292bc  mov     [rsp+1D0h+var_160], r14d
0x1800292c1  mov     [rsp+1D0h+var_168], r14
0x1800292c6  mov     [rsp+1D0h+var_170], esi
0x1800292ca  mov     [rsp+1D0h+var_178], r14
0x1800292cf  mov     [rsp+1D0h+var_180], r14
0x1800292d4  mov     [rsp+1D0h+var_188], r14
0x1800292d9  mov     [rsp+1D0h+var_190], rax
0x1800292de  lea     rax, [rbp+0A0h+Buffer]
0x1800292e2  mov     [rsp+1D0h+var_198], r14
0x1800292e7  mov     dword ptr [rsp+1D0h+var_1A0], 400h
0x1800292ef  mov     [rsp+1D0h+var_1A8], rax
0x1800292f4  mov     [rsp+1D0h+var_1B0], r14
0x1800292f9  call    ?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@PEAU_SECURITY_CAPABILITIES@@K2KW4AicAgenticFlags@@0_K1PEAU_PROCESS_INFORMATION@@2@Z; AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,_SECURITY_CAPABILITIES *,ulong,ushort *,ulong,AicAgenticFlags,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *,ushort *)
0x1800292fe  mov     [rbp+0A0h+ExitCode], eax
0x180029301  test    eax, eax
0x180029303  jnz     loc_1800293E2
0x180029309  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x18002930d  call    ?AipVerifyConsent@@YAKPEAX@Z; AipVerifyConsent(void *)
0x180029312  mov     [rbp+0A0h+ExitCode], eax
0x180029315  test    eax, eax
0x180029317  jnz     loc_1800293E2
0x18002931d  mov     rcx, [rbp+0A0h+hThread+8]; hThread
0x180029321  call    cs:__imp_ResumeThread
0x180029327  mov     edx, [rbp+0A0h+dwMilliseconds]; dwMilliseconds
0x18002932d  mov     rcx, [rbp+0A0h+hThread]; hHandle
0x180029331  call    cs:__imp_WaitForSingleObject
0x180029337  mov     [rbp+0A0h+ExitCode], eax
0x18002933a  test    eax, eax
0x18002933c  jnz     loc_1800293E2
0x180029342  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x180029346  lea     rdx, [rbp+0A0h+ExitCode]; lpExitCode
0x18002934a  call    cs:__imp_GetExitCodeProcess
0x180029350  test    eax, eax
0x180029352  jnz     short loc_18002935F
0x180029354  call    cs:__imp_GetLastError
0x18002935a  jmp     loc_180029150
0x18002935f  mov     eax, [rbp+0A0h+ExitCode]
0x180029362  test    eax, eax
0x180029364  jz      short loc_18002937E
0x180029366  mov     rcx, [rbp+0A0h+Handle]; Handle
0x18002936a  test    rcx, rcx
0x18002936d  jz      short loc_1800293E2
0x18002936f  call    cs:__imp_NtClose
0x180029375  mov     [rbp+0A0h+Handle], r14
0x180029379  mov     eax, [rbp+0A0h+ExitCode]
0x18002937c  jmp     short loc_1800293E2
0x18002937e  bt      edi, 10h
0x180029382  jnb     short loc_1800293AA
0x180029384  mov     rax, [rbp+0A0h+Handle]
0x180029388  test    rax, rax
0x18002938b  jz      short loc_1800293AE
0x18002938d  mov     rcx, rax; TokenHandle
0x180029390  call    ?AipMarkAutoApprovedToken@@YAJPEAX@Z; AipMarkAutoApprovedToken(void *)
0x180029395  test    eax, eax
0x180029397  jns     short loc_1800293AA
0x180029399  mov     ecx, eax; Status
0x18002939b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800293a1  mov     rcx, [rbp+0A0h+Handle]
0x1800293a5  mov     [rbp+0A0h+ExitCode], eax
0x1800293a8  jmp     short loc_18002936F
0x1800293aa  mov     rax, [rbp+0A0h+Handle]
0x1800293ae  mov     [r12], rax
0x1800293b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800293b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1800293be  test    al, al
0x1800293c0  jz      short loc_180029379
0x1800293c2  call    LUAIsShadowAdminEnabled
0x1800293c7  test    eax, eax
0x1800293c9  jz      short loc_180029379
0x1800293cb  mov     rdx, [rbp+0A0h+Handle]; void *
0x1800293cf  test    rdx, rdx
0x1800293d2  jz      short loc_180029379
0x1800293d4  mov     rcx, r13; void *
0x1800293d7  call    ?AiSettingsSync@@YAJPEAX0@Z; AiSettingsSync(void *,void *)
0x1800293dc  jmp     short loc_180029379
0x1800293de  mov     rbx, [rbp+0A0h+var_108]
0x1800293e2  mov     rcx, [rbp+0A0h+hThread+8]; hObject
0x1800293e6  test    rcx, rcx
0x1800293e9  jz      short loc_1800293F4
0x1800293eb  call    cs:__imp_CloseHandle
0x1800293f1  mov     eax, [rbp+0A0h+ExitCode]
0x1800293f4  mov     rcx, [rbp+0A0h+hThread]; hProcess
0x1800293f8  mov     edi, 42Bh
0x1800293fd  test    rcx, rcx
0x180029400  jz      short loc_18002941F
0x180029402  test    eax, eax
0x180029404  jz      short loc_180029416
0x180029406  cmp     eax, edi
0x180029408  jz      short loc_180029416
0x18002940a  mov     edx, eax; uExitCode
0x18002940c  call    cs:__imp_TerminateProcess
0x180029412  mov     rcx, [rbp+0A0h+hThread]; hObject
0x180029416  call    cs:__imp_CloseHandle
0x18002941c  mov     eax, [rbp+0A0h+ExitCode]
0x18002941f  test    rbx, rbx
0x180029422  jz      short loc_180029430
0x180029424  mov     rcx, rbx; Handle
0x180029427  call    cs:__imp_NtClose
0x18002942d  mov     eax, [rbp+0A0h+ExitCode]
0x180029430  cmp     eax, 102h
0x180029435  jz      short loc_18002943B
0x180029437  cmp     eax, edi
0x180029439  jnz     short loc_180029440
0x18002943b  mov     eax, 4C7h
0x180029440  mov     rcx, [rbp+0A0h+var_40]
0x180029444  xor     rcx, rsp; StackCookie
0x180029447  call    __security_check_cookie
0x18002944c  mov     rbx, [rsp+1D0h+arg_18]
0x180029454  add     rsp, 1A0h
0x18002945b  pop     r15
0x18002945d  pop     r14
0x18002945f  pop     r13
0x180029461  pop     r12
0x180029463  pop     rdi
0x180029464  pop     rsi
0x180029465  pop     rbp
0x180029466  retn
```
