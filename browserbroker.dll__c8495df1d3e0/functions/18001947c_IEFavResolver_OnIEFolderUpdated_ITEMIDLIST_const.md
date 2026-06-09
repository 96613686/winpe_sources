# IEFavResolver::OnIEFolderUpdated(_ITEMIDLIST const *)

- ea: `0x18001947c`
- end: `0x180019535`
- name: `?OnIEFolderUpdated@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `185`
- prototype: `int(IEFavResolver *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180018aac`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x18001947c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800194db`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800194db`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800194cb`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800194cb`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x18001949f`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x18001949f`

## pseudocode

```c
__int64 __fastcall IEFavResolver::OnIEFolderUpdated(IEFavResolver *this, const struct _ITEMIDLIST *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  char v7[8]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR *v8; // [rsp+48h] [rbp-240h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v9; // [rsp+50h] [rbp-238h] BYREF
  __int64 CLSID; // [rsp+58h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-228h] BYREF

  v2 = SHGetPathFromIDListW(a2, pszPath) ? 0 : 0x80004005;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v7[0] = 1;
    v8 = pszPath;
    v9 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v3,
      (__int64)byte_180036053,
      v4,
      v5,
      &CLSID,
      (__int64 *)&v9,
      (__int64)v7,
      (const WCHAR **)&v8);
  }
  return v2;
}

```

## disassembly

```asm
0x18001947c  push    rbx
0x18001947e  sub     rsp, 280h
0x180019485  mov     rax, cs:__security_cookie
0x18001948c  xor     rax, rsp
0x18001948f  mov     [rsp+288h+var_18], rax
0x180019497  mov     rcx, rdx; pidl
0x18001949a  lea     rdx, [rsp+288h+pszPath]; pszPath
0x18001949f  call    cs:__imp_SHGetPathFromIDListW
0x1800194a5  neg     eax
0x1800194a7  mov     eax, cs:dword_18003F000
0x1800194ad  sbb     ebx, ebx
0x1800194af  not     ebx
0x1800194b1  and     ebx, 80004005h
0x1800194b7  cmp     eax, 5
0x1800194ba  jbe     short loc_18001951A
0x1800194bc  lea     rax, [rsp+288h+pszPath]
0x1800194c1  mov     [rsp+288h+var_248], 1
0x1800194c6  mov     [rsp+288h+var_240], rax
0x1800194cb  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800194d1  mov     ecx, 10000003h
0x1800194d6  mov     [rsp+288h+var_238], rax
0x1800194db  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800194e1  mov     [rsp+288h+var_230], rax
0x1800194e6  lea     rdx, byte_180036053
0x1800194ed  lea     rax, [rsp+288h+var_240]
0x1800194f2  mov     [rsp+288h+var_250], rax
0x1800194f7  lea     rax, [rsp+288h+var_248]
0x1800194fc  mov     [rsp+288h+var_258], rax
0x180019501  lea     rax, [rsp+288h+var_238]
0x180019506  mov     [rsp+288h+var_260], rax
0x18001950b  lea     rax, [rsp+288h+var_230]
0x180019510  mov     [rsp+288h+var_268], rax
0x180019515  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18001951a  mov     eax, ebx
0x18001951c  mov     rcx, [rsp+288h+var_18]
0x180019524  xor     rcx, rsp; StackCookie
0x180019527  call    __security_check_cookie
0x18001952c  add     rsp, 280h
0x180019533  pop     rbx
0x180019534  retn
```
