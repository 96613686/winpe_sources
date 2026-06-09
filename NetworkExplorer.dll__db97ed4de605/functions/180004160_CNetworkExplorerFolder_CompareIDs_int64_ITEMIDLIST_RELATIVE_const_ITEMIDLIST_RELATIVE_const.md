# CNetworkExplorerFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180004160`
- end: `0x180004757`
- name: `?CompareIDs@CNetworkExplorerFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `1527`
- prototype: `int(CNetworkExplorerFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004160`
- `0x180004760`
- `0x180004cf4`
- `0x180004db4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000427a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800043e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004453`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800044eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004542`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000460c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000465f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800046b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000427a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800043e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004453`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800044eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004542`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000460c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000465f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800046b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000438b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000438b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004732`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800045ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000471a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800045ab`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000471a`
- `SHELL32!__imp_ILCloneFirst` at `0x1800042ca`
- `SHELL32!__imp_ILCloneFirst` at `0x1800042ca`
- `SHELL32!__imp_ILFree` at `0x180004377`
- `SHELL32!__imp_ILFree` at `0x180004377`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000424a`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000441b`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004512`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004632`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004685`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000424a`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000441b`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004512`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004632`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004685`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004652`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800046a4`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004652`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800046a4`

## pseudocode

```c
int __fastcall CNetworkExplorerFolder::CompareIDs(
        CNetworkExplorerFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  __int64 v6; // r13
  CNetworkExplorerFolder *v7; // r12
  HRESULT FIID; // edi
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  CNetworkExplorerFolder *v11; // rcx
  HRESULT v12; // r14d
  int v13; // edi
  CNetworkExplorerFolder *v14; // rcx
  int result; // eax
  CNetworkExplorerFolder *v16; // rcx
  _WORD *v17; // rsi
  _WORD *v18; // r14
  ITEMIDLIST *v19; // rbx
  __int64 v20; // rax
  BOOL v21; // eax
  const SERIALIZEDPROPSTORAGE *v22; // r15
  unsigned __int64 v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  unsigned __int64 v27; // rax
  __int64 v28; // r9
  int v29; // eax
  int v30; // r14d
  unsigned __int64 v31; // rax
  __int64 v32; // rdx
  CNetworkExplorerFolder *v33; // rcx
  PCNZWCH lpString1; // [rsp+30h] [rbp-30h] BYREF
  PCNZWCH v35; // [rsp+38h] [rbp-28h] BYREF
  PCNZWCH lpString2; // [rsp+40h] [rbp-20h] BYREF
  PROPVARIANT ppropvar; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+38h] BYREF

  v6 = a2;
  v7 = this;
  if ( (a2 & 0x10000000) != 0 )
  {
    lpString1 = 0;
    FIID = -2147024809;
    memset(&ppropvar, 0, sizeof(ppropvar));
    if ( a3 )
    {
      v9 = *(unsigned __int16 *)a3;
      if ( (unsigned int)v9 >= 0x12 && *(_DWORD *)((char *)a3 + 6) == 999534523 )
      {
        v10 = *((unsigned __int16 *)a3 + 5);
        this = (CNetworkExplorerFolder *)(v10 + 18);
        if ( v9 >= v10 + 18 )
        {
          if ( (_WORD)v10 )
          {
            v22 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18);
            if ( a3 != (const struct _ITEMIDLIST_RELATIVE *)-18LL
              && PSGetPropertyFromPropertyStorage(
                   (const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18),
                   v10,
                   &rpkey,
                   &ppropvar) >= 0
              && ppropvar.vt )
            {
              if ( ppropvar.iVal == -1 && ppropvar.vt == 11 )
              {
                PropVariantClear(&ppropvar);
                lpString1 = 0;
                v23 = *(unsigned __int16 *)a3;
                v12 = -2147024809;
                memset(&ppropvar, 0, sizeof(ppropvar));
                if ( (unsigned int)v23 >= 0x12 && *(_DWORD *)((char *)a3 + 6) == 999534523 )
                {
                  v24 = *((unsigned __int16 *)a3 + 5);
                  if ( v23 >= v24 + 18 )
                  {
                    if ( (_WORD)v24 )
                    {
                      v12 = PSGetPropertyFromPropertyStorage(v22, v24, &PKEY_ItemNameDisplay, &ppropvar);
                      if ( v12 >= 0 )
                      {
                        if ( ppropvar.vt )
                        {
                          v12 = PropVariantToStringAlloc(&ppropvar, (PWSTR *)&lpString1);
                          PropVariantClear(&ppropvar);
                        }
                        else
                        {
                          v12 = -2147023288;
                        }
                      }
                    }
                  }
                }
LABEL_53:
                if ( v12 < 0 )
                  return v12;
                pv = 0;
                memset(&ppropvar, 0, sizeof(ppropvar));
                if ( a4 )
                {
                  v25 = *(unsigned __int16 *)a4;
                  if ( (unsigned int)v25 >= 0x12 && *(_DWORD *)((char *)a4 + 6) == 999534523 )
                  {
                    v26 = *((unsigned __int16 *)a4 + 5);
                    v11 = (CNetworkExplorerFolder *)(v26 + 18);
                    if ( v25 >= v26 + 18
                      && (_WORD)v26
                      && a4 != (const struct _ITEMIDLIST_RELATIVE *)-18LL
                      && PSGetPropertyFromPropertyStorage(
                           (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + 18),
                           v26,
                           &rpkey,
                           &ppropvar) >= 0
                      && ppropvar.vt )
                    {
                      if ( ppropvar.iVal == -1 && ppropvar.vt == 11 )
                      {
                        PropVariantClear(&ppropvar);
                        pv = 0;
                        v27 = *(unsigned __int16 *)a4;
                        memset(&ppropvar, 0, sizeof(ppropvar));
                        if ( (unsigned int)v27 >= 0x12 && *(_DWORD *)((char *)a4 + 6) == 999534523 )
                        {
                          v28 = *((unsigned __int16 *)a4 + 5);
                          if ( v27 >= v28 + 18 )
                          {
                            if ( (_WORD)v28 )
                            {
                              FIID = PSGetPropertyFromPropertyStorage(
                                       (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + 18),
                                       v28,
                                       &PKEY_ItemNameDisplay,
                                       &ppropvar);
                              if ( FIID >= 0 )
                              {
                                if ( ppropvar.vt )
                                {
                                  FIID = PropVariantToStringAlloc(&ppropvar, (PWSTR *)&pv);
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
LABEL_70:
                        if ( FIID < 0 )
                          goto LABEL_32;
                        FIID = 1;
                        v29 = CompareStringW(0x7Fu, 1u, lpString1, -1, (PCNZWCH)pv, -1);
                        v30 = v29 - 2;
                        if ( v29 != 2 )
                          goto LABEL_77;
                        memset(&ppropvar, 0, sizeof(ppropvar));
                        if ( a3 )
                        {
                          v31 = *(unsigned __int16 *)a3;
                          if ( (unsigned int)v31 >= 0x12 && *(_DWORD *)((char *)a3 + 6) == 999534523 )
                          {
                            v32 = *((unsigned __int16 *)a3 + 5);
                            if ( v31 >= v32 + 18
                              && (_WORD)v32
                              && a3 != (const struct _ITEMIDLIST_RELATIVE *)-18LL
                              && PSGetPropertyFromPropertyStorage(
                                   (const struct _ITEMIDLIST_RELATIVE *)((char *)a3 + 18),
                                   v32,
                                   &rpkey,
                                   &ppropvar) >= 0
                              && ppropvar.vt )
                            {
                              if ( ppropvar.iVal == -1 && ppropvar.vt == 11 )
                              {
                                PropVariantClear(&ppropvar);
                                if ( (v6 & 0x80000000) == 0 )
                                  goto LABEL_19;
                                v35 = 0;
                                lpString2 = 0;
                                if ( CNetworkExplorerFolder::_GetFIID(v16, a3, (unsigned __int16 **)&v35) >= 0
                                  && CNetworkExplorerFolder::_GetFIID(v33, a4, (unsigned __int16 **)&lpString2) >= 0 )
                                {
                                  v30 = CompareStringW(0x7Fu, 1u, v35, -1, lpString2, -1) - 2;
                                }
                                CoTaskMemFree((LPVOID)v35);
                                CoTaskMemFree((LPVOID)lpString2);
                                if ( !v30 )
                                  goto LABEL_19;
LABEL_77:
                                FIID = (unsigned __int16)v30;
LABEL_31:
                                CoTaskMemFree(pv);
LABEL_32:
                                CoTaskMemFree((LPVOID)lpString1);
                                return FIID;
                              }
                              PropVariantClear(&ppropvar);
                            }
                          }
                        }
LABEL_19:
                        if ( v7 == (CNetworkExplorerFolder *)32 )
                          v7 = 0;
                        v17 = (_WORD *)((char *)a4 + *(unsigned __int16 *)a4);
                        v18 = (_WORD *)((char *)a3 + *(unsigned __int16 *)a3);
                        if ( v18 && *v18 )
                        {
                          if ( v17 && *v17 )
                          {
                            v19 = ILCloneFirst((LPCITEMIDLIST)a3);
                            if ( v19 )
                            {
                              v20 = *(_QWORD *)v7;
                              v35 = 0;
                              FIID = (*(__int64 (__fastcall **)(CNetworkExplorerFolder *, ITEMIDLIST *, _QWORD, GUID *, PCNZWCH *))(v20 + 40))(
                                       v7,
                                       v19,
                                       0,
                                       &GUID_000214e6_0000_0000_c000_000000000046,
                                       &v35);
                              if ( FIID >= 0 )
                              {
                                lpString2 = 0;
                                if ( (**(int (__fastcall ***)(PCNZWCH, GUID *, PCNZWCH *))v35)(
                                       v35,
                                       &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                                       &lpString2) < 0 )
                                  v6 = 0;
                                else
                                  (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)lpString2 + 16LL))(lpString2);
                                FIID = (*(__int64 (__fastcall **)(PCNZWCH, unsigned __int64, _WORD *, _WORD *))(*(_QWORD *)v35 + 56LL))(
                                         v35,
                                         v6 & 0xFFFFFFFFFFFF0000uLL,
                                         v18,
                                         v17);
                                (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)v35 + 16LL))(v35);
                              }
                              ILFree(v19);
                            }
                            else
                            {
                              FIID = -2147024882;
                            }
                          }
                        }
                        else
                        {
                          v21 = !v17 || !*v17;
                          FIID = 0;
                          if ( !v21 )
                            FIID = 0xFFFF;
                        }
                        goto LABEL_31;
                      }
                      PropVariantClear(&ppropvar);
                    }
                  }
                }
                FIID = CNetworkExplorerFolder::_GetFIID(v11, a4, (unsigned __int16 **)&pv);
                goto LABEL_70;
              }
              PropVariantClear(&ppropvar);
            }
          }
        }
      }
    }
    v12 = CNetworkExplorerFolder::_GetFIID(this, a3, (unsigned __int16 **)&lpString1);
    goto LABEL_53;
  }
  v13 = (unsigned __int16)a2;
  v14 = (CNetworkExplorerFolder *)((char *)this - 32);
  if ( (_WORD)a2 )
    result = CNetworkExplorerFolder::_CanonicalCompare(v14, a2, a3, a4);
  else
    result = CNetworkExplorerFolder::_CompareByName(v14, a3, a4, a2);
  if ( !result && v13 )
    return CNetworkExplorerFolder::_CompareByName((CNetworkExplorerFolder *)((char *)v7 - 32), a3, a4, v6);
  return result;
}

```

## disassembly

```asm
0x180004160  mov     [rsp-28h+arg_10], rbx
0x180004165  mov     [rsp-28h+arg_18], rsi
0x18000416a  push    rbp
0x18000416b  push    rdi
0x18000416c  push    r12
0x18000416e  push    r13
0x180004170  push    r14
0x180004172  mov     rbp, rsp
0x180004175  sub     rsp, 60h
0x180004179  mov     rsi, r9
0x18000417c  mov     rbx, r8
0x18000417f  mov     r13, rdx
0x180004182  mov     r12, rcx
0x180004185  bt      rdx, 1Ch
0x18000418a  jnb     short loc_1800041EB
0x18000418c  xor     r14d, r14d
0x18000418f  mov     [rsp+60h+arg_0], r15
0x180004197  xor     eax, eax
0x180004199  mov     [rbp+lpString1], r14
0x18000419d  mov     qword ptr [rbp+ppropvar+10h], rax
0x1800041a1  xorps   xmm0, xmm0
0x1800041a4  mov     edi, 80070057h
0x1800041a9  movups  xmmword ptr [rbp+ppropvar], xmm0
0x1800041ad  test    rbx, rbx
0x1800041b0  jz      short loc_1800041D7
0x1800041b2  movzx   eax, word ptr [r8]
0x1800041b6  cmp     eax, 12h
0x1800041b9  jb      short loc_1800041D7
0x1800041bb  cmp     dword ptr [r8+6], 3B93AFBBh
0x1800041c3  jnz     short loc_1800041D7
0x1800041c5  movzx   edx, word ptr [r8+0Ah]; cb
0x1800041ca  lea     rcx, [rdx+12h]; this
0x1800041ce  cmp     rax, rcx
0x1800041d1  jnb     loc_1800043F7
0x1800041d7  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x1800041db  mov     rdx, rbx; struct _ITEMIDLIST_RELATIVE *
0x1800041de  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x1800041e3  mov     r14d, eax
0x1800041e6  jmp     loc_180004490
0x1800041eb  movzx   edi, r13w
0x1800041ef  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x1800041f3  test    edi, edi
0x1800041f5  jnz     loc_18000474D
0x1800041fb  mov     r9, r13; __int64
0x1800041fe  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x180004201  mov     rdx, rbx; struct _ITEMIDLIST_RELATIVE *
0x180004204  call    ?_CompareByName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@0_J@Z; CNetworkExplorerFolder::_CompareByName(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)
0x180004209  test    eax, eax
0x18000420b  jnz     loc_18000439B
0x180004211  test    edi, edi
0x180004213  jz      loc_18000439B
0x180004219  mov     r9, r13; __int64
0x18000421c  lea     rcx, [r12-20h]; this
0x180004221  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x180004224  mov     rdx, rbx; struct _ITEMIDLIST_RELATIVE *
0x180004227  call    ?_CompareByName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@0_J@Z; CNetworkExplorerFolder::_CompareByName(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)
0x18000422c  jmp     loc_18000439B
0x180004231  test    dx, dx
0x180004234  jz      short loc_18000428B
0x180004236  lea     rcx, [rbx+12h]; psps
0x18000423a  test    rcx, rcx
0x18000423d  jz      short loc_18000428B
0x18000423f  lea     r9, [rbp+ppropvar]; ppropvar
0x180004243  lea     r8, rpkey; rpkey
0x18000424a  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004250  test    eax, eax
0x180004252  js      short loc_18000428B
0x180004254  movzx   eax, word ptr [rbp+ppropvar]
0x180004258  test    ax, ax
0x18000425b  jz      short loc_18000428B
0x18000425d  cmp     word ptr [rbp+ppropvar+8], 0FFFFh
0x180004262  mov     ecx, 0Bh
0x180004267  jnz     loc_1800043E0
0x18000426d  cmp     cx, ax
0x180004270  jnz     loc_1800043E0
0x180004276  lea     rcx, [rbp+ppropvar]; pvar
0x18000427a  call    cs:__imp_PropVariantClear
0x180004280  bt      r13, 1Fh
0x180004285  jb      loc_1800046D0
0x18000428b  movzx   eax, word ptr [rsi]
0x18000428e  lea     rcx, [r12-20h]
0x180004293  movzx   r14d, word ptr [rbx]
0x180004297  test    rcx, rcx
0x18000429a  cmovz   r12, r15
0x18000429e  add     rsi, rax
0x1800042a1  add     r14, rbx
0x1800042a4  jz      loc_1800043BB
0x1800042aa  cmp     [r14], r15w
0x1800042ae  jz      loc_1800043BB
0x1800042b4  test    rsi, rsi
0x1800042b7  jz      loc_18000437D
0x1800042bd  cmp     [rsi], r15w
0x1800042c1  jz      loc_18000437D
0x1800042c7  mov     rcx, rbx; pidl
0x1800042ca  call    cs:__imp_ILCloneFirst
0x1800042d0  mov     rbx, rax
0x1800042d3  test    rax, rax
0x1800042d6  jz      loc_1800043B4
0x1800042dc  mov     rax, [r12]
0x1800042e0  lea     rcx, [rbp+var_28]
0x1800042e4  mov     [rsp+60h+lpString2], rcx
0x1800042e9  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800042f0  xor     r8d, r8d
0x1800042f3  mov     [rbp+var_28], r15
0x1800042f7  mov     rdx, rbx
0x1800042fa  mov     rcx, r12
0x1800042fd  mov     rax, [rax+28h]
0x180004301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004306  mov     edi, eax
0x180004308  test    eax, eax
0x18000430a  js      short loc_180004374
0x18000430c  mov     rcx, [rbp+var_28]
0x180004310  lea     r8, [rbp+var_20]
0x180004314  mov     [rbp+var_20], r15
0x180004318  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18000431f  mov     rax, [rcx]
0x180004322  mov     rax, [rax]
0x180004325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000432a  test    eax, eax
0x18000432c  js      loc_1800043EF
0x180004332  mov     rcx, [rbp+var_20]
0x180004336  mov     rax, [rcx]
0x180004339  mov     rax, [rax+10h]
0x18000433d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004342  mov     rcx, [rbp+var_28]
0x180004346  and     r13, 0FFFFFFFFFFFF0000h
0x18000434d  mov     r9, rsi
0x180004350  mov     r8, r14
0x180004353  mov     rdx, r13
0x180004356  mov     rax, [rcx]
0x180004359  mov     rax, [rax+38h]
0x18000435d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004362  mov     rcx, [rbp+var_28]
0x180004366  mov     edi, eax
0x180004368  mov     rax, [rcx]
0x18000436b  mov     rax, [rax+10h]
0x18000436f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004374  mov     rcx, rbx; pidl
0x180004377  call    cs:__imp_ILFree
0x18000437d  mov     rcx, [rbp+pv]; pv
0x180004381  call    cs:__imp_CoTaskMemFree
0x180004387  mov     rcx, [rbp+lpString1]; pv
0x18000438b  call    cs:__imp_CoTaskMemFree
0x180004391  mov     r15, [rsp+60h+arg_0]
0x180004399  mov     eax, edi
0x18000439b  lea     r11, [rsp+60h+var_s0]
0x1800043a0  mov     rbx, [r11+40h]
0x1800043a4  mov     rsi, [r11+48h]
0x1800043a8  mov     rsp, r11
0x1800043ab  pop     r14
0x1800043ad  pop     r13
0x1800043af  pop     r12
0x1800043b1  pop     rdi
0x1800043b2  pop     rbp
0x1800043b3  retn
0x1800043b4  mov     edi, 8007000Eh
0x1800043b9  jmp     short loc_18000437D
0x1800043bb  test    rsi, rsi
0x1800043be  jz      loc_180004746
0x1800043c4  cmp     [rsi], r15w
0x1800043c8  jz      loc_180004746
0x1800043ce  mov     eax, r15d
0x1800043d1  test    eax, eax
0x1800043d3  mov     edi, r15d
0x1800043d6  mov     ecx, 0FFFFh
0x1800043db  cmovz   edi, ecx
0x1800043de  jmp     short loc_18000437D
0x1800043e0  lea     rcx, [rbp+ppropvar]; pvar
0x1800043e4  call    cs:__imp_PropVariantClear
0x1800043ea  jmp     loc_18000428B
0x1800043ef  mov     r13, r15
0x1800043f2  jmp     loc_180004342
0x1800043f7  test    dx, dx
0x1800043fa  jz      loc_1800041D7
0x180004400  lea     r15, [r8+12h]
0x180004404  test    r15, r15
0x180004407  jz      loc_1800041D7
0x18000440d  lea     r9, [rbp+ppropvar]; ppropvar
0x180004411  mov     rcx, r15; psps
0x180004414  lea     r8, rpkey; rpkey
0x18000441b  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004421  test    eax, eax
0x180004423  js      loc_1800041D7
0x180004429  movzx   eax, word ptr [rbp+ppropvar]
0x18000442d  test    ax, ax
0x180004430  jz      loc_1800041D7
0x180004436  cmp     word ptr [rbp+ppropvar+8], 0FFFFh
0x18000443b  mov     ecx, 0Bh
0x180004440  jnz     loc_1800044E7
0x180004446  cmp     cx, ax
0x180004449  jnz     loc_1800044E7
0x18000444f  lea     rcx, [rbp+ppropvar]; pvar
0x180004453  call    cs:__imp_PropVariantClear
0x180004459  xor     eax, eax
0x18000445b  mov     [rbp+lpString1], r14
0x18000445f  mov     qword ptr [rbp+ppropvar+10h], rax
0x180004463  xorps   xmm0, xmm0
0x180004466  movzx   eax, word ptr [rbx]
0x180004469  mov     r14d, edi
0x18000446c  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180004470  cmp     eax, 12h
0x180004473  jb      short loc_180004490
0x180004475  cmp     dword ptr [rbx+6], 3B93AFBBh
0x18000447c  jnz     short loc_180004490
0x18000447e  movzx   r8d, word ptr [rbx+0Ah]
0x180004483  lea     rdx, [r8+12h]
0x180004487  cmp     rax, rdx
0x18000448a  jnb     loc_180004617
0x180004490  test    r14d, r14d
0x180004493  js      short loc_1800044DF
0x180004495  xor     r15d, r15d
0x180004498  xor     eax, eax
0x18000449a  mov     [rbp+pv], r15
0x18000449e  xorps   xmm0, xmm0
0x1800044a1  mov     qword ptr [rbp+ppropvar+10h], rax
0x1800044a5  movups  xmmword ptr [rbp+ppropvar], xmm0
0x1800044a9  test    rsi, rsi
0x1800044ac  jz      short loc_1800044CC
0x1800044ae  movzx   eax, word ptr [rsi]
0x1800044b1  cmp     eax, 12h
0x1800044b4  jb      short loc_1800044CC
0x1800044b6  cmp     dword ptr [rsi+6], 3B93AFBBh
0x1800044bd  jnz     short loc_1800044CC
0x1800044bf  movzx   edx, word ptr [rsi+0Ah]; cb
0x1800044c3  lea     rcx, [rdx+12h]; this
0x1800044c7  cmp     rax, rcx
0x1800044ca  jnb     short loc_1800044F6
0x1800044cc  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800044d0  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800044d3  call    ?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x1800044d8  mov     edi, eax
0x1800044da  jmp     loc_18000457C
0x1800044df  mov     edi, r14d
0x1800044e2  jmp     loc_180004391
0x1800044e7  lea     rcx, [rbp+ppropvar]; pvar
0x1800044eb  call    cs:__imp_PropVariantClear
0x1800044f1  jmp     loc_1800041D7
0x1800044f6  test    dx, dx
0x1800044f9  jz      short loc_1800044CC
0x1800044fb  lea     r14, [rsi+12h]
0x1800044ff  test    r14, r14
0x180004502  jz      short loc_1800044CC
0x180004504  lea     r9, [rbp+ppropvar]; ppropvar
0x180004508  mov     rcx, r14; psps
0x18000450b  lea     r8, rpkey; rpkey
0x180004512  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004518  test    eax, eax
0x18000451a  js      short loc_1800044CC
0x18000451c  movzx   eax, word ptr [rbp+ppropvar]
0x180004520  test    ax, ax
0x180004523  jz      short loc_1800044CC
0x180004525  cmp     word ptr [rbp+ppropvar+8], 0FFFFh
0x18000452a  mov     ecx, 0Bh
0x18000452f  jnz     loc_180004608
0x180004535  cmp     cx, ax
0x180004538  jnz     loc_180004608
0x18000453e  lea     rcx, [rbp+ppropvar]; pvar
0x180004542  call    cs:__imp_PropVariantClear
0x180004548  xor     eax, eax
0x18000454a  mov     [rbp+pv], r15
0x18000454e  mov     qword ptr [rbp+ppropvar+10h], rax
0x180004552  xorps   xmm0, xmm0
0x180004555  movzx   eax, word ptr [rsi]
0x180004558  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18000455c  cmp     eax, 12h
0x18000455f  jb      short loc_18000457C
0x180004561  cmp     dword ptr [rsi+6], 3B93AFBBh
0x180004568  jnz     short loc_18000457C
0x18000456a  movzx   r9d, word ptr [rsi+0Ah]
0x18000456f  lea     rdx, [r9+12h]
0x180004573  cmp     rax, rdx
0x180004576  jnb     loc_18000466A
0x18000457c  test    edi, edi
0x18000457e  js      loc_180004387
0x180004584  mov     rax, [rbp+pv]
0x180004588  mov     edi, 1
0x18000458d  mov     r8, [rbp+lpString1]; lpString1
0x180004591  mov     edx, edi; dwCmpFlags
0x180004593  mov     [rsp+60h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000459b  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800045a1  mov     ecx, 7Fh; Locale
0x1800045a6  mov     [rsp+60h+lpString2], rax; lpString2
0x1800045ab  call    cs:__imp_CompareStringW
0x1800045b1  lea     r14d, [rax-2]
0x1800045b5  test    r14d, r14d
0x1800045b8  jnz     short loc_1800045FF
0x1800045ba  xor     eax, eax
0x1800045bc  xorps   xmm0, xmm0
0x1800045bf  mov     qword ptr [rbp+ppropvar+10h], rax
0x1800045c3  movups  xmmword ptr [rbp+ppropvar], xmm0
0x1800045c7  test    rbx, rbx
0x1800045ca  jz      loc_18000428B
0x1800045d0  movzx   eax, word ptr [rbx]
0x1800045d3  cmp     eax, 12h
0x1800045d6  jb      loc_18000428B
0x1800045dc  cmp     dword ptr [rbx+6], 3B93AFBBh
0x1800045e3  jnz     loc_18000428B
0x1800045e9  movzx   edx, word ptr [rbx+0Ah]; cb
0x1800045ed  lea     rcx, [rdx+12h]
0x1800045f1  cmp     rax, rcx
  ... truncated ...
```
