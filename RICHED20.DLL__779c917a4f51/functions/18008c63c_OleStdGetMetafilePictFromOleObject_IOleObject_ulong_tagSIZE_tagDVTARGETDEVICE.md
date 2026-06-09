# OleStdGetMetafilePictFromOleObject(IOleObject *,ulong,tagSIZE *,tagDVTARGETDEVICE *)

- ea: `0x18008c63c`
- end: `0x18008c8d6`
- name: `?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@KPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@@Z`
- size: `666`
- prototype: `void *__fastcall(struct IOleObject *, unsigned int, struct tagSIZE *, struct tagDVTARGETDEVICE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005a618`
- `0x18007d7bc`

## callees

- `0x18008c63c`
- `0x18008fd94`
- `0x180090508`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18008c899`
- `KERNEL32!GlobalAlloc` at `0x18008c899`
- `KERNEL32!GlobalLock` at `0x18008c8aa`
- `KERNEL32!GlobalLock` at `0x18008c8aa`
- `KERNEL32!GlobalUnlock` at `0x18008c8ce`
- `KERNEL32!GlobalUnlock` at `0x18008c8ce`
- `GDI32!DeleteMetaFile` at `0x18008c863`
- `GDI32!DeleteMetaFile` at `0x18008c863`
- `GDI32!SetWindowExtEx` at `0x18008c7f0`
- `GDI32!SetWindowExtEx` at `0x18008c7f0`
- `GDI32!SetWindowOrgEx` at `0x18008c7de`
- `GDI32!SetWindowOrgEx` at `0x18008c7de`
- `GDI32!CreateMetaFileA` at `0x18008c7b9`
- `GDI32!CreateMetaFileA` at `0x18008c7b9`
- `GDI32!CloseMetaFile` at `0x18008c850`
- `GDI32!CloseMetaFile` at `0x18008c850`

## pseudocode

```c
void *__fastcall OleStdGetMetafilePictFromOleObject(
        struct IOleObject *a1,
        unsigned int a2,
        struct tagSIZE *a3,
        struct tagDVTARGETDEVICE *a4)
{
  struct IOleObjectVtbl *lpVtbl; // rax
  void *v8; // rbx
  HRESULT (__stdcall *QueryInterface)(IOleObject *, const IID *const, void **); // rax
  unsigned __int16 v10; // dx
  unsigned int v11; // r8d
  HDC MetaFileA; // rax
  int v14; // edi
  int v15; // ebx
  HDC v16; // rsi
  int v17; // ebx
  HMETAFILE v18; // rdi
  HGLOBAL v19; // rax
  _QWORD *v20; // rax
  int x[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v22; // [rsp+68h] [rbp-41h] BYREF
  __int64 v23; // [rsp+70h] [rbp-39h] BYREF
  __int64 v24; // [rsp+78h] [rbp-31h] BYREF
  struct tagPOINT pt; // [rsp+80h] [rbp-29h] BYREF
  tagSIZE sz; // [rsp+88h] [rbp-21h] BYREF
  __int128 v27; // [rsp+90h] [rbp-19h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-9h]
  struct tagSTGMEDIUM v29; // [rsp+B0h] [rbp+7h] BYREF
  __int128 v30; // [rsp+C8h] [rbp+1Fh] BYREF

  v28 = 0;
  v27 = 0;
  LODWORD(v28) = a2;
  LOWORD(v27) = 3;
  v22 = 0;
  lpVtbl = a1->lpVtbl;
  v30 = 0;
  *(_QWORD *)x = 0;
  v8 = 0;
  sz = 0;
  QueryInterface = lpVtbl->QueryInterface;
  pt = 0;
  v24 = 0;
  v23 = 0;
  *(_QWORD *)((char *)&v28 + 4) = 0x20FFFFFFFFLL;
  memset(&v29, 0, sizeof(v29));
  if ( !((unsigned int (__fastcall *)(struct IOleObject *, GUID *, __int64 *, struct tagDVTARGETDEVICE *))QueryInterface)(
          a1,
          &IID_IOleCache,
          &v24,
          a4)
    && !(**(unsigned int (__fastcall ***)(__int64, GUID *, __int64 *))v24)(v24, &IID_IDataObject, &v23)
    && !(*(unsigned int (__fastcall **)(__int64, __int128 *, struct tagSTGMEDIUM *))(*(_QWORD *)v23 + 24LL))(
          v23,
          &v27,
          &v29) )
  {
    v8 = CW32System::OleDuplicateData(v29.hBitmap, v10, v11);
    CW32System::ReleaseStgMedium(&v29);
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v8 )
    return v8;
  if ( ((__int64 (__fastcall *)(struct IOleObject *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IViewObject2,
         &v22) )
  {
    return 0;
  }
  if ( a3 )
  {
    *(struct tagSIZE *)x = *a3;
  }
  else if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)v22 + 72LL))(
              v22,
              a2,
              0xFFFFFFFFLL,
              0,
              x) )
  {
    *(_QWORD *)x = 0;
  }
  MetaFileA = CreateMetaFileA(0);
  v14 = x[0];
  v15 = x[1];
  *(_QWORD *)&v30 = 0;
  *((_QWORD *)&v30 + 1) = *(_QWORD *)x;
  v16 = MetaFileA;
  SetWindowOrgEx(MetaFileA, 0, 0, &pt);
  SetWindowExtEx(v16, v14, v15, &sz);
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, HDC, __int128 *, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v22 + 24LL))(
          v22,
          a2,
          0xFFFFFFFFLL,
          0,
          0,
          0,
          v16,
          &v30,
          &v30,
          0,
          0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v18 = CloseMetaFile(v16);
  if ( v17 )
  {
    v8 = 0;
  }
  else
  {
    v19 = GlobalAlloc(0x2042u, 0x18u);
    v8 = v19;
    if ( v19 )
    {
      v20 = GlobalLock(v19);
      if ( v20 )
      {
        v20[2] = v18;
        *((_DWORD *)v20 + 1) = x[0];
        *((_DWORD *)v20 + 2) = x[1];
        *(_DWORD *)v20 = 8;
        GlobalUnlock(v8);
      }
      return v8;
    }
  }
  DeleteMetaFile(v18);
  return v8;
}

```

## disassembly

```asm
0x18008c63c  mov     [rsp-8+arg_18], rbx
0x18008c641  push    rbp
0x18008c642  push    rsi
0x18008c643  push    rdi
0x18008c644  push    r14
0x18008c646  push    r15
0x18008c648  lea     rbp, [rsp-37h]
0x18008c64d  sub     rsp, 0E0h
0x18008c654  mov     rax, cs:__security_cookie
0x18008c65b  xor     rax, rsp
0x18008c65e  mov     [rbp+57h+var_28], rax
0x18008c662  xor     r15d, r15d
0x18008c665  xorps   xmm0, xmm0
0x18008c668  movups  [rbp+57h+var_60], xmm0
0x18008c66c  mov     rsi, r8
0x18008c66f  mov     r14d, edx
0x18008c672  movups  [rbp+57h+var_70], xmm0
0x18008c676  lea     eax, [r15+3]
0x18008c67a  mov     dword ptr [rbp+57h+var_60], edx
0x18008c67d  mov     word ptr [rbp+57h+var_70], ax
0x18008c681  lea     r8, [rbp+57h+var_88]
0x18008c685  xor     eax, eax
0x18008c687  mov     [rbp+57h+var_98], r15
0x18008c68b  mov     [rbp+57h+var_50.pUnkForRelease], rax
0x18008c68f  lea     rdx, IID_IOleCache
0x18008c696  mov     rax, [rcx]
0x18008c699  mov     rdi, rcx
0x18008c69c  movups  [rbp+57h+var_38], xmm0
0x18008c6a0  mov     qword ptr [rbp+57h+x], r15
0x18008c6a4  mov     ebx, r15d
0x18008c6a7  mov     qword ptr [rbp+57h+sz.cx], r15
0x18008c6ab  mov     rax, [rax]
0x18008c6ae  mov     qword ptr [rbp+57h+pt.x], r15
0x18008c6b2  mov     [rbp+57h+var_88], r15
0x18008c6b6  mov     [rbp+57h+var_90], r15
0x18008c6ba  mov     dword ptr [rbp+57h+var_60+4], 0FFFFFFFFh
0x18008c6c1  mov     dword ptr [rbp+57h+var_60+8], 20h ; ' '
0x18008c6c8  movups  xmmword ptr [rbp+57h+var_50.tymed], xmm0
0x18008c6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c6d1  test    eax, eax
0x18008c6d3  jnz     short loc_18008C724
0x18008c6d5  mov     rcx, [rbp+57h+var_88]
0x18008c6d9  lea     r8, [rbp+57h+var_90]
0x18008c6dd  lea     rdx, IID_IDataObject
0x18008c6e4  mov     rax, [rcx]
0x18008c6e7  mov     rax, [rax]
0x18008c6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c6ef  test    eax, eax
0x18008c6f1  jnz     short loc_18008C724
0x18008c6f3  mov     rcx, [rbp+57h+var_90]
0x18008c6f7  lea     r8, [rbp+57h+var_50]
0x18008c6fb  lea     rdx, [rbp+57h+var_70]
0x18008c6ff  mov     rax, [rcx]
0x18008c702  mov     rax, [rax+18h]
0x18008c706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c70b  test    eax, eax
0x18008c70d  jnz     short loc_18008C724
0x18008c70f  mov     rcx, qword ptr [rbp+57h+var_50.8]; void *
0x18008c713  call    ?OleDuplicateData@CW32System@@SAPEAXPEAXGI@Z; CW32System::OleDuplicateData(void *,ushort,uint)
0x18008c718  lea     rcx, [rbp+57h+var_50]; struct tagSTGMEDIUM *
0x18008c71c  mov     rbx, rax
0x18008c71f  call    ?ReleaseStgMedium@CW32System@@SAJPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x18008c724  mov     rdx, [rbp+57h+var_90]
0x18008c728  test    rdx, rdx
0x18008c72b  jz      short loc_18008C73C
0x18008c72d  mov     rcx, [rdx]
0x18008c730  mov     rax, [rcx+10h]
0x18008c734  mov     rcx, rdx
0x18008c737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c73c  mov     rcx, [rbp+57h+var_88]
0x18008c740  test    rcx, rcx
0x18008c743  jz      short loc_18008C751
0x18008c745  mov     rax, [rcx]
0x18008c748  mov     rax, [rax+10h]
0x18008c74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c751  test    rbx, rbx
0x18008c754  jnz     loc_18008C869
0x18008c75a  mov     rax, [rdi]
0x18008c75d  lea     r8, [rbp+57h+var_98]
0x18008c761  lea     rdx, IID_IViewObject2
0x18008c768  mov     rcx, rdi
0x18008c76b  mov     rax, [rax]
0x18008c76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c773  test    eax, eax
0x18008c775  jz      short loc_18008C77E
0x18008c777  xor     eax, eax
0x18008c779  jmp     loc_18008C86C
0x18008c77e  test    rsi, rsi
0x18008c781  jz      short loc_18008C78C
0x18008c783  mov     rax, [rsi]
0x18008c786  mov     qword ptr [rbp+57h+x], rax
0x18008c78a  jmp     short loc_18008C7B7
0x18008c78c  mov     rcx, [rbp+57h+var_98]
0x18008c790  lea     rdx, [rbp+57h+x]
0x18008c794  mov     [rsp+100h+var_E0], rdx
0x18008c799  xor     r9d, r9d
0x18008c79c  or      r8d, 0FFFFFFFFh
0x18008c7a0  mov     edx, r14d
0x18008c7a3  mov     rax, [rcx]
0x18008c7a6  mov     rax, [rax+48h]
0x18008c7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c7af  test    eax, eax
0x18008c7b1  jz      short loc_18008C7B7
0x18008c7b3  mov     qword ptr [rbp+57h+x], r15
0x18008c7b7  xor     ecx, ecx; pszFile
0x18008c7b9  call    cs:__imp_CreateMetaFileA
0x18008c7bf  mov     edi, [rbp+57h+x]
0x18008c7c2  lea     r9, [rbp+57h+pt]; lppt
0x18008c7c6  mov     ebx, [rbp+57h+x+4]
0x18008c7c9  mov     rcx, rax; hdc
0x18008c7cc  xor     r8d, r8d; y
0x18008c7cf  mov     qword ptr [rbp+57h+var_38], r15
0x18008c7d3  xor     edx, edx; x
0x18008c7d5  mov     dword ptr [rbp+57h+var_38+8], edi
0x18008c7d8  mov     rsi, rax
0x18008c7db  mov     dword ptr [rbp+57h+var_38+0Ch], ebx
0x18008c7de  call    cs:__imp_SetWindowOrgEx
0x18008c7e4  lea     r9, [rbp+57h+sz]; lpsz
0x18008c7e8  mov     r8d, ebx; y
0x18008c7eb  mov     edx, edi; x
0x18008c7ed  mov     rcx, rsi; hdc
0x18008c7f0  call    cs:__imp_SetWindowExtEx
0x18008c7f6  mov     rcx, [rbp+57h+var_98]
0x18008c7fa  lea     rdx, [rbp+57h+var_38]
0x18008c7fe  mov     [rsp+100h+var_B0], r15
0x18008c803  xor     r9d, r9d
0x18008c806  mov     [rsp+100h+var_B8], r15
0x18008c80b  or      r8d, 0FFFFFFFFh
0x18008c80f  mov     [rsp+100h+var_C0], rdx
0x18008c814  lea     rdx, [rbp+57h+var_38]
0x18008c818  mov     rax, [rcx]
0x18008c81b  mov     [rsp+100h+var_C8], rdx
0x18008c820  mov     edx, r14d
0x18008c823  mov     [rsp+100h+var_D0], rsi
0x18008c828  mov     [rsp+100h+var_D8], r15
0x18008c82d  mov     rax, [rax+18h]
0x18008c831  mov     [rsp+100h+var_E0], r15
0x18008c836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c83b  mov     rcx, [rbp+57h+var_98]
0x18008c83f  mov     ebx, eax
0x18008c841  mov     rdx, [rcx]
0x18008c844  mov     rax, [rdx+10h]
0x18008c848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c84d  mov     rcx, rsi; hdc
0x18008c850  call    cs:__imp_CloseMetaFile
0x18008c856  mov     rdi, rax
0x18008c859  test    ebx, ebx
0x18008c85b  jz      short loc_18008C88F
0x18008c85d  mov     rbx, r15
0x18008c860  mov     rcx, rdi; hmf
0x18008c863  call    cs:__imp_DeleteMetaFile
0x18008c869  mov     rax, rbx
0x18008c86c  mov     rcx, [rbp+57h+var_28]
0x18008c870  xor     rcx, rsp; StackCookie
0x18008c873  call    __security_check_cookie
0x18008c878  mov     rbx, [rsp+100h+arg_18]
0x18008c880  add     rsp, 0E0h
0x18008c887  pop     r15
0x18008c889  pop     r14
0x18008c88b  pop     rdi
0x18008c88c  pop     rsi
0x18008c88d  pop     rbp
0x18008c88e  retn
0x18008c88f  mov     edx, 18h; dwBytes
0x18008c894  mov     ecx, 2042h; uFlags
0x18008c899  call    cs:__imp_GlobalAlloc
0x18008c89f  mov     rbx, rax
0x18008c8a2  test    rax, rax
0x18008c8a5  jz      short loc_18008C860
0x18008c8a7  mov     rcx, rax; hMem
0x18008c8aa  call    cs:__imp_GlobalLock
0x18008c8b0  test    rax, rax
0x18008c8b3  jz      short loc_18008C869
0x18008c8b5  mov     [rax+10h], rdi
0x18008c8b9  mov     ecx, [rbp+57h+x]
0x18008c8bc  mov     [rax+4], ecx
0x18008c8bf  mov     ecx, [rbp+57h+x+4]
0x18008c8c2  mov     [rax+8], ecx
0x18008c8c5  mov     rcx, rbx; hMem
0x18008c8c8  mov     dword ptr [rax], 8
0x18008c8ce  call    cs:__imp_GlobalUnlock
0x18008c8d4  jmp     short loc_18008C869
```
