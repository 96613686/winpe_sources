# BrowserTelemetry::HandleItemDeletedFromEdge<ushort const * &,ushort const * &,long &>(ushort const * &,ushort const * &,long &)

- ea: `0x180016700`
- end: `0x1800167b0`
- name: `??$HandleItemDeletedFromEdge@AEAPEBGAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAPEBG0AEAJ@Z`
- size: `176`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800179f0`

## callees

- `0x180001358`
- `0x1800021b8`
- `0x180016700`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001675b`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001675b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001674c`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001674c`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::HandleItemDeletedFromEdge<unsigned short const * &,unsigned short const * &,long &>(
        __int64 a1)
{
  __int64 result; // rax
  int *v2; // r8
  __int64 *v3; // r9
  __int64 *v4; // r10
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // [rsp+50h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-20h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v11; // [rsp+68h] [rbp-18h] BYREF
  __int64 CLSID; // [rsp+70h] [rbp-10h] BYREF
  char v13; // [rsp+A8h] [rbp+28h] BYREF

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
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v5,
               (unsigned int)&byte_180035A1F,
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
0x180016700  push    rbp
0x180016702  mov     rbp, rsp
0x180016705  sub     rsp, 80h
0x18001670c  mov     eax, cs:dword_18003F000
0x180016712  mov     r9, rdx
0x180016715  mov     r10, rcx
0x180016718  cmp     eax, 5
0x18001671b  jbe     loc_1800167A7
0x180016721  mov     rdx, 400000000000h
0x18001672b  call    _tlgKeywordOn
0x180016730  test    al, al
0x180016732  jz      short loc_1800167A7
0x180016734  mov     eax, [r8]
0x180016737  mov     [rbp+var_30], eax
0x18001673a  mov     rax, [r9]
0x18001673d  mov     [rbp+var_28], rax
0x180016741  mov     rax, [r10]
0x180016744  mov     [rbp+var_20], rax
0x180016748  mov     [rbp+arg_18], 1
0x18001674c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180016752  mov     ecx, 10000003h
0x180016757  mov     [rbp+var_18], rax
0x18001675b  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180016761  mov     [rbp+var_10], rax
0x180016765  lea     rdx, byte_180035A1F
0x18001676c  lea     rax, [rbp+var_30]
0x180016770  mov     [rsp+80h+var_38], rax
0x180016775  lea     rax, [rbp+var_28]
0x180016779  mov     [rsp+80h+var_40], rax
0x18001677e  lea     rax, [rbp+var_20]
0x180016782  mov     [rsp+80h+var_48], rax
0x180016787  lea     rax, [rbp+arg_18]
0x18001678b  mov     [rsp+80h+var_50], rax
0x180016790  lea     rax, [rbp+var_18]
0x180016794  mov     [rsp+80h+var_58], rax
0x180016799  lea     rax, [rbp+var_10]
0x18001679d  mov     [rsp+80h+var_60], rax
0x1800167a2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800167a7  add     rsp, 80h
0x1800167ae  pop     rbp
0x1800167af  retn
```
