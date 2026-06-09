# BrowserTelemetry::HandleFullScanFromEdge<ulong &,ulong &>(ulong &,ulong &)

- ea: `0x1800164d0`
- end: `0x180016579`
- name: `??$HandleFullScanFromEdge@AEAKAEAK@BrowserTelemetry@@SAXAEAK0@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800173a8`

## callees

- `0x180001358`
- `0x1800014ec`
- `0x1800164d0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180016525`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180016525`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180016515`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180016515`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::HandleFullScanFromEdge<unsigned long &,unsigned long &>(__int64 a1)
{
  __int64 result; // rax
  int *v2; // r8
  int *v3; // r9
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // [rsp+50h] [rbp-28h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v8; // [rsp+58h] [rbp-20h] BYREF
  __int64 v9[3]; // [rsp+60h] [rbp-18h] BYREF
  char v10; // [rsp+90h] [rbp+18h] BYREF
  int v11; // [rsp+98h] [rbp+20h] BYREF

  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v11 = *v2;
      v7 = *v3;
      v10 = 1;
      v8 = GlobalThreadState();
      v9[0] = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v4,
               (unsigned int)byte_180035909,
               v5,
               v6,
               (__int64)v9,
               (__int64)&v8,
               (__int64)&v10,
               (__int64)&v7,
               (__int64)&v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800164d0  sub     rsp, 78h
0x1800164d4  mov     eax, cs:dword_18003F000
0x1800164da  mov     r8, rdx
0x1800164dd  mov     r9, rcx
0x1800164e0  cmp     eax, 5
0x1800164e3  jbe     loc_180016574
0x1800164e9  mov     rdx, 400000000000h
0x1800164f3  call    _tlgKeywordOn
0x1800164f8  test    al, al
0x1800164fa  jz      short loc_180016574
0x1800164fc  mov     eax, [r8]
0x1800164ff  mov     [rsp+78h+arg_18], eax
0x180016506  mov     eax, [r9]
0x180016509  mov     [rsp+78h+var_28], eax
0x18001650d  mov     [rsp+78h+arg_10], 1
0x180016515  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18001651b  mov     ecx, 10000003h
0x180016520  mov     [rsp+78h+var_20], rax
0x180016525  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18001652b  mov     [rsp+78h+var_18], rax
0x180016530  lea     rdx, byte_180035909
0x180016537  lea     rax, [rsp+78h+arg_18]
0x18001653f  mov     [rsp+78h+var_38], rax
0x180016544  lea     rax, [rsp+78h+var_28]
0x180016549  mov     [rsp+78h+var_40], rax
0x18001654e  lea     rax, [rsp+78h+arg_10]
0x180016556  mov     [rsp+78h+var_48], rax
0x18001655b  lea     rax, [rsp+78h+var_20]
0x180016560  mov     [rsp+78h+var_50], rax
0x180016565  lea     rax, [rsp+78h+var_18]
0x18001656a  mov     [rsp+78h+var_58], rax
0x18001656f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016574  add     rsp, 78h
0x180016578  retn
```
