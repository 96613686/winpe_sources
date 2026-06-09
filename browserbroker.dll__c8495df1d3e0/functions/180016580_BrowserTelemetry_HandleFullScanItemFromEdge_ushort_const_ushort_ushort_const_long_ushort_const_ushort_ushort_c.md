# BrowserTelemetry::HandleFullScanItemFromEdge<ushort const * &,ushort * &,ushort const * &,long &>(ushort const * &,ushort * &,ushort const * &,long &)

- ea: `0x180016580`
- end: `0x180016646`
- name: `??$HandleFullScanItemFromEdge@AEAPEBGAEAPEAGAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAPEBGAEAPEAG0AEAJ@Z`
- size: `198`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800173a8`

## callees

- `0x180001358`
- `0x18000206c`
- `0x180016580`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800165e8`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800165e8`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800165d9`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800165d9`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::HandleFullScanItemFromEdge<unsigned short const * &,unsigned short * &,unsigned short const * &,long &>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 *v2; // r8
  int *v3; // r9
  __int64 *v4; // r10
  __int64 *v5; // r11
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char v9[4]; // [rsp+60h] [rbp+27h] BYREF
  int v10; // [rsp+64h] [rbp+2Bh] BYREF
  __int64 v11; // [rsp+68h] [rbp+2Fh] BYREF
  __int64 v12; // [rsp+70h] [rbp+37h] BYREF
  __int64 v13; // [rsp+78h] [rbp+3Fh] BYREF
  struct IE_GLOBAL_THREAD_STATE *v14; // [rsp+80h] [rbp+47h] BYREF
  __int64 CLSID; // [rsp+88h] [rbp+4Fh] BYREF

  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v10 = *v3;
      v11 = *v2;
      v12 = *v4;
      v13 = *v5;
      v9[0] = 1;
      v14 = GlobalThreadState();
      CLSID = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v6,
               (unsigned int)&dword_18003587C,
               v7,
               v8,
               (__int64)&CLSID,
               (__int64)&v14,
               (__int64)v9,
               (__int64)&v13,
               (__int64)&v12,
               (__int64)&v11,
               (__int64)&v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016580  push    rbp
0x180016582  lea     rbp, [rsp-57h]
0x180016587  sub     rsp, 90h
0x18001658e  mov     eax, cs:dword_18003F000
0x180016594  mov     r10, rdx
0x180016597  mov     r11, rcx
0x18001659a  cmp     eax, 5
0x18001659d  jbe     loc_18001663D
0x1800165a3  mov     rdx, 400000000000h
0x1800165ad  call    _tlgKeywordOn
0x1800165b2  test    al, al
0x1800165b4  jz      loc_18001663D
0x1800165ba  mov     eax, [r9]
0x1800165bd  mov     [rbp+57h+var_2C], eax
0x1800165c0  mov     rax, [r8]
0x1800165c3  mov     [rbp+57h+var_28], rax
0x1800165c7  mov     rax, [r10]
0x1800165ca  mov     [rbp+57h+var_20], rax
0x1800165ce  mov     rax, [r11]
0x1800165d1  mov     [rbp+57h+var_18], rax
0x1800165d5  mov     [rbp+57h+var_30], 1
0x1800165d9  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800165df  mov     ecx, 10000003h
0x1800165e4  mov     [rbp+57h+var_10], rax
0x1800165e8  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800165ee  mov     [rbp+57h+var_8], rax
0x1800165f2  lea     rdx, dword_18003587C
0x1800165f9  lea     rax, [rbp+57h+var_2C]
0x1800165fd  mov     [rsp+90h+var_40], rax
0x180016602  lea     rax, [rbp+57h+var_28]
0x180016606  mov     [rsp+90h+var_48], rax
0x18001660b  lea     rax, [rbp+57h+var_20]
0x18001660f  mov     [rsp+90h+var_50], rax
0x180016614  lea     rax, [rbp+57h+var_18]
0x180016618  mov     [rsp+90h+var_58], rax
0x18001661d  lea     rax, [rbp+57h+var_30]
0x180016621  mov     [rsp+90h+var_60], rax
0x180016626  lea     rax, [rbp+57h+var_10]
0x18001662a  mov     [rsp+90h+var_68], rax
0x18001662f  lea     rax, [rbp+57h+var_8]
0x180016633  mov     [rsp+90h+var_70], rax
0x180016638  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@55AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001663d  add     rsp, 90h
0x180016644  pop     rbp
0x180016645  retn
```
