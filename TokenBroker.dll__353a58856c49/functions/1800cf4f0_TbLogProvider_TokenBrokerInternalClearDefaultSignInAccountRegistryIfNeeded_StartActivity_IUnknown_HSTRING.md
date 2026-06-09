# TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::StartActivity(IUnknown *,HSTRING__ *)

- ea: `0x1800cf4f0`
- end: `0x1800cf665`
- name: `?StartActivity@TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUHSTRING__@@@Z`
- size: `373`
- prototype: `void(TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *__hidden this, struct IUnknown *, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ccf00`

## callees

- `0x180003a8c`
- `0x18000ac90`
- `0x18000f3f4`
- `0x18004384c`
- `0x1800455a4`
- `0x180045b10`
- `0x18007f528`
- `0x1800cf4f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf5a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf5a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf59c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf59c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf645`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cf58c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cf58c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::StartActivity(
        TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  HSTRING v6; // rdi
  int CallingAppName; // eax
  HSTRING v8; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v10; // r9
  const struct _tlgProvider_t *v11; // rax
  int v12; // r14d
  const WCHAR *v13; // rax
  __int64 v14; // r8
  int v15; // ecx
  HSTRING string; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int16 v17[4]; // [rsp+58h] [rbp-40h] BYREF
  PCWSTR v18; // [rsp+60h] [rbp-38h] BYREF
  LPWSTR FileNameW; // [rsp+68h] [rbp-30h] BYREF
  PCWSTR v20; // [rsp+70h] [rbp-28h] BYREF
  __int64 v21; // [rsp+78h] [rbp-20h] BYREF
  DWORD CurrentThreadId; // [rsp+B8h] [rbp+20h] BYREF

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
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v18 = WindowsGetStringRawBuffer(v6, 0);
      v13 = WindowsGetStringRawBuffer(v8, 0);
      FileNameW = PathFindFileNameW(v13);
      v20 = WindowsGetStringRawBuffer((HSTRING)a3, 0);
      CurrentThreadId = GetCurrentThreadId();
      v21 = 0;
      v14 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v14 + 4) || _tlgGuidIsZero((const struct _GUID *)(v14 + 24)) )
        v15 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&word_18014F126,
        v14 + 8,
        v15,
        (__int64)&v21,
        (__int64)&CurrentThreadId,
        (__int64)&v20,
        (__int64)&FileNameW,
        (__int64)&v18);
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
0x1800cf4f0  mov     rax, rsp
0x1800cf4f3  mov     [rax+8], rbx
0x1800cf4f7  mov     [rax+10h], rsi
0x1800cf4fb  push    rdi
0x1800cf4fc  push    r14
0x1800cf4fe  push    r15
0x1800cf500  sub     rsp, 80h
0x1800cf507  mov     r15, r8
0x1800cf50a  mov     r14, rdx
0x1800cf50d  mov     rsi, rcx
0x1800cf510  mov     qword ptr [rax-48h], 0
0x1800cf518  xor     edi, edi
0x1800cf51a  mov     [rax-40h], rdi
0x1800cf51e  lea     rdx, [rax-48h]; struct IUnknown *
0x1800cf522  mov     rcx, r14; this
0x1800cf525  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800cf52a  mov     rbx, [rsp+98h+string]
0x1800cf52f  test    eax, eax
0x1800cf531  js      short loc_1800CF553
0x1800cf533  xor     edx, edx; length
0x1800cf535  mov     rcx, rbx; string
0x1800cf538  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf53e  lea     r8, [rsp+98h+var_40]; unsigned __int16 *
0x1800cf543  mov     rdx, rax; struct IUnknown *
0x1800cf546  mov     rcx, r14; this
0x1800cf549  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800cf54e  mov     rdi, qword ptr [rsp+98h+var_40]
0x1800cf553  mov     rcx, rsi
0x1800cf556  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800cf55b  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800cf560  mov     r14, rax
0x1800cf563  mov     ecx, [rax]
0x1800cf565  cmp     ecx, 5
0x1800cf568  jbe     loc_1800CF625
0x1800cf56e  xor     edx, edx; length
0x1800cf570  mov     rcx, rdi; string
0x1800cf573  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf579  mov     [rsp+98h+var_38], rax
0x1800cf57e  xor     edx, edx; length
0x1800cf580  mov     rcx, rbx; string
0x1800cf583  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf589  mov     rcx, rax; pszPath
0x1800cf58c  call    cs:__imp_PathFindFileNameW
0x1800cf592  mov     [rsp+98h+var_30], rax
0x1800cf597  xor     edx, edx; length
0x1800cf599  mov     rcx, r15; string
0x1800cf59c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf5a2  mov     [rsp+98h+var_28], rax
0x1800cf5a7  call    cs:__imp_GetCurrentThreadId
0x1800cf5ad  mov     [rsp+98h+arg_18], eax
0x1800cf5b4  mov     [rsp+98h+var_20], 0
0x1800cf5bd  mov     r8, [rsi+110h]
0x1800cf5c4  cmp     byte ptr [r8+4], 0
0x1800cf5c9  jz      short loc_1800CF5D8
0x1800cf5cb  lea     rcx, [r8+18h]; struct _GUID *
0x1800cf5cf  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800cf5d4  test    al, al
0x1800cf5d6  jz      short loc_1800CF5DA
0x1800cf5d8  xor     ecx, ecx
0x1800cf5da  add     r8, 8
0x1800cf5de  lea     rax, [rsp+98h+var_38]
0x1800cf5e3  mov     [rsp+98h+var_58], rax
0x1800cf5e8  lea     rax, [rsp+98h+var_30]
0x1800cf5ed  mov     [rsp+98h+var_60], rax
0x1800cf5f2  lea     rax, [rsp+98h+var_28]
0x1800cf5f7  mov     [rsp+98h+var_68], rax
0x1800cf5fc  lea     rax, [rsp+98h+arg_18]
0x1800cf604  mov     [rsp+98h+var_70], rax
0x1800cf609  lea     rax, [rsp+98h+var_20]
0x1800cf60e  mov     [rsp+98h+var_78], rax
0x1800cf613  mov     r9, rcx
0x1800cf616  lea     rdx, word_18014F126
0x1800cf61d  mov     rcx, r14
0x1800cf620  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cf625  mov     rcx, rsi
0x1800cf628  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800cf62d  nop
0x1800cf62e  test    rdi, rdi
0x1800cf631  jz      short loc_1800CF63D
0x1800cf633  mov     rcx, rdi; string
0x1800cf636  call    cs:__imp_WindowsDeleteString
0x1800cf63c  nop
0x1800cf63d  test    rbx, rbx
0x1800cf640  jz      short loc_1800CF64C
0x1800cf642  mov     rcx, rbx; string
0x1800cf645  call    cs:__imp_WindowsDeleteString
0x1800cf64b  nop
0x1800cf64c  lea     r11, [rsp+98h+var_18]
0x1800cf654  mov     rbx, [r11+20h]
0x1800cf658  mov     rsi, [r11+28h]
0x1800cf65c  mov     rsp, r11
0x1800cf65f  pop     r15
0x1800cf661  pop     r14
0x1800cf663  pop     rdi
0x1800cf664  retn
```
