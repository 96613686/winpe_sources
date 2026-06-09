# WnsListener::CreateWpnObjects(Microsoft::WRL::ComPtr<IWpnPlatform> &,Microsoft::WRL::ComPtr<IWpnSystemRegistrationEndpoint> &)

- ea: `0x180058a98`
- end: `0x180058d51`
- name: `?CreateWpnObjects@WnsListener@@AEAAXAEAV?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@AEAV?$ComPtr@UIWpnSystemRegistrationEndpoint@@@34@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009e070`

## callees

- `0x180004738`
- `0x180058a98`
- `0x1800593bc`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058b33`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058bbc`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058c5d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058cf3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058b33`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058bbc`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058c5d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180058cf3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058adb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058adb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WnsListener::CreateWpnObjects(IUnknown *a1, LPVOID *a2, IUnknown **a3)
{
  HRESULT Instance; // eax
  HRESULT v6; // eax
  int v7; // eax
  HRESULT v8; // eax
  IUnknown *v9; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v11; // eax
  HRESULT v12; // eax
  IUnknown *v13; // rbx
  HRESULT (__stdcall *v14)(IUnknown *, const IID *const, void **); // rdi
  int v15; // eax
  HRESULT v16; // eax
  __int64 result; // rax
  IUnknown *v18; // rcx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  int ppvb; // [rsp+20h] [rbp-20h]
  int ppvc; // [rsp+20h] [rbp-20h]
  int ppvd; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  IUnknown *v25; // [rsp+60h] [rbp+20h] BYREF
  IUnknown *pProxy; // [rsp+68h] [rbp+28h] BYREF

  v25 = a1;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  Instance = CoCreateInstance(
               &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
               0,
               0x100404u,
               &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
               a2);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v6 = CoSetProxyBlanket((IUnknown *)*a2, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v6,
      ppva);
  pProxy = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, IUnknown **))(*(_QWORD *)*a2 + 40LL))(*a2, &pProxy);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v7,
      ppva);
  v8 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v8,
      ppvb);
  v25 = 0;
  v9 = pProxy;
  QueryInterface = pProxy->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v11 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))QueryInterface)(
          v9,
          &GUID_00000000_0000_0000_c000_000000000046,
          &v25);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v11,
      ppvb);
  v12 = CoSetProxyBlanket(v25, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v12,
      ppvc);
  v13 = v25;
  v14 = v25->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a3);
  v15 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v14)(
          v13,
          &GUID_7d85494e_d99e_493a_bf51_80d2c9feab49,
          a3);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v15,
      ppvc);
  v16 = CoSetProxyBlanket(*a3, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
      (const char *)(unsigned int)v16,
      ppvd);
  result = Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v18 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    return ((__int64 (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
  }
  return result;
}

```

## disassembly

```asm
0x180058a98  mov     [rsp-18h+arg_10], rbx
0x180058a9d  mov     [rsp-18h+arg_18], rsi
0x180058aa2  mov     [rsp-18h+arg_0], rcx
0x180058aa7  push    rbp
0x180058aa8  push    rdi
0x180058aa9  push    r15
0x180058aab  mov     rbp, rsp
0x180058aae  sub     rsp, 40h
0x180058ab2  mov     rsi, r8
0x180058ab5  mov     rbx, rdx
0x180058ab8  mov     rcx, rdx
0x180058abb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180058ac0  mov     [rsp+40h+ppv], rbx; int
0x180058ac5  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180058acc  xor     edx, edx; pUnkOuter
0x180058ace  mov     r8d, 100404h; dwClsContext
0x180058ad4  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x180058adb  call    cs:__imp_CoCreateInstance
0x180058ae1  mov     rcx, [rbp+18h]; this
0x180058ae5  test    eax, eax
0x180058ae7  jns     short loc_180058AFE
0x180058ae9  mov     r9d, eax; char *
0x180058aec  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058af3  mov     edx, 22Ch; void *
0x180058af8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058afe  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180058b06  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x180058b0f  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180058b17  mov     dword ptr [rsp+40h+ppv], 0; int
0x180058b1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180058b23  mov     r9, rdi; pServerPrincName
0x180058b26  or      r15d, 0FFFFFFFFh
0x180058b2a  mov     r8d, r15d; dwAuthzSvc
0x180058b2d  mov     edx, r15d; dwAuthnSvc
0x180058b30  mov     rcx, [rbx]; pProxy
0x180058b33  call    cs:__imp_CoSetProxyBlanket
0x180058b39  mov     rcx, [rbp+18h]; this
0x180058b3d  test    eax, eax
0x180058b3f  jns     short loc_180058B56
0x180058b41  mov     r9d, eax; char *
0x180058b44  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058b4b  mov     edx, 22Dh; void *
0x180058b50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058b56  mov     [rbp+pProxy], 0
0x180058b5e  mov     rcx, [rbx]
0x180058b61  mov     rax, [rcx]
0x180058b64  lea     rdx, [rbp+pProxy]
0x180058b68  mov     rax, [rax+28h]
0x180058b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b71  mov     rcx, [rbp+18h]; this
0x180058b75  test    eax, eax
0x180058b77  jns     short loc_180058B8E
0x180058b79  mov     r9d, eax; char *
0x180058b7c  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058b83  mov     edx, 230h; void *
0x180058b88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058b8e  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180058b96  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x180058b9f  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180058ba7  mov     dword ptr [rsp+40h+ppv], 0; int
0x180058baf  mov     r9, rdi; pServerPrincName
0x180058bb2  mov     r8d, r15d; dwAuthzSvc
0x180058bb5  mov     edx, r15d; dwAuthnSvc
0x180058bb8  mov     rcx, [rbp+pProxy]; pProxy
0x180058bbc  call    cs:__imp_CoSetProxyBlanket
0x180058bc2  mov     rcx, [rbp+18h]; this
0x180058bc6  test    eax, eax
0x180058bc8  jns     short loc_180058BDF
0x180058bca  mov     r9d, eax; char *
0x180058bcd  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058bd4  mov     edx, 231h; void *
0x180058bd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058bdf  mov     [rbp+arg_0], 0
0x180058be7  mov     rbx, [rbp+pProxy]
0x180058beb  mov     rax, [rbx]
0x180058bee  mov     rdi, [rax]
0x180058bf1  lea     rcx, [rbp+arg_0]
0x180058bf5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180058bfa  lea     r8, [rbp+arg_0]
0x180058bfe  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180058c05  mov     rcx, rbx
0x180058c08  mov     rax, rdi
0x180058c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c10  nop
0x180058c11  mov     rcx, [rbp+18h]; this
0x180058c15  test    eax, eax
0x180058c17  jns     short loc_180058C2E
0x180058c19  mov     r9d, eax; char *
0x180058c1c  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058c23  mov     edx, 234h; void *
0x180058c28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058c2e  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180058c36  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x180058c3f  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180058c47  mov     dword ptr [rsp+40h+ppv], 0; int
0x180058c4f  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180058c53  mov     r8d, r15d; dwAuthzSvc
0x180058c56  mov     edx, r15d; dwAuthnSvc
0x180058c59  mov     rcx, [rbp+arg_0]; pProxy
0x180058c5d  call    cs:__imp_CoSetProxyBlanket
0x180058c63  mov     rcx, [rbp+18h]; this
0x180058c67  test    eax, eax
0x180058c69  jns     short loc_180058C80
0x180058c6b  mov     r9d, eax; char *
0x180058c6e  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058c75  mov     edx, 235h; void *
0x180058c7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058c80  mov     rbx, [rbp+arg_0]
0x180058c84  mov     rax, [rbx]
0x180058c87  mov     rdi, [rax]
0x180058c8a  mov     rcx, rsi
0x180058c8d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180058c92  mov     r8, rsi
0x180058c95  lea     rdx, _GUID_7d85494e_d99e_493a_bf51_80d2c9feab49
0x180058c9c  mov     rcx, rbx
0x180058c9f  mov     rax, rdi
0x180058ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ca7  nop
0x180058ca8  mov     rcx, [rbp+18h]; this
0x180058cac  test    eax, eax
0x180058cae  jns     short loc_180058CC5
0x180058cb0  mov     r9d, eax; char *
0x180058cb3  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058cba  mov     edx, 237h; void *
0x180058cbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058cc5  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180058ccd  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x180058cd6  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180058cde  mov     dword ptr [rsp+40h+ppv], 0; int
0x180058ce6  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180058cea  mov     r8d, r15d; dwAuthzSvc
0x180058ced  mov     edx, r15d; dwAuthnSvc
0x180058cf0  mov     rcx, [rsi]; pProxy
0x180058cf3  call    cs:__imp_CoSetProxyBlanket
0x180058cf9  mov     rcx, [rbp+18h]; this
0x180058cfd  test    eax, eax
0x180058cff  jns     short loc_180058D16
0x180058d01  mov     r9d, eax; char *
0x180058d04  lea     r8, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058d0b  mov     edx, 238h; void *
0x180058d10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058d16  lea     rcx, [rbp+arg_0]
0x180058d1a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180058d1f  nop
0x180058d20  mov     rcx, [rbp+pProxy]
0x180058d24  test    rcx, rcx
0x180058d27  jz      short loc_180058D3E
0x180058d29  mov     [rbp+pProxy], 0
0x180058d31  mov     rax, [rcx]
0x180058d34  mov     rax, [rax+10h]
0x180058d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d3d  nop
0x180058d3e  mov     rbx, [rsp+40h+arg_10]
0x180058d43  mov     rsi, [rsp+40h+arg_18]
0x180058d48  add     rsp, 40h
0x180058d4c  pop     r15
0x180058d4e  pop     rdi
0x180058d4f  pop     rbp
0x180058d50  retn
```
