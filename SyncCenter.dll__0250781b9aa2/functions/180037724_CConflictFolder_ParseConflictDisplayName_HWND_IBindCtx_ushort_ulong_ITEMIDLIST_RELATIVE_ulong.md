# CConflictFolder::_ParseConflictDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180037724`
- end: `0x18003790e`
- name: `?_ParseConflictDisplayName@CConflictFolder@@AEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `490`
- prototype: `__int64 __fastcall(CConflictFolder *this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800340f0`

## callees

- `0x180028d84`
- `0x180031498`
- `0x180035f98`
- `0x180037680`
- `0x180037724`
- `0x180038590`
- `0x180052950`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180037792`
- `SHLWAPI!StrChrW` at `0x1800377e0`
- `SHLWAPI!StrChrW` at `0x180037792`
- `SHLWAPI!StrChrW` at `0x1800377e0`
- `SHLWAPI!StrCmpNW` at `0x18003777a`
- `SHLWAPI!StrCmpNW` at `0x18003777a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800378d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800378dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800378d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800378dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800378e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800378e6`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_ParseConflictDisplayName(
        CConflictFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  int v8; // ebx
  PWSTR v9; // rax
  PWSTR v10; // rdi
  __int64 v11; // r13
  const WCHAR *v12; // rsi
  PWSTR v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  PWSTR v16; // r14
  __int64 v17; // rdi
  CConflictFolder *v18; // rcx
  int v19; // eax
  HLOCAL v20; // rsi
  void *v21; // rdi
  CConflictFolder *v22; // rcx
  const struct CConflictFolder::tagIDCONFLICT *v23; // rdx
  unsigned int v24; // eax
  unsigned __int16 *v26; // [rsp+30h] [rbp-D0h]
  unsigned int v27; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  struct tagBLOB v29; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v31[64]; // [rsp+70h] [rbp-90h] BYREF

  v8 = -2147467259;
  *a6 = 0;
  *a5 = 0;
  if ( !StrCmpNW(a4, L"::", 2) )
  {
    v9 = StrChrW(a4 + 2, 0x3Au);
    v10 = v9;
    if ( v9 )
    {
      if ( (int)StringCchCopyNW(v31, 0x40u, a4 + 2, v9 - (a4 + 2)) >= 0 )
      {
        v11 = (unsigned int)(((char *)v10 - (char *)a4 + 2) >> 1);
        v12 = &a4[v11];
        v13 = StrChrW(v12, 0x3Au);
        v16 = v13;
        if ( v13 )
        {
          hMem = 0;
          v17 = v13 - v12;
          v8 = _AllocStringWorker<CTLocalAllocPolicy>(v15, v14, v12, v17, 1, &hMem);
          if ( v8 >= 0 )
          {
            v27 = v17 + v11 + 1;
            v29 = 0;
            *(_OWORD *)pv = 0;
            v19 = CConflictFolder::_ParseBlobPart(v18, v16 + 1, &v29, (struct tagBLOB *)pv, &v27);
            v20 = hMem;
            v8 = v19;
            if ( v19 >= 0 )
            {
              v21 = pv[1];
              v26 = (unsigned __int16 *)hMem;
              hMem = 0;
              v8 = CConflictFolder::s_IDCONFLICT_Create(
                     v31,
                     v29.cbSize,
                     v29.pBlobData,
                     (unsigned int)pv[0],
                     (const unsigned __int8 *)pv[1],
                     (struct CConflictFolder::tagIDCONFLICT **)&hMem,
                     v26);
              if ( v8 >= 0 )
              {
                v23 = (const struct CConflictFolder::tagIDCONFLICT *)hMem;
                v24 = v27;
                *a6 = (struct _ITEMIDLIST_RELATIVE *)hMem;
                *a5 = v24;
                if ( a7 )
                  CConflictFolder::_GetAttributesOfConflict(v22, v23, a7);
              }
              CoTaskMemFree(v21);
              CoTaskMemFree(v29.pBlobData);
            }
            LocalFree(v20);
          }
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180037724  push    rbp
0x180037726  push    rbx
0x180037727  push    rsi
0x180037728  push    rdi
0x180037729  push    r12
0x18003772b  push    r13
0x18003772d  push    r14
0x18003772f  push    r15
0x180037731  lea     rbp, [rsp-8]
0x180037736  sub     rsp, 108h
0x18003773d  mov     rax, cs:__security_cookie
0x180037744  xor     rax, rsp
0x180037747  mov     [rbp+40h+var_50], rax
0x18003774b  mov     r12, [rbp+40h+arg_28]
0x18003774f  lea     rdx, asc_18005E9EC; "::"
0x180037756  mov     r15, [rbp+40h+arg_20]
0x18003775a  mov     r8d, 2; nChar
0x180037760  mov     rcx, r9; psz1
0x180037763  mov     r14, r9
0x180037766  mov     ebx, 80004005h
0x18003776b  mov     qword ptr [r12], 0
0x180037773  mov     dword ptr [r15], 0
0x18003777a  call    cs:__imp_StrCmpNW
0x180037780  test    eax, eax
0x180037782  jnz     loc_1800378EC
0x180037788  lea     rsi, [r14+4]
0x18003778c  mov     rcx, rsi; pszStart
0x18003778f  lea     edx, [rax+3Ah]; wMatch
0x180037792  call    cs:__imp_StrChrW
0x180037798  mov     rdi, rax
0x18003779b  test    rax, rax
0x18003779e  jz      loc_1800378EC
0x1800377a4  mov     r9, rax
0x1800377a7  lea     rcx, [rsp+140h+var_D0]; unsigned __int16 *
0x1800377ac  sub     r9, rsi
0x1800377af  mov     r8, rsi; unsigned __int16 *
0x1800377b2  sar     r9, 1; unsigned __int64
0x1800377b5  mov     edx, 40h ; '@'; unsigned __int64
0x1800377ba  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800377bf  test    eax, eax
0x1800377c1  js      loc_1800378EC
0x1800377c7  sub     rdi, r14
0x1800377ca  mov     edx, 3Ah ; ':'; wMatch
0x1800377cf  lea     r13, [rdi+2]
0x1800377d3  sar     r13, 1
0x1800377d6  mov     r13d, r13d
0x1800377d9  lea     rsi, [r14+r13*2]
0x1800377dd  mov     rcx, rsi; pszStart
0x1800377e0  call    cs:__imp_StrChrW
0x1800377e6  mov     r14, rax
0x1800377e9  test    rax, rax
0x1800377ec  jz      loc_1800378EC
0x1800377f2  mov     rdi, rax
0x1800377f5  mov     [rsp+140h+hMem], 0
0x1800377fe  lea     rax, [rsp+140h+hMem]
0x180037803  sub     rdi, rsi
0x180037806  mov     [rsp+140h+var_118], rax
0x18003780b  mov     r8, rsi
0x18003780e  sar     rdi, 1
0x180037811  mov     r9, rdi
0x180037814  mov     [rsp+140h+var_120], 1
0x18003781d  call    ??$_AllocStringWorker@VCTLocalAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTLocalAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180037822  mov     ebx, eax
0x180037824  test    eax, eax
0x180037826  js      loc_1800378EC
0x18003782c  lea     eax, [r13+1]
0x180037830  xorps   xmm0, xmm0
0x180037833  add     eax, edi
0x180037835  lea     rdx, [r14+2]; unsigned __int16 *
0x180037839  mov     [rsp+140h+var_100], eax
0x18003783d  lea     r9, [rsp+140h+pv]; struct tagBLOB *
0x180037842  lea     rax, [rsp+140h+var_100]
0x180037847  xorps   xmm1, xmm1
0x18003784a  lea     r8, [rsp+140h+var_F0]; struct tagBLOB *
0x18003784f  mov     [rsp+140h+var_120], rax; unsigned int *
0x180037854  movups  xmmword ptr [rsp+140h+var_F0.cbSize], xmm0
0x180037859  movups  xmmword ptr [rsp+140h+pv], xmm1
0x18003785e  call    ?_ParseBlobPart@CConflictFolder@@AEAAJPEBGPEAUtagBLOB@@1PEAK@Z; CConflictFolder::_ParseBlobPart(ushort const *,tagBLOB *,tagBLOB *,ulong *)
0x180037863  mov     rsi, [rsp+140h+hMem]
0x180037868  mov     ebx, eax
0x18003786a  test    eax, eax
0x18003786c  js      short loc_1800378E3
0x18003786e  mov     rdi, [rsp+140h+pv+8]
0x180037873  lea     rax, [rsp+140h+hMem]
0x180037878  mov     r9d, dword ptr [rsp+140h+pv]; unsigned int
0x18003787d  lea     rcx, [rsp+140h+var_D0]; unsigned __int16 *
0x180037882  mov     r8, [rsp+140h+var_F0.pBlobData]; unsigned __int8 *
0x180037887  mov     edx, [rsp+140h+var_F0.cbSize]; unsigned int
0x18003788b  mov     [rsp+140h+var_110], rsi; unsigned __int16 *
0x180037890  mov     [rsp+140h+var_118], rax; struct CConflictFolder::tagIDCONFLICT **
0x180037895  mov     [rsp+140h+var_120], rdi; unsigned __int8 *
0x18003789a  mov     [rsp+140h+hMem], 0
0x1800378a3  call    ?s_IDCONFLICT_Create@CConflictFolder@@CAJPEBGKPEBEK1PEAPEAUtagIDCONFLICT@1@0@Z; CConflictFolder::s_IDCONFLICT_Create(ushort const *,ulong,uchar const *,ulong,uchar const *,CConflictFolder::tagIDCONFLICT * *,ushort const *)
0x1800378a8  mov     ebx, eax
0x1800378aa  test    eax, eax
0x1800378ac  js      short loc_1800378CF
0x1800378ae  mov     rdx, [rsp+140h+hMem]; struct CConflictFolder::tagIDCONFLICT *
0x1800378b3  mov     r8, [rbp+40h+arg_30]; unsigned int *
0x1800378ba  mov     eax, [rsp+140h+var_100]
0x1800378be  mov     [r12], rdx
0x1800378c2  mov     [r15], eax
0x1800378c5  test    r8, r8
0x1800378c8  jz      short loc_1800378CF
0x1800378ca  call    ?_GetAttributesOfConflict@CConflictFolder@@AEAAJPEFBUtagIDCONFLICT@1@PEAK@Z; CConflictFolder::_GetAttributesOfConflict(CConflictFolder::tagIDCONFLICT const *,ulong *)
0x1800378cf  mov     rcx, rdi; pv
0x1800378d2  call    cs:__imp_CoTaskMemFree
0x1800378d8  mov     rcx, [rsp+140h+var_F0.pBlobData]; pv
0x1800378dd  call    cs:__imp_CoTaskMemFree
0x1800378e3  mov     rcx, rsi; hMem
0x1800378e6  call    cs:__imp_LocalFree
0x1800378ec  mov     eax, ebx
0x1800378ee  mov     rcx, [rbp+40h+var_50]
0x1800378f2  xor     rcx, rsp; StackCookie
0x1800378f5  call    __security_check_cookie
0x1800378fa  add     rsp, 108h
0x180037901  pop     r15
0x180037903  pop     r14
0x180037905  pop     r13
0x180037907  pop     r12
0x180037909  pop     rdi
0x18003790a  pop     rsi
0x18003790b  pop     rbx
0x18003790c  pop     rbp
0x18003790d  retn
```
