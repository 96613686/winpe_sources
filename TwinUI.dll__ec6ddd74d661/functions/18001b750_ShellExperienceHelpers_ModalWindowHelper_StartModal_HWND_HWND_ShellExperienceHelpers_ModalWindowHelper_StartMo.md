# ShellExperienceHelpers::ModalWindowHelper::StartModal(HWND__ *,HWND__ *,ShellExperienceHelpers::ModalWindowHelper::StartModalFlags,IPrivilegedWindowOwnershipOperations *,IPrivilegedForegroundOperations *)

- ea: `0x18001b750`
- end: `0x18001bba9`
- name: `?StartModal@ModalWindowHelper@ShellExperienceHelpers@@QEAAJPEAUHWND__@@0W4StartModalFlags@12@PEAUIPrivilegedWindowOwnershipOperations@@PEAUIPrivilegedForegroundOperations@@@Z`
- size: `1113`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019fb0`
- `0x1802198b8`

## callees

- `0x180009dfc`
- `0x18001b750`
- `0x1800378dc`
- `0x180037b9c`
- `0x1800eb924`
- `0x1800f5074`
- `0x1800f8f10`
- `0x180142e10`
- `0x1801a0d7c`
- `0x180213e0c`
- `0x180216838`
- `0x18021b9e8`
- `0x18021baf8`
- `0x1803bb010`

## import_xrefs

- `USER32!FlashWindow` at `0x18001bb0e`
- `USER32!FlashWindow` at `0x18001bb0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b7d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18001b9ae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18001b9ae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ba8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ba9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ba8b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ba9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18001bb57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18001bb57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18001b8d2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18001bad5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18001baf6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18001b8d2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18001bad5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18001baf6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18001bb3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18001bb3d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18001b9ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18001bae4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18001b9ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18001bae4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18001b966`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18001b966`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18001b91a`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18001b932`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18001b91a`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellManagedWindow` at `0x18001b932`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellExperienceHelpers::ModalWindowHelper::StartModal(
        _QWORD *a1,
        HWND a2,
        HWND a3,
        char a4,
        __int64 a5,
        struct IPrivilegedForegroundOperations *a6)
{
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // ebx
  __int64 v14; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, _QWORD *); // rbx
  _QWORD *v18; // r15
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  HWND v22; // r8
  __int64 v23; // rbx
  unsigned int UniqueContext; // eax
  __int64 v25; // rcx
  HWND v26; // r8
  HWND ForegroundWindow; // rax
  HWND v28; // rcx
  __int64 v29; // rdx
  DWORD WindowThreadProcessId; // ebx
  HWND Ancestor; // rbx
  HWND v32; // rax
  int v33; // [rsp+20h] [rbp-59h]
  HWND hwnd; // [rsp+40h] [rbp-39h] BYREF
  HWND hWnd; // [rsp+48h] [rbp-31h] BYREF
  __int64 v36; // [rsp+50h] [rbp-29h] BYREF
  struct IPrivilegedForegroundOperations *v37; // [rsp+58h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  hWnd = a2;
  hwnd = a3;
  v37 = a6;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup>::GetImpl'::`2'::impl,
    a2);
  if ( (a4 & 1) == 0 )
  {
    v36 = 0;
    string = 0;
    v9 = WindowsCreateStringReference(L"Windows.Internal.Shell.Popups.PopupClient", 0x29u, &hstringHeader, &string);
    if ( v9 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
      __debugbreak();
    }
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Shell::Popups::IPopupClientStatics>>(
            string,
            &v36);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
        (const char *)(unsigned int)v12,
        v33);
      v14 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return (unsigned int)v13;
    }
    v16 = v36;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v36 + 56LL);
    v18 = a1 + 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 1);
    v19 = v17(v16, (unsigned int)hwnd, a1 + 1);
    v13 = v19;
    if ( v19 != -2147024891 )
    {
      if ( v19 < 0 )
      {
        v20 = 271;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
          (const char *)(unsigned int)v19,
          v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        return (unsigned int)v13;
      }
      hstringHeader.Reserved.Reserved1 = 0;
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      v19 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*v18 + 72LL))(*v18, &hstringHeader);
      v13 = v19;
      if ( v19 < 0 )
      {
        v20 = 274;
        goto LABEL_13;
      }
      if ( *(_DWORD *)&hstringHeader.Reserved.Reserved2[4] )
        hwnd = GetAncestor((HWND)*(unsigned int *)&hstringHeader.Reserved.Reserved2[4], 2u);
      v21 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 56LL))(*v18);
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11C,
          (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
          (const char *)(unsigned int)v21,
          v33);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  }
  if ( !(unsigned int)IsShellManagedWindow(hWnd) || (unsigned int)IsShellManagedWindow(hwnd) )
  {
    if ( a5 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, HWND, HWND))(*(_QWORD *)a5 + 24LL))(a5, hWnd, hwnd);
      if ( v13 < 0 )
      {
        v29 = 325;
        goto LABEL_31;
      }
    }
    else
    {
      v13 = ShellExperienceHelpers::SetWindowOwner(hWnd, hwnd, v22);
      if ( v13 < 0 )
      {
        v29 = 329;
        goto LABEL_31;
      }
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
    v23 = _lambda_e71153b4466264dd044f9579b1f36c18_::_lambda_e71153b4466264dd044f9579b1f36c18_(
            &hstringHeader,
            &hWnd,
            &hwnd,
            &v37);
    UniqueContext = SHTaskPoolGetUniqueContext();
    v13 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<ShellExperienceHelpers::Internal::ProxyModalWindow,ShellExperienceHelpers::Internal::IProxyModalWindow,_lambda_b61c939eac1c13c2fa01af63e4f28967_>(
            v25,
            UniqueContext,
            a1,
            v23);
    if ( v13 == -2147024891 )
    {
      SetWindowPos(hWnd, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x13u);
      *((_BYTE *)a1 + 41) = 1;
      goto LABEL_23;
    }
    if ( v13 < 0 )
    {
      v29 = 311;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"shell\\twinui\\ExperienceManagers\\inc\\ModalWindowHelpers.h",
        (const char *)(unsigned int)v13,
        v33);
      return (unsigned int)v13;
    }
    ShellExperienceHelpers::FixRelativeZOrderingBeforeOwnership(hWnd, hwnd, v26);
  }
LABEL_23:
  if ( (a4 & 8) != 0 )
    goto LABEL_43;
  ForegroundWindow = GetForegroundWindow();
  if ( (a4 & 2) == 0 )
  {
    v28 = hwnd;
    if ( ForegroundWindow != hwnd && (ForegroundWindow || (a4 & 4) == 0) )
    {
LABEL_44:
      Ancestor = GetAncestor(v28, 3u);
      v32 = GetForegroundWindow();
      if ( Ancestor != GetAncestor(v32, 3u) )
        FlashWindow(Ancestor, 1);
      goto LABEL_46;
    }
    goto LABEL_42;
  }
  if ( !ForegroundWindow )
  {
    if ( (a4 & 4) != 0 )
      goto LABEL_42;
LABEL_43:
    v28 = hwnd;
    goto LABEL_44;
  }
  WindowThreadProcessId = GetWindowThreadProcessId(ForegroundWindow, 0);
  if ( WindowThreadProcessId != GetWindowThreadProcessId(hwnd, 0) )
    goto LABEL_43;
LABEL_42:
  if ( !ShellExperienceHelpers::ModalWindowHelper::SetForegroundWindowWithPrivilegedOperation(
          (ShellExperienceHelpers::ModalWindowHelper *)v28,
          v37,
          hWnd) )
    goto LABEL_43;
LABEL_46:
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 32LL))(*a1);
  SetPropW(hwnd, L"ModalExperienceWindowProp", hWnd);
  *((_BYTE *)a1 + 40) = 0;
  if ( (a4 & 8) == 0 )
    *((_BYTE *)a1 + 40) = !EnableWindow(hwnd, 0);
  a1[2] = hWnd;
  a1[4] = hwnd;
  a1[3] = a3;
  return 0;
}

```

## disassembly

```asm
0x18001b750  mov     [rsp-8+arg_18], rbx
0x18001b755  push    rbp
0x18001b756  push    rsi
0x18001b757  push    rdi
0x18001b758  push    r12
0x18001b75a  push    r13
0x18001b75c  push    r14
0x18001b75e  push    r15
0x18001b760  lea     rbp, [rsp-17h]
0x18001b765  sub     rsp, 90h
0x18001b76c  mov     rax, cs:__security_cookie
0x18001b773  xor     rax, rsp
0x18001b776  mov     [rbp+47h+var_40], rax
0x18001b77a  mov     r14d, r9d
0x18001b77d  mov     r13, r8
0x18001b780  mov     rsi, rcx
0x18001b783  mov     [rbp+47h+hWnd], rdx
0x18001b787  mov     [rbp+47h+hwnd], r8
0x18001b78b  mov     r12, [rbp+47h+arg_20]
0x18001b78f  mov     rax, [rbp+47h+arg_28]
0x18001b793  mov     [rbp+47h+var_68], rax
0x18001b797  mov     dl, 1
0x18001b799  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup@@@details@3@XZ@4V453@A
0x18001b7a0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModalWindowHelper_CUIHostLookup@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z
0x18001b7a5  test    r14b, 1
0x18001b7a9  jnz     loc_18001B916
0x18001b7af  mov     [rbp+47h+var_70], 0
0x18001b7b7  mov     [rbp+47h+string], 0
0x18001b7bf  lea     r9, [rbp+47h+string]; string
0x18001b7c3  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18001b7c7  mov     edx, 29h ; ')'; length
0x18001b7cc  lea     rcx, ?RuntimeClass_Windows_Internal_Shell_Popups_PopupClient@@3QBGB
0x18001b7d3  call    cs:__imp_WindowsCreateStringReference
0x18001b7da  nop     dword ptr [rax+rax+00h]
0x18001b7df  test    eax, eax
0x18001b7e1  jns     short loc_18001B7EB
0x18001b7e3  mov     ecx, eax; this
0x18001b7e5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z
0x18001b7ea  int     3; Trap to Debugger
0x18001b7eb  lea     rdx, [rbp+47h+var_70]
0x18001b7ef  mov     rcx, [rbp+47h+string]
0x18001b7f3  call    ??$GetActivationFactory@V?$ComPtr@UIPopupClientStatics@Popups@Shell@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPopupClientStatics@Popups@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z
0x18001b7f8  mov     ebx, eax
0x18001b7fa  test    eax, eax
0x18001b7fc  jns     short loc_18001B83C
0x18001b7fe  mov     rcx, [rbp+4Fh]; this
0x18001b802  mov     r9d, eax; char *
0x18001b805  lea     r8, aShellTwinuiExp_12
0x18001b80c  mov     edx, 108h; void *
0x18001b811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001b816  nop
0x18001b817  mov     rcx, [rbp+47h+var_70]
0x18001b81b  test    rcx, rcx
0x18001b81e  jz      short loc_18001B835
0x18001b820  mov     [rbp+47h+var_70], 0
0x18001b828  mov     rax, [rcx]
0x18001b82b  mov     rax, [rax+10h]
0x18001b82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b834  nop
0x18001b835  mov     eax, ebx
0x18001b837  jmp     loc_18001BB81
0x18001b83c  mov     rdi, [rbp+47h+var_70]
0x18001b840  mov     rax, [rdi]
0x18001b843  mov     rbx, [rax+38h]
0x18001b847  lea     r15, [rsi+8]
0x18001b84b  mov     rcx, r15
0x18001b84e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001b853  mov     r8, r15
0x18001b856  mov     edx, dword ptr [rbp+47h+hwnd]
0x18001b859  mov     rcx, rdi
0x18001b85c  mov     rax, rbx
0x18001b85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b864  mov     ebx, eax
0x18001b866  cmp     eax, 80070005h
0x18001b86b  jz      loc_18001B90D
0x18001b871  test    eax, eax
0x18001b873  jns     short loc_18001B87C
0x18001b875  mov     edx, 10Fh
0x18001b87a  jmp     short loc_18001B8A3
0x18001b87c  xor     eax, eax
0x18001b87e  mov     qword ptr [rbp+47h+hstringHeader.Reserved], rax
0x18001b882  mov     dword ptr [rbp+47h+hstringHeader.Reserved+8], eax
0x18001b885  mov     rcx, [r15]
0x18001b888  mov     rax, [rcx]
0x18001b88b  lea     rdx, [rbp+47h+hstringHeader]
0x18001b88f  mov     rax, [rax+48h]
0x18001b893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b898  mov     ebx, eax
0x18001b89a  test    eax, eax
0x18001b89c  jns     short loc_18001B8C4
0x18001b89e  mov     edx, 112h; void *
0x18001b8a3  mov     r9d, eax; char *
0x18001b8a6  lea     r8, aShellTwinuiExp_12
0x18001b8ad  mov     rcx, [rbp+4Fh]; this
0x18001b8b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001b8b6  lea     rcx, [rbp+47h+var_70]
0x18001b8ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001b8bf  jmp     loc_18001B835
0x18001b8c4  mov     eax, dword ptr [rbp+47h+hstringHeader.Reserved+4]
0x18001b8c7  test    eax, eax
0x18001b8c9  jz      short loc_18001B8E2
0x18001b8cb  mov     ecx, eax; hwnd
0x18001b8cd  mov     edx, 2; gaFlags
0x18001b8d2  call    cs:__imp_GetAncestor
0x18001b8d9  nop     dword ptr [rax+rax+00h]
0x18001b8de  mov     [rbp+47h+hwnd], rax
0x18001b8e2  mov     rcx, [r15]
0x18001b8e5  mov     rax, [rcx]
0x18001b8e8  mov     rax, [rax+38h]
0x18001b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f1  test    eax, eax
0x18001b8f3  jns     short loc_18001B90D
0x18001b8f5  mov     rcx, [rbp+4Fh]; this
0x18001b8f9  mov     r9d, eax; char *
0x18001b8fc  lea     r8, aShellTwinuiExp_12
0x18001b903  mov     edx, 11Ch; void *
0x18001b908  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001b90d  lea     rcx, [rbp+47h+var_70]
0x18001b911  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001b916  mov     rcx, [rbp+47h+hWnd]
0x18001b91a  call    cs:__imp_IsShellManagedWindow
0x18001b921  nop     dword ptr [rax+rax+00h]
0x18001b926  test    eax, eax
0x18001b928  jz      loc_18001BA35
0x18001b92e  mov     rcx, [rbp+47h+hwnd]
0x18001b932  call    cs:__imp_IsShellManagedWindow
0x18001b939  nop     dword ptr [rax+rax+00h]
0x18001b93e  test    eax, eax
0x18001b940  jnz     loc_18001BA35
0x18001b946  mov     rcx, rsi
0x18001b949  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18001b94e  lea     r9, [rbp+47h+var_68]
0x18001b952  lea     r8, [rbp+47h+hwnd]
0x18001b956  lea     rdx, [rbp+47h+hWnd]
0x18001b95a  lea     rcx, [rbp+47h+hstringHeader]
0x18001b95e  call    ??0_lambda_e71153b4466264dd044f9579b1f36c18_@@QEAA@PEAV?$SimpleVectorView@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@V?$Vector@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@@2Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@@2785@U?$VectorOptions@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@$00$00$0A@@2785@@2Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@@2785@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAIAEAPEAPEAUIContactActionControlItem@2Contacts@ApplicationModel@5@@Z
0x18001b963  mov     rbx, rax
0x18001b966  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18001b96d  nop     dword ptr [rax+rax+00h]
0x18001b972  mov     r9, rbx
0x18001b975  mov     r8, rsi
0x18001b978  mov     edx, eax
0x18001b97a  call    ??$_MakeAndInitializeOnSTAThread@VProxyModalWindow@Internal@ShellExperienceHelpers@@UIProxyModalWindow@23@V_lambda_b61c939eac1c13c2fa01af63e4f28967_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIProxyModalWindow@1ShellExperienceHelpers@@AEBV_lambda_b61c939eac1c13c2fa01af63e4f28967_@@@Z
0x18001b97f  mov     ebx, eax
0x18001b981  cmp     eax, 80070005h
0x18001b986  jnz     short loc_18001BA05
0x18001b988  mov     [rsp+0C0h+uFlags], 13h; uFlags
0x18001b990  mov     [rsp+0C0h+cy], 0; cy
0x18001b998  mov     [rsp+0C0h+var_A0], 0; cx
0x18001b9a0  xor     r9d, r9d; Y
0x18001b9a3  xor     r8d, r8d; X
0x18001b9a6  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18001b9aa  mov     rcx, [rbp+47h+hWnd]; hWnd
0x18001b9ae  call    cs:__imp_SetWindowPos
0x18001b9b5  nop     dword ptr [rax+rax+00h]
0x18001b9ba  mov     byte ptr [rsi+29h], 1
0x18001b9be  mov     edi, r14d
0x18001b9c1  and     edi, 8
0x18001b9c4  jnz     loc_18001BAC8
0x18001b9ca  call    cs:__imp_GetForegroundWindow
0x18001b9d1  nop     dword ptr [rax+rax+00h]
0x18001b9d6  test    r14b, 2
0x18001b9da  jnz     loc_18001BA81
0x18001b9e0  mov     rcx, [rbp+47h+hwnd]
0x18001b9e4  cmp     rax, rcx
0x18001b9e7  jz      loc_18001BAB7
0x18001b9ed  test    rax, rax
0x18001b9f0  jnz     loc_18001BACC
0x18001b9f6  test    r14b, 4
0x18001b9fa  jz      loc_18001BACC
0x18001ba00  jmp     loc_18001BAB7
0x18001ba05  test    ebx, ebx
0x18001ba07  jns     short loc_18001BA26
0x18001ba09  mov     edx, 137h; void *
0x18001ba0e  mov     rcx, [rbp+4Fh]; this
0x18001ba12  mov     r9d, ebx; char *
0x18001ba15  lea     r8, aShellTwinuiExp_12
0x18001ba1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18001ba21  jmp     loc_18001B835
0x18001ba26  mov     rdx, [rbp+47h+hwnd]; hWnd
0x18001ba2a  mov     rcx, [rbp+47h+hWnd]; hWndInsertAfter
0x18001ba2e  call    ?FixRelativeZOrderingBeforeOwnership@ShellExperienceHelpers@@YAXPEAUHWND__@@0@Z
0x18001ba33  jmp     short loc_18001B9BE
0x18001ba35  test    r12, r12
0x18001ba38  jz      short loc_18001BA63
0x18001ba3a  mov     rax, [r12]
0x18001ba3e  mov     r8, [rbp+47h+hwnd]
0x18001ba42  mov     rdx, [rbp+47h+hWnd]
0x18001ba46  mov     rcx, r12
0x18001ba49  mov     rax, [rax+18h]
0x18001ba4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba52  mov     ebx, eax
0x18001ba54  test    eax, eax
0x18001ba56  jns     loc_18001B9BE
0x18001ba5c  mov     edx, 145h
0x18001ba61  jmp     short loc_18001BA0E
0x18001ba63  mov     rdx, [rbp+47h+hwnd]; hWndInsertAfter
0x18001ba67  mov     rcx, [rbp+47h+hWnd]; hWnd
0x18001ba6b  call    ?SetWindowOwner@ShellExperienceHelpers@@YAJPEAUHWND__@@0@Z
0x18001ba70  mov     ebx, eax
0x18001ba72  test    eax, eax
0x18001ba74  jns     loc_18001B9BE
0x18001ba7a  mov     edx, 149h
0x18001ba7f  jmp     short loc_18001BA0E
0x18001ba81  test    rax, rax
0x18001ba84  jz      short loc_18001BAB1
0x18001ba86  xor     edx, edx; lpdwProcessId
0x18001ba88  mov     rcx, rax; hWnd
0x18001ba8b  call    cs:__imp_GetWindowThreadProcessId
0x18001ba92  nop     dword ptr [rax+rax+00h]
0x18001ba97  mov     ebx, eax
0x18001ba99  xor     edx, edx; lpdwProcessId
0x18001ba9b  mov     rcx, [rbp+47h+hwnd]; hWnd
0x18001ba9f  call    cs:__imp_GetWindowThreadProcessId
0x18001baa6  nop     dword ptr [rax+rax+00h]
0x18001baab  cmp     ebx, eax
0x18001baad  jz      short loc_18001BAB7
0x18001baaf  jmp     short loc_18001BAC8
0x18001bab1  test    r14b, 4
0x18001bab5  jz      short loc_18001BAC8
0x18001bab7  mov     r8, [rbp+47h+hWnd]; HWND
0x18001babb  mov     rdx, [rbp+47h+var_68]; struct IPrivilegedForegroundOperations *
0x18001babf  call    ?SetForegroundWindowWithPrivilegedOperation@ModalWindowHelper@ShellExperienceHelpers@@AEAA_NPEAUIPrivilegedForegroundOperations@@PEAUHWND__@@@Z
0x18001bac4  test    al, al
0x18001bac6  jnz     short loc_18001BB1A
0x18001bac8  mov     rcx, [rbp+47h+hwnd]; hwnd
0x18001bacc  mov     r14d, 3
0x18001bad2  mov     edx, r14d; gaFlags
0x18001bad5  call    cs:__imp_GetAncestor
0x18001badc  nop     dword ptr [rax+rax+00h]
0x18001bae1  mov     rbx, rax
0x18001bae4  call    cs:__imp_GetForegroundWindow
0x18001baeb  nop     dword ptr [rax+rax+00h]
0x18001baf0  mov     rcx, rax; hwnd
0x18001baf3  mov     edx, r14d; gaFlags
0x18001baf6  call    cs:__imp_GetAncestor
0x18001bafd  nop     dword ptr [rax+rax+00h]
0x18001bb02  cmp     rbx, rax
0x18001bb05  jz      short loc_18001BB1A
0x18001bb07  lea     edx, [r14-2]; bInvert
0x18001bb0b  mov     rcx, rbx; hWnd
0x18001bb0e  call    cs:__imp_FlashWindow
0x18001bb15  nop     dword ptr [rax+rax+00h]
0x18001bb1a  mov     rcx, [rsi]
0x18001bb1d  test    rcx, rcx
0x18001bb20  jz      short loc_18001BB2E
0x18001bb22  mov     rax, [rcx]
0x18001bb25  mov     rax, [rax+20h]
0x18001bb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb2e  mov     r8, [rbp+47h+hWnd]; hData
0x18001bb32  lea     rdx, aModalexperienc_0
0x18001bb39  mov     rcx, [rbp+47h+hwnd]; hWnd
0x18001bb3d  call    cs:__imp_SetPropW
0x18001bb44  nop     dword ptr [rax+rax+00h]
0x18001bb49  mov     byte ptr [rsi+28h], 0
0x18001bb4d  test    edi, edi
0x18001bb4f  jnz     short loc_18001BB6B
0x18001bb51  xor     edx, edx; bEnable
0x18001bb53  mov     rcx, [rbp+47h+hwnd]; hWnd
0x18001bb57  call    cs:__imp_EnableWindow
0x18001bb5e  nop     dword ptr [rax+rax+00h]
0x18001bb63  test    eax, eax
0x18001bb65  setz    al
0x18001bb68  mov     [rsi+28h], al
0x18001bb6b  mov     rax, [rbp+47h+hWnd]
0x18001bb6f  mov     [rsi+10h], rax
0x18001bb73  mov     rax, [rbp+47h+hwnd]
0x18001bb77  mov     [rsi+20h], rax
0x18001bb7b  mov     [rsi+18h], r13
0x18001bb7f  xor     eax, eax
0x18001bb81  mov     rcx, [rbp+47h+var_40]
0x18001bb85  xor     rcx, rsp; StackCookie
0x18001bb88  call    __security_check_cookie
0x18001bb8d  mov     rbx, [rsp+0C0h+arg_18]
0x18001bb95  add     rsp, 90h
0x18001bb9c  pop     r15
0x18001bb9e  pop     r14
0x18001bba0  pop     r13
0x18001bba2  pop     r12
0x18001bba4  pop     rdi
0x18001bba5  pop     rsi
0x18001bba6  pop     rbp
0x18001bba7  retn
```
