# CSearchQueryHelper::_GenerateSql(ICondition *,IVirtualPropertyArray *,wchar_t *,unsigned __int64)

- ea: `0x180072eb0`
- end: `0x180073346`
- name: `?_GenerateSql@CSearchQueryHelper@@AEAAJPEAUICondition@@PEAUIVirtualPropertyArray@@PEA_W_K@Z`
- size: `1174`
- prototype: `__int64 __fastcall(CSearchQueryHelper *this, struct ICondition *, struct IVirtualPropertyArray *, wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800564f0`

## callees

- `0x180023e60`
- `0x18002e5c0`
- `0x18003bc28`
- `0x18005c9f4`
- `0x18005daf0`
- `0x18005e740`
- `0x180072c58`
- `0x180072eb0`
- `0x180073420`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800730e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007318f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800730e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007318f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800731ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800732ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800731ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800732ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073316`

## pseudocode

```c
__int64 __fastcall CSearchQueryHelper::_GenerateSql(
        CSearchQueryHelper *this,
        struct ICondition *a2,
        struct IVirtualPropertyArray *a3,
        wchar_t *a4)
{
  int v7; // ebx
  const wchar_t *v8; // rdx
  CSearchQueryHelper *v9; // rcx
  struct IConditionVtbl *lpVtbl; // rax
  int v11; // eax
  CSearchQueryHelper *v12; // rcx
  wchar_t *v13; // rsi
  unsigned int v14; // r14d
  unsigned __int64 v15; // rbx
  int v16; // eax
  int v17; // ecx
  const wchar_t *v18; // rdx
  CSearchQueryHelper *v19; // rcx
  wchar_t *v20; // rbx
  unsigned __int64 v21; // r15
  int v22; // eax
  int v23; // ecx
  WCHAR *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  WCHAR *v28; // rcx
  unsigned int cchCount2; // [rsp+28h] [rbp-D8h]
  unsigned int cchCount2a; // [rsp+28h] [rbp-D8h]
  unsigned int cchCount2b; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v36; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  PCNZWCH v38[10]; // [rsp+60h] [rbp-A0h] BYREF
  PCNZWCH lpString1[100]; // [rsp+B0h] [rbp-50h] BYREF

  pszDest = a4;
  v34 = 0x10000;
  v7 = StringCchCopyExW(a4, 0x10000u, L"SELECT", &pszDest, &v34, cchCount2);
  if ( v7 >= 0 )
  {
    if ( *((int *)this + 22) >= 0 )
    {
      v33 = *((_DWORD *)this + 22);
      v7 = StringCchPrintfExW(pszDest, v34, &pszDest, &v34, 0, L" TOP %d", v33);
    }
    if ( v7 >= 0 )
    {
      memset_0(lpString1, 0, sizeof(lpString1));
      v8 = (const wchar_t *)*((_QWORD *)this + 7);
      v36 = 0;
      v7 = CSearchQueryHelper::_ParseStringList(v9, v8, 0, (wchar_t **)lpString1, 0x64u, (unsigned __int64 *)&v36);
      if ( v7 >= 0 )
      {
        lpVtbl = a2->lpVtbl;
        pv = 0;
        v7 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, LPVOID *))lpVtbl->QueryInterface)(
               a2,
               &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
               &pv);
        if ( v7 < 0 )
        {
          v13 = v36;
        }
        else
        {
          v11 = CSearchQueryHelper::_GatherColumns(
                  this,
                  (struct ICondition2 *)pv,
                  a3,
                  (wchar_t **)lpString1,
                  0x64u,
                  (unsigned __int64 *)&v36);
          v13 = v36;
          v7 = v11;
          if ( v11 >= 0 )
          {
            v7 = CSearchQueryHelper::_WriteColumns(v12, lpString1, (unsigned __int64)v36, pszDest, v34, &pszDest, &v34);
            if ( v7 >= 0 )
            {
              v7 = StringCchPrintfExW(pszDest, v34, &pszDest, &v34, 0, L" FROM \"%s\"");
              if ( v7 >= 0 )
              {
                v7 = StringCchCopyExW(pszDest, v34, L" WHERE ", &pszDest, &v34, cchCount2a);
                if ( v7 >= 0 )
                {
                  v14 = 13;
                  v15 = 0;
                  if ( *((_DWORD *)this + 10) != 2 )
                    v14 = 5;
                  do
                  {
                    if ( v15 >= (unsigned __int64)v13 )
                      break;
                    v16 = CompareStringW(0x7Fu, 1u, lpString1[v15], -1, L"System.Search.Rank", -1);
                    v17 = v14 | 2;
                    if ( v16 != 2 )
                      v17 = v14;
                    ++v15;
                    v14 = v17;
                  }
                  while ( (v17 & 2) == 0 );
                  if ( (v14 & 2) == 0
                    && !(unsigned int)CSearchQueryHelper::_IsEmptyString(*((const wchar_t **)this + 9)) )
                  {
                    memset_0(v38, 0, sizeof(v38));
                    v18 = (const wchar_t *)*((_QWORD *)this + 9);
                    v36 = 0;
                    if ( CSearchQueryHelper::_ParseStringList(
                           v19,
                           v18,
                           1u,
                           (wchar_t **)v38,
                           0xAu,
                           (unsigned __int64 *)&v36) >= 0 )
                    {
                      v20 = v36;
                      v21 = 0;
                      do
                      {
                        if ( v21 >= (unsigned __int64)v20 )
                          break;
                        v22 = CompareStringW(0x7Fu, 1u, v38[v21], -1, L"System.Search.Rank", -1);
                        v23 = v14 | 2;
                        if ( v22 != 2 )
                          v23 = v14;
                        ++v21;
                        v14 = v23;
                      }
                      while ( (v23 & 2) == 0 );
                      while ( v20 )
                      {
                        v24 = (WCHAR *)v38[(_QWORD)v20 - 1];
                        v20 = (wchar_t *)((char *)v20 - 1);
                        CoTaskMemFree(v24);
                      }
                    }
                  }
                  if ( (unsigned int)CSearchQueryHelper::_IsEmptyString(*((const wchar_t **)this + 12))
                    || (v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 136LL))(*((_QWORD *)this + 15)),
                        v7 >= 0) )
                  {
                    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 144LL))(
                           *((_QWORD *)this + 15),
                           *((unsigned int *)this + 26));
                    if ( v7 >= 0 )
                    {
                      v25 = *((_QWORD *)this + 15);
                      v36 = 0;
                      v7 = (*(__int64 (__fastcall **)(__int64, struct ICondition *, _QWORD, wchar_t **))(*(_QWORD *)v25 + 104LL))(
                             v25,
                             a2,
                             v14,
                             &v36);
                      if ( v7 >= 0 )
                      {
                        v7 = StringCchCopyExW(pszDest, v34, v36, &pszDest, &v34, cchCount2b);
                        if ( v7 >= 0 )
                        {
                          if ( (unsigned int)CSearchQueryHelper::_IsEmptyString(*((const wchar_t **)this + 8))
                            || (v7 = StringCchPrintfExW(pszDest, v34, &pszDest, &v34, 0, L" %s", v26), v7 >= 0) )
                          {
                            if ( !(unsigned int)CSearchQueryHelper::_IsEmptyString(*((const wchar_t **)this + 9)) )
                              v7 = StringCchPrintfExW(pszDest, v34, &pszDest, &v34, 0, L" ORDER BY %s", v27);
                          }
                        }
                        CoTaskMemFree(v36);
                      }
                    }
                  }
                }
              }
            }
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        }
        while ( v13 )
        {
          v28 = (WCHAR *)v38[(_QWORD)v13 + 9];
          v13 = (wchar_t *)((char *)v13 - 1);
          CoTaskMemFree(v28);
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180072eb0  push    rbp
0x180072eb2  push    rbx
0x180072eb3  push    rsi
0x180072eb4  push    rdi
0x180072eb5  push    r12
0x180072eb7  push    r13
0x180072eb9  push    r14
0x180072ebb  push    r15
0x180072ebd  lea     rbp, [rsp-2E8h]
0x180072ec5  sub     rsp, 3E8h
0x180072ecc  mov     rax, cs:__security_cookie
0x180072ed3  xor     rax, rsp
0x180072ed6  mov     [rbp+320h+var_50], rax
0x180072edd  mov     rax, r9
0x180072ee0  mov     rdi, rcx
0x180072ee3  lea     rcx, [rsp+420h+var_3E0]
0x180072ee8  mov     [rsp+420h+pszDest], rax
0x180072eed  mov     r12, rdx
0x180072ef0  mov     [rsp+420h+lpString2], rcx; unsigned __int64 *
0x180072ef5  mov     rsi, r8
0x180072ef8  lea     r9, [rsp+420h+pszDest]; wchar_t **
0x180072efd  mov     edx, 10000h; unsigned __int64
0x180072f02  lea     r8, aSelect; "SELECT"
0x180072f09  mov     rcx, rax; wchar_t *
0x180072f0c  mov     [rsp+420h+var_3E0], rdx
0x180072f11  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180072f16  xor     r13d, r13d
0x180072f19  mov     ebx, eax
0x180072f1b  test    eax, eax
0x180072f1d  js      loc_180073321
0x180072f23  mov     eax, [rdi+58h]
0x180072f26  test    eax, eax
0x180072f28  js      short loc_180072F5A
0x180072f2a  mov     rdx, [rsp+420h+var_3E0]; unsigned __int64
0x180072f2f  lea     r9, [rsp+420h+var_3E0]; unsigned __int64 *
0x180072f34  mov     rcx, [rsp+420h+pszDest]; pszDest
0x180072f39  lea     r8, [rsp+420h+pszDest]; wchar_t **
0x180072f3e  mov     [rsp+420h+var_3F0], eax
0x180072f42  lea     rax, aTopD; " TOP %d"
0x180072f49  mov     qword ptr [rsp+420h+cchCount2], rax; wchar_t *
0x180072f4e  mov     [rsp+420h+lpString2], r13; unsigned int
0x180072f53  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x180072f58  mov     ebx, eax
0x180072f5a  test    ebx, ebx
0x180072f5c  js      loc_180073321
0x180072f62  xor     edx, edx; Val
0x180072f64  lea     rcx, [rbp+320h+lpString1]; void *
0x180072f68  mov     r8d, 320h; Size
0x180072f6e  call    memset_0
0x180072f73  mov     rdx, [rdi+38h]; wchar_t *
0x180072f77  lea     rax, [rsp+420h+var_3D0]
0x180072f7c  mov     qword ptr [rsp+420h+cchCount2], rax; unsigned __int64 *
0x180072f81  lea     r9, [rbp+320h+lpString1]; wchar_t **
0x180072f85  mov     r14d, 64h ; 'd'
0x180072f8b  mov     [rsp+420h+var_3D0], r13
0x180072f90  xor     r8d, r8d; unsigned __int64
0x180072f93  mov     [rsp+420h+lpString2], r14; unsigned __int64
0x180072f98  call    ?_ParseStringList@CSearchQueryHelper@@AEAAJPEB_W_KPEAPEA_W1PEA_K@Z; CSearchQueryHelper::_ParseStringList(wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64,unsigned __int64 *)
0x180072f9d  mov     ebx, eax
0x180072f9f  test    eax, eax
0x180072fa1  js      loc_180073321
0x180072fa7  mov     rax, [r12]
0x180072fab  lea     r8, [rsp+420h+pv]
0x180072fb0  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180072fb7  mov     [rsp+420h+pv], r13
0x180072fbc  mov     rcx, r12
0x180072fbf  mov     rax, [rax]
0x180072fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072fc7  mov     ebx, eax
0x180072fc9  test    eax, eax
0x180072fcb  js      loc_180073307
0x180072fd1  mov     rdx, [rsp+420h+pv]; struct ICondition2 *
0x180072fd6  lea     rax, [rsp+420h+var_3D0]
0x180072fdb  mov     qword ptr [rsp+420h+cchCount2], rax; unsigned __int64 *
0x180072fe0  lea     r9, [rbp+320h+lpString1]; wchar_t **
0x180072fe4  mov     r8, rsi; struct IVirtualPropertyArray *
0x180072fe7  mov     [rsp+420h+lpString2], r14; unsigned __int64
0x180072fec  mov     rcx, rdi; this
0x180072fef  call    ?_GatherColumns@CSearchQueryHelper@@AEAAJPEAUICondition2@@PEAUIVirtualPropertyArray@@PEAPEA_W_KPEA_K@Z; CSearchQueryHelper::_GatherColumns(ICondition2 *,IVirtualPropertyArray *,wchar_t * *,unsigned __int64,unsigned __int64 *)
0x180072ff4  mov     rsi, [rsp+420h+var_3D0]
0x180072ff9  mov     ebx, eax
0x180072ffb  test    eax, eax
0x180072ffd  js      loc_1800732F4
0x180073003  mov     r9, [rsp+420h+pszDest]; wchar_t *
0x180073008  lea     rax, [rsp+420h+var_3E0]
0x18007300d  mov     qword ptr [rsp+420h+var_3F0], rax; unsigned __int64 *
0x180073012  lea     rdx, [rbp+320h+lpString1]; wchar_t **
0x180073016  lea     rax, [rsp+420h+pszDest]
0x18007301b  mov     r8, rsi; unsigned __int64
0x18007301e  mov     qword ptr [rsp+420h+cchCount2], rax; wchar_t **
0x180073023  mov     rax, [rsp+420h+var_3E0]
0x180073028  mov     [rsp+420h+lpString2], rax; unsigned __int64
0x18007302d  call    ?_WriteColumns@CSearchQueryHelper@@AEAAJPEBQEB_W_KPEA_W1PEAPEA_WPEA_K@Z; CSearchQueryHelper::_WriteColumns(wchar_t const * const *,unsigned __int64,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x180073032  mov     ebx, eax
0x180073034  test    eax, eax
0x180073036  js      loc_1800732F4
0x18007303c  mov     rax, [rdi+50h]
0x180073040  lea     r9, [rsp+420h+var_3E0]; unsigned __int64 *
0x180073045  mov     rdx, [rsp+420h+var_3E0]; unsigned __int64
0x18007304a  lea     r8, [rsp+420h+pszDest]; wchar_t **
0x18007304f  mov     rcx, [rsp+420h+pszDest]; pszDest
0x180073054  mov     qword ptr [rsp+420h+var_3F0], rax
0x180073059  lea     rax, aFromS; " FROM \"%s\""
0x180073060  mov     qword ptr [rsp+420h+cchCount2], rax; unsigned int
0x180073065  mov     [rsp+420h+lpString2], r13; unsigned int
0x18007306a  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x18007306f  mov     ebx, eax
0x180073071  test    eax, eax
0x180073073  js      loc_1800732F4
0x180073079  mov     rdx, [rsp+420h+var_3E0]; unsigned __int64
0x18007307e  lea     rax, [rsp+420h+var_3E0]
0x180073083  mov     rcx, [rsp+420h+pszDest]; wchar_t *
0x180073088  lea     r9, [rsp+420h+pszDest]; wchar_t **
0x18007308d  lea     r8, aWhere; " WHERE "
0x180073094  mov     [rsp+420h+lpString2], rax; unsigned __int64 *
0x180073099  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18007309e  mov     ebx, eax
0x1800730a0  test    eax, eax
0x1800730a2  js      loc_1800732F4
0x1800730a8  cmp     dword ptr [rdi+28h], 2
0x1800730ac  lea     eax, [r14-5Fh]
0x1800730b0  lea     r14d, [rax+8]
0x1800730b4  mov     rbx, r13
0x1800730b7  cmovnz  r14d, eax
0x1800730bb  lea     r13, String2; "System.Search.Rank"
0x1800730c2  cmp     rbx, rsi
0x1800730c5  jnb     short loc_180073102
0x1800730c7  mov     r8, [rbp+rbx*8+320h+lpString1]; lpString1
0x1800730cc  or      r9d, 0FFFFFFFFh; cchCount1
0x1800730d0  mov     [rsp+420h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800730d8  mov     [rsp+420h+lpString2], r13; lpString2
0x1800730dd  lea     edx, [r9+2]; dwCmpFlags
0x1800730e1  lea     ecx, [rdx+7Eh]; Locale
0x1800730e4  call    cs:__imp_CompareStringW
0x1800730ea  mov     ecx, r14d
0x1800730ed  or      ecx, 2
0x1800730f0  cmp     eax, 2
0x1800730f3  cmovnz  ecx, r14d
0x1800730f7  inc     rbx
0x1800730fa  mov     r14d, ecx
0x1800730fd  test    cl, 2
0x180073100  jz      short loc_1800730C2
0x180073102  mov     r13d, 0
0x180073108  test    r14b, 2
0x18007310c  jnz     loc_1800731C5
0x180073112  mov     rcx, [rdi+48h]; wchar_t *
0x180073116  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x18007311b  test    eax, eax
0x18007311d  jnz     loc_1800731C5
0x180073123  xor     edx, edx; Val
0x180073125  lea     r8d, [r13+50h]; Size
0x180073129  lea     rcx, [rsp+420h+var_3C0]; void *
0x18007312e  call    memset_0
0x180073133  mov     rdx, [rdi+48h]; wchar_t *
0x180073137  lea     rax, [rsp+420h+var_3D0]
0x18007313c  mov     qword ptr [rsp+420h+cchCount2], rax; unsigned __int64 *
0x180073141  lea     r9, [rsp+420h+var_3C0]; wchar_t **
0x180073146  lea     r8d, [r13+1]; unsigned __int64
0x18007314a  mov     [rsp+420h+lpString2], 0Ah; unsigned __int64
0x180073153  mov     [rsp+420h+var_3D0], r13
0x180073158  call    ?_ParseStringList@CSearchQueryHelper@@AEAAJPEB_W_KPEAPEA_W1PEA_K@Z; CSearchQueryHelper::_ParseStringList(wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64,unsigned __int64 *)
0x18007315d  test    eax, eax
0x18007315f  js      short loc_1800731C5
0x180073161  mov     rbx, [rsp+420h+var_3D0]
0x180073166  mov     r15d, r13d
0x180073169  lea     r13, String2; "System.Search.Rank"
0x180073170  cmp     r15, rbx
0x180073173  jnb     short loc_1800731AD
0x180073175  mov     r8, [rsp+r15*8+420h+var_3C0]; lpString1
0x18007317a  or      eax, 0FFFFFFFFh
0x18007317d  mov     [rsp+420h+cchCount2], eax; cchCount2
0x180073181  mov     r9d, eax; cchCount1
0x180073184  mov     [rsp+420h+lpString2], r13; lpString2
0x180073189  lea     edx, [rax+2]; dwCmpFlags
0x18007318c  lea     ecx, [rdx+7Eh]; Locale
0x18007318f  call    cs:__imp_CompareStringW
0x180073195  mov     ecx, r14d
0x180073198  or      ecx, 2
0x18007319b  cmp     eax, 2
0x18007319e  cmovnz  ecx, r14d
0x1800731a2  inc     r15
0x1800731a5  mov     r14d, ecx
0x1800731a8  test    cl, 2
0x1800731ab  jz      short loc_180073170
0x1800731ad  xor     r13d, r13d
0x1800731b0  jmp     short loc_1800731C0
0x1800731b2  mov     rcx, [rsp+rbx*8+420h+pv]; pv
0x1800731b7  dec     rbx
0x1800731ba  call    cs:__imp_CoTaskMemFree
0x1800731c0  test    rbx, rbx
0x1800731c3  jnz     short loc_1800731B2
0x1800731c5  mov     rdx, [rdi+60h]
0x1800731c9  mov     rcx, rdx; wchar_t *
0x1800731cc  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x1800731d1  test    eax, eax
0x1800731d3  jnz     short loc_1800731F2
0x1800731d5  mov     rcx, [rdi+78h]
0x1800731d9  mov     rax, [rcx]
0x1800731dc  mov     rax, [rax+88h]
0x1800731e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800731e8  mov     ebx, eax
0x1800731ea  test    eax, eax
0x1800731ec  js      loc_1800732F4
0x1800731f2  mov     rcx, [rdi+78h]
0x1800731f6  mov     edx, [rdi+68h]
0x1800731f9  mov     rax, [rcx]
0x1800731fc  mov     rax, [rax+90h]
0x180073203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073208  mov     ebx, eax
0x18007320a  test    eax, eax
0x18007320c  js      loc_1800732F4
0x180073212  mov     rcx, [rdi+78h]
0x180073216  lea     r9, [rsp+420h+var_3D0]
0x18007321b  mov     [rsp+420h+var_3D0], r13
0x180073220  mov     r8d, r14d
0x180073223  mov     rdx, r12
0x180073226  mov     rax, [rcx]
0x180073229  mov     rax, [rax+68h]
0x18007322d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073232  mov     ebx, eax
0x180073234  test    eax, eax
0x180073236  js      loc_1800732F4
0x18007323c  mov     r8, [rsp+420h+var_3D0]; wchar_t *
0x180073241  lea     rax, [rsp+420h+var_3E0]
0x180073246  mov     rdx, [rsp+420h+var_3E0]; unsigned __int64
0x18007324b  lea     r9, [rsp+420h+pszDest]; wchar_t **
0x180073250  mov     rcx, [rsp+420h+pszDest]; wchar_t *
0x180073255  mov     [rsp+420h+lpString2], rax; unsigned __int64 *
0x18007325a  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18007325f  mov     ebx, eax
0x180073261  test    eax, eax
0x180073263  js      loc_1800732E9
0x180073269  mov     rcx, [rdi+40h]; wchar_t *
0x18007326d  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x180073272  test    eax, eax
0x180073274  jnz     short loc_1800732AB
0x180073276  mov     rdx, [rsp+420h+var_3E0]; unsigned __int64
0x18007327b  lea     rax, aS; " %s"
0x180073282  mov     qword ptr [rsp+420h+var_3F0], rcx
0x180073287  lea     r9, [rsp+420h+var_3E0]; unsigned __int64 *
0x18007328c  mov     rcx, [rsp+420h+pszDest]; pszDest
0x180073291  lea     r8, [rsp+420h+pszDest]; wchar_t **
0x180073296  mov     qword ptr [rsp+420h+cchCount2], rax; wchar_t *
0x18007329b  mov     [rsp+420h+lpString2], r13; unsigned int
0x1800732a0  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x1800732a5  mov     ebx, eax
0x1800732a7  test    eax, eax
0x1800732a9  js      short loc_1800732E9
0x1800732ab  mov     rcx, [rdi+48h]; wchar_t *
0x1800732af  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x1800732b4  test    eax, eax
0x1800732b6  jnz     short loc_1800732E9
0x1800732b8  mov     rdx, [rsp+420h+var_3E0]; unsigned __int64
0x1800732bd  lea     rax, aOrderByS; " ORDER BY %s"
0x1800732c4  mov     qword ptr [rsp+420h+var_3F0], rcx
0x1800732c9  lea     r9, [rsp+420h+var_3E0]; unsigned __int64 *
0x1800732ce  mov     rcx, [rsp+420h+pszDest]; pszDest
0x1800732d3  lea     r8, [rsp+420h+pszDest]; wchar_t **
0x1800732d8  mov     qword ptr [rsp+420h+cchCount2], rax; wchar_t *
0x1800732dd  mov     [rsp+420h+lpString2], r13; unsigned int
0x1800732e2  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x1800732e7  mov     ebx, eax
0x1800732e9  mov     rcx, [rsp+420h+var_3D0]; pv
0x1800732ee  call    cs:__imp_CoTaskMemFree
0x1800732f4  mov     rcx, [rsp+420h+pv]
0x1800732f9  mov     rax, [rcx]
0x1800732fc  mov     rax, [rax+10h]
0x180073300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073305  jmp     short loc_18007331C
0x180073307  mov     rsi, [rsp+420h+var_3D0]
0x18007330c  jmp     short loc_18007331C
0x18007330e  mov     rcx, [rbp+rsi*8+320h+var_378]; pv
0x180073313  dec     rsi
0x180073316  call    cs:__imp_CoTaskMemFree
0x18007331c  test    rsi, rsi
0x18007331f  jnz     short loc_18007330E
0x180073321  mov     eax, ebx
0x180073323  mov     rcx, [rbp+320h+var_50]
0x18007332a  xor     rcx, rsp; StackCookie
0x18007332d  call    __security_check_cookie
0x180073332  add     rsp, 3E8h
0x180073339  pop     r15
0x18007333b  pop     r14
0x18007333d  pop     r13
0x18007333f  pop     r12
0x180073341  pop     rdi
0x180073342  pop     rsi
0x180073343  pop     rbx
0x180073344  pop     rbp
0x180073345  retn
```
