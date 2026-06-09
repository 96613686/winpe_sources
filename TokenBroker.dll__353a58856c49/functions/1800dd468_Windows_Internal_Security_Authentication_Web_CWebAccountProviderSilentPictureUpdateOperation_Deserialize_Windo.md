# Windows::Internal::Security::Authentication::Web::CWebAccountProviderSilentPictureUpdateOperation::Deserialize(Windows::Foundation::Collections::IPropertySet *,_GUID &,_GUID &,Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation * *)

- ea: `0x1800dd468`
- end: `0x1800dd87f`
- name: `?Deserialize@CWebAccountProviderSilentPictureUpdateOperation@Web@Authentication@Security@Internal@Windows@@SAJPEAUIPropertySet@Collections@Foundation@6@AEAU_GUID@@1PEAPEAUIWebAccountProviderOperation@Provider@2346@@Z`
- size: `1047`
- prototype: `__int64 __fastcall(struct Windows::Foundation::Collections::IPropertySet *, struct _GUID *, struct _GUID *, struct Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a9220`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180018224`
- `0x1800184ac`
- `0x180025bd8`
- `0x180026870`
- `0x180040980`
- `0x180047794`
- `0x18004c014`
- `0x180050240`
- `0x18007f230`
- `0x18008e690`
- `0x1800b4fe4`
- `0x1800dcd34`
- `0x1800dd468`
- `0x1800f260c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd62e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd6c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd78d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd7a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd62e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd6c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd78d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd7a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800dd6dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800dd6dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd54a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd5c8`

## string_xrefs

- `0x1800dd4cb`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`
- `0x1800dd613`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`
- `0x1800dd665`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`
- `0x1800dd6ab`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`
- `0x1800dd772`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`
- `0x1800dd813`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`
- `0x1800dd835`: `onecore\ds\security\tokenbroker\broker\lib\webaccountproviderpictureupdateoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CWebAccountProviderSilentPictureUpdateOperation::Deserialize(
        struct Windows::Foundation::Collections::IPropertySet *a1,
        struct _GUID *a2,
        struct _GUID *a3,
        struct Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation **a4)
{
  int v4; // r15d
  int v7; // eax
  int BytesProperty; // ebx
  const unsigned __int16 (*v9)[50]; // rdx
  HSTRING v10; // rdx
  void *v11; // rdi
  HSTRING v12; // rdx
  void *v13; // rdi
  HSTRING *v14; // rax
  int StringProperty; // eax
  int v16; // eax
  int v17; // eax
  int v18; // r9d
  WCHAR *StringRawBuffer; // rax
  HSTRING v20; // rbx
  int v21; // eax
  int v22; // edi
  int v24; // [rsp+20h] [rbp-79h]
  int v25; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+40h] [rbp-59h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v27; // [rsp+48h] [rbp-51h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v28; // [rsp+50h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-41h] BYREF
  HSTRING v30; // [rsp+60h] [rbp-39h] BYREF
  __int64 v31; // [rsp+68h] [rbp-31h] BYREF
  HSTRING v32; // [rsp+70h] [rbp-29h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v33; // [rsp+78h] [rbp-21h] BYREF
  _OWORD v34[2]; // [rsp+80h] [rbp-19h] BYREF
  int v35; // [rsp+A0h] [rbp+7h]
  char v36; // [rsp+A4h] [rbp+Bh]
  HSTRING v37[4]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v4 = (int)a4;
  memset(v34, 0, sizeof(v34));
  v35 = 0;
  v36 = 1;
  v7 = Windows::Internal::Security::CPropertiesSerializer::InitializeFromPropertySet(
         (Windows::Internal::Security::CPropertiesSerializer *)v34,
         a1);
  BytesProperty = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)v7,
      v24);
    goto LABEL_49;
  }
  v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v10 = *Windows::Internal::StringReference::StringReference(v37, v9);
  if ( !v10 )
  {
    BytesProperty = -2147024809;
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)BytesProperty,
      v24);
    goto LABEL_48;
  }
  pv = 0;
  LODWORD(string) = 0;
  BytesProperty = Windows::Internal::Security::CPropertiesSerializer::GetBytesProperty(
                    (Windows::Internal::Security::CPropertiesSerializer *)v34,
                    v10,
                    (unsigned __int8 **)&pv,
                    (unsigned int *)&string);
  v11 = pv;
  if ( BytesProperty >= 0 )
    BytesProperty = WebAccountFromBytesFactory((unsigned __int8 *const)pv, (unsigned int)string, &v27);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( BytesProperty < 0 )
    goto LABEL_47;
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v12 = *Windows::Internal::StringReference::StringReference(
           v37,
           L"webaccountpicture_{d88ff7bd-09ff-471e-9964-b9a1129076cb}");
  if ( !v12 )
  {
    BytesProperty = -2147024809;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)BytesProperty,
      v24);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
LABEL_48:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    goto LABEL_49;
  }
  pv = 0;
  LODWORD(string) = 0;
  BytesProperty = Windows::Internal::Security::CPropertiesSerializer::GetBytesProperty(
                    (Windows::Internal::Security::CPropertiesSerializer *)v34,
                    v12,
                    (unsigned __int8 **)&pv,
                    (unsigned int *)&string);
  v13 = pv;
  if ( BytesProperty >= 0 )
    BytesProperty = WebAccountPictureFromBytesFactory((unsigned __int8 *const)pv, (unsigned int)string, &v28);
  if ( v13 )
    CoTaskMemFree(v13);
  if ( BytesProperty < 0 )
    goto LABEL_45;
  string = 0;
  v14 = Windows::Internal::StringReference::StringReference(
          v37,
          L"correlationId_{b4d661af-69f2-4e77-b3e1-94d8c9e04d30}");
  StringProperty = Windows::Internal::Security::CPropertiesSerializer::GetStringProperty(
                     (Windows::Internal::Security::CPropertiesSerializer *)v34,
                     *v14,
                     &string);
  BytesProperty = 0;
  if ( StringProperty != -2147483637 )
    BytesProperty = StringProperty;
  if ( BytesProperty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)BytesProperty,
      v24);
    goto LABEL_19;
  }
  v31 = 0;
  v16 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v27,
          (__int64)&v31);
  BytesProperty = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)v16,
      v24);
LABEL_24:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
LABEL_19:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_21;
  }
  v30 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 48LL))(v31, &v30);
  BytesProperty = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)v17,
      v24);
    if ( v30 )
      WindowsDeleteString(v30);
    goto LABEL_24;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    if ( WindowsIsStringEmpty(v30) )
      StringRawBuffer = L"null";
    else
      StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(v30, 0);
    pv = StringRawBuffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180175000,
      (unsigned int)word_180151732,
      0,
      v18,
      (__int64)&pv);
  }
  pv = v28;
  v20 = string;
  v32 = string;
  v33 = v27;
  LODWORD(string) = 3;
  v21 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Security::Authentication::Web::CWebAccountProviderSilentPictureUpdateOperation,Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation,enum Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind,Windows::Security::Credentials::IWebAccount *,HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream *,_GUID &,_GUID &>(
          v4,
          (unsigned int)&string,
          (unsigned int)&v33,
          (unsigned int)&v32,
          (__int64)&pv,
          (__int64)a2,
          (__int64)a3);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( v30 )
      WindowsDeleteString(v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    if ( v20 )
      WindowsDeleteString(v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    BytesProperty = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\webaccountproviderpictureupdateoperation.cpp",
      (const char *)(unsigned int)v21,
      v25);
    if ( v30 )
      WindowsDeleteString(v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    if ( v20 )
      WindowsDeleteString(v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    BytesProperty = v22;
  }
LABEL_49:
  Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v34);
  return (unsigned int)BytesProperty;
}

```

## disassembly

```asm
0x1800dd468  mov     [rsp-8+arg_8], rbx
0x1800dd46d  push    rbp
0x1800dd46e  push    rsi
0x1800dd46f  push    rdi
0x1800dd470  push    r14
0x1800dd472  push    r15
0x1800dd474  lea     rbp, [rsp-37h]
0x1800dd479  sub     rsp, 0D0h
0x1800dd480  mov     rax, cs:__security_cookie
0x1800dd487  xor     rax, rsp
0x1800dd48a  mov     [rbp+57h+var_28], rax
0x1800dd48e  mov     r15, r9
0x1800dd491  mov     rsi, r8
0x1800dd494  mov     r14, rdx
0x1800dd497  xorps   xmm0, xmm0
0x1800dd49a  movdqu  [rbp+57h+var_70], xmm0
0x1800dd49f  xorps   xmm1, xmm1
0x1800dd4a2  movdqu  [rbp+57h+var_60], xmm1
0x1800dd4a7  mov     [rbp+57h+var_50], 0
0x1800dd4ae  mov     [rbp+57h+var_4C], 1
0x1800dd4b2  mov     rdx, rcx; struct Windows::Foundation::Collections::IPropertySet *
0x1800dd4b5  lea     rcx, [rbp+57h+var_70]; this
0x1800dd4b9  call    ?InitializeFromPropertySet@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUIPropertySet@Collections@Foundation@4@@Z; Windows::Internal::Security::CPropertiesSerializer::InitializeFromPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x1800dd4be  mov     ebx, eax
0x1800dd4c0  test    eax, eax
0x1800dd4c2  jns     short loc_1800DD4E1
0x1800dd4c4  mov     rcx, [rbp+5Fh]; this
0x1800dd4c8  mov     r9d, eax; char *
0x1800dd4cb  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd4d2  mov     edx, 0D4h; void *
0x1800dd4d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd4dc  jmp     loc_1800DD851
0x1800dd4e1  mov     [rbp+57h+var_A8], 0
0x1800dd4e9  lea     rcx, [rbp+57h+var_A8]
0x1800dd4ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd4f2  lea     rcx, [rbp+57h+var_48]; string
0x1800dd4f6  call    ??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[50])
0x1800dd4fb  mov     rdx, [rax]; HSTRING
0x1800dd4fe  test    rdx, rdx
0x1800dd501  jz      loc_1800DD829
0x1800dd507  mov     [rbp+57h+pv], 0
0x1800dd50f  mov     dword ptr [rbp+57h+string], 0
0x1800dd516  lea     r9, [rbp+57h+string]; unsigned int *
0x1800dd51a  lea     r8, [rbp+57h+pv]; unsigned __int8 **
0x1800dd51e  lea     rcx, [rbp+57h+var_70]; this
0x1800dd522  call    ?GetBytesProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAEPEAK@Z; Windows::Internal::Security::CPropertiesSerializer::GetBytesProperty(HSTRING__ *,uchar * *,ulong *)
0x1800dd527  mov     ebx, eax
0x1800dd529  mov     rdi, [rbp+57h+pv]
0x1800dd52d  test    eax, eax
0x1800dd52f  js      short loc_1800DD542
0x1800dd531  lea     r8, [rbp+57h+var_A8]; struct Windows::Security::Credentials::IWebAccount **
0x1800dd535  mov     edx, dword ptr [rbp+57h+string]; unsigned int
0x1800dd538  mov     rcx, rdi; unsigned __int8 *
0x1800dd53b  call    ?WebAccountFromBytesFactory@@YAJQEAEKPEAPEAUIWebAccount@Credentials@Security@Windows@@@Z; WebAccountFromBytesFactory(uchar * const,ulong,Windows::Security::Credentials::IWebAccount * *)
0x1800dd540  mov     ebx, eax
0x1800dd542  test    rdi, rdi
0x1800dd545  jz      short loc_1800DD550
0x1800dd547  mov     rcx, rdi; pv
0x1800dd54a  call    cs:__imp_CoTaskMemFree
0x1800dd550  test    ebx, ebx
0x1800dd552  js      loc_1800DD82E
0x1800dd558  mov     [rbp+57h+var_A0], 0
0x1800dd560  lea     rcx, [rbp+57h+var_A0]
0x1800dd564  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd569  lea     rdx, aWebaccountpict; "webaccountpicture_{d88ff7bd-09ff-471e-9"...
0x1800dd570  lea     rcx, [rbp+57h+var_48]; string
0x1800dd574  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x1800dd579  mov     rdx, [rax]; HSTRING
0x1800dd57c  test    rdx, rdx
0x1800dd57f  jz      loc_1800DD807
0x1800dd585  mov     [rbp+57h+pv], 0
0x1800dd58d  mov     dword ptr [rbp+57h+string], 0
0x1800dd594  lea     r9, [rbp+57h+string]; unsigned int *
0x1800dd598  lea     r8, [rbp+57h+pv]; unsigned __int8 **
0x1800dd59c  lea     rcx, [rbp+57h+var_70]; this
0x1800dd5a0  call    ?GetBytesProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAEPEAK@Z; Windows::Internal::Security::CPropertiesSerializer::GetBytesProperty(HSTRING__ *,uchar * *,ulong *)
0x1800dd5a5  mov     ebx, eax
0x1800dd5a7  mov     rdi, [rbp+57h+pv]
0x1800dd5ab  test    eax, eax
0x1800dd5ad  js      short loc_1800DD5C0
0x1800dd5af  lea     r8, [rbp+57h+var_A0]; struct Windows::Storage::Streams::IRandomAccessStream **
0x1800dd5b3  mov     edx, dword ptr [rbp+57h+string]; unsigned int
0x1800dd5b6  mov     rcx, rdi; unsigned __int8 *
0x1800dd5b9  call    ?WebAccountPictureFromBytesFactory@@YAJQEAEKPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; WebAccountPictureFromBytesFactory(uchar * const,ulong,Windows::Storage::Streams::IRandomAccessStream * *)
0x1800dd5be  mov     ebx, eax
0x1800dd5c0  test    rdi, rdi
0x1800dd5c3  jz      short loc_1800DD5CE
0x1800dd5c5  mov     rcx, rdi; pv
0x1800dd5c8  call    cs:__imp_CoTaskMemFree
0x1800dd5ce  test    ebx, ebx
0x1800dd5d0  js      loc_1800DD80C
0x1800dd5d6  mov     [rbp+57h+string], 0
0x1800dd5de  lea     rdx, aCorrelationidB; "correlationId_{b4d661af-69f2-4e77-b3e1-"...
0x1800dd5e5  lea     rcx, [rbp+57h+var_48]; string
0x1800dd5e9  call    ??$?0$0DF@@StringReference@Internal@Windows@@QEAA@AEAY0DF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[53])
0x1800dd5ee  lea     r8, [rbp+57h+string]; HSTRING *
0x1800dd5f2  mov     rdx, [rax]; HSTRING
0x1800dd5f5  lea     rcx, [rbp+57h+var_70]; this
0x1800dd5f9  call    ?GetStringProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAU5@@Z; Windows::Internal::Security::CPropertiesSerializer::GetStringProperty(HSTRING__ *,HSTRING__ * *)
0x1800dd5fe  xor     ebx, ebx
0x1800dd600  cmp     eax, 8000000Bh
0x1800dd605  cmovnz  ebx, eax
0x1800dd608  test    ebx, ebx
0x1800dd60a  jns     short loc_1800DD643
0x1800dd60c  mov     rcx, [rbp+5Fh]; this
0x1800dd610  mov     r9d, ebx; char *
0x1800dd613  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd61a  mov     edx, 0EBh; void *
0x1800dd61f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd624  nop
0x1800dd625  mov     rcx, [rbp+57h+string]; string
0x1800dd629  test    rcx, rcx
0x1800dd62c  jz      short loc_1800DD635
0x1800dd62e  call    cs:__imp_WindowsDeleteString
0x1800dd634  nop
0x1800dd635  lea     rcx, [rbp+57h+var_A0]
0x1800dd639  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd63e  jmp     loc_1800DD847
0x1800dd643  mov     [rbp+57h+var_88], 0
0x1800dd64b  lea     rdx, [rbp+57h+var_88]
0x1800dd64f  lea     rcx, [rbp+57h+var_A8]
0x1800dd653  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800dd658  mov     ebx, eax
0x1800dd65a  test    eax, eax
0x1800dd65c  jns     short loc_1800DD682
0x1800dd65e  mov     rcx, [rbp+5Fh]; this
0x1800dd662  mov     r9d, eax; char *
0x1800dd665  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd66c  mov     edx, 0F2h; void *
0x1800dd671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd676  nop
0x1800dd677  lea     rcx, [rbp+57h+var_88]
0x1800dd67b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd680  jmp     short loc_1800DD625
0x1800dd682  mov     [rbp+57h+var_90], 0
0x1800dd68a  mov     rcx, [rbp+57h+var_88]
0x1800dd68e  mov     rax, [rcx]
0x1800dd691  lea     rdx, [rbp+57h+var_90]
0x1800dd695  mov     rax, [rax+30h]
0x1800dd699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd69e  mov     ebx, eax
0x1800dd6a0  test    eax, eax
0x1800dd6a2  jns     short loc_1800DD6CE
0x1800dd6a4  mov     rcx, [rbp+5Fh]; this
0x1800dd6a8  mov     r9d, eax; char *
0x1800dd6ab  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd6b2  mov     edx, 0F4h; void *
0x1800dd6b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd6bc  nop
0x1800dd6bd  mov     rcx, [rbp+57h+var_90]; string
0x1800dd6c1  test    rcx, rcx
0x1800dd6c4  jz      short loc_1800DD677
0x1800dd6c6  call    cs:__imp_WindowsDeleteString
0x1800dd6cc  jmp     short loc_1800DD677
0x1800dd6ce  mov     eax, cs:dword_180175000
0x1800dd6d4  cmp     eax, 5
0x1800dd6d7  jbe     short loc_1800DD71F
0x1800dd6d9  mov     rcx, [rbp+57h+var_90]; string
0x1800dd6dd  call    cs:__imp_WindowsIsStringEmpty
0x1800dd6e3  test    eax, eax
0x1800dd6e5  jz      short loc_1800DD6F0
0x1800dd6e7  lea     rax, aNull; "null"
0x1800dd6ee  jmp     short loc_1800DD6FC
0x1800dd6f0  xor     edx, edx; length
0x1800dd6f2  mov     rcx, [rbp+57h+var_90]; string
0x1800dd6f6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dd6fc  mov     [rbp+57h+pv], rax
0x1800dd700  lea     rax, [rbp+57h+pv]
0x1800dd704  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800dd709  xor     r8d, r8d
0x1800dd70c  lea     rdx, word_180151732
0x1800dd713  lea     rcx, dword_180175000
0x1800dd71a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800dd71f  mov     rax, [rbp+57h+var_A0]
0x1800dd723  mov     [rbp+57h+pv], rax
0x1800dd727  mov     rbx, [rbp+57h+string]
0x1800dd72b  mov     [rbp+57h+var_80], rbx
0x1800dd72f  mov     rax, [rbp+57h+var_A8]
0x1800dd733  mov     [rbp+57h+var_78], rax
0x1800dd737  mov     dword ptr [rbp+57h+string], 3
0x1800dd73e  mov     [rsp+0F0h+var_C0], rsi
0x1800dd743  mov     [rsp+0F0h+var_C8], r14
0x1800dd748  lea     rax, [rbp+57h+pv]
0x1800dd74c  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800dd751  lea     r9, [rbp+57h+var_80]
0x1800dd755  lea     r8, [rbp+57h+var_78]
0x1800dd759  lea     rdx, [rbp+57h+string]
0x1800dd75d  mov     rcx, r15
0x1800dd760  call    ??$MakeAndInitialize@VCWebAccountProviderSilentPictureUpdateOperation@Web@Authentication@Security@Internal@Windows@@UIWebAccountProviderOperation@Provider@2346@W4WebAccountProviderOperationKind@82346@PEAUIWebAccount@Credentials@46@PEAUHSTRING__@@PEAUIRandomAccessStream@Streams@Storage@6@AEAU_GUID@@AEAU_GUID@@@Details@WRL@Microsoft@@YAJPEAPEAUIWebAccountProviderOperation@Provider@Web@Authentication@Security@Windows@@$$QEAW4WebAccountProviderOperationKind@45678@$$QEAPEAUIWebAccount@Credentials@78@$$QEAPEAUHSTRING__@@$$QEAPEAUIRandomAccessStream@Streams@Storage@8@AEAU_GUID@@5@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Security::Authentication::Web::CWebAccountProviderSilentPictureUpdateOperation,Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation,Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind,Windows::Security::Credentials::IWebAccount *,HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream *,_GUID &,_GUID &>(Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation * *,Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind &&,Windows::Security::Credentials::IWebAccount * &&,HSTRING__ * &&,Windows::Storage::Streams::IRandomAccessStream * &&,_GUID &,_GUID &)
0x1800dd765  mov     edi, eax
0x1800dd767  test    eax, eax
0x1800dd769  jns     short loc_1800DD7C7
0x1800dd76b  mov     rcx, [rbp+5Fh]; this
0x1800dd76f  mov     r9d, eax; char *
0x1800dd772  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd779  mov     edx, 103h; void *
0x1800dd77e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd783  nop
0x1800dd784  mov     rcx, [rbp+57h+var_90]; string
0x1800dd788  test    rcx, rcx
0x1800dd78b  jz      short loc_1800DD794
0x1800dd78d  call    cs:__imp_WindowsDeleteString
0x1800dd793  nop
0x1800dd794  lea     rcx, [rbp+57h+var_88]
0x1800dd798  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd79d  nop
0x1800dd79e  test    rbx, rbx
0x1800dd7a1  jz      short loc_1800DD7AD
0x1800dd7a3  mov     rcx, rbx; string
0x1800dd7a6  call    cs:__imp_WindowsDeleteString
0x1800dd7ac  nop
0x1800dd7ad  lea     rcx, [rbp+57h+var_A0]
0x1800dd7b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd7b6  nop
0x1800dd7b7  lea     rcx, [rbp+57h+var_A8]
0x1800dd7bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd7c0  mov     ebx, edi
0x1800dd7c2  jmp     loc_1800DD851
0x1800dd7c7  mov     rcx, [rbp+57h+var_90]; string
0x1800dd7cb  test    rcx, rcx
0x1800dd7ce  jz      short loc_1800DD7D7
0x1800dd7d0  call    cs:__imp_WindowsDeleteString
0x1800dd7d6  nop
0x1800dd7d7  lea     rcx, [rbp+57h+var_88]
0x1800dd7db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd7e0  nop
0x1800dd7e1  test    rbx, rbx
0x1800dd7e4  jz      short loc_1800DD7F0
0x1800dd7e6  mov     rcx, rbx; string
0x1800dd7e9  call    cs:__imp_WindowsDeleteString
0x1800dd7ef  nop
0x1800dd7f0  lea     rcx, [rbp+57h+var_A0]
0x1800dd7f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd7f9  nop
0x1800dd7fa  lea     rcx, [rbp+57h+var_A8]
0x1800dd7fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd803  xor     ebx, ebx
0x1800dd805  jmp     short loc_1800DD851
0x1800dd807  mov     ebx, 80070057h
0x1800dd80c  mov     rcx, [rbp+5Fh]; this
0x1800dd810  mov     r9d, ebx; char *
0x1800dd813  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd81a  mov     edx, 0E3h; void *
0x1800dd81f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd824  jmp     loc_1800DD635
0x1800dd829  mov     ebx, 80070057h
0x1800dd82e  mov     rcx, [rbp+5Fh]; this
0x1800dd832  mov     r9d, ebx; char *
0x1800dd835  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800dd83c  mov     edx, 0DBh; void *
0x1800dd841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd846  nop
0x1800dd847  lea     rcx, [rbp+57h+var_A8]
0x1800dd84b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dd850  nop
0x1800dd851  lea     rcx, [rbp+57h+var_70]; this
0x1800dd855  call    ??1CPropertiesSerializer@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer(void)
0x1800dd85a  mov     eax, ebx
0x1800dd85c  mov     rcx, [rbp+57h+var_28]
0x1800dd860  xor     rcx, rsp; StackCookie
0x1800dd863  call    __security_check_cookie
0x1800dd868  mov     rbx, [rsp+0F0h+arg_8]
0x1800dd870  add     rsp, 0D0h
0x1800dd877  pop     r15
0x1800dd879  pop     r14
0x1800dd87b  pop     rdi
0x1800dd87c  pop     rsi
0x1800dd87d  pop     rbp
0x1800dd87e  retn
```
