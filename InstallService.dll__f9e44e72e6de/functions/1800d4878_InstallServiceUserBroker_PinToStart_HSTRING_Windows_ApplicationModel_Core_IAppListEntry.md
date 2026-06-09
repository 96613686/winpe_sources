# InstallServiceUserBroker::PinToStart(HSTRING__ *,Windows::ApplicationModel::Core::IAppListEntry *)

- ea: `0x1800d4878`
- end: `0x1800d4f0e`
- name: `?PinToStart@InstallServiceUserBroker@@AEAAJPEAUHSTRING__@@PEAUIAppListEntry@Core@ApplicationModel@Windows@@@Z`
- size: `1686`
- prototype: `int(InstallServiceUserBroker *__hidden this, HSTRING, struct Windows::ApplicationModel::Core::IAppListEntry *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d52b0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x1800252e8`
- `0x1800d3b88`
- `0x1800d4878`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4ce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4ce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4d98`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d48d6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d48d6`

## string_xrefs

- `0x1800d48e9`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d493e`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d49b1`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4a41`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4a5d`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4adf`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4bb0`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4c41`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4d1c`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4d39`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4dce`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4e36`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4e99`: `onecoreuap\enduser\winstore\installservice\lib\shellhelpers.cpp`
- `0x1800d4a34`: `InstallServiceUserBroker::PinToStart`
- `0x1800d4ba3`: `InstallServiceUserBroker::PinToStart`
- `0x1800d4d0f`: `InstallServiceUserBroker::PinToStart`
- `0x1800d4dc1`: `InstallServiceUserBroker::PinToStart`
- `0x1800d4b8f`: `%s is already pinned to the Start screen.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InstallServiceUserBroker::PinToStart(
        InstallServiceUserBroker *this,
        HSTRING a2,
        struct Windows::ApplicationModel::Core::IAppListEntry *a3)
{
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, struct Windows::ApplicationModel::Core::IAppListEntry *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, struct Windows::ApplicationModel::Core::IAppListEntry *, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 v32; // rcx
  __int64 v33; // rcx
  PCWSTR v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // [rsp+20h] [rbp-49h]
  int v42; // [rsp+20h] [rbp-49h]
  int v43; // [rsp+20h] [rbp-49h]
  __int64 v44; // [rsp+50h] [rbp-19h] BYREF
  __int64 v45; // [rsp+58h] [rbp-11h] BYREF
  char v46; // [rsp+60h] [rbp-9h] BYREF
  char v47; // [rsp+61h] [rbp-8h] BYREF
  _BYTE v48[6]; // [rsp+62h] [rbp-7h] BYREF
  __int64 v49; // [rsp+68h] [rbp-1h] BYREF
  __int64 v50; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v52; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v45 = 0;
  v52 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.StartScreen.StartScreenManager",
    0x2Au,
    0x29u);
  ActivationFactory = RoGetActivationFactory(v52, &GUID_7865ef0f_b585_464e_8993_34e8f8738d48, &v45);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v41);
    v7 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
  v44 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL))(v45, &v44);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v8,
      v41);
    v9 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v6;
  }
  v46 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Core::IAppListEntry *, char *))(*(_QWORD *)v44 + 56LL))(
          v44,
          a3,
          &v46);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v11,
      v41);
    v12 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v6;
  }
  if ( !v46 )
  {
    WindowsGetStringRawBuffer(a2, 0);
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      0x7Du,
      "InstallServiceUserBroker::PinToStart",
      -1,
      L"Start screen does not support pinning. Not pinning %s",
      0,
      0);
    v6 = -2147024846;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)0x80070032LL,
      v42);
    v14 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v6;
  }
  v49 = 0;
  v16 = v44;
  v17 = *(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Core::IAppListEntry *, __int64 *))(*(_QWORD *)v44 + 64LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
  v18 = v17(v16, a3, &v49);
  v6 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)(unsigned int)v18,
      v41);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
    v19 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v6;
  }
  v47 = 0;
  v21 = v49;
  v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(v49);
  if ( (v6 & 0x80000000) != 0
    || (v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v21 + 64LL))(v21, &v47), (v6 & 0x80000000) != 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      (const char *)v6,
      v41);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
    v39 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v6;
  }
  if ( v47 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      0x8Au,
      "InstallServiceUserBroker::PinToStart",
      -1,
      L"%s is already pinned to the Start screen.",
      0,
      0,
      StringRawBuffer);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
    v23 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return 2147942583LL;
  }
  else
  {
    v50 = 0;
    v26 = v44;
    v27 = *(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Core::IAppListEntry *, __int64 *))(*(_QWORD *)v44 + 72LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
    v28 = v27(v26, a3, &v50);
    v6 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
        (const char *)(unsigned int)v28,
        v41);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
      v29 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      return v6;
    }
    v48[0] = 0;
    v31 = v50;
    v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(v50);
    if ( (v6 & 0x80000000) != 0
      || (v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 64LL))(v31, v48), (v6 & 0x80000000) != 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
        (const char *)v6,
        v41);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
      v37 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      return v6;
    }
    if ( !v48[0] )
    {
      WindowsGetStringRawBuffer(a2, 0);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
        0x96u,
        "InstallServiceUserBroker::PinToStart",
        -1,
        L"PinToStart for %s unsuccessful.",
        0,
        0);
      v6 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
        (const char *)0x80004005LL,
        v43);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
      v32 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v33 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      return v6;
    }
    v34 = WindowsGetStringRawBuffer(a2, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\shellhelpers.cpp",
      0x9Au,
      "InstallServiceUserBroker::PinToStart",
      -1,
      L"Successfully Pinned %s to Start.",
      0,
      0,
      v34);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v49);
    v35 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800d4878  mov     [rsp-8+arg_0], rbx
0x1800d487d  push    rbp
0x1800d487e  push    rsi
0x1800d487f  push    rdi
0x1800d4880  push    r14
0x1800d4882  push    r15
0x1800d4884  lea     rbp, [rsp-37h]
0x1800d4889  sub     rsp, 0A0h
0x1800d4890  mov     rax, cs:__security_cookie
0x1800d4897  xor     rax, rsp
0x1800d489a  mov     [rbp+57h+var_28], rax
0x1800d489e  mov     rsi, r8
0x1800d48a1  mov     r14, rdx
0x1800d48a4  xor     r15d, r15d
0x1800d48a7  mov     [rbp+57h+var_68], r15
0x1800d48ab  mov     [rbp+57h+var_30], r15
0x1800d48af  lea     r9d, [r15+29h]; unsigned int
0x1800d48b3  lea     r8d, [r15+2Ah]; unsigned int
0x1800d48b7  lea     rdx, ?RuntimeClass_Windows_UI_StartScreen_StartScreenManager@@3QBGB; "Windows.UI.StartScreen.StartScreenManag"...
0x1800d48be  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d48c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d48c7  lea     r8, [rbp+57h+var_68]
0x1800d48cb  lea     rdx, _GUID_7865ef0f_b585_464e_8993_34e8f8738d48
0x1800d48d2  mov     rcx, [rbp+57h+var_30]
0x1800d48d6  call    cs:__imp_RoGetActivationFactory
0x1800d48dc  mov     ebx, eax
0x1800d48de  test    eax, eax
0x1800d48e0  jns     short loc_1800D4919
0x1800d48e2  mov     rcx, [rbp+5Fh]; this
0x1800d48e6  mov     r9d, eax; char *
0x1800d48e9  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d48f0  lea     edx, [r15+74h]; void *
0x1800d48f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d48f9  nop
0x1800d48fa  mov     rcx, [rbp+57h+var_68]
0x1800d48fe  test    rcx, rcx
0x1800d4901  jz      short loc_1800D4914
0x1800d4903  mov     [rbp+57h+var_68], r15
0x1800d4907  mov     rax, [rcx]
0x1800d490a  mov     rax, [rax+10h]
0x1800d490e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4913  nop
0x1800d4914  jmp     loc_1800D4EE9
0x1800d4919  mov     [rbp+57h+var_70], r15
0x1800d491d  mov     rcx, [rbp+57h+var_68]
0x1800d4921  mov     rax, [rcx]
0x1800d4924  lea     rdx, [rbp+57h+var_70]
0x1800d4928  mov     rax, [rax+30h]
0x1800d492c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4931  mov     ebx, eax
0x1800d4933  test    eax, eax
0x1800d4935  jns     short loc_1800D4989
0x1800d4937  mov     rcx, [rbp+5Fh]; this
0x1800d493b  mov     r9d, eax; char *
0x1800d493e  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4945  mov     edx, 77h ; 'w'; void *
0x1800d494a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d494f  nop
0x1800d4950  mov     rcx, [rbp+57h+var_70]
0x1800d4954  test    rcx, rcx
0x1800d4957  jz      short loc_1800D496A
0x1800d4959  mov     [rbp+57h+var_70], r15
0x1800d495d  mov     rax, [rcx]
0x1800d4960  mov     rax, [rax+10h]
0x1800d4964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4969  nop
0x1800d496a  mov     rcx, [rbp+57h+var_68]
0x1800d496e  test    rcx, rcx
0x1800d4971  jz      short loc_1800D4984
0x1800d4973  mov     [rbp+57h+var_68], r15
0x1800d4977  mov     rax, [rcx]
0x1800d497a  mov     rax, [rax+10h]
0x1800d497e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4983  nop
0x1800d4984  jmp     loc_1800D4EE9
0x1800d4989  mov     [rbp+57h+var_60], r15b
0x1800d498d  mov     rcx, [rbp+57h+var_70]
0x1800d4991  mov     rax, [rcx]
0x1800d4994  lea     r8, [rbp+57h+var_60]
0x1800d4998  mov     rdx, rsi
0x1800d499b  mov     rax, [rax+38h]
0x1800d499f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49a4  mov     ebx, eax
0x1800d49a6  test    eax, eax
0x1800d49a8  jns     short loc_1800D49FC
0x1800d49aa  mov     rcx, [rbp+5Fh]; this
0x1800d49ae  mov     r9d, eax; char *
0x1800d49b1  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d49b8  mov     edx, 7Ah ; 'z'; void *
0x1800d49bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d49c2  nop
0x1800d49c3  mov     rcx, [rbp+57h+var_70]
0x1800d49c7  test    rcx, rcx
0x1800d49ca  jz      short loc_1800D49DD
0x1800d49cc  mov     [rbp+57h+var_70], r15
0x1800d49d0  mov     rax, [rcx]
0x1800d49d3  mov     rax, [rax+10h]
0x1800d49d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49dc  nop
0x1800d49dd  mov     rcx, [rbp+57h+var_68]
0x1800d49e1  test    rcx, rcx
0x1800d49e4  jz      short loc_1800D49F7
0x1800d49e6  mov     [rbp+57h+var_68], r15
0x1800d49ea  mov     rax, [rcx]
0x1800d49ed  mov     rax, [rax+10h]
0x1800d49f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49f6  nop
0x1800d49f7  jmp     loc_1800D4EE9
0x1800d49fc  cmp     [rbp+57h+var_60], r15b
0x1800d4a00  jnz     loc_1800D4AA8
0x1800d4a06  xor     edx, edx; length
0x1800d4a08  mov     rcx, r14; string
0x1800d4a0b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4a11  mov     [rsp+0C0h+var_80], rax
0x1800d4a16  mov     [rsp+0C0h+var_88], r15; unsigned __int16 *
0x1800d4a1b  mov     [rsp+0C0h+var_90], r15; char *
0x1800d4a20  lea     rax, aStartScreenDoe; "Start screen does not support pinning. "...
0x1800d4a27  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x1800d4a2c  mov     [rsp+0C0h+var_A0], 0FFFFFFFFh; int
0x1800d4a34  lea     r9, aInstallservice_7; "InstallServiceUserBroker::PinToStart"
0x1800d4a3b  mov     r8d, 7Dh ; '}'; unsigned int
0x1800d4a41  lea     rdx, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4a48  lea     ecx, [r8-7Bh]; unsigned int
0x1800d4a4c  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d4a51  mov     rcx, [rbp+5Fh]; this
0x1800d4a55  mov     ebx, 80070032h
0x1800d4a5a  mov     r9d, ebx; char *
0x1800d4a5d  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4a64  mov     edx, 7Fh; void *
0x1800d4a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4a6e  nop
0x1800d4a6f  mov     rcx, [rbp+57h+var_70]
0x1800d4a73  test    rcx, rcx
0x1800d4a76  jz      short loc_1800D4A89
0x1800d4a78  mov     [rbp+57h+var_70], r15
0x1800d4a7c  mov     rax, [rcx]
0x1800d4a7f  mov     rax, [rax+10h]
0x1800d4a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4a88  nop
0x1800d4a89  mov     rcx, [rbp+57h+var_68]
0x1800d4a8d  test    rcx, rcx
0x1800d4a90  jz      short loc_1800D4AA3
0x1800d4a92  mov     [rbp+57h+var_68], r15
0x1800d4a96  mov     rdx, [rcx]
0x1800d4a99  mov     rax, [rdx+10h]
0x1800d4a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4aa2  nop
0x1800d4aa3  jmp     loc_1800D4EE9
0x1800d4aa8  mov     [rbp+57h+var_58], r15
0x1800d4aac  mov     rdi, [rbp+57h+var_70]
0x1800d4ab0  mov     rax, [rdi]
0x1800d4ab3  mov     rbx, [rax+40h]
0x1800d4ab7  lea     rcx, [rbp+57h+var_58]
0x1800d4abb  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4ac0  lea     r8, [rbp+57h+var_58]
0x1800d4ac4  mov     rdx, rsi
0x1800d4ac7  mov     rcx, rdi
0x1800d4aca  mov     rax, rbx
0x1800d4acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4ad2  mov     ebx, eax
0x1800d4ad4  test    eax, eax
0x1800d4ad6  jns     short loc_1800D4B34
0x1800d4ad8  mov     rcx, [rbp+5Fh]; this
0x1800d4adc  mov     r9d, eax; char *
0x1800d4adf  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4ae6  mov     edx, 83h; void *
0x1800d4aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4af0  nop
0x1800d4af1  lea     rcx, [rbp+57h+var_58]
0x1800d4af5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4afa  nop
0x1800d4afb  mov     rcx, [rbp+57h+var_70]
0x1800d4aff  test    rcx, rcx
0x1800d4b02  jz      short loc_1800D4B15
0x1800d4b04  mov     [rbp+57h+var_70], r15
0x1800d4b08  mov     rax, [rcx]
0x1800d4b0b  mov     rax, [rax+10h]
0x1800d4b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4b14  nop
0x1800d4b15  mov     rcx, [rbp+57h+var_68]
0x1800d4b19  test    rcx, rcx
0x1800d4b1c  jz      short loc_1800D4B2F
0x1800d4b1e  mov     [rbp+57h+var_68], r15
0x1800d4b22  mov     rax, [rcx]
0x1800d4b25  mov     rax, [rax+10h]
0x1800d4b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4b2e  nop
0x1800d4b2f  jmp     loc_1800D4EE9
0x1800d4b34  mov     [rbp+57h+var_5F], r15b
0x1800d4b38  mov     rdi, [rbp+57h+var_58]
0x1800d4b3c  mov     rcx, rdi
0x1800d4b3f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)
0x1800d4b44  mov     ebx, eax
0x1800d4b46  test    eax, eax
0x1800d4b48  js      loc_1800D4E92
0x1800d4b4e  mov     rax, [rdi]
0x1800d4b51  lea     rdx, [rbp+57h+var_5F]
0x1800d4b55  mov     rcx, rdi
0x1800d4b58  mov     rax, [rax+40h]
0x1800d4b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4b61  mov     ebx, eax
0x1800d4b63  test    eax, eax
0x1800d4b65  js      loc_1800D4E92
0x1800d4b6b  cmp     [rbp+57h+var_5F], r15b
0x1800d4b6f  jz      loc_1800D4C0A
0x1800d4b75  xor     edx, edx; length
0x1800d4b77  mov     rcx, r14; string
0x1800d4b7a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4b80  mov     [rsp+0C0h+var_80], rax
0x1800d4b85  mov     [rsp+0C0h+var_88], r15; unsigned __int16 *
0x1800d4b8a  mov     [rsp+0C0h+var_90], r15; char *
0x1800d4b8f  lea     rax, aSIsAlreadyPinn; "%s is already pinned to the Start scree"...
0x1800d4b96  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x1800d4b9b  mov     [rsp+0C0h+var_A0], 0FFFFFFFFh; int
0x1800d4ba3  lea     r9, aInstallservice_7; "InstallServiceUserBroker::PinToStart"
0x1800d4baa  mov     r8d, 8Ah; unsigned int
0x1800d4bb0  lea     rdx, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4bb7  mov     ecx, 3; unsigned int
0x1800d4bbc  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d4bc1  nop
0x1800d4bc2  lea     rcx, [rbp+57h+var_58]
0x1800d4bc6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4bcb  nop
0x1800d4bcc  mov     rcx, [rbp+57h+var_70]
0x1800d4bd0  test    rcx, rcx
0x1800d4bd3  jz      short loc_1800D4BE6
0x1800d4bd5  mov     [rbp+57h+var_70], r15
0x1800d4bd9  mov     rax, [rcx]
0x1800d4bdc  mov     rax, [rax+10h]
0x1800d4be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4be5  nop
0x1800d4be6  mov     rcx, [rbp+57h+var_68]
0x1800d4bea  test    rcx, rcx
0x1800d4bed  jz      short loc_1800D4C00
0x1800d4bef  mov     [rbp+57h+var_68], r15
0x1800d4bf3  mov     rax, [rcx]
0x1800d4bf6  mov     rax, [rax+10h]
0x1800d4bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4bff  nop
0x1800d4c00  mov     eax, 800700B7h
0x1800d4c05  jmp     loc_1800D4EEB
0x1800d4c0a  mov     [rbp+57h+var_50], r15
0x1800d4c0e  mov     rdi, [rbp+57h+var_70]
0x1800d4c12  mov     rax, [rdi]
0x1800d4c15  mov     rbx, [rax+48h]
0x1800d4c19  lea     rcx, [rbp+57h+var_50]
0x1800d4c1d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4c22  lea     r8, [rbp+57h+var_50]
0x1800d4c26  mov     rdx, rsi
0x1800d4c29  mov     rcx, rdi
0x1800d4c2c  mov     rax, rbx
0x1800d4c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4c34  mov     ebx, eax
0x1800d4c36  test    eax, eax
0x1800d4c38  jns     short loc_1800D4CA0
0x1800d4c3a  mov     rcx, [rbp+5Fh]; this
0x1800d4c3e  mov     r9d, eax; char *
0x1800d4c41  lea     r8, aOnecoreuapEndu_51; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d4c48  mov     edx, 8Fh; void *
0x1800d4c4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4c52  nop
0x1800d4c53  lea     rcx, [rbp+57h+var_50]
0x1800d4c57  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4c5c  nop
0x1800d4c5d  lea     rcx, [rbp+57h+var_58]
0x1800d4c61  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800d4c66  nop
0x1800d4c67  mov     rcx, [rbp+57h+var_70]
0x1800d4c6b  test    rcx, rcx
0x1800d4c6e  jz      short loc_1800D4C81
0x1800d4c70  mov     [rbp+57h+var_70], r15
0x1800d4c74  mov     rax, [rcx]
0x1800d4c77  mov     rax, [rax+10h]
0x1800d4c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4c80  nop
0x1800d4c81  mov     rcx, [rbp+57h+var_68]
0x1800d4c85  test    rcx, rcx
0x1800d4c88  jz      short loc_1800D4C9B
0x1800d4c8a  mov     [rbp+57h+var_68], r15
0x1800d4c8e  mov     rax, [rcx]
0x1800d4c91  mov     rax, [rax+10h]
0x1800d4c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4c9a  nop
0x1800d4c9b  jmp     loc_1800D4EE9
0x1800d4ca0  mov     [rbp+57h+var_5E], r15b
0x1800d4ca4  mov     rdi, [rbp+57h+var_50]
0x1800d4ca8  mov     rcx, rdi
0x1800d4cab  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)
0x1800d4cb0  mov     ebx, eax
0x1800d4cb2  test    eax, eax
0x1800d4cb4  js      loc_1800D4E2F
0x1800d4cba  mov     rax, [rdi]
0x1800d4cbd  lea     rdx, [rbp+57h+var_5E]
0x1800d4cc1  mov     rcx, rdi
0x1800d4cc4  mov     rax, [rax+40h]
0x1800d4cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4ccd  mov     ebx, eax
0x1800d4ccf  test    eax, eax
0x1800d4cd1  js      loc_1800D4E2F
0x1800d4cd7  xor     edx, edx; length
  ... truncated ...
```
