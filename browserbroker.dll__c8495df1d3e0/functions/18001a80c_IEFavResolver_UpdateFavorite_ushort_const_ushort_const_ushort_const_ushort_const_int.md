# IEFavResolver::UpdateFavorite(ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x18001a80c`
- end: `0x18001aaec`
- name: `?UpdateFavorite@IEFavResolver@@QEAAJPEBG000H@Z`
- size: `736`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, const unsigned __int16 *, PCWSTR pszMore, const unsigned __int16 *, PCWSTR, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x1800167b8`
- `0x180016e70`
- `0x180017ba0`
- `0x180017cdc`
- `0x180018764`
- `0x18001a410`
- `0x18001a80c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001a961`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001a974`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001a961`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001a974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa08`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001a8b9`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001a918`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001a8b9`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001a918`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001a9f4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001a9f4`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18001a99a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18001a99a`

## pseudocode

```c
__int64 __fastcall IEFavResolver::UpdateFavorite(
        WCHAR *this,
        const unsigned __int16 *a2,
        PCWSTR pszMore,
        unsigned __int16 *a4,
        PCWSTR pszMorea,
        int a6)
{
  IEFavResolver *v10; // rcx
  int v11; // r9d
  signed int FavoriteUrl; // ebx
  IEFavResolver *v13; // rcx
  IEFavResolver *v14; // rcx
  int v15; // eax
  signed int LastError; // eax
  IEFavResolver *v17; // rcx
  int v18; // r9d
  unsigned int v20; // [rsp+28h] [rbp-D8h]
  unsigned int v21; // [rsp+28h] [rbp-D8h]
  HRESULT CompleteItemPathFromTitle; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v24; // [rsp+38h] [rbp-C8h]
  PCWSTR v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR v26[2]; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  WCHAR v29[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR NewFileName[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v32[2]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v33[524]; // [rsp+6A4h] [rbp+5A4h] BYREF
  unsigned __int16 v34[264]; // [rsp+8B0h] [rbp+7B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+AC0h] [rbp+9C0h] BYREF

  v27 = a2;
  v25[0] = pszMore;
  v24 = a4;
  v28 = a4;
  v26[0] = pszMorea;
  memset_0(v34, 0, 0x208u);
  v23 = 0;
  CompleteItemPathFromTitle = IEFavResolver::HandleSpecialCharacters(v10, a4, v34, v11, &v23);
  FavoriteUrl = CompleteItemPathFromTitle;
  if ( CompleteItemPathFromTitle >= 0 )
  {
    CompleteItemPathFromTitle = PathCchCombine(pszPathOut, 0x104u, this + 24, pszMore);
    FavoriteUrl = CompleteItemPathFromTitle;
    if ( CompleteItemPathFromTitle >= 0 )
    {
      CompleteItemPathFromTitle = IEFavResolver::GetCompleteItemPathFromTitle(
                                    v13,
                                    pszPathOut,
                                    a2,
                                    a6 != 0,
                                    pszPath,
                                    v20);
      FavoriteUrl = CompleteItemPathFromTitle;
      if ( CompleteItemPathFromTitle >= 0 )
      {
        CompleteItemPathFromTitle = PathCchCombine(v29, 0x104u, this + 24, pszMorea);
        FavoriteUrl = CompleteItemPathFromTitle;
        if ( CompleteItemPathFromTitle >= 0 )
        {
          CompleteItemPathFromTitle = IEFavResolver::GetCompleteItemPathFromTitle(
                                        v14,
                                        v29,
                                        v34,
                                        a6 != 0,
                                        NewFileName,
                                        v21);
          FavoriteUrl = CompleteItemPathFromTitle;
          if ( CompleteItemPathFromTitle >= 0 )
          {
            if ( PathFileExistsW(pszPath) )
            {
              if ( PathFileExistsW(v29) )
                goto LABEL_13;
              IEFavResolver::AddToSyncList((HDPA *)this, v29);
              v15 = SHCreateDirectoryExW(0, v29, 0);
              FavoriteUrl = v15;
              if ( !v15 || v15 == 183 )
                goto LABEL_13;
              if ( v15 > 0 )
                FavoriteUrl = (unsigned __int16)v15 | 0x80070000;
              CompleteItemPathFromTitle = FavoriteUrl;
              if ( FavoriteUrl >= 0 )
              {
LABEL_13:
                IEFavResolver::AddToSyncList((HDPA *)this, pszPath);
                IEFavResolver::AddToSyncList((HDPA *)this, NewFileName);
                if ( MoveFileExW(pszPath, NewFileName, 3u) )
                {
                  FavoriteUrl = 0;
                  CompleteItemPathFromTitle = 0;
LABEL_18:
                  if ( v23 )
                  {
                    *(_DWORD *)v32 = 0;
                    memset_0(v33, 0, 0x204u);
                    if ( !a6 )
                    {
                      FavoriteUrl = IEFavResolver::GetFavoriteUrl(v17, NewFileName, v32, v18);
                      CompleteItemPathFromTitle = FavoriteUrl;
                    }
                    if ( FavoriteUrl >= 0 )
                    {
                      FavoriteUrl = IEFavResolver::SendRenameFavoriteEventToEdge(
                                      (IEFavResolver *)this,
                                      v29,
                                      v34,
                                      v32,
                                      v24,
                                      a6 != 0);
                      CompleteItemPathFromTitle = FavoriteUrl;
                    }
                  }
                  goto LABEL_23;
                }
                LastError = GetLastError();
                FavoriteUrl = LastError;
                if ( LastError > 0 )
                  FavoriteUrl = (unsigned __int16)LastError | 0x80070000;
                CompleteItemPathFromTitle = FavoriteUrl;
                if ( FavoriteUrl >= 0 )
                  goto LABEL_18;
              }
            }
          }
        }
      }
    }
  }
LABEL_23:
  BrowserTelemetry::HandleItemUpdatedFromEdge<unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &,long &>(
    (__int64)&v28,
    (__int64)&v27,
    (__int64)v26,
    (__int64)v25,
    &CompleteItemPathFromTitle);
  return (unsigned int)FavoriteUrl;
}

```

## disassembly

```asm
0x18001a80c  push    rbp
0x18001a80e  push    rbx
0x18001a80f  push    rsi
0x18001a810  push    rdi
0x18001a811  push    r12
0x18001a813  push    r13
0x18001a815  push    r14
0x18001a817  lea     rbp, [rsp-0BE0h]
0x18001a81f  sub     rsp, 0CE0h
0x18001a826  mov     rax, cs:__security_cookie
0x18001a82d  xor     rax, rsp
0x18001a830  mov     [rbp+0C10h+var_40], rax
0x18001a837  mov     r13, [rbp+0C10h+pszMore]
0x18001a83e  mov     rbx, r9
0x18001a841  mov     rsi, r8
0x18001a844  mov     [rsp+0D10h+var_CB0], rdx
0x18001a849  mov     r12, rdx
0x18001a84c  mov     [rsp+0D10h+var_CD0], r8
0x18001a851  mov     rdi, rcx
0x18001a854  mov     [rsp+0D10h+var_CD8], rbx
0x18001a859  xor     edx, edx; Val
0x18001a85b  mov     [rsp+0D10h+var_CA8], rbx
0x18001a860  mov     r8d, 208h; Size
0x18001a866  mov     [rsp+0D10h+var_CC0], r13
0x18001a86b  lea     rcx, [rbp+0C10h+var_460]; void *
0x18001a872  call    memset_0
0x18001a877  lea     rax, [rsp+0D10h+var_CDC]
0x18001a87c  mov     [rsp+0D10h+var_CDC], 0
0x18001a884  lea     r8, [rbp+0C10h+var_460]; unsigned __int16 *
0x18001a88b  mov     [rsp+0D10h+var_CF0], rax; int *
0x18001a890  mov     rdx, rbx; unsigned __int16 *
0x18001a893  call    ?HandleSpecialCharacters@IEFavResolver@@AEAAJPEBGPEAGHPEAH@Z; IEFavResolver::HandleSpecialCharacters(ushort const *,ushort *,int,int *)
0x18001a898  mov     [rsp+0D10h+var_CE0], eax
0x18001a89c  mov     ebx, eax
0x18001a89e  test    eax, eax
0x18001a8a0  js      loc_18001AAA6
0x18001a8a6  mov     r9, rsi; pszMore
0x18001a8a9  lea     r8, [rdi+30h]; pszPathIn
0x18001a8ad  mov     edx, 104h; cchPathOut
0x18001a8b2  lea     rcx, [rbp+0C10h+pszPathOut]; pszPathOut
0x18001a8b9  call    cs:__imp_PathCchCombine
0x18001a8bf  mov     [rsp+0D10h+var_CE0], eax
0x18001a8c3  mov     ebx, eax
0x18001a8c5  test    eax, eax
0x18001a8c7  js      loc_18001AAA6
0x18001a8cd  cmp     [rbp+0C10h+arg_28], 0
0x18001a8d4  lea     rax, [rbp+0C10h+pszPath]
0x18001a8db  mov     r8, r12; unsigned __int16 *
0x18001a8de  mov     [rsp+0D10h+var_CF0], rax; unsigned __int16 *
0x18001a8e3  setnz   sil
0x18001a8e7  lea     rdx, [rbp+0C10h+pszPathOut]; unsigned __int16 *
0x18001a8ee  mov     r9b, sil; bool
0x18001a8f1  call    ?GetCompleteItemPathFromTitle@IEFavResolver@@AEAAJPEBG0_NPEAGI@Z; IEFavResolver::GetCompleteItemPathFromTitle(ushort const *,ushort const *,bool,ushort *,uint)
0x18001a8f6  xor     r12d, r12d
0x18001a8f9  mov     [rsp+0D10h+var_CE0], eax
0x18001a8fd  mov     ebx, eax
0x18001a8ff  test    eax, eax
0x18001a901  js      loc_18001AAA6
0x18001a907  mov     r9, r13; pszMore
0x18001a90a  lea     r8, [rdi+30h]; pszPathIn
0x18001a90e  mov     edx, 104h; cchPathOut
0x18001a913  lea     rcx, [rsp+0D10h+var_CA0]; pszPathOut
0x18001a918  call    cs:__imp_PathCchCombine
0x18001a91e  mov     [rsp+0D10h+var_CE0], eax
0x18001a922  mov     ebx, eax
0x18001a924  test    eax, eax
0x18001a926  js      loc_18001AAA6
0x18001a92c  lea     rax, [rbp+0C10h+NewFileName]
0x18001a933  mov     r9b, sil; bool
0x18001a936  lea     r8, [rbp+0C10h+var_460]; unsigned __int16 *
0x18001a93d  mov     [rsp+0D10h+var_CF0], rax; unsigned __int16 *
0x18001a942  lea     rdx, [rsp+0D10h+var_CA0]; unsigned __int16 *
0x18001a947  call    ?GetCompleteItemPathFromTitle@IEFavResolver@@AEAAJPEBG0_NPEAGI@Z; IEFavResolver::GetCompleteItemPathFromTitle(ushort const *,ushort const *,bool,ushort *,uint)
0x18001a94c  mov     [rsp+0D10h+var_CE0], eax
0x18001a950  mov     ebx, eax
0x18001a952  test    eax, eax
0x18001a954  js      loc_18001AAA6
0x18001a95a  lea     rcx, [rbp+0C10h+pszPath]; pszPath
0x18001a961  call    cs:__imp_PathFileExistsW
0x18001a967  test    eax, eax
0x18001a969  jz      loc_18001AAA6
0x18001a96f  lea     rcx, [rsp+0D10h+var_CA0]; pszPath
0x18001a974  call    cs:__imp_PathFileExistsW
0x18001a97a  mov     esi, 80070000h
0x18001a97f  test    eax, eax
0x18001a981  jnz     short loc_18001A9C2
0x18001a983  lea     rdx, [rsp+0D10h+var_CA0]; unsigned __int16 *
0x18001a988  mov     rcx, rdi; this
0x18001a98b  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x18001a990  xor     r8d, r8d; psa
0x18001a993  lea     rdx, [rsp+0D10h+var_CA0]; pszPath
0x18001a998  xor     ecx, ecx; hwnd
0x18001a99a  call    cs:__imp_SHCreateDirectoryExW
0x18001a9a0  mov     ebx, eax
0x18001a9a2  test    eax, eax
0x18001a9a4  jz      short loc_18001A9C2
0x18001a9a6  cmp     eax, 0B7h
0x18001a9ab  jz      short loc_18001A9C2
0x18001a9ad  test    eax, eax
0x18001a9af  jle     short loc_18001A9B6
0x18001a9b1  movzx   ebx, ax
0x18001a9b4  or      ebx, esi
0x18001a9b6  mov     [rsp+0D10h+var_CE0], ebx
0x18001a9ba  test    ebx, ebx
0x18001a9bc  js      loc_18001AAA6
0x18001a9c2  lea     rdx, [rbp+0C10h+pszPath]; unsigned __int16 *
0x18001a9c9  mov     rcx, rdi; this
0x18001a9cc  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x18001a9d1  lea     rdx, [rbp+0C10h+NewFileName]; unsigned __int16 *
0x18001a9d8  mov     rcx, rdi; this
0x18001a9db  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x18001a9e0  mov     r8d, 3; dwFlags
0x18001a9e6  lea     rdx, [rbp+0C10h+NewFileName]; lpNewFileName
0x18001a9ed  lea     rcx, [rbp+0C10h+pszPath]; lpExistingFileName
0x18001a9f4  call    cs:__imp_MoveFileExW
0x18001a9fa  test    eax, eax
0x18001a9fc  jz      short loc_18001AA08
0x18001a9fe  mov     ebx, r12d
0x18001aa01  mov     [rsp+0D10h+var_CE0], r12d
0x18001aa06  jmp     short loc_18001AA25
0x18001aa08  call    cs:__imp_GetLastError
0x18001aa0e  mov     ebx, eax
0x18001aa10  test    eax, eax
0x18001aa12  jle     short loc_18001AA19
0x18001aa14  movzx   ebx, ax
0x18001aa17  or      ebx, esi
0x18001aa19  mov     [rsp+0D10h+var_CE0], ebx
0x18001aa1d  test    ebx, ebx
0x18001aa1f  js      loc_18001AAA6
0x18001aa25  cmp     [rsp+0D10h+var_CDC], r12d
0x18001aa2a  jz      short loc_18001AAA6
0x18001aa2c  xor     edx, edx; Val
0x18001aa2e  mov     dword ptr [rbp+0C10h+var_670], r12d
0x18001aa35  mov     r8d, 204h; Size
0x18001aa3b  lea     rcx, [rbp+0C10h+var_66C]; void *
0x18001aa42  call    memset_0
0x18001aa47  cmp     [rbp+0C10h+arg_28], r12d
0x18001aa4e  jnz     short loc_18001AA69
0x18001aa50  lea     r8, [rbp+0C10h+var_670]; unsigned __int16 *
0x18001aa57  lea     rdx, [rbp+0C10h+NewFileName]; unsigned __int16 *
0x18001aa5e  call    ?GetFavoriteUrl@IEFavResolver@@AEAAJPEAG0H@Z; IEFavResolver::GetFavoriteUrl(ushort *,ushort *,int)
0x18001aa63  mov     ebx, eax
0x18001aa65  mov     [rsp+0D10h+var_CE0], eax
0x18001aa69  test    ebx, ebx
0x18001aa6b  js      short loc_18001AAA6
0x18001aa6d  cmp     [rbp+0C10h+arg_28], r12d
0x18001aa74  lea     r9, [rbp+0C10h+var_670]; unsigned __int16 *
0x18001aa7b  lea     r8, [rbp+0C10h+var_460]; unsigned __int16 *
0x18001aa82  mov     rcx, rdi; this
0x18001aa85  setnz   al
0x18001aa88  lea     rdx, [rsp+0D10h+var_CA0]; unsigned __int16 *
0x18001aa8d  mov     [rsp+0D10h+var_CE8], al; bool
0x18001aa91  mov     rax, [rsp+0D10h+var_CD8]
0x18001aa96  mov     [rsp+0D10h+var_CF0], rax; unsigned __int16 *
0x18001aa9b  call    ?SendRenameFavoriteEventToEdge@IEFavResolver@@AEAAJPEBG000_N@Z; IEFavResolver::SendRenameFavoriteEventToEdge(ushort const *,ushort const *,ushort const *,ushort const *,bool)
0x18001aaa0  mov     ebx, eax
0x18001aaa2  mov     [rsp+0D10h+var_CE0], eax
0x18001aaa6  lea     rax, [rsp+0D10h+var_CE0]
0x18001aaab  lea     r9, [rsp+0D10h+var_CD0]
0x18001aab0  mov     [rsp+0D10h+var_CF0], rax
0x18001aab5  lea     r8, [rsp+0D10h+var_CC0]
0x18001aaba  lea     rdx, [rsp+0D10h+var_CB0]
0x18001aabf  lea     rcx, [rsp+0D10h+var_CA8]
0x18001aac4  call    ??$HandleItemUpdatedFromEdge@AEAPEBGAEAPEBGAEAPEBGAEAPEBGAEAJ@BrowserTelemetry@@SAXAEAPEBG000AEAJ@Z; BrowserTelemetry::HandleItemUpdatedFromEdge<ushort const * &,ushort const * &,ushort const * &,ushort const * &,long &>(ushort const * &,ushort const * &,ushort const * &,ushort const * &,long &)
0x18001aac9  mov     eax, ebx
0x18001aacb  mov     rcx, [rbp+0C10h+var_40]
0x18001aad2  xor     rcx, rsp; StackCookie
0x18001aad5  call    __security_check_cookie
0x18001aada  add     rsp, 0CE0h
0x18001aae1  pop     r14
0x18001aae3  pop     r13
0x18001aae5  pop     r12
0x18001aae7  pop     rdi
0x18001aae8  pop     rsi
0x18001aae9  pop     rbx
0x18001aaea  pop     rbp
0x18001aaeb  retn
```
