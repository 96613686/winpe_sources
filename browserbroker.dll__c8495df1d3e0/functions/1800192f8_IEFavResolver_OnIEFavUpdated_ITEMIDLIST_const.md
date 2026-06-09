# IEFavResolver::OnIEFavUpdated(_ITEMIDLIST const *)

- ea: `0x1800192f8`
- end: `0x180019473`
- name: `?OnIEFavUpdated@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, LPCITEMIDLIST pidl)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180018aac`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x180017c44`
- `0x180017cdc`
- `0x180018080`
- `0x180018888`
- `0x1800192f8`
- `0x180019848`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001940e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001940e`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800193fe`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800193fe`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180019331`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180019331`

## pseudocode

```c
__int64 __fastcall IEFavResolver::OnIEFavUpdated(WCHAR *this, LPCITEMIDLIST pidl)
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
                            2,
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
      (__int64)&unk_1800360C0,
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
0x1800192f8  mov     [rsp-8+arg_10], rbx
0x1800192fd  mov     [rsp-8+arg_18], rdi
0x180019302  push    rbp
0x180019303  lea     rbp, [rsp-7B0h]
0x18001930b  sub     rsp, 8B0h
0x180019312  mov     rax, cs:__security_cookie
0x180019319  xor     rax, rsp
0x18001931c  mov     [rbp+7B0h+var_10], rax
0x180019323  mov     rax, rdx
0x180019326  mov     rdi, rcx
0x180019329  mov     rcx, rax; pidl
0x18001932c  lea     rdx, [rsp+8B0h+pszPath]; pszPath
0x180019331  call    cs:__imp_SHGetPathFromIDListW
0x180019337  test    eax, eax
0x180019339  jz      loc_1800193DF
0x18001933f  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180019344  mov     rcx, rdi; this
0x180019347  xor     ebx, ebx
0x180019349  call    ?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z; IEFavResolver::IsInSyncList(ushort *)
0x18001934e  test    al, al
0x180019350  jnz     loc_1800193E4
0x180019356  lea     r8, [rbp+7B0h+var_640]; unsigned __int16 *
0x18001935d  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180019362  call    ?GetFavoriteUrl@IEFavResolver@@AEAAJPEAG0H@Z; IEFavResolver::GetFavoriteUrl(ushort *,ushort *,int)
0x180019367  mov     ebx, eax
0x180019369  test    eax, eax
0x18001936b  js      short loc_1800193E4
0x18001936d  lea     r8, [rbp+7B0h+var_220]; unsigned __int16 *
0x180019374  mov     rcx, rdi; this
0x180019377  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x18001937c  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x180019381  mov     ebx, eax
0x180019383  test    eax, eax
0x180019385  js      short loc_1800193E4
0x180019387  lea     r8, [rbp+7B0h+var_430]; unsigned __int16 *
0x18001938e  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180019393  call    ?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)
0x180019398  mov     ebx, eax
0x18001939a  test    eax, eax
0x18001939c  js      short loc_1800193E4
0x18001939e  lea     rax, dword_18003240C
0x1800193a5  mov     byte ptr [rsp+8B0h+var_878], 0
0x1800193aa  mov     [rsp+8B0h+var_880], rax
0x1800193af  lea     r9, [rbp+7B0h+var_430]
0x1800193b6  mov     [rsp+8B0h+var_888], rax
0x1800193bb  lea     r8, [rbp+7B0h+var_220]
0x1800193c2  lea     rax, [rbp+7B0h+var_640]
0x1800193c9  mov     edx, 2
0x1800193ce  mov     rcx, rdi
0x1800193d1  mov     [rsp+8B0h+var_890], rax
0x1800193d6  call    ?PostFavoriteChangedEventToEdge@IEFavResolver@@AEAAJW4DATACHANGETYPE@@PEBG1111_N@Z; IEFavResolver::PostFavoriteChangedEventToEdge(DATACHANGETYPE,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x1800193db  mov     ebx, eax
0x1800193dd  jmp     short loc_1800193E4
0x1800193df  mov     ebx, 80004005h
0x1800193e4  mov     eax, cs:dword_18003F000
0x1800193ea  cmp     eax, 5
0x1800193ed  jbe     short loc_18001944D
0x1800193ef  lea     rax, [rsp+8B0h+pszPath]
0x1800193f4  mov     [rsp+8B0h+var_870], 1
0x1800193f9  mov     [rsp+8B0h+var_868], rax
0x1800193fe  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019404  mov     ecx, 10000003h
0x180019409  mov     [rsp+8B0h+var_860], rax
0x18001940e  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180019414  mov     [rsp+8B0h+var_858], rax
0x180019419  lea     rdx, unk_1800360C0
0x180019420  lea     rax, [rsp+8B0h+var_868]
0x180019425  mov     [rsp+8B0h+var_878], rax
0x18001942a  lea     rax, [rsp+8B0h+var_870]
0x18001942f  mov     [rsp+8B0h+var_880], rax
0x180019434  lea     rax, [rsp+8B0h+var_860]
0x180019439  mov     [rsp+8B0h+var_888], rax
0x18001943e  lea     rax, [rsp+8B0h+var_858]
0x180019443  mov     [rsp+8B0h+var_890], rax
0x180019448  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18001944d  mov     eax, ebx
0x18001944f  mov     rcx, [rbp+7B0h+var_10]
0x180019456  xor     rcx, rsp; StackCookie
0x180019459  call    __security_check_cookie
0x18001945e  lea     r11, [rsp+8B0h+var_s0]
0x180019466  mov     rbx, [r11+20h]
0x18001946a  mov     rdi, [r11+28h]
0x18001946e  mov     rsp, r11
0x180019471  pop     rbp
0x180019472  retn
```
