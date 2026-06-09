# TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount::StartActivity(IUnknown *,unsigned __int64)

- ea: `0x180023910`
- end: `0x180023a7a`
- name: `?StartActivity@TokenBrokerInternalGetDefaultSignInAccount@TbLogProvider@@QEAAXPEAUIUnknown@@_K@Z`
- size: `362`
- prototype: `void(TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount *__hidden this, struct IUnknown *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800232e8`

## callees

- `0x18000ac90`
- `0x18000f3f4`
- `0x180023910`
- `0x18004384c`
- `0x1800455a4`
- `0x180045b10`
- `0x18004c814`
- `0x18007f528`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023993`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800239a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023993`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800239a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800239ac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800239ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount::StartActivity(
        TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  int v3; // r15d
  HSTRING v6; // rdi
  int CallingAppName; // eax
  HSTRING v8; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v10; // r9
  const struct _tlgProvider_t *v11; // r14
  const WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  DWORD CurrentThreadId; // [rsp+50h] [rbp-48h] BYREF
  HSTRING string; // [rsp+58h] [rbp-40h] BYREF
  unsigned __int16 v17[4]; // [rsp+60h] [rbp-38h] BYREF
  PCWSTR v18; // [rsp+68h] [rbp-30h] BYREF
  LPWSTR FileNameW; // [rsp+70h] [rbp-28h] BYREF
  __int64 v20; // [rsp+78h] [rbp-20h] BYREF
  int v21; // [rsp+B8h] [rbp+20h] BYREF

  v3 = (int)a3;
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
    wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v11 = TbLogProvider::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      v18 = WindowsGetStringRawBuffer(v6, 0);
      v12 = WindowsGetStringRawBuffer(v8, 0);
      FileNameW = PathFindFileNameW(v12);
      v21 = v3;
      CurrentThreadId = GetCurrentThreadId();
      v20 = 0;
      v13 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
        v14 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v11,
        &word_18014F42E,
        v13 + 8,
        v14,
        &v20,
        &CurrentThreadId,
        &v21,
        &FileNameW,
        &v18);
    }
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
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
0x180023910  mov     rax, rsp
0x180023913  mov     [rax+8], rbx
0x180023917  mov     [rax+10h], rsi
0x18002391b  push    rdi
0x18002391c  push    r14
0x18002391e  push    r15
0x180023920  sub     rsp, 80h
0x180023927  mov     r15, r8
0x18002392a  mov     r14, rdx
0x18002392d  mov     rsi, rcx
0x180023930  mov     qword ptr [rax-40h], 0
0x180023938  xor     edi, edi
0x18002393a  mov     [rax-38h], rdi
0x18002393e  lea     rdx, [rax-40h]; struct IUnknown *
0x180023942  mov     rcx, r14; this
0x180023945  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x18002394a  mov     rbx, [rsp+98h+string]
0x18002394f  test    eax, eax
0x180023951  js      short loc_180023973
0x180023953  xor     edx, edx; length
0x180023955  mov     rcx, rbx; string
0x180023958  call    cs:__imp_WindowsGetStringRawBuffer
0x18002395e  lea     r8, [rsp+98h+var_38]; unsigned __int16 *
0x180023963  mov     rdx, rax; struct IUnknown *
0x180023966  mov     rcx, r14; this
0x180023969  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x18002396e  mov     rdi, qword ptr [rsp+98h+var_38]
0x180023973  mov     rcx, rsi
0x180023976  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002397b  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x180023980  mov     r14, rax
0x180023983  mov     ecx, [rax]
0x180023985  cmp     ecx, 5
0x180023988  jbe     loc_180023A3A
0x18002398e  xor     edx, edx; length
0x180023990  mov     rcx, rdi; string
0x180023993  call    cs:__imp_WindowsGetStringRawBuffer
0x180023999  mov     [rsp+98h+var_30], rax
0x18002399e  xor     edx, edx; length
0x1800239a0  mov     rcx, rbx; string
0x1800239a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800239a9  mov     rcx, rax; pszPath
0x1800239ac  call    cs:__imp_PathFindFileNameW
0x1800239b2  mov     [rsp+98h+var_28], rax
0x1800239b7  mov     [rsp+98h+arg_18], r15d
0x1800239bf  call    cs:__imp_GetCurrentThreadId
0x1800239c5  mov     [rsp+98h+var_48], eax
0x1800239c9  mov     [rsp+98h+var_20], 0
0x1800239d2  mov     r8, [rsi+110h]
0x1800239d9  cmp     byte ptr [r8+4], 0
0x1800239de  jz      short loc_1800239ED
0x1800239e0  lea     rcx, [r8+18h]; struct _GUID *
0x1800239e4  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800239e9  test    al, al
0x1800239eb  jz      short loc_1800239EF
0x1800239ed  xor     ecx, ecx
0x1800239ef  add     r8, 8
0x1800239f3  lea     rax, [rsp+98h+var_30]
0x1800239f8  mov     [rsp+98h+var_58], rax
0x1800239fd  lea     rax, [rsp+98h+var_28]
0x180023a02  mov     [rsp+98h+var_60], rax
0x180023a07  lea     rax, [rsp+98h+arg_18]
0x180023a0f  mov     [rsp+98h+var_68], rax
0x180023a14  lea     rax, [rsp+98h+var_48]
0x180023a19  mov     [rsp+98h+var_70], rax
0x180023a1e  lea     rax, [rsp+98h+var_20]
0x180023a23  mov     [rsp+98h+var_78], rax
0x180023a28  mov     r9, rcx
0x180023a2b  lea     rdx, word_18014F42E
0x180023a32  mov     rcx, r14
0x180023a35  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180023a3a  mov     rcx, rsi
0x180023a3d  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180023a42  nop
0x180023a43  test    rdi, rdi
0x180023a46  jz      short loc_180023A52
0x180023a48  mov     rcx, rdi; string
0x180023a4b  call    cs:__imp_WindowsDeleteString
0x180023a51  nop
0x180023a52  test    rbx, rbx
0x180023a55  jz      short loc_180023A61
0x180023a57  mov     rcx, rbx; string
0x180023a5a  call    cs:__imp_WindowsDeleteString
0x180023a60  nop
0x180023a61  lea     r11, [rsp+98h+var_18]
0x180023a69  mov     rbx, [r11+20h]
0x180023a6d  mov     rsi, [r11+28h]
0x180023a71  mov     rsp, r11
0x180023a74  pop     r15
0x180023a76  pop     r14
0x180023a78  pop     rdi
0x180023a79  retn
```
