# BrowserTelemetry::ElevationBrokerFailedToStartCrossProcessMessaging<bool,bool,bool>(bool &&,bool &&,bool &&)

- ea: `0x180005be8`
- end: `0x180005c90`
- name: `??$ElevationBrokerFailedToStartCrossProcessMessaging@_N_N_N@BrowserTelemetry@@SAX$$QEA_N00@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cd20`

## callees

- `0x1800011c4`
- `0x180001358`
- `0x180005be8`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180005c3e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180005c3e`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180005c2f`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180005c2f`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::ElevationBrokerFailedToStartCrossProcessMessaging<bool,bool,bool>(__int64 a1)
{
  __int64 result; // rax
  char *v2; // r8
  char *v3; // r9
  char *v4; // r10
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  char v8; // [rsp+50h] [rbp-20h] BYREF
  char v9; // [rsp+51h] [rbp-1Fh] BYREF
  char v10[6]; // [rsp+52h] [rbp-1Eh] BYREF
  struct IE_GLOBAL_THREAD_STATE *v11; // [rsp+58h] [rbp-18h] BYREF
  __int64 CLSID; // [rsp+60h] [rbp-10h] BYREF
  char v13; // [rsp+98h] [rbp+28h] BYREF

  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v13 = *v2;
      v8 = *v3;
      v9 = *v4;
      v10[0] = 1;
      v11 = GlobalThreadState();
      CLSID = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
               v5,
               (unsigned int)byte_180034B19,
               v6,
               v7,
               (__int64)&CLSID,
               (__int64)&v11,
               (__int64)v10,
               (__int64)&v9,
               (__int64)&v8,
               (__int64)&v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005be8  push    rbp
0x180005bea  mov     rbp, rsp
0x180005bed  sub     rsp, 70h
0x180005bf1  mov     eax, cs:dword_18003F000
0x180005bf7  mov     r9, rdx
0x180005bfa  mov     r10, rcx
0x180005bfd  cmp     eax, 5
0x180005c00  jbe     loc_180005C8A
0x180005c06  mov     rdx, 400000000000h
0x180005c10  call    _tlgKeywordOn
0x180005c15  test    al, al
0x180005c17  jz      short loc_180005C8A
0x180005c19  mov     al, [r8]
0x180005c1c  mov     [rbp+arg_18], al
0x180005c1f  mov     al, [r9]
0x180005c22  mov     [rbp+var_20], al
0x180005c25  mov     al, [r10]
0x180005c28  mov     [rbp+var_1F], al
0x180005c2b  mov     [rbp+var_1E], 1
0x180005c2f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180005c35  mov     ecx, 10000003h
0x180005c3a  mov     [rbp+var_18], rax
0x180005c3e  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180005c44  mov     [rbp+var_10], rax
0x180005c48  lea     rdx, byte_180034B19
0x180005c4f  lea     rax, [rbp+arg_18]
0x180005c53  mov     [rsp+70h+var_28], rax
0x180005c58  lea     rax, [rbp+var_20]
0x180005c5c  mov     [rsp+70h+var_30], rax
0x180005c61  lea     rax, [rbp+var_1F]
0x180005c65  mov     [rsp+70h+var_38], rax
0x180005c6a  lea     rax, [rbp+var_1E]
0x180005c6e  mov     [rsp+70h+var_40], rax
0x180005c73  lea     rax, [rbp+var_18]
0x180005c77  mov     [rsp+70h+var_48], rax
0x180005c7c  lea     rax, [rbp+var_10]
0x180005c80  mov     [rsp+70h+var_50], rax
0x180005c85  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x180005c8a  add     rsp, 70h
0x180005c8e  pop     rbp
0x180005c8f  retn
```
