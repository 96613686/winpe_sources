# IEFavResolver::ShutdownIEFavResolver(void)

- ea: `0x18001a4ac`
- end: `0x18001a534`
- name: `?ShutdownIEFavResolver@IEFavResolver@@SAXXZ`
- size: `136`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007094`

## callees

- `0x180001c64`
- `0x18001a16c`
- `0x18001a4ac`
- `0x18001a760`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a4d2`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a4d2`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a4c2`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a4c2`

## pseudocode

```c
void IEFavResolver::ShutdownIEFavResolver(void)
{
  __int64 v0; // rcx
  __int64 v1; // r8
  __int64 v2; // r9
  IEFavResolver *v3; // rbx
  IEFavResolver *v4; // rcx
  char v5; // [rsp+50h] [rbp+8h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v6; // [rsp+58h] [rbp+10h] BYREF
  __int64 CLSID; // [rsp+60h] [rbp+18h] BYREF

  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v5 = 1;
    v6 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
      v0,
      (__int64)byte_180036429,
      v1,
      v2,
      &CLSID,
      &v6,
      (__int64)&v5);
  }
  v3 = IEFavResolver::s_ieFavResolver;
  if ( IEFavResolver::s_ieFavResolver )
  {
    v4 = IEFavResolver::s_ieFavResolver;
    IEFavResolver::s_ieFavResolver = 0;
    IEFavResolver::Uninitialize(v4);
    IEFavResolver::Release(v3);
  }
}

```

## disassembly

```asm
0x18001a4ac  push    rbx
0x18001a4ae  sub     rsp, 40h
0x18001a4b2  mov     eax, cs:dword_18003F000
0x18001a4b8  cmp     eax, 5
0x18001a4bb  jbe     short loc_18001A507
0x18001a4bd  mov     [rsp+48h+arg_0], 1
0x18001a4c2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18001a4c8  mov     ecx, 10000003h
0x18001a4cd  mov     [rsp+48h+arg_8], rax
0x18001a4d2  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18001a4d8  mov     [rsp+48h+arg_10], rax
0x18001a4dd  lea     rdx, byte_180036429
0x18001a4e4  lea     rax, [rsp+48h+arg_0]
0x18001a4e9  mov     [rsp+48h+var_18], rax
0x18001a4ee  lea     rax, [rsp+48h+arg_8]
0x18001a4f3  mov     [rsp+48h+var_20], rax
0x18001a4f8  lea     rax, [rsp+48h+arg_10]
0x18001a4fd  mov     [rsp+48h+var_28], rax
0x18001a502  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x18001a507  mov     rbx, cs:?s_ieFavResolver@IEFavResolver@@0PEAV1@EA; IEFavResolver * IEFavResolver::s_ieFavResolver
0x18001a50e  test    rbx, rbx
0x18001a511  jz      short loc_18001A52E
0x18001a513  mov     rcx, rbx; this
0x18001a516  mov     cs:?s_ieFavResolver@IEFavResolver@@0PEAV1@EA, 0; IEFavResolver * IEFavResolver::s_ieFavResolver
0x18001a521  call    ?Uninitialize@IEFavResolver@@AEAAXXZ; IEFavResolver::Uninitialize(void)
0x18001a526  mov     rcx, rbx; this
0x18001a529  call    ?Release@IEFavResolver@@QEAAKXZ; IEFavResolver::Release(void)
0x18001a52e  add     rsp, 40h
0x18001a532  pop     rbx
0x18001a533  retn
```
