# IEFavResolver::OnIEFavRenamed(_ITEMIDLIST const *,_ITEMIDLIST const *,bool)

- ea: `0x180019088`
- end: `0x1800192ef`
- name: `?OnIEFavRenamed@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@0_N@Z`
- size: `615`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018aac`

## callees

- `0x180001d04`
- `0x180002ce0`
- `0x180017c44`
- `0x180017cdc`
- `0x180017f60`
- `0x180018080`
- `0x180018888`
- `0x180019088`
- `0x180019848`
- `0x18002b4e0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001927d`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001927d`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001926d`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001926d`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x1800190d0`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x1800190e5`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x1800190d0`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x1800190e5`

## pseudocode

```c
__int64 __fastcall IEFavResolver::OnIEFavRenamed(
        WCHAR *this,
        const struct _ITEMIDLIST *a2,
        const struct _ITEMIDLIST *a3,
        char a4)
{
  int FavoriteTitle; // ebx
  IEFavResolver *v8; // rcx
  int v9; // r9d
  IEFavResolver *v10; // rcx
  int v11; // r9d
  IEFavResolver *v12; // rcx
  int v13; // r9d
  IEFavResolver *v14; // rcx
  int v15; // r9d
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  char v21; // [rsp+50h] [rbp-B0h] BYREF
  char v22[7]; // [rsp+51h] [rbp-AFh] BYREF
  WCHAR *v23; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v24; // [rsp+60h] [rbp-A0h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 CLSID; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v27[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPath[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v29[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v30[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v31[264]; // [rsp+8C0h] [rbp+7C0h] BYREF
  unsigned __int16 v32[264]; // [rsp+AD0h] [rbp+9D0h] BYREF
  unsigned __int16 v33[264]; // [rsp+CE0h] [rbp+BE0h] BYREF
  unsigned __int16 v34[264]; // [rsp+EF0h] [rbp+DF0h] BYREF
  unsigned __int16 v35[264]; // [rsp+1100h] [rbp+1000h] BYREF

  FavoriteTitle = -2147467259;
  if ( SHGetPathFromIDListW(a2, pszPath) )
  {
    if ( SHGetPathFromIDListW(a3, v27) )
    {
      FavoriteTitle = 0;
      if ( !IEFavResolver::IsInSyncList((IEFavResolver *)this, pszPath)
        && !IEFavResolver::IsInSyncList((IEFavResolver *)this, v27) )
      {
        if ( IEFavResolver::GetFavoriteTitle(v8, pszPath, v29, v9) >= 0
          && IEFavResolver::GetParentFolderPath(v10, pszPath, v33, v11) >= 0 )
        {
          IEFavResolver::GetUnifiedFolderPath(this, v33, v32);
        }
        FavoriteTitle = IEFavResolver::GetFavoriteTitle(v10, v27, v31, v11);
        if ( FavoriteTitle >= 0 )
        {
          FavoriteTitle = IEFavResolver::GetParentFolderPath(v12, v27, v34, v13);
          if ( FavoriteTitle >= 0 )
          {
            FavoriteTitle = IEFavResolver::GetUnifiedFolderPath(this, v34, v30);
            if ( FavoriteTitle >= 0 )
            {
              if ( a4 )
              {
                v16 = IEFavResolver::PostFavoriteChangedEventToEdge(this, 2, v32, v31, &dword_18003240C, v30, v29, a4);
              }
              else
              {
                FavoriteTitle = IEFavResolver::GetFavoriteUrl(v14, v27, v35, v15);
                if ( FavoriteTitle < 0 )
                  goto LABEL_16;
                v16 = IEFavResolver::PostFavoriteChangedEventToEdge(this, 2, v32, v31, v35, v30, v29, 0);
              }
              FavoriteTitle = v16;
            }
          }
        }
      }
    }
  }
LABEL_16:
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v21 = a4;
    v23 = v27;
    v24 = pszPath;
    v22[0] = 1;
    v25 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v17,
      (__int64)word_18003612A,
      v18,
      v19,
      &CLSID,
      (__int64 *)&v25,
      (__int64)v22,
      (__int64)&v21,
      (const WCHAR **)&v24,
      (const WCHAR **)&v23);
  }
  return (unsigned int)FavoriteTitle;
}

```

## disassembly

```asm
0x180019088  push    rbp
0x18001908a  push    rbx
0x18001908b  push    rsi
0x18001908c  push    rdi
0x18001908d  push    r14
0x18001908f  lea     rbp, [rsp-1220h]
0x180019097  mov     eax, 1320h
0x18001909c  call    _alloca_probe
0x1800190a1  sub     rsp, rax
0x1800190a4  mov     rax, cs:__security_cookie
0x1800190ab  xor     rax, rsp
0x1800190ae  mov     [rbp+1240h+var_30], rax
0x1800190b5  mov     rax, rdx
0x1800190b8  mov     rdi, rcx
0x1800190bb  mov     rcx, rax; pidl
0x1800190be  lea     rdx, [rbp+1240h+pszPath]; pszPath
0x1800190c5  mov     sil, r9b
0x1800190c8  mov     r14, r8
0x1800190cb  mov     ebx, 80004005h
0x1800190d0  call    cs:__imp_SHGetPathFromIDListW
0x1800190d6  test    eax, eax
0x1800190d8  jz      loc_18001923F
0x1800190de  lea     rdx, [rbp+1240h+var_12C0]; pszPath
0x1800190e2  mov     rcx, r14; pidl
0x1800190e5  call    cs:__imp_SHGetPathFromIDListW
0x1800190eb  test    eax, eax
0x1800190ed  jz      loc_18001923F
0x1800190f3  lea     rdx, [rbp+1240h+pszPath]; unsigned __int16 *
0x1800190fa  mov     rcx, rdi; this
0x1800190fd  xor     ebx, ebx
0x1800190ff  call    ?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z; IEFavResolver::IsInSyncList(ushort *)
0x180019104  test    al, al
0x180019106  jnz     loc_18001923F
0x18001910c  lea     rdx, [rbp+1240h+var_12C0]; unsigned __int16 *
0x180019110  mov     rcx, rdi; this
0x180019113  call    ?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z; IEFavResolver::IsInSyncList(ushort *)
0x180019118  test    al, al
0x18001911a  jnz     loc_18001923F
0x180019120  lea     r8, [rbp+1240h+var_EA0]; unsigned __int16 *
0x180019127  lea     rdx, [rbp+1240h+pszPath]; unsigned __int16 *
0x18001912e  call    ?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)
0x180019133  test    eax, eax
0x180019135  js      short loc_180019164
0x180019137  lea     r8, [rbp+1240h+var_660]; unsigned __int16 *
0x18001913e  lea     rdx, [rbp+1240h+pszPath]; unsigned __int16 *
0x180019145  call    ?GetParentFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetParentFolderPath(ushort const *,ushort *,int)
0x18001914a  test    eax, eax
0x18001914c  js      short loc_180019164
0x18001914e  lea     r8, [rbp+1240h+var_870]; unsigned __int16 *
0x180019155  mov     rcx, rdi; this
0x180019158  lea     rdx, [rbp+1240h+var_660]; unsigned __int16 *
0x18001915f  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x180019164  lea     r8, [rbp+1240h+var_A80]; unsigned __int16 *
0x18001916b  lea     rdx, [rbp+1240h+var_12C0]; unsigned __int16 *
0x18001916f  call    ?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)
0x180019174  mov     ebx, eax
0x180019176  test    eax, eax
0x180019178  js      loc_18001923F
0x18001917e  lea     r8, [rbp+1240h+var_450]; unsigned __int16 *
0x180019185  lea     rdx, [rbp+1240h+var_12C0]; unsigned __int16 *
0x180019189  call    ?GetParentFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetParentFolderPath(ushort const *,ushort *,int)
0x18001918e  mov     ebx, eax
0x180019190  test    eax, eax
0x180019192  js      loc_18001923F
0x180019198  lea     r8, [rbp+1240h+var_C90]; unsigned __int16 *
0x18001919f  mov     rcx, rdi; this
0x1800191a2  lea     rdx, [rbp+1240h+var_450]; unsigned __int16 *
0x1800191a9  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x1800191ae  mov     ebx, eax
0x1800191b0  test    eax, eax
0x1800191b2  js      loc_18001923F
0x1800191b8  test    sil, sil
0x1800191bb  jz      short loc_1800191E3
0x1800191bd  lea     rax, [rbp+1240h+var_EA0]
0x1800191c4  mov     byte ptr [rsp+1340h+var_1308], sil
0x1800191c9  mov     [rsp+1340h+var_1310], rax
0x1800191ce  lea     rax, [rbp+1240h+var_C90]
0x1800191d5  mov     [rsp+1340h+var_1318], rax
0x1800191da  lea     rax, dword_18003240C
0x1800191e1  jmp     short loc_18001921D
0x1800191e3  lea     r8, [rbp+1240h+var_240]; unsigned __int16 *
0x1800191ea  lea     rdx, [rbp+1240h+var_12C0]; unsigned __int16 *
0x1800191ee  call    ?GetFavoriteUrl@IEFavResolver@@AEAAJPEAG0H@Z; IEFavResolver::GetFavoriteUrl(ushort *,ushort *,int)
0x1800191f3  mov     ebx, eax
0x1800191f5  test    eax, eax
0x1800191f7  js      short loc_18001923F
0x1800191f9  lea     rax, [rbp+1240h+var_EA0]
0x180019200  mov     byte ptr [rsp+1340h+var_1308], 0
0x180019205  mov     [rsp+1340h+var_1310], rax
0x18001920a  lea     rax, [rbp+1240h+var_C90]
0x180019211  mov     [rsp+1340h+var_1318], rax
0x180019216  lea     rax, [rbp+1240h+var_240]
0x18001921d  lea     r9, [rbp+1240h+var_A80]
0x180019224  mov     [rsp+1340h+var_1320], rax
0x180019229  lea     r8, [rbp+1240h+var_870]
0x180019230  mov     edx, 2
0x180019235  mov     rcx, rdi
0x180019238  call    ?PostFavoriteChangedEventToEdge@IEFavResolver@@AEAAJW4DATACHANGETYPE@@PEBG1111_N@Z; IEFavResolver::PostFavoriteChangedEventToEdge(DATACHANGETYPE,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x18001923d  mov     ebx, eax
0x18001923f  mov     eax, cs:dword_18003F000
0x180019245  cmp     eax, 5
0x180019248  jbe     loc_1800192D0
0x18001924e  lea     rax, [rbp+1240h+var_12C0]
0x180019252  mov     [rsp+1340h+var_12F0], sil
0x180019257  mov     [rsp+1340h+var_12E8], rax
0x18001925c  lea     rax, [rbp+1240h+pszPath]
0x180019263  mov     [rsp+1340h+var_12E0], rax
0x180019268  mov     [rsp+1340h+var_12EF], 1
0x18001926d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019273  mov     ecx, 10000003h
0x180019278  mov     [rsp+1340h+var_12D8], rax
0x18001927d  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180019283  mov     [rsp+1340h+var_12D0], rax
0x180019288  lea     rdx, word_18003612A
0x18001928f  lea     rax, [rsp+1340h+var_12E8]
0x180019294  mov     [rsp+1340h+var_12F8], rax
0x180019299  lea     rax, [rsp+1340h+var_12E0]
0x18001929e  mov     [rsp+1340h+var_1300], rax
0x1800192a3  lea     rax, [rsp+1340h+var_12F0]
0x1800192a8  mov     [rsp+1340h+var_1308], rax
0x1800192ad  lea     rax, [rsp+1340h+var_12EF]
0x1800192b2  mov     [rsp+1340h+var_1310], rax
0x1800192b7  lea     rax, [rsp+1340h+var_12D8]
0x1800192bc  mov     [rsp+1340h+var_1318], rax
0x1800192c1  lea     rax, [rsp+1340h+var_12D0]
0x1800192c6  mov     [rsp+1340h+var_1320], rax
0x1800192cb  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800192d0  mov     eax, ebx
0x1800192d2  mov     rcx, [rbp+1240h+var_30]
0x1800192d9  xor     rcx, rsp; StackCookie
0x1800192dc  call    __security_check_cookie
0x1800192e1  add     rsp, 1320h
0x1800192e8  pop     r14
0x1800192ea  pop     rdi
0x1800192eb  pop     rsi
0x1800192ec  pop     rbx
0x1800192ed  pop     rbp
0x1800192ee  retn
```
