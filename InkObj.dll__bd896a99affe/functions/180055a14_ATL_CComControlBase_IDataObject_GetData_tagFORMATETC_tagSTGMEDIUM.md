# ATL::CComControlBase::IDataObject_GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180055a14`
- end: `0x180055bef`
- name: `?IDataObject_GetData@CComControlBase@ATL@@QEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180054510`
- `0x180073c14`

## callees

- `0x18004d6c8`
- `0x180055a14`
- `0x180104ece`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180055b7e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180055b7e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180055b9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180055b9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180055bbb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180055bbb`
- `GDI32!DeleteMetaFile` at `0x180055b8f`
- `GDI32!DeleteMetaFile` at `0x180055b8f`
- `GDI32!CloseMetaFile` at `0x180055b5f`
- `GDI32!CloseMetaFile` at `0x180055b5f`
- `GDI32!RestoreDC` at `0x180055b55`
- `GDI32!RestoreDC` at `0x180055b55`
- `GDI32!SetWindowOrgEx` at `0x180055b21`
- `GDI32!SetWindowOrgEx` at `0x180055b21`
- `GDI32!SaveDC` at `0x180055b0f`
- `GDI32!SaveDC` at `0x180055b0f`
- `GDI32!SetWindowExtEx` at `0x180055b35`
- `GDI32!SetWindowExtEx` at `0x180055b35`
- `GDI32!CreateMetaFileW` at `0x180055b02`
- `GDI32!CreateMetaFileW` at `0x180055b02`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::IDataObject_GetData(
        struct tagSIZE *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  __int64 result; // rax
  bool v6; // zf
  struct tagSIZE v7; // rbx
  struct tagSIZE v8; // rax
  int v9; // eax
  HMETAFILE v10; // r14
  HBITMAP v11; // rax
  HBITMAP v12; // rsi
  _DWORD *v13; // rax
  struct tagSIZE v14; // [rsp+20h] [rbp-59h] BYREF
  struct tagSIZE v15; // [rsp+28h] [rbp-51h] BYREF
  _DWORD v16[4]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v17; // [rsp+40h] [rbp-39h]
  HDC hdc; // [rsp+50h] [rbp-29h]
  __int64 *v19; // [rsp+58h] [rbp-21h]
  __int64 *v20; // [rsp+60h] [rbp-19h]
  int v21; // [rsp+68h] [rbp-11h]
  int v22; // [rsp+70h] [rbp-9h]
  __int64 v23; // [rsp+90h] [rbp+17h] BYREF
  struct tagSIZE x; // [rsp+98h] [rbp+1Fh]

  if ( !a3 )
    return 2147500035LL;
  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  if ( (a2->tymed & 0x20) == 0 )
    return 2147745892LL;
  v6 = (this[13].cx & 0x1000) == 0;
  v15 = 0;
  if ( v6 )
    v7 = this[8];
  else
    v7 = this[7];
  v6 = (this[13].cx & 0x2000) == 0;
  v14 = v7;
  if ( v6 )
  {
    ATL::AtlHiMetricToPixel(&v14, &v15);
    v8 = v15;
  }
  else
  {
    v8 = v7;
  }
  x = v8;
  v23 = 0;
  memset_0(v16, 0, 0x58u);
  v16[0] = 88;
  v16[1] = 1;
  v19 = &v23;
  v21 = 1;
  v20 = &v23;
  v9 = ((unsigned int)this[13].cx >> 13) & 1;
  v16[2] = -1;
  v22 = v9;
  v17 = 0;
  hdc = CreateMetaFileW(0);
  SaveDC(hdc);
  SetWindowOrgEx(hdc, 0, 0, 0);
  SetWindowExtEx(hdc, x.cx, x.cy, 0);
  (*(void (__fastcall **)(struct tagSIZE *, _DWORD *))(*(_QWORD *)this + 16LL))(this, v16);
  RestoreDC(hdc, -1);
  v10 = CloseMetaFile(hdc);
  if ( !v10 )
    return 2147549183LL;
  v11 = (HBITMAP)GlobalAlloc(0x2002u, 0x18u);
  v12 = v11;
  if ( v11 )
  {
    v13 = GlobalLock(v11);
    v13[2] = v14.cy;
    *((_QWORD *)v13 + 2) = v10;
    *v13 = 8;
    v13[1] = v7.cx;
    GlobalUnlock(v12);
    result = 0;
    a3->tymed = 32;
    a3->hBitmap = v12;
    a3->pUnkForRelease = 0;
  }
  else
  {
    DeleteMetaFile(v10);
    return 2147680368LL;
  }
  return result;
}

```

## disassembly

```asm
0x180055a14  push    rbp
0x180055a16  push    rbx
0x180055a17  push    rsi
0x180055a18  push    rdi
0x180055a19  push    r14
0x180055a1b  lea     rbp, [rsp-37h]
0x180055a20  sub     rsp, 0B0h
0x180055a27  mov     rax, cs:__security_cookie
0x180055a2e  xor     rax, rsp
0x180055a31  mov     [rbp+57h+var_30], rax
0x180055a35  mov     rdi, r8
0x180055a38  mov     rsi, rcx
0x180055a3b  test    r8, r8
0x180055a3e  jnz     short loc_180055A4A
0x180055a40  mov     eax, 80004003h
0x180055a45  jmp     loc_180055BD5
0x180055a4a  xor     eax, eax
0x180055a4c  xorps   xmm0, xmm0
0x180055a4f  movups  xmmword ptr [r8], xmm0
0x180055a53  mov     [r8+10h], rax
0x180055a57  test    byte ptr [rdx+18h], 20h
0x180055a5b  jnz     short loc_180055A67
0x180055a5d  mov     eax, 80040064h
0x180055a62  jmp     loc_180055BD5
0x180055a67  test    dword ptr [rcx+68h], 1000h
0x180055a6e  mov     qword ptr [rbp+57h+var_A8.cx], rax
0x180055a72  jz      short loc_180055A7A
0x180055a74  mov     rbx, [rcx+38h]
0x180055a78  jmp     short loc_180055A7E
0x180055a7a  mov     rbx, [rcx+40h]
0x180055a7e  test    dword ptr [rcx+68h], 2000h
0x180055a85  mov     qword ptr [rbp+57h+var_B0.cx], rbx
0x180055a89  jnz     short loc_180055A9E
0x180055a8b  lea     rdx, [rbp+57h+var_A8]; struct tagSIZE *
0x180055a8f  lea     rcx, [rbp+57h+var_B0]; struct tagSIZE *
0x180055a93  call    ?AtlHiMetricToPixel@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlHiMetricToPixel(tagSIZE const *,tagSIZE *)
0x180055a98  mov     rax, qword ptr [rbp+57h+var_A8.cx]
0x180055a9c  jmp     short loc_180055AA1
0x180055a9e  mov     rax, rbx
0x180055aa1  mov     [rbp+57h+x], eax
0x180055aa4  lea     rcx, [rbp+57h+var_A0]; void *
0x180055aa8  shr     rax, 20h
0x180055aac  mov     r14d, 58h ; 'X'
0x180055ab2  mov     r8d, r14d; Size
0x180055ab5  mov     [rbp+57h+y], eax
0x180055ab8  xor     edx, edx; Val
0x180055aba  mov     [rbp+57h+var_40], 0
0x180055ac2  call    memset_0
0x180055ac7  lea     ecx, [r14-57h]
0x180055acb  mov     [rbp+57h+var_A0], r14d
0x180055acf  lea     rax, [rbp+57h+var_40]
0x180055ad3  mov     [rbp+57h+var_9C], ecx
0x180055ad6  mov     [rbp+57h+var_78], rax
0x180055ada  xorps   xmm0, xmm0
0x180055add  lea     rax, [rbp+57h+var_40]
0x180055ae1  mov     [rbp+57h+var_68], ecx
0x180055ae4  mov     [rbp+57h+var_70], rax
0x180055ae8  or      r14d, 0FFFFFFFFh
0x180055aec  mov     eax, [rsi+68h]
0x180055aef  shr     eax, 0Dh
0x180055af2  and     eax, ecx
0x180055af4  mov     [rbp+57h+var_98], r14d
0x180055af8  xor     ecx, ecx; pszFile
0x180055afa  mov     [rbp+57h+var_60], eax
0x180055afd  movdqa  [rbp+57h+var_90], xmm0
0x180055b02  call    cs:__imp_CreateMetaFileW
0x180055b08  mov     rcx, rax; hdc
0x180055b0b  mov     [rbp+57h+hdc], rax
0x180055b0f  call    cs:__imp_SaveDC
0x180055b15  mov     rcx, [rbp+57h+hdc]; hdc
0x180055b19  xor     r9d, r9d; lppt
0x180055b1c  xor     r8d, r8d; y
0x180055b1f  xor     edx, edx; x
0x180055b21  call    cs:__imp_SetWindowOrgEx
0x180055b27  mov     r8d, [rbp+57h+y]; y
0x180055b2b  xor     r9d, r9d; lpsz
0x180055b2e  mov     edx, [rbp+57h+x]; x
0x180055b31  mov     rcx, [rbp+57h+hdc]; hdc
0x180055b35  call    cs:__imp_SetWindowExtEx
0x180055b3b  mov     rax, [rsi]
0x180055b3e  lea     rdx, [rbp+57h+var_A0]
0x180055b42  mov     rcx, rsi
0x180055b45  mov     rax, [rax+10h]
0x180055b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b4e  mov     rcx, [rbp+57h+hdc]; hdc
0x180055b52  mov     edx, r14d; nSavedDC
0x180055b55  call    cs:__imp_RestoreDC
0x180055b5b  mov     rcx, [rbp+57h+hdc]; hdc
0x180055b5f  call    cs:__imp_CloseMetaFile
0x180055b65  mov     r14, rax
0x180055b68  test    rax, rax
0x180055b6b  jnz     short loc_180055B74
0x180055b6d  mov     eax, 8000FFFFh
0x180055b72  jmp     short loc_180055BD5
0x180055b74  mov     edx, 18h; dwBytes
0x180055b79  mov     ecx, 2002h; uFlags
0x180055b7e  call    cs:__imp_GlobalAlloc
0x180055b84  mov     rsi, rax
0x180055b87  test    rax, rax
0x180055b8a  jnz     short loc_180055B9C
0x180055b8c  mov     rcx, r14; hmf
0x180055b8f  call    cs:__imp_DeleteMetaFile
0x180055b95  mov     eax, 80030070h
0x180055b9a  jmp     short loc_180055BD5
0x180055b9c  mov     rcx, rsi; hMem
0x180055b9f  call    cs:__imp_GlobalLock
0x180055ba5  mov     ecx, [rbp+57h+var_B0.cy]
0x180055ba8  mov     [rax+8], ecx
0x180055bab  mov     rcx, rsi; hMem
0x180055bae  mov     [rax+10h], r14
0x180055bb2  mov     dword ptr [rax], 8
0x180055bb8  mov     [rax+4], ebx
0x180055bbb  call    cs:__imp_GlobalUnlock
0x180055bc1  xor     eax, eax
0x180055bc3  mov     dword ptr [rdi], 20h ; ' '
0x180055bc9  mov     [rdi+8], rsi
0x180055bcd  mov     qword ptr [rdi+10h], 0
0x180055bd5  mov     rcx, [rbp+57h+var_30]
0x180055bd9  xor     rcx, rsp; StackCookie
0x180055bdc  call    __security_check_cookie
0x180055be1  add     rsp, 0B0h
0x180055be8  pop     r14
0x180055bea  pop     rdi
0x180055beb  pop     rsi
0x180055bec  pop     rbx
0x180055bed  pop     rbp
0x180055bee  retn
```
