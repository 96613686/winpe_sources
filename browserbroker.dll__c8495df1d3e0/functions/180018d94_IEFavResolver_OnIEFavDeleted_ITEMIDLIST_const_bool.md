# IEFavResolver::OnIEFavDeleted(_ITEMIDLIST const *,bool)

- ea: `0x180018d94`
- end: `0x180018f06`
- name: `?OnIEFavDeleted@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@_N@Z`
- size: `370`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, LPCITEMIDLIST pidl, bool)`
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
- `0x180018d94`
- `0x180019848`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180018ea3`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180018ea3`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180018e93`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180018e93`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180018dd2`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x180018dd2`

## pseudocode

```c
__int64 __fastcall IEFavResolver::OnIEFavDeleted(WCHAR *this, LPCITEMIDLIST pidl, char a3)
{
  int FavoriteTitle; // ebx
  IEFavResolver *v6; // rcx
  int v7; // r9d
  IEFavResolver *v8; // rcx
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char v14; // [rsp+38h] [rbp-C8h]
  char v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v16; // [rsp+48h] [rbp-B8h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 CLSID; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v21[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v22[264]; // [rsp+690h] [rbp+590h] BYREF

  FavoriteTitle = -2147467259;
  if ( SHGetPathFromIDListW(pidl, pszPath) )
  {
    FavoriteTitle = 0;
    if ( !IEFavResolver::IsInSyncList((IEFavResolver *)this, pszPath) )
    {
      FavoriteTitle = IEFavResolver::GetFavoriteTitle(v6, pszPath, v21, v7);
      if ( FavoriteTitle >= 0 )
      {
        FavoriteTitle = IEFavResolver::GetParentFolderPath(v8, pszPath, v20, v9);
        if ( FavoriteTitle >= 0 )
        {
          FavoriteTitle = IEFavResolver::GetUnifiedFolderPath(this, v20, v22);
          if ( FavoriteTitle >= 0 )
          {
            v14 = a3;
            FavoriteTitle = IEFavResolver::PostFavoriteChangedEventToEdge(
                              this,
                              3,
                              v22,
                              v21,
                              &dword_18003240C,
                              &dword_18003240C,
                              &dword_18003240C,
                              v14);
          }
        }
      }
    }
  }
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v15[0] = 1;
    v16 = pszPath;
    v17 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v10,
      (__int64)&byte_1800361A7,
      v11,
      v12,
      &CLSID,
      (__int64 *)&v17,
      (__int64)v15,
      (const WCHAR **)&v16);
  }
  return (unsigned int)FavoriteTitle;
}

```

## disassembly

```asm
0x180018d94  mov     [rsp-8+arg_10], rbx
0x180018d99  push    rbp
0x180018d9a  push    rsi
0x180018d9b  push    rdi
0x180018d9c  lea     rbp, [rsp-7B0h]
0x180018da4  sub     rsp, 8B0h
0x180018dab  mov     rax, cs:__security_cookie
0x180018db2  xor     rax, rsp
0x180018db5  mov     [rbp+7C0h+var_20], rax
0x180018dbc  mov     rax, rdx
0x180018dbf  mov     rdi, rcx
0x180018dc2  mov     rcx, rax; pidl
0x180018dc5  lea     rdx, [rsp+8C0h+pszPath]; pszPath
0x180018dca  mov     sil, r8b
0x180018dcd  mov     ebx, 80004005h
0x180018dd2  call    cs:__imp_SHGetPathFromIDListW
0x180018dd8  test    eax, eax
0x180018dda  jz      loc_180018E79
0x180018de0  lea     rdx, [rsp+8C0h+pszPath]; unsigned __int16 *
0x180018de5  mov     rcx, rdi; this
0x180018de8  xor     ebx, ebx
0x180018dea  call    ?IsInSyncList@IEFavResolver@@AEAA_NPEAG@Z; IEFavResolver::IsInSyncList(ushort *)
0x180018def  test    al, al
0x180018df1  jnz     loc_180018E79
0x180018df7  lea     r8, [rbp+7C0h+var_440]; unsigned __int16 *
0x180018dfe  lea     rdx, [rsp+8C0h+pszPath]; unsigned __int16 *
0x180018e03  call    ?GetFavoriteTitle@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetFavoriteTitle(ushort const *,ushort *,int)
0x180018e08  mov     ebx, eax
0x180018e0a  test    eax, eax
0x180018e0c  js      short loc_180018E79
0x180018e0e  lea     r8, [rbp+7C0h+var_650]; unsigned __int16 *
0x180018e15  lea     rdx, [rsp+8C0h+pszPath]; unsigned __int16 *
0x180018e1a  call    ?GetParentFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetParentFolderPath(ushort const *,ushort *,int)
0x180018e1f  mov     ebx, eax
0x180018e21  test    eax, eax
0x180018e23  js      short loc_180018E79
0x180018e25  lea     r8, [rbp+7C0h+var_230]; unsigned __int16 *
0x180018e2c  mov     rcx, rdi; this
0x180018e2f  lea     rdx, [rbp+7C0h+var_650]; unsigned __int16 *
0x180018e36  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x180018e3b  mov     ebx, eax
0x180018e3d  test    eax, eax
0x180018e3f  js      short loc_180018E79
0x180018e41  lea     rax, dword_18003240C
0x180018e48  mov     byte ptr [rsp+8C0h+var_888], sil
0x180018e4d  mov     [rsp+8C0h+var_890], rax
0x180018e52  lea     r9, [rbp+7C0h+var_440]
0x180018e59  mov     [rsp+8C0h+var_898], rax
0x180018e5e  lea     r8, [rbp+7C0h+var_230]
0x180018e65  mov     edx, 3
0x180018e6a  mov     [rsp+8C0h+var_8A0], rax
0x180018e6f  mov     rcx, rdi
0x180018e72  call    ?PostFavoriteChangedEventToEdge@IEFavResolver@@AEAAJW4DATACHANGETYPE@@PEBG1111_N@Z; IEFavResolver::PostFavoriteChangedEventToEdge(DATACHANGETYPE,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180018e77  mov     ebx, eax
0x180018e79  mov     eax, cs:dword_18003F000
0x180018e7f  cmp     eax, 5
0x180018e82  jbe     short loc_180018EE2
0x180018e84  lea     rax, [rsp+8C0h+pszPath]
0x180018e89  mov     [rsp+8C0h+var_880], 1
0x180018e8e  mov     [rsp+8C0h+var_878], rax
0x180018e93  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180018e99  mov     ecx, 10000003h
0x180018e9e  mov     [rsp+8C0h+var_870], rax
0x180018ea3  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180018ea9  mov     [rsp+8C0h+var_868], rax
0x180018eae  lea     rdx, byte_1800361A7
0x180018eb5  lea     rax, [rsp+8C0h+var_878]
0x180018eba  mov     [rsp+8C0h+var_888], rax
0x180018ebf  lea     rax, [rsp+8C0h+var_880]
0x180018ec4  mov     [rsp+8C0h+var_890], rax
0x180018ec9  lea     rax, [rsp+8C0h+var_870]
0x180018ece  mov     [rsp+8C0h+var_898], rax
0x180018ed3  lea     rax, [rsp+8C0h+var_868]
0x180018ed8  mov     [rsp+8C0h+var_8A0], rax
0x180018edd  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180018ee2  mov     eax, ebx
0x180018ee4  mov     rcx, [rbp+7C0h+var_20]
0x180018eeb  xor     rcx, rsp; StackCookie
0x180018eee  call    __security_check_cookie
0x180018ef3  mov     rbx, [rsp+8C0h+arg_10]
0x180018efb  add     rsp, 8B0h
0x180018f02  pop     rdi
0x180018f03  pop     rsi
0x180018f04  pop     rbp
0x180018f05  retn
```
