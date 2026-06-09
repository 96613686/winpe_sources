# Windows::Security::Authentication::Web::Provider::CWebProviderTokenRequest::TelemetryGetApplicationTokenBindingKeyCallDetails<WamClientLogProvider::WebProviderTokenRequestGetApplicationTokenBindingKey>(WamClientLogProvider::WebProviderTokenRequestGetApplicationTokenBindingKey const &,int,Windows::Security::Authentication::Web::TokenBindingKeyType,Windows::Foundation::IUriRuntimeClass *)

- ea: `0x1800f4370`
- end: `0x1800f462a`
- name: `??$TelemetryGetApplicationTokenBindingKeyCallDetails@VWebProviderTokenRequestGetApplicationTokenBindingKey@WamClientLogProvider@@@CWebProviderTokenRequest@Provider@Web@Authentication@Security@Windows@@AEAAXAEBVWebProviderTokenRequestGetApplicationTokenBindingKey@WamClientLogProvider@@HW4TokenBindingKeyType@2345@PEAUIUriRuntimeClass@Foundation@5@@Z`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800f75b0`

## callees

- `0x180005488`
- `0x180007350`
- `0x180031220`
- `0x1800f0f44`
- `0x1800f4370`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f44c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f44e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f452b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f44c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f44e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f452b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f45e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f44a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f44d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f44f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f44a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f44d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f44f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f4539`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
double __fastcall Windows::Security::Authentication::Web::Provider::CWebProviderTokenRequest::TelemetryGetApplicationTokenBindingKeyCallDetails<WamClientLogProvider::WebProviderTokenRequestGetApplicationTokenBindingKey>(
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
      (unsigned int)&dword_18015427C,
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
0x1800f4370  mov     [rsp-8+arg_8], rbx
0x1800f4375  mov     [rsp-8+arg_10], r8d
0x1800f437a  push    rbp
0x1800f437b  push    rsi
0x1800f437c  push    rdi
0x1800f437d  push    r14
0x1800f437f  push    r15
0x1800f4381  lea     rbp, [rsp-2Fh]
0x1800f4386  sub     rsp, 0C0h
0x1800f438d  mov     r14d, r9d
0x1800f4390  mov     r15, rdx
0x1800f4393  mov     rsi, rcx
0x1800f4396  mov     [rbp+4Fh+arg_0], 0
0x1800f439e  mov     [rbp+4Fh+var_60], 0
0x1800f43a6  mov     rdi, [rcx+60h]
0x1800f43aa  mov     rax, [rdi]
0x1800f43ad  mov     rbx, [rax+30h]
0x1800f43b1  lea     rcx, [rbp+4Fh+arg_0]
0x1800f43b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f43ba  lea     rdx, [rbp+4Fh+arg_0]
0x1800f43be  mov     rcx, rdi
0x1800f43c1  mov     rax, rbx
0x1800f43c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f43c9  test    eax, eax
0x1800f43cb  js      short loc_1800F43E6
0x1800f43cd  mov     rcx, [rbp+4Fh+arg_0]
0x1800f43d1  test    rcx, rcx
0x1800f43d4  jz      short loc_1800F43E6
0x1800f43d6  mov     rax, [rcx]
0x1800f43d9  lea     rdx, [rbp+4Fh+var_60]
0x1800f43dd  mov     rax, [rax+30h]
0x1800f43e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f43e6  mov     [rbp+4Fh+var_58], 0
0x1800f43ee  mov     [rbp+4Fh+var_68], 0
0x1800f43f6  lea     rdx, [rbp+4Fh+var_58]
0x1800f43fa  lea     rcx, [rbp+4Fh+arg_0]
0x1800f43fe  call    ??$As@UIWebAccountProvider2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProvider2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider2>>)
0x1800f4403  test    eax, eax
0x1800f4405  js      short loc_1800F4420
0x1800f4407  mov     rcx, [rbp+4Fh+var_58]
0x1800f440b  test    rcx, rcx
0x1800f440e  jz      short loc_1800F4420
0x1800f4410  mov     rax, [rcx]
0x1800f4413  lea     rdx, [rbp+4Fh+var_68]
0x1800f4417  mov     rax, [rax+38h]
0x1800f441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4420  mov     [rbp+4Fh+var_70], 0
0x1800f4428  mov     rcx, [rsi+78h]
0x1800f442c  test    rcx, rcx
0x1800f442f  jz      short loc_1800F4441
0x1800f4431  mov     rax, [rcx]
0x1800f4434  lea     rdx, [rbp+4Fh+var_70]
0x1800f4438  mov     rax, [rax+30h]
0x1800f443c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4441  mov     [rbp+4Fh+var_78], 0
0x1800f4449  mov     [rbp+4Fh+string], 0
0x1800f4451  mov     rbx, [rbp+4Fh+arg_20]
0x1800f4455  test    rbx, rbx
0x1800f4458  jz      short loc_1800F4480
0x1800f445a  mov     rax, [rbx]
0x1800f445d  lea     rdx, [rbp+4Fh+var_78]
0x1800f4461  mov     rcx, rbx
0x1800f4464  mov     rax, [rax+30h]
0x1800f4468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f446d  mov     rax, [rbx]
0x1800f4470  lea     rdx, [rbp+4Fh+string]
0x1800f4474  mov     rcx, rbx
0x1800f4477  mov     rax, [rax+40h]
0x1800f447b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4480  call    ?Provider@WamClientLogProvider@@SAPEBU_tlgProvider_t@@XZ; WamClientLogProvider::Provider(void)
0x1800f4485  mov     rdi, rax
0x1800f4488  mov     ecx, [rax]
0x1800f448a  cmp     ecx, 5
0x1800f448d  jbe     loc_1800F45B0
0x1800f4493  mov     rcx, [rsi+80h]
0x1800f449a  mov     [rbp+4Fh+arg_20], rcx
0x1800f449e  mov     [rbp+4Fh+arg_10], r14d
0x1800f44a2  mov     rcx, [rbp+4Fh+string]; string
0x1800f44a6  call    cs:__imp_WindowsIsStringEmpty
0x1800f44ac  lea     rbx, aNull; "null"
0x1800f44b3  test    eax, eax
0x1800f44b5  jz      short loc_1800F44BC
0x1800f44b7  mov     rax, rbx
0x1800f44ba  jmp     short loc_1800F44C8
0x1800f44bc  xor     edx, edx; length
0x1800f44be  mov     rcx, [rbp+4Fh+string]; string
0x1800f44c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f44c8  mov     [rbp+4Fh+var_50], rax
0x1800f44cc  mov     rcx, [rbp+4Fh+var_78]; string
0x1800f44d0  call    cs:__imp_WindowsIsStringEmpty
0x1800f44d6  test    eax, eax
0x1800f44d8  jz      short loc_1800F44DF
0x1800f44da  mov     rax, rbx
0x1800f44dd  jmp     short loc_1800F44EB
0x1800f44df  xor     edx, edx; length
0x1800f44e1  mov     rcx, [rbp+4Fh+var_78]; string
0x1800f44e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f44eb  mov     [rbp+4Fh+var_48], rax
0x1800f44ef  mov     rcx, [rbp+4Fh+var_70]; string
0x1800f44f3  call    cs:__imp_WindowsIsStringEmpty
0x1800f44f9  test    eax, eax
0x1800f44fb  jz      short loc_1800F4502
0x1800f44fd  mov     rax, rbx
0x1800f4500  jmp     short loc_1800F450E
0x1800f4502  xor     edx, edx; length
0x1800f4504  mov     rcx, [rbp+4Fh+var_70]; string
0x1800f4508  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f450e  mov     [rbp+4Fh+var_40], rax
0x1800f4512  mov     rcx, [rbp+4Fh+var_68]; string
0x1800f4516  call    cs:__imp_WindowsIsStringEmpty
0x1800f451c  test    eax, eax
0x1800f451e  jz      short loc_1800F4525
0x1800f4520  mov     rax, rbx
0x1800f4523  jmp     short loc_1800F4531
0x1800f4525  xor     edx, edx; length
0x1800f4527  mov     rcx, [rbp+4Fh+var_68]; string
0x1800f452b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4531  mov     [rbp+4Fh+var_38], rax
0x1800f4535  mov     rcx, [rbp+4Fh+var_60]; string
0x1800f4539  call    cs:__imp_WindowsIsStringEmpty
0x1800f453f  test    eax, eax
0x1800f4541  jnz     short loc_1800F4552
0x1800f4543  xor     edx, edx; length
0x1800f4545  mov     rcx, [rbp+4Fh+var_60]; string
0x1800f4549  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f454f  mov     rbx, rax
0x1800f4552  mov     [rbp+4Fh+var_30], rbx
0x1800f4556  mov     r8, [r15+110h]
0x1800f455d  add     r8, 8
0x1800f4561  lea     rax, [rbp+4Fh+arg_20]
0x1800f4565  mov     [rsp+0E0h+var_90], rax
0x1800f456a  lea     rax, [rbp+4Fh+arg_10]
0x1800f456e  mov     [rsp+0E0h+var_98], rax
0x1800f4573  lea     rax, [rbp+4Fh+var_50]
0x1800f4577  mov     [rsp+0E0h+var_A0], rax
0x1800f457c  lea     rax, [rbp+4Fh+var_48]
0x1800f4580  mov     [rsp+0E0h+var_A8], rax
0x1800f4585  lea     rax, [rbp+4Fh+var_40]
0x1800f4589  mov     [rsp+0E0h+var_B0], rax
0x1800f458e  lea     rax, [rbp+4Fh+var_38]
0x1800f4592  mov     [rsp+0E0h+var_B8], rax
0x1800f4597  lea     rax, [rbp+4Fh+var_30]
0x1800f459b  mov     [rsp+0E0h+var_C0], rax
0x1800f45a0  lea     rdx, dword_18015427C
0x1800f45a7  mov     rcx, rdi
0x1800f45aa  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3333AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800f45af  nop
0x1800f45b0  mov     rcx, [rbp+4Fh+string]; string
0x1800f45b4  test    rcx, rcx
0x1800f45b7  jz      short loc_1800F45C0
0x1800f45b9  call    cs:__imp_WindowsDeleteString
0x1800f45bf  nop
0x1800f45c0  mov     rcx, [rbp+4Fh+var_78]; string
0x1800f45c4  test    rcx, rcx
0x1800f45c7  jz      short loc_1800F45D0
0x1800f45c9  call    cs:__imp_WindowsDeleteString
0x1800f45cf  nop
0x1800f45d0  mov     rcx, [rbp+4Fh+var_70]; string
0x1800f45d4  test    rcx, rcx
0x1800f45d7  jz      short loc_1800F45E0
0x1800f45d9  call    cs:__imp_WindowsDeleteString
0x1800f45df  nop
0x1800f45e0  mov     rcx, [rbp+4Fh+var_68]; string
0x1800f45e4  test    rcx, rcx
0x1800f45e7  jz      short loc_1800F45F0
0x1800f45e9  call    cs:__imp_WindowsDeleteString
0x1800f45ef  nop
0x1800f45f0  lea     rcx, [rbp+4Fh+var_58]
0x1800f45f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f45f9  nop
0x1800f45fa  mov     rcx, [rbp+4Fh+var_60]; string
0x1800f45fe  test    rcx, rcx
0x1800f4601  jz      short loc_1800F460A
0x1800f4603  call    cs:__imp_WindowsDeleteString
0x1800f4609  nop
0x1800f460a  lea     rcx, [rbp+4Fh+arg_0]
0x1800f460e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f4613  mov     rbx, [rsp+0E0h+arg_8]
0x1800f461b  add     rsp, 0C0h
0x1800f4622  pop     r15
0x1800f4624  pop     r14
0x1800f4626  pop     rdi
0x1800f4627  pop     rsi
0x1800f4628  pop     rbp
0x1800f4629  retn
```
