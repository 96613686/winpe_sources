# WlanSyncTaskCommon::UploadSignaturesToCloudForNetwork(wil::cloud_store &,INetworkPrivate *)

- ea: `0x180015624`
- end: `0x180015aa0`
- name: `?UploadSignaturesToCloudForNetwork@WlanSyncTaskCommon@@SAIAEAVcloud_store@wil@@PEAUINetworkPrivate@@@Z`
- size: `1148`
- prototype: `unsigned int __fastcall(struct wil::cloud_store *, struct INetworkPrivate *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800144c0`
- `0x180014d70`

## callees

- `0x180006b88`
- `0x180006d7c`
- `0x180007f90`
- `0x180015624`
- `0x1800168c4`
- `0x1800169bc`
- `0x1800169e0`
- `0x1800202e8`
- `0x180025308`
- `0x18002a030`
- `0x18002e2d0`
- `0x18002eecc`
- `0x18002f000`
- `0x18002f938`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800158a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001599c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800158a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001599c`
- `OLEAUT32!__imp_VariantInit` at `0x1800156eb`
- `OLEAUT32!__imp_VariantInit` at `0x1800156eb`
- `OLEAUT32!__imp_VariantClear` at `0x180015a07`
- `OLEAUT32!__imp_VariantClear` at `0x180015a65`
- `OLEAUT32!__imp_VariantClear` at `0x180015a07`
- `OLEAUT32!__imp_VariantClear` at `0x180015a65`

## string_xrefs

- `0x180015689`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x1800156d5`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x18001571f`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x18001576d`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x1800157db`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x1800159aa`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x180015a31`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WlanSyncTaskCommon::UploadSignaturesToCloudForNetwork(
        struct wil::cloud_store *a1,
        struct INetworkPrivate *a2)
{
  unsigned int v4; // esi
  int v5; // eax
  __int64 (__fastcall *v6)(struct INetworkPrivate *, GUID *, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  char *v10; // r8
  char *v11; // rdx
  __int64 (__fastcall *v12)(struct INetworkPrivate *, __int64, __int64 *); // rbx
  int v13; // eax
  __m128i si128; // xmm6
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD **, int *); // rbx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  void *v20; // rcx
  void **v21; // rdx
  void **v22; // rax
  void *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v28; // [rsp+20h] [rbp-E0h]
  char v29; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[3]; // [rsp+41h] [rbp-BFh] BYREF
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD *v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+70h] [rbp-90h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp-88h]
  void *v40; // [rsp+80h] [rbp-80h] BYREF
  char v41; // [rsp+88h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  void **v43; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v44[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-40h] BYREF
  char v46; // [rsp+C8h] [rbp-38h]
  _BYTE v47[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v48; // [rsp+E8h] [rbp-18h] BYREF
  void *v49[2]; // [rsp+F8h] [rbp-8h] BYREF
  __m128i v50; // [rsp+108h] [rbp+8h]
  _BYTE v51[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v52[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v4 = 0;
  v34 = 0;
  v48 = 0;
  v5 = (*(__int64 (__fastcall **)(struct INetworkPrivate *, __int128 *))(*(_QWORD *)a2 + 48LL))(a2, &v48);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v5,
      v28);
  v32 = 0;
  v6 = **(__int64 (__fastcall ***)(struct INetworkPrivate *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  v7 = v6(a2, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &v32);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v7,
      v28);
  VariantInit(&pvarg);
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v32 + 24LL))(
         v32,
         L"NA_NetworkClass",
         &pvarg,
         0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v8,
      v28);
  if ( pvarg.vt != 23 || pvarg.lVal != 2 )
  {
    v30[0] = 0;
    v29 = 0;
    v10 = v30;
    v11 = &v29;
    goto LABEL_43;
  }
  v31 = 0;
  v9 = (*(__int64 (__fastcall **)(struct INetworkPrivate *, unsigned int *))(*(_QWORD *)a2 + 104LL))(a2, &v31);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v9,
      v28);
  if ( v31 > 1 )
  {
    v29 = 1;
    v30[0] = 1;
    v10 = &v29;
    v11 = v30;
LABEL_43:
    WiFiCloudStoreTelemetry::NlmSkippingNetwork<_GUID &,bool,bool>(&v48, v11, v10);
    VariantClear(&pvarg);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    return 0;
  }
  v36 = 0;
  v12 = *(__int64 (__fastcall **)(struct INetworkPrivate *, __int64, __int64 *))(*(_QWORD *)a2 + 128LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  v13 = v12(a2, 3, &v36);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v13,
      v28);
  v35 = 0;
  v38 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v15 = v36;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **, int *))(*(_QWORD *)v36 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v17 = v16(v15, 1, &v35, &v38);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        (const char *)(unsigned int)v17,
        v28);
    if ( v17 )
      break;
    pv = 0;
    v33 = 0;
    v18 = *v35;
    p_pv = &pv;
    v40 = 0;
    v41 = 1;
    v19 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, void **))(v18 + 24))(v35, &v33, &v40);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        (const char *)(unsigned int)v19,
        v28);
    if ( v41 )
    {
      v20 = *p_pv;
      *p_pv = v40;
      if ( v20 )
        CoTaskMemFree(v20);
    }
    NetworkSignatureToCDSReferenceId(v49, pv, v33);
    v21 = v49;
    if ( v50.m128i_i64[1] > 7uLL )
      v21 = (void **)v49[0];
    wil::make_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(
      (__int64)v51,
      (__int64)v21,
      (__int64)c_wiFiCloudStoreDataReferenceDefaultCollectionName);
    wil::cloud_store::load<Windows::Data::Nlm::NlmSignature>((__int64)a1, (__int64)v44, (__int64)v51, 2);
    if ( v46 || v44[0] != v31 )
    {
      v44[0] = (int)v31;
      wil::cloud_store::save<Windows::Data::Nlm::NlmSignature>((int)a1, (__int64)v47, (int)v44, (int)v51);
      v34 = ++v4;
      v22 = v49;
      if ( v50.m128i_i64[1] > 7uLL )
        v22 = (void **)v49[0];
      v43 = v22;
      WiFiCloudStoreTelemetry::SignatureUploadedForNetwork<_GUID &,unsigned short const *>(&v48, &v43);
    }
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v45);
    std::wstring::~wstring((__int64)v52);
    std::wstring::~wstring((__int64)v51);
    if ( v50.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v49[0], 2 * v50.m128i_i64[1] + 2);
    v50 = si128;
    LOWORD(v49[0]) = 0;
    v23 = pv;
    pv = 0;
    if ( v23 )
      CoTaskMemFree(v23);
  }
  WiFiCloudStoreTelemetry::TotalSignaturesUploadedToCloudForNetwork<_GUID &,unsigned int &>(&v48, &v34);
  v24 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
  v25 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  VariantClear(&pvarg);
  v26 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return v4;
}

```

## disassembly

```asm
0x180015624  mov     rax, rsp
0x180015627  mov     [rax+18h], rbx
0x18001562b  push    rbp
0x18001562c  push    rsi
0x18001562d  push    rdi
0x18001562e  push    r14
0x180015630  push    r15
0x180015632  lea     rbp, [rsp-80h]
0x180015637  sub     rsp, 180h
0x18001563e  movaps  xmmword ptr [rax-38h], xmm6
0x180015642  mov     rax, cs:__security_cookie
0x180015649  xor     rax, rsp
0x18001564c  mov     [rbp+0A0h+var_40], rax
0x180015650  mov     rdi, rdx
0x180015653  mov     r14, rcx
0x180015656  xor     r15d, r15d
0x180015659  mov     esi, r15d
0x18001565c  mov     [rsp+1A0h+var_14C], r15d
0x180015661  xorps   xmm0, xmm0
0x180015664  movups  [rbp+0A0h+var_B8], xmm0
0x180015668  mov     rax, [rdx]
0x18001566b  lea     rdx, [rbp+0A0h+var_B8]
0x18001566f  mov     rcx, rdi
0x180015672  mov     rax, [rax+30h]
0x180015676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001567b  mov     rcx, [rbp+0A8h]; this
0x180015682  test    eax, eax
0x180015684  jns     short loc_18001569B
0x180015686  mov     r9d, eax; char *
0x180015689  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180015690  mov     edx, 125h; void *
0x180015695  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001569b  mov     [rsp+1A0h+var_158], r15
0x1800156a0  mov     rax, [rdi]
0x1800156a3  mov     rbx, [rax]
0x1800156a6  lea     rcx, [rsp+1A0h+var_158]
0x1800156ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800156b0  lea     r8, [rsp+1A0h+var_158]
0x1800156b5  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800156bc  mov     rcx, rdi
0x1800156bf  mov     rax, rbx
0x1800156c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c7  mov     rcx, [rbp+0A8h]; this
0x1800156ce  test    eax, eax
0x1800156d0  jns     short loc_1800156E7
0x1800156d2  mov     r9d, eax; char *
0x1800156d5  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800156dc  mov     edx, 128h; void *
0x1800156e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800156e7  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x1800156eb  call    cs:__imp_VariantInit
0x1800156f1  nop
0x1800156f2  mov     rcx, [rsp+1A0h+var_158]
0x1800156f7  mov     rax, [rcx]
0x1800156fa  xor     r9d, r9d
0x1800156fd  lea     r8, [rbp+0A0h+pvarg]
0x180015701  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x180015708  mov     rax, [rax+18h]
0x18001570c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015711  mov     rcx, [rbp+0A8h]; this
0x180015718  test    eax, eax
0x18001571a  jns     short loc_180015731
0x18001571c  mov     r9d, eax; char *
0x18001571f  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180015726  mov     edx, 12Ah; void *
0x18001572b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015731  cmp     word ptr [rbp+0A0h+pvarg], 17h
0x180015736  jnz     loc_180015A43
0x18001573c  cmp     dword ptr [rbp+0A0h+pvarg+8], 2
0x180015740  jnz     loc_180015A43
0x180015746  mov     [rsp+1A0h+var_15C], r15d
0x18001574b  mov     rax, [rdi]
0x18001574e  lea     rdx, [rsp+1A0h+var_15C]
0x180015753  mov     rcx, rdi
0x180015756  mov     rax, [rax+68h]
0x18001575a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001575f  mov     rcx, [rbp+0A8h]; this
0x180015766  test    eax, eax
0x180015768  jns     short loc_18001577F
0x18001576a  mov     r9d, eax; char *
0x18001576d  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180015774  mov     edx, 133h; void *
0x180015779  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001577f  cmp     [rsp+1A0h+var_15C], 1
0x180015784  jbe     short loc_18001579F
0x180015786  mov     [rsp+1A0h+var_160], 1
0x18001578b  mov     [rsp+1A0h+var_15F], 1
0x180015790  lea     r8, [rsp+1A0h+var_160]
0x180015795  lea     rdx, [rsp+1A0h+var_15F]
0x18001579a  jmp     loc_180015A57
0x18001579f  mov     [rsp+1A0h+var_140], r15
0x1800157a4  mov     rax, [rdi]
0x1800157a7  mov     rbx, [rax+80h]
0x1800157ae  lea     rcx, [rsp+1A0h+var_140]
0x1800157b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800157b8  lea     r8, [rsp+1A0h+var_140]
0x1800157bd  mov     edx, 3
0x1800157c2  mov     rcx, rdi
0x1800157c5  mov     rax, rbx
0x1800157c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157cd  mov     rcx, [rbp+0A8h]; this
0x1800157d4  test    eax, eax
0x1800157d6  jns     short loc_1800157ED
0x1800157d8  mov     r9d, eax; char *
0x1800157db  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800157e2  mov     edx, 13Ch; void *
0x1800157e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800157ed  mov     [rsp+1A0h+var_148], r15
0x1800157f2  mov     [rsp+1A0h+var_130], r15d
0x1800157f7  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800157ff  mov     rdi, [rsp+1A0h+var_140]
0x180015804  mov     rax, [rdi]
0x180015807  mov     rbx, [rax+18h]
0x18001580b  lea     rcx, [rsp+1A0h+var_148]
0x180015810  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015815  lea     r9, [rsp+1A0h+var_130]
0x18001581a  lea     r8, [rsp+1A0h+var_148]
0x18001581f  mov     edx, 1
0x180015824  mov     rcx, rdi
0x180015827  mov     rax, rbx
0x18001582a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001582f  mov     rcx, [rbp+0A8h]; this
0x180015836  test    eax, eax
0x180015838  js      loc_180015A2E
0x18001583e  jnz     loc_1800159BC
0x180015844  mov     [rsp+1A0h+pv], r15
0x180015849  mov     [rsp+1A0h+var_150], r15d
0x18001584e  mov     rcx, [rsp+1A0h+var_148]
0x180015853  mov     rax, [rcx]
0x180015856  lea     rdx, [rsp+1A0h+pv]
0x18001585b  mov     [rsp+1A0h+var_128], rdx
0x180015860  mov     [rbp+0A0h+var_120], r15
0x180015864  mov     [rbp+0A0h+var_118], 1
0x180015868  lea     r8, [rbp+0A0h+var_120]
0x18001586c  lea     rdx, [rsp+1A0h+var_150]
0x180015871  mov     rax, [rax+18h]
0x180015875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001587a  mov     rcx, [rbp+0A8h]; this
0x180015881  test    eax, eax
0x180015883  js      loc_1800159A7
0x180015889  cmp     [rbp+0A0h+var_118], r15b
0x18001588d  jz      short loc_1800158A9
0x18001588f  mov     rdx, [rsp+1A0h+var_128]
0x180015894  mov     rcx, [rdx]; pv
0x180015897  mov     rax, [rbp+0A0h+var_120]
0x18001589b  mov     [rdx], rax
0x18001589e  test    rcx, rcx
0x1800158a1  jz      short loc_1800158A9
0x1800158a3  call    cs:__imp_CoTaskMemFree
0x1800158a9  mov     r8d, [rsp+1A0h+var_150]
0x1800158ae  mov     rdx, [rsp+1A0h+pv]
0x1800158b3  lea     rcx, [rbp+0A0h+var_A8]
0x1800158b7  call    ?NetworkSignatureToCDSReferenceId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBEK@Z; NetworkSignatureToCDSReferenceId(uchar const * const,ulong)
0x1800158bc  nop
0x1800158bd  lea     rdx, [rbp+0A0h+var_A8]
0x1800158c1  cmp     [rbp+0A0h+var_90], 7
0x1800158c6  cmova   rdx, [rbp+0A0h+var_A8]
0x1800158cb  mov     r8, cs:?c_wiFiCloudStoreDataReferenceDefaultCollectionName@@3PEBGEB; ushort const * const c_wiFiCloudStoreDataReferenceDefaultCollectionName
0x1800158d2  lea     rcx, [rbp+0A0h+var_80]
0x1800158d6  call    ??$make_cloud_store_data_reference@UNlmSignature@Nlm@Data@Windows@@@wil@@YA?AU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(ushort const *,ushort const *)
0x1800158db  nop
0x1800158dc  mov     r9d, 2
0x1800158e2  lea     r8, [rbp+0A0h+var_80]
0x1800158e6  lea     rdx, [rbp+0A0h+var_F0]
0x1800158ea  mov     rcx, r14
0x1800158ed  call    ??$load@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@AEBU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Nlm::NlmSignature>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> const &,wil::cloud_store_load_options,char const *)
0x1800158f2  nop
0x1800158f3  cmp     [rbp+0A0h+var_D8], r15b
0x1800158f7  jnz     short loc_180015904
0x1800158f9  movsxd  rax, [rsp+1A0h+var_15C]
0x1800158fe  cmp     [rbp+0A0h+var_F0], rax
0x180015902  jz      short loc_180015947
0x180015904  movsxd  rax, [rsp+1A0h+var_15C]
0x180015909  mov     [rbp+0A0h+var_F0], rax
0x18001590d  lea     r9, [rbp+0A0h+var_80]
0x180015911  lea     r8, [rbp+0A0h+var_F0]
0x180015915  lea     rdx, [rbp+0A0h+var_C8]
0x180015919  mov     rcx, r14
0x18001591c  call    ??$save@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@AEBU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Nlm::NlmSignature>(wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &,Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x180015921  inc     esi
0x180015923  mov     [rsp+1A0h+var_14C], esi
0x180015927  lea     rax, [rbp+0A0h+var_A8]
0x18001592b  cmp     [rbp+0A0h+var_90], 7
0x180015930  cmova   rax, [rbp+0A0h+var_A8]
0x180015935  mov     [rbp+0A0h+var_F8], rax
0x180015939  lea     rdx, [rbp+0A0h+var_F8]
0x18001593d  lea     rcx, [rbp+0A0h+var_B8]
0x180015941  call    ??$SignatureUploadedForNetwork@AEAU_GUID@@PEBG@WiFiCloudStoreTelemetry@@SAXAEAU_GUID@@$$QEAPEBG@Z; WiFiCloudStoreTelemetry::SignatureUploadedForNetwork<_GUID &,ushort const *>(_GUID &,ushort const * &&)
0x180015946  nop
0x180015947  lea     rcx, [rbp+0A0h+var_E0]
0x18001594b  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180015950  nop
0x180015951  lea     rcx, [rbp+0A0h+var_60]
0x180015955  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001595a  lea     rcx, [rbp+0A0h+var_80]
0x18001595e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015963  nop
0x180015964  mov     rdx, [rbp+0A0h+var_90]
0x180015968  cmp     rdx, 7
0x18001596c  jbe     short loc_18001597F
0x18001596e  lea     rdx, ds:2[rdx*2]
0x180015976  mov     rcx, [rbp+0A0h+var_A8]
0x18001597a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001597f  movdqu  xmmword ptr [rbp+8], xmm6
0x180015984  mov     word ptr [rbp+0A0h+var_A8], r15w
0x180015989  mov     rcx, [rsp+1A0h+pv]; pv
0x18001598e  mov     [rsp+1A0h+pv], r15
0x180015993  test    rcx, rcx
0x180015996  jz      loc_1800157FF
0x18001599c  call    cs:__imp_CoTaskMemFree
0x1800159a2  jmp     loc_1800157FF
0x1800159a7  mov     r9d, eax; char *
0x1800159aa  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800159b1  mov     edx, 143h; void *
0x1800159b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800159bc  lea     rdx, [rsp+1A0h+var_14C]
0x1800159c1  lea     rcx, [rbp+0A0h+var_B8]
0x1800159c5  call    ??$TotalSignaturesUploadedToCloudForNetwork@AEAU_GUID@@AEAI@WiFiCloudStoreTelemetry@@SAXAEAU_GUID@@AEAI@Z; WiFiCloudStoreTelemetry::TotalSignaturesUploadedToCloudForNetwork<_GUID &,uint &>(_GUID &,uint &)
0x1800159ca  nop
0x1800159cb  mov     rcx, [rsp+1A0h+var_148]
0x1800159d0  test    rcx, rcx
0x1800159d3  jz      short loc_1800159E7
0x1800159d5  mov     [rsp+1A0h+var_148], r15
0x1800159da  mov     rax, [rcx]
0x1800159dd  mov     rax, [rax+10h]
0x1800159e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159e6  nop
0x1800159e7  mov     rcx, [rsp+1A0h+var_140]
0x1800159ec  test    rcx, rcx
0x1800159ef  jz      short loc_180015A03
0x1800159f1  mov     [rsp+1A0h+var_140], r15
0x1800159f6  mov     rax, [rcx]
0x1800159f9  mov     rax, [rax+10h]
0x1800159fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a02  nop
0x180015a03  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x180015a07  call    cs:__imp_VariantClear
0x180015a0d  nop
0x180015a0e  mov     rcx, [rsp+1A0h+var_158]
0x180015a13  test    rcx, rcx
0x180015a16  jz      short loc_180015A2A
0x180015a18  mov     [rsp+1A0h+var_158], r15
0x180015a1d  mov     rdx, [rcx]
0x180015a20  mov     rax, [rdx+10h]
0x180015a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a29  nop
0x180015a2a  mov     eax, esi
0x180015a2c  jmp     short loc_180015A78
0x180015a2e  mov     r9d, eax; char *
0x180015a31  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180015a38  mov     edx, 13Fh; void *
0x180015a3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015a43  mov     [rsp+1A0h+var_15F], r15b
0x180015a48  mov     [rsp+1A0h+var_160], r15b
0x180015a4d  lea     r8, [rsp+1A0h+var_15F]
0x180015a52  lea     rdx, [rsp+1A0h+var_160]
0x180015a57  lea     rcx, [rbp+0A0h+var_B8]
0x180015a5b  call    ??$NlmSkippingNetwork@AEAU_GUID@@_N_N@WiFiCloudStoreTelemetry@@SAXAEAU_GUID@@$$QEA_N1@Z; WiFiCloudStoreTelemetry::NlmSkippingNetwork<_GUID &,bool,bool>(_GUID &,bool &&,bool &&)
0x180015a60  nop
0x180015a61  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x180015a65  call    cs:__imp_VariantClear
0x180015a6b  nop
0x180015a6c  lea     rcx, [rsp+1A0h+var_158]
0x180015a71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015a76  xor     eax, eax
0x180015a78  mov     rcx, [rbp+0A0h+var_40]
0x180015a7c  xor     rcx, rsp; StackCookie
0x180015a7f  call    __security_check_cookie
0x180015a84  lea     r11, [rsp+1A0h+var_20]
0x180015a8c  mov     rbx, [r11+40h]
0x180015a90  movaps  xmm6, xmmword ptr [r11-10h]
0x180015a95  mov     rsp, r11
0x180015a98  pop     r15
0x180015a9a  pop     r14
0x180015a9c  pop     rdi
0x180015a9d  pop     rsi
0x180015a9e  pop     rbp
0x180015a9f  retn
```
