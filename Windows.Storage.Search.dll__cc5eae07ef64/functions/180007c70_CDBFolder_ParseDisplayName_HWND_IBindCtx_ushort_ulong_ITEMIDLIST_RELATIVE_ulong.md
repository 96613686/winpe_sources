# CDBFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180007c70`
- end: `0x180008298`
- name: `?ParseDisplayName@CDBFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `1576`
- prototype: `__int64 __usercall@<rax>(CDBFolder *__hidden this@<rcx>, HWND@<rdx>, struct IBindCtx *@<r8>, unsigned __int16 *@<r9>, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065100`

## callees

- `0x18000782c`
- `0x180007c70`
- `0x180009e20`
- `0x180019b60`
- `0x180028a68`
- `0x18003d6b0`
- `0x18004c300`
- `0x18004dc1c`
- `0x18005e034`
- `0x18005e950`
- `0x180072cdc`
- `0x180072cf4`
- `0x18008cb30`
- `0x18008cc38`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x180007e42`
- `Windows.Storage!ILFindLastID` at `0x180007e42`
- `Windows.Storage!ILFree` at `0x180007f18`
- `Windows.Storage!ILFree` at `0x180007fb7`
- `Windows.Storage!ILFree` at `0x180007f18`
- `Windows.Storage!ILFree` at `0x180007fb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800080a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008278`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800081d4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800081d4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800081f0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800081f0`

## pseudocode

```c
__int64 __fastcall CDBFolder::ParseDisplayName(
        CDBFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **Size,
        unsigned int *a7)
{
  struct _ITEMIDLIST_RELATIVE **v7; // r13
  CDBFolder *v10; // rsi
  PWSTR v11; // r12
  const struct _ITEMID_CHILD *v12; // r14
  struct IBindCtxVtbl *lpVtbl; // rax
  int v14; // ebx
  unsigned __int16 *v15; // r8
  __int64 (__fastcall ***v16)(_QWORD, GUID *, unsigned __int64 *); // r12
  __int64 v17; // rdi
  int v18; // eax
  __int64 v19; // rsi
  __int16 v20; // bx
  void *v21; // rax
  __int64 v22; // rdi
  __int16 v23; // ax
  void *v24; // rax
  LPITEMIDLIST ID; // rax
  LPITEMIDLIST v26; // rdx
  unsigned __int64 cb; // rax
  __int64 v28; // rax
  BYTE *abID; // rsi
  __int64 (__fastcall **v30)(_QWORD, GUID *, unsigned __int64 *); // rax
  __int64 v31; // r8
  int v32; // eax
  __int64 (__fastcall **v33)(_QWORD, GUID *, unsigned __int64 *); // rax
  unsigned int *v34; // rdi
  int v36; // eax
  __int64 v37; // rcx
  _WORD *v38; // rax
  __int64 v39; // r8
  int v40; // eax
  unsigned __int16 *v41; // rsi
  PWSTR v42; // rax
  __int64 v43; // rcx
  unsigned __int64 v44; // r12
  int v45; // eax
  int v46; // eax
  int v47; // eax
  __int64 v48; // [rsp+40h] [rbp-40h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, unsigned __int64 *); // [rsp+48h] [rbp-38h] BYREF
  void *Src; // [rsp+50h] [rbp-30h] BYREF
  PWSTR v51; // [rsp+58h] [rbp-28h]
  unsigned __int64 v52; // [rsp+60h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+50h] BYREF

  v7 = Size;
  v51 = 0;
  Size = 0;
  pv = 0;
  v10 = this;
  *v7 = 0;
  v11 = 0;
  v12 = 0;
  if ( a3
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a3->lpVtbl->GetObjectParam)(
         a3,
         L"ParseWithQueryResult",
         &pv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    lpVtbl = a3->lpVtbl;
    v49 = 0;
    v14 = -2147467262;
    pv = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))lpVtbl->GetObjectParam)(
           a3,
           L"ParseWithQueryResult",
           &pv) < 0 )
      goto LABEL_32;
    v14 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))pv)(
            pv,
            &GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160,
            &v49);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    if ( v14 < 0 )
      goto LABEL_32;
    LODWORD(pv) = 0;
    v14 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, unsigned __int64 *), LPVOID *))(*v49)[16])(
            v49,
            &pv);
    if ( v14 < 0 )
    {
LABEL_31:
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, unsigned __int64 *)))(*v49)[2])(v49);
LABEL_32:
      v11 = v51;
LABEL_33:
      v10 = this;
      goto LABEL_34;
    }
    if ( (_DWORD)pv != 1 )
    {
      Src = 0;
      v14 = (*v49)[24](v49, &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea, (unsigned __int64 *)&Src);
      if ( v14 >= 0 )
      {
        v39 = 2;
        if ( (_DWORD)pv == 2 )
        {
          v39 = 1;
        }
        else if ( (_DWORD)pv == 3 )
        {
          v39 = 3;
        }
        v14 = CDBFolder::_GenerateFilteredIDList(v10, Src, v39, v49, 0, &Size);
        (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
        v12 = (const struct _ITEMID_CHILD *)Size;
      }
      goto LABEL_31;
    }
    v16 = v49;
    v17 = *((_QWORD *)v10 + 26);
    v18 = 0;
    Src = 0;
    LODWORD(Size) = 0;
    if ( v49 )
    {
      v33 = *v49;
      v48 = 0;
      v14 = (*v33)(v49, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, (unsigned __int64 *)&v48);
      if ( v14 < 0 )
        goto LABEL_31;
      v14 = (*(__int64 (__fastcall **)(__int64, void **, struct _ITEMIDLIST_RELATIVE ***))(*(_QWORD *)v48 + 40LL))(
              v48,
              &Src,
              &Size);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      if ( v14 < 0 )
        goto LABEL_31;
      v18 = (int)Size;
    }
    v19 = (unsigned int)(v18 + 40) + 2LL;
    if ( v17 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 24LL))(v17, (unsigned int)(v18 + 40) + 2LL);
    }
    else
    {
      v20 = v18 + 50;
      if ( (unsigned __int64)(unsigned int)(v18 + 40) + 10 > 0x10001 )
        goto LABEL_51;
      v21 = CoTaskMemAlloc((unsigned int)(v18 + 40) + 10LL);
      v22 = (__int64)v21;
      if ( v21 )
      {
        memset_0(v21, 0, v19 + 8);
        *(_WORD *)(v22 + 4) = v19;
        *(_WORD *)v22 = v20 - 2;
        goto LABEL_12;
      }
    }
    if ( v22 )
    {
LABEL_12:
      *(_DWORD *)(v22 + 6) = 269752705;
      v23 = (__int16)Size;
      *(_OWORD *)(v22 + 14) = 0;
      *(_WORD *)(v22 + 10) = v23;
      *(_OWORD *)(v22 + 30) = 0;
      *(_WORD *)(v22 + 12) = 32;
      v24 = Src;
      if ( Src )
      {
        memcpy_0((void *)(v22 + 46), Src, (unsigned int)Size);
        v24 = Src;
      }
      CoTaskMemFree(v24);
      ID = ILFindLastID((LPCITEMIDLIST)v22);
      v26 = ID;
      if ( !ID
        || (cb = ID->mkid.cb, (unsigned int)cb < 0x2E)
        || *(_DWORD *)&v26[2].mkid.cb != 269752705
        || cb < (unsigned __int64)*(unsigned __int16 *)((char *)&v26[3].mkid.cb + 1) + 46
        || (abID = v26[4].mkid.abID, v26 == (LPITEMIDLIST)-14LL) )
      {
        v28 = ILFindHiddenIDOn(v22, 3203334163LL);
        if ( !v28 )
        {
          v14 = -2147024809;
LABEL_28:
          ILFree((LPITEMIDLIST)v22);
          goto LABEL_31;
        }
        abID = (BYTE *)(v28 + 8);
      }
      v30 = *v16;
      v52 = 0;
      v14 = (*v30)(v16, &GUID_3017056d_9a91_4e90_937d_746c72abbf4f, &v52);
      if ( v14 >= 0 )
      {
        *((_DWORD *)abID + 7) |= 0x100u;
        v32 = *((_DWORD *)abID + 7);
        if ( (v32 & 4) != 0 || (v32 & 2) != 0 || (v32 & 0x10) != 0 )
        {
          *(_DWORD *)abID = 0x20000000;
        }
        else
        {
          LODWORD(v48) = 0;
          v14 = CDBFolder::_AttributesFromIDList(this, v22, v31, 1684774912, &v48);
          if ( v14 >= 0 )
            *(_DWORD *)abID = v48;
        }
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v52 + 16LL))(v52);
        if ( v14 >= 0 )
        {
          v12 = (const struct _ITEMID_CHILD *)v22;
          v22 = 0;
        }
      }
      goto LABEL_28;
    }
LABEL_51:
    v14 = -2147024882;
    CoTaskMemFree(Src);
    goto LABEL_31;
  }
  pv = 0;
  if ( a3
    && ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, LPVOID *))a3->lpVtbl->GetObjectParam)(
         a3,
         L"ParseWithProperties",
         &pv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    v40 = CDBFolder::_ParseWithProperties(v10, a3, (struct _ITEMID_CHILD **)&Size);
    v12 = (const struct _ITEMID_CHILD *)Size;
    v14 = v40;
  }
  else
  {
    pv = 0;
    if ( !a3
      || ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a3->lpVtbl->GetObjectParam)(
           a3,
           L"ParseOriginalItem",
           &pv) < 0 )
    {
      v14 = -2147024809;
      if ( PathIsUNCW(a4) )
        return (unsigned int)v14;
      v41 = 0;
      pv = 0;
      v42 = StrChrW(a4, 0x5Cu);
      v51 = v42;
      v11 = v42;
      if ( !v42 )
        goto LABEL_74;
      v44 = v42 - a4;
      v52 = (int)v44 + 1;
      v45 = _AllocArray<unsigned short,CTLocalAllocPolicy>(v43, 64, v52, &pv);
      v41 = (unsigned __int16 *)pv;
      v14 = v45;
      if ( v45 >= 0 )
        v14 = StringCchCopyNW((unsigned __int16 *)pv, v52, a4, v44);
      v11 = v51;
      a4 = v41;
      if ( v14 >= 0 )
      {
LABEL_74:
        v46 = BindCtx_ContainsObject(a3, L"Assume wordwheel present");
        v47 = CDBFolder::_ParseSearchParsingName(this, a4, v46, (struct _ITEMID_CHILD **)&Size);
        v12 = (const struct _ITEMID_CHILD *)Size;
        v14 = v47;
      }
      CoTaskMemFree(v41);
      goto LABEL_33;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    v36 = CDBFolder::_ParseWithPartialIDList(v10, a3, (struct _ITEMID_CHILD **)&Size);
    v12 = (const struct _ITEMID_CHILD *)Size;
    v14 = v36;
  }
LABEL_34:
  if ( v14 >= 0 )
  {
    if ( !v11 )
      goto LABEL_36;
    v15 = v11 + 1;
    v38 = v11 + 1;
    if ( v11 != (PWSTR)-2LL )
    {
      do
      {
        if ( *v38 != 32 )
          break;
        ++v38;
      }
      while ( v38 );
    }
    v37 = -1;
    do
      ++v37;
    while ( v38[v37] );
    if ( v37 )
    {
      v14 = CDBFolder::_ParseNextAndAppend(v10, a2, v15, v12, a3, v7, a7);
    }
    else
    {
LABEL_36:
      v34 = a7;
      if ( a7 )
        *v34 = SHGetAttributesWithBindCtx((struct IShellFolder *)v10, v12, (struct IBindCtx *)v15, *a7);
      *v7 = v12;
      v12 = 0;
    }
    ILFree((LPITEMIDLIST)v12);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180007c70  mov     [rsp-38h+arg_18], rbx
0x180007c75  mov     [rsp-38h+arg_8], rdx
0x180007c7a  mov     [rsp-38h+arg_0], rcx
0x180007c7f  push    rbp
0x180007c80  push    rsi
0x180007c81  push    rdi
0x180007c82  push    r12
0x180007c84  push    r13
0x180007c86  push    r14
0x180007c88  push    r15
0x180007c8a  mov     rbp, rsp
0x180007c8d  sub     rsp, 80h
0x180007c94  mov     r13, [rbp+Size]
0x180007c98  xor     ebx, ebx
0x180007c9a  mov     [rbp+var_28], rbx
0x180007c9e  mov     rdi, r9
0x180007ca1  mov     [rbp+Size], rbx
0x180007ca5  mov     r15, r8
0x180007ca8  mov     [rbp+pv], rbx
0x180007cac  mov     rsi, rcx
0x180007caf  mov     [r13+0], rbx
0x180007cb3  mov     r12d, ebx
0x180007cb6  mov     r14d, ebx
0x180007cb9  test    r8, r8
0x180007cbc  jz      loc_180007FDA
0x180007cc2  mov     rax, [r8]
0x180007cc5  lea     rdx, aParsewithquery; "ParseWithQueryResult"
0x180007ccc  lea     r8, [rbp+pv]
0x180007cd0  mov     rcx, r15
0x180007cd3  mov     rax, [rax+50h]
0x180007cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cdc  test    eax, eax
0x180007cde  js      loc_180007FDA
0x180007ce4  mov     rcx, [rbp+pv]
0x180007ce8  mov     rax, [rcx]
0x180007ceb  mov     rax, [rax+10h]
0x180007cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf4  mov     rax, [r15]
0x180007cf7  lea     r8, [rbp+pv]
0x180007cfb  mov     [rbp+var_38], rbx
0x180007cff  lea     rdx, aParsewithquery; "ParseWithQueryResult"
0x180007d06  xor     edi, edi
0x180007d08  mov     rcx, r15
0x180007d0b  mov     ebx, 80004002h
0x180007d10  mov     [rbp+pv], rdi
0x180007d14  mov     rax, [rax+50h]
0x180007d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1d  test    eax, eax
0x180007d1f  js      loc_180007F8B
0x180007d25  mov     rcx, [rbp+pv]
0x180007d29  lea     r8, [rbp+var_38]
0x180007d2d  lea     rdx, _GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160
0x180007d34  mov     rax, [rcx]
0x180007d37  mov     rax, [rax]
0x180007d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d3f  mov     rcx, [rbp+pv]
0x180007d43  mov     ebx, eax
0x180007d45  mov     rax, [rcx]
0x180007d48  mov     rax, [rax+10h]
0x180007d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d51  test    ebx, ebx
0x180007d53  js      loc_180007F8B
0x180007d59  mov     rcx, [rbp+var_38]
0x180007d5d  lea     rdx, [rbp+pv]
0x180007d61  mov     dword ptr [rbp+pv], edi
0x180007d64  mov     rax, [rcx]
0x180007d67  mov     rax, [rax+80h]
0x180007d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d73  mov     ebx, eax
0x180007d75  test    eax, eax
0x180007d77  js      loc_180007F7B
0x180007d7d  cmp     dword ptr [rbp+pv], 1
0x180007d81  jnz     loc_18000811D
0x180007d87  mov     r12, [rbp+var_38]
0x180007d8b  xor     ecx, ecx
0x180007d8d  mov     rdi, [rsi+0D0h]
0x180007d94  mov     eax, ecx
0x180007d96  movaps  [rsp+80h+var_10], xmm6
0x180007d9b  xorps   xmm6, xmm6
0x180007d9e  mov     [rbp+Src], rcx
0x180007da2  mov     dword ptr [rbp+Size], ecx
0x180007da5  test    r12, r12
0x180007da8  jnz     loc_180007F20
0x180007dae  lea     esi, [rax+28h]
0x180007db1  add     rsi, 2
0x180007db5  test    rdi, rdi
0x180007db8  jnz     loc_18000807B
0x180007dbe  lea     rbx, [rsi+8]
0x180007dc2  cmp     rbx, 10001h
0x180007dc9  ja      loc_180008099
0x180007dcf  mov     rcx, rbx; cb
0x180007dd2  call    cs:__imp_CoTaskMemAlloc
0x180007dd8  mov     rdi, rax
0x180007ddb  test    rax, rax
0x180007dde  jz      loc_180008090
0x180007de4  mov     r8, rbx; Size
0x180007de7  xor     edx, edx; Val
0x180007de9  mov     rcx, rax; void *
0x180007dec  call    memset_0
0x180007df1  sub     bx, 2
0x180007df5  mov     [rdi+4], si
0x180007df9  mov     [rdi], bx
0x180007dfc  mov     dword ptr [rdi+6], 10141981h
0x180007e03  movzx   eax, word ptr [rbp+Size]
0x180007e07  movups  xmmword ptr [rdi+0Eh], xmm6
0x180007e0b  mov     [rdi+0Ah], ax
0x180007e0f  movups  xmmword ptr [rdi+1Eh], xmm6
0x180007e13  mov     word ptr [rdi+0Ch], 20h ; ' '
0x180007e19  mov     rax, [rbp+Src]
0x180007e1d  test    rax, rax
0x180007e20  jz      short loc_180007E36
0x180007e22  mov     r8d, dword ptr [rbp+Size]; Size
0x180007e26  lea     rcx, [rdi+2Eh]; void *
0x180007e2a  mov     rdx, rax; Src
0x180007e2d  call    memcpy_0
0x180007e32  mov     rax, [rbp+Src]
0x180007e36  mov     rcx, rax; pv
0x180007e39  call    cs:__imp_CoTaskMemFree
0x180007e3f  mov     rcx, rdi; pidl
0x180007e42  call    cs:__imp_ILFindLastID
0x180007e48  mov     rdx, rax
0x180007e4b  test    rax, rax
0x180007e4e  jz      short loc_180007E72
0x180007e50  movzx   eax, word ptr [rax]
0x180007e53  cmp     eax, 2Eh ; '.'
0x180007e56  jb      short loc_180007E72
0x180007e58  cmp     dword ptr [rdx+6], 10141981h
0x180007e5f  jnz     short loc_180007E72
0x180007e61  movzx   ecx, word ptr [rdx+0Ah]
0x180007e65  add     rcx, 2Eh ; '.'
0x180007e69  cmp     rax, rcx
0x180007e6c  jnb     loc_180008069
0x180007e72  mov     edx, 0BEEF0013h
0x180007e77  mov     rcx, rdi
0x180007e7a  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x180007e7f  test    rax, rax
0x180007e82  jz      loc_1800080AD
0x180007e88  lea     rsi, [rax+8]
0x180007e8c  mov     rax, [r12]
0x180007e90  lea     r8, [rbp+var_20]
0x180007e94  lea     rdx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x180007e9b  mov     [rbp+var_20], r14
0x180007e9f  mov     rcx, r12
0x180007ea2  mov     rax, [rax]
0x180007ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eaa  mov     ebx, eax
0x180007eac  test    eax, eax
0x180007eae  js      short loc_180007F15
0x180007eb0  or      dword ptr [rsi+1Ch], 100h
0x180007eb7  mov     eax, [rsi+1Ch]
0x180007eba  test    al, 4
0x180007ebc  jnz     loc_18000805E
0x180007ec2  test    al, 2
0x180007ec4  jnz     loc_18000805E
0x180007eca  test    al, 10h
0x180007ecc  jnz     loc_18000805E
0x180007ed2  mov     rcx, [rbp+arg_0]
0x180007ed6  lea     rax, [rbp+var_40]
0x180007eda  mov     r9d, 646BA000h
0x180007ee0  mov     [rsp+80h+var_60], rax
0x180007ee5  mov     rdx, rdi
0x180007ee8  mov     dword ptr [rbp+var_40], r14d
0x180007eec  call    ?_AttributesFromIDList@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@W4PROPERTY_GET_TYPE@@KPEAK@Z; CDBFolder::_AttributesFromIDList(_ITEMID_CHILD const *,PROPERTY_GET_TYPE,ulong,ulong *)
0x180007ef1  mov     ebx, eax
0x180007ef3  test    eax, eax
0x180007ef5  js      short loc_180007EFC
0x180007ef7  mov     eax, dword ptr [rbp+var_40]
0x180007efa  mov     [rsi], eax
0x180007efc  mov     rcx, [rbp+var_20]
0x180007f00  mov     rax, [rcx]
0x180007f03  mov     rax, [rax+10h]
0x180007f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0c  test    ebx, ebx
0x180007f0e  js      short loc_180007F15
0x180007f10  mov     r14, rdi
0x180007f13  xor     edi, edi
0x180007f15  mov     rcx, rdi; pidl
0x180007f18  call    cs:__imp_ILFree
0x180007f1e  jmp     short loc_180007F76
0x180007f20  mov     rax, [r12]
0x180007f24  lea     r8, [rbp+var_40]
0x180007f28  mov     [rbp+var_40], rcx
0x180007f2c  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180007f33  mov     rcx, r12
0x180007f36  mov     rax, [rax]
0x180007f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3e  mov     ebx, eax
0x180007f40  test    eax, eax
0x180007f42  js      short loc_180007F76
0x180007f44  mov     rcx, [rbp+var_40]
0x180007f48  lea     r8, [rbp+Size]
0x180007f4c  lea     rdx, [rbp+Src]
0x180007f50  mov     rax, [rcx]
0x180007f53  mov     rax, [rax+28h]
0x180007f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5c  mov     rcx, [rbp+var_40]
0x180007f60  mov     ebx, eax
0x180007f62  mov     rax, [rcx]
0x180007f65  mov     rax, [rax+10h]
0x180007f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f6e  test    ebx, ebx
0x180007f70  jns     loc_180008115
0x180007f76  movaps  xmm6, [rsp+80h+var_10]
0x180007f7b  mov     rcx, [rbp+var_38]
0x180007f7f  mov     rax, [rcx]
0x180007f82  mov     rax, [rax+10h]
0x180007f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8b  mov     r12, [rbp+var_28]
0x180007f8f  mov     rsi, [rbp+arg_0]
0x180007f93  test    ebx, ebx
0x180007f95  js      short loc_180007FBD
0x180007f97  test    r12, r12
0x180007f9a  jnz     loc_1800080FA
0x180007fa0  mov     rdi, [rbp+arg_30]
0x180007fa4  test    rdi, rdi
0x180007fa7  jnz     loc_180008283
0x180007fad  mov     [r13+0], r14
0x180007fb1  xor     r14d, r14d
0x180007fb4  mov     rcx, r14; pidl
0x180007fb7  call    cs:__imp_ILFree
0x180007fbd  mov     eax, ebx
0x180007fbf  mov     rbx, [rsp+80h+arg_18]
0x180007fc7  add     rsp, 80h
0x180007fce  pop     r15
0x180007fd0  pop     r14
0x180007fd2  pop     r13
0x180007fd4  pop     r12
0x180007fd6  pop     rdi
0x180007fd7  pop     rsi
0x180007fd8  pop     rbp
0x180007fd9  retn
0x180007fda  mov     [rbp+pv], rbx
0x180007fde  test    r15, r15
0x180007fe1  jz      short loc_180008005
0x180007fe3  mov     rax, [r15]
0x180007fe6  lea     r8, [rbp+pv]
0x180007fea  lea     rdx, aParsewithprope; "ParseWithProperties"
0x180007ff1  mov     rcx, r15
0x180007ff4  mov     rax, [rax+50h]
0x180007ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ffd  test    eax, eax
0x180007fff  jns     loc_1800081A2
0x180008005  mov     [rbp+pv], rbx
0x180008009  test    r15, r15
0x18000800c  jz      loc_1800081CC
0x180008012  mov     rax, [r15]
0x180008015  lea     r8, [rbp+pv]
0x180008019  lea     rdx, aParseoriginali; "ParseOriginalItem"
0x180008020  mov     rcx, r15
0x180008023  mov     rax, [rax+50h]
0x180008027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000802c  test    eax, eax
0x18000802e  js      loc_1800081CC
0x180008034  mov     rcx, [rbp+pv]
0x180008038  mov     rax, [rcx]
0x18000803b  mov     rax, [rax+10h]
0x18000803f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008044  lea     r8, [rbp+Size]; struct _ITEMID_CHILD **
0x180008048  mov     rdx, r15; struct IBindCtx *
0x18000804b  mov     rcx, rsi; this
0x18000804e  call    ?_ParseWithPartialIDList@CDBFolder@@AEAAJPEAUIBindCtx@@PEAPEAU_ITEMID_CHILD@@@Z; CDBFolder::_ParseWithPartialIDList(IBindCtx *,_ITEMID_CHILD * *)
0x180008053  mov     r14, [rbp+Size]
0x180008057  mov     ebx, eax
0x180008059  jmp     loc_180007F93
0x18000805e  mov     dword ptr [rsi], 20000000h
0x180008064  jmp     loc_180007EFC
0x180008069  lea     rsi, [rdx+0Eh]
0x18000806d  test    rsi, rsi
0x180008070  jnz     loc_180007E8C
0x180008076  jmp     loc_180007E72
0x18000807b  mov     rax, [rdi]
0x18000807e  mov     rdx, rsi
0x180008081  mov     rcx, rdi
0x180008084  mov     rax, [rax+18h]
0x180008088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808d  mov     rdi, rax
0x180008090  test    rdi, rdi
0x180008093  jnz     loc_180007DFC
0x180008099  mov     rcx, [rbp+Src]; pv
0x18000809d  mov     ebx, 8007000Eh
0x1800080a2  call    cs:__imp_CoTaskMemFree
0x1800080a8  jmp     loc_180007F76
0x1800080ad  mov     ebx, 80070057h
0x1800080b2  jmp     loc_180007F15
0x1800080b7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800080be  inc     rcx
0x1800080c1  cmp     word ptr [rax+rcx*2], 0
0x1800080c6  jnz     short loc_1800080BE
0x1800080c8  test    rcx, rcx
0x1800080cb  jz      loc_180007FA0
0x1800080d1  mov     rax, [rbp+arg_30]
0x1800080d5  mov     r9, r14; struct _ITEMID_CHILD *
0x1800080d8  mov     rdx, [rbp+arg_8]; HWND
0x1800080dc  mov     rcx, rsi; this
0x1800080df  mov     [rsp+80h+var_50], rax; unsigned int *
0x1800080e4  mov     [rsp+80h+var_58], r13; struct _ITEMIDLIST_RELATIVE **
0x1800080e9  mov     [rsp+80h+var_60], r15; struct IBindCtx *
0x1800080ee  call    ?_ParseNextAndAppend@CDBFolder@@AEAAJPEAUHWND__@@PEBGPEBU_ITEMID_CHILD@@PEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@PEAK@Z; CDBFolder::_ParseNextAndAppend(HWND__ *,ushort const *,_ITEMID_CHILD const *,IBindCtx *,_ITEMIDLIST_RELATIVE * *,ulong *)
0x1800080f3  mov     ebx, eax
0x1800080f5  jmp     loc_180007FB4
  ... truncated ...
```
