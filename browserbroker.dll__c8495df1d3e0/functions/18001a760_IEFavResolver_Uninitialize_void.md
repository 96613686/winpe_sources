# IEFavResolver::Uninitialize(void)

- ea: `0x18001a760`
- end: `0x18001a806`
- name: `?Uninitialize@IEFavResolver@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(IEFavResolver *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a4ac`

## callees

- `0x180001c64`
- `0x18001a760`

## import_xrefs

- `iertutil!__imp_DPA_DestroyCallback` at `0x18001a7ef`
- `iertutil!__imp_DPA_DestroyCallback` at `0x18001a7ef`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a789`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a789`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a779`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a779`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18001a7c2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18001a7c2`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotifyDeregister` at `0x18001a7d3`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotifyDeregister` at `0x18001a7d3`

## pseudocode

```c
void __fastcall IEFavResolver::Uninitialize(HWND *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  ULONG v5; // ecx
  struct _DPA *v6; // rcx
  char v7; // [rsp+50h] [rbp+8h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 CLSID; // [rsp+60h] [rbp+18h] BYREF

  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v7 = 1;
    v8 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
      v2,
      (__int64)byte_1800363CB,
      v3,
      v4,
      &CLSID,
      &v8,
      (__int64)&v7);
  }
  DestroyWindow(this[3]);
  v5 = *((_DWORD *)this + 4);
  this[3] = 0;
  SHChangeNotifyDeregister(v5);
  v6 = (struct _DPA *)this[72];
  if ( v6 )
  {
    DPA_DestroyCallback(v6, (PFNDAENUMCALLBACK)DPA_DeleteCB<SYNCITEM>, 0);
    this[72] = 0;
  }
}

```

## disassembly

```asm
0x18001a760  push    rbx
0x18001a762  sub     rsp, 40h
0x18001a766  mov     eax, cs:dword_18003F000
0x18001a76c  mov     rbx, rcx
0x18001a76f  cmp     eax, 5
0x18001a772  jbe     short loc_18001A7BE
0x18001a774  mov     [rsp+48h+arg_0], 1
0x18001a779  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18001a77f  mov     ecx, 10000003h
0x18001a784  mov     [rsp+48h+arg_8], rax
0x18001a789  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18001a78f  mov     [rsp+48h+arg_10], rax
0x18001a794  lea     rdx, byte_1800363CB
0x18001a79b  lea     rax, [rsp+48h+arg_0]
0x18001a7a0  mov     [rsp+48h+var_18], rax
0x18001a7a5  lea     rax, [rsp+48h+arg_8]
0x18001a7aa  mov     [rsp+48h+var_20], rax
0x18001a7af  lea     rax, [rsp+48h+arg_10]
0x18001a7b4  mov     [rsp+48h+var_28], rax
0x18001a7b9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x18001a7be  mov     rcx, [rbx+18h]; hWnd
0x18001a7c2  call    cs:__imp_DestroyWindow
0x18001a7c8  mov     ecx, [rbx+10h]; ulID
0x18001a7cb  mov     qword ptr [rbx+18h], 0
0x18001a7d3  call    cs:__imp_SHChangeNotifyDeregister
0x18001a7d9  mov     rcx, [rbx+240h]; hdpa
0x18001a7e0  test    rcx, rcx
0x18001a7e3  jz      short loc_18001A800
0x18001a7e5  xor     r8d, r8d; pData
0x18001a7e8  lea     rdx, ??$DPA_DeleteCB@USYNCITEM@@@@YAHPEAUSYNCITEM@@PEAX@Z; pfnCB
0x18001a7ef  call    cs:__imp_DPA_DestroyCallback
0x18001a7f5  mov     qword ptr [rbx+240h], 0
0x18001a800  add     rsp, 40h
0x18001a804  pop     rbx
0x18001a805  retn
```
