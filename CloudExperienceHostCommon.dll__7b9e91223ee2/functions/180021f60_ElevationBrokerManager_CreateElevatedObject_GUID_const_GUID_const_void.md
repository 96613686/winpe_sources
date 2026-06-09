# ElevationBrokerManager::CreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180021f60`
- end: `0x18002217d`
- name: `?CreateElevatedObject@ElevationBrokerManager@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `541`
- prototype: `__int64 __fastcall(ElevationBrokerManager *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000fa5c`
- `0x1800153f8`
- `0x180021f00`
- `0x180021f60`
- `0x180022338`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180022061`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180022061`

## string_xrefs

- `0x180021fbd`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`
- `0x180022017`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`
- `0x1800220ea`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\elevatedbrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ElevationBrokerManager::CreateElevatedObject(
        ElevationBrokerManager *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct IUnknown *v7; // r8
  unsigned int v8; // r9d
  int InstanceWithFallbackClsid; // eax
  unsigned int v10; // ebx
  const struct _GUID *v11; // rcx
  HRESULT SystemObjectServer; // eax
  __int64 v13; // rdx
  struct IUnknown *v14; // r8
  unsigned int v15; // r9d
  int v16; // eax
  __int64 v17; // rdx
  int dwAuthnLevel; // [rsp+20h] [rbp-40h]
  int dwAuthnLevela; // [rsp+20h] [rbp-40h]
  IUnknown *pProxy; // [rsp+40h] [rbp-20h] BYREF
  void *v22; // [rsp+48h] [rbp-18h] BYREF
  void *v23[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v23[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
  InstanceWithFallbackClsid = CoCreateInstanceWithFallbackClsid(
                                &GUID_4cd0569b_0239_4602_84a3_cfc5a9167c82,
                                &GUID_baffdff4_240b_4c36_8173_70c8301d7753,
                                v7,
                                v8,
                                &GUID_06d48c99_bab0_4e6e_ae56_358cec845441,
                                v23);
  v10 = InstanceWithFallbackClsid;
  if ( InstanceWithFallbackClsid >= 0 )
  {
    pProxy = 0;
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v23[0] + 24LL))(v23[0]) )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
      SystemObjectServer = GetCreateSystemObjectServer(v11, (void **)&pProxy);
      v10 = SystemObjectServer;
      if ( SystemObjectServer < 0 )
      {
        v13 = 118;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
          (const char *)(unsigned int)SystemObjectServer,
          dwAuthnLevel);
LABEL_7:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
        goto LABEL_21;
      }
      SystemObjectServer = CoSetProxyBlanket(
                             pProxy,
                             0xFFFFFFFF,
                             0xFFFFFFFF,
                             (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                             0,
                             4u,
                             0,
                             0x40u);
      v10 = SystemObjectServer;
      if ( SystemObjectServer < 0 )
      {
        v13 = 125;
        goto LABEL_6;
      }
      dwAuthnLevel = (int)a4;
      SystemObjectServer = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *, _QWORD, const struct _GUID *))pProxy->lpVtbl[1].QueryInterface)(
                             pProxy,
                             a2,
                             0,
                             a3);
      v10 = SystemObjectServer;
      if ( SystemObjectServer < 0 )
      {
        v13 = 126;
        goto LABEL_6;
      }
LABEL_20:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
      v10 = 0;
      goto LABEL_21;
    }
    v22 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    v16 = CoCreateInstanceWithFallbackClsid(
            &GUID_fe0bfe76_18b7_4ea4_a9ca_7277eef48747,
            &GUID_4b77066b_8a60_4162_9456_1b1e994eaf77,
            v14,
            v15,
            &GUID_10316cc3_d36e_46cd_8344_d85f12419862,
            &v22);
    v10 = v16;
    if ( v16 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(void *, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v22 + 24LL))(
              v22,
              a2,
              a3,
              a4);
      v10 = v16;
      if ( v16 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        goto LABEL_20;
      }
      if ( v16 == -2147024891 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
        v10 = -2147024891;
        goto LABEL_21;
      }
      v17 = 132;
    }
    else
    {
      v17 = 131;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
      (const char *)(unsigned int)v16,
      dwAuthnLevela);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\elevatedbrokermanager.cpp",
    (const char *)(unsigned int)InstanceWithFallbackClsid,
    dwAuthnLevel);
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
  return v10;
}

```

## disassembly

```asm
0x180021f60  push    rbp
0x180021f62  push    rbx
0x180021f63  push    rsi
0x180021f64  push    rdi
0x180021f65  push    r14
0x180021f67  mov     rbp, rsp
0x180021f6a  sub     rsp, 60h
0x180021f6e  mov     rdi, r9
0x180021f71  mov     rsi, r8
0x180021f74  mov     r14, rdx
0x180021f77  mov     [rbp+var_10], 0
0x180021f7f  lea     rcx, [rbp+var_10]
0x180021f83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021f88  lea     rax, [rbp+var_10]
0x180021f8c  mov     qword ptr [rsp+60h+dwImpLevel], rax; void **
0x180021f91  lea     rax, _GUID_06d48c99_bab0_4e6e_ae56_358cec845441
0x180021f98  mov     qword ptr [rsp+60h+dwAuthnLevel], rax; int
0x180021f9d  lea     rdx, _GUID_baffdff4_240b_4c36_8173_70c8301d7753; struct _GUID *
0x180021fa4  lea     rcx, _GUID_4cd0569b_0239_4602_84a3_cfc5a9167c82; struct _GUID *
0x180021fab  call    ?CoCreateInstanceWithFallbackClsid@@YAJAEBU_GUID@@0PEAUIUnknown@@K0PEAPEAX@Z; CoCreateInstanceWithFallbackClsid(_GUID const &,_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180021fb0  mov     ebx, eax
0x180021fb2  test    eax, eax
0x180021fb4  jns     short loc_180021FD3
0x180021fb6  mov     rcx, [rbp+28h]; this
0x180021fba  mov     r9d, eax; char *
0x180021fbd  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x180021fc4  mov     edx, 72h ; 'r'; void *
0x180021fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021fce  jmp     loc_180022167
0x180021fd3  mov     [rbp+pProxy], 0
0x180021fdb  mov     rcx, [rbp+var_10]
0x180021fdf  mov     rax, [rcx]
0x180021fe2  mov     rax, [rax+18h]
0x180021fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021feb  test    eax, eax
0x180021fed  jnz     loc_1800220A6
0x180021ff3  lea     rcx, [rbp+pProxy]
0x180021ff7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021ffc  lea     rdx, [rbp+pProxy]; void **
0x180022000  call    ?GetCreateSystemObjectServer@@YAJAEBU_GUID@@PEAPEAX@Z; GetCreateSystemObjectServer(_GUID const &,void * *)
0x180022005  mov     ebx, eax
0x180022007  test    eax, eax
0x180022009  jns     short loc_180022032
0x18002200b  mov     edx, 76h ; 'v'; void *
0x180022010  mov     rcx, [rbp+28h]; this
0x180022014  mov     r9d, eax; char *
0x180022017  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x18002201e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022023  nop
0x180022024  lea     rcx, [rbp+pProxy]
0x180022028  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002202d  jmp     loc_180022167
0x180022032  mov     [rsp+60h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002203a  mov     [rsp+60h+pAuthInfo], 0; pAuthInfo
0x180022043  mov     [rsp+60h+dwImpLevel], 4; dwImpLevel
0x18002204b  mov     [rsp+60h+dwAuthnLevel], 0; dwAuthnLevel
0x180022053  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180022057  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18002205a  mov     r8d, edx; dwAuthzSvc
0x18002205d  mov     rcx, [rbp+pProxy]; pProxy
0x180022061  call    cs:__imp_CoSetProxyBlanket
0x180022067  mov     ebx, eax
0x180022069  test    eax, eax
0x18002206b  jns     short loc_180022074
0x18002206d  mov     edx, 7Dh ; '}'
0x180022072  jmp     short loc_180022010
0x180022074  mov     rcx, [rbp+pProxy]
0x180022078  mov     rax, [rcx]
0x18002207b  mov     qword ptr [rsp+60h+dwAuthnLevel], rdi
0x180022080  mov     r9, rsi
0x180022083  xor     r8d, r8d
0x180022086  mov     rdx, r14
0x180022089  mov     rax, [rax+18h]
0x18002208d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022092  mov     ebx, eax
0x180022094  test    eax, eax
0x180022096  jns     loc_18002215C
0x18002209c  mov     edx, 7Eh ; '~'
0x1800220a1  jmp     loc_180022010
0x1800220a6  mov     [rbp+var_18], 0
0x1800220ae  lea     rcx, [rbp+var_18]
0x1800220b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800220b7  lea     rax, [rbp+var_18]
0x1800220bb  mov     qword ptr [rsp+60h+dwImpLevel], rax; void **
0x1800220c0  lea     rax, _GUID_10316cc3_d36e_46cd_8344_d85f12419862
0x1800220c7  mov     qword ptr [rsp+60h+dwAuthnLevel], rax; int
0x1800220cc  lea     rdx, _GUID_4b77066b_8a60_4162_9456_1b1e994eaf77; struct _GUID *
0x1800220d3  lea     rcx, _GUID_fe0bfe76_18b7_4ea4_a9ca_7277eef48747; struct _GUID *
0x1800220da  call    ?CoCreateInstanceWithFallbackClsid@@YAJAEBU_GUID@@0PEAUIUnknown@@K0PEAPEAX@Z; CoCreateInstanceWithFallbackClsid(_GUID const &,_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800220df  mov     ebx, eax
0x1800220e1  test    eax, eax
0x1800220e3  jns     short loc_18002210C
0x1800220e5  mov     edx, 83h; void *
0x1800220ea  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800220f1  mov     r9d, eax; char *
0x1800220f4  mov     rcx, [rbp+28h]; this
0x1800220f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220fd  nop
0x1800220fe  lea     rcx, [rbp+var_18]
0x180022102  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022107  jmp     loc_180022024
0x18002210c  mov     rcx, [rbp+var_18]
0x180022110  mov     rax, [rcx]
0x180022113  mov     r9, rdi
0x180022116  mov     r8, rsi
0x180022119  mov     rdx, r14
0x18002211c  mov     rax, [rax+18h]
0x180022120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022125  mov     ebx, eax
0x180022127  test    eax, eax
0x180022129  jns     short loc_180022152
0x18002212b  mov     edi, 80070005h
0x180022130  cmp     eax, edi
0x180022132  jnz     short loc_18002214B
0x180022134  lea     rcx, [rbp+var_18]
0x180022138  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002213d  nop
0x18002213e  lea     rcx, [rbp+pProxy]
0x180022142  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022147  mov     ebx, edi
0x180022149  jmp     short loc_180022167
0x18002214b  mov     edx, 84h
0x180022150  jmp     short loc_1800220EA
0x180022152  lea     rcx, [rbp+var_18]
0x180022156  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002215b  nop
0x18002215c  lea     rcx, [rbp+pProxy]
0x180022160  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022165  xor     ebx, ebx
0x180022167  lea     rcx, [rbp+var_10]
0x18002216b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022170  mov     eax, ebx
0x180022172  add     rsp, 60h
0x180022176  pop     r14
0x180022178  pop     rdi
0x180022179  pop     rsi
0x18002217a  pop     rbx
0x18002217b  pop     rbp
0x18002217c  retn
```
