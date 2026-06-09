# RegisterForWnf(void)

- ea: `0x180018378`
- end: `0x180018704`
- name: `?RegisterForWnf@@YAJXZ`
- size: `908`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022b70`

## callees

- `0x180018378`
- `0x180021e88`
- `0x180023278`
- `0x180025004`
- `0x180028b7c`
- `0x180028ec4`
- `0x180029040`
- `0x18002c640`
- `0x180037348`
- `0x180038c60`
- `0x180039700`
- `0x18003b650`
- `0x18003bee8`
- `0x180055e5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184cc`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180018475`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001855f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180018475`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001855f`
- `ntdll!LdrAddRefDll` at `0x180018410`
- `ntdll!LdrAddRefDll` at `0x1800184fd`
- `ntdll!LdrAddRefDll` at `0x180018410`
- `ntdll!LdrAddRefDll` at `0x1800184fd`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x1800185e4`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x1800185e4`

## string_xrefs

- `0x1800183ec`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int RegisterForWnf(void)
{
  int v0; // ebx
  LSTATUS ValueW; // eax
  NTSTATUS v2; // eax
  char v4; // si
  NTSTATUS v5; // eax
  __int64 v6; // rdx
  LSTATUS v7; // eax
  int v8; // eax
  int v9; // eax
  NgcUtils *v10; // rcx
  int v11; // r14d
  const char *v12; // r9
  wil *v13; // rcx
  struct wil::WNF_CHANGE_STAMP_STRUCT *v14; // r9
  int v15; // eax
  __int64 v16; // rdx
  int v17; // esi
  _QWORD *v18; // rax
  const char *v19; // r9
  int pdwType; // [rsp+20h] [rbp-E8h]
  int pdwTypea; // [rsp+20h] [rbp-E8h]
  _WNF_STATE_NAME v22; // [rsp+40h] [rbp-C8h] BYREF
  char v23; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v24; // [rsp+49h] [rbp-BFh]
  DWORD pcbData; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int pvData; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v27; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v28; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v29[8]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v30[14]; // [rsp+68h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v0 = 0;
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Cryptography\\NGC",
             L"DeviceLockPolicyChangeStamp",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x43E,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)ValueW,
      pdwType);
  v2 = LdrAddRefDll(0, g_hInstance);
  if ( v2 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x443,
             (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
             (const char *)(unsigned int)v2,
             pdwType);
  v24 = 256;
  v4 = 1;
  pdwTypea = 0;
  v5 = RtlSubscribeWnfStateChangeNotification(
         &g_deviceLockPolicySubscription,
         WNF_ENTR_DEVICELOCK_POLICY_VALUE_CHANGED,
         pvData,
         DeviceLockPolicyChangeNotification);
  if ( v5 >= 0 )
  {
    v27 = 0;
    pcbData = 4;
    v7 = RegGetValueW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Cryptography\\NGC",
           L"ProCspPolicyChangeStamp",
           0x10u,
           0,
           &v27,
           &pcbData);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x45D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
        (const char *)(unsigned int)v7,
        pdwTypea);
    v5 = LdrAddRefDll(0, g_hInstance);
    if ( v5 >= 0 )
    {
      *(_WORD *)((char *)&v22.Data[1] + 1) = 256;
      v8 = RtlSubscribeWnfStateChangeNotification(
             &g_proCspPolicySubscription,
             WNF_NGC_PRO_CSP_POLICY_CHANGED,
             v27,
             ProCspPolicyChangeNotification);
      if ( v8 >= 0 )
      {
        LOBYTE(v22.Data[0]) = 0;
        v9 = IsDeviceLockPolicyApplicable((bool *)&v22);
        v11 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x473,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
            (const char *)(unsigned int)v9,
            0);
          wil::details::ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b___::operator()(&v22.Data[1]);
          v0 = v11;
          goto LABEL_27;
        }
        if ( LOBYTE(v22.Data[0]) )
        {
          if ( (unsigned int)RegisterWaitUntilOOBECompleted(OobeDoneCallback, 0, &g_oobeDoneSubscription)
            || GetLastError() == 5023 )
          {
            v4 = 0;
          }
          v10 = retaddr;
          if ( v4 )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x47B,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
              v12);
        }
        if ( NgcUtils::IsSecureBioEnabled(v10) )
        {
          LODWORD(v28) = 0;
          v15 = wil::wnf_query_nothrow(v13, &v22, (bool *)&v28, v14);
          v17 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x485,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
              (const char *)(unsigned int)v15,
              0);
            wil::details::ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b___::operator()(&v22.Data[1]);
            v0 = v17;
            goto LABEL_27;
          }
          try
          {
            v30[0] = off_1800817C8;
            v30[13] = v30;
            v18 = wil::make_wnf_subscription<wil::details::empty_wnf_state>(&v28, v16, (__int64)v29, v28);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
              &g_pregenTriggerSubscription,
              v18);
            wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v28);
            wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v29);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x491,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
              v19);
            v0 = 0;
          }
        }
        HIBYTE(v24) = 0;
        BYTE2(v22.Data[1]) = 0;
      }
      else
      {
        v0 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x46E,
               (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
               (const char *)(unsigned int)v8,
               0);
      }
      wil::details::ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b___::operator()(&v22.Data[1]);
      goto LABEL_27;
    }
    v6 = 1119;
  }
  else
  {
    v6 = 1106;
  }
  v0 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)v6,
         (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
         (const char *)(unsigned int)v5,
         pdwTypea);
LABEL_27:
  wil::details::ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b___::operator()(&v23);
  return v0;
}

```

## disassembly

```asm
0x180018378  push    rbx
0x18001837a  push    rsi
0x18001837b  push    rdi
0x18001837c  push    r14
0x18001837e  sub     rsp, 0E8h
0x180018385  mov     rax, cs:__security_cookie
0x18001838c  xor     rax, rsp
0x18001838f  mov     [rsp+108h+var_30], rax
0x180018397  xor     ebx, ebx
0x180018399  mov     [rsp+108h+var_B8], ebx
0x18001839d  lea     r14d, [rbx+4]
0x1800183a1  mov     [rsp+108h+var_BC], r14d
0x1800183a6  lea     rax, [rsp+108h+var_BC]
0x1800183ab  mov     [rsp+108h+pcbData], rax; pcbData
0x1800183b0  lea     rax, [rsp+108h+var_B8]
0x1800183b5  mov     [rsp+108h+pvData], rax; pvData
0x1800183ba  mov     [rsp+108h+pdwType], rbx; int
0x1800183bf  lea     r9d, [rbx+10h]; dwFlags
0x1800183c3  lea     r8, aDevicelockpoli; "DeviceLockPolicyChangeStamp"
0x1800183ca  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Cryptography\\NGC"
0x1800183d1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800183d8  call    cs:__imp_RegGetValueW
0x1800183df  nop     dword ptr [rax+rax+00h]
0x1800183e4  mov     rcx, [rsp+108h]; this
0x1800183ec  lea     rdi, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800183f3  test    eax, eax
0x1800183f5  jns     short loc_180018407
0x1800183f7  mov     r9d, eax; char *
0x1800183fa  mov     r8, rdi; unsigned int
0x1800183fd  mov     edx, 43Eh; void *
0x180018402  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180018407  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; BaseAddress
0x18001840e  xor     ecx, ecx; Flags
0x180018410  call    cs:__imp_LdrAddRefDll
0x180018417  nop     dword ptr [rax+rax+00h]
0x18001841c  test    eax, eax
0x18001841e  jns     short loc_18001843D
0x180018420  mov     rcx, [rsp+108h]; this
0x180018428  mov     r9d, eax; char *
0x18001842b  mov     r8, rdi; unsigned int
0x18001842e  mov     edx, 443h; void *
0x180018433  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180018438  jmp     loc_1800186E6
0x18001843d  mov     [rsp+108h+var_BF], 100h
0x180018444  mov     esi, 1
0x180018449  mov     [rsp+108h+var_D0], esi
0x18001844d  mov     dword ptr [rsp+108h+pcbData], ebx
0x180018451  mov     [rsp+108h+pvData], rbx
0x180018456  mov     [rsp+108h+pdwType], rbx
0x18001845b  lea     r9, ?DeviceLockPolicyChangeNotification@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; DeviceLockPolicyChangeNotification(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180018462  mov     r8d, [rsp+108h+var_B8]
0x180018467  mov     rdx, cs:WNF_ENTR_DEVICELOCK_POLICY_VALUE_CHANGED
0x18001846e  lea     rcx, ?g_deviceLockPolicySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_deviceLockPolicySubscription
0x180018475  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001847c  nop     dword ptr [rax+rax+00h]
0x180018481  test    eax, eax
0x180018483  jns     short loc_18001848F
0x180018485  mov     edx, 452h
0x18001848a  jmp     loc_180018512
0x18001848f  mov     [rsp+108h+var_B4], ebx
0x180018493  mov     [rsp+108h+var_BC], r14d
0x180018498  lea     rax, [rsp+108h+var_BC]
0x18001849d  mov     [rsp+108h+pcbData], rax; pcbData
0x1800184a2  lea     rax, [rsp+108h+var_B4]
0x1800184a7  mov     [rsp+108h+pvData], rax; pvData
0x1800184ac  mov     [rsp+108h+pdwType], rbx; int
0x1800184b1  mov     r9d, 10h; dwFlags
0x1800184b7  lea     r8, aProcsppolicych; "ProCspPolicyChangeStamp"
0x1800184be  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Cryptography\\NGC"
0x1800184c5  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800184cc  call    cs:__imp_RegGetValueW
0x1800184d3  nop     dword ptr [rax+rax+00h]
0x1800184d8  mov     rcx, [rsp+108h]; this
0x1800184e0  test    eax, eax
0x1800184e2  jns     short loc_1800184F4
0x1800184e4  mov     r9d, eax; char *
0x1800184e7  mov     r8, rdi; unsigned int
0x1800184ea  mov     edx, 45Dh; void *
0x1800184ef  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800184f4  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; BaseAddress
0x1800184fb  xor     ecx, ecx; Flags
0x1800184fd  call    cs:__imp_LdrAddRefDll
0x180018504  nop     dword ptr [rax+rax+00h]
0x180018509  test    eax, eax
0x18001850b  jns     short loc_18001852C
0x18001850d  mov     edx, 45Fh; void *
0x180018512  mov     r8, rdi; unsigned int
0x180018515  mov     r9d, eax; char *
0x180018518  mov     rcx, [rsp+108h]; this
0x180018520  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180018525  mov     ebx, eax
0x180018527  jmp     loc_1800186DA
0x18001852c  mov     word ptr [rsp+108h+var_C8.Data+5], 100h
0x180018533  mov     [rsp+108h+var_D0], esi
0x180018537  mov     dword ptr [rsp+108h+pcbData], ebx
0x18001853b  mov     [rsp+108h+pvData], rbx
0x180018540  mov     [rsp+108h+pdwType], rbx; int
0x180018545  lea     r9, ?ProCspPolicyChangeNotification@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ProCspPolicyChangeNotification(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001854c  mov     r8d, [rsp+108h+var_B4]
0x180018551  mov     rdx, cs:WNF_NGC_PRO_CSP_POLICY_CHANGED
0x180018558  lea     rcx, ?g_proCspPolicySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_proCspPolicySubscription
0x18001855f  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180018566  nop     dword ptr [rax+rax+00h]
0x18001856b  test    eax, eax
0x18001856d  jns     short loc_18001858E
0x18001856f  mov     rcx, [rsp+108h]; this
0x180018577  mov     r9d, eax; char *
0x18001857a  mov     r8, rdi; unsigned int
0x18001857d  mov     edx, 46Eh; void *
0x180018582  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180018587  mov     ebx, eax
0x180018589  jmp     loc_1800186CF
0x18001858e  mov     byte ptr [rsp+108h+var_C8.Data], bl
0x180018592  lea     rcx, [rsp+108h+var_C8]; bool *
0x180018597  call    ?IsDeviceLockPolicyApplicable@@YAJPEA_N@Z; IsDeviceLockPolicyApplicable(bool *)
0x18001859c  mov     r14d, eax
0x18001859f  test    eax, eax
0x1800185a1  jns     short loc_1800185CE
0x1800185a3  mov     rcx, [rsp+108h]; this
0x1800185ab  mov     r9d, eax; char *
0x1800185ae  mov     r8, rdi; unsigned int
0x1800185b1  mov     edx, 473h; void *
0x1800185b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185bb  nop
0x1800185bc  lea     rcx, [rsp+108h+var_C8.Data+4]
0x1800185c1  call    wil__details__ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b_____operator__
0x1800185c6  mov     ebx, r14d
0x1800185c9  jmp     loc_1800186DA
0x1800185ce  cmp     byte ptr [rsp+108h+var_C8.Data], bl
0x1800185d2  jz      short loc_180018624
0x1800185d4  lea     r8, ?g_oobeDoneSubscription@@3PEAXEA; void * g_oobeDoneSubscription
0x1800185db  xor     edx, edx
0x1800185dd  lea     rcx, ?OobeDoneCallback@@YAXPEAX@Z; OobeDoneCallback(void *)
0x1800185e4  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x1800185eb  nop     dword ptr [rax+rax+00h]
0x1800185f0  test    eax, eax
0x1800185f2  jnz     short loc_180018607
0x1800185f4  call    cs:__imp_GetLastError
0x1800185fb  nop     dword ptr [rax+rax+00h]
0x180018600  cmp     eax, 139Fh
0x180018605  jnz     short loc_18001860A
0x180018607  mov     sil, bl
0x18001860a  mov     rcx, [rsp+108h]; this
0x180018612  test    sil, sil
0x180018615  jz      short loc_180018624
0x180018617  mov     r8, rdi; unsigned int
0x18001861a  mov     edx, 47Bh; void *
0x18001861f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180018624  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x180018629  test    al, al
0x18001862b  jz      loc_1800186C7
0x180018631  mov     dword ptr [rsp+108h+var_B0], ebx
0x180018635  lea     r8, [rsp+108h+var_B0]; bool *
0x18001863a  lea     rdx, [rsp+108h+var_C8]; struct _WNF_STATE_NAME *
0x18001863f  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180018644  mov     esi, eax
0x180018646  test    eax, eax
0x180018648  jns     short loc_180018671
0x18001864a  mov     rcx, [rsp+108h]; this
0x180018652  mov     r9d, eax; char *
0x180018655  mov     r8, rdi; unsigned int
0x180018658  mov     edx, 485h; void *
0x18001865d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018662  nop
0x180018663  lea     rcx, [rsp+108h+var_C8.Data+4]
0x180018668  call    wil__details__ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b_____operator__
0x18001866d  mov     ebx, esi
0x18001866f  jmp     short loc_1800186DA
0x180018671  lea     rax, off_1800817C8
0x180018678  mov     [rsp+108h+var_A0], rax
0x18001867d  lea     rax, [rsp+108h+var_A0]
0x180018682  mov     [rsp+108h+var_38], rax
0x18001868a  mov     r9d, dword ptr [rsp+108h+var_B0]
0x18001868f  lea     r8, [rsp+108h+var_A8]
0x180018694  lea     rcx, [rsp+108h+var_B0]
0x180018699  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18001869e  mov     rdx, rax
0x1800186a1  lea     rcx, ?g_pregenTriggerSubscription@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> g_pregenTriggerSubscription
0x1800186a8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x1800186ad  lea     rcx, [rsp+108h+var_B0]
0x1800186b2  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800186b7  nop
0x1800186b8  lea     rcx, [rsp+108h+var_A8]
0x1800186bd  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x1800186c2  nop
0x1800186c3  jmp     short loc_1800186C7
0x1800186c5  xor     ebx, ebx
0x1800186c7  mov     byte ptr [rsp+108h+var_BF+1], bl
0x1800186cb  mov     byte ptr [rsp+108h+var_C8.Data+6], bl
0x1800186cf  lea     rcx, [rsp+108h+var_C8.Data+4]
0x1800186d4  call    wil__details__ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b_____operator__
0x1800186d9  nop
0x1800186da  lea     rcx, [rsp+108h+var_C0]
0x1800186df  call    wil__details__ScopeExitFnGuard__lambda_c513ea588e859669ac6c5e41a958ac8b_____operator__
0x1800186e4  mov     eax, ebx
0x1800186e6  mov     rcx, [rsp+108h+var_30]
0x1800186ee  xor     rcx, rsp; StackCookie
0x1800186f1  call    __security_check_cookie
0x1800186f6  add     rsp, 0E8h
0x1800186fd  pop     r14
0x1800186ff  pop     rdi
0x180018700  pop     rsi
0x180018701  pop     rbx
0x180018702  retn
```
