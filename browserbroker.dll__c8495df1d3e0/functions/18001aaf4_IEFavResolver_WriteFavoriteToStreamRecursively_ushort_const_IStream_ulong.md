# IEFavResolver::WriteFavoriteToStreamRecursively(ushort const *,IStream * *,ulong *)

- ea: `0x18001aaf4`
- end: `0x18001ad6f`
- name: `?WriteFavoriteToStreamRecursively@IEFavResolver@@AEAAJPEBGPEAPEAUIStream@@PEAK@Z`
- size: `635`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, const unsigned __int16 *, struct IStream **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019724`
- `0x18001aaf4`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006cc4`
- `0x18000d17c`
- `0x180018080`
- `0x18001aaf4`
- `0x18001ae5c`
- `0x18001b6f8`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18001ac5e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18001acc1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18001ac5e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x18001acc1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001ac19`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001ac2f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001ac74`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001acd7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001ac19`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001ac2f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001ac74`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x18001acd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad39`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad28`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ad28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IEFavResolver::WriteFavoriteToStreamRecursively(
        IEFavResolver *this,
        unsigned __int16 *a2,
        struct IStream **a3,
        unsigned int *a4)
{
  HRESULT UnifiedFolderPath; // edi
  unsigned int v9; // esi
  unsigned int i; // r15d
  const unsigned __int16 *v11; // r12
  const WCHAR *v12; // rsi
  int v13; // r9d
  IStream *v14; // rcx
  HRESULT v15; // eax
  BSTR *v16; // r14
  unsigned int j; // r15d
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  int pv; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v21; // [rsp+48h] [rbp-B8h] BYREF
  struct IEdgeFavoritesEnumerator *v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-A8h]
  WCHAR psz[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v26; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v27[4174]; // [rsp+482h] [rbp+382h] BYREF

  v23 = a2;
  v22 = 0;
  UnifiedFolderPath = CFavoritesEnumerator_CreateInstance(&v22);
  if ( UnifiedFolderPath >= 0 )
  {
    v21 = 0;
    v19 = 0;
    UnifiedFolderPath = (*(__int64 (__fastcall **)(struct IEdgeFavoritesEnumerator *, unsigned __int16 *, __int64, LPVOID *, unsigned int *, _QWORD))(*(_QWORD *)v22 + 24LL))(
                          v22,
                          a2,
                          35,
                          &v21,
                          &v19,
                          0);
    v9 = v19;
    if ( UnifiedFolderPath >= 0 )
    {
      for ( i = 0; i < v19; v9 = v19 )
      {
        v11 = (const unsigned __int16 *)*((_QWORD *)v21 + 3 * i);
        v12 = (const WCHAR *)*((_QWORD *)v21 + 3 * i + 1);
        v26 = 0;
        memset_0(v27, 0, 0x1046u);
        if ( (int)GetUrlFromPath(v11, &v26) >= 0 )
        {
          UnifiedFolderPath = IEFavResolver::GetUnifiedFolderPath(this, v23, psz, v13);
          if ( UnifiedFolderPath >= 0 )
          {
            UnifiedFolderPath = IStream_WriteStr(*a3, psz);
            if ( UnifiedFolderPath >= 0 )
            {
              UnifiedFolderPath = IStream_WriteStr(*a3, v12);
              if ( UnifiedFolderPath >= 0 )
              {
                v14 = *a3;
                if ( v26 )
                {
                  pv = 0;
                  UnifiedFolderPath = IStream_Write(v14, &pv, 4u);
                  if ( UnifiedFolderPath >= 0 )
                    UnifiedFolderPath = IStream_WriteStr(*a3, &v26);
                  ++*a4;
                }
                else
                {
                  pv = 1;
                  UnifiedFolderPath = IStream_Write(v14, &pv, 4u);
                  if ( UnifiedFolderPath >= 0 )
                  {
                    UnifiedFolderPath = IStream_WriteStr(*a3, L" ");
                    ++*a4;
                    if ( UnifiedFolderPath >= 0 )
                    {
                      UnifiedFolderPath = StringCchCopyW(v25, 0x104u, v11);
                      if ( UnifiedFolderPath >= 0 )
                        UnifiedFolderPath = IEFavResolver::WriteFavoriteToStreamRecursively(this, v25, a3, a4);
                    }
                  }
                }
              }
            }
          }
        }
        ++i;
        v15 = 0;
        if ( UnifiedFolderPath >= 0 )
          v15 = UnifiedFolderPath;
        UnifiedFolderPath = v15;
      }
    }
    v16 = (BSTR *)v21;
    if ( v21 )
    {
      for ( j = 0; j < v9; ++j )
      {
        SysFreeString(v16[3 * j + 1]);
        SysFreeString(v16[3 * j]);
      }
      CoTaskMemFree(v16);
    }
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&v22);
  return (unsigned int)UnifiedFolderPath;
}

```

## disassembly

```asm
0x18001aaf4  push    rbp
0x18001aaf6  push    rbx
0x18001aaf7  push    rsi
0x18001aaf8  push    rdi
0x18001aaf9  push    r12
0x18001aafb  push    r13
0x18001aafd  push    r14
0x18001aaff  push    r15
0x18001ab01  lea     rbp, [rsp-13E8h]
0x18001ab09  mov     eax, 14E8h
0x18001ab0e  call    _alloca_probe
0x18001ab13  sub     rsp, rax
0x18001ab16  mov     rax, cs:__security_cookie
0x18001ab1d  xor     rax, rsp
0x18001ab20  mov     [rbp+1420h+var_50], rax
0x18001ab27  mov     r14, r9
0x18001ab2a  mov     rbx, r8
0x18001ab2d  mov     rsi, rdx
0x18001ab30  mov     [rsp+1520h+var_14C8], rdx
0x18001ab35  mov     r13, rcx
0x18001ab38  xor     r12d, r12d
0x18001ab3b  mov     [rsp+1520h+var_14D0], r12
0x18001ab40  lea     rcx, [rsp+1520h+var_14D0]; struct IEdgeFavoritesEnumerator **
0x18001ab45  call    ?CFavoritesEnumerator_CreateInstance@@YAJPEAPEAUIEdgeFavoritesEnumerator@@@Z; CFavoritesEnumerator_CreateInstance(IEdgeFavoritesEnumerator * *)
0x18001ab4a  mov     edi, eax
0x18001ab4c  test    eax, eax
0x18001ab4e  js      loc_18001AD40
0x18001ab54  mov     [rsp+1520h+var_14D8], r12
0x18001ab59  mov     [rsp+1520h+var_14E0], r12d
0x18001ab5e  mov     rcx, [rsp+1520h+var_14D0]
0x18001ab63  mov     rax, [rcx]
0x18001ab66  mov     [rsp+1520h+var_14F8], r12
0x18001ab6b  lea     rdx, [rsp+1520h+var_14E0]
0x18001ab70  mov     [rsp+1520h+var_1500], rdx
0x18001ab75  lea     r9, [rsp+1520h+var_14D8]
0x18001ab7a  lea     r8d, [r12+23h]
0x18001ab7f  mov     rdx, rsi
0x18001ab82  mov     rax, [rax+18h]
0x18001ab86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab8b  mov     edi, eax
0x18001ab8d  mov     esi, [rsp+1520h+var_14E0]
0x18001ab91  test    eax, eax
0x18001ab93  js      loc_18001AD01
0x18001ab99  mov     r15d, r12d
0x18001ab9c  test    esi, esi
0x18001ab9e  jz      loc_18001AD01
0x18001aba4  test    edi, edi
0x18001aba6  js      loc_18001AD01
0x18001abac  mov     eax, r15d
0x18001abaf  lea     rcx, [rax+rax*2]
0x18001abb3  mov     rax, [rsp+1520h+var_14D8]
0x18001abb8  mov     r12, [rax+rcx*8]
0x18001abbc  mov     rsi, [rax+rcx*8+8]
0x18001abc1  xor     eax, eax
0x18001abc3  mov     [rbp+1420h+var_10A0], ax
0x18001abca  xor     edx, edx; Val
0x18001abcc  mov     r8d, 1046h; Size
0x18001abd2  lea     rcx, [rbp+1420h+var_109E]; void *
0x18001abd9  call    memset_0
0x18001abde  lea     rdx, [rbp+1420h+var_10A0]
0x18001abe5  mov     rcx, r12
0x18001abe8  call    GetUrlFromPath
0x18001abed  test    eax, eax
0x18001abef  js      loc_18001ACE4
0x18001abf5  lea     r8, [rsp+1520h+psz]; unsigned __int16 *
0x18001abfa  mov     rdx, [rsp+1520h+var_14C8]; unsigned __int16 *
0x18001abff  mov     rcx, r13; this
0x18001ac02  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x18001ac07  mov     edi, eax
0x18001ac09  test    eax, eax
0x18001ac0b  js      loc_18001ACE4
0x18001ac11  lea     rdx, [rsp+1520h+psz]; psz
0x18001ac16  mov     rcx, [rbx]; pstm
0x18001ac19  call    cs:__imp_IStream_WriteStr
0x18001ac1f  mov     edi, eax
0x18001ac21  test    eax, eax
0x18001ac23  js      loc_18001ACE4
0x18001ac29  mov     rdx, rsi; psz
0x18001ac2c  mov     rcx, [rbx]; pstm
0x18001ac2f  call    cs:__imp_IStream_WriteStr
0x18001ac35  mov     edi, eax
0x18001ac37  xor     esi, esi
0x18001ac39  test    eax, eax
0x18001ac3b  js      loc_18001ACE4
0x18001ac41  lea     r8d, [rsi+4]; cb
0x18001ac45  lea     rdx, [rsp+1520h+pv]; pv
0x18001ac4a  mov     rcx, [rbx]; pstm
0x18001ac4d  cmp     [rbp+1420h+var_10A0], si
0x18001ac54  jnz     short loc_18001ACB9
0x18001ac56  mov     [rsp+1520h+pv], 1
0x18001ac5e  call    cs:__imp_IStream_Write
0x18001ac64  mov     edi, eax
0x18001ac66  test    eax, eax
0x18001ac68  js      short loc_18001ACE4
0x18001ac6a  lea     rdx, pszTrimChars; " "
0x18001ac71  mov     rcx, [rbx]; pstm
0x18001ac74  call    cs:__imp_IStream_WriteStr
0x18001ac7a  mov     edi, eax
0x18001ac7c  inc     dword ptr [r14]
0x18001ac7f  test    eax, eax
0x18001ac81  js      short loc_18001ACE4
0x18001ac83  mov     r8, r12; unsigned __int16 *
0x18001ac86  mov     edx, 104h; unsigned __int64
0x18001ac8b  lea     rcx, [rbp+1420h+var_12B0]; unsigned __int16 *
0x18001ac92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ac97  mov     edi, eax
0x18001ac99  xor     r12d, r12d
0x18001ac9c  test    eax, eax
0x18001ac9e  js      short loc_18001ACE7
0x18001aca0  mov     r9, r14; unsigned int *
0x18001aca3  mov     r8, rbx; struct IStream **
0x18001aca6  lea     rdx, [rbp+1420h+var_12B0]; unsigned __int16 *
0x18001acad  mov     rcx, r13; this
0x18001acb0  call    ?WriteFavoriteToStreamRecursively@IEFavResolver@@AEAAJPEBGPEAPEAUIStream@@PEAK@Z; IEFavResolver::WriteFavoriteToStreamRecursively(ushort const *,IStream * *,ulong *)
0x18001acb5  mov     edi, eax
0x18001acb7  jmp     short loc_18001ACE7
0x18001acb9  xor     r12d, r12d
0x18001acbc  mov     [rsp+1520h+pv], r12d
0x18001acc1  call    cs:__imp_IStream_Write
0x18001acc7  mov     edi, eax
0x18001acc9  test    eax, eax
0x18001accb  js      short loc_18001ACDF
0x18001accd  lea     rdx, [rbp+1420h+var_10A0]; psz
0x18001acd4  mov     rcx, [rbx]; pstm
0x18001acd7  call    cs:__imp_IStream_WriteStr
0x18001acdd  mov     edi, eax
0x18001acdf  inc     dword ptr [r14]
0x18001ace2  jmp     short loc_18001ACE7
0x18001ace4  xor     r12d, r12d
0x18001ace7  inc     r15d
0x18001acea  mov     eax, r12d
0x18001aced  test    edi, edi
0x18001acef  cmovns  eax, edi
0x18001acf2  mov     edi, eax
0x18001acf4  mov     esi, [rsp+1520h+var_14E0]
0x18001acf8  cmp     r15d, esi
0x18001acfb  jb      loc_18001ABA4
0x18001ad01  mov     r14, [rsp+1520h+var_14D8]
0x18001ad06  test    r14, r14
0x18001ad09  jz      short loc_18001AD40
0x18001ad0b  mov     r15d, r12d
0x18001ad0e  test    esi, esi
0x18001ad10  jz      short loc_18001AD36
0x18001ad12  mov     eax, r15d
0x18001ad15  lea     rbx, [rax+rax*2]
0x18001ad19  mov     rcx, [r14+rbx*8+8]; bstrString
0x18001ad1e  call    cs:__imp_SysFreeString
0x18001ad24  mov     rcx, [r14+rbx*8]; bstrString
0x18001ad28  call    cs:__imp_SysFreeString
0x18001ad2e  inc     r15d
0x18001ad31  cmp     r15d, esi
0x18001ad34  jb      short loc_18001AD12
0x18001ad36  mov     rcx, r14; pv
0x18001ad39  call    cs:__imp_CoTaskMemFree
0x18001ad3f  nop
0x18001ad40  lea     rcx, [rsp+1520h+var_14D0]
0x18001ad45  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001ad4a  mov     eax, edi
0x18001ad4c  mov     rcx, [rbp+1420h+var_50]
0x18001ad53  xor     rcx, rsp; StackCookie
0x18001ad56  call    __security_check_cookie
0x18001ad5b  add     rsp, 14E8h
0x18001ad62  pop     r15
0x18001ad64  pop     r14
0x18001ad66  pop     r13
0x18001ad68  pop     r12
0x18001ad6a  pop     rdi
0x18001ad6b  pop     rsi
0x18001ad6c  pop     rbx
0x18001ad6d  pop     rbp
0x18001ad6e  retn
```
