# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::_CreateDialog(bool)

- ea: `0x1800139a4`
- end: `0x180014050`
- name: `?_CreateDialog@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAX_N@Z`
- size: `1708`
- prototype: `void __fastcall(HWND *this, char)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019220`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x180002d55`
- `0x180002d91`
- `0x180002d9d`
- `0x180005cd8`
- `0x180007940`
- `0x180008820`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000b5f0`
- `0x18000e9d4`
- `0x1800100cc`
- `0x180012eb8`
- `0x1800139a4`
- `0x180014700`
- `0x1800148d0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013c7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013f1e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013f2e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013c7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013f1e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013ee2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013ee2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013ef0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013ef0`

## string_xrefs

- `0x180013f69`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180013f7e`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180013fab`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180013fc0`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180013fd5`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180013fea`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180013fff`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180014014`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x180014029`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x18001403e`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::_CreateDialog(
        HWND *this,
        char a2)
{
  const struct _tlgProvider_t *v3; // rax
  HWND *v4; // r14
  HRESULT v5; // eax
  LPVOID v6; // rbx
  LPVOID v7; // rsi
  LPVOID v8; // rdi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 (__fastcall *v12)(LPVOID, HWND *); // rdi
  _QWORD *v13; // r12
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, const wchar_t *); // r13
  __int64 ResourceString; // rax
  const wchar_t *v20; // rdx
  int v21; // eax
  void *v22; // rdi
  int v23; // eax
  HANDLE ProcessHeap; // rax
  int v25; // eax
  const struct _tlgProvider_t *v26; // rax
  void *v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdi
  void *v30; // rdi
  int v31; // eax
  HANDLE v32; // rax
  unsigned int v33; // eax
  __int64 v34; // rdi
  void *v35; // rdi
  int v36; // r13d
  HANDLE v37; // rax
  LPVOID v38; // rdi
  LPVOID v39; // r15
  int v40; // eax
  int v41; // eax
  void *v42; // rbx
  HANDLE v43; // rax
  int v44; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v47; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID v48; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v53; // [rsp+60h] [rbp-A0h] BYREF
  HWND *v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  char v56; // [rsp+78h] [rbp-88h]
  LPVOID v57[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v58[16]; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v59; // [rsp+A0h] [rbp-60h]
  char v60; // [rsp+A8h] [rbp-58h]
  _BYTE v61[48]; // [rsp+B0h] [rbp-50h] BYREF
  IID rclsid; // [rsp+E0h] [rbp-20h] BYREF
  int v63; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v64; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
    this + 12,
    v58);
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::_Initialize((winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase *)this);
  v3 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v3, &unk_180032EDB, 0, 0, 2, &v63);
  v4 = 0;
  v54 = 0;
  if ( this )
  {
    v4 = this;
    v54 = this;
    (*((void (__fastcall **)(HWND *))*this + 1))(this);
  }
  rclsid = CLSID_PopupWindowFactory;
  v48 = 0;
  v63 = 0;
  v64 = 0;
  v5 = CoCreateInstance_0(&rclsid, 0, 1u, &winrt::impl::guid_v<IPopupWindowFactory>, &v48);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v63);
  v6 = v48;
  v57[0] = v48;
  if ( v48 )
  {
    v48 = 0;
    v63 = 0;
    v64 = 0;
    v9 = (**(__int64 (__fastcall ***)(LPVOID, void *, LPVOID *))v6)(
           v6,
           &winrt::impl::guid_v<IXamlPopupFactoryConfigurationOptions>,
           &v48);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v63);
    v7 = v48;
    v53 = v48;
    v8 = v48;
  }
  else
  {
    v7 = 0;
    v53 = 0;
    v8 = 0;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v6 + 24LL))(v6, 1157627905);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v10,
      ppv);
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v8 + 32LL))(v8, 2);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  v49 = 0;
  v12 = *(__int64 (__fastcall **)(LPVOID, HWND *))(*(_QWORD *)v6 + 80LL);
  v13 = this + 54;
  if ( this[54] )
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(this + 54);
  v14 = v12(v6, this + 54);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v14,
      ppv);
  if ( v49 )
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v49);
  rclsid = IID_IOleWindow;
  v15 = (**(__int64 (__fastcall ***)(_QWORD, IID *, __int64 *))*v13)(*v13, &rclsid, &v49);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v15,
      ppv);
  v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v49 + 24LL))(v49, (char *)this + 88);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v16,
      ppv);
  FirewallUxTelemetry::DialogInitialize::PopupCreated(this[11]);
  v17 = *v13;
  v18 = *(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)*v13 + 32LL);
  ResourceString = GetResourceString(&lpMem, 1);
  if ( *(_QWORD *)ResourceString )
    v20 = *(const wchar_t **)(*(_QWORD *)ResourceString + 16LL);
  else
    v20 = &szFile;
  v21 = v18(v17, v20);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v21,
      ppv);
  v22 = lpMem;
  if ( lpMem )
  {
    v23 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v23 )
    {
      if ( v23 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v22);
    }
  }
  if ( a2 )
  {
    v26 = FirewallUxTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v26 <= 5u )
      goto LABEL_35;
    v27 = &unk_180032E6C;
    goto LABEL_34;
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD, HWND *))(*(_QWORD *)*v13 + 376LL))(*v13, v4);
  if ( v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v25,
      ppv);
  v26 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v26 > 5u )
  {
    v27 = &unk_180032E92;
LABEL_34:
    tlgWriteTransfer_EventWriteTransfer(v26, v27, 0, 0, 2, &v63);
  }
LABEL_35:
  (*((void (__fastcall **)(HWND *, __int64 *))*this + 10))(this, &v52);
  v28 = (*((__int64 (__fastcall **)(HWND *))*this + 8))(this);
  v29 = GetResourceString(&v51, v28);
  v47 = (*((__int64 (__fastcall **)(HWND *))*this + 8))(this);
  winrt::make_self<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,int,winrt::hstring,winrt::delegate<IPopupWindow *,IPopupCommand *> const &>(
    &v48,
    &v47,
    v29,
    &v52);
  v30 = v51;
  if ( v51 )
  {
    v31 = _InterlockedDecrement((volatile signed __int32 *)v51 + 6);
    if ( v31 )
    {
      if ( v31 < 0 )
        abort();
    }
    else
    {
      v32 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v32, 0, v30);
    }
    v51 = 0;
  }
  (*((void (__fastcall **)(HWND *, __int64 *))*this + 11))(this, &v55);
  if ( v56 )
  {
    v33 = (*((__int64 (__fastcall **)(HWND *))*this + 9))(this);
    v34 = GetResourceString(&v51, v33);
    v47 = (*((__int64 (__fastcall **)(HWND *))*this + 9))(this);
    winrt::make_self<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,int,winrt::hstring,winrt::delegate<IPopupWindow *,IPopupCommand *> const &>(
      &lpMem,
      &v47,
      v34,
      &v55);
    v35 = v51;
    if ( v51 )
    {
      v36 = _InterlockedDecrement((volatile signed __int32 *)v51 + 6);
      if ( v36 )
      {
        if ( v36 < 0 )
          abort();
      }
      else
      {
        v37 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v37, 0, v35);
      }
      v51 = 0;
    }
    v38 = v48;
    *(_QWORD *)&rclsid.Data1 = v48;
    v39 = lpMem;
    *(_QWORD *)rclsid.Data4 = lpMem;
    v40 = (*(__int64 (__fastcall **)(_QWORD, __int64, IID *))(*(_QWORD *)*v13 + 64LL))(*v13, 2, &rclsid);
    if ( v40 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
        (const char *)(unsigned int)v40,
        ppv);
    if ( v39 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  }
  else
  {
    v38 = v48;
    lpMem = v48;
    v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(*(_QWORD *)*v13 + 64LL))(*v13, 1, &lpMem);
    if ( v44 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
        (const char *)(unsigned int)v44,
        ppv);
  }
  v41 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v13 + 120LL))(*v13, 0);
  if ( v41 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
      (const char *)(unsigned int)v41,
      ppv);
  if ( v56 && v55 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v55);
  if ( v38 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v48);
  if ( v52 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v52);
  if ( v49 )
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v49);
  if ( v7 )
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v53);
  if ( v6 )
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(v57);
  if ( v4 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v54);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v61);
  if ( v60 )
  {
    v42 = v59;
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v42);
  }
}

```

## disassembly

```asm
0x1800139a4  push    rbp
0x1800139a6  push    rbx
0x1800139a7  push    rsi
0x1800139a8  push    rdi
0x1800139a9  push    r12
0x1800139ab  push    r13
0x1800139ad  push    r14
0x1800139af  push    r15
0x1800139b1  lea     rbp, [rsp-28h]
0x1800139b6  sub     rsp, 128h
0x1800139bd  mov     rax, cs:__security_cookie
0x1800139c4  xor     rax, rsp
0x1800139c7  mov     [rbp+60h+var_50], rax
0x1800139cb  mov     [rsp+160h+var_130], dl
0x1800139cf  mov     r15, rcx
0x1800139d2  xor     r13d, r13d
0x1800139d5  add     rcx, 60h ; '`'
0x1800139d9  lea     rdx, [rbp+60h+var_D0]
0x1800139dd  call    ?ContinueOnCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800139e2  nop
0x1800139e3  mov     rcx, r15; this
0x1800139e6  call    ?_Initialize@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::_Initialize(void)
0x1800139eb  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800139f0  mov     ecx, [rax]
0x1800139f2  lea     r12d, [r13+2]
0x1800139f6  cmp     ecx, 5
0x1800139f9  jbe     short loc_180013A1E
0x1800139fb  lea     rcx, [rbp+60h+var_70]
0x1800139ff  mov     [rsp+160h+var_138], rcx
0x180013a04  mov     dword ptr [rsp+160h+ppv], r12d
0x180013a09  xor     r9d, r9d
0x180013a0c  xor     r8d, r8d
0x180013a0f  lea     rdx, unk_180032EDB
0x180013a16  mov     rcx, rax
0x180013a19  call    _tlgWriteTransfer_EventWriteTransfer
0x180013a1e  mov     r14, r13
0x180013a21  mov     [rsp+160h+var_F8], r13
0x180013a26  test    r15, r15
0x180013a29  jz      short loc_180013A43
0x180013a2b  mov     r14, r15
0x180013a2e  mov     [rsp+160h+var_F8], r15
0x180013a33  mov     rax, [r15]
0x180013a36  mov     rcx, r15
0x180013a39  mov     rax, [rax+8]
0x180013a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a42  nop
0x180013a43  movups  xmm0, xmmword ptr cs:CLSID_PopupWindowFactory.Data1
0x180013a4a  movdqu  xmmword ptr [rbp+60h+rclsid.Data1], xmm0
0x180013a4f  mov     [rsp+160h+var_128], r13
0x180013a54  mov     [rbp+60h+var_70], r13d
0x180013a58  xorps   xmm0, xmm0
0x180013a5b  movdqu  [rbp+60h+var_68], xmm0
0x180013a60  lea     rax, [rsp+160h+var_128]
0x180013a65  mov     [rsp+160h+ppv], rax; int
0x180013a6a  lea     r9, ??$guid_v@UIPopupWindowFactory@@@impl@winrt@@3Uguid@2@B; riid
0x180013a71  xor     edx, edx; pUnkOuter
0x180013a73  lea     r8d, [rdx+1]; dwClsContext
0x180013a77  lea     rcx, [rbp+60h+rclsid]; rclsid
0x180013a7b  call    CoCreateInstance_0
0x180013a80  test    eax, eax
0x180013a82  js      loc_180013F90
0x180013a88  mov     rbx, [rsp+160h+var_128]
0x180013a8d  mov     [rbp+60h+var_E0], rbx
0x180013a91  test    rbx, rbx
0x180013a94  jnz     short loc_180013AA3
0x180013a96  mov     rsi, r13
0x180013a99  mov     [rsp+160h+var_100], r13
0x180013a9e  mov     rdi, r13
0x180013aa1  jmp     short loc_180013AE3
0x180013aa3  mov     [rsp+160h+var_128], r13
0x180013aa8  mov     [rbp+60h+var_70], r13d
0x180013aac  xorps   xmm0, xmm0
0x180013aaf  movdqu  [rbp+60h+var_68], xmm0
0x180013ab4  mov     rax, [rbx]
0x180013ab7  lea     r8, [rsp+160h+var_128]
0x180013abc  lea     rdx, ??$guid_v@UIXamlPopupFactoryConfigurationOptions@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IXamlPopupFactoryConfigurationOptions>
0x180013ac3  mov     rcx, rbx
0x180013ac6  mov     rax, [rax]
0x180013ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ace  test    eax, eax
0x180013ad0  js      loc_180013F9C
0x180013ad6  mov     rsi, [rsp+160h+var_128]
0x180013adb  mov     [rsp+160h+var_100], rsi
0x180013ae0  mov     rdi, rsi
0x180013ae3  mov     rax, [rbx]
0x180013ae6  mov     edx, 45000001h
0x180013aeb  mov     rcx, rbx
0x180013aee  mov     rax, [rax+18h]
0x180013af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af7  mov     rcx, [rbp+68h]; this
0x180013afb  test    eax, eax
0x180013afd  js      loc_180013FA8
0x180013b03  mov     rax, [rdi]
0x180013b06  mov     edx, r12d
0x180013b09  mov     rcx, rdi
0x180013b0c  mov     rax, [rax+20h]
0x180013b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b15  mov     rcx, [rbp+68h]; this
0x180013b19  test    eax, eax
0x180013b1b  js      loc_180013FBD
0x180013b21  mov     [rsp+160h+var_120], r13
0x180013b26  mov     rax, [rbx]
0x180013b29  mov     rdi, [rax+50h]
0x180013b2d  lea     r12, [r15+1B0h]
0x180013b34  cmp     [r12], r13
0x180013b38  jz      short loc_180013B42
0x180013b3a  mov     rcx, r12
0x180013b3d  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180013b42  mov     rdx, r12
0x180013b45  mov     rcx, rbx
0x180013b48  mov     rax, rdi
0x180013b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b50  mov     rcx, [rbp+68h]; this
0x180013b54  test    eax, eax
0x180013b56  js      loc_180013FD2
0x180013b5c  cmp     [rsp+160h+var_120], r13
0x180013b61  jz      short loc_180013B6D
0x180013b63  lea     rcx, [rsp+160h+var_120]
0x180013b68  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x180013b6d  movups  xmm0, xmmword ptr cs:IID_IOleWindow.Data1
0x180013b74  movdqu  xmmword ptr [rbp+60h+rclsid.Data1], xmm0
0x180013b79  mov     rcx, [r12]
0x180013b7d  mov     rax, [rcx]
0x180013b80  lea     r8, [rsp+160h+var_120]
0x180013b85  lea     rdx, [rbp+60h+rclsid]
0x180013b89  mov     rax, [rax]
0x180013b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b91  nop
0x180013b92  mov     rcx, [rbp+68h]; this
0x180013b96  test    eax, eax
0x180013b98  js      loc_180013FE7
0x180013b9e  mov     rcx, [rsp+160h+var_120]
0x180013ba3  mov     rax, [rcx]
0x180013ba6  lea     rdx, [r15+58h]
0x180013baa  mov     rax, [rax+18h]
0x180013bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb3  mov     rcx, [rbp+68h]; this
0x180013bb7  test    eax, eax
0x180013bb9  js      loc_180013FFC
0x180013bbf  mov     rcx, [r15+58h]; HWND
0x180013bc3  call    ?PopupCreated@DialogInitialize@FirewallUxTelemetry@@SAXPEAUHWND__@@@Z; FirewallUxTelemetry::DialogInitialize::PopupCreated(HWND__ *)
0x180013bc8  mov     rdi, [r12]
0x180013bcc  mov     rax, [rdi]
0x180013bcf  mov     r13, [rax+20h]
0x180013bd3  mov     edx, 1
0x180013bd8  lea     rcx, [rsp+160h+lpMem]
0x180013bdd  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180013be2  nop
0x180013be3  mov     rdx, [rax]
0x180013be6  test    rdx, rdx
0x180013be9  jz      short loc_180013BF1
0x180013beb  mov     rdx, [rdx+10h]
0x180013bef  jmp     short loc_180013BF8
0x180013bf1  lea     rdx, szFile
0x180013bf8  mov     rcx, rdi
0x180013bfb  mov     rax, r13
0x180013bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c03  mov     rcx, [rbp+68h]; this
0x180013c07  test    eax, eax
0x180013c09  js      loc_180014011
0x180013c0f  mov     rdi, [rsp+160h+lpMem]
0x180013c14  or      r13d, 0FFFFFFFFh
0x180013c18  test    rdi, rdi
0x180013c1b  jz      short loc_180013C3D
0x180013c1d  mov     eax, r13d
0x180013c20  lock xadd [rdi+18h], eax
0x180013c25  sub     eax, 1
0x180013c28  jnz     short loc_180013C7B
0x180013c2a  nop
0x180013c2b  call    WINRT_IMPL_GetProcessHeap
0x180013c30  mov     rcx, rax; hHeap
0x180013c33  mov     r8, rdi; lpMem
0x180013c36  xor     edx, edx; dwFlags
0x180013c38  call    WINRT_IMPL_HeapFree
0x180013c3d  cmp     [rsp+160h+var_130], 0
0x180013c42  jnz     short loc_180013C86
0x180013c44  mov     rcx, [r12]
0x180013c48  mov     rax, [rcx]
0x180013c4b  mov     rdx, r14
0x180013c4e  mov     rax, [rax+178h]
0x180013c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c5a  mov     rcx, [rbp+68h]; this
0x180013c5e  test    eax, eax
0x180013c60  js      loc_180014026
0x180013c66  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180013c6b  mov     ecx, [rax]
0x180013c6d  cmp     ecx, 5
0x180013c70  jbe     short loc_180013CB8
0x180013c72  lea     rdx, unk_180032E92
0x180013c79  jmp     short loc_180013C99
0x180013c7b  test    eax, eax
0x180013c7d  jns     short loc_180013C3D
0x180013c7f  call    cs:__imp_abort
0x180013c86  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180013c8b  mov     ecx, [rax]
0x180013c8d  cmp     ecx, 5
0x180013c90  jbe     short loc_180013CB8
0x180013c92  lea     rdx, unk_180032E6C
0x180013c99  lea     rcx, [rbp+60h+var_70]
0x180013c9d  mov     [rsp+160h+var_138], rcx
0x180013ca2  mov     dword ptr [rsp+160h+ppv], 2; int
0x180013caa  xor     r9d, r9d
0x180013cad  xor     r8d, r8d
0x180013cb0  mov     rcx, rax
0x180013cb3  call    _tlgWriteTransfer_EventWriteTransfer
0x180013cb8  mov     rax, [r15]
0x180013cbb  lea     rdx, [rsp+160h+var_108]
0x180013cc0  mov     rcx, r15
0x180013cc3  mov     rax, [rax+50h]
0x180013cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ccc  nop
0x180013ccd  mov     rax, [r15]
0x180013cd0  mov     rcx, r15
0x180013cd3  mov     rax, [rax+40h]
0x180013cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cdc  mov     edx, eax
0x180013cde  lea     rcx, [rsp+160h+var_110]
0x180013ce3  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180013ce8  mov     rdi, rax
0x180013ceb  mov     rcx, [r15]
0x180013cee  mov     rax, [rcx+40h]
0x180013cf2  mov     rcx, r15
0x180013cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cfa  mov     [rsp+160h+var_12C], eax
0x180013cfe  lea     r9, [rsp+160h+var_108]
0x180013d03  mov     r8, rdi
0x180013d06  lea     rdx, [rsp+160h+var_12C]
0x180013d0b  lea     rcx, [rsp+160h+var_128]
0x180013d10  call    ??$make_self@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@HUhstring@7@AEBU?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@7@@winrt@@YA?AU?$com_ptr@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@0@$$QEAH$$QEAUhstring@0@AEBU?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@0@@Z; winrt::make_self<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,int,winrt::hstring,winrt::delegate<IPopupWindow *,IPopupCommand *> const &>(int &&,winrt::hstring &&,winrt::delegate<IPopupWindow *,IPopupCommand *> const &)
0x180013d15  nop
0x180013d16  mov     rdi, [rsp+160h+var_110]
0x180013d1b  test    rdi, rdi
0x180013d1e  jz      short loc_180013D4D
0x180013d20  mov     eax, r13d
0x180013d23  lock xadd [rdi+18h], eax
0x180013d28  sub     eax, 1
0x180013d2b  jnz     loc_180013F16
0x180013d31  nop
0x180013d32  call    WINRT_IMPL_GetProcessHeap
0x180013d37  mov     rcx, rax; hHeap
0x180013d3a  mov     r8, rdi; lpMem
0x180013d3d  xor     edx, edx; dwFlags
0x180013d3f  call    WINRT_IMPL_HeapFree
0x180013d44  mov     [rsp+160h+var_110], 0
0x180013d4d  mov     rax, [r15]
0x180013d50  lea     rdx, [rsp+160h+var_F0]
0x180013d55  mov     rcx, r15
0x180013d58  mov     rax, [rax+58h]
0x180013d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d61  nop
0x180013d62  cmp     [rsp+160h+var_E8], 0
0x180013d67  jz      loc_180013F35
0x180013d6d  mov     rax, [r15]
0x180013d70  mov     rcx, r15
0x180013d73  mov     rax, [rax+48h]
0x180013d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d7c  mov     edx, eax
0x180013d7e  lea     rcx, [rsp+160h+var_110]
0x180013d83  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180013d88  mov     rdi, rax
0x180013d8b  mov     rdx, [r15]
0x180013d8e  mov     rcx, r15
0x180013d91  mov     rax, [rdx+48h]
0x180013d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d9a  mov     [rsp+160h+var_12C], eax
0x180013d9e  lea     r9, [rsp+160h+var_F0]
0x180013da3  mov     r8, rdi
0x180013da6  lea     rdx, [rsp+160h+var_12C]
0x180013dab  lea     rcx, [rsp+160h+lpMem]
0x180013db0  call    ??$make_self@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@HUhstring@7@AEBU?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@7@@winrt@@YA?AU?$com_ptr@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@0@$$QEAH$$QEAUhstring@0@AEBU?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@0@@Z; winrt::make_self<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,int,winrt::hstring,winrt::delegate<IPopupWindow *,IPopupCommand *> const &>(int &&,winrt::hstring &&,winrt::delegate<IPopupWindow *,IPopupCommand *> const &)
0x180013db5  nop
0x180013db6  mov     rdi, [rsp+160h+var_110]
0x180013dbb  test    rdi, rdi
0x180013dbe  jz      short loc_180013DEC
0x180013dc0  lock xadd [rdi+18h], r13d
0x180013dc6  sub     r13d, 1
0x180013dca  jnz     loc_180013F25
0x180013dd0  nop
0x180013dd1  call    WINRT_IMPL_GetProcessHeap
0x180013dd6  mov     rcx, rax; hHeap
0x180013dd9  mov     r8, rdi; lpMem
0x180013ddc  xor     edx, edx; dwFlags
0x180013dde  call    WINRT_IMPL_HeapFree
0x180013de3  mov     [rsp+160h+var_110], 0
0x180013dec  mov     rdi, [rsp+160h+var_128]
0x180013df1  mov     qword ptr [rbp+60h+rclsid.Data1], rdi
0x180013df5  mov     r15, [rsp+160h+lpMem]
0x180013dfa  mov     qword ptr [rbp+60h+rclsid.Data4], r15
0x180013dfe  mov     rcx, [r12]
0x180013e02  mov     rax, [rcx]
0x180013e05  lea     r8, [rbp+60h+rclsid]
0x180013e09  mov     edx, 2
0x180013e0e  mov     rax, [rax+40h]
0x180013e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e17  mov     rcx, [rbp+68h]; this
0x180013e1b  test    eax, eax
0x180013e1d  js      loc_18001403B
0x180013e23  test    r15, r15
0x180013e26  jz      short loc_180013E32
0x180013e28  lea     rcx, [rsp+160h+lpMem]
  ... truncated ...
```
