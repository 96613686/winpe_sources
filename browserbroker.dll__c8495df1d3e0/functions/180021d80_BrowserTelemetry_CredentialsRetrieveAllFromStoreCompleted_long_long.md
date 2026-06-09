# BrowserTelemetry::CredentialsRetrieveAllFromStoreCompleted<long &>(long &)

- ea: `0x180021d80`
- end: `0x180021e05`
- name: `??$CredentialsRetrieveAllFromStoreCompleted@AEAJ@BrowserTelemetry@@SAXAEAJ@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002420c`

## callees

- `0x180001010`
- `0x180001358`
- `0x180021d80`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180021dc1`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180021dc1`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180021db1`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180021db1`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::CredentialsRetrieveAllFromStoreCompleted<long &>(__int64 a1)
{
  __int64 result; // rax
  int *v2; // r8
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  __int64 v6[3]; // [rsp+40h] [rbp-18h] BYREF
  char v7; // [rsp+68h] [rbp+10h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v9; // [rsp+78h] [rbp+20h] BYREF

  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v8 = *v2;
      v7 = 1;
      v9 = GlobalThreadState();
      v6[0] = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
               v3,
               (unsigned int)&unk_180036490,
               v4,
               v5,
               (__int64)v6,
               (__int64)&v9,
               (__int64)&v7,
               (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021d80  sub     rsp, 58h
0x180021d84  mov     eax, cs:dword_18003F000
0x180021d8a  mov     r8, rcx
0x180021d8d  cmp     eax, 5
0x180021d90  jbe     short loc_180021E00
0x180021d92  mov     rdx, 400000000000h
0x180021d9c  call    _tlgKeywordOn
0x180021da1  test    al, al
0x180021da3  jz      short loc_180021E00
0x180021da5  mov     eax, [r8]
0x180021da8  mov     [rsp+58h+arg_10], eax
0x180021dac  mov     [rsp+58h+arg_8], 1
0x180021db1  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180021db7  mov     ecx, 10000003h
0x180021dbc  mov     [rsp+58h+arg_18], rax
0x180021dc1  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180021dc7  mov     [rsp+58h+var_18], rax
0x180021dcc  lea     rdx, unk_180036490
0x180021dd3  lea     rax, [rsp+58h+arg_10]
0x180021dd8  mov     [rsp+58h+var_20], rax
0x180021ddd  lea     rax, [rsp+58h+arg_8]
0x180021de2  mov     [rsp+58h+var_28], rax
0x180021de7  lea     rax, [rsp+58h+arg_18]
0x180021dec  mov     [rsp+58h+var_30], rax
0x180021df1  lea     rax, [rsp+58h+var_18]
0x180021df6  mov     [rsp+58h+var_38], rax
0x180021dfb  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180021e00  add     rsp, 58h
0x180021e04  retn
```
