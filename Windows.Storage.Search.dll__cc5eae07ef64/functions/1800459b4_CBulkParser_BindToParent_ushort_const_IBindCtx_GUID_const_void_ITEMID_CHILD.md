# CBulkParser::_BindToParent(ushort const *,IBindCtx *,_GUID const &,void * *,_ITEMID_CHILD * *)

- ea: `0x1800459b4`
- end: `0x180045cea`
- name: `?_BindToParent@CBulkParser@@AEAAJPEBGPEAUIBindCtx@@AEBU_GUID@@PEAPEAXPEAPEAU_ITEMID_CHILD@@@Z`
- size: `822`
- prototype: `int(CBulkParser *__hidden this, const unsigned __int16 *, struct IBindCtx *, const struct _GUID *, void **, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800458c0`

## callees

- `0x180006ca8`
- `0x1800459b4`
- `0x18007a4e0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x180045b84`
- `Windows.Storage!ILFree` at `0x180045b84`
- `Windows.Storage!SHParseDisplayName` at `0x180045b46`
- `Windows.Storage!SHParseDisplayName` at `0x180045b46`
- `Windows.Storage!SHBindToParent` at `0x180045b70`
- `Windows.Storage!SHBindToParent` at `0x180045b70`
- `Windows.Storage!ILCloneFirst` at `0x180045cb2`
- `Windows.Storage!ILCloneFirst` at `0x180045cb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045ab6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045ad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045c8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045ab6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045ad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045c8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045a11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045a11`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180045c2b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180045c2b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180045aa9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180045aa9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180045bd5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180045bd5`

## pseudocode

```c
__int64 __fastcall CBulkParser::_BindToParent(
        CBulkParser *this,
        const unsigned __int16 *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5,
        struct _ITEMID_CHILD **a6)
{
  unsigned __int64 v6; // rsi
  unsigned __int64 v10; // rdi
  _WORD *v11; // rbx
  const WCHAR *v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  _WORD *v15; // r8
  __int64 v16; // r10
  _WORD *v17; // rcx
  __int64 v18; // r9
  struct _ITEMID_CHILD **v19; // r12
  _QWORD *v20; // rsi
  int v21; // edi
  HRESULT v22; // edi
  __int64 v23; // rdi
  bool v24; // cf
  const WCHAR *v25; // rdx
  LPWSTR FileNameW; // rax
  __int64 (__fastcall ***v27)(_QWORD, const struct _GUID *, void **); // rcx
  LPITEMIDLIST v29; // rax
  LPCITEMIDLIST ppidlLast[2]; // [rsp+40h] [rbp-10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+90h] [rbp+40h] BYREF
  const struct _GUID *v32; // [rsp+A8h] [rbp+58h]

  v32 = a4;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v10 = v6 + 1;
  if ( v6 + 1 < v6 )
    goto LABEL_19;
  ppidl = 0;
  if ( !is_mul_ok(v10, 2u) )
    goto LABEL_19;
  v11 = LocalAlloc(0, 2 * v10);
  if ( v11 )
  {
    if ( v10 <= 0x7FFFFFFF )
    {
      if ( v6 < 0x7FFFFFFF )
      {
        v12 = &pszFormat;
        v13 = v6 & -(__int64)(a2 != 0);
        if ( a2 )
          v12 = a2;
        v14 = v6 + 1;
        v15 = v11;
        v16 = 0;
        do
        {
          if ( !v13 )
            break;
          if ( !*v12 )
            break;
          *v15++ = *v12++;
          --v13;
          ++v16;
          --v14;
        }
        while ( v14 );
        v17 = v15 - 1;
        v18 = v16 - 1;
        if ( v14 )
        {
          v17 = v15;
          v18 = v16;
        }
        *v17 = 0;
        if ( v14 )
        {
          v24 = v10 == v18;
          v23 = v10 - v18;
          if ( !v24 && v23 != 1 )
            StringExHandleFillBehindNullW(&v11[v18], 2 * v23, 0x300u);
        }
LABEL_17:
        if ( !PathRemoveFileSpecW(v11) )
        {
          LocalFree(v11);
LABEL_19:
          v11 = 0;
          goto LABEL_20;
        }
        goto LABEL_20;
      }
      if ( v6 == -1 )
        goto LABEL_17;
    }
    *v11 = 0;
    goto LABEL_17;
  }
LABEL_20:
  v19 = a6;
  v20 = (_QWORD *)((char *)this + 24);
  v21 = 0;
  if ( *((_QWORD *)this + 3) )
  {
    v25 = (const WCHAR *)*((_QWORD *)this + 2);
    if ( v25 )
    {
      if ( v11 && !StrCmpICW(v11, v25) )
      {
        if ( *((_DWORD *)this + 8) )
        {
          ppidl = 0;
          if ( !a3
            || ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPITEMIDLIST *))a3->lpVtbl->GetObjectParam)(
                 a3,
                 L"File System Bind Data",
                 &ppidl) < 0 )
          {
            goto LABEL_21;
          }
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
        }
        FileNameW = PathFindFileNameW(a2);
        v27 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v20;
        *v19 = 0;
        ppidl = 0;
        if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **), _QWORD, struct IBindCtx *, LPWSTR, _QWORD, LPITEMIDLIST *, _QWORD))(*v27)[3])(
               v27,
               0,
               a3,
               FileNameW,
               0,
               &ppidl,
               0) >= 0 )
        {
          *v19 = (struct _ITEMID_CHILD *)ppidl;
LABEL_39:
          v22 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v20)(*v20, v32, a5);
          goto LABEL_40;
        }
      }
    }
  }
LABEL_21:
  LocalFree(*((HLOCAL *)this + 2));
  *((_QWORD *)this + 2) = 0;
  SafeRelease<IShellItemArray>((__int64 *)this + 3);
  ppidlLast[0] = 0;
  if ( a3
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPCITEMIDLIST *))a3->lpVtbl->GetObjectParam)(
         a3,
         L"File System Bind Data",
         ppidlLast) >= 0 )
  {
    v21 = 1;
    (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)ppidlLast[0] + 16LL))(ppidlLast[0]);
  }
  *((_DWORD *)this + 8) = v21;
  ppidl = 0;
  v22 = SHParseDisplayName(a2, a3, &ppidl, 0, 0);
  if ( v22 >= 0 )
  {
    ppidlLast[0] = 0;
    v22 = SHBindToParent(ppidl, &GUID_000214e6_0000_0000_c000_000000000046, (void **)this + 3, ppidlLast);
    if ( v22 >= 0 )
    {
      v29 = ILCloneFirst(ppidlLast[0]);
      *v19 = (struct _ITEMID_CHILD *)v29;
      if ( v29 )
      {
        v22 = 0;
        *((_QWORD *)this + 2) = v11;
        v11 = 0;
      }
      else
      {
        v22 = -2147024882;
      }
    }
    ILFree(ppidl);
    if ( v22 >= 0 )
      goto LABEL_39;
  }
LABEL_40:
  LocalFree(v11);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800459b4  mov     [rsp-38h+arg_8], rbx
0x1800459b9  mov     [rsp-38h+arg_18], r9
0x1800459be  push    rbp
0x1800459bf  push    rsi
0x1800459c0  push    rdi
0x1800459c1  push    r12
0x1800459c3  push    r13
0x1800459c5  push    r14
0x1800459c7  push    r15
0x1800459c9  mov     rbp, rsp
0x1800459cc  sub     rsp, 50h
0x1800459d0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800459d4  mov     r15, r8
0x1800459d7  xor     r12d, r12d
0x1800459da  mov     r13, rdx
0x1800459dd  mov     r14, rcx
0x1800459e0  inc     rsi
0x1800459e3  cmp     [rdx+rsi*2], r12w
0x1800459e8  jnz     short loc_1800459E0
0x1800459ea  lea     rdi, [rsi+1]
0x1800459ee  cmp     rdi, rsi
0x1800459f1  jb      loc_180045ABC
0x1800459f7  mov     eax, 2
0x1800459fc  mov     [rbp+ppidl], r12
0x180045a00  mul     rdi
0x180045a03  test    rdx, rdx
0x180045a06  jnz     loc_180045ABC
0x180045a0c  mov     rdx, rax; uBytes
0x180045a0f  xor     ecx, ecx; uFlags
0x180045a11  call    cs:__imp_LocalAlloc
0x180045a17  mov     rbx, rax
0x180045a1a  test    rax, rax
0x180045a1d  jz      loc_180045ABF
0x180045a23  mov     eax, 7FFFFFFFh
0x180045a28  cmp     rdi, rax
0x180045a2b  ja      loc_180045CE1
0x180045a31  cmp     rsi, rax
0x180045a34  jnb     loc_180045CD8
0x180045a3a  mov     rax, r13
0x180045a3d  neg     rax
0x180045a40  lea     rax, pszFormat
0x180045a47  sbb     rcx, rcx
0x180045a4a  and     rcx, rsi
0x180045a4d  test    r13, r13
0x180045a50  cmovnz  rax, r13
0x180045a54  test    rdi, rdi
0x180045a57  jz      short loc_180045AA6
0x180045a59  mov     rdx, rdi
0x180045a5c  mov     r8, rbx
0x180045a5f  mov     r10, r12
0x180045a62  test    rcx, rcx
0x180045a65  jz      short loc_180045A89
0x180045a67  movzx   r9d, word ptr [rax]
0x180045a6b  test    r9w, r9w
0x180045a6f  jz      short loc_180045A89
0x180045a71  mov     [r8], r9w
0x180045a75  add     rax, 2
0x180045a79  add     r8, 2
0x180045a7d  dec     rcx
0x180045a80  inc     r10
0x180045a83  sub     rdx, 1
0x180045a87  jnz     short loc_180045A62
0x180045a89  test    rdx, rdx
0x180045a8c  lea     rcx, [r8-2]
0x180045a90  lea     r9, [r10-1]
0x180045a94  cmovnz  rcx, r8
0x180045a98  cmovnz  r9, r10
0x180045a9c  mov     [rcx], r12w
0x180045aa0  jnz     loc_180045B97
0x180045aa6  mov     rcx, rbx; pszPath
0x180045aa9  call    cs:__imp_PathRemoveFileSpecW
0x180045aaf  test    eax, eax
0x180045ab1  jnz     short loc_180045ABF
0x180045ab3  mov     rcx, rbx; hMem
0x180045ab6  call    cs:__imp_LocalFree
0x180045abc  mov     rbx, r12
0x180045abf  mov     r12, [rbp+arg_28]
0x180045ac3  lea     rsi, [r14+18h]
0x180045ac7  xor     edi, edi
0x180045ac9  cmp     [rsi], rdi
0x180045acc  jnz     loc_180045BBC
0x180045ad2  mov     rcx, [r14+10h]; hMem
0x180045ad6  call    cs:__imp_LocalFree
0x180045adc  mov     rcx, rsi
0x180045adf  mov     [r14+10h], rdi
0x180045ae3  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180045ae8  mov     [rbp+ppidlLast], rdi
0x180045aec  test    r15, r15
0x180045aef  jz      short loc_180045B24
0x180045af1  mov     rax, [r15]
0x180045af4  lea     r8, [rbp+ppidlLast]
0x180045af8  lea     rdx, aFileSystemBind; "File System Bind Data"
0x180045aff  mov     rcx, r15
0x180045b02  mov     rax, [rax+50h]
0x180045b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b0b  test    eax, eax
0x180045b0d  js      short loc_180045B24
0x180045b0f  mov     rcx, [rbp+ppidlLast]
0x180045b13  mov     edi, 1
0x180045b18  mov     rax, [rcx]
0x180045b1b  mov     rax, [rax+10h]
0x180045b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b24  xor     r9d, r9d; sfgaoIn
0x180045b27  mov     [r14+20h], edi
0x180045b2b  lea     r8, [rbp+ppidl]; ppidl
0x180045b2f  mov     [rbp+ppidl], 0
0x180045b37  mov     rdx, r15; pbc
0x180045b3a  mov     [rsp+50h+psfgaoOut], 0; psfgaoOut
0x180045b43  mov     rcx, r13; pszName
0x180045b46  call    cs:__imp_SHParseDisplayName
0x180045b4c  mov     edi, eax
0x180045b4e  test    eax, eax
0x180045b50  js      loc_180045C8B
0x180045b56  mov     rcx, [rbp+ppidl]; pidl
0x180045b5a  lea     r9, [rbp+ppidlLast]; ppidlLast
0x180045b5e  mov     r8, rsi; ppv
0x180045b61  mov     [rbp+ppidlLast], 0
0x180045b69  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180045b70  call    cs:__imp_SHBindToParent
0x180045b76  mov     edi, eax
0x180045b78  test    eax, eax
0x180045b7a  jns     loc_180045CAE
0x180045b80  mov     rcx, [rbp+ppidl]; pidl
0x180045b84  call    cs:__imp_ILFree
0x180045b8a  test    edi, edi
0x180045b8c  js      loc_180045C8B
0x180045b92  jmp     loc_180045C73
0x180045b97  sub     rdi, r9
0x180045b9a  cmp     rdi, 1
0x180045b9e  jbe     loc_180045AA6
0x180045ba4  lea     rdx, [rdi+rdi]; cbRemaining
0x180045ba8  mov     r8d, 300h; dwFlags
0x180045bae  lea     rcx, [rbx+r9*2]; pszDestEnd
0x180045bb2  call    StringExHandleFillBehindNullW
0x180045bb7  jmp     loc_180045AA6
0x180045bbc  mov     rdx, [r14+10h]; pszStr2
0x180045bc0  test    rdx, rdx
0x180045bc3  jz      loc_180045AD2
0x180045bc9  test    rbx, rbx
0x180045bcc  jz      loc_180045AD2
0x180045bd2  mov     rcx, rbx; pszStr1
0x180045bd5  call    cs:__imp_StrCmpICW
0x180045bdb  test    eax, eax
0x180045bdd  jnz     loc_180045AD2
0x180045be3  cmp     [r14+20h], edi
0x180045be7  jz      short loc_180045C28
0x180045be9  mov     [rbp+ppidl], rdi
0x180045bed  test    r15, r15
0x180045bf0  jz      loc_180045AD2
0x180045bf6  mov     rax, [r15]
0x180045bf9  lea     r8, [rbp+ppidl]
0x180045bfd  lea     rdx, aFileSystemBind; "File System Bind Data"
0x180045c04  mov     rcx, r15
0x180045c07  mov     rax, [rax+50h]
0x180045c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c10  test    eax, eax
0x180045c12  js      loc_180045AD2
0x180045c18  mov     rcx, [rbp+ppidl]
0x180045c1c  mov     rax, [rcx]
0x180045c1f  mov     rax, [rax+10h]
0x180045c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c28  mov     rcx, r13; pszPath
0x180045c2b  call    cs:__imp_PathFindFileNameW
0x180045c31  mov     rcx, [rsi]
0x180045c34  mov     r8, r15
0x180045c37  mov     [r12], rdi
0x180045c3b  mov     r9, rax
0x180045c3e  mov     [rsp+50h+var_20], rdi
0x180045c43  mov     [rbp+ppidl], rdi
0x180045c47  mov     rdx, [rcx]
0x180045c4a  mov     rax, [rdx+18h]
0x180045c4e  lea     rdx, [rbp+ppidl]
0x180045c52  mov     [rsp+50h+var_28], rdx
0x180045c57  xor     edx, edx
0x180045c59  mov     [rsp+50h+psfgaoOut], rdi
0x180045c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c63  test    eax, eax
0x180045c65  js      loc_180045AD2
0x180045c6b  mov     rax, [rbp+ppidl]
0x180045c6f  mov     [r12], rax
0x180045c73  mov     rcx, [rsi]
0x180045c76  mov     r8, [rbp+arg_20]
0x180045c7a  mov     rdx, [rbp+arg_18]
0x180045c7e  mov     rax, [rcx]
0x180045c81  mov     rax, [rax]
0x180045c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c89  mov     edi, eax
0x180045c8b  mov     rcx, rbx; hMem
0x180045c8e  call    cs:__imp_LocalFree
0x180045c94  mov     rbx, [rsp+50h+arg_8]
0x180045c9c  mov     eax, edi
0x180045c9e  add     rsp, 50h
0x180045ca2  pop     r15
0x180045ca4  pop     r14
0x180045ca6  pop     r13
0x180045ca8  pop     r12
0x180045caa  pop     rdi
0x180045cab  pop     rsi
0x180045cac  pop     rbp
0x180045cad  retn
0x180045cae  mov     rcx, [rbp+ppidlLast]; pidl
0x180045cb2  call    cs:__imp_ILCloneFirst
0x180045cb8  mov     [r12], rax
0x180045cbc  test    rax, rax
0x180045cbf  jz      short loc_180045CCE
0x180045cc1  xor     edi, edi
0x180045cc3  mov     [r14+10h], rbx
0x180045cc7  xor     ebx, ebx
0x180045cc9  jmp     loc_180045B80
0x180045cce  mov     edi, 8007000Eh
0x180045cd3  jmp     loc_180045B80
0x180045cd8  test    rdi, rdi
0x180045cdb  jz      loc_180045AA6
0x180045ce1  mov     [rbx], r12w
0x180045ce5  jmp     loc_180045AA6
```
