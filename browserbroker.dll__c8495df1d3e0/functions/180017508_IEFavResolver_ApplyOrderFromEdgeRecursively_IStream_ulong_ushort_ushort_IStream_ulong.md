# IEFavResolver::ApplyOrderFromEdgeRecursively(IStream *,ulong *,ushort *,ushort *,IStream * *,ulong *)

- ea: `0x180017508`
- end: `0x18001784c`
- name: `?ApplyOrderFromEdgeRecursively@IEFavResolver@@AEAAXPEAUIStream@@PEAKPEAG2PEAPEAU2@1@Z`
- size: `836`
- prototype: `void __fastcall(IEFavResolver *__hidden this, struct IStream *, unsigned int *, unsigned __int16 *, unsigned __int16 *, struct IStream **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180017508`
- `0x180019b8c`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006cc4`
- `0x18000d17c`
- `0x180016fa8`
- `0x180017508`
- `0x180024f94`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180017633`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001764d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180017663`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800176f1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180017633`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001764d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180017663`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800176f1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180017601`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180017601`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18001769b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180017744`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18001769b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x180017744`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001767c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180017726`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001767c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180017726`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001770e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001770e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800177dc`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800176dd`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180017774`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800176dd`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180017774`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800176c6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180017761`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800176c6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180017761`

## string_xrefs

- `0x18001766b`: `Links`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall IEFavResolver::ApplyOrderFromEdgeRecursively(
        IEFavResolver *this,
        struct IStream *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IStream **a6,
        unsigned int *a7)
{
  bool v11; // zf
  int v12; // eax
  const WCHAR *v13; // rdx
  int pv; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszStr1; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR psz; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h]
  LPVOID v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszPathOut; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[526]; // [rsp+82h] [rbp-7Eh] BYREF

  pszPathOut = 0;
  memset_0(v23, 0, 0x206u);
  if ( StringCchCopyW(&pszPathOut, 0x104u, a5) >= 0 )
  {
    while ( 1 )
    {
      v11 = *a3 == 0;
      if ( !*a3 )
        break;
      v19 = 0;
      v21 = 0;
      if ( (*(int (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, 0, 1, &v21) >= 0 )
      {
        pszStr1 = 0;
        if ( (int)IStream_ReadStrIE(a2, &pszStr1) >= 0 )
        {
          psz = 0;
          if ( (int)IStream_ReadStrIE(a2, &psz) >= 0 )
          {
            pv = 0;
            if ( IStream_Read(a2, &pv, 4u) >= 0 )
            {
              v20 = 0;
              if ( (int)IStream_ReadStrIE(a2, &v20) >= 0 )
              {
                --*a3;
                if ( StrCmpICW(pszStr1, a4) )
                {
                  if ( StrCmpICW(&pszPathOut, pszStr1) )
                  {
                    (*(void (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
                      a2,
                      v21,
                      0,
                      0);
                    ++*a3;
                    IEFavResolver::ApplyFavoriteOrder(this, a4, *a6, *a7);
                    v11 = *a3 == 0;
                    break;
                  }
                  ppstm = 0;
                  if ( CreateStreamOnHGlobal(0, 1, &ppstm) >= 0
                    && IStream_WriteStr(ppstm, psz) >= 0
                    && IStream_Write(ppstm, &pv, 4u) >= 0
                    && PathCchCombine(&pszPathOut, 0x104u, pszStr1, psz) >= 0
                    && PathCchAddBackslash(&pszPathOut, 0x104u) >= 0 )
                  {
                    v18 = 1;
                    IEFavResolver::ApplyOrderFromEdgeRecursively(
                      this,
                      a2,
                      a3,
                      (unsigned __int16 *)pszStr1,
                      &pszPathOut,
                      &ppstm,
                      &v18);
                  }
                  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppstm);
                }
                else
                {
                  if ( StrCmpICW(pszStr1, L"ROOT") || (v12 = StrCmpICW(psz, L"_Favorites_Bar_"), v13 = L"Links", v12) )
                    v13 = psz;
                  if ( IStream_WriteStr(*a6, v13) >= 0 )
                  {
                    ++*a7;
                    if ( IStream_Write(*a6, &pv, 4u) >= 0 )
                    {
                      if ( pv )
                      {
                        if ( PathCchCombine(&pszPathOut, 0x104u, pszStr1, psz) >= 0 )
                          PathCchAddBackslash(&pszPathOut, 0x104u);
                      }
                    }
                  }
                }
              }
              CoTaskMemFree(v20);
            }
          }
          CoTaskMemFree((LPVOID)psz);
        }
        CoTaskMemFree((LPVOID)pszStr1);
      }
    }
    if ( v11 )
      IEFavResolver::ApplyFavoriteOrder(this, a4, *a6, *a7);
  }
}

```

## disassembly

```asm
0x180017508  push    rbp
0x18001750a  push    rbx
0x18001750b  push    rsi
0x18001750c  push    rdi
0x18001750d  push    r12
0x18001750f  push    r13
0x180017511  push    r14
0x180017513  push    r15
0x180017515  lea     rbp, [rsp-1A8h]
0x18001751d  sub     rsp, 2A8h
0x180017524  mov     rax, cs:__security_cookie
0x18001752b  xor     rax, rsp
0x18001752e  mov     [rbp+1E0h+var_50], rax
0x180017535  mov     r12, r9
0x180017538  mov     rsi, r8
0x18001753b  mov     rdi, rdx
0x18001753e  mov     r13, rcx
0x180017541  mov     rbx, [rbp+1E0h+arg_20]
0x180017548  mov     r14, [rbp+1E0h+arg_28]
0x18001754f  mov     r15, [rbp+1E0h+arg_30]
0x180017556  xor     eax, eax
0x180017558  mov     [rbp+1E0h+pszPathOut], ax
0x18001755c  xor     edx, edx; Val
0x18001755e  mov     r8d, 206h; Size
0x180017564  lea     rcx, [rbp+1E0h+var_25E]; void *
0x180017568  call    memset_0
0x18001756d  mov     r8, rbx; unsigned __int16 *
0x180017570  mov     edx, 104h; unsigned __int64
0x180017575  lea     rcx, [rbp+1E0h+pszPathOut]; unsigned __int16 *
0x180017579  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001757e  xor     ebx, ebx
0x180017580  test    eax, eax
0x180017582  js      loc_180017829
0x180017588  cmp     [rsi], ebx
0x18001758a  jbe     loc_180017816
0x180017590  mov     [rsp+2E0h+var_278], rbx
0x180017595  mov     [rsp+2E0h+var_268], rbx
0x18001759a  mov     rax, [rdi]
0x18001759d  lea     r9, [rsp+2E0h+var_268]
0x1800175a2  mov     r8d, 1
0x1800175a8  mov     rdx, rbx
0x1800175ab  mov     rcx, rdi
0x1800175ae  mov     rax, [rax+28h]
0x1800175b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175b7  test    eax, eax
0x1800175b9  js      short loc_180017588
0x1800175bb  mov     [rsp+2E0h+pszStr1], rbx
0x1800175c0  lea     rdx, [rsp+2E0h+pszStr1]
0x1800175c5  mov     rcx, rdi
0x1800175c8  call    IStream_ReadStrIE
0x1800175cd  test    eax, eax
0x1800175cf  js      loc_1800177D7
0x1800175d5  mov     [rsp+2E0h+psz], rbx
0x1800175da  lea     rdx, [rsp+2E0h+psz]
0x1800175df  mov     rcx, rdi
0x1800175e2  call    IStream_ReadStrIE
0x1800175e7  test    eax, eax
0x1800175e9  js      loc_1800177CC
0x1800175ef  mov     [rsp+2E0h+pv], ebx
0x1800175f3  mov     r8d, 4; cb
0x1800175f9  lea     rdx, [rsp+2E0h+pv]; pv
0x1800175fe  mov     rcx, rdi; pstm
0x180017601  call    cs:__imp_IStream_Read
0x180017607  test    eax, eax
0x180017609  js      loc_1800177CC
0x18001760f  mov     [rsp+2E0h+var_270], rbx
0x180017614  lea     rdx, [rsp+2E0h+var_270]
0x180017619  mov     rcx, rdi
0x18001761c  call    IStream_ReadStrIE
0x180017621  test    eax, eax
0x180017623  js      loc_1800177C1
0x180017629  dec     dword ptr [rsi]
0x18001762b  mov     rdx, r12; pszStr2
0x18001762e  mov     rcx, [rsp+2E0h+pszStr1]; pszStr1
0x180017633  call    cs:__imp_StrCmpICW
0x180017639  test    eax, eax
0x18001763b  jnz     loc_1800176E8
0x180017641  lea     rdx, aRoot_0; "ROOT"
0x180017648  mov     rcx, [rsp+2E0h+pszStr1]; pszStr1
0x18001764d  call    cs:__imp_StrCmpICW
0x180017653  test    eax, eax
0x180017655  jnz     short loc_180017674
0x180017657  lea     rdx, aFavoritesBar_0; "_Favorites_Bar_"
0x18001765e  mov     rcx, [rsp+2E0h+psz]; pszStr1
0x180017663  call    cs:__imp_StrCmpICW
0x180017669  test    eax, eax
0x18001766b  lea     rdx, aLinks; "Links"
0x180017672  jz      short loc_180017679
0x180017674  mov     rdx, [rsp+2E0h+psz]; psz
0x180017679  mov     rcx, [r14]; pstm
0x18001767c  call    cs:__imp_IStream_WriteStr
0x180017682  test    eax, eax
0x180017684  js      loc_1800177C1
0x18001768a  inc     dword ptr [r15]
0x18001768d  mov     r8d, 4; cb
0x180017693  lea     rdx, [rsp+2E0h+pv]; pv
0x180017698  mov     rcx, [r14]; pstm
0x18001769b  call    cs:__imp_IStream_Write
0x1800176a1  test    eax, eax
0x1800176a3  js      loc_1800177C1
0x1800176a9  cmp     [rsp+2E0h+pv], ebx
0x1800176ad  jz      loc_1800177C1
0x1800176b3  mov     r9, [rsp+2E0h+psz]; pszMore
0x1800176b8  mov     r8, [rsp+2E0h+pszStr1]; pszPathIn
0x1800176bd  mov     edx, 104h; cchPathOut
0x1800176c2  lea     rcx, [rbp+1E0h+pszPathOut]; pszPathOut
0x1800176c6  call    cs:__imp_PathCchCombine
0x1800176cc  test    eax, eax
0x1800176ce  js      loc_1800177C1
0x1800176d4  mov     edx, 104h; cchPath
0x1800176d9  lea     rcx, [rbp+1E0h+pszPathOut]; pszPath
0x1800176dd  call    cs:__imp_PathCchAddBackslash
0x1800176e3  jmp     loc_1800177C1
0x1800176e8  mov     rdx, [rsp+2E0h+pszStr1]; pszStr2
0x1800176ed  lea     rcx, [rbp+1E0h+pszPathOut]; pszStr1
0x1800176f1  call    cs:__imp_StrCmpICW
0x1800176f7  test    eax, eax
0x1800176f9  jnz     loc_1800177E7
0x1800176ff  mov     [rsp+2E0h+ppstm], rbx
0x180017704  lea     r8, [rsp+2E0h+ppstm]; ppstm
0x180017709  lea     edx, [rax+1]; fDeleteOnRelease
0x18001770c  xor     ecx, ecx; hGlobal
0x18001770e  call    cs:__imp_CreateStreamOnHGlobal
0x180017714  test    eax, eax
0x180017716  js      loc_1800177B7
0x18001771c  mov     rdx, [rsp+2E0h+psz]; psz
0x180017721  mov     rcx, [rsp+2E0h+ppstm]; pstm
0x180017726  call    cs:__imp_IStream_WriteStr
0x18001772c  test    eax, eax
0x18001772e  js      loc_1800177B7
0x180017734  mov     r8d, 4; cb
0x18001773a  lea     rdx, [rsp+2E0h+pv]; pv
0x18001773f  mov     rcx, [rsp+2E0h+ppstm]; pstm
0x180017744  call    cs:__imp_IStream_Write
0x18001774a  test    eax, eax
0x18001774c  js      short loc_1800177B7
0x18001774e  mov     r9, [rsp+2E0h+psz]; pszMore
0x180017753  mov     r8, [rsp+2E0h+pszStr1]; pszPathIn
0x180017758  mov     edx, 104h; cchPathOut
0x18001775d  lea     rcx, [rbp+1E0h+pszPathOut]; pszPathOut
0x180017761  call    cs:__imp_PathCchCombine
0x180017767  test    eax, eax
0x180017769  js      short loc_1800177B7
0x18001776b  mov     edx, 104h; cchPath
0x180017770  lea     rcx, [rbp+1E0h+pszPathOut]; pszPath
0x180017774  call    cs:__imp_PathCchAddBackslash
0x18001777a  test    eax, eax
0x18001777c  js      short loc_1800177B7
0x18001777e  mov     [rsp+2E0h+var_280], 1
0x180017786  lea     rax, [rsp+2E0h+var_280]
0x18001778b  mov     [rsp+2E0h+var_2B0], rax; unsigned int *
0x180017790  lea     rax, [rsp+2E0h+ppstm]
0x180017795  mov     [rsp+2E0h+var_2B8], rax; struct IStream **
0x18001779a  lea     rax, [rbp+1E0h+pszPathOut]
0x18001779e  mov     [rsp+2E0h+var_2C0], rax; unsigned __int16 *
0x1800177a3  mov     r9, [rsp+2E0h+pszStr1]; unsigned __int16 *
0x1800177a8  mov     r8, rsi; unsigned int *
0x1800177ab  mov     rdx, rdi; struct IStream *
0x1800177ae  mov     rcx, r13; this
0x1800177b1  call    ?ApplyOrderFromEdgeRecursively@IEFavResolver@@AEAAXPEAUIStream@@PEAKPEAG2PEAPEAU2@1@Z; IEFavResolver::ApplyOrderFromEdgeRecursively(IStream *,ulong *,ushort *,ushort *,IStream * *,ulong *)
0x1800177b6  nop
0x1800177b7  lea     rcx, [rsp+2E0h+ppstm]
0x1800177bc  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x1800177c1  mov     rcx, [rsp+2E0h+var_270]; pv
0x1800177c6  call    cs:__imp_CoTaskMemFree
0x1800177cc  mov     rcx, [rsp+2E0h+psz]; pv
0x1800177d1  call    cs:__imp_CoTaskMemFree
0x1800177d7  mov     rcx, [rsp+2E0h+pszStr1]; pv
0x1800177dc  call    cs:__imp_CoTaskMemFree
0x1800177e2  jmp     loc_180017588
0x1800177e7  mov     rax, [rdi]
0x1800177ea  xor     r9d, r9d
0x1800177ed  xor     r8d, r8d
0x1800177f0  mov     rdx, [rsp+2E0h+var_268]
0x1800177f5  mov     rcx, rdi
0x1800177f8  mov     rax, [rax+28h]
0x1800177fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017801  inc     dword ptr [rsi]
0x180017803  mov     r9d, [r15]; unsigned int
0x180017806  mov     r8, [r14]; struct IStream *
0x180017809  mov     rdx, r12; unsigned __int16 *
0x18001780c  mov     rcx, r13; this
0x18001780f  call    ?ApplyFavoriteOrder@IEFavResolver@@AEAAJPEAGPEAUIStream@@K@Z; IEFavResolver::ApplyFavoriteOrder(ushort *,IStream *,ulong)
0x180017814  cmp     [rsi], ebx
0x180017816  jnz     short loc_180017829
0x180017818  mov     r9d, [r15]; unsigned int
0x18001781b  mov     r8, [r14]; struct IStream *
0x18001781e  mov     rdx, r12; unsigned __int16 *
0x180017821  mov     rcx, r13; this
0x180017824  call    ?ApplyFavoriteOrder@IEFavResolver@@AEAAJPEAGPEAUIStream@@K@Z; IEFavResolver::ApplyFavoriteOrder(ushort *,IStream *,ulong)
0x180017829  mov     rcx, [rbp+1E0h+var_50]
0x180017830  xor     rcx, rsp; StackCookie
0x180017833  call    __security_check_cookie
0x180017838  add     rsp, 2A8h
0x18001783f  pop     r15
0x180017841  pop     r14
0x180017843  pop     r13
0x180017845  pop     r12
0x180017847  pop     rdi
0x180017848  pop     rsi
0x180017849  pop     rbx
0x18001784a  pop     rbp
0x18001784b  retn
```
