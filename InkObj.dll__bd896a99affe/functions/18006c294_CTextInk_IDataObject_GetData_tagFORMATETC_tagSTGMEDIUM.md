# CTextInk::IDataObject_GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18006c294`
- end: `0x18006c7bc`
- name: `?IDataObject_GetData@CTextInk@@QEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `1320`
- prototype: `__int64 __fastcall(CTextInk *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054540`

## callees

- `0x180044ac6`
- `0x18005ec60`
- `0x18006b88c`
- `0x18006baa0`
- `0x18006c294`
- `0x180104ece`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006c3ff`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006c457`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006c6d9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006c3ff`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006c457`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18006c6d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006c41b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006c473`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006c6fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006c41b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006c473`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006c6fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006c481`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006c71a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006c481`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006c71a`
- `USER32!RegisterClipboardFormatW` at `0x18006c353`
- `USER32!RegisterClipboardFormatW` at `0x18006c379`
- `USER32!RegisterClipboardFormatW` at `0x18006c5b9`
- `USER32!RegisterClipboardFormatW` at `0x18006c5ef`
- `USER32!RegisterClipboardFormatW` at `0x18006c353`
- `USER32!RegisterClipboardFormatW` at `0x18006c379`
- `USER32!RegisterClipboardFormatW` at `0x18006c5b9`
- `USER32!RegisterClipboardFormatW` at `0x18006c5ef`
- `GDI32!DeleteMetaFile` at `0x18006c6ea`
- `GDI32!DeleteMetaFile` at `0x18006c6ea`
- `GDI32!CloseMetaFile` at `0x18006c6b7`
- `GDI32!CloseMetaFile` at `0x18006c6b7`
- `GDI32!RestoreDC` at `0x18006c695`
- `GDI32!RestoreDC` at `0x18006c695`
- `GDI32!SaveDC` at `0x18006c664`
- `GDI32!SaveDC` at `0x18006c664`
- `GDI32!CreateMetaFileW` at `0x18006c560`
- `GDI32!CreateMetaFileW` at `0x18006c560`
- `GDI32!CreateEnhMetaFileW` at `0x18006c59e`
- `GDI32!CreateEnhMetaFileW` at `0x18006c59e`
- `GDI32!CloseEnhMetaFile` at `0x18006c73b`
- `GDI32!CloseEnhMetaFile` at `0x18006c73b`
- `GDI32!CopyEnhMetaFileW` at `0x18006c755`
- `GDI32!CopyEnhMetaFileW` at `0x18006c755`
- `GDI32!DeleteEnhMetaFile` at `0x18006c766`
- `GDI32!DeleteEnhMetaFile` at `0x18006c766`
- `ole32!WriteClassStg` at `0x18006c61e`
- `ole32!WriteClassStg` at `0x18006c61e`

## string_xrefs

- `0x18006c372`: `Object Descriptor`
- `0x18006c5b2`: `Object Descriptor`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
HRESULT __fastcall CTextInk::IDataObject_GetData(const void ***this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  HRESULT result; // eax
  int cfFormat; // edi
  UINT v8; // eax
  UINT v9; // eax
  unsigned __int64 v10; // rcx
  HBITMAP v11; // rax
  void *v12; // rbx
  void *v13; // rcx
  HBITMAP v14; // rax
  _WORD *v15; // rax
  const void **v16; // rbx
  __int64 v17; // rcx
  HDC MetaFileW; // rax
  int v19; // edi
  HBITMAP Descriptor; // rax
  int v21; // edi
  unsigned int v22; // edx
  CTextInk *v23; // rcx
  IStorage *StorageOnHGlobal; // rax
  HBITMAP v25; // rdi
  HMETAFILE v26; // rsi
  HBITMAP v27; // rax
  HBITMAP v28; // rdi
  _QWORD *v29; // rax
  HENHMETAFILE v30; // rax
  HENHMETAFILE v31; // rbx
  HBITMAP v32; // rcx
  _DWORD v33[4]; // [rsp+30h] [rbp-C8h] BYREF
  __int128 v34; // [rsp+40h] [rbp-B8h]
  HDC hdc; // [rsp+50h] [rbp-A8h]
  RECT *v36; // [rsp+58h] [rbp-A0h]
  RECT *v37; // [rsp+60h] [rbp-98h]
  int v38; // [rsp+68h] [rbp-90h]
  int v39; // [rsp+70h] [rbp-88h]
  RECT v40; // [rsp+90h] [rbp-68h] BYREF
  RECT rc; // [rsp+A0h] [rbp-58h] BYREF

  if ( !a2 || !a3 )
    return -2147467261;
  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  if ( a2->tymed == 1 )
  {
    v9 = RegisterClipboardFormatW(L"Object Descriptor");
    cfFormat = a2->cfFormat;
    if ( cfFormat != v9 )
    {
      if ( (_WORD)cfFormat != 13 )
        return -2147221404;
      goto LABEL_21;
    }
  }
  else
  {
    if ( a2->tymed != 8 )
    {
      if ( a2->tymed == 32 )
      {
        if ( a2->cfFormat != 3 )
          return -2147221404;
        LOWORD(cfFormat) = 3;
      }
      else
      {
        if ( a2->tymed != 64 )
          return -2147221404;
        if ( a2->cfFormat != 14 )
          return -2147221404;
        LOWORD(cfFormat) = 14;
      }
      goto LABEL_35;
    }
    v8 = RegisterClipboardFormatW(L"Embed Source");
    cfFormat = a2->cfFormat;
    if ( cfFormat != v8 || a2->dwAspect != 1 )
      return -2147221404;
  }
  if ( (_WORD)cfFormat == 13 )
  {
LABEL_21:
    if ( *((_DWORD *)this + 119) && this[61] && this[60] )
    {
      a3->tymed = 1;
      v10 = 2LL * *(unsigned int *)this[60] + 2;
      if ( v10 > 0xFFFFFFFF )
        return -2147418113;
      v11 = (HBITMAP)GlobalAlloc(0x42u, (unsigned int)v10);
      a3->hBitmap = v11;
      if ( !v11 )
        return -2147024882;
      v12 = GlobalLock(v11);
      memcpy_0(v12, *this[61], 2LL * *(unsigned int *)this[60]);
      v13 = v12;
    }
    else
    {
      a3->tymed = 1;
      v14 = (HBITMAP)GlobalAlloc(0x42u, 2u);
      a3->hBitmap = v14;
      if ( !v14 )
        return -2147024882;
      v15 = GlobalLock(v14);
      *v15 = 0;
      v13 = v15;
    }
    if ( GlobalUnlock(v13) )
      return 0;
    else
      return -2147418113;
  }
LABEL_35:
  if ( ((_DWORD)this[14] & 0x1000) != 0 )
    v16 = this[8];
  else
    v16 = this[9];
  v17 = *(__int64 *)((char *)this + (-(__int64)(((_DWORD)this[14] & 0x1000) != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 72);
  *(_QWORD *)&v40.left = 0;
  *(_QWORD *)&v40.right = __PAIR64__(HIDWORD(v17), (unsigned int)v16);
  memset_0(v33, 0, 0x58u);
  v33[0] = 88;
  v33[1] = 1;
  v33[2] = -1;
  v34 = 0;
  v36 = &v40;
  v37 = &v40;
  v38 = 1;
  v39 = 1;
  if ( (_WORD)cfFormat == 3 )
  {
    *((_WORD *)this + 286) = 1;
    *((_BYTE *)this + 574) = 0;
    MetaFileW = CreateMetaFileW(0);
LABEL_42:
    hdc = MetaFileW;
    goto LABEL_53;
  }
  if ( (_WORD)cfFormat == 14 )
  {
    *((_WORD *)this + 286) = 256;
    *((_BYTE *)this + 574) = 0;
    rc = v40;
    MetaFileW = CreateEnhMetaFileW(0, 0, &rc, 0);
    goto LABEL_42;
  }
  v19 = a2->cfFormat;
  if ( v19 == RegisterClipboardFormatW(L"Object Descriptor") )
  {
    Descriptor = (HBITMAP)CTextInk::CreateDescriptor((CTextInk *)this, a2->dwAspect);
    if ( !Descriptor )
      return -2147467259;
    a3->hBitmap = Descriptor;
    goto LABEL_52;
  }
  v21 = a2->cfFormat;
  if ( v21 != RegisterClipboardFormatW(L"Embed Source") )
    return -2147221404;
  StorageOnHGlobal = CTextInk::CreateStorageOnHGlobal(v23, v22);
  v25 = (HBITMAP)StorageOnHGlobal;
  if ( !StorageOnHGlobal )
    return -2147418113;
  result = WriteClassStg(StorageOnHGlobal, &CLSID_Ink);
  if ( result >= 0 )
  {
    ATL::IPersistStorageImpl<CTextInk>::Save(this + 30, v25, 0);
    (*(void (__fastcall **)(HBITMAP, _QWORD))(*(_QWORD *)v25 + 72LL))(v25, 0);
    a3->hBitmap = v25;
LABEL_52:
    MetaFileW = hdc;
LABEL_53:
    if ( MetaFileW )
    {
      if ( !SaveDC(MetaFileW) )
        return -2147418113;
      ((void (__fastcall *)(char *, _DWORD *))this[1][2])((char *)this + 8, v33);
      if ( !RestoreDC(hdc, -1) )
        return -2147418113;
      if ( *((_BYTE *)this + 572) )
      {
        v26 = CloseMetaFile(hdc);
        if ( !v26 )
          return -2147418113;
        v27 = (HBITMAP)GlobalAlloc(0x2002u, 0x18u);
        v28 = v27;
        if ( !v27 )
        {
          DeleteMetaFile(v26);
          return -2147286928;
        }
        v29 = GlobalLock(v27);
        v29[2] = v26;
        *(_DWORD *)v29 = 8;
        *(_QWORD *)((char *)v29 + 4) = v16;
        GlobalUnlock(v28);
        a3->tymed = 32;
        a3->hBitmap = v28;
LABEL_70:
        a3->pUnkForRelease = 0;
        return 0;
      }
      if ( *((_BYTE *)this + 573) )
      {
        v30 = CloseEnhMetaFile(hdc);
        v31 = v30;
        if ( !v30 )
          return -2147418113;
        v32 = (HBITMAP)CopyEnhMetaFileW(v30, 0);
        if ( !v32 )
        {
          DeleteEnhMetaFile(v31);
          return -2147286928;
        }
        a3->tymed = a2->tymed;
        a3->hBitmap = v32;
        goto LABEL_70;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18006c294  push    rbx
0x18006c296  push    rsi
0x18006c297  push    rdi
0x18006c298  push    r12
0x18006c29a  push    r13
0x18006c29c  push    r14
0x18006c29e  push    r15
0x18006c2a0  sub     rsp, 0C0h
0x18006c2a7  mov     rax, cs:__security_cookie
0x18006c2ae  xor     rax, rsp
0x18006c2b1  mov     [rsp+0F8h+var_48], rax
0x18006c2b9  mov     r14, r8
0x18006c2bc  mov     r15, rdx
0x18006c2bf  mov     rsi, rcx
0x18006c2c2  xor     r12d, r12d
0x18006c2c5  test    rdx, rdx
0x18006c2c8  jz      loc_18006C793
0x18006c2ce  test    r8, r8
0x18006c2d1  jz      loc_18006C793
0x18006c2d7  xorps   xmm0, xmm0
0x18006c2da  xor     eax, eax
0x18006c2dc  movups  xmmword ptr [r8], xmm0
0x18006c2e0  mov     [r8+10h], rax
0x18006c2e4  mov     ecx, [rdx+18h]
0x18006c2e7  sub     ecx, 1
0x18006c2ea  jz      loc_18006C372
0x18006c2f0  sub     ecx, 7
0x18006c2f3  jz      short loc_18006C34C
0x18006c2f5  sub     ecx, 18h
0x18006c2f8  jz      short loc_18006C328
0x18006c2fa  cmp     ecx, 20h ; ' '
0x18006c2fd  jz      short loc_18006C309
0x18006c2ff  mov     eax, 80040064h
0x18006c304  jmp     loc_18006C798
0x18006c309  mov     r12d, 0Eh
0x18006c30f  cmp     r12w, [rdx]
0x18006c313  jz      short loc_18006C31F
0x18006c315  mov     eax, 80040064h
0x18006c31a  jmp     loc_18006C798
0x18006c31f  movzx   edi, r12w
0x18006c323  jmp     loc_18006C4A2
0x18006c328  mov     r13d, 3
0x18006c32e  cmp     r13w, [rdx]
0x18006c332  jz      short loc_18006C33E
0x18006c334  mov     eax, 80040064h
0x18006c339  jmp     loc_18006C798
0x18006c33e  mov     edi, r13d
0x18006c341  mov     r12d, 0Eh
0x18006c347  jmp     loc_18006C4A8
0x18006c34c  lea     rcx, aEmbedSource; "Embed Source"
0x18006c353  call    cs:__imp_RegisterClipboardFormatW
0x18006c359  movzx   edi, word ptr [r15]
0x18006c35d  cmp     edi, eax
0x18006c35f  jnz     short loc_18006C368
0x18006c361  cmp     dword ptr [r15+10h], 1
0x18006c366  jz      short loc_18006C39B
0x18006c368  mov     eax, 80040064h
0x18006c36d  jmp     loc_18006C798
0x18006c372  lea     rcx, aObjectDescript; "Object Descriptor"
0x18006c379  call    cs:__imp_RegisterClipboardFormatW
0x18006c37f  movzx   edi, word ptr [r15]
0x18006c383  cmp     edi, eax
0x18006c385  jz      short loc_18006C39B
0x18006c387  mov     eax, 0Dh
0x18006c38c  cmp     di, ax
0x18006c38f  jz      short loc_18006C3A9
0x18006c391  mov     eax, 80040064h
0x18006c396  jmp     loc_18006C798
0x18006c39b  mov     eax, 0Dh
0x18006c3a0  cmp     ax, di
0x18006c3a3  jnz     loc_18006C49C
0x18006c3a9  cmp     [rsi+1DCh], r12d
0x18006c3b0  jz      loc_18006C448
0x18006c3b6  cmp     [rsi+1E8h], r12
0x18006c3bd  jz      loc_18006C448
0x18006c3c3  cmp     [rsi+1E0h], r12
0x18006c3ca  jz      short loc_18006C448
0x18006c3cc  mov     dword ptr [r14], 1
0x18006c3d3  mov     rax, [rsi+1E0h]
0x18006c3da  mov     ecx, [rax]
0x18006c3dc  lea     rcx, ds:2[rcx*2]
0x18006c3e4  mov     eax, 0FFFFFFFFh
0x18006c3e9  cmp     rcx, rax
0x18006c3ec  jbe     short loc_18006C3F8
0x18006c3ee  mov     eax, 8000FFFFh
0x18006c3f3  jmp     loc_18006C798
0x18006c3f8  mov     edx, ecx; dwBytes
0x18006c3fa  mov     ecx, 42h ; 'B'; uFlags
0x18006c3ff  call    cs:__imp_GlobalAlloc
0x18006c405  mov     [r14+8], rax
0x18006c409  test    rax, rax
0x18006c40c  jnz     short loc_18006C418
0x18006c40e  mov     eax, 8007000Eh
0x18006c413  jmp     loc_18006C798
0x18006c418  mov     rcx, rax; hMem
0x18006c41b  call    cs:__imp_GlobalLock
0x18006c421  mov     rbx, rax
0x18006c424  mov     rcx, [rsi+1E0h]
0x18006c42b  mov     r8d, [rcx]
0x18006c42e  add     r8, r8; Size
0x18006c431  mov     rdx, [rsi+1E8h]
0x18006c438  mov     rdx, [rdx]; Src
0x18006c43b  mov     rcx, rax; void *
0x18006c43e  call    memcpy_0
0x18006c443  mov     rcx, rbx
0x18006c446  jmp     short loc_18006C481
0x18006c448  mov     dword ptr [r14], 1
0x18006c44f  mov     edx, 2; dwBytes
0x18006c454  lea     ecx, [rdx+40h]; uFlags
0x18006c457  call    cs:__imp_GlobalAlloc
0x18006c45d  mov     [r14+8], rax
0x18006c461  test    rax, rax
0x18006c464  jnz     short loc_18006C470
0x18006c466  mov     eax, 8007000Eh
0x18006c46b  jmp     loc_18006C798
0x18006c470  mov     rcx, rax; hMem
0x18006c473  call    cs:__imp_GlobalLock
0x18006c479  xor     ecx, ecx
0x18006c47b  mov     [rax], cx
0x18006c47e  mov     rcx, rax; hMem
0x18006c481  call    cs:__imp_GlobalUnlock
0x18006c487  test    eax, eax
0x18006c489  jnz     short loc_18006C495
0x18006c48b  mov     eax, 8000FFFFh
0x18006c490  jmp     loc_18006C798
0x18006c495  xor     eax, eax
0x18006c497  jmp     loc_18006C798
0x18006c49c  mov     r12d, 0Eh
0x18006c4a2  mov     r13d, 3
0x18006c4a8  mov     eax, [rsi+70h]
0x18006c4ab  and     eax, 1000h
0x18006c4b0  jz      short loc_18006C4B8
0x18006c4b2  mov     rbx, [rsi+40h]
0x18006c4b6  jmp     short loc_18006C4BC
0x18006c4b8  mov     rbx, [rsi+48h]
0x18006c4bc  mov     [rsp+0F8h+var_D8], rbx
0x18006c4c1  neg     eax
0x18006c4c3  sbb     rax, rax
0x18006c4c6  and     rax, 0FFFFFFFFFFFFFFF8h
0x18006c4ca  mov     rcx, [rax+rsi+48h]
0x18006c4cf  mov     qword ptr [rsp+0F8h+var_68], 0
0x18006c4db  mov     dword ptr [rsp+0F8h+var_68+8], ebx
0x18006c4e2  shr     rcx, 20h
0x18006c4e6  mov     dword ptr [rsp+0F8h+var_68+0Ch], ecx
0x18006c4ed  xor     edx, edx; Val
0x18006c4ef  lea     r8d, [rdx+58h]; Size
0x18006c4f3  lea     rcx, [rsp+0F8h+var_C8]; void *
0x18006c4f8  call    memset_0
0x18006c4fd  mov     [rsp+0F8h+var_C8], 58h ; 'X'
0x18006c505  mov     [rsp+0F8h+var_C4], 1
0x18006c50d  mov     [rsp+0F8h+var_C0], 0FFFFFFFFh
0x18006c515  xorps   xmm0, xmm0
0x18006c518  movdqa  [rsp+0F8h+var_B8], xmm0
0x18006c51e  lea     rax, [rsp+0F8h+var_68]
0x18006c526  mov     [rsp+0F8h+var_A0], rax
0x18006c52b  lea     rax, [rsp+0F8h+var_68]
0x18006c533  mov     [rsp+0F8h+var_98], rax
0x18006c538  mov     [rsp+0F8h+var_90], 1
0x18006c540  mov     [rsp+0F8h+var_88], 1
0x18006c548  cmp     r13w, di
0x18006c54c  jnz     short loc_18006C568
0x18006c54e  mov     word ptr [rsi+23Ch], 1
0x18006c557  mov     byte ptr [rsi+23Eh], 0
0x18006c55e  xor     ecx, ecx; pszFile
0x18006c560  call    cs:__imp_CreateMetaFileW
0x18006c566  jmp     short loc_18006C5A4
0x18006c568  cmp     r12w, di
0x18006c56c  jnz     short loc_18006C5AE
0x18006c56e  mov     word ptr [rsi+23Ch], 100h
0x18006c577  mov     byte ptr [rsi+23Eh], 0
0x18006c57e  movaps  xmm0, [rsp+0F8h+var_68]
0x18006c586  movdqa  xmmword ptr [rsp+0F8h+rc.left], xmm0
0x18006c58f  xor     r9d, r9d; lpDesc
0x18006c592  lea     r8, [rsp+0F8h+rc]; lprc
0x18006c59a  xor     edx, edx; lpFilename
0x18006c59c  xor     ecx, ecx; hdc
0x18006c59e  call    cs:__imp_CreateEnhMetaFileW
0x18006c5a4  mov     [rsp+0F8h+hdc], rax
0x18006c5a9  jmp     loc_18006C658
0x18006c5ae  movzx   edi, word ptr [r15]
0x18006c5b2  lea     rcx, aObjectDescript; "Object Descriptor"
0x18006c5b9  call    cs:__imp_RegisterClipboardFormatW
0x18006c5bf  cmp     edi, eax
0x18006c5c1  jnz     short loc_18006C5E4
0x18006c5c3  mov     edx, [r15+10h]; unsigned int
0x18006c5c7  mov     rcx, rsi; this
0x18006c5ca  call    ?CreateDescriptor@CTextInk@@IEAAPEAXK@Z; CTextInk::CreateDescriptor(ulong)
0x18006c5cf  test    rax, rax
0x18006c5d2  jnz     short loc_18006C5DE
0x18006c5d4  mov     eax, 80004005h
0x18006c5d9  jmp     loc_18006C798
0x18006c5de  mov     [r14+8], rax
0x18006c5e2  jmp     short loc_18006C653
0x18006c5e4  movzx   edi, word ptr [r15]
0x18006c5e8  lea     rcx, aEmbedSource; "Embed Source"
0x18006c5ef  call    cs:__imp_RegisterClipboardFormatW
0x18006c5f5  cmp     edi, eax
0x18006c5f7  jnz     loc_18006C788
0x18006c5fd  call    ?CreateStorageOnHGlobal@CTextInk@@IEAAPEAUIStorage@@K@Z; CTextInk::CreateStorageOnHGlobal(ulong)
0x18006c602  mov     rdi, rax
0x18006c605  test    rax, rax
0x18006c608  jnz     short loc_18006C614
0x18006c60a  mov     eax, 8000FFFFh
0x18006c60f  jmp     loc_18006C798
0x18006c614  lea     rdx, CLSID_Ink; rclsid
0x18006c61b  mov     rcx, rdi; pStg
0x18006c61e  call    cs:__imp_WriteClassStg
0x18006c624  test    eax, eax
0x18006c626  js      loc_18006C798
0x18006c62c  lea     rcx, [rsi+0F0h]
0x18006c633  xor     r8d, r8d
0x18006c636  mov     rdx, rdi
0x18006c639  call    ?Save@?$IPersistStorageImpl@VCTextInk@@@ATL@@UEAAJPEAUIStorage@@H@Z; ATL::IPersistStorageImpl<CTextInk>::Save(IStorage *,int)
0x18006c63e  mov     rax, [rdi]
0x18006c641  xor     edx, edx
0x18006c643  mov     rcx, rdi
0x18006c646  mov     rax, [rax+48h]
0x18006c64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c64f  mov     [r14+8], rdi
0x18006c653  mov     rax, [rsp+0F8h+hdc]
0x18006c658  test    rax, rax
0x18006c65b  jz      loc_18006C786
0x18006c661  mov     rcx, rax; hdc
0x18006c664  call    cs:__imp_SaveDC
0x18006c66a  test    eax, eax
0x18006c66c  jnz     short loc_18006C678
0x18006c66e  mov     eax, 8000FFFFh
0x18006c673  jmp     loc_18006C798
0x18006c678  lea     rcx, [rsi+8]
0x18006c67c  mov     rax, [rcx]
0x18006c67f  lea     rdx, [rsp+0F8h+var_C8]
0x18006c684  mov     rax, [rax+10h]
0x18006c688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c68d  or      edx, 0FFFFFFFFh; nSavedDC
0x18006c690  mov     rcx, [rsp+0F8h+hdc]; hdc
0x18006c695  call    cs:__imp_RestoreDC
0x18006c69b  test    eax, eax
0x18006c69d  jnz     short loc_18006C6A9
0x18006c69f  mov     eax, 8000FFFFh
0x18006c6a4  jmp     loc_18006C798
0x18006c6a9  cmp     byte ptr [rsi+23Ch], 0
0x18006c6b0  jz      short loc_18006C72D
0x18006c6b2  mov     rcx, [rsp+0F8h+hdc]; hdc
0x18006c6b7  call    cs:__imp_CloseMetaFile
0x18006c6bd  mov     rsi, rax
0x18006c6c0  test    rax, rax
0x18006c6c3  jnz     short loc_18006C6CF
0x18006c6c5  mov     eax, 8000FFFFh
0x18006c6ca  jmp     loc_18006C798
0x18006c6cf  mov     edx, 18h; dwBytes
0x18006c6d4  mov     ecx, 2002h; uFlags
0x18006c6d9  call    cs:__imp_GlobalAlloc
0x18006c6df  mov     rdi, rax
0x18006c6e2  test    rax, rax
0x18006c6e5  jnz     short loc_18006C6FA
0x18006c6e7  mov     rcx, rsi; hmf
0x18006c6ea  call    cs:__imp_DeleteMetaFile
0x18006c6f0  mov     eax, 80030070h
0x18006c6f5  jmp     loc_18006C798
0x18006c6fa  mov     rcx, rdi; hMem
0x18006c6fd  call    cs:__imp_GlobalLock
0x18006c703  mov     [rax+10h], rsi
0x18006c707  mov     dword ptr [rax], 8
0x18006c70d  mov     [rax+4], ebx
0x18006c710  mov     ecx, dword ptr [rsp+0F8h+var_D8+4]
0x18006c714  mov     [rax+8], ecx
0x18006c717  mov     rcx, rdi; hMem
0x18006c71a  call    cs:__imp_GlobalUnlock
0x18006c720  mov     dword ptr [r14], 20h ; ' '
0x18006c727  mov     [r14+8], rdi
0x18006c72b  jmp     short loc_18006C77E
0x18006c72d  cmp     byte ptr [rsi+23Dh], 0
0x18006c734  jz      short loc_18006C786
0x18006c736  mov     rcx, [rsp+0F8h+hdc]; hdc
0x18006c73b  call    cs:__imp_CloseEnhMetaFile
0x18006c741  mov     rbx, rax
0x18006c744  test    rax, rax
0x18006c747  jnz     short loc_18006C750
0x18006c749  mov     eax, 8000FFFFh
0x18006c74e  jmp     short loc_18006C798
0x18006c750  xor     edx, edx; lpFileName
0x18006c752  mov     rcx, rbx; hEnh
0x18006c755  call    cs:__imp_CopyEnhMetaFileW
0x18006c75b  mov     rcx, rax
0x18006c75e  test    rax, rax
0x18006c761  jnz     short loc_18006C773
0x18006c763  mov     rcx, rbx; hmf
0x18006c766  call    cs:__imp_DeleteEnhMetaFile
0x18006c76c  mov     eax, 80030070h
0x18006c771  jmp     short loc_18006C798
0x18006c773  mov     eax, [r15+18h]
0x18006c777  mov     [r14], eax
0x18006c77a  mov     [r14+8], rcx
0x18006c77e  mov     qword ptr [r14+10h], 0
0x18006c786  jmp     short loc_18006C78F
0x18006c788  mov     eax, 80040064h
0x18006c78d  jmp     short loc_18006C798
0x18006c78f  xor     eax, eax
0x18006c791  jmp     short loc_18006C798
0x18006c793  mov     eax, 80004003h
  ... truncated ...
```
