# TbLogProvider::FindAllSecondaryAccountsAsync::StartActivity(IUnknown *,Windows::Security::Credentials::IWebAccountProvider *)

- ea: `0x1800c3708`
- end: `0x1800c38d2`
- name: `?StartActivity@FindAllSecondaryAccountsAsync@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `458`
- prototype: `void(TbLogProvider::FindAllSecondaryAccountsAsync *__hidden this, struct IUnknown *, struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800899a0`

## callees

- `0x180003a8c`
- `0x18000ac90`
- `0x18000f3f4`
- `0x1800455a4`
- `0x180063fc4`
- `0x18007f528`
- `0x1800a939c`
- `0x1800b406c`
- `0x1800c3708`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c37fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c37fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c37c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c37d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c37f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c37c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c37d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c37f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c38b2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c37e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c37e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TbLogProvider::FindAllSecondaryAccountsAsync::StartActivity(
        TbLogProvider::FindAllSecondaryAccountsAsync *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  HSTRING v6; // rdi
  int CallingAppName; // eax
  HSTRING v8; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v10; // r9
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  int v13; // esi
  const WCHAR *v14; // rax
  __int64 v15; // r8
  int v16; // ecx
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v18; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int16 v19[4]; // [rsp+60h] [rbp-48h] BYREF
  PCWSTR v20; // [rsp+68h] [rbp-40h] BYREF
  LPWSTR FileNameW; // [rsp+70h] [rbp-38h] BYREF
  PCWSTR v22; // [rsp+78h] [rbp-30h] BYREF
  __int64 v23; // [rsp+80h] [rbp-28h] BYREF
  DWORD CurrentThreadId; // [rsp+C8h] [rbp+20h] BYREF

  string = 0;
  v6 = 0;
  *(_QWORD *)v19 = 0;
  try
  {
    CallingAppName = Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(
                       (Windows::Internal::Security::Authentication::TokenBroker *)a2,
                       (struct IUnknown *)&string,
                       a3);
    v8 = string;
    if ( CallingAppName >= 0 )
    {
      StringRawBuffer = (struct IUnknown *)WindowsGetStringRawBuffer(string, 0);
      Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(
        (Windows::Internal::Security::Authentication::TokenBroker *)a2,
        StringRawBuffer,
        v19,
        v10);
      v6 = *(HSTRING *)v19;
    }
    v18 = 0;
    if ( a3 )
      (*((void (__fastcall **)(HSTRING *, HSTRING *))*a3 + 6))(a3, &v18);
    wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v11 = TbLogProvider::Provider();
    v13 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12) )
    {
      v20 = WindowsGetStringRawBuffer(v6, 0);
      v14 = WindowsGetStringRawBuffer(v8, 0);
      FileNameW = PathFindFileNameW(v14);
      v22 = WindowsGetStringRawBuffer(v18, 0);
      CurrentThreadId = GetCurrentThreadId();
      v23 = 0x1000000;
      v15 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v15 + 4) || _tlgGuidIsZero((const struct _GUID *)(v15 + 24)) )
        v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v13,
        (unsigned int)&word_18014CD3E,
        v15 + 8,
        v16,
        (__int64)&v23,
        (__int64)&CurrentThreadId,
        (__int64)&v22,
        (__int64)&FileNameW,
        (__int64)&v20);
    }
    wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v6 )
      WindowsDeleteString(v6);
    if ( v8 )
      WindowsDeleteString(v8);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800c3708  mov     rax, rsp
0x1800c370b  mov     [rax+8], rbx
0x1800c370f  mov     [rax+10h], rsi
0x1800c3713  push    rdi
0x1800c3714  push    r14
0x1800c3716  push    r15
0x1800c3718  sub     rsp, 90h
0x1800c371f  mov     rsi, r8
0x1800c3722  mov     r15, rdx
0x1800c3725  mov     r14, rcx
0x1800c3728  mov     qword ptr [rax-58h], 0
0x1800c3730  xor     edi, edi
0x1800c3732  mov     [rax-48h], rdi
0x1800c3736  lea     rdx, [rax-58h]; struct IUnknown *
0x1800c373a  mov     rcx, r15; this
0x1800c373d  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800c3742  mov     rbx, [rsp+0A8h+string]
0x1800c3747  test    eax, eax
0x1800c3749  js      short loc_1800C376B
0x1800c374b  xor     edx, edx; length
0x1800c374d  mov     rcx, rbx; string
0x1800c3750  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3756  lea     r8, [rsp+0A8h+var_48]; unsigned __int16 *
0x1800c375b  mov     rdx, rax; struct IUnknown *
0x1800c375e  mov     rcx, r15; this
0x1800c3761  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800c3766  mov     rdi, qword ptr [rsp+0A8h+var_48]
0x1800c376b  mov     [rsp+0A8h+var_50], 0
0x1800c3774  test    rsi, rsi
0x1800c3777  jz      short loc_1800C378D
0x1800c3779  mov     rax, [rsi]
0x1800c377c  lea     rdx, [rsp+0A8h+var_50]
0x1800c3781  mov     rcx, rsi
0x1800c3784  mov     rax, [rax+30h]
0x1800c3788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c378d  mov     rcx, r14
0x1800c3790  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800c3795  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800c379a  mov     rsi, rax
0x1800c379d  mov     ecx, [rax]
0x1800c379f  cmp     ecx, 5
0x1800c37a2  jbe     loc_1800C3881
0x1800c37a8  mov     rdx, 400000000000h
0x1800c37b2  mov     rcx, rax
0x1800c37b5  call    _tlgKeywordOn
0x1800c37ba  test    al, al
0x1800c37bc  jz      loc_1800C3881
0x1800c37c2  xor     edx, edx; length
0x1800c37c4  mov     rcx, rdi; string
0x1800c37c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c37cd  mov     [rsp+0A8h+var_40], rax
0x1800c37d2  xor     edx, edx; length
0x1800c37d4  mov     rcx, rbx; string
0x1800c37d7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c37dd  mov     rcx, rax; pszPath
0x1800c37e0  call    cs:__imp_PathFindFileNameW
0x1800c37e6  mov     [rsp+0A8h+var_38], rax
0x1800c37eb  xor     edx, edx; length
0x1800c37ed  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c37f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c37f8  mov     [rsp+0A8h+var_30], rax
0x1800c37fd  call    cs:__imp_GetCurrentThreadId
0x1800c3803  mov     [rsp+0A8h+arg_18], eax
0x1800c380a  mov     [rsp+0A8h+var_28], 1000000h
0x1800c3816  mov     r8, [r14+110h]
0x1800c381d  cmp     byte ptr [r8+4], 0
0x1800c3822  jz      short loc_1800C3831
0x1800c3824  lea     rcx, [r8+18h]; struct _GUID *
0x1800c3828  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800c382d  test    al, al
0x1800c382f  jz      short loc_1800C3833
0x1800c3831  xor     ecx, ecx
0x1800c3833  add     r8, 8
0x1800c3837  lea     rax, [rsp+0A8h+var_40]
0x1800c383c  mov     [rsp+0A8h+var_68], rax
0x1800c3841  lea     rax, [rsp+0A8h+var_38]
0x1800c3846  mov     [rsp+0A8h+var_70], rax
0x1800c384b  lea     rax, [rsp+0A8h+var_30]
0x1800c3850  mov     [rsp+0A8h+var_78], rax
0x1800c3855  lea     rax, [rsp+0A8h+arg_18]
0x1800c385d  mov     [rsp+0A8h+var_80], rax
0x1800c3862  lea     rax, [rsp+0A8h+var_28]
0x1800c386a  mov     [rsp+0A8h+var_88], rax
0x1800c386f  mov     r9, rcx
0x1800c3872  lea     rdx, word_18014CD3E
0x1800c3879  mov     rcx, rsi
0x1800c387c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800c3881  mov     rcx, r14
0x1800c3884  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800c3889  nop
0x1800c388a  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c388f  test    rcx, rcx
0x1800c3892  jz      short loc_1800C389B
0x1800c3894  call    cs:__imp_WindowsDeleteString
0x1800c389a  nop
0x1800c389b  test    rdi, rdi
0x1800c389e  jz      short loc_1800C38AA
0x1800c38a0  mov     rcx, rdi; string
0x1800c38a3  call    cs:__imp_WindowsDeleteString
0x1800c38a9  nop
0x1800c38aa  test    rbx, rbx
0x1800c38ad  jz      short loc_1800C38B9
0x1800c38af  mov     rcx, rbx; string
0x1800c38b2  call    cs:__imp_WindowsDeleteString
0x1800c38b8  nop
0x1800c38b9  lea     r11, [rsp+0A8h+var_18]
0x1800c38c1  mov     rbx, [r11+20h]
0x1800c38c5  mov     rsi, [r11+28h]
0x1800c38c9  mov     rsp, r11
0x1800c38cc  pop     r15
0x1800c38ce  pop     r14
0x1800c38d0  pop     rdi
0x1800c38d1  retn
```
