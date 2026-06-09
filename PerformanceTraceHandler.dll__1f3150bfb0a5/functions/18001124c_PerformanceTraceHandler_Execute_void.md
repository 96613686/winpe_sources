# PerformanceTraceHandler::Execute(void)

- ea: `0x18001124c`
- end: `0x180011616`
- name: `?Execute@PerformanceTraceHandler@@AEAAJXZ`
- size: `970`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012890`

## callees

- `0x180007f3c`
- `0x18000b544`
- `0x180010a90`
- `0x180010b08`
- `0x180010ca4`
- `0x180010fc4`
- `0x18001117c`
- `0x18001124c`
- `0x1800118d4`
- `0x180011a84`
- `0x180011e50`
- `0x180012018`
- `0x180012334`
- `0x180012c10`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001138d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180011513`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001138d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180011513`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001131c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001131c`

## string_xrefs

- `0x1800112bc`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x1800112fc`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::Execute(const unsigned __int16 **this)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int v5; // eax
  PerformanceTraceHandler *v6; // rcx
  HRESULT v7; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  int TraceFolderPath; // eax
  PerformanceTraceHandler *v12; // rcx
  __int64 v13; // rdx
  HRESULT v14; // eax
  PerformanceTraceHandler *v15; // rcx
  int FileToken; // eax
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+20h] [rbp-58h]
  _BYTE v21[8]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v22; // [rsp+58h] [rbp-20h] BYREF
  int v23; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  PWSTR ppszPathOut; // [rsp+B0h] [rbp+38h] BYREF
  PCWSTR pszPathIn; // [rsp+B8h] [rbp+40h] BYREF
  PWSTR v27; // [rsp+C0h] [rbp+48h] BYREF
  HSTRING v28; // [rsp+C8h] [rbp+50h] BYREF

  v22 = 0;
  v23 = 0;
  v19 = 0;
  v2 = Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(
         this + 7,
         L"UifId\\uifTraceProfile\\1\\ReproduceScenario\\Start",
         &dword_18001E1D4);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                            this + 24,
                            v21)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
    v5 = PerformanceTraceHandler::LaunchToastNotificationBeginning((PerformanceTraceHandler *)this);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
        (const char *)(unsigned int)v5,
        0);
    Sleep(0x2710u);
    v2 = PerformanceTraceHandler::EnsureFolderExists(v6, this[21]);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = 267;
      goto LABEL_7;
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                            this + 24,
                            v21)
             + 275LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
    ppszPathOut = 0;
    v7 = PathAllocCombine(this[21], L"DiagOutputDir", 1u, &ppszPathOut);
    v3 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
        (const char *)(unsigned int)v7,
        v19);
      v8 = v3;
      v9 = 270;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
        (const char *)v8,
        v20);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      goto LABEL_31;
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                            this + 24,
                            v21)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
    v20 = 1;
    v10 = Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(
            this + 7,
            L"UifId\\uifTraceProfile\\1\\ReproduceScenario\\Stop",
            ppszPathOut);
    v3 = v10;
    if ( v10 < 0 )
    {
      v8 = (unsigned int)v10;
      v9 = 271;
      goto LABEL_10;
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                            this + 24,
                            v21)
             + 277LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
    pszPathIn = 0;
    TraceFolderPath = PerformanceTraceHandler::GetTraceFolderPath(
                        (PerformanceTraceHandler *)this,
                        (unsigned __int16 **)&pszPathIn);
    v3 = TraceFolderPath;
    if ( TraceFolderPath >= 0 )
    {
      TraceFolderPath = PerformanceTraceHandler::EnsureFolderExists(v12, pszPathIn);
      v3 = TraceFolderPath;
      if ( TraceFolderPath >= 0 )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                                this + 24,
                                v21)
                 + 279LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
        TraceFolderPath = PerformanceTraceHandler::MoveTracesToFinalFolder(
                            (PerformanceTraceHandler *)this,
                            ppszPathOut,
                            pszPathIn);
        v3 = TraceFolderPath;
        if ( TraceFolderPath >= 0 )
        {
          v27 = 0;
          v14 = PathAllocCombine(pszPathIn, L"diagnostics.zip", 1u, &v27);
          v3 = v14;
          if ( v14 >= 0 )
          {
            *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                                    this + 24,
                                    v21)
                     + 281LL) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
            v28 = 0;
            FileToken = PerformanceTraceHandler::GetFileToken(v15, v27, &v28);
            v3 = FileToken;
            if ( FileToken >= 0 )
            {
              *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                                      this + 24,
                                      v21)
                       + 282LL) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v21);
              FileToken = PerformanceTraceHandler::LaunchToastNotification((PerformanceTraceHandler *)this, v28);
              v3 = FileToken;
              if ( FileToken >= 0 )
              {
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
                v3 = 0;
                goto LABEL_31;
              }
              v17 = 289;
            }
            else
            {
              v17 = 287;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
              (const char *)(unsigned int)FileToken,
              1);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v28);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11C,
              (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
              (const char *)(unsigned int)v14,
              1);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          goto LABEL_17;
        }
        v13 = 280;
      }
      else
      {
        v13 = 278;
      }
    }
    else
    {
      v13 = 277;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)TraceFolderPath,
      1);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    goto LABEL_11;
  }
  v4 = 257;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
    (const char *)(unsigned int)v2,
    v19);
LABEL_31:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
  return v3;
}

```

## disassembly

```asm
0x18001124c  push    rbp
0x18001124e  push    rbx
0x18001124f  push    rsi
0x180011250  push    rdi
0x180011251  push    r14
0x180011253  push    r15
0x180011255  mov     rbp, rsp
0x180011258  sub     rsp, 78h
0x18001125c  mov     rsi, rcx
0x18001125f  mov     [rbp+var_20], 0
0x180011267  mov     [rbp+var_18], 0
0x18001126e  lea     rax, [rbp+var_20]
0x180011272  mov     [rsp+78h+var_30], rax
0x180011277  lea     rax, ?k_startPerfReproPropertyIdentifierValues@@3PAPEBGA; ushort const * near * k_startPerfReproPropertyIdentifierValues
0x18001127e  mov     [rsp+78h+var_38], rax
0x180011283  lea     rax, ?k_startPerfReproPropertyIdentifierKeys@@3PAPEBGA; ushort const * near * k_startPerfReproPropertyIdentifierKeys
0x18001128a  mov     [rsp+78h+var_40], rax
0x18001128f  mov     [rsp+78h+var_48], 3
0x180011297  mov     [rsp+78h+var_58], 0; int
0x18001129f  lea     r8, dword_18001E1D4
0x1800112a6  lea     rdx, aUifidUiftracep_0; "UifId\\uifTraceProfile\\1\\ReproduceSce"...
0x1800112ad  add     rcx, 38h ; '8'
0x1800112b1  call    ?EscalateScenarioEx@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJPEBG0HHW4__MIDL_UtcApiStructures_0004@@KPEAPEBG2AEAVAutoEscalationResultsList@123@@Z; Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(ushort const *,ushort const *,int,int,__MIDL_UtcApiStructures_0004,ulong,ushort const * *,ushort const * *,Microsoft::Diagnostics::UtcApiWrapper::AutoEscalationResultsList &)
0x1800112b6  mov     ebx, eax
0x1800112b8  test    eax, eax
0x1800112ba  jns     short loc_1800112CA
0x1800112bc  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x1800112c3  mov     edx, 101h
0x1800112c8  jmp     short loc_18001133C
0x1800112ca  lea     r14, [rsi+0C0h]
0x1800112d1  lea     rdx, [rbp+var_28]
0x1800112d5  mov     rcx, r14
0x1800112d8  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x1800112dd  mov     rcx, [rax]
0x1800112e0  mov     byte ptr [rcx+112h], 1
0x1800112e7  lea     rcx, [rbp+var_28]
0x1800112eb  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x1800112f0  mov     rcx, rsi; this
0x1800112f3  call    ?LaunchToastNotificationBeginning@PerformanceTraceHandler@@AEAAJXZ; PerformanceTraceHandler::LaunchToastNotificationBeginning(void)
0x1800112f8  mov     rcx, [rbp+30h]; this
0x1800112fc  lea     rdi, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x180011303  test    eax, eax
0x180011305  jns     short loc_180011317
0x180011307  mov     r9d, eax; char *
0x18001130a  mov     r8, rdi; unsigned int
0x18001130d  mov     edx, 105h; void *
0x180011312  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011317  mov     ecx, 2710h; dwMilliseconds
0x18001131c  call    cs:__imp_Sleep
0x180011322  mov     rdx, [rsi+0A8h]; unsigned __int16 *
0x180011329  call    ?EnsureFolderExists@PerformanceTraceHandler@@AEAAJPEBG@Z; PerformanceTraceHandler::EnsureFolderExists(ushort const *)
0x18001132e  mov     ebx, eax
0x180011330  test    eax, eax
0x180011332  jns     short loc_18001134D
0x180011334  mov     r8, rdi; unsigned int
0x180011337  mov     edx, 10Bh; void *
0x18001133c  mov     r9d, eax; char *
0x18001133f  mov     rcx, [rbp+30h]; this
0x180011343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011348  jmp     loc_1800115FE
0x18001134d  lea     rdx, [rbp+var_28]
0x180011351  mov     rcx, r14
0x180011354  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180011359  mov     rcx, [rax]
0x18001135c  mov     byte ptr [rcx+113h], 1
0x180011363  lea     rcx, [rbp+var_28]
0x180011367  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x18001136c  nop
0x18001136d  mov     [rbp+ppszPathOut], 0
0x180011375  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180011379  mov     r8d, 1; dwFlags
0x18001137f  lea     rdx, pszMore; "DiagOutputDir"
0x180011386  mov     rcx, [rsi+0A8h]; pszPathIn
0x18001138d  call    cs:__imp_PathAllocCombine
0x180011393  mov     ebx, eax
0x180011395  test    eax, eax
0x180011397  jns     short loc_1800113D0
0x180011399  mov     rcx, [rbp+30h]; this
0x18001139d  mov     r9d, eax; char *
0x1800113a0  mov     r8, rdi; unsigned int
0x1800113a3  mov     edx, 9Dh; void *
0x1800113a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113ad  mov     r9d, ebx; char *
0x1800113b0  mov     edx, 10Eh; void *
0x1800113b5  mov     r8, rdi; unsigned int
0x1800113b8  mov     rcx, [rbp+30h]; this
0x1800113bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113c1  nop
0x1800113c2  lea     rcx, [rbp+ppszPathOut]
0x1800113c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800113cb  jmp     loc_1800115FE
0x1800113d0  lea     rdx, [rbp+var_28]
0x1800113d4  mov     rcx, r14
0x1800113d7  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x1800113dc  mov     rdx, [rax]
0x1800113df  mov     byte ptr [rdx+114h], 1
0x1800113e6  lea     rcx, [rbp+var_28]
0x1800113ea  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x1800113ef  lea     rax, [rbp+var_20]
0x1800113f3  mov     [rsp+78h+var_30], rax
0x1800113f8  lea     rax, ?k_stopPerfReproPropertyIdentifierValues@@3PAPEBGA; ushort const * near * k_stopPerfReproPropertyIdentifierValues
0x1800113ff  mov     [rsp+78h+var_38], rax
0x180011404  lea     rax, ?k_stopPerfReproPropertyIdentifierKeys@@3PAPEBGA; ushort const * near * k_stopPerfReproPropertyIdentifierKeys
0x18001140b  mov     [rsp+78h+var_40], rax
0x180011410  mov     [rsp+78h+var_48], 4
0x180011418  mov     [rsp+78h+var_58], 1; int
0x180011420  mov     r8, [rbp+ppszPathOut]
0x180011424  lea     rdx, aUifidUiftracep; "UifId\\uifTraceProfile\\1\\ReproduceSce"...
0x18001142b  lea     rcx, [rsi+38h]
0x18001142f  call    ?EscalateScenarioEx@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJPEBG0HHW4__MIDL_UtcApiStructures_0004@@KPEAPEBG2AEAVAutoEscalationResultsList@123@@Z; Microsoft::Diagnostics::UtcApiWrapper::EscalateScenarioEx(ushort const *,ushort const *,int,int,__MIDL_UtcApiStructures_0004,ulong,ushort const * *,ushort const * *,Microsoft::Diagnostics::UtcApiWrapper::AutoEscalationResultsList &)
0x180011434  mov     ebx, eax
0x180011436  test    eax, eax
0x180011438  jns     short loc_180011447
0x18001143a  mov     r9d, eax
0x18001143d  mov     edx, 10Fh
0x180011442  jmp     loc_1800113B5
0x180011447  lea     rdx, [rbp+var_28]
0x18001144b  mov     rcx, r14
0x18001144e  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180011453  mov     rcx, [rax]
0x180011456  mov     byte ptr [rcx+115h], 1
0x18001145d  lea     rcx, [rbp+var_28]
0x180011461  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180011466  nop
0x180011467  mov     [rbp+pszPathIn], 0
0x18001146f  lea     rdx, [rbp+pszPathIn]; unsigned __int16 **
0x180011473  mov     rcx, rsi; this
0x180011476  call    ?GetTraceFolderPath@PerformanceTraceHandler@@AEAAJPEAPEAG@Z; PerformanceTraceHandler::GetTraceFolderPath(ushort * *)
0x18001147b  mov     ebx, eax
0x18001147d  test    eax, eax
0x18001147f  jns     short loc_1800114A4
0x180011481  mov     edx, 115h; void *
0x180011486  mov     rcx, [rbp+30h]; this
0x18001148a  mov     r9d, eax; char *
0x18001148d  mov     r8, rdi; unsigned int
0x180011490  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011495  nop
0x180011496  lea     rcx, [rbp+pszPathIn]
0x18001149a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001149f  jmp     loc_1800113C2
0x1800114a4  mov     rdx, [rbp+pszPathIn]; unsigned __int16 *
0x1800114a8  call    ?EnsureFolderExists@PerformanceTraceHandler@@AEAAJPEBG@Z; PerformanceTraceHandler::EnsureFolderExists(ushort const *)
0x1800114ad  mov     ebx, eax
0x1800114af  test    eax, eax
0x1800114b1  jns     short loc_1800114BA
0x1800114b3  mov     edx, 116h
0x1800114b8  jmp     short loc_180011486
0x1800114ba  lea     rdx, [rbp+var_28]
0x1800114be  mov     rcx, r14
0x1800114c1  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x1800114c6  mov     rcx, [rax]
0x1800114c9  mov     byte ptr [rcx+117h], 1
0x1800114d0  lea     rcx, [rbp+var_28]
0x1800114d4  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x1800114d9  mov     r8, [rbp+pszPathIn]; unsigned __int16 *
0x1800114dd  mov     rdx, [rbp+ppszPathOut]; unsigned __int16 *
0x1800114e1  mov     rcx, rsi; this
0x1800114e4  call    ?MoveTracesToFinalFolder@PerformanceTraceHandler@@AEAAJPEBG0@Z; PerformanceTraceHandler::MoveTracesToFinalFolder(ushort const *,ushort const *)
0x1800114e9  mov     ebx, eax
0x1800114eb  test    eax, eax
0x1800114ed  jns     short loc_1800114F6
0x1800114ef  mov     edx, 118h
0x1800114f4  jmp     short loc_180011486
0x1800114f6  mov     [rbp+arg_10], 0
0x1800114fe  lea     r9, [rbp+arg_10]; ppszPathOut
0x180011502  mov     r8d, 1; dwFlags
0x180011508  lea     rdx, aDiagnosticsZip; "diagnostics.zip"
0x18001150f  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x180011513  call    cs:__imp_PathAllocCombine
0x180011519  mov     ebx, eax
0x18001151b  test    eax, eax
0x18001151d  jns     short loc_180011542
0x18001151f  mov     rcx, [rbp+30h]; this
0x180011523  mov     r9d, eax; char *
0x180011526  mov     r8, rdi; unsigned int
0x180011529  mov     edx, 11Ch; void *
0x18001152e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011533  nop
0x180011534  lea     rcx, [rbp+arg_10]
0x180011538  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001153d  jmp     loc_180011496
0x180011542  lea     rdx, [rbp+var_28]
0x180011546  mov     rcx, r14
0x180011549  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x18001154e  mov     rcx, [rax]
0x180011551  mov     byte ptr [rcx+119h], 1
0x180011558  lea     rcx, [rbp+var_28]
0x18001155c  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180011561  nop
0x180011562  mov     [rbp+arg_18], 0
0x18001156a  lea     r8, [rbp+arg_18]; HSTRING *
0x18001156e  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x180011572  call    ?GetFileToken@PerformanceTraceHandler@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; PerformanceTraceHandler::GetFileToken(ushort const *,HSTRING__ * *)
0x180011577  mov     ebx, eax
0x180011579  test    eax, eax
0x18001157b  jns     short loc_18001159D
0x18001157d  mov     edx, 11Fh; void *
0x180011582  mov     r8, rdi; unsigned int
0x180011585  mov     r9d, eax; char *
0x180011588  mov     rcx, [rbp+30h]; this
0x18001158c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011591  nop
0x180011592  lea     rcx, [rbp+arg_18]
0x180011596  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18001159b  jmp     short loc_180011534
0x18001159d  lea     rdx, [rbp+var_28]
0x1800115a1  mov     rcx, r14
0x1800115a4  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x1800115a9  mov     rcx, [rax]
0x1800115ac  mov     byte ptr [rcx+11Ah], 1
0x1800115b3  lea     rcx, [rbp+var_28]
0x1800115b7  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x1800115bc  mov     rdx, [rbp+arg_18]; HSTRING
0x1800115c0  mov     rcx, rsi; this
0x1800115c3  call    ?LaunchToastNotification@PerformanceTraceHandler@@AEAAJPEAUHSTRING__@@@Z; PerformanceTraceHandler::LaunchToastNotification(HSTRING__ *)
0x1800115c8  mov     ebx, eax
0x1800115ca  test    eax, eax
0x1800115cc  jns     short loc_1800115D5
0x1800115ce  mov     edx, 121h
0x1800115d3  jmp     short loc_180011582
0x1800115d5  lea     rcx, [rbp+arg_18]
0x1800115d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800115de  nop
0x1800115df  lea     rcx, [rbp+arg_10]
0x1800115e3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800115e8  nop
0x1800115e9  lea     rcx, [rbp+pszPathIn]
0x1800115ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800115f2  nop
0x1800115f3  lea     rcx, [rbp+ppszPathOut]
0x1800115f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800115fc  xor     ebx, ebx
0x1800115fe  lea     rcx, [rbp+var_20]
0x180011602  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011607  mov     eax, ebx
0x180011609  add     rsp, 78h
0x18001160d  pop     r15
0x18001160f  pop     r14
0x180011611  pop     rdi
0x180011612  pop     rsi
0x180011613  pop     rbx
0x180011614  pop     rbp
0x180011615  retn
```
