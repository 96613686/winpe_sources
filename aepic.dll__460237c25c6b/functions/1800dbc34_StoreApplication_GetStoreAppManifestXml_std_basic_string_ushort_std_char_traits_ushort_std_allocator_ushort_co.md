# StoreApplication::GetStoreAppManifestXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800dbc34`
- end: `0x1800dbfeb`
- name: `?GetStoreAppManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dc88c`

## callees

- `0x18000a2d4`
- `0x1800c97f0`
- `0x1800dbc34`
- `0x1800decb8`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbc7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbd36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbe5a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbc7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbd36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dbe5a`

## string_xrefs

- `0x1800dbc8f`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbcf6`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbd47`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbd8f`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbdfd`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbe6b`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbeb3`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbefd`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dbf41`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
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
  __int64 v20; // r9
  LPVOID v21; // rcx
  HRESULT v22; // eax
  LPVOID v23; // rdi
  __int64 (__fastcall *v24)(LPVOID, __int64, _QWORD); // rbx
  int v25; // eax
  void (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, LPVOID *); // rbx
  int v28; // eax
  LPVOID v29; // rdi
  __int64 (__fastcall *v30)(LPVOID, __int64 *); // rbx
  int v31; // eax
  LPVOID v32; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int ppvb; // [rsp+20h] [rbp-60h]
  __int64 v37; // [rsp+48h] [rbp-38h] BYREF
  LPVOID v38; // [rsp+50h] [rbp-30h] BYREF
  void (__fastcall ***v39)(_QWORD, GUID *, LPVOID *); // [rsp+58h] [rbp-28h] BYREF
  LPVOID v40; // [rsp+60h] [rbp-20h] BYREF
  LPVOID v41; // [rsp+68h] [rbp-18h] BYREF
  __int64 v42; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v44; // [rsp+C8h] [rbp+48h] BYREF

  v41 = 0;
  v6 = CoCreateInstance(
         &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
         0,
         1u,
         &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
         &v41);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x63F,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v37 = 0;
  v7 = v41;
  v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64))(*(_QWORD *)v41 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  if ( a2[3] <= 7u )
    v9 = a2;
  else
    v9 = (_QWORD *)*a2;
  v10 = v8(v7, v9, 1);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      128);
  v44 = 0;
  if ( a3 )
  {
    v40 = 0;
    v11 = CoCreateInstance(
            &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
            0,
            1u,
            &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
            &v40);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x650,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v11,
        ppva);
    v39 = 0;
    v12 = v40;
    v13 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v40 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v14 = v13(v12, v37, &v39);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x653,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v14,
        ppva);
    v38 = 0;
    v15 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v39;
    v16 = **v39;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v16(v15, &GUID_c0fc0853_18d7_43e8_afca_414a07af67a2, &v38);
    v17 = v38;
    v18 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v38 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v19 = v18(v17, &v44);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x657,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v19,
        ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v21 = v40;
    if ( v40 )
    {
      v40 = 0;
LABEL_27:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  else
  {
    v38 = 0;
    v22 = CoCreateInstance(
            &GUID_378e0446_5384_43b7_8877_e7dbdd883446,
            0,
            1u,
            &GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b,
            &v38);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x65F,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v22,
        ppvb);
    v39 = 0;
    v23 = v38;
    v24 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v38 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v25 = v24(v23, v37, &v39);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x662,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v25,
        ppvb);
    v40 = 0;
    v26 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v39;
    v27 = (__int64 (__fastcall *)(_QWORD, GUID *, LPVOID *))**v39;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    v28 = v27(v26, &GUID_c0fc0853_18d7_43e8_afca_414a07af67a2, &v40);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x665,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v28,
        ppvb);
    v42 = 0;
    v29 = v40;
    v30 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v40 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v31 = v30(v29, &v44);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x668,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v31,
        ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v21 = v38;
    if ( v38 )
    {
      v38 = 0;
      goto LABEL_27;
    }
  }
  LOBYTE(v20) = a3;
  StoreApplication::TransformAndLocalizeManifestXml(a1, &v44, a2, v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v32 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return a1;
}

```

## disassembly

```asm
0x1800dbc34  mov     [rsp-28h+arg_0], rbx
0x1800dbc39  mov     [rsp-28h+arg_8], rsi
0x1800dbc3e  push    rbp
0x1800dbc3f  push    rdi
0x1800dbc40  push    r12
0x1800dbc42  push    r14
0x1800dbc44  push    r15
0x1800dbc46  mov     rbp, rsp
0x1800dbc49  sub     rsp, 80h
0x1800dbc50  mov     r15b, r8b
0x1800dbc53  mov     rsi, rdx
0x1800dbc56  mov     r14, rcx
0x1800dbc59  xor     r12d, r12d
0x1800dbc5c  mov     [rbp+var_18], r12
0x1800dbc60  lea     rax, [rbp+var_18]
0x1800dbc64  mov     [rsp+80h+ppv], rax; int
0x1800dbc69  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x1800dbc70  xor     edx, edx; pUnkOuter
0x1800dbc72  lea     r8d, [r12+1]; dwClsContext
0x1800dbc77  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x1800dbc7e  call    cs:__imp_CoCreateInstance
0x1800dbc84  mov     rcx, [rbp+28h]; this
0x1800dbc88  test    eax, eax
0x1800dbc8a  jns     short loc_1800DBCA1
0x1800dbc8c  mov     r9d, eax; char *
0x1800dbc8f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbc96  mov     edx, 63Fh; void *
0x1800dbc9b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbca1  mov     [rbp+var_38], r12
0x1800dbca5  mov     rbx, [rbp+var_18]
0x1800dbca9  mov     rax, [rbx]
0x1800dbcac  mov     rdi, [rax+28h]
0x1800dbcb0  lea     rcx, [rbp+var_38]
0x1800dbcb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbcb9  cmp     qword ptr [rsi+18h], 7
0x1800dbcbe  jbe     short loc_1800DBCC5
0x1800dbcc0  mov     rdx, [rsi]
0x1800dbcc3  jmp     short loc_1800DBCC8
0x1800dbcc5  mov     rdx, rsi
0x1800dbcc8  lea     rax, [rbp+var_38]
0x1800dbccc  mov     [rsp+80h+var_58], rax
0x1800dbcd1  mov     dword ptr [rsp+80h+ppv], 80h; int
0x1800dbcd9  xor     r9d, r9d
0x1800dbcdc  lea     r8d, [r9+1]
0x1800dbce0  mov     rcx, rbx
0x1800dbce3  mov     rax, rdi
0x1800dbce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbceb  mov     rcx, [rbp+28h]; this
0x1800dbcef  test    eax, eax
0x1800dbcf1  jns     short loc_1800DBD08
0x1800dbcf3  mov     r9d, eax; char *
0x1800dbcf6  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbcfd  mov     edx, 646h; void *
0x1800dbd02  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbd08  mov     [rbp+arg_18], r12
0x1800dbd0c  test    r15b, r15b
0x1800dbd0f  jz      loc_1800DBE39
0x1800dbd15  mov     [rbp+var_20], r12
0x1800dbd19  lea     rax, [rbp+var_20]
0x1800dbd1d  mov     [rsp+80h+ppv], rax; int
0x1800dbd22  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x1800dbd29  xor     edx, edx; pUnkOuter
0x1800dbd2b  lea     r8d, [rdx+1]; dwClsContext
0x1800dbd2f  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800dbd36  call    cs:__imp_CoCreateInstance
0x1800dbd3c  mov     rcx, [rbp+28h]; this
0x1800dbd40  test    eax, eax
0x1800dbd42  jns     short loc_1800DBD59
0x1800dbd44  mov     r9d, eax; char *
0x1800dbd47  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbd4e  mov     edx, 650h; void *
0x1800dbd53  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbd59  mov     [rbp+var_28], r12
0x1800dbd5d  mov     rdi, [rbp+var_20]
0x1800dbd61  mov     rax, [rdi]
0x1800dbd64  mov     rbx, [rax+28h]
0x1800dbd68  lea     rcx, [rbp+var_28]
0x1800dbd6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbd71  lea     r8, [rbp+var_28]
0x1800dbd75  mov     rdx, [rbp+var_38]
0x1800dbd79  mov     rcx, rdi
0x1800dbd7c  mov     rax, rbx
0x1800dbd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbd84  mov     rcx, [rbp+28h]; this
0x1800dbd88  test    eax, eax
0x1800dbd8a  jns     short loc_1800DBDA1
0x1800dbd8c  mov     r9d, eax; char *
0x1800dbd8f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbd96  mov     edx, 653h; void *
0x1800dbd9b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbda1  mov     [rbp+var_30], r12
0x1800dbda5  mov     rbx, [rbp+var_28]
0x1800dbda9  mov     rax, [rbx]
0x1800dbdac  mov     rdi, [rax]
0x1800dbdaf  lea     rcx, [rbp+var_30]
0x1800dbdb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbdb8  lea     r8, [rbp+var_30]
0x1800dbdbc  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x1800dbdc3  mov     rcx, rbx
0x1800dbdc6  mov     rax, rdi
0x1800dbdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbdce  nop
0x1800dbdcf  mov     rdi, [rbp+var_30]
0x1800dbdd3  mov     rax, [rdi]
0x1800dbdd6  mov     rbx, [rax+18h]
0x1800dbdda  lea     rcx, [rbp+arg_18]
0x1800dbdde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbde3  lea     rdx, [rbp+arg_18]
0x1800dbde7  mov     rcx, rdi
0x1800dbdea  mov     rax, rbx
0x1800dbded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbdf2  mov     rcx, [rbp+28h]; this
0x1800dbdf6  test    eax, eax
0x1800dbdf8  jns     short loc_1800DBE0F
0x1800dbdfa  mov     r9d, eax; char *
0x1800dbdfd  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbe04  mov     edx, 657h; void *
0x1800dbe09  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbe0f  lea     rcx, [rbp+var_30]
0x1800dbe13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbe18  nop
0x1800dbe19  lea     rcx, [rbp+var_28]
0x1800dbe1d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbe22  nop
0x1800dbe23  mov     rcx, [rbp+var_20]
0x1800dbe27  test    rcx, rcx
0x1800dbe2a  jz      loc_1800DBF8B
0x1800dbe30  mov     [rbp+var_20], r12
0x1800dbe34  jmp     loc_1800DBF7E
0x1800dbe39  mov     [rbp+var_30], r12
0x1800dbe3d  lea     rax, [rbp+var_30]
0x1800dbe41  mov     [rsp+80h+ppv], rax; int
0x1800dbe46  lea     r9, _GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b; riid
0x1800dbe4d  xor     edx, edx; pUnkOuter
0x1800dbe4f  lea     r8d, [rdx+1]; dwClsContext
0x1800dbe53  lea     rcx, _GUID_378e0446_5384_43b7_8877_e7dbdd883446; rclsid
0x1800dbe5a  call    cs:__imp_CoCreateInstance
0x1800dbe60  mov     rcx, [rbp+28h]; this
0x1800dbe64  test    eax, eax
0x1800dbe66  jns     short loc_1800DBE7D
0x1800dbe68  mov     r9d, eax; char *
0x1800dbe6b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbe72  mov     edx, 65Fh; void *
0x1800dbe77  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbe7d  mov     [rbp+var_28], r12
0x1800dbe81  mov     rdi, [rbp+var_30]
0x1800dbe85  mov     rax, [rdi]
0x1800dbe88  mov     rbx, [rax+28h]
0x1800dbe8c  lea     rcx, [rbp+var_28]
0x1800dbe90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbe95  lea     r8, [rbp+var_28]
0x1800dbe99  mov     rdx, [rbp+var_38]
0x1800dbe9d  mov     rcx, rdi
0x1800dbea0  mov     rax, rbx
0x1800dbea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbea8  mov     rcx, [rbp+28h]; this
0x1800dbeac  test    eax, eax
0x1800dbeae  jns     short loc_1800DBEC5
0x1800dbeb0  mov     r9d, eax; char *
0x1800dbeb3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbeba  mov     edx, 662h; void *
0x1800dbebf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbec5  mov     [rbp+var_20], r12
0x1800dbec9  mov     rdi, [rbp+var_28]
0x1800dbecd  mov     rax, [rdi]
0x1800dbed0  mov     rbx, [rax]
0x1800dbed3  lea     rcx, [rbp+var_20]
0x1800dbed7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbedc  lea     r8, [rbp+var_20]
0x1800dbee0  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x1800dbee7  mov     rcx, rdi
0x1800dbeea  mov     rax, rbx
0x1800dbeed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbef2  mov     rcx, [rbp+28h]; this
0x1800dbef6  test    eax, eax
0x1800dbef8  jns     short loc_1800DBF0F
0x1800dbefa  mov     r9d, eax; char *
0x1800dbefd  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbf04  mov     edx, 665h; void *
0x1800dbf09  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbf0f  mov     [rbp+var_10], r12
0x1800dbf13  mov     rdi, [rbp+var_20]
0x1800dbf17  mov     rax, [rdi]
0x1800dbf1a  mov     rbx, [rax+18h]
0x1800dbf1e  lea     rcx, [rbp+arg_18]
0x1800dbf22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbf27  lea     rdx, [rbp+arg_18]
0x1800dbf2b  mov     rcx, rdi
0x1800dbf2e  mov     rax, rbx
0x1800dbf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf36  mov     rcx, [rbp+28h]; this
0x1800dbf3a  test    eax, eax
0x1800dbf3c  jns     short loc_1800DBF53
0x1800dbf3e  mov     r9d, eax; char *
0x1800dbf41  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dbf48  mov     edx, 668h; void *
0x1800dbf4d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dbf53  lea     rcx, [rbp+var_10]
0x1800dbf57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbf5c  nop
0x1800dbf5d  lea     rcx, [rbp+var_20]
0x1800dbf61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbf66  nop
0x1800dbf67  lea     rcx, [rbp+var_28]
0x1800dbf6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbf70  nop
0x1800dbf71  mov     rcx, [rbp+var_30]
0x1800dbf75  test    rcx, rcx
0x1800dbf78  jz      short loc_1800DBF8B
0x1800dbf7a  mov     [rbp+var_30], r12
0x1800dbf7e  mov     rax, [rcx]
0x1800dbf81  mov     rax, [rax+10h]
0x1800dbf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf8a  nop
0x1800dbf8b  mov     r9b, r15b
0x1800dbf8e  mov     r8, rsi
0x1800dbf91  lea     rdx, [rbp+arg_18]
0x1800dbf95  mov     rcx, r14
0x1800dbf98  call    ?TransformAndLocalizeManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV23@_N@Z; StoreApplication::TransformAndLocalizeManifestXml(Microsoft::WRL::ComPtr<IXMLDOMDocument> const &,std::wstring const &,bool)
0x1800dbf9d  nop
0x1800dbf9e  lea     rcx, [rbp+arg_18]
0x1800dbfa2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbfa7  nop
0x1800dbfa8  lea     rcx, [rbp+var_38]
0x1800dbfac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dbfb1  nop
0x1800dbfb2  mov     rcx, [rbp+var_18]
0x1800dbfb6  test    rcx, rcx
0x1800dbfb9  jz      short loc_1800DBFCC
0x1800dbfbb  mov     [rbp+var_18], r12
0x1800dbfbf  mov     rax, [rcx]
0x1800dbfc2  mov     rax, [rax+10h]
0x1800dbfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfcb  nop
0x1800dbfcc  mov     rax, r14
0x1800dbfcf  lea     r11, [rsp+80h+var_s0]
0x1800dbfd7  mov     rbx, [r11+30h]
0x1800dbfdb  mov     rsi, [r11+38h]
0x1800dbfdf  mov     rsp, r11
0x1800dbfe2  pop     r15
0x1800dbfe4  pop     r14
0x1800dbfe6  pop     r12
0x1800dbfe8  pop     rdi
0x1800dbfe9  pop     rbp
0x1800dbfea  retn
```
