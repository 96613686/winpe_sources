# TbLogProvider::TokenBrokerInternalGetWebAccountProviderGuid::StartActivity(IUnknown *,Windows::Security::Credentials::IWebAccountProvider *)

- ea: `0x1800cf66c`
- end: `0x1800cf81c`
- name: `?StartActivity@TokenBrokerInternalGetWebAccountProviderGuid@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `432`
- prototype: `void(TbLogProvider::TokenBrokerInternalGetWebAccountProviderGuid *__hidden this, struct IUnknown *, struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800803f0`

## callees

- `0x180003a8c`
- `0x18000ac90`
- `0x18000f3f4`
- `0x18004384c`
- `0x1800455a4`
- `0x180045b10`
- `0x18007f528`
- `0x1800cf66c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf73c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf73c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf7de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf7ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf7fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf7de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf7ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf7fc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cf72a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cf72a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TbLogProvider::TokenBrokerInternalGetWebAccountProviderGuid::StartActivity(
        TbLogProvider::TokenBrokerInternalGetWebAccountProviderGuid *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  HSTRING v6; // rdi
  int CallingAppName; // eax
  HSTRING v8; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v10; // r9
  const struct _tlgProvider_t *v11; // rsi
  const WCHAR *v12; // rax
  __int64 v13; // r8
  int v14; // ecx
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v16; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int16 v17[4]; // [rsp+60h] [rbp-48h] BYREF
  PCWSTR v18; // [rsp+68h] [rbp-40h] BYREF
  LPWSTR FileNameW; // [rsp+70h] [rbp-38h] BYREF
  PCWSTR v20; // [rsp+78h] [rbp-30h] BYREF
  __int64 v21; // [rsp+80h] [rbp-28h] BYREF
  DWORD CurrentThreadId; // [rsp+C8h] [rbp+20h] BYREF

  string = 0;
  v6 = 0;
  *(_QWORD *)v17 = 0;
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
        v17,
        v10);
      v6 = *(HSTRING *)v17;
    }
    v16 = 0;
    if ( a3 )
      (*((void (__fastcall **)(HSTRING *, HSTRING *))*a3 + 6))(a3, &v16);
    wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v11 = TbLogProvider::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      v18 = WindowsGetStringRawBuffer(v6, 0);
      v12 = WindowsGetStringRawBuffer(v8, 0);
      FileNameW = PathFindFileNameW(v12);
      v20 = WindowsGetStringRawBuffer(v16, 0);
      CurrentThreadId = GetCurrentThreadId();
      v21 = 0;
      v13 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
        v14 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v11,
        (unsigned int)&unk_18014F1C0,
        v13 + 8,
        v14,
        (__int64)&v21,
        (__int64)&CurrentThreadId,
        (__int64)&v20,
        (__int64)&FileNameW,
        (__int64)&v18);
    }
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
    if ( v16 )
      WindowsDeleteString(v16);
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
0x1800cf66c  mov     rax, rsp
0x1800cf66f  mov     [rax+8], rbx
0x1800cf673  mov     [rax+10h], rsi
0x1800cf677  push    rdi
0x1800cf678  push    r14
0x1800cf67a  push    r15
0x1800cf67c  sub     rsp, 90h
0x1800cf683  mov     rsi, r8
0x1800cf686  mov     r15, rdx
0x1800cf689  mov     r14, rcx
0x1800cf68c  mov     qword ptr [rax-58h], 0
0x1800cf694  xor     edi, edi
0x1800cf696  mov     [rax-48h], rdi
0x1800cf69a  lea     rdx, [rax-58h]; struct IUnknown *
0x1800cf69e  mov     rcx, r15; this
0x1800cf6a1  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800cf6a6  mov     rbx, [rsp+0A8h+string]
0x1800cf6ab  test    eax, eax
0x1800cf6ad  js      short loc_1800CF6CF
0x1800cf6af  xor     edx, edx; length
0x1800cf6b1  mov     rcx, rbx; string
0x1800cf6b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf6ba  lea     r8, [rsp+0A8h+var_48]; unsigned __int16 *
0x1800cf6bf  mov     rdx, rax; struct IUnknown *
0x1800cf6c2  mov     rcx, r15; this
0x1800cf6c5  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800cf6ca  mov     rdi, qword ptr [rsp+0A8h+var_48]
0x1800cf6cf  mov     [rsp+0A8h+var_50], 0
0x1800cf6d8  test    rsi, rsi
0x1800cf6db  jz      short loc_1800CF6F1
0x1800cf6dd  mov     rax, [rsi]
0x1800cf6e0  lea     rdx, [rsp+0A8h+var_50]
0x1800cf6e5  mov     rcx, rsi
0x1800cf6e8  mov     rax, [rax+30h]
0x1800cf6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf6f1  mov     rcx, r14
0x1800cf6f4  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800cf6f9  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800cf6fe  mov     rsi, rax
0x1800cf701  mov     ecx, [rax]
0x1800cf703  cmp     ecx, 5
0x1800cf706  jbe     loc_1800CF7CB
0x1800cf70c  xor     edx, edx; length
0x1800cf70e  mov     rcx, rdi; string
0x1800cf711  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf717  mov     [rsp+0A8h+var_40], rax
0x1800cf71c  xor     edx, edx; length
0x1800cf71e  mov     rcx, rbx; string
0x1800cf721  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf727  mov     rcx, rax; pszPath
0x1800cf72a  call    cs:__imp_PathFindFileNameW
0x1800cf730  mov     [rsp+0A8h+var_38], rax
0x1800cf735  xor     edx, edx; length
0x1800cf737  mov     rcx, [rsp+0A8h+var_50]; string
0x1800cf73c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf742  mov     [rsp+0A8h+var_30], rax
0x1800cf747  call    cs:__imp_GetCurrentThreadId
0x1800cf74d  mov     [rsp+0A8h+arg_18], eax
0x1800cf754  mov     [rsp+0A8h+var_28], 0
0x1800cf760  mov     r8, [r14+110h]
0x1800cf767  cmp     byte ptr [r8+4], 0
0x1800cf76c  jz      short loc_1800CF77B
0x1800cf76e  lea     rcx, [r8+18h]; struct _GUID *
0x1800cf772  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800cf777  test    al, al
0x1800cf779  jz      short loc_1800CF77D
0x1800cf77b  xor     ecx, ecx
0x1800cf77d  add     r8, 8
0x1800cf781  lea     rax, [rsp+0A8h+var_40]
0x1800cf786  mov     [rsp+0A8h+var_68], rax
0x1800cf78b  lea     rax, [rsp+0A8h+var_38]
0x1800cf790  mov     [rsp+0A8h+var_70], rax
0x1800cf795  lea     rax, [rsp+0A8h+var_30]
0x1800cf79a  mov     [rsp+0A8h+var_78], rax
0x1800cf79f  lea     rax, [rsp+0A8h+arg_18]
0x1800cf7a7  mov     [rsp+0A8h+var_80], rax
0x1800cf7ac  lea     rax, [rsp+0A8h+var_28]
0x1800cf7b4  mov     [rsp+0A8h+var_88], rax
0x1800cf7b9  mov     r9, rcx
0x1800cf7bc  lea     rdx, unk_18014F1C0
0x1800cf7c3  mov     rcx, rsi
0x1800cf7c6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cf7cb  mov     rcx, r14
0x1800cf7ce  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800cf7d3  nop
0x1800cf7d4  mov     rcx, [rsp+0A8h+var_50]; string
0x1800cf7d9  test    rcx, rcx
0x1800cf7dc  jz      short loc_1800CF7E5
0x1800cf7de  call    cs:__imp_WindowsDeleteString
0x1800cf7e4  nop
0x1800cf7e5  test    rdi, rdi
0x1800cf7e8  jz      short loc_1800CF7F4
0x1800cf7ea  mov     rcx, rdi; string
0x1800cf7ed  call    cs:__imp_WindowsDeleteString
0x1800cf7f3  nop
0x1800cf7f4  test    rbx, rbx
0x1800cf7f7  jz      short loc_1800CF803
0x1800cf7f9  mov     rcx, rbx; string
0x1800cf7fc  call    cs:__imp_WindowsDeleteString
0x1800cf802  nop
0x1800cf803  lea     r11, [rsp+0A8h+var_18]
0x1800cf80b  mov     rbx, [r11+20h]
0x1800cf80f  mov     rsi, [r11+28h]
0x1800cf813  mov     rsp, r11
0x1800cf816  pop     r15
0x1800cf818  pop     r14
0x1800cf81a  pop     rdi
0x1800cf81b  retn
```
