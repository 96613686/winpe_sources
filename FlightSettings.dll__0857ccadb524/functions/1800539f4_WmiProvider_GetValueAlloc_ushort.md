# WmiProvider::GetValueAlloc(ushort * *)

- ea: `0x1800539f4`
- end: `0x180053dd9`
- name: `?GetValueAlloc@WmiProvider@@QEAAJPEAPEAG@Z`
- size: `997`
- prototype: `__int64 __fastcall(WmiProvider *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049d30`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x1800539f4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053a45`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053a45`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180053ae3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180053bbe`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180053ae3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180053bbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053c99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053c99`
- `OLEAUT32!__imp_VariantInit` at `0x180053c81`
- `OLEAUT32!__imp_VariantInit` at `0x180053c81`
- `OLEAUT32!__imp_VariantClear` at `0x180053ce1`
- `OLEAUT32!__imp_VariantClear` at `0x180053d8b`
- `OLEAUT32!__imp_VariantClear` at `0x180053ce1`
- `OLEAUT32!__imp_VariantClear` at `0x180053d8b`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180053d0f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180053d0f`

## string_xrefs

- `0x180053a58`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180053af6`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180053b6a`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180053c1c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180053cc9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`
- `0x180053d4b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\wmiprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WmiProvider::GetValueAlloc(WmiProvider *this, unsigned __int16 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rdi
  void (__fastcall *v7)(LPVOID, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // rbx
  HRESULT v8; // eax
  IUnknown *v9; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  HRESULT v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  IUnknown *v14; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PCWSTR, _QWORD, VARIANTARG *); // rbx
  PCWSTR StringRawBuffer; // rax
  HRESULT v22; // eax
  __int64 v23; // rdx
  int v24; // eax
  unsigned __int16 *v25; // rax
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  int ppvb; // [rsp+20h] [rbp-49h]
  int ppvc; // [rsp+20h] [rbp-49h]
  IUnknown *v31; // [rsp+50h] [rbp-19h] BYREF
  __int64 v32; // [rsp+58h] [rbp-11h] BYREF
  LPVOID v33; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-1h] BYREF
  __int64 v35; // [rsp+70h] [rbp+7h]
  __int64 v36; // [rsp+78h] [rbp+Fh]
  VARIANTARG pvarg; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v39; // [rsp+E0h] [rbp+77h] BYREF
  IUnknown *pProxy; // [rsp+E8h] [rbp+7Fh] BYREF

  v33 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v4 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &v33);
  v5 = v4;
  if ( v4 >= 0 )
  {
    pProxy = 0;
    v6 = v33;
    v7 = *(void (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)v33 + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
    v7(v6, *((_QWORD *)this + 3), 0, 0, 0, 0, 0, 0, &pProxy);
    v8 = CoSetProxyBlanket(
           pProxy,
           0xFFFFFFFF,
           0xFFFFFFFF,
           (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
           0,
           3u,
           (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
           0x800u);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
        (const char *)(unsigned int)v8,
        ppva);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
      goto LABEL_33;
    }
    v31 = 0;
    v9 = pProxy;
    Release = pProxy->lpVtbl[6].Release;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    ppvb = 0;
    v11 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, __int64))Release)(
            v9,
            *((_QWORD *)this + 4),
            *((_QWORD *)this + 2),
            48);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = 131;
LABEL_8:
      v13 = (unsigned int)v11;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
        (const char *)v13,
        ppvb);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      goto LABEL_5;
    }
    if ( !v31 )
    {
      v5 = -2147418113;
      v13 = 2147549183LL;
      v12 = 132;
      goto LABEL_9;
    }
    v11 = CoSetProxyBlanket(
            v31,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            0,
            3u,
            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
            0x800u);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = 143;
      goto LABEL_8;
    }
    v32 = 0;
    v39 = 0;
    v14 = v31;
    AddRef = v31->lpVtbl[1].AddRef;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    v16 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, __int64 *))AddRef)(
            v14,
            *((unsigned int *)this + 12),
            1,
            &v32);
    v5 = v16;
    if ( v16 < 0 )
    {
      v17 = (unsigned int)v16;
      v18 = 153;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
        (const char *)v17,
        (int)&v39);
LABEL_18:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      goto LABEL_10;
    }
    if ( !v39 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
      v5 = -2147020590;
      goto LABEL_33;
    }
    if ( !v32 )
    {
      v5 = -2147418113;
      v17 = 2147549183LL;
      v18 = 161;
      goto LABEL_17;
    }
    VariantInit(&pvarg);
    v19 = v32;
    v20 = *(__int64 (__fastcall **)(__int64, PCWSTR, _QWORD, VARIANTARG *))(*(_QWORD *)v32 + 32LL);
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 5), 0);
    ppvc = 0;
    v22 = v20(v19, StringRawBuffer, 0, &pvarg);
    v5 = v22;
    if ( v22 >= 0 )
    {
      if ( pvarg.vt == 8
        || (v22 = VariantChangeTypeEx(&pvarg, &pvarg, 0x400u, *((_WORD *)this + 26), 8u), v5 = v22, v22 >= 0) )
      {
        v34 = 0;
        v35 = 0;
        v36 = 0;
        v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v34,
                pvarg.llVal,
                -1);
        v5 = v24;
        if ( v24 >= 0 )
        {
          v25 = v34;
          v34 = 0;
          v36 = 0;
          v35 = 0;
          *a2 = v25;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v34);
          VariantClear(&pvarg);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
          v5 = 0;
          goto LABEL_33;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
          (const char *)(unsigned int)v24,
          ppvc);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v34);
        goto LABEL_26;
      }
      v23 = 171;
    }
    else
    {
      v23 = 166;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
      (const char *)(unsigned int)v22,
      ppvc);
LABEL_26:
    VariantClear(&pvarg);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\wmiprovider.cpp",
    (const char *)(unsigned int)v4,
    ppv);
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  return v5;
}

```

## disassembly

```asm
0x1800539f4  mov     [rsp-8+arg_0], rbx
0x1800539f9  mov     [rsp-8+arg_8], rsi
0x1800539fe  push    rbp
0x1800539ff  push    rdi
0x180053a00  push    r12
0x180053a02  push    r14
0x180053a04  push    r15
0x180053a06  lea     rbp, [rsp-37h]
0x180053a0b  sub     rsp, 0A0h
0x180053a12  mov     r14, rdx
0x180053a15  mov     rsi, rcx
0x180053a18  xor     r15d, r15d
0x180053a1b  mov     [rbp+57h+var_60], r15
0x180053a1f  lea     rcx, [rbp+57h+var_60]
0x180053a23  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053a28  lea     rax, [rbp+57h+var_60]
0x180053a2c  mov     [rsp+0C0h+ppv], rax; int
0x180053a31  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x180053a38  xor     edx, edx; pUnkOuter
0x180053a3a  lea     r8d, [r15+1]; dwClsContext
0x180053a3e  lea     rcx, CLSID_WbemLocator; rclsid
0x180053a45  call    cs:__imp_CoCreateInstance
0x180053a4b  mov     ebx, eax
0x180053a4d  test    eax, eax
0x180053a4f  jns     short loc_180053A6D
0x180053a51  mov     rcx, [rbp+5Fh]; this
0x180053a55  mov     r9d, eax; char *
0x180053a58  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053a5f  lea     edx, [r15+63h]; void *
0x180053a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053a68  jmp     loc_180053DB2
0x180053a6d  mov     [rbp+57h+pProxy], r15
0x180053a71  mov     rdi, [rbp+57h+var_60]
0x180053a75  mov     rax, [rdi]
0x180053a78  mov     rbx, [rax+18h]
0x180053a7c  lea     rcx, [rbp+57h+pProxy]
0x180053a80  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053a85  lea     rax, [rbp+57h+pProxy]
0x180053a89  mov     [rsp+0C0h+var_80], rax
0x180053a8e  mov     qword ptr [rsp+0C0h+dwCapabilities], r15
0x180053a93  mov     [rsp+0C0h+pAuthInfo], r15
0x180053a98  mov     [rsp+0C0h+dwImpLevel], r15d
0x180053a9d  mov     [rsp+0C0h+ppv], r15
0x180053aa2  xor     r9d, r9d
0x180053aa5  xor     r8d, r8d
0x180053aa8  mov     rdx, [rsi+18h]
0x180053aac  mov     rcx, rdi
0x180053aaf  mov     rax, rbx
0x180053ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ab7  mov     [rsp+0C0h+dwCapabilities], 800h; dwCapabilities
0x180053abf  or      r12, 0FFFFFFFFFFFFFFFFh
0x180053ac3  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x180053ac8  mov     [rsp+0C0h+dwImpLevel], 3; dwImpLevel
0x180053ad0  mov     dword ptr [rsp+0C0h+ppv], r15d; int
0x180053ad5  mov     r9, r12; pServerPrincName
0x180053ad8  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180053adc  or      edx, r8d; dwAuthnSvc
0x180053adf  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180053ae3  call    cs:__imp_CoSetProxyBlanket
0x180053ae9  mov     ebx, eax
0x180053aeb  test    eax, eax
0x180053aed  jns     short loc_180053B16
0x180053aef  mov     rcx, [rbp+5Fh]; this
0x180053af3  mov     r9d, eax; char *
0x180053af6  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053afd  lea     edx, [r12+7Bh]; void *
0x180053b02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053b07  nop
0x180053b08  lea     rcx, [rbp+57h+pProxy]
0x180053b0c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053b11  jmp     loc_180053DB2
0x180053b16  mov     [rbp+57h+var_70], r15
0x180053b1a  mov     rdi, [rbp+57h+pProxy]
0x180053b1e  mov     rax, [rdi]
0x180053b21  mov     rbx, [rax+0A0h]
0x180053b28  lea     rcx, [rbp+57h+var_70]
0x180053b2c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053b31  lea     rax, [rbp+57h+var_70]
0x180053b35  mov     qword ptr [rsp+0C0h+dwImpLevel], rax
0x180053b3a  mov     [rsp+0C0h+ppv], r15; int
0x180053b3f  mov     r9d, 30h ; '0'
0x180053b45  mov     r8, [rsi+10h]
0x180053b49  mov     rdx, [rsi+20h]
0x180053b4d  mov     rcx, rdi
0x180053b50  mov     rax, rbx
0x180053b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b58  mov     ebx, eax
0x180053b5a  test    eax, eax
0x180053b5c  jns     short loc_180053B82
0x180053b5e  mov     edx, 83h; void *
0x180053b63  mov     r9d, eax; char *
0x180053b66  mov     rcx, [rbp+5Fh]; this
0x180053b6a  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053b76  nop
0x180053b77  lea     rcx, [rbp+57h+var_70]
0x180053b7b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053b80  jmp     short loc_180053B08
0x180053b82  mov     rcx, [rbp+57h+var_70]; pProxy
0x180053b86  test    rcx, rcx
0x180053b89  jnz     short loc_180053B9A
0x180053b8b  mov     ebx, 8000FFFFh
0x180053b90  mov     r9d, ebx
0x180053b93  mov     edx, 84h
0x180053b98  jmp     short loc_180053B66
0x180053b9a  mov     [rsp+0C0h+dwCapabilities], 800h; dwCapabilities
0x180053ba2  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x180053ba7  mov     [rsp+0C0h+dwImpLevel], 3; dwImpLevel
0x180053baf  mov     dword ptr [rsp+0C0h+ppv], r15d; dwAuthnLevel
0x180053bb4  mov     r9, r12; pServerPrincName
0x180053bb7  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x180053bbb  or      edx, r8d; dwAuthnSvc
0x180053bbe  call    cs:__imp_CoSetProxyBlanket
0x180053bc4  mov     ebx, eax
0x180053bc6  test    eax, eax
0x180053bc8  jns     short loc_180053BD1
0x180053bca  mov     edx, 8Fh
0x180053bcf  jmp     short loc_180053B63
0x180053bd1  mov     [rbp+57h+var_68], r15
0x180053bd5  mov     [rbp+57h+arg_10], r15d
0x180053bd9  mov     rdi, [rbp+57h+var_70]
0x180053bdd  mov     rax, [rdi]
0x180053be0  mov     rbx, [rax+20h]
0x180053be4  lea     rcx, [rbp+57h+var_68]
0x180053be8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053bed  lea     rax, [rbp+57h+arg_10]
0x180053bf1  mov     [rsp+0C0h+ppv], rax; int
0x180053bf6  lea     r9, [rbp+57h+var_68]
0x180053bfa  mov     r8d, 1
0x180053c00  mov     edx, [rsi+30h]
0x180053c03  mov     rcx, rdi
0x180053c06  mov     rax, rbx
0x180053c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c0e  mov     ebx, eax
0x180053c10  test    eax, eax
0x180053c12  jns     short loc_180053C3B
0x180053c14  mov     r9d, eax; char *
0x180053c17  mov     edx, 99h; void *
0x180053c1c  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053c23  mov     rcx, [rbp+5Fh]; this
0x180053c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053c2c  nop
0x180053c2d  lea     rcx, [rbp+57h+var_68]
0x180053c31  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053c36  jmp     loc_180053B77
0x180053c3b  cmp     [rbp+57h+arg_10], r15d
0x180053c3f  jnz     short loc_180053C68
0x180053c41  lea     rcx, [rbp+57h+var_68]
0x180053c45  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053c4a  nop
0x180053c4b  lea     rcx, [rbp+57h+var_70]
0x180053c4f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053c54  nop
0x180053c55  lea     rcx, [rbp+57h+pProxy]
0x180053c59  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053c5e  mov     ebx, 800710D2h
0x180053c63  jmp     loc_180053DB2
0x180053c68  cmp     [rbp+57h+var_68], r15
0x180053c6c  jnz     short loc_180053C7D
0x180053c6e  mov     ebx, 8000FFFFh
0x180053c73  mov     r9d, ebx
0x180053c76  mov     edx, 0A1h
0x180053c7b  jmp     short loc_180053C1C
0x180053c7d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180053c81  call    cs:__imp_VariantInit
0x180053c87  nop
0x180053c88  mov     rdi, [rbp+57h+var_68]
0x180053c8c  mov     rax, [rdi]
0x180053c8f  mov     rbx, [rax+20h]
0x180053c93  xor     edx, edx; length
0x180053c95  mov     rcx, [rsi+28h]; string
0x180053c99  call    cs:__imp_WindowsGetStringRawBuffer
0x180053c9f  mov     qword ptr [rsp+0C0h+dwImpLevel], r15
0x180053ca4  mov     [rsp+0C0h+ppv], r15; int
0x180053ca9  lea     r9, [rbp+57h+pvarg]
0x180053cad  xor     r8d, r8d
0x180053cb0  mov     rdx, rax
0x180053cb3  mov     rcx, rdi
0x180053cb6  mov     rax, rbx
0x180053cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cbe  mov     ebx, eax
0x180053cc0  test    eax, eax
0x180053cc2  jns     short loc_180053CEC
0x180053cc4  mov     edx, 0A6h; void *
0x180053cc9  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053cd0  mov     r9d, eax; char *
0x180053cd3  mov     rcx, [rbp+5Fh]; this
0x180053cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053cdc  nop
0x180053cdd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180053ce1  call    cs:__imp_VariantClear
0x180053ce7  jmp     loc_180053C2D
0x180053cec  mov     eax, 8
0x180053cf1  cmp     ax, word ptr [rbp+57h+pvarg]
0x180053cf5  jz      short loc_180053D22
0x180053cf7  mov     word ptr [rsp+0C0h+ppv], ax; vt
0x180053cfc  movzx   r9d, word ptr [rsi+34h]; wFlags
0x180053d01  mov     r8d, 400h; lcid
0x180053d07  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x180053d0b  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x180053d0f  call    cs:__imp_VariantChangeTypeEx
0x180053d15  mov     ebx, eax
0x180053d17  test    eax, eax
0x180053d19  jns     short loc_180053D22
0x180053d1b  mov     edx, 0ABh
0x180053d20  jmp     short loc_180053CC9
0x180053d22  mov     [rbp+57h+var_58], r15
0x180053d26  mov     [rbp+57h+var_50], r15
0x180053d2a  mov     [rbp+57h+var_48], r15
0x180053d2e  mov     r8, r12
0x180053d31  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180053d35  lea     rcx, [rbp+57h+var_58]
0x180053d39  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180053d3e  mov     ebx, eax
0x180053d40  test    eax, eax
0x180053d42  jns     short loc_180053D6A
0x180053d44  mov     rcx, [rbp+5Fh]; this
0x180053d48  mov     r9d, eax; char *
0x180053d4b  lea     r8, aOnecoreBaseFli_43; "onecore\\base\\flighting\\flightsetting"...
0x180053d52  mov     edx, 0B0h; void *
0x180053d57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053d5c  lea     rcx, [rbp+57h+var_58]
0x180053d60  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053d65  jmp     loc_180053CDD
0x180053d6a  mov     rax, [rbp+57h+var_58]
0x180053d6e  mov     [rbp+57h+var_58], r15
0x180053d72  mov     [rbp+57h+var_48], r15
0x180053d76  mov     [rbp+57h+var_50], r15
0x180053d7a  mov     [r14], rax
0x180053d7d  lea     rcx, [rbp+57h+var_58]
0x180053d81  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053d86  nop
0x180053d87  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180053d8b  call    cs:__imp_VariantClear
0x180053d91  nop
0x180053d92  lea     rcx, [rbp+57h+var_68]
0x180053d96  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053d9b  nop
0x180053d9c  lea     rcx, [rbp+57h+var_70]
0x180053da0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053da5  nop
0x180053da6  lea     rcx, [rbp+57h+pProxy]
0x180053daa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053daf  mov     ebx, r15d
0x180053db2  lea     rcx, [rbp+57h+var_60]
0x180053db6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053dbb  mov     eax, ebx
0x180053dbd  lea     r11, [rsp+0C0h+var_20]
0x180053dc5  mov     rbx, [r11+30h]
0x180053dc9  mov     rsi, [r11+38h]
0x180053dcd  mov     rsp, r11
0x180053dd0  pop     r15
0x180053dd2  pop     r14
0x180053dd4  pop     r12
0x180053dd6  pop     rdi
0x180053dd7  pop     rbp
0x180053dd8  retn
```
