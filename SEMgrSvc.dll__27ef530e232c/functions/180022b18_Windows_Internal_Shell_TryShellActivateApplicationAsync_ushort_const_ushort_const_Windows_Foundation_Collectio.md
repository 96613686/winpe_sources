# `Windows::Internal::Shell::TryShellActivateApplicationAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)'::`2'::_lambda_1_::operator()(Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::PlatformExtensions::IShellActivationResult> &)

- ea: `0x180022b18`
- end: `0x18002307b`
- name: `??R_lambda_1_@?1??TryShellActivateApplicationAsync@Shell@Internal@Windows@@YAJPEBG0PEAUIPropertySet@Collections@Foundation@4@0UWindowId@WindowManagement@ApplicationModel@34@_KPEAPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@74@$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@@Z@QEAA@AEAV?$CMarshaledInterfaceResult@UIShellActivationResult@PlatformExtensions@Internal@Windows@@@34@@Z`
- size: `1379`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a3f0`

## callees

- `0x1800049a0`
- `0x180004e9c`
- `0x1800057c6`
- `0x180005840`
- `0x180005858`
- `0x18000c964`
- `0x1800144a0`
- `0x18001e61c`
- `0x18001eb04`
- `0x18001f288`
- `0x1800205d0`
- `0x1800218d4`
- `0x180022b18`
- `0x180024340`
- `0x1800258bc`
- `0x180029b90`
- `0x18002b064`
- `0x18002c538`
- `0x18002cac4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022bd9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022bd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022fcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023035`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022fcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023035`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022fdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023043`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022fdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023043`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022ba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022c5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022c5d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180022f7c`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180022f7c`

## string_xrefs

- `0x180022ca5`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall `Windows::Internal::Shell::TryShellActivateApplicationAsync'::`2'::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2)
{
  Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication *v4; // r15
  __int64 v5; // rcx
  _WORD *v6; // rsi
  __int64 v7; // rax
  SIZE_T v8; // r14
  HANDLE ProcessHeap; // rax
  void *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // r14d
  HRESULT v15; // eax
  int v16; // edx
  __int64 v17; // r8
  int v18; // eax
  int v19; // esi
  __int64 v20; // rcx
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rax
  Windows::Internal::Shell::Details::AppActivationResult *v28; // rax
  __int64 v29; // rdi
  signed __int64 v30; // rdx
  signed __int64 v31; // rcx
  bool v32; // zf
  signed __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rcx
  signed __int32 v36; // eax
  __int64 *v37; // rsi
  __int64 v38; // rcx
  __int64 v39; // rcx
  bool v40; // dl
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rcx
  void *v44; // rbx
  HANDLE v45; // rax
  __int64 v47; // rcx
  void *v48; // rbx
  HANDLE v49; // rax
  int v50; // [rsp+20h] [rbp-A9h]
  int *v51; // [rsp+20h] [rbp-A9h]
  __int64 v52; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v53; // [rsp+58h] [rbp-71h] BYREF
  int v54; // [rsp+5Ch] [rbp-6Dh] BYREF
  int v55; // [rsp+60h] [rbp-69h] BYREF
  __int16 v56; // [rsp+64h] [rbp-65h]
  unsigned int *v57; // [rsp+68h] [rbp-61h]
  __int128 v58; // [rsp+70h] [rbp-59h] BYREF
  LPVOID lpMem[2]; // [rsp+80h] [rbp-49h]
  __int128 v60; // [rsp+90h] [rbp-39h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-29h]
  int v62; // [rsp+A8h] [rbp-21h]
  __int128 *v63; // [rsp+B0h] [rbp-19h]
  char v64; // [rsp+B8h] [rbp-11h]
  __int64 v65; // [rsp+C0h] [rbp-9h] BYREF
  int v66[2]; // [rsp+C8h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp+7h] BYREF
  HSTRING string; // [rsp+E8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v4 = (Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication *)(a1 + 200);
  v5 = *(_QWORD *)(a1 + 472);
  if ( *(_DWORD *)v5 == 1 )
  {
    LOBYTE(lpMem[1]) = 0;
    LODWORD(v58) = *(_DWORD *)(v5 + 40);
    *((_QWORD *)&v58 + 1) = *(_QWORD *)(v5 + 48);
    v6 = *(_WORD **)(v5 + 56);
    if ( *(_BYTE *)(v5 + 64) )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v7 )
      {
        v8 = 2 * v7 + 2;
        ProcessHeap = GetProcessHeap();
        v10 = HeapAlloc(ProcessHeap, 0, v8);
        lpMem[0] = v10;
        if ( v10 )
        {
          LOBYTE(lpMem[1]) = 1;
          if ( v8 )
          {
            if ( v6 )
            {
              memcpy_0(v10, v6, v8);
            }
            else
            {
              memset_0(v10, 0, v8);
              *(_DWORD *)_o__errno(v12, v11, v13) = 22;
              invalid_parameter_noinfo();
            }
          }
        }
      }
    }
    else
    {
      lpMem[0] = *(LPVOID *)(v5 + 56);
    }
    *(_QWORD *)&v60 = 0;
    *((_QWORD *)&v60 + 1) = v4;
    v61 = 0;
    v62 = 0;
    v63 = &v58;
    v64 = 0;
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)&v60);
  }
  else
  {
    v58 = 0;
    *(_OWORD *)lpMem = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
  }
  v54 = 0;
  v53 = 0;
  v52 = 0;
  v14 = *(_DWORD *)(a1 + 184);
  string = 0;
  v15 = WindowsCreateStringReference(L"Windows.Internal.ActivationPolicy", 0x21u, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    JUMPOUT(0x18002307ALL);
  }
  v18 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(string, v14, v17, &v52);
  v19 = v18;
  if ( v18 >= 0 )
    v19 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v18,
      v50);
  Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::ExtensionActivationAttempted<Microsoft::WRL::ComPtr<Windows::Internal::PlatformExtensions::IShellActivationManager> &>(
    v4,
    &v52);
  v21 = *(_DWORD *)Feature_TryShellActivateApplicationFallback__descriptor;
  if ( (*(_DWORD *)Feature_TryShellActivateApplicationFallback__descriptor & 4) == 0 )
  {
    v57 = *(unsigned int **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TryShellActivateApplicationFallback>::GetCachedFeatureEnabledState(
                              v20,
                              &v65);
    v21 = (unsigned int)v57;
  }
  v55 = 0;
  v56 = 3;
  v51 = &v55;
  wil::details::ReportUsageToService(&qword_1801331F8, 23674478, (v21 >> 10) & 1, (v21 >> 11) & 1);
  if ( v19 >= 0 && v52 )
  {
    v22 = Windows::Internal::Shell::Details::TryActivateThroughShellPolicy(
            v52,
            *(_QWORD *)(a1 + 128),
            *(_QWORD *)(a1 + 144),
            *(_QWORD *)(a1 + 160),
            *(_QWORD *)(a1 + 168),
            *(_DWORD *)(a1 + 184),
            *(_QWORD *)(a1 + 192),
            a1,
            (__int64)&v54,
            (__int64)&v53);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
        (const char *)(unsigned int)v22,
        (int)v51);
      v24 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      if ( v62 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v60);
LABEL_59:
      if ( LOBYTE(lpMem[1]) )
      {
        v48 = lpMem[0];
        v49 = GetProcessHeap();
        HeapFree(v49, 0, v48);
      }
      return v23;
    }
  }
  else
  {
    v25 = *(_QWORD *)(a1 + 144);
    v26 = *(_QWORD *)(a1 + 112);
    v27 = *(_QWORD *)(a1 + 192);
    hstringHeader.Reserved.Reserved1 = *(PVOID *)(a1 + 128);
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v25;
    if ( v26 )
    {
      *(_QWORD *)v66 = v27;
      v65 = *(_QWORD *)(a1 + 160);
      v57 = &v53;
      v55 = *(_DWORD *)(a1 + 184);
      v51 = v66;
      v54 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *, int *))(*(_QWORD *)v26 + 32LL))(
              v26,
              &hstringHeader,
              &v65,
              &v55);
    }
    else
    {
      v34 = Windows::Internal::Shell::Details::FallbackActivateApplication(&hstringHeader, v27);
      v23 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
          (const char *)(unsigned int)v34,
          (int)&v55);
        v35 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        if ( v62 )
          wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v60);
        goto LABEL_59;
      }
    }
  }
  v28 = (Windows::Internal::Shell::Details::AppActivationResult *)operator new(
                                                                    0x48u,
                                                                    (const struct std::nothrow_t *)std::nothrow);
  if ( !v28 )
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
      (const char *)0x8007000ELL,
      (int)v51);
    v47 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    if ( v62 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v60);
    goto LABEL_59;
  }
  v29 = Windows::Internal::Shell::Details::AppActivationResult::AppActivationResult(v28);
  v30 = v53;
  *(_DWORD *)(v29 + 64) = v54;
  *(_DWORD *)(v29 + 68) = v30;
  v31 = *(_QWORD *)(v29 + 56);
  while ( v31 >= 0 )
  {
    if ( (_DWORD)v31 != 0x7FFFFFFF )
    {
      v30 = v31 + 1;
      v33 = _InterlockedCompareExchange64((volatile signed __int64 *)(v29 + 56), v31 + 1, v31);
      v32 = v31 == v33;
      v31 = v33;
      if ( !v32 )
        continue;
    }
    goto LABEL_44;
  }
  do
  {
    v36 = *(_DWORD *)(2 * v31 + 0x10);
    if ( v36 == 0x7FFFFFFF )
      break;
    v30 = (unsigned int)(v36 + 1);
  }
  while ( v36 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v31 + 16), v30, v36) );
LABEL_44:
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::PlatformExtensions::IShellActivationResult,Microsoft::WRL::FtmBase>::Release(
    v29,
    v30,
    0x7FFFFFFF);
  v37 = (__int64 *)(a2 + 16);
  v38 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  v39 = *v37;
  if ( *v37 )
  {
    *v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  RoGetAgileReference(0, &GUID_e889ba92_1857_489e_b60e_a60ccf66e5da, v29, a2 + 16);
  Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::Stop(
    v4,
    v40,
    v54,
    v53,
    (bool)v51);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::PlatformExtensions::IShellActivationResult,Microsoft::WRL::FtmBase>::Release(
    v29,
    v41,
    v42);
  v43 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  if ( v62 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v60);
  if ( LOBYTE(lpMem[1]) )
  {
    v44 = lpMem[0];
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v44);
  }
  return 0;
}

```

## disassembly

```asm
0x180022b18  mov     [rsp-8+arg_10], rbx
0x180022b1d  mov     [rsp-8+arg_18], rsi
0x180022b22  push    rbp
0x180022b23  push    rdi
0x180022b24  push    r13
0x180022b26  push    r14
0x180022b28  push    r15
0x180022b2a  lea     rbp, [rsp-37h]
0x180022b2f  sub     rsp, 100h
0x180022b36  mov     rax, cs:__security_cookie
0x180022b3d  xor     rax, rsp
0x180022b40  mov     [rbp+57h+var_30], rax
0x180022b44  mov     r13, rdx
0x180022b47  mov     rdi, rcx
0x180022b4a  lea     r15, [rcx+0C8h]
0x180022b51  mov     rcx, [r15+110h]
0x180022b58  xor     ebx, ebx
0x180022b5a  cmp     dword ptr [rcx], 1
0x180022b5d  jnz     loc_180022C16
0x180022b63  mov     byte ptr [rbp+57h+lpMem+8], bl
0x180022b66  mov     eax, [rcx+28h]
0x180022b69  mov     dword ptr [rbp+57h+var_B0], eax
0x180022b6c  mov     rax, [rcx+30h]
0x180022b70  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180022b74  mov     rsi, [rcx+38h]
0x180022b78  cmp     [rcx+40h], bl
0x180022b7b  jz      short loc_180022BEC
0x180022b7d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022b81  inc     rax
0x180022b84  cmp     [rsi+rax*2], bx
0x180022b88  jnz     short loc_180022B81
0x180022b8a  test    rax, rax
0x180022b8d  jz      short loc_180022BF0
0x180022b8f  lea     r14, ds:2[rax*2]
0x180022b97  call    cs:__imp_GetProcessHeap
0x180022b9d  mov     rcx, rax; hHeap
0x180022ba0  mov     r8, r14; dwBytes
0x180022ba3  xor     edx, edx; dwFlags
0x180022ba5  call    cs:__imp_HeapAlloc
0x180022bab  mov     [rbp+57h+lpMem], rax
0x180022baf  test    rax, rax
0x180022bb2  jz      short loc_180022BF0
0x180022bb4  mov     byte ptr [rbp+57h+lpMem+8], 1
0x180022bb8  test    r14, r14
0x180022bbb  jz      short loc_180022BF0
0x180022bbd  mov     r8, r14; Size
0x180022bc0  mov     rcx, rax; void *
0x180022bc3  test    rsi, rsi
0x180022bc6  jz      short loc_180022BD2
0x180022bc8  mov     rdx, rsi; Src
0x180022bcb  call    memcpy_0
0x180022bd0  jmp     short loc_180022BF0
0x180022bd2  xor     edx, edx; Val
0x180022bd4  call    memset_0
0x180022bd9  call    cs:__imp__o__errno
0x180022bdf  mov     dword ptr [rax], 16h
0x180022be5  call    _invalid_parameter_noinfo
0x180022bea  jmp     short loc_180022BF0
0x180022bec  mov     [rbp+57h+lpMem], rsi
0x180022bf0  mov     qword ptr [rbp+57h+var_90], rbx
0x180022bf4  mov     qword ptr [rbp+57h+var_90+8], r15
0x180022bf8  mov     [rbp+57h+var_80], rbx
0x180022bfc  mov     [rbp+57h+var_78], ebx
0x180022bff  lea     rax, [rbp+57h+var_B0]
0x180022c03  mov     [rbp+57h+var_70], rax
0x180022c07  mov     [rbp+57h+var_68], bl
0x180022c0a  lea     rcx, [rbp+57h+var_90]; this
0x180022c0e  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180022c13  nop
0x180022c14  jmp     short loc_180022C34
0x180022c16  xorps   xmm0, xmm0
0x180022c19  movups  [rbp+57h+var_B0], xmm0
0x180022c1d  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x180022c21  movdqa  [rbp+57h+var_90], xmm0
0x180022c26  mov     [rbp+57h+var_80], rbx
0x180022c2a  mov     [rbp+57h+var_78], ebx
0x180022c2d  mov     [rbp+57h+var_70], rbx
0x180022c31  mov     [rbp+57h+var_68], bl
0x180022c34  mov     [rbp+57h+var_C4], ebx
0x180022c37  mov     [rbp+57h+var_C8], ebx
0x180022c3a  mov     [rbp+57h+var_D0], rbx
0x180022c3e  mov     r14d, [rdi+0B8h]
0x180022c45  mov     [rbp+57h+string], rbx
0x180022c49  lea     r9, [rbp+57h+string]; string
0x180022c4d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180022c51  mov     edx, 21h ; '!'; length
0x180022c56  lea     rcx, sourceString; "Windows.Internal.ActivationPolicy"
0x180022c5d  call    cs:__imp_WindowsCreateStringReference
0x180022c63  test    eax, eax
0x180022c65  js      loc_180023073
0x180022c6b  mov     rsi, [rbp+57h+string]
0x180022c6f  mov     rcx, [rbp+57h+var_D0]
0x180022c73  test    rcx, rcx
0x180022c76  jz      short loc_180022C89
0x180022c78  mov     [rbp+57h+var_D0], rbx
0x180022c7c  mov     rax, [rcx]
0x180022c7f  mov     rax, [rax+10h]
0x180022c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c88  nop
0x180022c89  lea     r9, [rbp+57h+var_D0]
0x180022c8d  mov     edx, r14d
0x180022c90  mov     rcx, rsi
0x180022c93  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180022c98  mov     esi, eax
0x180022c9a  test    eax, eax
0x180022c9c  jns     short loc_180022CB8
0x180022c9e  mov     rcx, [rbp+5Fh]; this
0x180022ca2  mov     r9d, eax; char *
0x180022ca5  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180022cac  mov     edx, 2A3h; void *
0x180022cb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022cb6  jmp     short loc_180022CBA
0x180022cb8  mov     esi, ebx
0x180022cba  lea     rdx, [rbp+57h+var_D0]
0x180022cbe  mov     rcx, r15
0x180022cc1  call    ??$ExtensionActivationAttempted@AEAV?$ComPtr@UIShellActivationManager@PlatformExtensions@Internal@Windows@@@WRL@Microsoft@@@ShellActivateApplication@ShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@QEAAXAEAV?$ComPtr@UIShellActivationManager@PlatformExtensions@Internal@Windows@@@WRL@Microsoft@@@Z; Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::ExtensionActivationAttempted<Microsoft::WRL::ComPtr<Windows::Internal::PlatformExtensions::IShellActivationManager> &>(Microsoft::WRL::ComPtr<Windows::Internal::PlatformExtensions::IShellActivationManager> &)
0x180022cc6  mov     rax, cs:Feature_TryShellActivateApplicationFallback__descriptor
0x180022ccd  mov     r8d, [rax]
0x180022cd0  test    r8b, 4
0x180022cd4  jnz     short loc_180022CE9
0x180022cd6  lea     rdx, [rbp+57h+var_60]
0x180022cda  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TryShellActivateApplicationFallback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TryShellActivateApplicationFallback>::GetCachedFeatureEnabledState(void)
0x180022cdf  mov     rcx, [rax]
0x180022ce2  mov     [rbp+57h+var_B8], rcx
0x180022ce6  mov     r8d, ecx
0x180022ce9  mov     [rbp+57h+var_C0], 0
0x180022cf0  mov     [rbp+57h+var_BC], 3
0x180022cf6  mov     r9d, r8d
0x180022cf9  shr     r9d, 0Bh
0x180022cfd  and     r9d, 1
0x180022d01  shr     r8d, 0Ah
0x180022d05  and     r8d, 1
0x180022d09  mov     dword ptr [rsp+120h+var_F0], 3
0x180022d11  mov     dword ptr [rsp+120h+var_F8], 1
0x180022d19  lea     rax, [rbp+57h+var_C0]
0x180022d1d  mov     qword ptr [rsp+120h+var_100], rax; int
0x180022d22  mov     edx, 1693E6Eh
0x180022d27  lea     rcx, qword_1801331F8
0x180022d2e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022d33  test    esi, esi
0x180022d35  js      loc_180022DEC
0x180022d3b  mov     rcx, [rbp+57h+var_D0]
0x180022d3f  test    rcx, rcx
0x180022d42  jz      loc_180022DEC
0x180022d48  mov     eax, [rdi+0B8h]
0x180022d4e  lea     rdx, [rbp+57h+var_C8]
0x180022d52  mov     [rsp+120h+var_D8], rdx
0x180022d57  lea     rdx, [rbp+57h+var_C4]
0x180022d5b  mov     [rsp+120h+var_E0], rdx
0x180022d60  mov     [rsp+120h+var_E8], rdi
0x180022d65  mov     r8, [rdi+0C0h]
0x180022d6c  mov     [rsp+120h+var_F0], r8
0x180022d71  mov     dword ptr [rsp+120h+var_F8], eax
0x180022d75  mov     rax, [rdi+0A8h]
0x180022d7c  mov     qword ptr [rsp+120h+var_100], rax; int
0x180022d81  mov     r9, [rdi+0A0h]
0x180022d88  mov     r8, [rdi+90h]
0x180022d8f  mov     rdx, [rdi+80h]
0x180022d96  call    ?TryActivateThroughShellPolicy@Details@Shell@Internal@Windows@@YAJPEAUIShellActivationManager@PlatformExtensions@34@PEAUHSTRING__@@1PEAUIPropertySet@Collections@Foundation@4@1UWindowId@WindowManagement@ApplicationModel@34@_K$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@PEAJPEAK@Z; Windows::Internal::Shell::Details::TryActivateThroughShellPolicy(Windows::Internal::PlatformExtensions::IShellActivationManager *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&,long *,ulong *)
0x180022d9b  mov     edi, eax
0x180022d9d  test    eax, eax
0x180022d9f  jns     loc_180022E63
0x180022da5  mov     rcx, [rbp+5Fh]; this
0x180022da9  mov     r9d, eax; char *
0x180022dac  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x180022db3  mov     edx, 195h; void *
0x180022db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022dbd  nop
0x180022dbe  mov     rcx, [rbp+57h+var_D0]
0x180022dc2  test    rcx, rcx
0x180022dc5  jz      short loc_180022DD8
0x180022dc7  mov     [rbp+57h+var_D0], rbx
0x180022dcb  mov     rax, [rcx]
0x180022dce  mov     rax, [rax+10h]
0x180022dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dd7  nop
0x180022dd8  cmp     [rbp+57h+var_78], ebx
0x180022ddb  jz      short loc_180022DE7
0x180022ddd  lea     rcx, [rbp+57h+var_90]; this
0x180022de1  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180022de6  nop
0x180022de7  jmp     loc_18002302C
0x180022dec  mov     rdx, [rdi+80h]
0x180022df3  mov     r8, [rdi+90h]
0x180022dfa  mov     rcx, [rdi+70h]
0x180022dfe  mov     rax, [rdi+0C0h]
0x180022e05  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdx
0x180022e09  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r8
0x180022e0d  test    rcx, rcx
0x180022e10  jz      loc_180022EC4
0x180022e16  mov     qword ptr [rbp+57h+var_58], rax
0x180022e1a  mov     rax, [rdi+0A0h]
0x180022e21  mov     [rbp+57h+var_60], rax
0x180022e25  lea     rax, [rbp+57h+var_C8]
0x180022e29  mov     [rbp+57h+var_B8], rax
0x180022e2d  mov     eax, [rdi+0B8h]
0x180022e33  mov     [rbp+57h+var_C0], eax
0x180022e36  mov     rax, [rcx]
0x180022e39  lea     rdx, [rbp+57h+var_B8]
0x180022e3d  mov     [rsp+120h+var_F8], rdx
0x180022e42  lea     rdx, [rbp+57h+var_58]
0x180022e46  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180022e4b  lea     r9, [rbp+57h+var_C0]
0x180022e4f  lea     r8, [rbp+57h+var_60]
0x180022e53  lea     rdx, [rbp+57h+hstringHeader]
0x180022e57  mov     rax, [rax+20h]
0x180022e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e60  mov     [rbp+57h+var_C4], eax
0x180022e63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022e6a  mov     ecx, 48h ; 'H'; unsigned __int64
0x180022e6f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022e74  test    rax, rax
0x180022e77  jz      loc_180022FE5
0x180022e7d  mov     rcx, rax; this
0x180022e80  call    ??0AppActivationResult@Details@Shell@Internal@Windows@@QEAA@XZ; Windows::Internal::Shell::Details::AppActivationResult::AppActivationResult(void)
0x180022e85  mov     rdi, rax
0x180022e88  mov     edx, [rbp+57h+var_C8]
0x180022e8b  mov     ecx, [rbp+57h+var_C4]
0x180022e8e  mov     [rax+40h], ecx
0x180022e91  mov     [rax+44h], edx
0x180022e94  mov     rcx, [rax+38h]
0x180022e98  mov     r8d, 7FFFFFFFh
0x180022e9e  test    rcx, rcx
0x180022ea1  js      loc_180022F28
0x180022ea7  cmp     ecx, r8d
0x180022eaa  jz      loc_180022F31
0x180022eb0  lea     rdx, [rcx+1]
0x180022eb4  mov     rax, rcx
0x180022eb7  lock cmpxchg [rdi+38h], rdx
0x180022ebd  mov     rcx, rax
0x180022ec0  jnz     short loc_180022E9E
0x180022ec2  jmp     short loc_180022F31
0x180022ec4  mov     rdx, rax
0x180022ec7  lea     rcx, [rbp+57h+hstringHeader]
0x180022ecb  call    ?FallbackActivateApplication@Details@Shell@Internal@Windows@@YAJUActivationArguments@234@_K@Z; Windows::Internal::Shell::Details::FallbackActivateApplication(Windows::Internal::Shell::ActivationArguments,unsigned __int64)
0x180022ed0  mov     edi, eax
0x180022ed2  test    eax, eax
0x180022ed4  jns     short loc_180022E63
0x180022ed6  mov     rcx, [rbp+5Fh]; this
0x180022eda  mov     r9d, eax; char *
0x180022edd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x180022ee4  mov     edx, 1A8h; void *
0x180022ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022eee  nop
0x180022eef  mov     rcx, [rbp+57h+var_D0]
0x180022ef3  test    rcx, rcx
0x180022ef6  jz      short loc_180022F09
0x180022ef8  mov     [rbp+57h+var_D0], rbx
0x180022efc  mov     rax, [rcx]
0x180022eff  mov     rax, [rax+10h]
0x180022f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f08  nop
0x180022f09  cmp     [rbp+57h+var_78], ebx
0x180022f0c  jz      short loc_180022F18
0x180022f0e  lea     rcx, [rbp+57h+var_90]; this
0x180022f12  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180022f17  nop
0x180022f18  jmp     loc_18002302C
0x180022f1d  lea     edx, [rax+1]
0x180022f20  lock cmpxchg [rcx+rcx+10h], edx
0x180022f26  jz      short loc_180022F31
0x180022f28  mov     eax, [rcx+rcx+10h]
0x180022f2c  cmp     eax, r8d
0x180022f2f  jnz     short loc_180022F1D
0x180022f31  mov     rcx, rdi
0x180022f34  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIShellActivationResult@PlatformExtensions@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::PlatformExtensions::IShellActivationResult,Microsoft::WRL::FtmBase>::Release(void)
0x180022f39  lea     rsi, [r13+10h]
0x180022f3d  mov     rcx, [rsi]
0x180022f40  mov     [rsi], rbx
0x180022f43  test    rcx, rcx
0x180022f46  jz      short loc_180022F55
0x180022f48  mov     rax, [rcx]
0x180022f4b  mov     rax, [rax+10h]
0x180022f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f54  nop
0x180022f55  mov     rcx, [rsi]
0x180022f58  test    rcx, rcx
0x180022f5b  jz      short loc_180022F6D
0x180022f5d  mov     [rsi], rbx
0x180022f60  mov     rax, [rcx]
0x180022f63  mov     rax, [rax+10h]
0x180022f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f6c  nop
0x180022f6d  mov     r9, rsi
0x180022f70  mov     r8, rdi
0x180022f73  lea     rdx, _GUID_e889ba92_1857_489e_b60e_a60ccf66e5da
0x180022f7a  xor     ecx, ecx
0x180022f7c  call    cs:__imp_RoGetAgileReference
0x180022f82  mov     r9d, [rbp+57h+var_C8]; unsigned int
0x180022f86  mov     r8d, [rbp+57h+var_C4]; int
0x180022f8a  mov     rcx, r15; this
0x180022f8d  call    ?Stop@ShellActivateApplication@ShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@QEAAX_NJK0@Z; Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::Stop(bool,long,ulong,bool)
0x180022f92  mov     rcx, rdi
0x180022f95  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIShellActivationResult@PlatformExtensions@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::PlatformExtensions::IShellActivationResult,Microsoft::WRL::FtmBase>::Release(void)
0x180022f9a  nop
0x180022f9b  mov     rcx, [rbp+57h+var_D0]
0x180022f9f  test    rcx, rcx
0x180022fa2  jz      short loc_180022FB5
0x180022fa4  mov     [rbp+57h+var_D0], rbx
0x180022fa8  mov     rax, [rcx]
  ... truncated ...
```
