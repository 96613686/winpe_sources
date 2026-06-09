# LegacySystemLanguagePackResourceProvider::_SearchForPackage(bool *)

- ea: `0x180049d70`
- end: `0x18004a343`
- name: `?_SearchForPackage@LegacySystemLanguagePackResourceProvider@@AEBA?AV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@PEA_N@Z`
- size: `1491`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045570`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180035ce4`
- `0x180043cb8`
- `0x180046280`
- `0x180046330`
- `0x180047e48`
- `0x180048568`
- `0x180049d70`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a0dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a0dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180049e7c`
- `OLEAUT32!__imp_VariantInit` at `0x180049dd1`
- `OLEAUT32!__imp_VariantInit` at `0x180049dd1`
- `OLEAUT32!__imp_VariantClear` at `0x18004a1a0`
- `OLEAUT32!__imp_VariantClear` at `0x18004a1a0`

## string_xrefs

- `0x18004a220`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x18004a331`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x18004a20b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a235`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a24a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a25f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a274`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a289`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a29e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a2b0`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a2c5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a2da`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a2ef`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a307`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004a31c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
LPVOID *__fastcall LegacySystemLanguagePackResourceProvider::_SearchForPackage(__int64 a1, LPVOID *a2, _BYTE *a3)
{
  __int64 *v6; // rdi
  __int64 v7; // r13
  __int128 v8; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  int v10; // eax
  __int64 v11; // rbx
  BSTR *v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int i; // edi
  int v21; // eax
  int v22; // eax
  BSTR v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  HRESULT Instance; // eax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  void **v34; // rcx
  __int64 *v35; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  __int128 v39; // [rsp+48h] [rbp-C0h] BYREF
  IRecordInfo *v40; // [rsp+58h] [rbp-B0h]
  LPVOID *v41; // [rsp+68h] [rbp-A0h]
  __int64 v42; // [rsp+70h] [rbp-98h] BYREF
  __int64 v43; // [rsp+78h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-80h] BYREF
  int v46; // [rsp+90h] [rbp-78h] BYREF
  int v47; // [rsp+94h] [rbp-74h] BYREF
  int v48; // [rsp+98h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-68h] BYREF
  int v50[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-58h] BYREF
  void **v52; // [rsp+B8h] [rbp-50h] BYREF
  __int64 *v53; // [rsp+C0h] [rbp-48h] BYREF
  int v54; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v41 = a2;
  LegacySystemLanguagePackResourceProvider::_CreateUpdateSearcher(a1, &v53);
  Microsoft::WRL::Details::Make<CompletionCallback,>((CompletionCallback **)&v52);
  VariantInit(&pvarg);
  pvarg.lVal = -2147352572;
  pvarg.vt = 10;
  *(_QWORD *)v50 = 0;
  v6 = v53;
  v7 = *v53;
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  v42 = 0;
  v10 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(
          v52,
          &GUID_88aee058_d4b0_4725_a2f1_814a67ae964c,
          &v42);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
      (const char *)(unsigned int)v10,
      ppv);
  v11 = v42;
  v12 = LegacySystemLanguagePackResourceProvider::_CreateUUPSearchCriteria(&bstrString, a3);
  v39 = v8;
  v40 = pRecInfo;
  v13 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int128 *))(v7 + 120))(v6, *v12, v11, &v39);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v13,
      (int)v50);
  if ( bstrString )
    SysFreeString(bstrString);
  v14 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = *(_QWORD *)v50;
  if ( *(_QWORD *)v50 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v50 + 8LL))(*(_QWORD *)v50);
  *(_QWORD *)&v39 = v15;
  BYTE8(v39) = 1;
  CancellableWait(v52[27], *(void **)(a1 + 24), 0x493E0u);
  BYTE8(v39) = 0;
  v44 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v53 + 128))(v53, *(_QWORD *)v50, &v44);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v16,
      (int)v50);
  v46 = 2;
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 56LL))(v44, &v46);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B2,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v17,
      (int)v50);
  if ( v46 != 2 )
  {
    v42 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, &v42);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B7,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v18,
        (int)v50);
    LODWORD(v43) = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 72LL))(v42, &v43);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2BA,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v19,
        (int)v50);
    for ( i = 0; i < (int)v43; ++i )
    {
      bstrString = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v42 + 56LL))(
              v42,
              (unsigned int)i,
              &bstrString);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2BF,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v21,
          (int)v50);
      v47 = 0;
      v22 = (*(__int64 (__fastcall **)(BSTR, int *))(*(_QWORD *)bstrString + 64LL))(bstrString, &v47);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2C2,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v22,
          (int)v50);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2C4,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v47,
          (int)v50);
      v23 = bstrString;
      if ( bstrString )
      {
        bstrString = 0;
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    v24 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  v49 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 72LL))(v44, &v49);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v25,
      (int)v50);
  v48 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 80LL))(v49, &v48);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v26,
      (int)v50);
  if ( v48 <= 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)0x80073CF1LL,
      (int)v50);
  v51 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 56LL))(v49, 0, &v51);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v27,
      (int)v50);
  *a2 = 0;
  Instance = CoCreateInstance(
               &GUID_13639463_00db_4646_803d_528026140d88,
               0,
               0x17u,
               &GUID_07f7438c_7709_4ca5_b518_91279288134e,
               a2);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
      (const char *)(unsigned int)Instance,
      ppva);
  v54 = 0;
  v29 = (*(__int64 (__fastcall **)(LPVOID, __int64, int *))(*(_QWORD *)*a2 + 96LL))(*a2, v51, &v54);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v29,
      ppva);
  v30 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v33 = *(_QWORD *)v50;
  if ( *(_QWORD *)v50 )
  {
    *(_QWORD *)v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  VariantClear(&pvarg);
  v34 = v52;
  if ( v52 )
  {
    v52 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(v34);
  }
  v35 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
  }
  return a2;
}

```

## disassembly

```asm
0x180049d70  mov     rax, rsp
0x180049d73  mov     [rax+20h], rbx
0x180049d77  push    rbp
0x180049d78  push    rsi
0x180049d79  push    rdi
0x180049d7a  push    r12
0x180049d7c  push    r13
0x180049d7e  push    r14
0x180049d80  push    r15
0x180049d82  lea     rbp, [rax-48h]
0x180049d86  sub     rsp, 110h
0x180049d8d  movaps  xmmword ptr [rax-48h], xmm6
0x180049d91  movaps  xmmword ptr [rax-58h], xmm7
0x180049d95  mov     rax, cs:__security_cookie
0x180049d9c  xor     rax, rsp
0x180049d9f  mov     [rbp+40h+var_60], rax
0x180049da3  mov     r15, r8
0x180049da6  mov     rsi, rdx
0x180049da9  mov     r14, rcx
0x180049dac  mov     [rsp+140h+var_E0], rdx
0x180049db1  xor     r12d, r12d
0x180049db4  mov     [rsp+140h+var_110], r12d
0x180049db9  lea     rdx, [rbp+40h+var_88]
0x180049dbd  call    ?_CreateUpdateSearcher@LegacySystemLanguagePackResourceProvider@@AEBA?AV?$ComPtr@UIUpdateSearcher@@@WRL@Microsoft@@XZ; LegacySystemLanguagePackResourceProvider::_CreateUpdateSearcher(void)
0x180049dc2  nop
0x180049dc3  lea     rcx, [rbp+40h+var_90]
0x180049dc7  call    ??$Make@VCompletionCallback@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCompletionCallback@@@12@XZ; Microsoft::WRL::Details::Make<CompletionCallback,>(void)
0x180049dcc  nop
0x180049dcd  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180049dd1  call    cs:__imp_VariantInit
0x180049dd7  nop
0x180049dd8  mov     dword ptr [rbp+40h+pvarg+8], 80020004h
0x180049ddf  lea     eax, [r12+0Ah]
0x180049de4  mov     word ptr [rbp+40h+pvarg], ax
0x180049de8  mov     qword ptr [rbp+40h+var_A0], r12
0x180049dec  mov     rdi, [rbp+40h+var_88]
0x180049df0  mov     r13, [rdi]
0x180049df3  movups  xmm6, xmmword ptr [rbp+40h+pvarg]
0x180049df7  movsd   xmm7, qword ptr [rbp+40h+pvarg+10h]
0x180049dfc  mov     [rsp+140h+var_D8], r12
0x180049e01  mov     [rsp+140h+var_110], 4
0x180049e09  lea     r8, [rsp+140h+var_D8]
0x180049e0e  lea     rdx, _GUID_88aee058_d4b0_4725_a2f1_814a67ae964c
0x180049e15  mov     rcx, [rbp+40h+var_90]
0x180049e19  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISearchCompletedCallback@@UIDownloadCompletedCallback@@UIInstallationCompletedCallback@@UIDownloadProgressChangedCallback@@UIInstallationProgressChangedCallback@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(_GUID const &,void * *)
0x180049e1e  mov     rcx, [rbp+48h]; this
0x180049e22  test    eax, eax
0x180049e24  js      loc_18004A21D
0x180049e2a  mov     rbx, [rsp+140h+var_D8]
0x180049e2f  mov     rdx, r15
0x180049e32  lea     rcx, [rbp+40h+bstrString]
0x180049e36  call    ?_CreateUUPSearchCriteria@LegacySystemLanguagePackResourceProvider@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_N@Z; LegacySystemLanguagePackResourceProvider::_CreateUUPSearchCriteria(bool *)
0x180049e3b  nop
0x180049e3c  movaps  [rsp+140h+var_108+8], xmm6
0x180049e41  movsd   [rsp+140h+var_F0], xmm7
0x180049e47  lea     rcx, [rbp+40h+var_A0]
0x180049e4b  mov     qword ptr [rsp+140h+ppv], rcx; int
0x180049e50  lea     r9, [rsp+140h+var_108+8]
0x180049e55  mov     r8, rbx
0x180049e58  mov     rdx, [rax]
0x180049e5b  mov     rcx, rdi
0x180049e5e  mov     rax, [r13+78h]
0x180049e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e67  mov     rcx, [rbp+48h]; this
0x180049e6b  test    eax, eax
0x180049e6d  js      loc_18004A232
0x180049e73  mov     rcx, [rbp+40h+bstrString]; bstrString
0x180049e77  test    rcx, rcx
0x180049e7a  jz      short loc_180049E82
0x180049e7c  call    cs:__imp_SysFreeString
0x180049e82  mov     [rsp+140h+var_110], r12d
0x180049e87  mov     rcx, [rsp+140h+var_D8]
0x180049e8c  test    rcx, rcx
0x180049e8f  jz      short loc_180049EA3
0x180049e91  mov     [rsp+140h+var_D8], r12
0x180049e96  mov     rax, [rcx]
0x180049e99  mov     rax, [rax+10h]
0x180049e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ea2  nop
0x180049ea3  mov     rbx, qword ptr [rbp+40h+var_A0]
0x180049ea7  test    rbx, rbx
0x180049eaa  jz      short loc_180049EBC
0x180049eac  mov     rax, [rbx]
0x180049eaf  mov     rcx, rbx
0x180049eb2  mov     rax, [rax+8]
0x180049eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ebb  nop
0x180049ebc  mov     qword ptr [rsp+140h+var_108+8], rbx
0x180049ec1  mov     byte ptr [rsp+140h+var_F8], 1
0x180049ec6  mov     r8d, 493E0h; unsigned int
0x180049ecc  mov     rdx, [r14+18h]; void *
0x180049ed0  mov     rcx, [rbp+40h+var_90]
0x180049ed4  mov     rcx, [rcx+0D8h]; void *
0x180049edb  call    ?CancellableWait@@YAXPEAX0K@Z; CancellableWait(void *,void *,ulong)
0x180049ee0  mov     byte ptr [rsp+140h+var_F8], r12b
0x180049ee5  mov     [rsp+140h+var_C8], r12
0x180049eea  mov     rcx, [rbp+40h+var_88]
0x180049eee  mov     rax, [rcx]
0x180049ef1  lea     r8, [rsp+140h+var_C8]
0x180049ef6  mov     rdx, qword ptr [rbp+40h+var_A0]
0x180049efa  mov     rax, [rax+80h]
0x180049f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f06  mov     rcx, [rbp+48h]; this
0x180049f0a  test    eax, eax
0x180049f0c  js      loc_18004A247
0x180049f12  mov     [rbp+40h+var_B8], 2
0x180049f19  mov     rcx, [rsp+140h+var_C8]
0x180049f1e  mov     rax, [rcx]
0x180049f21  lea     rdx, [rbp+40h+var_B8]
0x180049f25  mov     rax, [rax+38h]
0x180049f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f2e  mov     rcx, [rbp+48h]; this
0x180049f32  test    eax, eax
0x180049f34  js      loc_18004A25C
0x180049f3a  cmp     [rbp+40h+var_B8], 2
0x180049f3e  jz      loc_18004A036
0x180049f44  mov     [rsp+140h+var_D8], r12
0x180049f49  mov     rcx, [rsp+140h+var_C8]
0x180049f4e  mov     rax, [rcx]
0x180049f51  lea     rdx, [rsp+140h+var_D8]
0x180049f56  mov     rax, [rax+50h]
0x180049f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f5f  mov     rcx, [rbp+48h]; this
0x180049f63  test    eax, eax
0x180049f65  js      loc_18004A271
0x180049f6b  mov     dword ptr [rsp+140h+var_D0], r12d
0x180049f70  mov     rcx, [rsp+140h+var_D8]
0x180049f75  mov     rax, [rcx]
0x180049f78  lea     rdx, [rsp+140h+var_D0]
0x180049f7d  mov     rax, [rax+48h]
0x180049f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f86  mov     rcx, [rbp+48h]; this
0x180049f8a  test    eax, eax
0x180049f8c  js      loc_18004A286
0x180049f92  mov     edi, r12d
0x180049f95  cmp     dword ptr [rsp+140h+var_D0], r12d
0x180049f9a  jle     short loc_18004A01A
0x180049f9c  mov     [rbp+40h+bstrString], r12
0x180049fa0  mov     rcx, [rsp+140h+var_D8]
0x180049fa5  mov     rax, [rcx]
0x180049fa8  lea     r8, [rbp+40h+bstrString]
0x180049fac  mov     edx, edi
0x180049fae  mov     rax, [rax+38h]
0x180049fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fb7  mov     rcx, [rbp+48h]; this
0x180049fbb  test    eax, eax
0x180049fbd  js      loc_18004A2D7
0x180049fc3  mov     dword ptr [rbp+40h+var_B4], r12d
0x180049fc7  mov     rcx, [rbp+40h+bstrString]
0x180049fcb  mov     rax, [rcx]
0x180049fce  lea     rdx, [rbp+40h+var_B4]
0x180049fd2  mov     rax, [rax+40h]
0x180049fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fdb  mov     rcx, [rbp+48h]; this
0x180049fdf  test    eax, eax
0x180049fe1  js      loc_18004A2C2
0x180049fe7  mov     r9d, dword ptr [rbp+40h+var_B4]; char *
0x180049feb  mov     rcx, [rbp+48h]; this
0x180049fef  test    r9d, r9d
0x180049ff2  js      loc_18004A2B0
0x180049ff8  mov     rcx, [rbp+40h+bstrString]
0x180049ffc  test    rcx, rcx
0x180049fff  jz      short loc_18004A012
0x18004a001  mov     [rbp+40h+bstrString], r12
0x18004a005  mov     rax, [rcx]
0x18004a008  mov     rax, [rax+10h]
0x18004a00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a011  nop
0x18004a012  inc     edi
0x18004a014  cmp     edi, dword ptr [rsp+140h+var_D0]
0x18004a018  jl      short loc_180049F9C
0x18004a01a  mov     rcx, [rsp+140h+var_D8]
0x18004a01f  test    rcx, rcx
0x18004a022  jz      short loc_18004A036
0x18004a024  mov     [rsp+140h+var_D8], r12
0x18004a029  mov     rax, [rcx]
0x18004a02c  mov     rax, [rax+10h]
0x18004a030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a035  nop
0x18004a036  mov     [rbp+40h+var_A8], r12
0x18004a03a  mov     rcx, [rsp+140h+var_C8]
0x18004a03f  mov     rax, [rcx]
0x18004a042  lea     rdx, [rbp+40h+var_A8]
0x18004a046  mov     rax, [rax+48h]
0x18004a04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a04f  mov     rcx, [rbp+48h]; this
0x18004a053  test    eax, eax
0x18004a055  js      loc_18004A29B
0x18004a05b  mov     dword ptr [rbp+40h+var_B4+4], r12d
0x18004a05f  mov     rcx, [rbp+40h+var_A8]
0x18004a063  mov     rax, [rcx]
0x18004a066  lea     rdx, [rbp+40h+var_B4+4]
0x18004a06a  mov     rax, [rax+50h]
0x18004a06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a073  mov     rcx, [rbp+48h]; this
0x18004a077  test    eax, eax
0x18004a079  js      loc_18004A2EC
0x18004a07f  cmp     dword ptr [rbp+40h+var_B4+4], r12d
0x18004a083  setle   al
0x18004a086  mov     rcx, [rbp+48h]; this
0x18004a08a  test    al, al
0x18004a08c  jnz     loc_18004A301
0x18004a092  mov     [rbp+40h+var_98], r12
0x18004a096  mov     rcx, [rbp+40h+var_A8]
0x18004a09a  mov     rax, [rcx]
0x18004a09d  lea     r8, [rbp+40h+var_98]
0x18004a0a1  xor     edx, edx
0x18004a0a3  mov     rax, [rax+38h]
0x18004a0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0ac  mov     rcx, [rbp+48h]; this
0x18004a0b0  test    eax, eax
0x18004a0b2  js      loc_18004A319
0x18004a0b8  mov     [rsi], r12
0x18004a0bb  mov     [rsp+140h+var_110], 8
0x18004a0c3  mov     qword ptr [rsp+140h+ppv], rsi; int
0x18004a0c8  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x18004a0cf  xor     edx, edx; pUnkOuter
0x18004a0d1  lea     r8d, [rdx+17h]; dwClsContext
0x18004a0d5  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x18004a0dc  call    cs:__imp_CoCreateInstance
0x18004a0e2  mov     rcx, [rbp+48h]; this
0x18004a0e6  test    eax, eax
0x18004a0e8  js      loc_18004A32E
0x18004a0ee  mov     [rsp+140h+var_110], 1
0x18004a0f6  mov     [rbp+40h+var_80], r12d
0x18004a0fa  mov     rcx, [rsi]
0x18004a0fd  mov     rax, [rcx]
0x18004a100  lea     r8, [rbp+40h+var_80]
0x18004a104  mov     rdx, [rbp+40h+var_98]
0x18004a108  mov     rax, [rax+60h]
0x18004a10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a111  mov     rcx, [rbp+48h]; this
0x18004a115  test    eax, eax
0x18004a117  js      loc_18004A208
0x18004a11d  mov     rcx, [rbp+40h+var_98]
0x18004a121  test    rcx, rcx
0x18004a124  jz      short loc_18004A137
0x18004a126  mov     [rbp+40h+var_98], r12
0x18004a12a  mov     rax, [rcx]
0x18004a12d  mov     rax, [rax+10h]
0x18004a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a136  nop
0x18004a137  mov     rcx, [rbp+40h+var_A8]
0x18004a13b  test    rcx, rcx
0x18004a13e  jz      short loc_18004A151
0x18004a140  mov     [rbp+40h+var_A8], r12
0x18004a144  mov     rax, [rcx]
0x18004a147  mov     rax, [rax+10h]
0x18004a14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a150  nop
0x18004a151  mov     rcx, [rsp+140h+var_C8]
0x18004a156  test    rcx, rcx
0x18004a159  jz      short loc_18004A16D
0x18004a15b  mov     [rsp+140h+var_C8], r12
0x18004a160  mov     rax, [rcx]
0x18004a163  mov     rax, [rax+10h]
0x18004a167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a16c  nop
0x18004a16d  test    rbx, rbx
0x18004a170  jz      short loc_18004A182
0x18004a172  mov     rax, [rbx]
0x18004a175  mov     rcx, rbx
0x18004a178  mov     rax, [rax+10h]
0x18004a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a181  nop
0x18004a182  mov     rcx, qword ptr [rbp+40h+var_A0]
0x18004a186  test    rcx, rcx
0x18004a189  jz      short loc_18004A19C
0x18004a18b  mov     qword ptr [rbp+40h+var_A0], r12
0x18004a18f  mov     rax, [rcx]
0x18004a192  mov     rax, [rax+10h]
0x18004a196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a19b  nop
0x18004a19c  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18004a1a0  call    cs:__imp_VariantClear
0x18004a1a6  nop
0x18004a1a7  mov     rcx, [rbp+40h+var_90]
0x18004a1ab  test    rcx, rcx
0x18004a1ae  jz      short loc_18004A1BA
0x18004a1b0  mov     [rbp+40h+var_90], r12
0x18004a1b4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(void)
0x18004a1b9  nop
0x18004a1ba  mov     rcx, [rbp+40h+var_88]
0x18004a1be  test    rcx, rcx
0x18004a1c1  jz      short loc_18004A1D4
0x18004a1c3  mov     [rbp+40h+var_88], r12
0x18004a1c7  mov     rdx, [rcx]
0x18004a1ca  mov     rax, [rdx+10h]
0x18004a1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1d3  nop
0x18004a1d4  mov     rax, rsi
0x18004a1d7  mov     rcx, [rbp+40h+var_60]
0x18004a1db  xor     rcx, rsp; StackCookie
0x18004a1de  call    __security_check_cookie
0x18004a1e3  lea     r11, [rsp+140h+var_30]
0x18004a1eb  mov     rbx, [r11+58h]
0x18004a1ef  movaps  xmm6, xmmword ptr [r11-10h]
0x18004a1f4  movaps  xmm7, xmmword ptr [r11-20h]
0x18004a1f9  mov     rsp, r11
0x18004a1fc  pop     r15
  ... truncated ...
```
