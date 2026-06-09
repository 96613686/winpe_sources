# BrowserTelemetry::HandleOrderChangedFromEdge<ushort * &,ulong &,long &>(ushort * &,ulong &,long &)

- ea: `0x180016898`
- end: `0x180016941`
- name: `??$HandleOrderChangedFromEdge@AEAPEAGAEAKAEAJ@BrowserTelemetry@@SAXAEAPEAGAEAKAEAJ@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016fa8`

## callees

- `0x180001358`
- `0x1800022d0`
- `0x180016898`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800168ef`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800168ef`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800168e0`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800168e0`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::HandleOrderChangedFromEdge<unsigned short * &,unsigned long &,long &>(__int64 a1)
{
  __int64 result; // rax
  int *v2; // r8
  int *v3; // r9
  __int64 *v4; // r10
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // [rsp+50h] [rbp-20h] BYREF
  int v9; // [rsp+54h] [rbp-1Ch] BYREF
  __int64 v10; // [rsp+58h] [rbp-18h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v11; // [rsp+60h] [rbp-10h] BYREF
  __int64 CLSID; // [rsp+68h] [rbp-8h] BYREF
  char v13; // [rsp+98h] [rbp+28h] BYREF

  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v8 = *v2;
      v9 = *v3;
      v10 = *v4;
      v13 = 1;
      v11 = GlobalThreadState();
      CLSID = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v5,
               (unsigned int)byte_180035993,
               v6,
               v7,
               (__int64)&CLSID,
               (__int64)&v11,
               (__int64)&v13,
               (__int64)&v10,
               (__int64)&v9,
               (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016898  push    rbp
0x18001689a  mov     rbp, rsp
0x18001689d  sub     rsp, 70h
0x1800168a1  mov     eax, cs:dword_18003F000
0x1800168a7  mov     r9, rdx
0x1800168aa  mov     r10, rcx
0x1800168ad  cmp     eax, 5
0x1800168b0  jbe     loc_18001693B
0x1800168b6  mov     rdx, 400000000000h
0x1800168c0  call    _tlgKeywordOn
0x1800168c5  test    al, al
0x1800168c7  jz      short loc_18001693B
0x1800168c9  mov     eax, [r8]
0x1800168cc  mov     [rbp+var_20], eax
0x1800168cf  mov     eax, [r9]
0x1800168d2  mov     [rbp+var_1C], eax
0x1800168d5  mov     rax, [r10]
0x1800168d8  mov     [rbp+var_18], rax
0x1800168dc  mov     [rbp+arg_18], 1
0x1800168e0  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800168e6  mov     ecx, 10000003h
0x1800168eb  mov     [rbp+var_10], rax
0x1800168ef  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800168f5  mov     [rbp+var_8], rax
0x1800168f9  lea     rdx, byte_180035993
0x180016900  lea     rax, [rbp+var_20]
0x180016904  mov     [rsp+70h+var_28], rax
0x180016909  lea     rax, [rbp+var_1C]
0x18001690d  mov     [rsp+70h+var_30], rax
0x180016912  lea     rax, [rbp+var_18]
0x180016916  mov     [rsp+70h+var_38], rax
0x18001691b  lea     rax, [rbp+arg_18]
0x18001691f  mov     [rsp+70h+var_40], rax
0x180016924  lea     rax, [rbp+var_10]
0x180016928  mov     [rsp+70h+var_48], rax
0x18001692d  lea     rax, [rbp+var_8]
0x180016931  mov     [rsp+70h+var_50], rax
0x180016936  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001693b  add     rsp, 70h
0x18001693f  pop     rbp
0x180016940  retn
```
