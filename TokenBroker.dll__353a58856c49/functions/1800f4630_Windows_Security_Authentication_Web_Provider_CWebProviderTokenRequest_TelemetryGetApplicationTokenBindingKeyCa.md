# Windows::Security::Authentication::Web::Provider::CWebProviderTokenRequest::TelemetryGetApplicationTokenBindingKeyCallDetails<WamClientLogProvider::WebProviderTokenRequestGetApplicationTokenBindingKeyId>(WamClientLogProvider::WebProviderTokenRequestGetApplicationTokenBindingKeyId const &,int,Windows::Security::Authentication::Web::TokenBindingKeyType,Windows::Foundation::IUriRuntimeClass *)

- ea: `0x1800f4630`
- end: `0x1800f48ea`
- name: `??$TelemetryGetApplicationTokenBindingKeyCallDetails@VWebProviderTokenRequestGetApplicationTokenBindingKeyId@WamClientLogProvider@@@CWebProviderTokenRequest@Provider@Web@Authentication@Security@Windows@@AEAAXAEBVWebProviderTokenRequestGetApplicationTokenBindingKeyId@WamClientLogProvider@@HW4TokenBindingKeyType@2345@PEAUIUriRuntimeClass@Foundation@5@@Z`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800f7740`

## callees

- `0x180005488`
- `0x180007350`
- `0x180031220`
- `0x1800f0f44`
- `0x1800f4630`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f47a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f47c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f47eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f47a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f47c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f47eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f48a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f48c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f48a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f48c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f47b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f47d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f47f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f47b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f47d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f47f9`

## pseudocode

```c
double __fastcall Windows::Security::Authentication::Web::Provider::CWebProviderTokenRequest::TelemetryGetApplicationTokenBindingKeyCallDetails<WamClientLogProvider::WebProviderTokenRequestGetApplicationTokenBindingKeyId>(
        _QWORD *a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5)
{
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  __int64 v10; // rcx
  __int64 v11; // rbx
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  PCWSTR v14; // rbx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v16; // rax
  PCWSTR v17; // rax
  PCWSTR v18; // rax
  int v19; // r9d
  HSTRING string; // [rsp+60h] [rbp-31h] BYREF
  HSTRING v22; // [rsp+68h] [rbp-29h] BYREF
  HSTRING v23; // [rsp+70h] [rbp-21h] BYREF
  HSTRING v24; // [rsp+78h] [rbp-19h] BYREF
  HSTRING v25; // [rsp+80h] [rbp-11h] BYREF
  __int64 v26; // [rsp+88h] [rbp-9h] BYREF
  PCWSTR v27; // [rsp+90h] [rbp-1h] BYREF
  PCWSTR v28; // [rsp+98h] [rbp+7h] BYREF
  PCWSTR v29; // [rsp+A0h] [rbp+Fh] BYREF
  PCWSTR v30; // [rsp+A8h] [rbp+17h] BYREF
  PCWSTR v31[6]; // [rsp+B0h] [rbp+1Fh] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64); // [rsp+F0h] [rbp+5Fh] BYREF
  int v33; // [rsp+100h] [rbp+6Fh] BYREF

  v33 = a3;
  v32 = 0;
  v25 = 0;
  v8 = a1[12];
  v9 = *(int (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v8 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  if ( v9(v8, &v32) >= 0 && v32 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))(*v32)[6])(v32, &v25);
  v26 = 0;
  v24 = 0;
  if ( (int)Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(
              &v32,
              (__int64)&v26) >= 0
    && v26 )
  {
    (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 56LL))(v26, &v24);
  }
  v23 = 0;
  v10 = a1[15];
  if ( v10 )
    (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL))(v10, &v23);
  v22 = 0;
  string = 0;
  v11 = a5;
  if ( a5 )
  {
    (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a5 + 48LL))(a5, &v22);
    (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 64LL))(v11, &string);
  }
  v12 = WamClientLogProvider::Provider();
  v13 = (int)v12;
  if ( *(_DWORD *)v12 > 5u )
  {
    a5 = a1[16];
    v33 = a4;
    v14 = L"null";
    if ( WindowsIsStringEmpty(string) )
      StringRawBuffer = L"null";
    else
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v27 = StringRawBuffer;
    if ( WindowsIsStringEmpty(v22) )
      v16 = L"null";
    else
      v16 = WindowsGetStringRawBuffer(v22, 0);
    v28 = v16;
    if ( WindowsIsStringEmpty(v23) )
      v17 = L"null";
    else
      v17 = WindowsGetStringRawBuffer(v23, 0);
    v29 = v17;
    if ( WindowsIsStringEmpty(v24) )
      v18 = L"null";
    else
      v18 = WindowsGetStringRawBuffer(v24, 0);
    v30 = v18;
    if ( !WindowsIsStringEmpty(v25) )
      v14 = WindowsGetStringRawBuffer(v25, 0);
    v31[0] = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v13,
      (unsigned int)byte_1801541EB,
      *(_QWORD *)(a2 + 272) + 8,
      v19,
      (__int64)v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v33,
      (__int64)&a5);
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v22 )
    WindowsDeleteString(v22);
  if ( v23 )
    WindowsDeleteString(v23);
  if ( v24 )
    WindowsDeleteString(v24);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  if ( v25 )
    WindowsDeleteString(v25);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
}

```

## disassembly

```asm
0x1800f4630  mov     [rsp-8+arg_8], rbx
0x1800f4635  mov     [rsp-8+arg_10], r8d
0x1800f463a  push    rbp
0x1800f463b  push    rsi
0x1800f463c  push    rdi
0x1800f463d  push    r14
0x1800f463f  push    r15
0x1800f4641  lea     rbp, [rsp-2Fh]
0x1800f4646  sub     rsp, 0C0h
0x1800f464d  mov     r14d, r9d
0x1800f4650  mov     r15, rdx
0x1800f4653  mov     rsi, rcx
0x1800f4656  mov     [rbp+4Fh+arg_0], 0
0x1800f465e  mov     [rbp+4Fh+var_60], 0
0x1800f4666  mov     rdi, [rcx+60h]
0x1800f466a  mov     rax, [rdi]
0x1800f466d  mov     rbx, [rax+30h]
0x1800f4671  lea     rcx, [rbp+4Fh+arg_0]
0x1800f4675  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f467a  lea     rdx, [rbp+4Fh+arg_0]
0x1800f467e  mov     rcx, rdi
0x1800f4681  mov     rax, rbx
0x1800f4684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4689  test    eax, eax
0x1800f468b  js      short loc_1800F46A6
0x1800f468d  mov     rcx, [rbp+4Fh+arg_0]
0x1800f4691  test    rcx, rcx
0x1800f4694  jz      short loc_1800F46A6
0x1800f4696  mov     rax, [rcx]
0x1800f4699  lea     rdx, [rbp+4Fh+var_60]
0x1800f469d  mov     rax, [rax+30h]
0x1800f46a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f46a6  mov     [rbp+4Fh+var_58], 0
0x1800f46ae  mov     [rbp+4Fh+var_68], 0
0x1800f46b6  lea     rdx, [rbp+4Fh+var_58]
0x1800f46ba  lea     rcx, [rbp+4Fh+arg_0]
0x1800f46be  call    ??$As@UIWebAccountProvider2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProvider2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider2>>)
0x1800f46c3  test    eax, eax
0x1800f46c5  js      short loc_1800F46E0
0x1800f46c7  mov     rcx, [rbp+4Fh+var_58]
0x1800f46cb  test    rcx, rcx
0x1800f46ce  jz      short loc_1800F46E0
0x1800f46d0  mov     rax, [rcx]
0x1800f46d3  lea     rdx, [rbp+4Fh+var_68]
0x1800f46d7  mov     rax, [rax+38h]
0x1800f46db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f46e0  mov     [rbp+4Fh+var_70], 0
0x1800f46e8  mov     rcx, [rsi+78h]
0x1800f46ec  test    rcx, rcx
0x1800f46ef  jz      short loc_1800F4701
0x1800f46f1  mov     rax, [rcx]
0x1800f46f4  lea     rdx, [rbp+4Fh+var_70]
0x1800f46f8  mov     rax, [rax+30h]
0x1800f46fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4701  mov     [rbp+4Fh+var_78], 0
0x1800f4709  mov     [rbp+4Fh+string], 0
0x1800f4711  mov     rbx, [rbp+4Fh+arg_20]
0x1800f4715  test    rbx, rbx
0x1800f4718  jz      short loc_1800F4740
0x1800f471a  mov     rax, [rbx]
0x1800f471d  lea     rdx, [rbp+4Fh+var_78]
0x1800f4721  mov     rcx, rbx
0x1800f4724  mov     rax, [rax+30h]
0x1800f4728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f472d  mov     rax, [rbx]
0x1800f4730  lea     rdx, [rbp+4Fh+string]
0x1800f4734  mov     rcx, rbx
0x1800f4737  mov     rax, [rax+40h]
0x1800f473b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4740  call    ?Provider@WamClientLogProvider@@SAPEBU_tlgProvider_t@@XZ; WamClientLogProvider::Provider(void)
0x1800f4745  mov     rdi, rax
0x1800f4748  mov     ecx, [rax]
0x1800f474a  cmp     ecx, 5
0x1800f474d  jbe     loc_1800F4870
0x1800f4753  mov     rcx, [rsi+80h]
0x1800f475a  mov     [rbp+4Fh+arg_20], rcx
0x1800f475e  mov     [rbp+4Fh+arg_10], r14d
0x1800f4762  mov     rcx, [rbp+4Fh+string]; string
0x1800f4766  call    cs:__imp_WindowsIsStringEmpty
0x1800f476c  lea     rbx, aNull; "null"
0x1800f4773  test    eax, eax
0x1800f4775  jz      short loc_1800F477C
0x1800f4777  mov     rax, rbx
0x1800f477a  jmp     short loc_1800F4788
0x1800f477c  xor     edx, edx; length
0x1800f477e  mov     rcx, [rbp+4Fh+string]; string
0x1800f4782  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4788  mov     [rbp+4Fh+var_50], rax
0x1800f478c  mov     rcx, [rbp+4Fh+var_78]; string
0x1800f4790  call    cs:__imp_WindowsIsStringEmpty
0x1800f4796  test    eax, eax
0x1800f4798  jz      short loc_1800F479F
0x1800f479a  mov     rax, rbx
0x1800f479d  jmp     short loc_1800F47AB
0x1800f479f  xor     edx, edx; length
0x1800f47a1  mov     rcx, [rbp+4Fh+var_78]; string
0x1800f47a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f47ab  mov     [rbp+4Fh+var_48], rax
0x1800f47af  mov     rcx, [rbp+4Fh+var_70]; string
0x1800f47b3  call    cs:__imp_WindowsIsStringEmpty
0x1800f47b9  test    eax, eax
0x1800f47bb  jz      short loc_1800F47C2
0x1800f47bd  mov     rax, rbx
0x1800f47c0  jmp     short loc_1800F47CE
0x1800f47c2  xor     edx, edx; length
0x1800f47c4  mov     rcx, [rbp+4Fh+var_70]; string
0x1800f47c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f47ce  mov     [rbp+4Fh+var_40], rax
0x1800f47d2  mov     rcx, [rbp+4Fh+var_68]; string
0x1800f47d6  call    cs:__imp_WindowsIsStringEmpty
0x1800f47dc  test    eax, eax
0x1800f47de  jz      short loc_1800F47E5
0x1800f47e0  mov     rax, rbx
0x1800f47e3  jmp     short loc_1800F47F1
0x1800f47e5  xor     edx, edx; length
0x1800f47e7  mov     rcx, [rbp+4Fh+var_68]; string
0x1800f47eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f47f1  mov     [rbp+4Fh+var_38], rax
0x1800f47f5  mov     rcx, [rbp+4Fh+var_60]; string
0x1800f47f9  call    cs:__imp_WindowsIsStringEmpty
0x1800f47ff  test    eax, eax
0x1800f4801  jnz     short loc_1800F4812
0x1800f4803  xor     edx, edx; length
0x1800f4805  mov     rcx, [rbp+4Fh+var_60]; string
0x1800f4809  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f480f  mov     rbx, rax
0x1800f4812  mov     [rbp+4Fh+var_30], rbx
0x1800f4816  mov     r8, [r15+110h]
0x1800f481d  add     r8, 8
0x1800f4821  lea     rax, [rbp+4Fh+arg_20]
0x1800f4825  mov     [rsp+0E0h+var_90], rax
0x1800f482a  lea     rax, [rbp+4Fh+arg_10]
0x1800f482e  mov     [rsp+0E0h+var_98], rax
0x1800f4833  lea     rax, [rbp+4Fh+var_50]
0x1800f4837  mov     [rsp+0E0h+var_A0], rax
0x1800f483c  lea     rax, [rbp+4Fh+var_48]
0x1800f4840  mov     [rsp+0E0h+var_A8], rax
0x1800f4845  lea     rax, [rbp+4Fh+var_40]
0x1800f4849  mov     [rsp+0E0h+var_B0], rax
0x1800f484e  lea     rax, [rbp+4Fh+var_38]
0x1800f4852  mov     [rsp+0E0h+var_B8], rax
0x1800f4857  lea     rax, [rbp+4Fh+var_30]
0x1800f485b  mov     [rsp+0E0h+var_C0], rax
0x1800f4860  lea     rdx, byte_1801541EB
0x1800f4867  mov     rcx, rdi
0x1800f486a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3333AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800f486f  nop
0x1800f4870  mov     rcx, [rbp+4Fh+string]; string
0x1800f4874  test    rcx, rcx
0x1800f4877  jz      short loc_1800F4880
0x1800f4879  call    cs:__imp_WindowsDeleteString
0x1800f487f  nop
0x1800f4880  mov     rcx, [rbp+4Fh+var_78]; string
0x1800f4884  test    rcx, rcx
0x1800f4887  jz      short loc_1800F4890
0x1800f4889  call    cs:__imp_WindowsDeleteString
0x1800f488f  nop
0x1800f4890  mov     rcx, [rbp+4Fh+var_70]; string
0x1800f4894  test    rcx, rcx
0x1800f4897  jz      short loc_1800F48A0
0x1800f4899  call    cs:__imp_WindowsDeleteString
0x1800f489f  nop
0x1800f48a0  mov     rcx, [rbp+4Fh+var_68]; string
0x1800f48a4  test    rcx, rcx
0x1800f48a7  jz      short loc_1800F48B0
0x1800f48a9  call    cs:__imp_WindowsDeleteString
0x1800f48af  nop
0x1800f48b0  lea     rcx, [rbp+4Fh+var_58]
0x1800f48b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f48b9  nop
0x1800f48ba  mov     rcx, [rbp+4Fh+var_60]; string
0x1800f48be  test    rcx, rcx
0x1800f48c1  jz      short loc_1800F48CA
0x1800f48c3  call    cs:__imp_WindowsDeleteString
0x1800f48c9  nop
0x1800f48ca  lea     rcx, [rbp+4Fh+arg_0]
0x1800f48ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f48d3  mov     rbx, [rsp+0E0h+arg_8]
0x1800f48db  add     rsp, 0C0h
0x1800f48e2  pop     r15
0x1800f48e4  pop     r14
0x1800f48e6  pop     rdi
0x1800f48e7  pop     rsi
0x1800f48e8  pop     rbp
0x1800f48e9  retn
```
