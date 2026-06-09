# Windows::Networking::UX::CreateProvisioningDocumentFromXml(HSTRING__ *,IProvisioningDocument * *)

- ea: `0x18002a4dc`
- end: `0x18002a6be`
- name: `?CreateProvisioningDocumentFromXml@UX@Networking@Windows@@YAJPEAUHSTRING__@@PEAPEAUIProvisioningDocument@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(Windows::Networking::UX *__hidden this, HSTRING, struct IProvisioningDocument **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a740`
- `0x18002b640`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x1800097b4`
- `0x18002a4dc`
- `0x18002b488`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002a5db`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002a654`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002a5db`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002a654`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a579`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a579`

## string_xrefs

- `0x18002a535`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002a58a`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::UX::CreateProvisioningDocumentFromXml(
        Windows::Networking::UX *this,
        IUnknown **a2,
        struct IProvisioningDocument **a3)
{
  struct IStream **v4; // r8
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  HRESULT Instance; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  IUnknown *v17; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  IUnknown *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  int ppv; // [rsp+20h] [rbp-29h]
  int ppva; // [rsp+20h] [rbp-29h]
  IUnknown *pProxy; // [rsp+40h] [rbp-9h] BYREF
  IUnknown *v28; // [rsp+48h] [rbp-1h] BYREF
  __int64 v29; // [rsp+50h] [rbp+7h] BYREF
  Windows::Networking::UX *v30; // [rsp+58h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v28 = 0;
  v30 = this;
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, a2, a3);
  v5 = WcmProvisioningUtil::PrepareStreamFromString(
         (WcmProvisioningUtil *)&v30,
         (const struct Windows::Internal::StringReference *)&v29,
         v4);
  v8 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    goto LABEL_15;
  }
  pProxy = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy, v6, v7);
  Instance = CoCreateInstance(
               &CLSID_ProvisioningEngine,
               0,
               4u,
               &GUID_217700e0_1001_11df_adb9_f4ce462d9137,
               (LPVOID *)&pProxy);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v12 = 65;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy, v13, v14);
    goto LABEL_15;
  }
  Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x40u);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v12 = 77;
    goto LABEL_5;
  }
  v17 = pProxy;
  QueryInterface = pProxy->lpVtbl[1].QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v15, v16);
  Instance = ((__int64 (__fastcall *)(IUnknown *, __int64, IUnknown **))QueryInterface)(v17, v29, &v28);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v12 = 79;
    goto LABEL_5;
  }
  Instance = CoSetProxyBlanket(v28, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x40u);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v12 = 88;
    goto LABEL_5;
  }
  v21 = v28;
  if ( v28 )
  {
    ((void (__fastcall *)(IUnknown *))v28->lpVtbl->AddRef)(v28);
    v21 = v28;
  }
  *a2 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy, v19, v20);
  v8 = 0;
LABEL_15:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29, v9, v10);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v22, v23);
  return v8;
}

```

## disassembly

```asm
0x18002a4dc  push    rbp
0x18002a4de  push    rbx
0x18002a4df  push    rsi
0x18002a4e0  push    rdi
0x18002a4e1  lea     rbp, [rsp-3Fh]
0x18002a4e6  sub     rsp, 88h
0x18002a4ed  mov     rax, cs:__security_cookie
0x18002a4f4  xor     rax, rsp
0x18002a4f7  mov     [rbp+57h+var_28], rax
0x18002a4fb  mov     rsi, rdx
0x18002a4fe  mov     [rbp+57h+var_58], 0
0x18002a506  mov     [rbp+57h+var_48], rcx
0x18002a50a  mov     [rbp+57h+var_50], 0
0x18002a512  lea     rcx, [rbp+57h+var_50]
0x18002a516  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a51b  lea     rdx, [rbp+57h+var_50]; struct Windows::Internal::StringReference *
0x18002a51f  lea     rcx, [rbp+57h+var_48]; this
0x18002a523  call    ?PrepareStreamFromString@WcmProvisioningUtil@@YAJAEBVStringReference@Internal@Windows@@PEAPEAUIStream@@@Z; WcmProvisioningUtil::PrepareStreamFromString(Windows::Internal::StringReference const &,IStream * *)
0x18002a528  mov     ebx, eax
0x18002a52a  test    eax, eax
0x18002a52c  jns     short loc_18002A54B
0x18002a52e  mov     rcx, [rbp+5Fh]; this
0x18002a532  mov     r9d, eax; char *
0x18002a535  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a53c  mov     edx, 3Dh ; '='; void *
0x18002a541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a546  jmp     loc_18002A691
0x18002a54b  mov     [rbp+57h+pProxy], 0
0x18002a553  lea     rcx, [rbp+57h+pProxy]
0x18002a557  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a55c  lea     rax, [rbp+57h+pProxy]
0x18002a560  mov     [rsp+0A0h+ppv], rax; int
0x18002a565  lea     r9, _GUID_217700e0_1001_11df_adb9_f4ce462d9137; riid
0x18002a56c  xor     edx, edx; pUnkOuter
0x18002a56e  lea     r8d, [rdx+4]; dwClsContext
0x18002a572  lea     rcx, CLSID_ProvisioningEngine; rclsid
0x18002a579  call    cs:__imp_CoCreateInstance
0x18002a57f  mov     ebx, eax
0x18002a581  test    eax, eax
0x18002a583  jns     short loc_18002A5AC
0x18002a585  mov     edx, 41h ; 'A'; void *
0x18002a58a  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002a591  mov     r9d, eax; char *
0x18002a594  mov     rcx, [rbp+5Fh]; this
0x18002a598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a59d  nop
0x18002a59e  lea     rcx, [rbp+57h+pProxy]
0x18002a5a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a5a7  jmp     loc_18002A691
0x18002a5ac  mov     [rsp+0A0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002a5b4  mov     [rsp+0A0h+pAuthInfo], 0; pAuthInfo
0x18002a5bd  mov     [rsp+0A0h+dwImpLevel], 4; dwImpLevel
0x18002a5c5  mov     dword ptr [rsp+0A0h+ppv], 0; dwAuthnLevel
0x18002a5cd  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18002a5d1  xor     r8d, r8d; dwAuthzSvc
0x18002a5d4  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18002a5d7  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18002a5db  call    cs:__imp_CoSetProxyBlanket
0x18002a5e1  mov     ebx, eax
0x18002a5e3  test    eax, eax
0x18002a5e5  jns     short loc_18002A5EE
0x18002a5e7  mov     edx, 4Dh ; 'M'
0x18002a5ec  jmp     short loc_18002A58A
0x18002a5ee  mov     rdi, [rbp+57h+pProxy]
0x18002a5f2  mov     rax, [rdi]
0x18002a5f5  mov     rbx, [rax+18h]
0x18002a5f9  lea     rcx, [rbp+57h+var_58]
0x18002a5fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a602  lea     r8, [rbp+57h+var_58]
0x18002a606  mov     rdx, [rbp+57h+var_50]
0x18002a60a  mov     rcx, rdi
0x18002a60d  mov     rax, rbx
0x18002a610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a615  mov     ebx, eax
0x18002a617  test    eax, eax
0x18002a619  jns     short loc_18002A625
0x18002a61b  mov     edx, 4Fh ; 'O'
0x18002a620  jmp     loc_18002A58A
0x18002a625  mov     [rsp+0A0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002a62d  mov     [rsp+0A0h+pAuthInfo], 0; pAuthInfo
0x18002a636  mov     [rsp+0A0h+dwImpLevel], 4; dwImpLevel
0x18002a63e  mov     dword ptr [rsp+0A0h+ppv], 0; dwAuthnLevel
0x18002a646  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18002a64a  xor     r8d, r8d; dwAuthzSvc
0x18002a64d  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18002a650  mov     rcx, [rbp+57h+var_58]; pProxy
0x18002a654  call    cs:__imp_CoSetProxyBlanket
0x18002a65a  mov     ebx, eax
0x18002a65c  test    eax, eax
0x18002a65e  jns     short loc_18002A66A
0x18002a660  mov     edx, 58h ; 'X'
0x18002a665  jmp     loc_18002A58A
0x18002a66a  mov     rcx, [rbp+57h+var_58]
0x18002a66e  test    rcx, rcx
0x18002a671  jz      short loc_18002A683
0x18002a673  mov     rax, [rcx]
0x18002a676  mov     rax, [rax+8]
0x18002a67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a67f  mov     rcx, [rbp+57h+var_58]
0x18002a683  mov     [rsi], rcx
0x18002a686  lea     rcx, [rbp+57h+pProxy]
0x18002a68a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a68f  xor     ebx, ebx
0x18002a691  lea     rcx, [rbp+57h+var_50]
0x18002a695  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a69a  nop
0x18002a69b  lea     rcx, [rbp+57h+var_58]
0x18002a69f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a6a4  mov     eax, ebx
0x18002a6a6  mov     rcx, [rbp+57h+var_28]
0x18002a6aa  xor     rcx, rsp; StackCookie
0x18002a6ad  call    __security_check_cookie
0x18002a6b2  add     rsp, 88h
0x18002a6b9  pop     rdi
0x18002a6ba  pop     rsi
0x18002a6bb  pop     rbx
0x18002a6bc  pop     rbp
0x18002a6bd  retn
```
