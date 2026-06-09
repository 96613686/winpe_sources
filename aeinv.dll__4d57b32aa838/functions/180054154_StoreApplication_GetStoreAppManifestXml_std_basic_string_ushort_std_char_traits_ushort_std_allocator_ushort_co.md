# StoreApplication::GetStoreAppManifestXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180054154`
- end: `0x180054514`
- name: `?GetStoreAppManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z`
- size: `960`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061a00`
- `0x1800fc498`

## callees

- `0x18000a39c`
- `0x180025340`
- `0x180054154`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800541a7`
- `ole32!CoCreateInstance` at `0x18005425f`
- `ole32!CoCreateInstance` at `0x180054383`
- `ole32!CoCreateInstance` at `0x1800541a7`
- `ole32!CoCreateInstance` at `0x18005425f`
- `ole32!CoCreateInstance` at `0x180054383`

## string_xrefs

- `0x1800541b8`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18005421f`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180054270`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800542b8`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180054326`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180054394`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800543dc`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180054426`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18005446a`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall StoreApplication::GetStoreAppManifestXml(__int64 a1, _QWORD *a2, char a3)
{
  HRESULT v6; // eax
  LPVOID v7; // rbx
  __int64 (__fastcall *v8)(LPVOID, _QWORD *, __int64); // rdi
  _QWORD *v9; // rdx
  int v10; // eax
  HRESULT v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, __int64, _QWORD); // rbx
  int v14; // eax
  void (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v16)(_QWORD, GUID *, LPVOID *); // rdi
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, __int64 *); // rbx
  int v19; // eax
  LPVOID v20; // rcx
  HRESULT v21; // eax
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, __int64, _QWORD); // rbx
  int v24; // eax
  void (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, LPVOID *); // rbx
  int v27; // eax
  LPVOID v28; // rdi
  __int64 (__fastcall *v29)(LPVOID, __int64 *); // rbx
  int v30; // eax
  LPVOID v31; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int ppvb; // [rsp+20h] [rbp-60h]
  __int64 v36; // [rsp+48h] [rbp-38h] BYREF
  LPVOID v37; // [rsp+50h] [rbp-30h] BYREF
  void (__fastcall ***v38)(_QWORD, GUID *, LPVOID *); // [rsp+58h] [rbp-28h] BYREF
  LPVOID v39; // [rsp+60h] [rbp-20h] BYREF
  LPVOID v40; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v41[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v43; // [rsp+C8h] [rbp+48h] BYREF

  v41[1] = -2;
  v40 = 0;
  v6 = CoCreateInstance(
         &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
         0,
         1u,
         &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
         &v40);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x63F,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v36 = 0;
  v7 = v40;
  v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64))(*(_QWORD *)v40 + 40LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v36);
  if ( a2[3] <= 7u )
    v9 = a2;
  else
    v9 = (_QWORD *)*a2;
  v10 = v8(v7, v9, 1);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      128);
  v43 = 0;
  if ( a3 )
  {
    v39 = 0;
    v11 = CoCreateInstance(
            &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
            0,
            1u,
            &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
            &v39);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x650,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v11,
        ppva);
    v38 = 0;
    v12 = v39;
    v13 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v39 + 40LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v38);
    v14 = v13(v12, v36, &v38);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x653,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v14,
        ppva);
    v37 = 0;
    v15 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
    v16 = **v38;
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v37);
    v16(v15, &GUID_c0fc0853_18d7_43e8_afca_414a07af67a2, &v37);
    v17 = v37;
    v18 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v37 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v43);
    v19 = v18(v17, &v43);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x657,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v19,
        ppva);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v38);
    v20 = v39;
    if ( v39 )
    {
      v39 = 0;
LABEL_27:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  else
  {
    v37 = 0;
    v21 = CoCreateInstance(
            &GUID_378e0446_5384_43b7_8877_e7dbdd883446,
            0,
            1u,
            &GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b,
            &v37);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x65F,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v21,
        ppvb);
    v38 = 0;
    v22 = v37;
    v23 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v37 + 40LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v38);
    v24 = v23(v22, v36, &v38);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x662,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v24,
        ppvb);
    v39 = 0;
    v25 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
    v26 = (__int64 (__fastcall *)(_QWORD, GUID *, LPVOID *))**v38;
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v39);
    v27 = v26(v25, &GUID_c0fc0853_18d7_43e8_afca_414a07af67a2, &v39);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x665,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v27,
        ppvb);
    v41[0] = 0;
    v28 = v39;
    v29 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v39 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v43);
    v30 = v29(v28, &v43);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x668,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v30,
        ppvb);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(v41);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v38);
    v20 = v37;
    if ( v37 )
    {
      v37 = 0;
      goto LABEL_27;
    }
  }
  StoreApplication::TransformAndLocalizeManifestXml(a1, &v43, (__int64)a2, a3);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v36);
  v31 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return a1;
}

```

## disassembly

```asm
0x180054154  mov     rax, rsp
0x180054157  push    rbp
0x180054158  push    rdi
0x180054159  push    r12
0x18005415b  push    r14
0x18005415d  push    r15
0x18005415f  mov     rbp, rsp
0x180054162  sub     rsp, 80h
0x180054169  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180054171  mov     [rax+8], rbx
0x180054175  mov     [rax+10h], rsi
0x180054179  mov     r15b, r8b
0x18005417c  mov     rsi, rdx
0x18005417f  mov     r14, rcx
0x180054182  xor     r12d, r12d
0x180054185  mov     [rbp+var_18], r12
0x180054189  lea     rax, [rbp+var_18]
0x18005418d  mov     [rsp+80h+ppv], rax; int
0x180054192  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x180054199  xor     edx, edx; pUnkOuter
0x18005419b  lea     r8d, [r12+1]; dwClsContext
0x1800541a0  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x1800541a7  call    cs:__imp_CoCreateInstance
0x1800541ad  mov     rcx, [rbp+28h]; this
0x1800541b1  test    eax, eax
0x1800541b3  jns     short loc_1800541CA
0x1800541b5  mov     r9d, eax; char *
0x1800541b8  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800541bf  mov     edx, 63Fh; void *
0x1800541c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800541ca  mov     [rbp+var_38], r12
0x1800541ce  mov     rbx, [rbp+var_18]
0x1800541d2  mov     rax, [rbx]
0x1800541d5  mov     rdi, [rax+28h]
0x1800541d9  lea     rcx, [rbp+var_38]
0x1800541dd  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800541e2  cmp     qword ptr [rsi+18h], 7
0x1800541e7  jbe     short loc_1800541EE
0x1800541e9  mov     rdx, [rsi]
0x1800541ec  jmp     short loc_1800541F1
0x1800541ee  mov     rdx, rsi
0x1800541f1  lea     rax, [rbp+var_38]
0x1800541f5  mov     [rsp+80h+var_58], rax
0x1800541fa  mov     dword ptr [rsp+80h+ppv], 80h; int
0x180054202  xor     r9d, r9d
0x180054205  lea     r8d, [r9+1]
0x180054209  mov     rcx, rbx
0x18005420c  mov     rax, rdi
0x18005420f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054214  mov     rcx, [rbp+28h]; this
0x180054218  test    eax, eax
0x18005421a  jns     short loc_180054231
0x18005421c  mov     r9d, eax; char *
0x18005421f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180054226  mov     edx, 646h; void *
0x18005422b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180054231  mov     [rbp+arg_18], r12
0x180054235  test    r15b, r15b
0x180054238  jz      loc_180054362
0x18005423e  mov     [rbp+var_20], r12
0x180054242  lea     rax, [rbp+var_20]
0x180054246  mov     [rsp+80h+ppv], rax; int
0x18005424b  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x180054252  xor     edx, edx; pUnkOuter
0x180054254  lea     r8d, [rdx+1]; dwClsContext
0x180054258  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x18005425f  call    cs:__imp_CoCreateInstance
0x180054265  mov     rcx, [rbp+28h]; this
0x180054269  test    eax, eax
0x18005426b  jns     short loc_180054282
0x18005426d  mov     r9d, eax; char *
0x180054270  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180054277  mov     edx, 650h; void *
0x18005427c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180054282  mov     [rbp+var_28], r12
0x180054286  mov     rdi, [rbp+var_20]
0x18005428a  mov     rax, [rdi]
0x18005428d  mov     rbx, [rax+28h]
0x180054291  lea     rcx, [rbp+var_28]
0x180054295  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18005429a  lea     r8, [rbp+var_28]
0x18005429e  mov     rdx, [rbp+var_38]
0x1800542a2  mov     rcx, rdi
0x1800542a5  mov     rax, rbx
0x1800542a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542ad  mov     rcx, [rbp+28h]; this
0x1800542b1  test    eax, eax
0x1800542b3  jns     short loc_1800542CA
0x1800542b5  mov     r9d, eax; char *
0x1800542b8  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800542bf  mov     edx, 653h; void *
0x1800542c4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800542ca  mov     [rbp+var_30], r12
0x1800542ce  mov     rbx, [rbp+var_28]
0x1800542d2  mov     rax, [rbx]
0x1800542d5  mov     rdi, [rax]
0x1800542d8  lea     rcx, [rbp+var_30]
0x1800542dc  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800542e1  lea     r8, [rbp+var_30]
0x1800542e5  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x1800542ec  mov     rcx, rbx
0x1800542ef  mov     rax, rdi
0x1800542f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542f7  nop
0x1800542f8  mov     rdi, [rbp+var_30]
0x1800542fc  mov     rax, [rdi]
0x1800542ff  mov     rbx, [rax+18h]
0x180054303  lea     rcx, [rbp+arg_18]
0x180054307  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18005430c  lea     rdx, [rbp+arg_18]
0x180054310  mov     rcx, rdi
0x180054313  mov     rax, rbx
0x180054316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005431b  mov     rcx, [rbp+28h]; this
0x18005431f  test    eax, eax
0x180054321  jns     short loc_180054338
0x180054323  mov     r9d, eax; char *
0x180054326  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18005432d  mov     edx, 657h; void *
0x180054332  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180054338  lea     rcx, [rbp+var_30]
0x18005433c  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180054341  nop
0x180054342  lea     rcx, [rbp+var_28]
0x180054346  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18005434b  nop
0x18005434c  mov     rcx, [rbp+var_20]
0x180054350  test    rcx, rcx
0x180054353  jz      loc_1800544B4
0x180054359  mov     [rbp+var_20], r12
0x18005435d  jmp     loc_1800544A7
0x180054362  mov     [rbp+var_30], r12
0x180054366  lea     rax, [rbp+var_30]
0x18005436a  mov     [rsp+80h+ppv], rax; int
0x18005436f  lea     r9, _GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b; riid
0x180054376  xor     edx, edx; pUnkOuter
0x180054378  lea     r8d, [rdx+1]; dwClsContext
0x18005437c  lea     rcx, _GUID_378e0446_5384_43b7_8877_e7dbdd883446; rclsid
0x180054383  call    cs:__imp_CoCreateInstance
0x180054389  mov     rcx, [rbp+28h]; this
0x18005438d  test    eax, eax
0x18005438f  jns     short loc_1800543A6
0x180054391  mov     r9d, eax; char *
0x180054394  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18005439b  mov     edx, 65Fh; void *
0x1800543a0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800543a6  mov     [rbp+var_28], r12
0x1800543aa  mov     rdi, [rbp+var_30]
0x1800543ae  mov     rax, [rdi]
0x1800543b1  mov     rbx, [rax+28h]
0x1800543b5  lea     rcx, [rbp+var_28]
0x1800543b9  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800543be  lea     r8, [rbp+var_28]
0x1800543c2  mov     rdx, [rbp+var_38]
0x1800543c6  mov     rcx, rdi
0x1800543c9  mov     rax, rbx
0x1800543cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800543d1  mov     rcx, [rbp+28h]; this
0x1800543d5  test    eax, eax
0x1800543d7  jns     short loc_1800543EE
0x1800543d9  mov     r9d, eax; char *
0x1800543dc  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800543e3  mov     edx, 662h; void *
0x1800543e8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800543ee  mov     [rbp+var_20], r12
0x1800543f2  mov     rdi, [rbp+var_28]
0x1800543f6  mov     rax, [rdi]
0x1800543f9  mov     rbx, [rax]
0x1800543fc  lea     rcx, [rbp+var_20]
0x180054400  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180054405  lea     r8, [rbp+var_20]
0x180054409  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x180054410  mov     rcx, rdi
0x180054413  mov     rax, rbx
0x180054416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005441b  mov     rcx, [rbp+28h]; this
0x18005441f  test    eax, eax
0x180054421  jns     short loc_180054438
0x180054423  mov     r9d, eax; char *
0x180054426  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18005442d  mov     edx, 665h; void *
0x180054432  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180054438  mov     [rbp+var_10], r12
0x18005443c  mov     rdi, [rbp+var_20]
0x180054440  mov     rax, [rdi]
0x180054443  mov     rbx, [rax+18h]
0x180054447  lea     rcx, [rbp+arg_18]
0x18005444b  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180054450  lea     rdx, [rbp+arg_18]
0x180054454  mov     rcx, rdi
0x180054457  mov     rax, rbx
0x18005445a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005445f  mov     rcx, [rbp+28h]; this
0x180054463  test    eax, eax
0x180054465  jns     short loc_18005447C
0x180054467  mov     r9d, eax; char *
0x18005446a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180054471  mov     edx, 668h; void *
0x180054476  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18005447c  lea     rcx, [rbp+var_10]
0x180054480  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180054485  nop
0x180054486  lea     rcx, [rbp+var_20]
0x18005448a  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18005448f  nop
0x180054490  lea     rcx, [rbp+var_28]
0x180054494  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180054499  nop
0x18005449a  mov     rcx, [rbp+var_30]
0x18005449e  test    rcx, rcx
0x1800544a1  jz      short loc_1800544B4
0x1800544a3  mov     [rbp+var_30], r12
0x1800544a7  mov     rax, [rcx]
0x1800544aa  mov     rax, [rax+10h]
0x1800544ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544b3  nop
0x1800544b4  mov     r9b, r15b
0x1800544b7  mov     r8, rsi
0x1800544ba  lea     rdx, [rbp+arg_18]
0x1800544be  mov     rcx, r14
0x1800544c1  call    ?TransformAndLocalizeManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV23@_N@Z; StoreApplication::TransformAndLocalizeManifestXml(Microsoft::WRL::ComPtr<IXMLDOMDocument> const &,std::wstring const &,bool)
0x1800544c6  nop
0x1800544c7  lea     rcx, [rbp+arg_18]
0x1800544cb  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800544d0  nop
0x1800544d1  lea     rcx, [rbp+var_38]
0x1800544d5  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800544da  nop
0x1800544db  mov     rcx, [rbp+var_18]
0x1800544df  test    rcx, rcx
0x1800544e2  jz      short loc_1800544F5
0x1800544e4  mov     [rbp+var_18], r12
0x1800544e8  mov     rax, [rcx]
0x1800544eb  mov     rax, [rax+10h]
0x1800544ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544f4  nop
0x1800544f5  mov     rax, r14
0x1800544f8  lea     r11, [rsp+80h+var_s0]
0x180054500  mov     rbx, [r11+30h]
0x180054504  mov     rsi, [r11+38h]
0x180054508  mov     rsp, r11
0x18005450b  pop     r15
0x18005450d  pop     r14
0x18005450f  pop     r12
0x180054511  pop     rdi
0x180054512  pop     rbp
0x180054513  retn
```
