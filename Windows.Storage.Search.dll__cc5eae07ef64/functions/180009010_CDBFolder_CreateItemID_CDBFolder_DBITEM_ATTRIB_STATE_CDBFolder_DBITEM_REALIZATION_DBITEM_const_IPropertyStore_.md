# CDBFolder::_CreateItemID(CDBFolder::DBITEM_ATTRIB_STATE,CDBFolder::DBITEM_REALIZATION,DBITEM const *,IPropertyStore *,_ITEMID_CHILD * *)

- ea: `0x180009010`
- end: `0x18000960a`
- name: `?_CreateItemID@CDBFolder@@AEAAJW4DBITEM_ATTRIB_STATE@1@W4DBITEM_REALIZATION@1@PEFBUDBITEM@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `1530`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000782c`
- `0x18002eb80`
- `0x18005e034`
- `0x180088660`
- `0x18008a460`
- `0x18008cc38`

## callees

- `0x180009010`
- `0x18000a350`
- `0x18000a730`
- `0x18000b650`
- `0x180019b60`
- `0x180072cdc`
- `0x180072cf4`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x180009108`
- `Windows.Storage!ILFindLastID` at `0x18000913f`
- `Windows.Storage!ILFindLastID` at `0x18000926b`
- `Windows.Storage!ILFindLastID` at `0x180009108`
- `Windows.Storage!ILFindLastID` at `0x18000913f`
- `Windows.Storage!ILFindLastID` at `0x18000926b`
- `Windows.Storage!ILFree` at `0x18000918d`
- `Windows.Storage!ILFree` at `0x180009476`
- `Windows.Storage!ILFree` at `0x18000918d`
- `Windows.Storage!ILFree` at `0x180009476`
- `Windows.Storage!SHBindToFolderIDListParentEx` at `0x180009417`
- `Windows.Storage!SHBindToFolderIDListParentEx` at `0x180009417`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009355`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009531`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009355`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009531`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180009343`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180009343`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x1800095fd`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x1800095fd`

## pseudocode

```c
__int64 __fastcall CDBFolder::_CreateItemID(
        __int64 a1,
        int a2,
        int a3,
        _OWORD *a4,
        __int64 (__fastcall ***a5)(_QWORD, GUID *, __int64 *),
        size_t Size)
{
  _QWORD *v6; // r15
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v10; // rsi
  int v11; // eax
  __int64 v12; // r13
  __int16 v13; // si
  void *v14; // rax
  __int64 v15; // rbx
  void *v16; // rax
  LPITEMIDLIST ID; // rax
  unsigned __int64 cb; // rcx
  const struct _ITEMIDLIST_RELATIVE *v19; // rsi
  const struct _HIDDENITEMID *HiddenID; // rdx
  unsigned __int64 v21; // rsi
  int PropertyForItem; // edi
  _DWORD *abID; // r14
  __int64 (__fastcall **v25)(_QWORD, GUID *, __int64 *); // rax
  int *v26; // rsi
  int v27; // eax
  __int64 v28; // r12
  LPITEMIDLIST v29; // rax
  LPITEMIDLIST v30; // r8
  unsigned __int64 v31; // rax
  __int64 v32; // rax
  ITEMIDLIST *v33; // r8
  int v34; // eax
  ULONG v35; // esi
  int v36; // ebx
  __int64 (__fastcall **v37)(_QWORD, GUID *, __int64 *); // rax
  const struct _HIDDENITEMID *v38; // r8
  unsigned __int16 *v39; // rcx
  LONG v40; // esi
  __int64 v41; // [rsp+40h] [rbp-49h] BYREF
  void *Src; // [rsp+48h] [rbp-41h] BYREF
  void *ppv; // [rsp+50h] [rbp-39h] BYREF
  IShellFolder *psfRoot; // [rsp+58h] [rbp-31h] BYREF
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp-29h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+68h] [rbp-21h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v48; // [rsp+80h] [rbp-9h]
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v50; // [rsp+98h] [rbp+Fh]
  __int64 v51; // [rsp+E0h] [rbp+57h] BYREF
  int v52; // [rsp+E8h] [rbp+5Fh]

  v52 = a2;
  v51 = a1;
  v6 = (_QWORD *)Size;
  v7 = a5;
  Src = 0;
  LODWORD(Size) = 0;
  *v6 = 0;
  v10 = *(_QWORD *)(a1 + 208);
  v11 = 0;
  if ( v7 )
  {
    v37 = *v7;
    a5 = 0;
    v36 = (*v37)(v7, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, (__int64 *)&a5);
    if ( v36 < 0 )
      return (unsigned int)v36;
    v36 = (*a5)[5](a5, (GUID *)&Src, (__int64 *)&Size);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a5)[2])(a5);
    if ( v36 < 0 )
      return (unsigned int)v36;
    v11 = Size;
  }
  v12 = (unsigned int)(v11 + 40) + 2LL;
  if ( v10 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, (unsigned int)(v11 + 40) + 2LL);
LABEL_59:
    if ( v15 )
    {
LABEL_6:
      *(_DWORD *)(v15 + 6) = 269752705;
      *(_WORD *)(v15 + 10) = Size;
      *(_WORD *)(v15 + 12) = 32;
      if ( a4 )
      {
        *(_OWORD *)(v15 + 14) = *a4;
        *(_OWORD *)(v15 + 30) = a4[1];
      }
      v16 = Src;
      if ( Src )
      {
        memcpy_0((void *)(v15 + 46), Src, (unsigned int)Size);
        v16 = Src;
      }
      CoTaskMemFree(v16);
      ID = ILFindLastID((LPCITEMIDLIST)v15);
      if ( !ID
        || (cb = ID->mkid.cb, (unsigned int)cb < 0x2E)
        || *(_DWORD *)&ID[2].mkid.cb != 269752705
        || cb < (unsigned __int64)*(unsigned __int16 *)((char *)&ID[3].mkid.cb + 1) + 46
        || (abID = ID[4].mkid.abID, ID == (LPITEMIDLIST)-14LL) )
      {
        if ( !v15
          || !*(_WORD *)v15
          || (v19 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID((LPCITEMIDLIST)v15),
              HiddenID = ILFindFirstHiddenID(v19),
              v21 = (unsigned __int64)v19 + *(unsigned __int16 *)v19,
              !HiddenID) )
        {
LABEL_17:
          PropertyForItem = -2147024809;
          goto LABEL_22;
        }
        while ( 1 )
        {
          abID = (_DWORD *)((char *)HiddenID + 8);
          if ( *((_DWORD *)HiddenID + 1) == -1091633133 )
            break;
          v38 = 0;
          if ( (unsigned __int64)abID <= v21 )
          {
            v39 = (unsigned __int16 *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
            if ( v39 == (unsigned __int16 *)v21 )
              goto LABEL_17;
            if ( (unsigned __int64)v39 <= v21 )
            {
              if ( (unsigned __int64)(v39 + 4) > v21
                || HIWORD(*((_DWORD *)v39 + 1)) != 0xBEEF
                || (unsigned __int64)v39 + *v39 > v21
                || v39 < (unsigned __int16 *)abID )
              {
                goto LABEL_17;
              }
              v38 = (const struct _HIDDENITEMID *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
            }
          }
          HiddenID = v38;
          if ( !v38 )
            goto LABEL_17;
        }
      }
      v25 = *v7;
      v41 = 0;
      PropertyForItem = (*v25)(v7, &GUID_3017056d_9a91_4e90_937d_746c72abbf4f, &v41);
      if ( PropertyForItem >= 0 )
      {
        LODWORD(a5) = 0;
        if ( a3 == 1
          || (v34 = abID[7], v26 = abID + 7, (v34 & 4) != 0)
          || (v34 & 2) != 0
          || (v34 & 0x10) != 0
          || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, _QWORD *))(*(_QWORD *)v41 + 64LL))(
               v41,
               &PKEY_ParsingPath,
               &a5) >= 0
          && !(_DWORD)a5
          || (*(int (__fastcall **)(__int64, const struct _tagpropertykey *, _QWORD *))(*(_QWORD *)v41 + 64LL))(
               v41,
               &PKEY_ResultSourceId,
               &a5) >= 0
          && !(_DWORD)a5 )
        {
          abID[7] |= 0x100u;
          v26 = abID + 7;
        }
        if ( v52 != 2 )
          goto LABEL_20;
        v27 = *v26;
        if ( (*v26 & 4) != 0 || (v27 & 2) != 0 || (v27 & 0x10) != 0 )
        {
          *abID = 0x20000000;
          goto LABEL_20;
        }
        v48 = 0;
        v28 = v51 + 184;
        *(_OWORD *)propvarIn = 0;
        PropertyForItem = CDBFolder::GetPropertyForItem(v51 + 184, v15, &PKEY_SFGAOFlags, 0, propvarIn);
        if ( PropertyForItem >= 0 && LOWORD(propvarIn[0]) != 1 )
        {
          v35 = PropVariantToUInt32WithDefault(propvarIn, 0) & 0x646BA000;
          PropVariantClear(propvarIn);
LABEL_19:
          *abID = v35;
          goto LABEL_20;
        }
        v29 = ILFindLastID((LPCITEMIDLIST)v15);
        v30 = v29;
        if ( v29
          && (v31 = v29->mkid.cb, (unsigned int)v31 >= 0x2E)
          && *(_DWORD *)&v30[2].mkid.cb == 269752705
          && v31 >= (unsigned __int64)*(unsigned __int16 *)((char *)&v30[3].mkid.cb + 1) + 46
          && v30 != (LPITEMIDLIST)-14LL )
        {
          v33 = v30 + 14;
        }
        else
        {
          v32 = ILFindHiddenIDOn(v15, 3203334163LL);
          if ( !v32 )
            goto LABEL_49;
          v33 = (ITEMIDLIST *)(v32 + 36);
        }
        if ( (v33->mkid.cb & 1) != 0 )
        {
LABEL_67:
          v35 = 0;
          if ( PropertyForItem < 0 )
          {
            v35 = -1;
            PropertyForItem = 0;
          }
          goto LABEL_19;
        }
LABEL_49:
        v50 = 0;
        *(_OWORD *)pvar = 0;
        if ( (int)CDBFolder::GetPropertyForItem(v28, v15, PKEY_DelegationFlags, 0, pvar) >= 0 )
        {
          v40 = -1;
          if ( LOWORD(pvar[0]) != 1 )
            v40 = PropVariantToInt32WithDefault(pvar, -1);
          PropVariantClear(pvar);
          if ( v40 != -1 )
            goto LABEL_67;
        }
        psfRoot = 0;
        pidl = 0;
        v35 = 0;
        PropertyForItem = CDBFolder::DelegateBindToParent(
                            v28,
                            v15,
                            1,
                            0xFFFFFFFFLL,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            &psfRoot,
                            &pidl);
        if ( PropertyForItem >= 0 )
        {
          ppidlLast = 0;
          ppv = 0;
          if ( SHBindToFolderIDListParentEx(
                 psfRoot,
                 pidl,
                 0,
                 &GUID_000214e6_0000_0000_c000_000000000046,
                 &ppv,
                 &ppidlLast) >= 0 )
          {
            LODWORD(v51) = 1684774912;
            if ( (*(int (__fastcall **)(void *, __int64, LPCITEMIDLIST *, __int64 *))(*(_QWORD *)ppv + 72LL))(
                   ppv,
                   1,
                   &ppidlLast,
                   &v51) >= 0 )
              v35 = v51 & 0x646BA000;
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          ((void (__fastcall *)(IShellFolder *))psfRoot->lpVtbl->Release)(psfRoot);
          ILFree((LPITEMIDLIST)pidl);
          goto LABEL_19;
        }
LABEL_20:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        if ( PropertyForItem >= 0 )
        {
          *v6 = v15;
          v15 = 0;
        }
      }
LABEL_22:
      ILFree((LPITEMIDLIST)v15);
      return (unsigned int)PropertyForItem;
    }
    goto LABEL_60;
  }
  v13 = v11 + 50;
  if ( (unsigned __int64)(unsigned int)(v11 + 40) + 10 <= 0x10001 )
  {
    v14 = CoTaskMemAlloc((unsigned int)(v11 + 40) + 10LL);
    v15 = (__int64)v14;
    if ( v14 )
    {
      memset_0(v14, 0, v12 + 8);
      *(_WORD *)(v15 + 4) = v12;
      *(_WORD *)v15 = v13 - 2;
      goto LABEL_6;
    }
    goto LABEL_59;
  }
LABEL_60:
  v36 = -2147024882;
  CoTaskMemFree(Src);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x180009010  mov     [rsp-8+arg_10], rbx
0x180009015  mov     [rsp-8+arg_8], edx
0x180009019  mov     [rsp-8+arg_0], rcx
0x18000901e  push    rbp
0x18000901f  push    rsi
0x180009020  push    rdi
0x180009021  push    r12
0x180009023  push    r13
0x180009025  push    r14
0x180009027  push    r15
0x180009029  lea     rbp, [rsp-17h]
0x18000902e  sub     rsp, 0A0h
0x180009035  mov     r15, [rbp+47h+Size]
0x180009039  mov     rax, rcx
0x18000903c  mov     rdi, [rbp+47h+arg_20]
0x180009040  xor     ecx, ecx
0x180009042  mov     [rbp+47h+Src], rcx
0x180009046  mov     r14, r9
0x180009049  mov     dword ptr [rbp+47h+Size], ecx
0x18000904c  mov     r12d, r8d
0x18000904f  mov     [r15], rcx
0x180009052  mov     rsi, [rax+0D0h]
0x180009059  mov     eax, ecx
0x18000905b  test    rdi, rdi
0x18000905e  jnz     loc_1800094BF
0x180009064  lea     r13d, [rax+28h]
0x180009068  add     r13, 2
0x18000906c  test    rsi, rsi
0x18000906f  jnz     loc_180009490
0x180009075  lea     rsi, [r13+8]
0x180009079  cmp     rsi, 10001h
0x180009080  ja      loc_1800094AE
0x180009086  mov     rcx, rsi; cb
0x180009089  call    cs:__imp_CoTaskMemAlloc
0x18000908f  mov     rbx, rax
0x180009092  test    rax, rax
0x180009095  jz      loc_1800094A5
0x18000909b  mov     r8, rsi; Size
0x18000909e  xor     edx, edx; Val
0x1800090a0  mov     rcx, rax; void *
0x1800090a3  call    memset_0
0x1800090a8  sub     si, 2
0x1800090ac  mov     [rbx+4], r13w
0x1800090b1  mov     [rbx], si
0x1800090b4  mov     dword ptr [rbx+6], 10141981h
0x1800090bb  movzx   eax, word ptr [rbp+47h+Size]
0x1800090bf  mov     [rbx+0Ah], ax
0x1800090c3  mov     word ptr [rbx+0Ch], 20h ; ' '
0x1800090c9  test    r14, r14
0x1800090cc  jz      short loc_1800090DF
0x1800090ce  movups  xmm0, xmmword ptr [r14]
0x1800090d2  movups  xmmword ptr [rbx+0Eh], xmm0
0x1800090d6  movups  xmm1, xmmword ptr [r14+10h]
0x1800090db  movups  xmmword ptr [rbx+1Eh], xmm1
0x1800090df  mov     rax, [rbp+47h+Src]
0x1800090e3  test    rax, rax
0x1800090e6  jz      short loc_1800090FC
0x1800090e8  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x1800090ec  lea     rcx, [rbx+2Eh]; void *
0x1800090f0  mov     rdx, rax; Src
0x1800090f3  call    memcpy_0
0x1800090f8  mov     rax, [rbp+47h+Src]
0x1800090fc  mov     rcx, rax; pv
0x1800090ff  call    cs:__imp_CoTaskMemFree
0x180009105  mov     rcx, rbx; pidl
0x180009108  call    cs:__imp_ILFindLastID
0x18000910e  test    rax, rax
0x180009111  jz      short loc_180009131
0x180009113  movzx   ecx, word ptr [rax]
0x180009116  cmp     ecx, 2Eh ; '.'
0x180009119  jb      short loc_180009131
0x18000911b  cmp     dword ptr [rax+6], 10141981h
0x180009122  jnz     short loc_180009131
0x180009124  movzx   edx, word ptr [rax+0Ah]
0x180009128  add     rdx, 2Eh ; '.'
0x18000912c  cmp     rcx, rdx
0x18000912f  jnb     short loc_1800091B0
0x180009131  test    rbx, rbx
0x180009134  jz      short loc_180009162
0x180009136  cmp     word ptr [rbx], 0
0x18000913a  jz      short loc_180009162
0x18000913c  mov     rcx, rbx; pidl
0x18000913f  call    cs:__imp_ILFindLastID
0x180009145  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x180009148  mov     rsi, rax
0x18000914b  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x180009150  movzx   ecx, word ptr [rsi]
0x180009153  mov     rdx, rax
0x180009156  add     rsi, rcx
0x180009159  test    rax, rax
0x18000915c  jnz     loc_1800095D9
0x180009162  mov     edi, 80070057h
0x180009167  jmp     short loc_18000918A
0x180009169  test    edi, edi
0x18000916b  js      short loc_180009170
0x18000916d  mov     [r14], esi
0x180009170  mov     rcx, [rbp+47h+var_90]
0x180009174  mov     rax, [rcx]
0x180009177  mov     rax, [rax+10h]
0x18000917b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009180  test    edi, edi
0x180009182  js      short loc_18000918A
0x180009184  mov     [r15], rbx
0x180009187  mov     rbx, r13
0x18000918a  mov     rcx, rbx; pidl
0x18000918d  call    cs:__imp_ILFree
0x180009193  mov     eax, edi
0x180009195  mov     rbx, [rsp+0D0h+arg_10]
0x18000919d  add     rsp, 0A0h
0x1800091a4  pop     r15
0x1800091a6  pop     r14
0x1800091a8  pop     r13
0x1800091aa  pop     r12
0x1800091ac  pop     rdi
0x1800091ad  pop     rsi
0x1800091ae  pop     rbp
0x1800091af  retn
0x1800091b0  lea     r14, [rax+0Eh]
0x1800091b4  test    r14, r14
0x1800091b7  jz      loc_180009131
0x1800091bd  xor     r13d, r13d
0x1800091c0  mov     rax, [rdi]
0x1800091c3  lea     r8, [rbp+47h+var_90]
0x1800091c7  lea     rdx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x1800091ce  mov     [rbp+47h+var_90], r13
0x1800091d2  mov     rcx, rdi
0x1800091d5  mov     rax, [rax]
0x1800091d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091dd  mov     edi, eax
0x1800091df  test    eax, eax
0x1800091e1  js      short loc_18000918A
0x1800091e3  mov     dword ptr [rbp+47h+arg_20], r13d
0x1800091e7  cmp     r12d, 1
0x1800091eb  jnz     loc_1800092C8
0x1800091f1  or      dword ptr [r14+1Ch], 100h
0x1800091f9  lea     rsi, [r14+1Ch]
0x1800091fd  cmp     [rbp+47h+arg_8], 2
0x180009201  jnz     loc_180009170
0x180009207  mov     eax, [rsi]
0x180009209  test    al, 4
0x18000920b  jnz     loc_1800092BC
0x180009211  test    al, 2
0x180009213  jnz     loc_1800092BC
0x180009219  test    al, 10h
0x18000921b  jnz     loc_1800092BC
0x180009221  mov     r12, [rbp+47h+arg_0]
0x180009225  lea     r8, PKEY_SFGAOFlags
0x18000922c  xor     eax, eax
0x18000922e  xorps   xmm0, xmm0
0x180009231  mov     [rbp+47h+var_50], rax
0x180009235  add     r12, 0B8h
0x18000923c  lea     rax, [rbp+47h+propvarIn]
0x180009240  mov     rcx, r12
0x180009243  xor     r9d, r9d
0x180009246  mov     [rsp+0D0h+ppv], rax
0x18000924b  mov     rdx, rbx
0x18000924e  movups  xmmword ptr [rbp+47h+propvarIn], xmm0
0x180009252  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180009257  mov     edi, eax
0x180009259  test    eax, eax
0x18000925b  js      short loc_180009268
0x18000925d  cmp     word ptr [rbp+47h+propvarIn], 1
0x180009262  jnz     loc_18000933D
0x180009268  mov     rcx, rbx; pidl
0x18000926b  call    cs:__imp_ILFindLastID
0x180009271  mov     r8, rax
0x180009274  test    rax, rax
0x180009277  jz      short loc_18000929D
0x180009279  movzx   eax, word ptr [rax]
0x18000927c  cmp     eax, 2Eh ; '.'
0x18000927f  jb      short loc_18000929D
0x180009281  cmp     dword ptr [r8+6], 10141981h
0x180009289  jnz     short loc_18000929D
0x18000928b  movzx   edx, word ptr [r8+0Ah]
0x180009290  add     rdx, 2Eh ; '.'
0x180009294  cmp     rax, rdx
0x180009297  jnb     loc_18000951B
0x18000929d  mov     edx, 0BEEF0013h
0x1800092a2  mov     rcx, rbx
0x1800092a5  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x1800092aa  test    rax, rax
0x1800092ad  jz      loc_18000936E
0x1800092b3  lea     r8, [rax+24h]
0x1800092b7  jmp     loc_180009364
0x1800092bc  mov     dword ptr [r14], 20000000h
0x1800092c3  jmp     loc_180009170
0x1800092c8  mov     eax, [r14+1Ch]
0x1800092cc  lea     rsi, [r14+1Ch]
0x1800092d0  test    al, 4
0x1800092d2  jnz     loc_1800091F1
0x1800092d8  test    al, 2
0x1800092da  jnz     loc_1800091F1
0x1800092e0  test    al, 10h
0x1800092e2  jnz     loc_1800091F1
0x1800092e8  mov     rcx, [rbp+47h+var_90]
0x1800092ec  lea     r8, [rbp+47h+arg_20]
0x1800092f0  lea     rdx, PKEY_ParsingPath
0x1800092f7  mov     rax, [rcx]
0x1800092fa  mov     rax, [rax+40h]
0x1800092fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009303  test    eax, eax
0x180009305  jns     loc_180009481
0x18000930b  mov     rcx, [rbp+47h+var_90]
0x18000930f  lea     r8, [rbp+47h+arg_20]
0x180009313  lea     rdx, PKEY_ResultSourceId
0x18000931a  mov     rax, [rcx]
0x18000931d  mov     rax, [rax+40h]
0x180009321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009326  test    eax, eax
0x180009328  js      loc_1800091FD
0x18000932e  cmp     dword ptr [rbp+47h+arg_20], 0
0x180009332  jnz     loc_1800091FD
0x180009338  jmp     loc_1800091F1
0x18000933d  xor     edx, edx; ulDefault
0x18000933f  lea     rcx, [rbp+47h+propvarIn]; propvarIn
0x180009343  call    cs:__imp_PropVariantToUInt32WithDefault
0x180009349  mov     esi, eax
0x18000934b  lea     rcx, [rbp+47h+propvarIn]; pvar
0x18000934f  and     esi, 646BA000h
0x180009355  call    cs:__imp_PropVariantClear
0x18000935b  jmp     loc_18000916D
0x180009360  add     r8, 2Ah ; '*'
0x180009364  test    byte ptr [r8], 1
0x180009368  jnz     loc_180009540
0x18000936e  xor     eax, eax
0x180009370  lea     r8, PKEY_DelegationFlags
0x180009377  mov     [rbp+47h+var_38], rax
0x18000937b  xorps   xmm0, xmm0
0x18000937e  lea     rax, [rbp+47h+pvar]
0x180009382  xor     r9d, r9d
0x180009385  mov     rdx, rbx
0x180009388  mov     [rsp+0D0h+ppv], rax
0x18000938d  mov     rcx, r12
0x180009390  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180009394  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180009399  test    eax, eax
0x18000939b  jns     loc_1800095E7
0x1800093a1  lea     rax, [rbp+47h+pidl]
0x1800093a5  mov     [rbp+47h+psfRoot], r13
0x1800093a9  mov     [rsp+0D0h+var_A0], rax
0x1800093ae  mov     r9d, 0FFFFFFFFh
0x1800093b4  lea     rax, [rbp+47h+psfRoot]
0x1800093b8  mov     [rbp+47h+pidl], r13
0x1800093bc  mov     [rsp+0D0h+ppidlLast], rax
0x1800093c1  mov     r8d, 1
0x1800093c7  lea     rax, _GUID_000214e6_0000_0000_c000_000000000046
0x1800093ce  mov     rdx, rbx
0x1800093d1  mov     rcx, r12
0x1800093d4  mov     [rsp+0D0h+ppv], rax
0x1800093d9  mov     esi, r13d
0x1800093dc  call    ?DelegateBindToParent@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@W4DELBIND_TYPE@@W4DELEGATION_FLAGS@@AEBU_GUID@@PEAPEAXPEAPEAU2@@Z; CDBFolder::DelegateBindToParent(_ITEMID_CHILD const *,DELBIND_TYPE,DELEGATION_FLAGS,_GUID const &,void * *,_ITEMID_CHILD * *)
0x1800093e1  mov     edi, eax
0x1800093e3  test    eax, eax
0x1800093e5  js      loc_180009169
0x1800093eb  mov     rdx, [rbp+47h+pidl]; pidl
0x1800093ef  lea     rax, [rbp+47h+var_68]
0x1800093f3  mov     rcx, [rbp+47h+psfRoot]; psfRoot
0x1800093f7  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800093fe  mov     [rsp+0D0h+ppidlLast], rax; ppidlLast
0x180009403  xor     r8d, r8d; ppbc
0x180009406  lea     rax, [rbp+47h+var_80]
0x18000940a  mov     [rbp+47h+var_68], r13
0x18000940e  mov     [rsp+0D0h+ppv], rax; ppv
0x180009413  mov     [rbp+47h+var_80], r13
0x180009417  call    cs:__imp_SHBindToFolderIDListParentEx
0x18000941d  test    eax, eax
0x18000941f  js      short loc_180009462
0x180009421  mov     rcx, [rbp+47h+var_80]
0x180009425  lea     r9, [rbp+47h+arg_0]
0x180009429  mov     dword ptr [rbp+47h+arg_0], 646BA000h
0x180009430  lea     r8, [rbp+47h+var_68]
0x180009434  mov     edx, 1
0x180009439  mov     rax, [rcx]
0x18000943c  mov     rax, [rax+48h]
0x180009440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009445  test    eax, eax
0x180009447  js      short loc_180009452
0x180009449  mov     esi, dword ptr [rbp+47h+arg_0]
0x18000944c  and     esi, 646BA000h
0x180009452  mov     rcx, [rbp+47h+var_80]
0x180009456  mov     rax, [rcx]
0x180009459  mov     rax, [rax+10h]
0x18000945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009462  mov     rcx, [rbp+47h+psfRoot]
0x180009466  mov     rax, [rcx]
0x180009469  mov     rax, [rax+10h]
0x18000946d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009472  mov     rcx, [rbp+47h+pidl]; pidl
0x180009476  call    cs:__imp_ILFree
0x18000947c  jmp     loc_18000916D
0x180009481  cmp     dword ptr [rbp+47h+arg_20], 0
0x180009485  jnz     loc_18000930B
0x18000948b  jmp     loc_1800091F1
0x180009490  mov     rax, [rsi]
0x180009493  mov     rdx, r13
0x180009496  mov     rcx, rsi
0x180009499  mov     rax, [rax+18h]
0x18000949d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094a2  mov     rbx, rax
0x1800094a5  test    rbx, rbx
  ... truncated ...
```
