# TbLogProvider::InvokePluginToAddAccountSilently::StartActivity(IUnknown *,Windows::Security::Credentials::IWebAccountProvider *)

- ea: `0x1800c38d8`
- end: `0x1800c3aa2`
- name: `?StartActivity@InvokePluginToAddAccountSilently@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `458`
- prototype: `void(TbLogProvider::InvokePluginToAddAccountSilently *__hidden this, struct IUnknown *, struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180081890`

## callees

- `0x180003a8c`
- `0x18000ac90`
- `0x18000f3f4`
- `0x1800455a4`
- `0x180063fc4`
- `0x18007f528`
- `0x1800a939c`
- `0x1800b406c`
- `0x1800c38d8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c39cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c39cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c39a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c39c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c39a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c39c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3a82`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c39b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c39b0`

## pseudocode

```c
void __fastcall TbLogProvider::InvokePluginToAddAccountSilently::StartActivity(
        TbLogProvider::InvokePluginToAddAccountSilently *this,
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
      (unsigned int)&unk_18014CDB8,
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

```

## disassembly

```asm
0x1800c38d8  mov     rax, rsp
0x1800c38db  mov     [rax+8], rbx
0x1800c38df  mov     [rax+10h], rsi
0x1800c38e3  push    rdi
0x1800c38e4  push    r14
0x1800c38e6  push    r15
0x1800c38e8  sub     rsp, 90h
0x1800c38ef  mov     rsi, r8
0x1800c38f2  mov     r15, rdx
0x1800c38f5  mov     r14, rcx
0x1800c38f8  mov     qword ptr [rax-58h], 0
0x1800c3900  xor     edi, edi
0x1800c3902  mov     [rax-48h], rdi
0x1800c3906  lea     rdx, [rax-58h]; struct IUnknown *
0x1800c390a  mov     rcx, r15; this
0x1800c390d  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800c3912  mov     rbx, [rsp+0A8h+string]
0x1800c3917  test    eax, eax
0x1800c3919  js      short loc_1800C393B
0x1800c391b  xor     edx, edx; length
0x1800c391d  mov     rcx, rbx; string
0x1800c3920  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3926  lea     r8, [rsp+0A8h+var_48]; unsigned __int16 *
0x1800c392b  mov     rdx, rax; struct IUnknown *
0x1800c392e  mov     rcx, r15; this
0x1800c3931  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800c3936  mov     rdi, qword ptr [rsp+0A8h+var_48]
0x1800c393b  mov     [rsp+0A8h+var_50], 0
0x1800c3944  test    rsi, rsi
0x1800c3947  jz      short loc_1800C395D
0x1800c3949  mov     rax, [rsi]
0x1800c394c  lea     rdx, [rsp+0A8h+var_50]
0x1800c3951  mov     rcx, rsi
0x1800c3954  mov     rax, [rax+30h]
0x1800c3958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c395d  mov     rcx, r14
0x1800c3960  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800c3965  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800c396a  mov     rsi, rax
0x1800c396d  mov     ecx, [rax]
0x1800c396f  cmp     ecx, 5
0x1800c3972  jbe     loc_1800C3A51
0x1800c3978  mov     rdx, 400000000000h
0x1800c3982  mov     rcx, rax
0x1800c3985  call    _tlgKeywordOn
0x1800c398a  test    al, al
0x1800c398c  jz      loc_1800C3A51
0x1800c3992  xor     edx, edx; length
0x1800c3994  mov     rcx, rdi; string
0x1800c3997  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c399d  mov     [rsp+0A8h+var_40], rax
0x1800c39a2  xor     edx, edx; length
0x1800c39a4  mov     rcx, rbx; string
0x1800c39a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c39ad  mov     rcx, rax; pszPath
0x1800c39b0  call    cs:__imp_PathFindFileNameW
0x1800c39b6  mov     [rsp+0A8h+var_38], rax
0x1800c39bb  xor     edx, edx; length
0x1800c39bd  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c39c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c39c8  mov     [rsp+0A8h+var_30], rax
0x1800c39cd  call    cs:__imp_GetCurrentThreadId
0x1800c39d3  mov     [rsp+0A8h+arg_18], eax
0x1800c39da  mov     [rsp+0A8h+var_28], 1000000h
0x1800c39e6  mov     r8, [r14+110h]
0x1800c39ed  cmp     byte ptr [r8+4], 0
0x1800c39f2  jz      short loc_1800C3A01
0x1800c39f4  lea     rcx, [r8+18h]; struct _GUID *
0x1800c39f8  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800c39fd  test    al, al
0x1800c39ff  jz      short loc_1800C3A03
0x1800c3a01  xor     ecx, ecx
0x1800c3a03  add     r8, 8
0x1800c3a07  lea     rax, [rsp+0A8h+var_40]
0x1800c3a0c  mov     [rsp+0A8h+var_68], rax
0x1800c3a11  lea     rax, [rsp+0A8h+var_38]
0x1800c3a16  mov     [rsp+0A8h+var_70], rax
0x1800c3a1b  lea     rax, [rsp+0A8h+var_30]
0x1800c3a20  mov     [rsp+0A8h+var_78], rax
0x1800c3a25  lea     rax, [rsp+0A8h+arg_18]
0x1800c3a2d  mov     [rsp+0A8h+var_80], rax
0x1800c3a32  lea     rax, [rsp+0A8h+var_28]
0x1800c3a3a  mov     [rsp+0A8h+var_88], rax
0x1800c3a3f  mov     r9, rcx
0x1800c3a42  lea     rdx, unk_18014CDB8
0x1800c3a49  mov     rcx, rsi
0x1800c3a4c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800c3a51  mov     rcx, r14
0x1800c3a54  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800c3a59  nop
0x1800c3a5a  mov     rcx, [rsp+0A8h+var_50]; string
0x1800c3a5f  test    rcx, rcx
0x1800c3a62  jz      short loc_1800C3A6B
0x1800c3a64  call    cs:__imp_WindowsDeleteString
0x1800c3a6a  nop
0x1800c3a6b  test    rdi, rdi
0x1800c3a6e  jz      short loc_1800C3A7A
0x1800c3a70  mov     rcx, rdi; string
0x1800c3a73  call    cs:__imp_WindowsDeleteString
0x1800c3a79  nop
0x1800c3a7a  test    rbx, rbx
0x1800c3a7d  jz      short loc_1800C3A89
0x1800c3a7f  mov     rcx, rbx; string
0x1800c3a82  call    cs:__imp_WindowsDeleteString
0x1800c3a88  nop
0x1800c3a89  lea     r11, [rsp+0A8h+var_18]
0x1800c3a91  mov     rbx, [r11+20h]
0x1800c3a95  mov     rsi, [r11+28h]
0x1800c3a99  mov     rsp, r11
0x1800c3a9c  pop     r15
0x1800c3a9e  pop     r14
0x1800c3aa0  pop     rdi
0x1800c3aa1  retn
```
