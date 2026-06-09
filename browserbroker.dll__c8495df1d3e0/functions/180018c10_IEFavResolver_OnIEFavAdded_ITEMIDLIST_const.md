# IEFavResolver::OnIEFavAdded(_ITEMIDLIST const *)

- ea: `0x180018c10`
- end: `0x180018d8b`
- name: `?OnIEFavAdded@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, LPCITEMIDLIST pidl)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018aac`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x180017c44`
- `0x180017cdc`
- `0x180018080`
- `0x180018888`
- `0x180018c10`
- `0x180019848`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180018d26`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180018d26`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180018d16`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180018d16`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180018c49`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180018c49`

## pseudocode

```c
__int64 __fastcall IEFavResolver::OnIEFavAdded(WCHAR *this, LPCITEMIDLIST pidl)
{
  int FavoriteUrl; // ebx
  IEFavResolver *v4; // rcx
  int v5; // r9d
  IEFavResolver *v6; // rcx
  int v7; // r9d
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  char v12; // [rsp+38h] [rbp-C8h]
  char v13[8]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v14; // [rsp+48h] [rbp-B8h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 CLSID; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v18[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v19[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v20[264]; // [rsp+690h] [rbp+590h] BYREF

  if ( SHGetPathFromIDListW(pidl, pszPath) )
  {
    FavoriteUrl = 0;
    if ( !IEFavResolver::IsInSyncList((IEFavResolver *)this, pszPath) )
    {
      FavoriteUrl = IEFavResolver::GetFavoriteUrl(v4, pszPath, v18, v5);
      if ( FavoriteUrl >= 0 )
      {
        FavoriteUrl = IEFavResolver::GetUnifiedFolderPath(this, pszPath, v20);
        if ( FavoriteUrl >= 0 )
        {
          FavoriteUrl = IEFavResolver::GetFavoriteTitle(v6, pszPath, v19, v7);
          if ( FavoriteUrl >= 0 )
          {
            v12 = 0;
            FavoriteUrl = IEFavResolver::PostFavoriteChangedEventToEdge(
                            this,
                            1,
                            v20,
                            v19,
                            v18,
                            &dword_18003240C,
                            &dword_18003240C,
                            v12);
          }
        }
      }
    }
  }
  else
  {
    FavoriteUrl = -2147467259;
  }
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v13[0] = 1;
    v14 = pszPath;
    v15 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v8,
      (__int64)byte_180036281,
      v9,
      v10,
      &CLSID,
      (__int64 *)&v15,
      (__int64)v13,
      (const WCHAR **)&v14);
  }
  return (unsigned int)FavoriteUrl;
}

```

## disassembly

```asm
0x180018c10  mov     [rsp-8+arg_10], rbx
0x180018c15  mov     [rsp-8+arg_18], rdi
0x180018c1a  push    rbp
0x180018c1b  lea     rbp, [rsp-7B0h]
0x180018c23  sub     rsp, 8B0h
0x180018c2a  mov     rax, cs:__security_cookie
0x180018c31  xor     rax, rsp
0x180018c34  mov     [rbp+7B0h+var_10], rax
0x180018c3b  mov     rax, rdx
0x180018c3e  mov     rdi, rcx
0x180018c41  mov     rcx, rax; pidl
0x180018c44  lea     rdx, [rsp+8B0h+pszPath]; pszPath
0x180018c49  call    cs:__imp_SHGetPathFromIDListW
0x180018c4f  test    eax, eax
0x180018c51  jz      loc_180018CF7
0x180018c57  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018c5c  mov     rcx, rdi; this
0x180018c5f  xor     ebx, ebx
0x180018c61  call    ?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z; IEFavResolver::IsInSyncList(ushort *)
0x180018c66  test    al, al
0x180018c68  jnz     loc_180018CFC
0x180018c6e  lea     r8, [rbp+7B0h+var_640]; unsigned __int16 *
0x180018c75  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018c7a  call    ?GetFavoriteUrl@IEFavResolver@@AEAAJPEAG0H@Z; IEFavResolver::GetFavoriteUrl(ushort *,ushort *,int)
0x180018c7f  mov     ebx, eax
0x180018c81  test    eax, eax
0x180018c83  js      short loc_180018CFC
0x180018c85  lea     r8, [rbp+7B0h+var_220]; unsigned __int16 *
0x180018c8c  mov     rcx, rdi; this
0x180018c8f  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018c94  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x180018c99  mov     ebx, eax
0x180018c9b  test    eax, eax
0x180018c9d  js      short loc_180018CFC
0x180018c9f  lea     r8, [rbp+7B0h+var_430]; unsigned __int16 *
0x180018ca6  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018cab  call    ?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)
0x180018cb0  mov     ebx, eax
0x180018cb2  test    eax, eax
0x180018cb4  js      short loc_180018CFC
0x180018cb6  lea     rax, dword_18003240C
0x180018cbd  mov     byte ptr [rsp+8B0h+var_878], 0
0x180018cc2  mov     [rsp+8B0h+var_880], rax
0x180018cc7  lea     r9, [rbp+7B0h+var_430]
0x180018cce  mov     [rsp+8B0h+var_888], rax
0x180018cd3  lea     r8, [rbp+7B0h+var_220]
0x180018cda  lea     rax, [rbp+7B0h+var_640]
0x180018ce1  mov     edx, 1
0x180018ce6  mov     rcx, rdi
0x180018ce9  mov     [rsp+8B0h+var_890], rax
0x180018cee  call    ?PostFavoriteChangedEventToEdge@IEFavResolver@@AEAAJW4DATACHANGETYPE@@PEBG1111_N@Z; IEFavResolver::PostFavoriteChangedEventToEdge(DATACHANGETYPE,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180018cf3  mov     ebx, eax
0x180018cf5  jmp     short loc_180018CFC
0x180018cf7  mov     ebx, 80004005h
0x180018cfc  mov     eax, cs:dword_18003F000
0x180018d02  cmp     eax, 5
0x180018d05  jbe     short loc_180018D65
0x180018d07  lea     rax, [rsp+8B0h+pszPath]
0x180018d0c  mov     [rsp+8B0h+var_870], 1
0x180018d11  mov     [rsp+8B0h+var_868], rax
0x180018d16  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180018d1c  mov     ecx, 10000003h
0x180018d21  mov     [rsp+8B0h+var_860], rax
0x180018d26  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180018d2c  mov     [rsp+8B0h+var_858], rax
0x180018d31  lea     rdx, byte_180036281
0x180018d38  lea     rax, [rsp+8B0h+var_868]
0x180018d3d  mov     [rsp+8B0h+var_878], rax
0x180018d42  lea     rax, [rsp+8B0h+var_870]
0x180018d47  mov     [rsp+8B0h+var_880], rax
0x180018d4c  lea     rax, [rsp+8B0h+var_860]
0x180018d51  mov     [rsp+8B0h+var_888], rax
0x180018d56  lea     rax, [rsp+8B0h+var_858]
0x180018d5b  mov     [rsp+8B0h+var_890], rax
0x180018d60  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180018d65  mov     eax, ebx
0x180018d67  mov     rcx, [rbp+7B0h+var_10]
0x180018d6e  xor     rcx, rsp; StackCookie
0x180018d71  call    __security_check_cookie
0x180018d76  lea     r11, [rsp+8B0h+var_s0]
0x180018d7e  mov     rbx, [r11+20h]
0x180018d82  mov     rdi, [r11+28h]
0x180018d86  mov     rsp, r11
0x180018d89  pop     rbp
0x180018d8a  retn
```
