# CNetworkExplorerFolder::_CanonicalCompare(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180004760`
- end: `0x180004ceb`
- name: `?_CanonicalCompare@CNetworkExplorerFolder@@AEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `1419`
- prototype: `int(CNetworkExplorerFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004160`

## callees

- `0x180004760`
- `0x180004cf4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000481f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004900`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a6e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004add`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ba7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004bfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004c4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000481f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004900`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a6e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004add`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ba7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004bfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ccd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004b46`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004cb5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004b46`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004cb5`
- `SHELL32!__imp_ILCloneFirst` at `0x180004950`
- `SHELL32!__imp_ILCloneFirst` at `0x180004950`
- `SHELL32!__imp_ILFree` at `0x1800049ff`
- `SHELL32!__imp_ILFree` at `0x1800049ff`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800047ef`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800048d0`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004aa5`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004bcd`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004c20`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800047ef`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800048d0`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004aa5`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004bcd`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004c20`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004bed`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004c3f`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004bed`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004c3f`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_CanonicalCompare(
        CNetworkExplorerFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  CNetworkExplorerFolder *v7; // r13
  HRESULT v8; // edi
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  CNetworkExplorerFolder *v11; // rcx
  HRESULT FIID; // r14d
  const SERIALIZEDPROPSTORAGE *v13; // r15
  unsigned __int64 v14; // rax
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  CNetworkExplorerFolder *v19; // rcx
  __int64 *v20; // r14
  _WORD *v21; // rsi
  _WORD *v22; // r15
  ITEMIDLIST *v23; // rbx
  __int64 v24; // rax
  BOOL v25; // eax
  unsigned __int64 v26; // rax
  __int64 v27; // r9
  int v28; // eax
  int v29; // r14d
  unsigned __int64 v30; // rax
  __int64 v31; // rdx
  CNetworkExplorerFolder *v32; // rcx
  PCNZWCH lpString1; // [rsp+30h] [rbp-38h] BYREF
  PCNZWCH v34; // [rsp+38h] [rbp-30h] BYREF
  PCNZWCH lpString2; // [rsp+40h] [rbp-28h] BYREF
  PROPVARIANT ppropvar; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+58h] BYREF

  lpString1 = 0;
  v7 = this;
  v8 = -2147024809;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( !a3 )
    goto LABEL_5;
  v9 = *(unsigned __int16 *)a3;
  if ( (unsigned int)v9 < 0x12 )
    goto LABEL_5;
  if ( *(_DWORD *)((char *)a3 + 6) != 999534523 )
    goto LABEL_5;
  v10 = *((unsigned __int16 *)a3 + 5);
  this = (CNetworkExplorerFolder *)(v10 + 18);
  if ( v9 < v10 + 18 )
    goto LABEL_5;
  if ( !(_WORD)v10 )
    goto LABEL_5;
  v13 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18);
  if ( a3 == (const struct _ITEMIDLIST_RELATIVE *)-18LL
    || PSGetPropertyFromPropertyStorage((const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18), v10, &rpkey, &ppropvar) < 0
    || !ppropvar.vt )
  {
    goto LABEL_5;
  }
  if ( ppropvar.iVal != -1 || ppropvar.vt != 11 )
  {
    PropVariantClear(&ppropvar);
LABEL_5:
    FIID = CNetworkExplorerFolder::_GetFIID(this, a3, (unsigned __int16 **)&lpString1);
    goto LABEL_15;
  }
  PropVariantClear(&ppropvar);
  lpString1 = 0;
  v14 = *(unsigned __int16 *)a3;
  FIID = -2147024809;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( (unsigned int)v14 >= 0x12 && *(_DWORD *)((char *)a3 + 6) == 999534523 )
  {
    v15 = *((unsigned __int16 *)a3 + 5);
    if ( v14 >= v15 + 18 )
    {
      if ( (_WORD)v15 )
      {
        FIID = PSGetPropertyFromPropertyStorage(v13, v15, &PKEY_ItemNameDisplay, &ppropvar);
        if ( FIID >= 0 )
        {
          if ( ppropvar.vt )
          {
            FIID = PropVariantToStringAlloc(&ppropvar, (PWSTR *)&lpString1);
            PropVariantClear(&ppropvar);
          }
          else
          {
            FIID = -2147023288;
          }
        }
      }
    }
  }
LABEL_15:
  if ( FIID < 0 )
    return (unsigned int)FIID;
  pv = 0;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( !a4 )
    goto LABEL_20;
  v16 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v16 < 0x12 )
    goto LABEL_20;
  if ( *(_DWORD *)((char *)a4 + 6) != 999534523 )
    goto LABEL_20;
  v17 = *((unsigned __int16 *)a4 + 5);
  v11 = (CNetworkExplorerFolder *)(v17 + 18);
  if ( v16 < v17 + 18
    || !(_WORD)v17
    || a4 == (const struct _ITEMIDLIST_RELATIVE *)-18LL
    || PSGetPropertyFromPropertyStorage((const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + 18), v17, &rpkey, &ppropvar) < 0
    || !ppropvar.vt )
  {
    goto LABEL_20;
  }
  if ( ppropvar.iVal != -1 || ppropvar.vt != 11 )
  {
    PropVariantClear(&ppropvar);
LABEL_20:
    v8 = CNetworkExplorerFolder::_GetFIID(v11, a4, (unsigned __int16 **)&pv);
    goto LABEL_62;
  }
  PropVariantClear(&ppropvar);
  pv = 0;
  v26 = *(unsigned __int16 *)a4;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( (unsigned int)v26 >= 0x12 && *(_DWORD *)((char *)a4 + 6) == 999534523 )
  {
    v27 = *((unsigned __int16 *)a4 + 5);
    if ( v26 >= v27 + 18 )
    {
      if ( (_WORD)v27 )
      {
        v8 = PSGetPropertyFromPropertyStorage(
               (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + 18),
               v27,
               &PKEY_ItemNameDisplay,
               &ppropvar);
        if ( v8 >= 0 )
        {
          if ( ppropvar.vt )
          {
            v8 = PropVariantToStringAlloc(&ppropvar, (PWSTR *)&pv);
            PropVariantClear(&ppropvar);
          }
          else
          {
            v8 = -2147023288;
          }
        }
      }
    }
  }
LABEL_62:
  if ( v8 < 0 )
    goto LABEL_42;
  v8 = 1;
  v28 = CompareStringW(0x7Fu, 1u, lpString1, -1, (PCNZWCH)pv, -1);
  v29 = v28 - 2;
  if ( v28 != 2 )
    goto LABEL_69;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( !a3
    || (v30 = *(unsigned __int16 *)a3, (unsigned int)v30 < 0x12)
    || *(_DWORD *)((char *)a3 + 6) != 999534523
    || (v31 = *((unsigned __int16 *)a3 + 5), v30 < v31 + 18)
    || !(_WORD)v31
    || a3 == (const struct _ITEMIDLIST_RELATIVE *)-18LL
    || PSGetPropertyFromPropertyStorage((const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18), v31, &rpkey, &ppropvar) < 0
    || !ppropvar.vt )
  {
LABEL_29:
    v20 = (__int64 *)((char *)v7 + 32);
    if ( !v7 )
      v20 = 0;
    v21 = (_WORD *)((char *)a4 + *(unsigned __int16 *)a4);
    v22 = (_WORD *)((char *)a3 + *(unsigned __int16 *)a3);
    if ( v22 && *v22 )
    {
      if ( v21 && *v21 )
      {
        v23 = ILCloneFirst((LPCITEMIDLIST)a3);
        if ( v23 )
        {
          v24 = *v20;
          v34 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64 *, ITEMIDLIST *, _QWORD, GUID *, PCNZWCH *))(v24 + 40))(
                 v20,
                 v23,
                 0,
                 &GUID_000214e6_0000_0000_c000_000000000046,
                 &v34);
          if ( v8 >= 0 )
          {
            lpString2 = 0;
            if ( (**(int (__fastcall ***)(PCNZWCH, GUID *, PCNZWCH *))v34)(
                   v34,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   &lpString2) < 0 )
              a2 = 0;
            else
              (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)lpString2 + 16LL))(lpString2);
            v8 = (*(__int64 (__fastcall **)(PCNZWCH, unsigned __int64, _WORD *, _WORD *))(*(_QWORD *)v34 + 56LL))(
                   v34,
                   a2 & 0xFFFFFFFFFFFF0000uLL,
                   v22,
                   v21);
            (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)v34 + 16LL))(v34);
          }
          ILFree(v23);
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
    else
    {
      v25 = !v21 || !*v21;
      v8 = 0;
      if ( !v25 )
        v8 = 0xFFFF;
    }
    goto LABEL_41;
  }
  if ( ppropvar.iVal != -1 || ppropvar.vt != 11 )
  {
    PropVariantClear(&ppropvar);
    goto LABEL_29;
  }
  PropVariantClear(&ppropvar);
  if ( (a2 & 0x80000000) == 0 )
    goto LABEL_29;
  v34 = 0;
  lpString2 = 0;
  if ( CNetworkExplorerFolder::_GetFIID(v19, a3, (unsigned __int16 **)&v34) >= 0
    && CNetworkExplorerFolder::_GetFIID(v32, a4, (unsigned __int16 **)&lpString2) >= 0 )
  {
    v29 = CompareStringW(0x7Fu, 1u, v34, -1, lpString2, -1) - 2;
  }
  CoTaskMemFree((LPVOID)v34);
  CoTaskMemFree((LPVOID)lpString2);
  if ( !v29 )
    goto LABEL_29;
LABEL_69:
  v8 = (unsigned __int16)v29;
LABEL_41:
  CoTaskMemFree(pv);
LABEL_42:
  CoTaskMemFree((LPVOID)lpString1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004760  push    rbp
0x180004762  push    rbx
0x180004763  push    rsi
0x180004764  push    rdi
0x180004765  push    r12
0x180004767  push    r13
0x180004769  push    r14
0x18000476b  push    r15
0x18000476d  mov     rbp, rsp
0x180004770  sub     rsp, 68h
0x180004774  xor     r14d, r14d
0x180004777  xor     eax, eax
0x180004779  mov     [rbp+lpString1], r14
0x18000477d  xorps   xmm0, xmm0
0x180004780  mov     qword ptr [rbp+ppropvar+10h], rax
0x180004784  mov     rsi, r9
0x180004787  mov     rbx, r8
0x18000478a  mov     r12, rdx
0x18000478d  mov     r13, rcx
0x180004790  mov     edi, 80070057h
0x180004795  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180004799  test    r8, r8
0x18000479c  jz      short loc_1800047BF
0x18000479e  movzx   eax, word ptr [r8]
0x1800047a2  cmp     eax, 12h
0x1800047a5  jb      short loc_1800047BF
0x1800047a7  cmp     dword ptr [r8+6], 3B93AFBBh
0x1800047af  jnz     short loc_1800047BF
0x1800047b1  movzx   edx, word ptr [r8+0Ah]; cb
0x1800047b6  lea     rcx, [rdx+12h]; this
0x1800047ba  cmp     rax, rcx
0x1800047bd  jnb     short loc_1800047D3
0x1800047bf  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x1800047c3  mov     rdx, rbx; struct _ITEMIDLIST_RELATIVE *
0x1800047c6  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x1800047cb  mov     r14d, eax
0x1800047ce  jmp     loc_18000485C
0x1800047d3  test    dx, dx
0x1800047d6  jz      short loc_1800047BF
0x1800047d8  lea     r15, [r8+12h]
0x1800047dc  test    r15, r15
0x1800047df  jz      short loc_1800047BF
0x1800047e1  lea     r9, [rbp+ppropvar]; ppropvar
0x1800047e5  mov     rcx, r15; psps
0x1800047e8  lea     r8, rpkey; rpkey
0x1800047ef  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x1800047f5  test    eax, eax
0x1800047f7  js      short loc_1800047BF
0x1800047f9  movzx   eax, word ptr [rbp+ppropvar]
0x1800047fd  test    ax, ax
0x180004800  jz      short loc_1800047BF
0x180004802  cmp     word ptr [rbp+ppropvar+8], 0FFFFh
0x180004807  mov     ecx, 0Bh
0x18000480c  jnz     loc_180004A33
0x180004812  cmp     cx, ax
0x180004815  jnz     loc_180004A33
0x18000481b  lea     rcx, [rbp+ppropvar]; pvar
0x18000481f  call    cs:__imp_PropVariantClear
0x180004825  xor     eax, eax
0x180004827  mov     [rbp+lpString1], r14
0x18000482b  mov     qword ptr [rbp+ppropvar+10h], rax
0x18000482f  xorps   xmm0, xmm0
0x180004832  movzx   eax, word ptr [rbx]
0x180004835  mov     r14d, edi
0x180004838  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18000483c  cmp     eax, 12h
0x18000483f  jb      short loc_18000485C
0x180004841  cmp     dword ptr [rbx+6], 3B93AFBBh
0x180004848  jnz     short loc_18000485C
0x18000484a  movzx   r8d, word ptr [rbx+0Ah]
0x18000484f  lea     rdx, [r8+12h]
0x180004853  cmp     rax, rdx
0x180004856  jnb     loc_180004BB2
0x18000485c  test    r14d, r14d
0x18000485f  js      short loc_1800048AF
0x180004861  xor     r15d, r15d
0x180004864  xor     eax, eax
0x180004866  mov     [rbp+pv], r15
0x18000486a  xorps   xmm0, xmm0
0x18000486d  mov     qword ptr [rbp+ppropvar+10h], rax
0x180004871  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180004875  test    rsi, rsi
0x180004878  jz      short loc_18000489C
0x18000487a  movzx   eax, word ptr [rsi]
0x18000487d  cmp     eax, 12h
0x180004880  jb      short loc_18000489C
0x180004882  cmp     dword ptr [rsi+6], 3B93AFBBh
0x180004889  jnz     short loc_18000489C
0x18000488b  movzx   edx, word ptr [rsi+0Ah]; cb
0x18000488f  lea     rcx, [rdx+12h]; this
0x180004893  cmp     rax, rcx
0x180004896  jnb     loc_180004A81
0x18000489c  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800048a0  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800048a3  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x1800048a8  mov     edi, eax
0x1800048aa  jmp     loc_180004B17
0x1800048af  mov     eax, r14d
0x1800048b2  jmp     loc_180004A1B
0x1800048b7  test    dx, dx
0x1800048ba  jz      short loc_180004911
0x1800048bc  lea     rcx, [rbx+12h]; psps
0x1800048c0  test    rcx, rcx
0x1800048c3  jz      short loc_180004911
0x1800048c5  lea     r9, [rbp+ppropvar]; ppropvar
0x1800048c9  lea     r8, rpkey; rpkey
0x1800048d0  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x1800048d6  test    eax, eax
0x1800048d8  js      short loc_180004911
0x1800048da  movzx   eax, word ptr [rbp+ppropvar]
0x1800048de  test    ax, ax
0x1800048e1  jz      short loc_180004911
0x1800048e3  cmp     word ptr [rbp+ppropvar+8], 0FFFFh
0x1800048e8  mov     ecx, 0Bh
0x1800048ed  jnz     loc_180004A6A
0x1800048f3  cmp     cx, ax
0x1800048f6  jnz     loc_180004A6A
0x1800048fc  lea     rcx, [rbp+ppropvar]; pvar
0x180004900  call    cs:__imp_PropVariantClear
0x180004906  bt      r12, 1Fh
0x18000490b  jb      loc_180004C6B
0x180004911  movzx   eax, word ptr [rsi]
0x180004914  lea     r14, [r13+20h]
0x180004918  test    r13, r13
0x18000491b  cmovz   r14, r15
0x18000491f  movzx   r15d, word ptr [rbx]
0x180004923  add     rsi, rax
0x180004926  add     r15, rbx
0x180004929  jz      loc_180004A42
0x18000492f  cmp     word ptr [r15], 0
0x180004934  jz      loc_180004A42
0x18000493a  test    rsi, rsi
0x18000493d  jz      loc_180004A05
0x180004943  cmp     word ptr [rsi], 0
0x180004947  jz      loc_180004A05
0x18000494d  mov     rcx, rbx; pidl
0x180004950  call    cs:__imp_ILCloneFirst
0x180004956  mov     rbx, rax
0x180004959  test    rax, rax
0x18000495c  jz      loc_180004A2C
0x180004962  mov     rax, [r14]
0x180004965  lea     rcx, [rbp+var_30]
0x180004969  mov     [rsp+68h+lpString2], rcx
0x18000496e  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180004975  xor     r13d, r13d
0x180004978  xor     r8d, r8d
0x18000497b  mov     rdx, rbx
0x18000497e  mov     [rbp+var_30], r13
0x180004982  mov     rax, [rax+28h]
0x180004986  mov     rcx, r14
0x180004989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000498e  mov     edi, eax
0x180004990  test    eax, eax
0x180004992  js      short loc_1800049FC
0x180004994  mov     rcx, [rbp+var_30]
0x180004998  lea     r8, [rbp+var_28]
0x18000499c  mov     [rbp+var_28], r13
0x1800049a0  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x1800049a7  mov     rax, [rcx]
0x1800049aa  mov     rax, [rax]
0x1800049ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b2  test    eax, eax
0x1800049b4  js      loc_180004A79
0x1800049ba  mov     rcx, [rbp+var_28]
0x1800049be  mov     rax, [rcx]
0x1800049c1  mov     rax, [rax+10h]
0x1800049c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ca  mov     rcx, [rbp+var_30]
0x1800049ce  and     r12, 0FFFFFFFFFFFF0000h
0x1800049d5  mov     r9, rsi
0x1800049d8  mov     r8, r15
0x1800049db  mov     rdx, r12
0x1800049de  mov     rax, [rcx]
0x1800049e1  mov     rax, [rax+38h]
0x1800049e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ea  mov     rcx, [rbp+var_30]
0x1800049ee  mov     edi, eax
0x1800049f0  mov     rax, [rcx]
0x1800049f3  mov     rax, [rax+10h]
0x1800049f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fc  mov     rcx, rbx; pidl
0x1800049ff  call    cs:__imp_ILFree
0x180004a05  mov     rcx, [rbp+pv]; pv
0x180004a09  call    cs:__imp_CoTaskMemFree
0x180004a0f  mov     rcx, [rbp+lpString1]; pv
0x180004a13  call    cs:__imp_CoTaskMemFree
0x180004a19  mov     eax, edi
0x180004a1b  add     rsp, 68h
0x180004a1f  pop     r15
0x180004a21  pop     r14
0x180004a23  pop     r13
0x180004a25  pop     r12
0x180004a27  pop     rdi
0x180004a28  pop     rsi
0x180004a29  pop     rbx
0x180004a2a  pop     rbp
0x180004a2b  retn
0x180004a2c  mov     edi, 8007000Eh
0x180004a31  jmp     short loc_180004A05
0x180004a33  lea     rcx, [rbp+ppropvar]; pvar
0x180004a37  call    cs:__imp_PropVariantClear
0x180004a3d  jmp     loc_1800047BF
0x180004a42  test    rsi, rsi
0x180004a45  jz      loc_180004CE1
0x180004a4b  cmp     word ptr [rsi], 0
0x180004a4f  jz      loc_180004CE1
0x180004a55  xor     r13d, r13d
0x180004a58  mov     eax, r13d
0x180004a5b  test    eax, eax
0x180004a5d  mov     edi, r13d
0x180004a60  mov     ecx, 0FFFFh
0x180004a65  cmovz   edi, ecx
0x180004a68  jmp     short loc_180004A05
0x180004a6a  lea     rcx, [rbp+ppropvar]; pvar
0x180004a6e  call    cs:__imp_PropVariantClear
0x180004a74  jmp     loc_180004911
0x180004a79  mov     r12, r13
0x180004a7c  jmp     loc_1800049CA
0x180004a81  test    dx, dx
0x180004a84  jz      loc_18000489C
0x180004a8a  lea     r14, [rsi+12h]
0x180004a8e  test    r14, r14
0x180004a91  jz      loc_18000489C
0x180004a97  lea     r9, [rbp+ppropvar]; ppropvar
0x180004a9b  mov     rcx, r14; psps
0x180004a9e  lea     r8, rpkey; rpkey
0x180004aa5  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004aab  test    eax, eax
0x180004aad  js      loc_18000489C
0x180004ab3  movzx   eax, word ptr [rbp+ppropvar]
0x180004ab7  test    ax, ax
0x180004aba  jz      loc_18000489C
0x180004ac0  cmp     word ptr [rbp+ppropvar+8], 0FFFFh
0x180004ac5  mov     ecx, 0Bh
0x180004aca  jnz     loc_180004BA3
0x180004ad0  cmp     cx, ax
0x180004ad3  jnz     loc_180004BA3
0x180004ad9  lea     rcx, [rbp+ppropvar]; pvar
0x180004add  call    cs:__imp_PropVariantClear
0x180004ae3  xor     eax, eax
0x180004ae5  mov     [rbp+pv], r15
0x180004ae9  mov     qword ptr [rbp+ppropvar+10h], rax
0x180004aed  xorps   xmm0, xmm0
0x180004af0  movzx   eax, word ptr [rsi]
0x180004af3  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180004af7  cmp     eax, 12h
0x180004afa  jb      short loc_180004B17
0x180004afc  cmp     dword ptr [rsi+6], 3B93AFBBh
0x180004b03  jnz     short loc_180004B17
0x180004b05  movzx   r9d, word ptr [rsi+0Ah]
0x180004b0a  lea     rdx, [r9+12h]
0x180004b0e  cmp     rax, rdx
0x180004b11  jnb     loc_180004C05
0x180004b17  test    edi, edi
0x180004b19  js      loc_180004A0F
0x180004b1f  mov     rax, [rbp+pv]
0x180004b23  mov     edi, 1
0x180004b28  mov     r8, [rbp+lpString1]; lpString1
0x180004b2c  mov     edx, edi; dwCmpFlags
0x180004b2e  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180004b36  mov     r9d, 0FFFFFFFFh; cchCount1
0x180004b3c  mov     ecx, 7Fh; Locale
0x180004b41  mov     [rsp+68h+lpString2], rax; lpString2
0x180004b46  call    cs:__imp_CompareStringW
0x180004b4c  lea     r14d, [rax-2]
0x180004b50  test    r14d, r14d
0x180004b53  jnz     short loc_180004B9A
0x180004b55  xor     eax, eax
0x180004b57  xorps   xmm0, xmm0
0x180004b5a  mov     qword ptr [rbp+ppropvar+10h], rax
0x180004b5e  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180004b62  test    rbx, rbx
0x180004b65  jz      loc_180004911
0x180004b6b  movzx   eax, word ptr [rbx]
0x180004b6e  cmp     eax, 12h
0x180004b71  jb      loc_180004911
0x180004b77  cmp     dword ptr [rbx+6], 3B93AFBBh
0x180004b7e  jnz     loc_180004911
0x180004b84  movzx   edx, word ptr [rbx+0Ah]; cb
0x180004b88  lea     rcx, [rdx+12h]
0x180004b8c  cmp     rax, rcx
0x180004b8f  jb      loc_180004911
0x180004b95  jmp     loc_1800048B7
0x180004b9a  movzx   edi, r14w
0x180004b9e  jmp     loc_180004A05
0x180004ba3  lea     rcx, [rbp+ppropvar]; pvar
0x180004ba7  call    cs:__imp_PropVariantClear
0x180004bad  jmp     loc_18000489C
0x180004bb2  test    r8w, r8w
0x180004bb6  jz      loc_18000485C
0x180004bbc  mov     edx, r8d; cb
0x180004bbf  lea     r9, [rbp+ppropvar]; ppropvar
0x180004bc3  lea     r8, PKEY_ItemNameDisplay; rpkey
0x180004bca  mov     rcx, r15; psps
0x180004bcd  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004bd3  mov     r14d, eax
0x180004bd6  test    eax, eax
0x180004bd8  js      loc_18000485C
0x180004bde  cmp     word ptr [rbp+ppropvar], 0
0x180004be3  jz      short loc_180004C56
  ... truncated ...
```
