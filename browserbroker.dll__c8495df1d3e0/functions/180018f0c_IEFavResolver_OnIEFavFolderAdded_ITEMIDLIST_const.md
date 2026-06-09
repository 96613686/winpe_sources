# IEFavResolver::OnIEFavFolderAdded(_ITEMIDLIST const *)

- ea: `0x180018f0c`
- end: `0x180019080`
- name: `?OnIEFavFolderAdded@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `372`
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
- `0x180017f60`
- `0x180018080`
- `0x180018888`
- `0x180018f0c`
- `0x180019848`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001901b`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001901b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001900b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001900b`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180018f4a`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180018f4a`

## pseudocode

```c
__int64 __fastcall IEFavResolver::OnIEFavFolderAdded(WCHAR *this, LPCITEMIDLIST pidl)
{
  int FavoriteTitle; // ebx
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

  FavoriteTitle = -2147467259;
  if ( SHGetPathFromIDListW(pidl, pszPath) )
  {
    FavoriteTitle = 0;
    if ( !IEFavResolver::IsInSyncList((IEFavResolver *)this, pszPath) )
    {
      FavoriteTitle = IEFavResolver::GetFavoriteTitle(v4, pszPath, v19, v5);
      if ( FavoriteTitle >= 0 )
      {
        FavoriteTitle = IEFavResolver::GetParentFolderPath(v6, pszPath, v18, v7);
        if ( FavoriteTitle >= 0 )
        {
          FavoriteTitle = IEFavResolver::GetUnifiedFolderPath(this, v18, v20);
          if ( FavoriteTitle >= 0 )
          {
            v12 = 1;
            FavoriteTitle = IEFavResolver::PostFavoriteChangedEventToEdge(
                              this,
                              1,
                              v20,
                              v19,
                              &dword_18003240C,
                              &dword_18003240C,
                              &dword_18003240C,
                              v12);
          }
        }
      }
    }
  }
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v13[0] = 1;
    v14 = pszPath;
    v15 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v8,
      (__int64)byte_180036211,
      v9,
      v10,
      &CLSID,
      (__int64 *)&v15,
      (__int64)v13,
      (const WCHAR **)&v14);
  }
  return (unsigned int)FavoriteTitle;
}

```

## disassembly

```asm
0x180018f0c  mov     [rsp-8+arg_10], rbx
0x180018f11  mov     [rsp-8+arg_18], rdi
0x180018f16  push    rbp
0x180018f17  lea     rbp, [rsp-7B0h]
0x180018f1f  sub     rsp, 8B0h
0x180018f26  mov     rax, cs:__security_cookie
0x180018f2d  xor     rax, rsp
0x180018f30  mov     [rbp+7B0h+var_10], rax
0x180018f37  mov     rax, rdx
0x180018f3a  mov     rdi, rcx
0x180018f3d  mov     rcx, rax; pidl
0x180018f40  lea     rdx, [rsp+8B0h+pszPath]; pszPath
0x180018f45  mov     ebx, 80004005h
0x180018f4a  call    cs:__imp_SHGetPathFromIDListW
0x180018f50  test    eax, eax
0x180018f52  jz      loc_180018FF1
0x180018f58  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018f5d  mov     rcx, rdi; this
0x180018f60  xor     ebx, ebx
0x180018f62  call    ?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z; IEFavResolver::IsInSyncList(ushort *)
0x180018f67  test    al, al
0x180018f69  jnz     loc_180018FF1
0x180018f6f  lea     r8, [rbp+7B0h+var_430]; unsigned __int16 *
0x180018f76  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018f7b  call    ?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)
0x180018f80  mov     ebx, eax
0x180018f82  test    eax, eax
0x180018f84  js      short loc_180018FF1
0x180018f86  lea     r8, [rbp+7B0h+var_640]; unsigned __int16 *
0x180018f8d  lea     rdx, [rsp+8B0h+pszPath]; unsigned __int16 *
0x180018f92  call    ?GetParentFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetParentFolderPath(ushort const *,ushort *,int)
0x180018f97  mov     ebx, eax
0x180018f99  test    eax, eax
0x180018f9b  js      short loc_180018FF1
0x180018f9d  lea     r8, [rbp+7B0h+var_220]; unsigned __int16 *
0x180018fa4  mov     rcx, rdi; this
0x180018fa7  lea     rdx, [rbp+7B0h+var_640]; unsigned __int16 *
0x180018fae  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x180018fb3  mov     ebx, eax
0x180018fb5  test    eax, eax
0x180018fb7  js      short loc_180018FF1
0x180018fb9  lea     rax, dword_18003240C
0x180018fc0  mov     byte ptr [rsp+8B0h+var_878], 1
0x180018fc5  mov     [rsp+8B0h+var_880], rax
0x180018fca  lea     r9, [rbp+7B0h+var_430]
0x180018fd1  mov     [rsp+8B0h+var_888], rax
0x180018fd6  lea     r8, [rbp+7B0h+var_220]
0x180018fdd  mov     edx, 1
0x180018fe2  mov     [rsp+8B0h+var_890], rax
0x180018fe7  mov     rcx, rdi
0x180018fea  call    ?PostFavoriteChangedEventToEdge@IEFavResolver@@AEAAJW4DATACHANGETYPE@@PEBG1111_N@Z; IEFavResolver::PostFavoriteChangedEventToEdge(DATACHANGETYPE,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180018fef  mov     ebx, eax
0x180018ff1  mov     eax, cs:dword_18003F000
0x180018ff7  cmp     eax, 5
0x180018ffa  jbe     short loc_18001905A
0x180018ffc  lea     rax, [rsp+8B0h+pszPath]
0x180019001  mov     [rsp+8B0h+var_870], 1
0x180019006  mov     [rsp+8B0h+var_868], rax
0x18001900b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019011  mov     ecx, 10000003h
0x180019016  mov     [rsp+8B0h+var_860], rax
0x18001901b  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180019021  mov     [rsp+8B0h+var_858], rax
0x180019026  lea     rdx, byte_180036211
0x18001902d  lea     rax, [rsp+8B0h+var_868]
0x180019032  mov     [rsp+8B0h+var_878], rax
0x180019037  lea     rax, [rsp+8B0h+var_870]
0x18001903c  mov     [rsp+8B0h+var_880], rax
0x180019041  lea     rax, [rsp+8B0h+var_860]
0x180019046  mov     [rsp+8B0h+var_888], rax
0x18001904b  lea     rax, [rsp+8B0h+var_858]
0x180019050  mov     [rsp+8B0h+var_890], rax
0x180019055  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18001905a  mov     eax, ebx
0x18001905c  mov     rcx, [rbp+7B0h+var_10]
0x180019063  xor     rcx, rsp; StackCookie
0x180019066  call    __security_check_cookie
0x18001906b  lea     r11, [rsp+8B0h+var_s0]
0x180019073  mov     rbx, [r11+20h]
0x180019077  mov     rdi, [r11+28h]
0x18001907b  mov     rsp, r11
0x18001907e  pop     rbp
0x18001907f  retn
```
