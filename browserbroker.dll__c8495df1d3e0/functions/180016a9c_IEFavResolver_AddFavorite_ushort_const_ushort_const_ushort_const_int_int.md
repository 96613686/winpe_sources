# IEFavResolver::AddFavorite(ushort const *,ushort const *,ushort const *,int,int)

- ea: `0x180016a9c`
- end: `0x180016e6a`
- name: `?AddFavorite@IEFavResolver@@QEAAJPEBG00HH@Z`
- size: `974`
- prototype: `__int64 __fastcall(WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800173a8`
- `0x180019b8c`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006cc4`
- `0x18001664c`
- `0x180016a9c`
- `0x180016e70`
- `0x180017ff4`
- `0x180018764`
- `0x18001a1b0`
- `0x18001a308`
- `0x18001a410`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180016b18`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180016b18`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180016df4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180016df4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016c9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c22`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016c18`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016c18`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180016b4d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180016bec`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180016b4d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180016bec`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180016bc1`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180016bc1`

## pseudocode

```c
__int64 __fastcall IEFavResolver::AddFavorite(
        WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6)
{
  int RelativePathFromFullUnifiedPath; // ebx
  __int64 v11; // rax
  IEFavResolver *v12; // rcx
  int v13; // r9d
  int LastError; // eax
  __int64 v15; // rcx
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  struct IPersistFile *v18; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v23[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR PathName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR pszMore[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v21[1] = (__int64)a3;
  RelativePathFromFullUnifiedPath = IEFavResolver::GetRelativePathFromFullUnifiedPath(
                                      (IEFavResolver *)this,
                                      a4,
                                      (unsigned int)a3,
                                      pszMore);
  if ( RelativePathFromFullUnifiedPath >= 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( pszMore[v11] );
    if ( v11 || StrCmpICW(a2, L"_Favorites_Bar_") )
    {
      memset_0(pszPathOut, 0, 0x208u);
      RelativePathFromFullUnifiedPath = PathCchCombine(pszPathOut, 0x104u, this + 24, pszMore);
      if ( RelativePathFromFullUnifiedPath >= 0 )
      {
        memset_0(v23, 0, 0x208u);
        v17 = 0;
        RelativePathFromFullUnifiedPath = IEFavResolver::HandleSpecialCharacters(v12, a2, v23, v13, &v17);
        if ( RelativePathFromFullUnifiedPath >= 0 )
        {
          if ( !a5 )
          {
            ppv = 0;
            RelativePathFromFullUnifiedPath = CoCreateInstance(
                                                &CLSID_InternetShortcut,
                                                0,
                                                1u,
                                                &GUID_cabb0da0_da57_11cf_9974_0020afd79762,
                                                &ppv);
            if ( RelativePathFromFullUnifiedPath >= 0 )
            {
              RelativePathFromFullUnifiedPath = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                                                  ppv,
                                                  a3,
                                                  0);
              if ( RelativePathFromFullUnifiedPath >= 0 )
              {
                v18 = 0;
                RelativePathFromFullUnifiedPath = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IPersistFile **))ppv)(
                                                    ppv,
                                                    &GUID_0000010b_0000_0000_c000_000000000046,
                                                    &v18);
                if ( RelativePathFromFullUnifiedPath >= 0 )
                {
                  RelativePathFromFullUnifiedPath = IEFavResolver::SaveFile(
                                                      (IEFavResolver *)this,
                                                      v18,
                                                      pszPathOut,
                                                      v23,
                                                      a6);
                  if ( RelativePathFromFullUnifiedPath >= 0 )
                  {
                    if ( !v17
                      || (RelativePathFromFullUnifiedPath = IEFavResolver::SendRenameFavoriteEventToEdge(
                                                              (IEFavResolver *)this,
                                                              pszPathOut,
                                                              v23,
                                                              a3,
                                                              a2,
                                                              0),
                          RelativePathFromFullUnifiedPath >= 0) )
                    {
                      v15 = 0;
                      v21[0] = 0;
                      if ( v18 )
                      {
                        ((void (__fastcall *)(struct IPersistFile *, GUID *, __int64 *))v18->lpVtbl->QueryInterface)(
                          v18,
                          &GUID_000214fa_0000_0000_c000_000000000046,
                          v21);
                        v15 = v21[0];
                      }
                      if ( v15 )
                      {
                        v20 = 0;
                        v17 = 0;
                        if ( (*(int (__fastcall **)(__int64, _QWORD, WCHAR *, __int64, int *, int *))(*(_QWORD *)v15 + 24LL))(
                               v15,
                               0,
                               PathName,
                               260,
                               &v20,
                               &v17) < 0
                          || StrCmpNICW(PathName, L"http", 4) )
                        {
                          IEFavResolver::RequestFaviconDataFromEdge((IEFavResolver *)this, v23, a4);
                        }
                      }
                      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(v21);
                    }
                  }
                }
                ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&v18);
              }
            }
            ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppv);
            goto LABEL_34;
          }
          IEFavResolver::AddToSyncList((IEFavResolver *)this, pszPathOut);
          LastError = SHCreateDirectoryExW(0, pszPathOut, 0);
          RelativePathFromFullUnifiedPath = LastError;
          if ( LastError && LastError != 183 )
          {
LABEL_14:
            if ( LastError > 0 )
              RelativePathFromFullUnifiedPath = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_34;
          }
          RelativePathFromFullUnifiedPath = PathCchCombine(PathName, 0x104u, pszPathOut, v23);
          if ( RelativePathFromFullUnifiedPath >= 0 )
          {
            IEFavResolver::AddToSyncList((IEFavResolver *)this, PathName);
            if ( CreateDirectoryW(PathName, 0) )
            {
              if ( v17 )
                RelativePathFromFullUnifiedPath = IEFavResolver::SendRenameFavoriteEventToEdge(
                                                    (IEFavResolver *)this,
                                                    pszPathOut,
                                                    v23,
                                                    &dword_18003240C,
                                                    a2,
                                                    1);
              goto LABEL_34;
            }
            LastError = GetLastError();
            RelativePathFromFullUnifiedPath = LastError;
            goto LABEL_14;
          }
        }
LABEL_34:
        BrowserTelemetry::HandleItemAddedFromEdge<unsigned short (&)[260],unsigned short const * &,long &>((__int64)v23);
      }
    }
  }
  return (unsigned int)RelativePathFromFullUnifiedPath;
}

```

## disassembly

```asm
0x180016a9c  push    rbp
0x180016a9e  push    rbx
0x180016a9f  push    rsi
0x180016aa0  push    rdi
0x180016aa1  push    r12
0x180016aa3  push    r14
0x180016aa5  push    r15
0x180016aa7  lea     rbp, [rsp-7C0h]
0x180016aaf  sub     rsp, 8C0h
0x180016ab6  mov     rax, cs:__security_cookie
0x180016abd  xor     rax, rsp
0x180016ac0  mov     [rbp+7F0h+var_40], rax
0x180016ac7  mov     r15, r9
0x180016aca  mov     r14, r8
0x180016acd  mov     rsi, rdx
0x180016ad0  mov     rdi, rcx
0x180016ad3  mov     [rsp+8F0h+var_888], r8
0x180016ad8  lea     r9, [rbp+7F0h+pszMore]; unsigned __int16 *
0x180016adf  mov     rdx, r15; unsigned __int16 *
0x180016ae2  call    ?GetRelativePathFromFullUnifiedPath@IEFavResolver@@AEAAJPEBGIPEAG@Z; IEFavResolver::GetRelativePathFromFullUnifiedPath(ushort const *,uint,ushort *)
0x180016ae7  mov     ebx, eax
0x180016ae9  xor     r12d, r12d
0x180016aec  test    eax, eax
0x180016aee  js      loc_180016E47
0x180016af4  lea     rcx, [rbp+7F0h+pszMore]
0x180016afb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016aff  inc     rax
0x180016b02  cmp     [rcx+rax*2], r12w
0x180016b07  jnz     short loc_180016AFF
0x180016b09  test    rax, rax
0x180016b0c  jnz     short loc_180016B26
0x180016b0e  lea     rdx, aFavoritesBar_0; "_Favorites_Bar_"
0x180016b15  mov     rcx, rsi; pszStr1
0x180016b18  call    cs:__imp_StrCmpICW
0x180016b1e  test    eax, eax
0x180016b20  jz      loc_180016E47
0x180016b26  xor     edx, edx; Val
0x180016b28  mov     r8d, 208h; Size
0x180016b2e  lea     rcx, [rsp+8F0h+pszPathOut]; void *
0x180016b33  call    memset_0
0x180016b38  lea     r8, [rdi+30h]; pszPathIn
0x180016b3c  lea     r9, [rbp+7F0h+pszMore]; pszMore
0x180016b43  mov     edx, 104h; cchPathOut
0x180016b48  lea     rcx, [rsp+8F0h+pszPathOut]; pszPathOut
0x180016b4d  call    cs:__imp_PathCchCombine
0x180016b53  mov     ebx, eax
0x180016b55  test    eax, eax
0x180016b57  js      loc_180016E47
0x180016b5d  xor     edx, edx; Val
0x180016b5f  mov     r8d, 208h; Size
0x180016b65  lea     rcx, [rbp+7F0h+var_670]; void *
0x180016b6c  call    memset_0
0x180016b71  mov     [rsp+8F0h+var_8AC], r12d
0x180016b76  lea     rax, [rsp+8F0h+var_8AC]
0x180016b7b  mov     [rsp+8F0h+ppv], rax; int *
0x180016b80  lea     r8, [rbp+7F0h+var_670]; unsigned __int16 *
0x180016b87  mov     rdx, rsi; unsigned __int16 *
0x180016b8a  call    ?HandleSpecialCharacters@IEFavResolver@@AEAAJPEBGPEAGHPEAH@Z; IEFavResolver::HandleSpecialCharacters(ushort const *,ushort *,int,int *)
0x180016b8f  mov     ebx, eax
0x180016b91  mov     [rsp+8F0h+var_8B0], eax
0x180016b95  test    eax, eax
0x180016b97  js      loc_180016E31
0x180016b9d  cmp     [rbp+7F0h+arg_20], r12d
0x180016ba4  jz      loc_180016C7B
0x180016baa  lea     rdx, [rsp+8F0h+pszPathOut]; unsigned __int16 *
0x180016baf  mov     rcx, rdi; this
0x180016bb2  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x180016bb7  xor     r8d, r8d; psa
0x180016bba  lea     rdx, [rsp+8F0h+pszPathOut]; pszPath
0x180016bbf  xor     ecx, ecx; hwnd
0x180016bc1  call    cs:__imp_SHCreateDirectoryExW
0x180016bc7  mov     ebx, eax
0x180016bc9  test    eax, eax
0x180016bcb  jz      short loc_180016BD4
0x180016bcd  cmp     eax, 0B7h
0x180016bd2  jnz     short loc_180016C2A
0x180016bd4  lea     r9, [rbp+7F0h+var_670]; pszMore
0x180016bdb  lea     r8, [rsp+8F0h+pszPathOut]; pszPathIn
0x180016be0  mov     edx, 104h; cchPathOut
0x180016be5  lea     rcx, [rbp+7F0h+PathName]; pszPathOut
0x180016bec  call    cs:__imp_PathCchCombine
0x180016bf2  mov     ebx, eax
0x180016bf4  mov     [rsp+8F0h+var_8B0], eax
0x180016bf8  test    eax, eax
0x180016bfa  js      loc_180016E31
0x180016c00  lea     rdx, [rbp+7F0h+PathName]; unsigned __int16 *
0x180016c07  mov     rcx, rdi; this
0x180016c0a  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x180016c0f  xor     edx, edx; lpSecurityAttributes
0x180016c11  lea     rcx, [rbp+7F0h+PathName]; lpPathName
0x180016c18  call    cs:__imp_CreateDirectoryW
0x180016c1e  test    eax, eax
0x180016c20  jnz     short loc_180016C40
0x180016c22  call    cs:__imp_GetLastError
0x180016c28  mov     ebx, eax
0x180016c2a  test    eax, eax
0x180016c2c  jle     short loc_180016C37
0x180016c2e  movzx   ebx, ax
0x180016c31  or      ebx, 80070000h
0x180016c37  mov     [rsp+8F0h+var_8B0], ebx
0x180016c3b  jmp     loc_180016E31
0x180016c40  cmp     [rsp+8F0h+var_8AC], r12d
0x180016c45  jz      loc_180016E31
0x180016c4b  mov     [rsp+8F0h+var_8C8], 1; bool
0x180016c50  mov     [rsp+8F0h+ppv], rsi; unsigned __int16 *
0x180016c55  lea     r9, dword_18003240C; unsigned __int16 *
0x180016c5c  lea     r8, [rbp+7F0h+var_670]; unsigned __int16 *
0x180016c63  lea     rdx, [rsp+8F0h+pszPathOut]; unsigned __int16 *
0x180016c68  mov     rcx, rdi; this
0x180016c6b  call    ?SendRenameFavoriteEventToEdge@IEFavResolver@@AEAAJPEBG000_N@Z; IEFavResolver::SendRenameFavoriteEventToEdge(ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180016c70  mov     ebx, eax
0x180016c72  mov     [rsp+8F0h+var_8B0], eax
0x180016c76  jmp     loc_180016E31
0x180016c7b  mov     [rsp+8F0h+var_8A0], r12
0x180016c80  lea     rax, [rsp+8F0h+var_8A0]
0x180016c85  mov     [rsp+8F0h+ppv], rax; ppv
0x180016c8a  lea     r9, _GUID_cabb0da0_da57_11cf_9974_0020afd79762; riid
0x180016c91  xor     edx, edx; pUnkOuter
0x180016c93  lea     r8d, [rdx+1]; dwClsContext
0x180016c97  lea     rcx, CLSID_InternetShortcut; rclsid
0x180016c9e  call    cs:__imp_CoCreateInstance
0x180016ca4  mov     ebx, eax
0x180016ca6  mov     [rsp+8F0h+var_8B0], eax
0x180016caa  test    eax, eax
0x180016cac  js      loc_180016E27
0x180016cb2  mov     rcx, [rsp+8F0h+var_8A0]
0x180016cb7  mov     rax, [rcx]
0x180016cba  xor     r8d, r8d
0x180016cbd  mov     rdx, r14
0x180016cc0  mov     rax, [rax+18h]
0x180016cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cc9  mov     ebx, eax
0x180016ccb  mov     [rsp+8F0h+var_8B0], eax
0x180016ccf  test    eax, eax
0x180016cd1  js      loc_180016E27
0x180016cd7  mov     [rsp+8F0h+var_8A8], r12
0x180016cdc  mov     rcx, [rsp+8F0h+var_8A0]
0x180016ce1  mov     rax, [rcx]
0x180016ce4  lea     r8, [rsp+8F0h+var_8A8]
0x180016ce9  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180016cf0  mov     rax, [rax]
0x180016cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cf8  mov     ebx, eax
0x180016cfa  mov     [rsp+8F0h+var_8B0], eax
0x180016cfe  test    eax, eax
0x180016d00  js      loc_180016E1C
0x180016d06  mov     eax, [rbp+7F0h+arg_28]
0x180016d0c  mov     dword ptr [rsp+8F0h+ppv], eax; int
0x180016d10  lea     r9, [rbp+7F0h+var_670]; unsigned __int16 *
0x180016d17  lea     r8, [rsp+8F0h+pszPathOut]; unsigned __int16 *
0x180016d1c  mov     rdx, [rsp+8F0h+var_8A8]; struct IPersistFile *
0x180016d21  mov     rcx, rdi; this
0x180016d24  call    ?SaveFile@IEFavResolver@@AEAAJPEAUIPersistFile@@PEBG1H@Z; IEFavResolver::SaveFile(IPersistFile *,ushort const *,ushort const *,int)
0x180016d29  mov     ebx, eax
0x180016d2b  mov     [rsp+8F0h+var_8B0], eax
0x180016d2f  test    eax, eax
0x180016d31  js      loc_180016E1C
0x180016d37  cmp     [rsp+8F0h+var_8AC], r12d
0x180016d3c  jz      short loc_180016D6D
0x180016d3e  mov     [rsp+8F0h+var_8C8], r12b; bool
0x180016d43  mov     [rsp+8F0h+ppv], rsi; unsigned __int16 *
0x180016d48  mov     r9, r14; unsigned __int16 *
0x180016d4b  lea     r8, [rbp+7F0h+var_670]; unsigned __int16 *
0x180016d52  lea     rdx, [rsp+8F0h+pszPathOut]; unsigned __int16 *
0x180016d57  mov     rcx, rdi; this
0x180016d5a  call    ?SendRenameFavoriteEventToEdge@IEFavResolver@@AEAAJPEBG000_N@Z; IEFavResolver::SendRenameFavoriteEventToEdge(ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x180016d5f  mov     ebx, eax
0x180016d61  mov     [rsp+8F0h+var_8B0], eax
0x180016d65  test    eax, eax
0x180016d67  js      loc_180016E1C
0x180016d6d  mov     r9, [rsp+8F0h+var_8A8]
0x180016d72  mov     rcx, r12
0x180016d75  mov     [rsp+8F0h+var_890], rcx
0x180016d7a  test    r9, r9
0x180016d7d  jz      short loc_180016D9E
0x180016d7f  mov     rax, [r9]
0x180016d82  lea     r8, [rsp+8F0h+var_890]
0x180016d87  lea     rdx, _GUID_000214fa_0000_0000_c000_000000000046
0x180016d8e  mov     rcx, r9
0x180016d91  mov     rax, [rax]
0x180016d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d99  mov     rcx, [rsp+8F0h+var_890]
0x180016d9e  test    rcx, rcx
0x180016da1  jz      short loc_180016E11
0x180016da3  mov     [rsp+8F0h+var_898], r12d
0x180016da8  mov     [rsp+8F0h+var_8AC], r12d
0x180016dad  mov     rax, [rcx]
0x180016db0  lea     rdx, [rsp+8F0h+var_8AC]
0x180016db5  mov     qword ptr [rsp+8F0h+var_8C8], rdx
0x180016dba  lea     rdx, [rsp+8F0h+var_898]
0x180016dbf  mov     [rsp+8F0h+ppv], rdx
0x180016dc4  mov     r9d, 104h
0x180016dca  lea     r8, [rbp+7F0h+PathName]
0x180016dd1  xor     edx, edx
0x180016dd3  mov     rax, [rax+18h]
0x180016dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ddc  test    eax, eax
0x180016dde  js      short loc_180016DFE
0x180016de0  mov     r8d, 4; nChar
0x180016de6  lea     rdx, aHttp; "http"
0x180016ded  lea     rcx, [rbp+7F0h+PathName]; pszStr1
0x180016df4  call    cs:__imp_StrCmpNICW
0x180016dfa  test    eax, eax
0x180016dfc  jz      short loc_180016E11
0x180016dfe  mov     r8, r15; unsigned __int16 *
0x180016e01  lea     rdx, [rbp+7F0h+var_670]; unsigned __int16 *
0x180016e08  mov     rcx, rdi; this
0x180016e0b  call    ?RequestFaviconDataFromEdge@IEFavResolver@@AEAAJPEBG0@Z; IEFavResolver::RequestFaviconDataFromEdge(ushort const *,ushort const *)
0x180016e10  nop
0x180016e11  lea     rcx, [rsp+8F0h+var_890]
0x180016e16  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180016e1b  nop
0x180016e1c  lea     rcx, [rsp+8F0h+var_8A8]
0x180016e21  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180016e26  nop
0x180016e27  lea     rcx, [rsp+8F0h+var_8A0]
0x180016e2c  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180016e31  lea     r8, [rsp+8F0h+var_8B0]
0x180016e36  lea     rdx, [rsp+8F0h+var_888]
0x180016e3b  lea     rcx, [rbp+7F0h+var_670]
0x180016e42  call    ??$HandleItemAddedFromEdge@AEAY0BAE@GAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAY0BAE@GAEAPEBGAEAJ@Z; BrowserTelemetry::HandleItemAddedFromEdge<ushort (&)[260],ushort const * &,long &>(ushort (&)[260],ushort const * &,long &)
0x180016e47  mov     eax, ebx
0x180016e49  mov     rcx, [rbp+7F0h+var_40]
0x180016e50  xor     rcx, rsp; StackCookie
0x180016e53  call    __security_check_cookie
0x180016e58  add     rsp, 8C0h
0x180016e5f  pop     r15
0x180016e61  pop     r14
0x180016e63  pop     r12
0x180016e65  pop     rdi
0x180016e66  pop     rsi
0x180016e67  pop     rbx
0x180016e68  pop     rbp
0x180016e69  retn
```
