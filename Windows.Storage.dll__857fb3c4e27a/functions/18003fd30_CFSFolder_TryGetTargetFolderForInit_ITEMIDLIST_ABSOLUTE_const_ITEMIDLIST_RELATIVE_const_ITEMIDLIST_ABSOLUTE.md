# CFSFolder::TryGetTargetFolderForInit(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x18003fd30`
- end: `0x180040289`
- name: `?TryGetTargetFolderForInit@CFSFolder@@IEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU2@@Z`
- size: `1369`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_RELATIVE *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18050e5a0`

## callees

- `0x18003fd30`
- `0x180041b00`
- `0x1800432f0`
- `0x180054860`
- `0x18008acc0`
- `0x180093c20`
- `0x1800daee0`
- `0x1800dfcf0`
- `0x180127470`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fde6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fde6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fed2`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003fe04`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003feef`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003fe04`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003feef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fe6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004007f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800400c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004011e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800401cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fe6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ff61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004007f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800400c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004011e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800401cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040219`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFSFolder::TryGetTargetFolderForInit(
        CFSFolder *this,
        const struct _ITEMIDLIST_ABSOLUTE *a2,
        IMalloc *a3,
        struct _ITEMIDLIST_ABSOLUTE **a4)
{
  CFSFolder *v4; // r14
  void *v5; // rbx
  _QWORD *v6; // r13
  __int64 v7; // rax
  SIZE_T v8; // rdi
  int v9; // r15d
  int v10; // esi
  const void *v11; // r14
  unsigned __int16 *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rax
  size_t v15; // rsi
  size_t v16; // r15
  void *v17; // rcx
  __int64 v18; // rax
  void *v19; // r14
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  void *v22; // rbx
  size_t v23; // rsi
  unsigned int v24; // edi
  void *v25; // rcx
  const void *v27; // r14
  LPMALLOC v28; // r13
  unsigned __int16 *v29; // rdx
  int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // r12
  LPMALLOC v33; // rdx
  __int64 lpVtbl_low; // rcx
  ITEMIDLIST *v35; // rax
  LPITEMIDLIST v36; // rsi
  void *v37; // rcx
  void *v38; // rcx
  char v39; // r14
  IMalloc *v40; // rbx
  const struct _ITEMIDLIST_RELATIVE *v41; // r13
  const ITEMIDLIST *v42; // rax
  __int64 v43; // rcx
  LPMALLOC v44; // rcx
  int v45; // eax
  unsigned int v46; // ebx
  LPMALLOC v47; // rcx
  LPMALLOC v48; // rdi
  LPMALLOC v49; // rcx
  LPMALLOC v50; // rcx
  void *v51; // rcx
  struct _ITEMIDLIST_ABSOLUTE *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  char v54; // [rsp+38h] [rbp-40h]
  CFSFolder *v55; // [rsp+40h] [rbp-38h]
  void *Src; // [rsp+48h] [rbp-30h]
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-28h] BYREF
  LPMALLOC v58; // [rsp+58h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v58 = a3;
  Src = a2;
  v4 = this;
  v55 = this;
  *a4 = 0;
  pv = 0;
  v54 = 1;
  v5 = 0;
  TokenHandle = 0;
  v6 = (_QWORD *)((char *)this + 496);
  v7 = *((_QWORD *)this + 62) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v7 )
    v7 = *((_QWORD *)this + 63) - *(_QWORD *)GUID_NULL.Data4;
  v8 = 2;
  v9 = -2147024882;
  if ( v7 )
  {
    v10 = SHGetKnownFolderIDList_Internal((struct _GUID *)this + 31, 0x1000u, 0, &TokenHandle);
    if ( !v54 )
      goto LABEL_17;
    v5 = TokenHandle;
  }
  else
  {
    v10 = -2147467259;
    v11 = (const void *)*((_QWORD *)this + 55);
    if ( v11 )
    {
      v12 = (unsigned __int16 *)*((_QWORD *)this + 55);
      v13 = 2;
      do
      {
        v14 = *v12;
        if ( !(_WORD)v14 )
          break;
        v13 += v14;
        v12 = (unsigned __int16 *)((char *)v12 + v14);
      }
      while ( v12 );
      v15 = v13;
      v5 = CoTaskMemAlloc(v13);
      if ( v5 )
      {
        v16 = 0;
        ppMalloc = 0;
        if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
        {
          v16 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v5);
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
        memset_0(v5, 0, v16);
        memcpy_0(v5, v11, v15);
        v9 = -2147024882;
      }
      v10 = 0;
      if ( !v5 )
        v10 = -2147024882;
    }
    v4 = v55;
  }
  v17 = pv;
  pv = v5;
  if ( v17 )
    CoTaskMemFree(v17);
LABEL_17:
  if ( v10 < 0 )
  {
    v18 = *v6 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *v6 == *(_QWORD *)&GUID_NULL.Data1 )
      v18 = v6[1] - *(_QWORD *)GUID_NULL.Data4;
    if ( !v18 && !*((_QWORD *)v4 + 55) )
    {
      v19 = Src;
      if ( !Src )
      {
        *a4 = 0;
        v24 = -2147024809;
        goto LABEL_54;
      }
      v20 = (unsigned __int16 *)Src;
      do
      {
        v21 = *v20;
        if ( !(_WORD)v21 )
          break;
        v8 = (unsigned int)(v21 + v8);
        v20 = (unsigned __int16 *)((char *)v20 + v21);
      }
      while ( v20 );
      v22 = CoTaskMemAlloc(v8);
      if ( v22 )
      {
        v23 = 0;
        v58 = 0;
        if ( CoGetMalloc(1u, &v58) >= 0 )
        {
          v23 = ((__int64 (__fastcall *)(LPMALLOC, void *))v58->lpVtbl->GetSize)(v58, v22);
          ((void (__fastcall *)(LPMALLOC))v58->lpVtbl->Release)(v58);
        }
        memset_0(v22, 0, v23);
        memcpy_0(v22, v19, v8);
      }
      *a4 = (struct _ITEMIDLIST_ABSOLUTE *)v22;
      if ( !v22 )
      {
        v24 = -2147024882;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x257F,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)v24,
          (int)a4);
        v38 = pv;
        pv = 0;
        if ( v38 )
          CoTaskMemFree(v38);
        return v24;
      }
    }
    goto LABEL_32;
  }
  if ( !*((_QWORD *)v4 + 77) )
  {
    v27 = pv;
    v28 = v58;
    if ( pv )
    {
      if ( v58 )
      {
        v29 = (unsigned __int16 *)pv;
        v30 = 2;
        do
        {
          v31 = *v29;
          if ( !(_WORD)v31 )
            break;
          v30 += v31;
          v29 = (unsigned __int16 *)((char *)v29 + v31);
        }
        while ( v29 );
        v32 = (unsigned int)(v30 - 2);
        v33 = v58;
        do
        {
          lpVtbl_low = LOWORD(v33->lpVtbl);
          if ( !(_WORD)lpVtbl_low )
            break;
          LODWORD(v8) = lpVtbl_low + v8;
          v33 = (LPMALLOC)((char *)v33 + lpVtbl_low);
        }
        while ( v33 );
        v35 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc((unsigned int)(v8 + v32));
        v36 = v35;
        if ( v35 )
        {
          memset_0(v35, 0, (unsigned int)(v8 + v32));
          memcpy_0(v36, v27, (unsigned int)v32);
          memcpy_0((char *)v36 + v32, v28, (unsigned int)v8);
        }
      }
      else
      {
        v36 = ILClone((LPCITEMIDLIST)pv);
      }
    }
    else
    {
      if ( !v58 )
      {
        *a4 = 0;
        goto LABEL_49;
      }
      v36 = ILClone((LPCITEMIDLIST)v58);
    }
    *a4 = (struct _ITEMIDLIST_ABSOLUTE *)v36;
    if ( !v36 )
    {
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2577,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)0x8007000ELL,
        (int)a4);
LABEL_50:
      v37 = pv;
      pv = 0;
      if ( v37 )
        CoTaskMemFree(v37);
      return (unsigned int)v9;
    }
LABEL_32:
    v25 = pv;
    pv = 0;
    if ( v25 )
      CoTaskMemFree(v25);
    return 0;
  }
  ppMalloc = 0;
  v39 = 1;
  v54 = 1;
  v40 = 0;
  TokenHandle = 0;
  v41 = (const struct _ITEMIDLIST_RELATIVE *)v58;
  v42 = (const ITEMIDLIST *)CFSFolder::_IsValidID((CFSFolder *)v17, (const struct _ITEMIDLIST_RELATIVE *)v58);
  v58 = (LPMALLOC)ILCloneFirst(v42);
  if ( v58 )
  {
    v9 = CFSFolder::_CopyHiddenData(v43, v41, 2, &v58);
    if ( v9 >= 0 )
    {
      if ( (unsigned int)ILIsChild(v41) )
      {
        v40 = v58;
        v48 = 0;
      }
      else
      {
        v48 = v58;
        v9 = SHILCombine(
               (const struct _ITEMIDLIST_ABSOLUTE *)v58,
               (const struct _ITEMIDLIST_RELATIVE *)((char *)v41 + *(unsigned __int16 *)v41),
               &TokenHandle);
        v39 = v54;
        v40 = (IMalloc *)TokenHandle;
      }
      CoTaskMemFree(v48);
    }
  }
  if ( v39 )
  {
    v44 = ppMalloc;
    ppMalloc = v40;
    if ( v44 )
      CoTaskMemFree(v44);
  }
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2572,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v9,
      (int)a4);
    v49 = ppMalloc;
    ppMalloc = 0;
    if ( v49 )
      CoTaskMemFree(v49);
    goto LABEL_50;
  }
  v45 = SHILCombine((const struct _ITEMIDLIST_ABSOLUTE *)pv, (const struct _ITEMIDLIST_RELATIVE *)ppMalloc, a4);
  v46 = v45;
  if ( v45 >= 0 )
  {
    v47 = ppMalloc;
    ppMalloc = 0;
    if ( v47 )
      CoTaskMemFree(v47);
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2573,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v45,
    (int)a4);
  v50 = ppMalloc;
  ppMalloc = 0;
  if ( v50 )
    CoTaskMemFree(v50);
  v51 = pv;
  pv = 0;
  if ( v51 )
    CoTaskMemFree(v51);
  return v46;
}

```

## disassembly

```asm
0x18003fd30  push    rbp
0x18003fd32  push    rbx
0x18003fd33  push    rsi
0x18003fd34  push    rdi
0x18003fd35  push    r12
0x18003fd37  push    r13
0x18003fd39  push    r14
0x18003fd3b  push    r15
0x18003fd3d  mov     rbp, rsp
0x18003fd40  sub     rsp, 78h
0x18003fd44  mov     rax, cs:__security_cookie
0x18003fd4b  xor     rax, rsp
0x18003fd4e  mov     [rbp+var_10], rax
0x18003fd52  mov     [rbp+var_58], r9
0x18003fd56  mov     [rbp+var_20], r8
0x18003fd5a  mov     [rbp+Src], rdx
0x18003fd5e  mov     r14, rcx
0x18003fd61  mov     [rbp+var_38], rcx
0x18003fd65  xor     ecx, ecx
0x18003fd67  mov     [r9], rcx
0x18003fd6a  mov     [rbp+pv], rcx
0x18003fd6e  lea     r12, [rbp+pv]
0x18003fd72  mov     [rbp+var_50], r12
0x18003fd76  mov     [rbp+var_40], 1
0x18003fd7a  mov     ebx, ecx
0x18003fd7c  mov     [rbp+TokenHandle], rcx
0x18003fd80  lea     r13, [r14+1F0h]
0x18003fd87  mov     rax, [r13+0]
0x18003fd8b  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18003fd92  jnz     short loc_18003FD9F
0x18003fd94  mov     rax, [r13+8]
0x18003fd98  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18003fd9f  mov     edi, 2
0x18003fda4  mov     r15d, 8007000Eh
0x18003fdaa  test    rax, rax
0x18003fdad  jnz     loc_18003FF86
0x18003fdb3  mov     esi, 80004005h
0x18003fdb8  mov     r14, [r14+1B8h]
0x18003fdbf  test    r14, r14
0x18003fdc2  jz      loc_18003FE5E
0x18003fdc8  mov     rdx, r14
0x18003fdcb  mov     r8d, edi
0x18003fdce  xchg    ax, ax
0x18003fdd0  movzx   eax, word ptr [rdx]
0x18003fdd3  test    ax, ax
0x18003fdd6  jz      short loc_18003FDE0
0x18003fdd8  add     r8d, eax
0x18003fddb  add     rdx, rax
0x18003fdde  jnz     short loc_18003FDD0
0x18003fde0  mov     esi, r8d
0x18003fde3  mov     ecx, r8d; cb
0x18003fde6  call    cs:__imp_CoTaskMemAlloc
0x18003fdec  mov     rbx, rax
0x18003fdef  test    rax, rax
0x18003fdf2  jz      short loc_18003FE55
0x18003fdf4  xor     r15d, r15d
0x18003fdf7  mov     [rbp+ppMalloc], r15
0x18003fdfb  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x18003fdff  mov     ecx, 1; dwMemContext
0x18003fe04  call    cs:__imp_CoGetMalloc
0x18003fe0a  test    eax, eax
0x18003fe0c  js      short loc_18003FE34
0x18003fe0e  mov     rcx, [rbp+ppMalloc]
0x18003fe12  mov     rax, [rcx]
0x18003fe15  mov     rdx, rbx
0x18003fe18  mov     rax, [rax+30h]
0x18003fe1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe21  mov     r15, rax
0x18003fe24  mov     rcx, [rbp+ppMalloc]
0x18003fe28  mov     rdx, [rcx]
0x18003fe2b  mov     rax, [rdx+10h]
0x18003fe2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe34  mov     r8, r15; Size
0x18003fe37  xor     edx, edx; Val
0x18003fe39  mov     rcx, rbx; void *
0x18003fe3c  call    memset_0
0x18003fe41  mov     r8, rsi; Size
0x18003fe44  mov     rdx, r14; Src
0x18003fe47  mov     rcx, rbx; void *
0x18003fe4a  call    memcpy_0
0x18003fe4f  mov     r15d, 8007000Eh
0x18003fe55  xor     esi, esi
0x18003fe57  test    rbx, rbx
0x18003fe5a  cmovz   esi, r15d
0x18003fe5e  mov     r14, [rbp+var_38]
0x18003fe62  mov     rcx, [r12]; pv
0x18003fe66  mov     [r12], rbx
0x18003fe6a  test    rcx, rcx
0x18003fe6d  jz      short loc_18003FE75
0x18003fe6f  call    cs:__imp_CoTaskMemFree
0x18003fe75  test    esi, esi
0x18003fe77  jns     loc_18003FFB2
0x18003fe7d  mov     rax, [r13+0]
0x18003fe81  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18003fe88  jnz     short loc_18003FE95
0x18003fe8a  mov     rax, [r13+8]
0x18003fe8e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18003fe95  test    rax, rax
0x18003fe98  jnz     loc_18003FF50
0x18003fe9e  cmp     [r14+1B8h], rax
0x18003fea5  jnz     loc_18003FF50
0x18003feab  mov     r14, [rbp+Src]
0x18003feaf  test    r14, r14
0x18003feb2  jz      loc_18004008D
0x18003feb8  mov     rdx, r14
0x18003febb  nop     dword ptr [rax+rax+00h]
0x18003fec0  movzx   ecx, word ptr [rdx]
0x18003fec3  test    cx, cx
0x18003fec6  jz      short loc_18003FECF
0x18003fec8  add     edi, ecx
0x18003feca  add     rdx, rcx
0x18003fecd  jnz     short loc_18003FEC0
0x18003fecf  mov     rcx, rdi; cb
0x18003fed2  call    cs:__imp_CoTaskMemAlloc
0x18003fed8  mov     rbx, rax
0x18003fedb  test    rax, rax
0x18003fede  jz      short loc_18003FF3A
0x18003fee0  xor     esi, esi
0x18003fee2  mov     [rbp+var_20], rsi
0x18003fee6  lea     rdx, [rbp+var_20]; ppMalloc
0x18003feea  mov     ecx, 1; dwMemContext
0x18003feef  call    cs:__imp_CoGetMalloc
0x18003fef5  test    eax, eax
0x18003fef7  js      short loc_18003FF1F
0x18003fef9  mov     rcx, [rbp+var_20]
0x18003fefd  mov     rdx, [rcx]
0x18003ff00  mov     rax, [rdx+30h]
0x18003ff04  mov     rdx, rbx
0x18003ff07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff0c  mov     rsi, rax
0x18003ff0f  mov     rcx, [rbp+var_20]
0x18003ff13  mov     r9, [rcx]
0x18003ff16  mov     rax, [r9+10h]
0x18003ff1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff1f  mov     r8, rsi; Size
0x18003ff22  xor     edx, edx; Val
0x18003ff24  mov     rcx, rbx; void *
0x18003ff27  call    memset_0
0x18003ff2c  mov     r8, rdi; Size
0x18003ff2f  mov     rdx, r14; Src
0x18003ff32  mov     rcx, rbx; void *
0x18003ff35  call    memcpy_0
0x18003ff3a  mov     rax, [rbp+var_58]
0x18003ff3e  mov     [rax], rbx
0x18003ff41  xor     edi, edi
0x18003ff43  test    rbx, rbx
0x18003ff46  cmovz   edi, r15d
0x18003ff4a  jz      loc_18004009D
0x18003ff50  mov     rcx, [rbp+pv]; pv
0x18003ff54  mov     [rbp+pv], 0
0x18003ff5c  test    rcx, rcx
0x18003ff5f  jz      short loc_18003FF67
0x18003ff61  call    cs:__imp_CoTaskMemFree
0x18003ff67  xor     eax, eax
0x18003ff69  mov     rcx, [rbp+var_10]
0x18003ff6d  xor     rcx, rsp; StackCookie
0x18003ff70  call    __security_check_cookie
0x18003ff75  add     rsp, 78h
0x18003ff79  pop     r15
0x18003ff7b  pop     r14
0x18003ff7d  pop     r13
0x18003ff7f  pop     r12
0x18003ff81  pop     rdi
0x18003ff82  pop     rsi
0x18003ff83  pop     rbx
0x18003ff84  pop     rbp
0x18003ff85  retn
0x18003ff86  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003ff8a  xor     r8d, r8d; void *
0x18003ff8d  mov     edx, 1000h; unsigned int
0x18003ff92  mov     rcx, r13; struct _GUID *
0x18003ff95  call    SHGetKnownFolderIDList_Internal
0x18003ff9a  mov     esi, eax
0x18003ff9c  cmp     [rbp+var_40], bl
0x18003ff9f  jz      loc_18003FE75
0x18003ffa5  mov     rbx, [rbp+TokenHandle]
0x18003ffa9  mov     r12, [rbp+var_50]
0x18003ffad  jmp     loc_18003FE62
0x18003ffb2  cmp     qword ptr [r14+268h], 0
0x18003ffba  jnz     loc_1800400D4
0x18003ffc0  mov     r14, [rbp+pv]
0x18003ffc4  mov     r13, [rbp+var_20]
0x18003ffc8  test    r14, r14
0x18003ffcb  jz      loc_180040226
0x18003ffd1  test    r13, r13
0x18003ffd4  jz      loc_180040278
0x18003ffda  mov     rdx, r14
0x18003ffdd  mov     r8d, edi
0x18003ffe0  movzx   ecx, word ptr [rdx]
0x18003ffe3  test    cx, cx
0x18003ffe6  jz      short loc_18003FFF0
0x18003ffe8  add     r8d, ecx
0x18003ffeb  add     rdx, rcx
0x18003ffee  jnz     short loc_18003FFE0
0x18003fff0  lea     r12d, [r8-2]
0x18003fff4  mov     rdx, r13
0x18003fff7  movzx   ecx, word ptr [rdx]
0x18003fffa  test    cx, cx
0x18003fffd  jz      short loc_180040006
0x18003ffff  add     edi, ecx
0x180040001  add     rdx, rcx
0x180040004  jnz     short loc_18003FFF7
0x180040006  lea     eax, [rdi+r12]
0x18004000a  mov     ebx, eax
0x18004000c  mov     ecx, eax; cb
0x18004000e  call    WINRT_IMPL_CoTaskMemAlloc
0x180040013  mov     rsi, rax
0x180040016  test    rax, rax
0x180040019  jz      short loc_180040045
0x18004001b  mov     r8d, ebx; Size
0x18004001e  xor     edx, edx; Val
0x180040020  mov     rcx, rax; void *
0x180040023  call    memset_0
0x180040028  mov     r8d, r12d; Size
0x18004002b  mov     rdx, r14; Src
0x18004002e  mov     rcx, rsi; void *
0x180040031  call    memcpy_0
0x180040036  mov     r8d, edi; Size
0x180040039  lea     rcx, [r12+rsi]; void *
0x18004003d  mov     rdx, r13; Src
0x180040040  call    memcpy_0
0x180040045  mov     rax, [rbp+var_58]
0x180040049  mov     [rax], rsi
0x18004004c  test    rsi, rsi
0x18004004f  jnz     loc_18003FF50
0x180040055  mov     rcx, [rbp+40h]; this
0x180040059  mov     r9d, r15d; char *
0x18004005c  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180040063  mov     edx, 2577h; void *
0x180040068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004006d  nop
0x18004006e  mov     rcx, [rbp+pv]; pv
0x180040072  mov     [rbp+pv], 0
0x18004007a  test    rcx, rcx
0x18004007d  jz      short loc_180040085
0x18004007f  call    cs:__imp_CoTaskMemFree
0x180040085  mov     eax, r15d
0x180040088  jmp     loc_18003FF69
0x18004008d  mov     rax, [rbp+var_58]
0x180040091  mov     qword ptr [rax], 0
0x180040098  mov     edi, 80070057h
0x18004009d  mov     rcx, [rbp+40h]; this
0x1800400a1  mov     r9d, edi; char *
0x1800400a4  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800400ab  mov     edx, 257Fh; void *
0x1800400b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800400b5  nop
0x1800400b6  mov     rcx, [rbp+pv]; pv
0x1800400ba  mov     [rbp+pv], 0
0x1800400c2  test    rcx, rcx
0x1800400c5  jz      short loc_1800400CD
0x1800400c7  call    cs:__imp_CoTaskMemFree
0x1800400cd  mov     eax, edi
0x1800400cf  jmp     loc_18003FF69
0x1800400d4  mov     [rbp+ppMalloc], 0
0x1800400dc  lea     rsi, [rbp+ppMalloc]
0x1800400e0  mov     [rbp+var_50], rsi
0x1800400e4  mov     r14b, 1
0x1800400e7  mov     [rbp+var_40], r14b
0x1800400eb  xor     ebx, ebx
0x1800400ed  mov     [rbp+TokenHandle], rbx
0x1800400f1  mov     r13, [rbp+var_20]
0x1800400f5  mov     rdx, r13; struct _ITEMIDLIST_RELATIVE *
0x1800400f8  call    ?_IsValidID@CFSFolder@@IEAAPEFBUIDFOLDER@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CFSFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x1800400fd  mov     rcx, rax; pidl
0x180040100  call    ILCloneFirst
0x180040105  mov     [rbp+var_20], rax
0x180040109  test    rax, rax
0x18004010c  jnz     short loc_180040164
0x18004010e  test    r14b, r14b
0x180040111  jz      short loc_180040124
0x180040113  mov     rcx, [rsi]; pv
0x180040116  mov     [rsi], rbx
0x180040119  test    rcx, rcx
0x18004011c  jz      short loc_180040124
0x18004011e  call    cs:__imp_CoTaskMemFree
0x180040124  test    r15d, r15d
0x180040127  js      short loc_18004019E
0x180040129  mov     r8, [rbp+var_58]; struct _ITEMIDLIST_ABSOLUTE **
0x18004012d  mov     rdx, [rbp+ppMalloc]; struct _ITEMIDLIST_RELATIVE *
0x180040131  mov     rcx, [rbp+pv]; Src
0x180040135  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18004013a  mov     ebx, eax
0x18004013c  test    eax, eax
0x18004013e  js      loc_1800401D7
0x180040144  mov     rcx, [rbp+ppMalloc]; pv
0x180040148  mov     [rbp+ppMalloc], 0
0x180040150  test    rcx, rcx
0x180040153  jz      loc_18003FF50
0x180040159  call    cs:__imp_CoTaskMemFree
0x18004015f  jmp     loc_18003FF50
0x180040164  lea     r9, [rbp+var_20]
0x180040168  mov     r8d, edi
0x18004016b  mov     rdx, r13
0x18004016e  call    ?_CopyHiddenData@CFSFolder@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@W4CREATE_IDLIST_FLAGS@@PEAPEAU_ITEMID_CHILD@@@Z; CFSFolder::_CopyHiddenData(_ITEMIDLIST_RELATIVE const *,CREATE_IDLIST_FLAGS,_ITEMID_CHILD * *)
0x180040173  mov     r15d, eax
0x180040176  test    eax, eax
0x180040178  js      short loc_18004010E
0x18004017a  mov     rcx, r13; struct _ITEMIDLIST_RELATIVE *
0x18004017d  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
  ... truncated ...
```
