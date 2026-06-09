# BrowserTelemetry::HandleItemUpdatedFromEdge<ushort const * &,ushort const * &,ushort const * &,ushort const * &,long &>(ushort const * &,ushort const * &,ushort const * &,ushort const * &,long &)

- ea: `0x1800167b8`
- end: `0x180016891`
- name: `??$HandleItemUpdatedFromEdge@AEAPEBGAEAPEBGAEAPEBGAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAPEBG000AEAJ@Z`
- size: `217`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a80c`

## callees

- `0x180001358`
- `0x180001eec`
- `0x1800167b8`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001682a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001682a`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001681b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001681b`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::HandleItemUpdatedFromEdge<unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &,long &>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  __int64 result; // rax
  __int64 *v6; // r8
  __int64 *v7; // r9
  __int64 *v8; // r10
  __int64 *v9; // r11
  int v10; // ecx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  char v14[4]; // [rsp+60h] [rbp+Fh] BYREF
  int v15; // [rsp+64h] [rbp+13h] BYREF
  __int64 v16; // [rsp+68h] [rbp+17h] BYREF
  __int64 v17; // [rsp+70h] [rbp+1Fh] BYREF
  __int64 v18; // [rsp+78h] [rbp+27h] BYREF
  __int64 v19; // [rsp+80h] [rbp+2Fh] BYREF
  struct IE_GLOBAL_THREAD_STATE *v20; // [rsp+88h] [rbp+37h] BYREF
  __int64 CLSID; // [rsp+90h] [rbp+3Fh] BYREF

  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v14[0] = 1;
      v10 = *a5;
      v16 = *v7;
      v17 = *v6;
      v18 = *v8;
      v19 = *v9;
      v15 = v10;
      v20 = GlobalThreadState();
      CLSID = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
               v11,
               (unsigned int)&unk_180035AA8,
               v12,
               v13,
               (__int64)&CLSID,
               (__int64)&v20,
               (__int64)v14,
               (__int64)&v19,
               (__int64)&v18,
               (__int64)&v17,
               (__int64)&v16,
               (__int64)&v15);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800167b8  push    rbp
0x1800167ba  lea     rbp, [rsp-4Fh]
0x1800167bf  sub     rsp, 0A0h
0x1800167c6  mov     eax, cs:dword_18003F000
0x1800167cc  mov     r10, rdx
0x1800167cf  mov     r11, rcx
0x1800167d2  cmp     eax, 5
0x1800167d5  jbe     loc_180016888
0x1800167db  mov     rdx, 400000000000h
0x1800167e5  call    _tlgKeywordOn
0x1800167ea  test    al, al
0x1800167ec  jz      loc_180016888
0x1800167f2  mov     rax, [rbp+4Fh+arg_20]
0x1800167f6  mov     [rbp+4Fh+var_40], 1
0x1800167fa  mov     ecx, [rax]
0x1800167fc  mov     rax, [r9]
0x1800167ff  mov     [rbp+4Fh+var_38], rax
0x180016803  mov     rax, [r8]
0x180016806  mov     [rbp+4Fh+var_30], rax
0x18001680a  mov     rax, [r10]
0x18001680d  mov     [rbp+4Fh+var_28], rax
0x180016811  mov     rax, [r11]
0x180016814  mov     [rbp+4Fh+var_20], rax
0x180016818  mov     [rbp+4Fh+var_3C], ecx
0x18001681b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180016821  mov     ecx, 10000003h
0x180016826  mov     [rbp+4Fh+var_18], rax
0x18001682a  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180016830  mov     [rbp+4Fh+var_10], rax
0x180016834  lea     rdx, unk_180035AA8
0x18001683b  lea     rax, [rbp+4Fh+var_3C]
0x18001683f  mov     [rsp+0A0h+var_48], rax
0x180016844  lea     rax, [rbp+4Fh+var_38]
0x180016848  mov     [rsp+0A0h+var_50], rax
0x18001684d  lea     rax, [rbp+4Fh+var_30]
0x180016851  mov     [rsp+0A0h+var_58], rax
0x180016856  lea     rax, [rbp+4Fh+var_28]
0x18001685a  mov     [rsp+0A0h+var_60], rax
0x18001685f  lea     rax, [rbp+4Fh+var_20]
0x180016863  mov     [rsp+0A0h+var_68], rax
0x180016868  lea     rax, [rbp+4Fh+var_40]
0x18001686c  mov     [rsp+0A0h+var_70], rax
0x180016871  lea     rax, [rbp+4Fh+var_18]
0x180016875  mov     [rsp+0A0h+var_78], rax
0x18001687a  lea     rax, [rbp+4Fh+var_10]
0x18001687e  mov     [rsp+0A0h+var_80], rax
0x180016883  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U3@U3@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@555AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180016888  add     rsp, 0A0h
0x18001688f  pop     rbp
0x180016890  retn
```
