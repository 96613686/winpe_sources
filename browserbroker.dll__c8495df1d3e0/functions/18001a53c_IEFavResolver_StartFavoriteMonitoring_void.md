# IEFavResolver::StartFavoriteMonitoring(void)

- ea: `0x18001a53c`
- end: `0x18001a651`
- name: `?StartFavoriteMonitoring@IEFavResolver@@AEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x180001c64`
- `0x18001a53c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a568`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a568`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a558`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a558`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x18001a5cd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHCreateWorkerWindowW` at `0x18001a5cd`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x18001a5f9`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x18001a5f9`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotifyRegister` at `0x18001a62c`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotifyRegister` at `0x18001a62c`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001a640`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001a640`

## pseudocode

```c
__int64 __fastcall IEFavResolver::StartFavoriteMonitoring(IEFavResolver *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  HRESULT v5; // ebx
  __int64 v6; // rax
  ULONG v7; // eax
  ITEMIDLIST *pidl; // rcx
  SHChangeNotifyEntry ppidl[3]; // [rsp+40h] [rbp-28h] BYREF
  char v11; // [rsp+70h] [rbp+8h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v12; // [rsp+78h] [rbp+10h] BYREF
  __int64 CLSID; // [rsp+80h] [rbp+18h] BYREF

  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v11 = 1;
    v12 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
      v2,
      (__int64)byte_1800362E9,
      v3,
      v4,
      &CLSID,
      &v12,
      (__int64)&v11);
  }
  v5 = -2147467259;
  v6 = SHCreateWorkerWindowW(IEFavResolver::s_WndProc, 0, 0, 0, 0, 0);
  *((_QWORD *)this + 3) = v6;
  if ( v6 )
  {
    ppidl[0].pidl = 0;
    ppidl[0].fRecursive = 1;
    v5 = SHGetSpecialFolderLocation(0, 6, (LPITEMIDLIST *)ppidl);
    if ( v5 >= 0 )
    {
      v7 = SHChangeNotifyRegister(*((HWND *)this + 3), 32771, 67252255, 0x610u, 1, ppidl);
      pidl = (ITEMIDLIST *)ppidl[0].pidl;
      *((_DWORD *)this + 4) = v7;
      if ( !v7 )
        v5 = -2147467259;
      ILFree(pidl);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a53c  push    rbx
0x18001a53e  push    rdi
0x18001a53f  push    r14
0x18001a541  sub     rsp, 50h
0x18001a545  mov     eax, cs:dword_18003F000
0x18001a54b  mov     rdi, rcx
0x18001a54e  cmp     eax, 5
0x18001a551  jbe     short loc_18001A5A3
0x18001a553  mov     [rsp+68h+arg_0], 1
0x18001a558  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18001a55e  mov     ecx, 10000003h
0x18001a563  mov     [rsp+68h+arg_8], rax
0x18001a568  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18001a56e  mov     [rsp+68h+arg_10], rax
0x18001a576  lea     rdx, byte_1800362E9
0x18001a57d  lea     rax, [rsp+68h+arg_0]
0x18001a582  mov     [rsp+68h+var_38], rax
0x18001a587  lea     rax, [rsp+68h+arg_8]
0x18001a58c  mov     [rsp+68h+pshcne], rax
0x18001a591  lea     rax, [rsp+68h+arg_10]
0x18001a599  mov     qword ptr [rsp+68h+cEntries], rax
0x18001a59e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x18001a5a3  mov     r14d, 80004005h
0x18001a5a9  mov     [rsp+68h+pshcne], 0
0x18001a5b2  xor     r9d, r9d
0x18001a5b5  mov     qword ptr [rsp+68h+cEntries], 0
0x18001a5be  xor     r8d, r8d
0x18001a5c1  lea     rcx, ?s_WndProc@IEFavResolver@@CA_JPEAUHWND__@@I_K_J@Z; IEFavResolver::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001a5c8  xor     edx, edx
0x18001a5ca  mov     ebx, r14d
0x18001a5cd  call    cs:__imp_SHCreateWorkerWindowW
0x18001a5d3  mov     [rdi+18h], rax
0x18001a5d7  test    rax, rax
0x18001a5da  jz      short loc_18001A646
0x18001a5dc  lea     r8, [rsp+68h+ppidl]; ppidl
0x18001a5e1  mov     [rsp+68h+ppidl], 0
0x18001a5ea  mov     edx, 6; csidl
0x18001a5ef  mov     [rsp+68h+var_20], 1
0x18001a5f7  xor     ecx, ecx; hwnd
0x18001a5f9  call    cs:__imp_SHGetSpecialFolderLocation
0x18001a5ff  mov     ebx, eax
0x18001a601  test    eax, eax
0x18001a603  js      short loc_18001A646
0x18001a605  mov     rcx, [rdi+18h]; hwnd
0x18001a609  lea     rax, [rsp+68h+ppidl]
0x18001a60e  mov     [rsp+68h+pshcne], rax; pshcne
0x18001a613  mov     edx, 8003h; fSources
0x18001a618  mov     r9d, 610h; wMsg
0x18001a61e  mov     [rsp+68h+cEntries], 1; cEntries
0x18001a626  mov     r8d, 402301Fh; fEvents
0x18001a62c  call    cs:__imp_SHChangeNotifyRegister
0x18001a632  mov     rcx, [rsp+68h+ppidl]; pidl
0x18001a637  test    eax, eax
0x18001a639  mov     [rdi+10h], eax
0x18001a63c  cmovz   ebx, r14d
0x18001a640  call    cs:__imp_ILFree
0x18001a646  mov     eax, ebx
0x18001a648  add     rsp, 50h
0x18001a64c  pop     r14
0x18001a64e  pop     rdi
0x18001a64f  pop     rbx
0x18001a650  retn
```
