# _AfxCopyStgMedium(ushort,tagSTGMEDIUM *,tagSTGMEDIUM *)

- ea: `0x180093e40`
- end: `0x180094182`
- name: `?_AfxCopyStgMedium@@YAHGPEAUtagSTGMEDIUM@@0@Z`
- size: `834`
- prototype: `__int64 __fastcall(unsigned __int16, struct tagSTGMEDIUM *, struct tagSTGMEDIUM *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180086ba0`
- `0x180086e20`
- `0x1800875d0`
- `0x1800876c0`

## callees

- `0x180093da4`
- `0x180093e40`
- `0x180094c50`
- `0x1800d1f7a`
- `0x1800d1f92`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180093fd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180093fd1`
- `KERNEL32!GlobalFree` at `0x180093f49`
- `KERNEL32!GlobalFree` at `0x180093f49`
- `KERNEL32!GlobalUnlock` at `0x180093f40`
- `KERNEL32!GlobalUnlock` at `0x180093f56`
- `KERNEL32!GlobalUnlock` at `0x180093f40`
- `KERNEL32!GlobalUnlock` at `0x180093f56`
- `KERNEL32!GlobalLock` at `0x180093f1a`
- `KERNEL32!GlobalLock` at `0x180093f1a`
- `KERNEL32!CopyFileW` at `0x180094140`
- `KERNEL32!CopyFileW` at `0x180094140`
- `GDI32!CopyMetaFileW` at `0x180093f2e`
- `GDI32!CopyMetaFileW` at `0x180093f2e`
- `OLE32!OleDuplicateData` at `0x180093ef0`
- `OLE32!OleDuplicateData` at `0x180093ef0`

## pseudocode

```c
BOOL __fastcall _AfxCopyStgMedium(CLIPFORMAT a1, struct tagSTGMEDIUM *a2, struct tagSTGMEDIUM *a3)
{
  __int64 v5; // rdx
  HBITMAP v6; // rax
  HBITMAP v7; // rax
  HBITMAP v8; // rbx
  HMETAFILE *v9; // rax
  HMETAFILE *v10; // rsi
  HMETAFILE v11; // rax
  HBITMAP v13; // rcx
  HBITMAP hBitmap; // rcx
  const unsigned __int16 *lpszFileName; // rcx
  SIZE_T v16; // rbx
  HBITMAP v17; // rax
  HBITMAP v18; // rcx
  HBITMAP v19; // rbx
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rdx
  HBITMAP v22; // rax
  _BYTE v23[16]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v24; // [rsp+50h] [rbp-68h]

  v5 = a1;
  if ( !a2->tymed )
  {
    if ( a3->tymed != 1 )
    {
      switch ( a3->tymed )
      {
        case 2u:
          a2->tymed = 2;
          lpszFileName = a3->lpszFileName;
          if ( !lpszFileName )
            return 0;
          v16 = 2LL * ((unsigned int)ocslen(lpszFileName) + 1);
          v17 = (HBITMAP)CoTaskMemAlloc(v16);
          a2->hBitmap = v17;
          if ( !v17 )
            return 0;
          memcpy_0(v17, a3->hBitmap, v16);
          return 1;
        case 4u:
          hBitmap = a3->hBitmap;
          a2->hBitmap = hBitmap;
          (*(void (__fastcall **)(HBITMAP, __int64))(*(_QWORD *)hBitmap + 8LL))(hBitmap, v5);
          a2->tymed = 4;
          return 1;
        case 8u:
          v13 = a3->hBitmap;
          a2->hBitmap = v13;
          (*(void (__fastcall **)(HBITMAP, __int64))(*(_QWORD *)v13 + 8LL))(v13, v5);
          a2->tymed = 8;
          return 1;
        case 0x10u:
          a2->tymed = 16;
          goto LABEL_10;
        case 0x20u:
          v7 = (HBITMAP)_AfxCopyGlobalMemory(0, a3->hBitmap);
          v8 = v7;
          if ( !v7 )
            return 0;
          v9 = (HMETAFILE *)GlobalLock(v7);
          v10 = v9;
          if ( !v9 )
            return 0;
          v11 = CopyMetaFileW(v9[2], 0);
          v10[2] = v11;
          if ( !v11 )
          {
            GlobalUnlock(v8);
            GlobalFree(v8);
            return 0;
          }
          GlobalUnlock(v8);
          a2->hBitmap = v8;
          a2->tymed = 32;
          return 1;
      }
      if ( a3->tymed != 64 )
        return 0;
    }
    a2->tymed = a3->tymed;
LABEL_10:
    a2->hBitmap = 0;
  }
  switch ( a3->tymed )
  {
    case 1u:
      v22 = (HBITMAP)_AfxCopyGlobalMemory(a2->hBitmap, a3->hBitmap);
      if ( !v22 )
        return 0;
      a2->hBitmap = v22;
      break;
    case 2u:
      v20 = a3->lpszFileName;
      if ( v20 )
      {
        v21 = a2->lpszFileName;
        if ( v21 )
          return CopyFileW(v20, v21, 0);
      }
      return 0;
    case 4u:
      if ( !a2->hBitmap )
        return 0;
      v19 = a3->hBitmap;
      if ( !v19 )
        return 0;
      memset_0(v23, 0, 0x50u);
      if ( (*(unsigned int (__fastcall **)(HBITMAP, _BYTE *, __int64))(*(_QWORD *)v19 + 96LL))(v19, v23, 1) )
        return 0;
      (*(void (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2->hBitmap + 40LL))(a2->hBitmap, 0, 0, 0);
      (*(void (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3->hBitmap + 40LL))(a3->hBitmap, 0, 0, 0);
      if ( (*(unsigned int (__fastcall **)(HBITMAP, HBITMAP, __int64, _QWORD, _QWORD))(*(_QWORD *)a3->hBitmap + 56LL))(
             a3->hBitmap,
             a2->hBitmap,
             v24,
             0,
             0) )
      {
        return 0;
      }
      (*(void (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2->hBitmap + 40LL))(a2->hBitmap, 0, 0, 0);
      (*(void (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3->hBitmap + 40LL))(a3->hBitmap, 0, 0, 0);
      break;
    case 8u:
      if ( !a2->hBitmap )
        return 0;
      v18 = a3->hBitmap;
      if ( !v18
        || (*(unsigned int (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD, HBITMAP))(*(_QWORD *)v18 + 56LL))(
             v18,
             0,
             0,
             0,
             a2->hBitmap) )
      {
        return 0;
      }
      break;
    default:
      if ( (a3->tymed == 16 || a3->tymed == 64) && !a2->hBitmap )
      {
        v6 = (HBITMAP)OleDuplicateData(a3->hBitmap, a1, 0);
        a2->hBitmap = v6;
        if ( v6 )
          return 1;
      }
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180093e40  push    rbx
0x180093e42  push    rsi
0x180093e43  push    rdi
0x180093e44  sub     rsp, 0A0h
0x180093e4b  mov     rax, cs:__security_cookie
0x180093e52  xor     rax, rsp
0x180093e55  mov     [rsp+0B8h+var_28], rax
0x180093e5d  mov     rdi, rdx
0x180093e60  mov     rsi, r8
0x180093e63  movzx   edx, cx; cfFormat
0x180093e66  cmp     dword ptr [rdi], 0
0x180093e69  jnz     short loc_180093EB1
0x180093e6b  mov     ecx, [r8]
0x180093e6e  mov     eax, ecx
0x180093e70  sub     eax, 1
0x180093e73  jz      short loc_180093EA7
0x180093e75  sub     eax, 1
0x180093e78  jz      loc_180093FB4
0x180093e7e  sub     eax, 2
0x180093e81  jz      loc_180093F95
0x180093e87  sub     eax, 4
0x180093e8a  jz      loc_180093F76
0x180093e90  sub     eax, 8
0x180093e93  jz      loc_180093F6B
0x180093e99  sub     eax, 10h
0x180093e9c  jz      short loc_180093F04
0x180093e9e  cmp     eax, 20h ; ' '
0x180093ea1  jnz     loc_180093F4F
0x180093ea7  mov     [rdi], ecx
0x180093ea9  mov     qword ptr [rdi+8], 0
0x180093eb1  mov     ecx, [r8]
0x180093eb4  sub     ecx, 1
0x180093eb7  jz      loc_180094148
0x180093ebd  sub     ecx, 1
0x180093ec0  jz      loc_180094123
0x180093ec6  sub     ecx, 2
0x180093ec9  jz      loc_180094038
0x180093ecf  sub     ecx, 4
0x180093ed2  jz      loc_180093FF8
0x180093ed8  sub     ecx, 8
0x180093edb  jz      short loc_180093EE2
0x180093edd  cmp     ecx, 30h ; '0'
0x180093ee0  jnz     short loc_180093F4F
0x180093ee2  cmp     qword ptr [rdi+8], 0
0x180093ee7  jnz     short loc_180093F4F
0x180093ee9  mov     rcx, [rsi+8]; hSrc
0x180093eed  xor     r8d, r8d; uiFlags
0x180093ef0  call    cs:__imp_OleDuplicateData
0x180093ef6  mov     [rdi+8], rax
0x180093efa  test    rax, rax
0x180093efd  jz      short loc_180093F4F
0x180093eff  jmp     loc_180094162
0x180093f04  mov     rdx, [r8+8]; HGLOBAL
0x180093f08  xor     ecx, ecx; hMem
0x180093f0a  call    ?_AfxCopyGlobalMemory@@YAPEAXPEAX0@Z; _AfxCopyGlobalMemory(void *,void *)
0x180093f0f  mov     rbx, rax
0x180093f12  test    rax, rax
0x180093f15  jz      short loc_180093F4F
0x180093f17  mov     rcx, rax; hMem
0x180093f1a  call    cs:__imp_GlobalLock
0x180093f20  mov     rsi, rax
0x180093f23  test    rax, rax
0x180093f26  jz      short loc_180093F4F
0x180093f28  mov     rcx, [rax+10h]; HMETAFILE
0x180093f2c  xor     edx, edx; LPCWSTR
0x180093f2e  call    cs:__imp_CopyMetaFileW
0x180093f34  mov     [rsi+10h], rax
0x180093f38  mov     rcx, rbx; hMem
0x180093f3b  test    rax, rax
0x180093f3e  jnz     short loc_180093F56
0x180093f40  call    cs:__imp_GlobalUnlock
0x180093f46  mov     rcx, rbx; hMem
0x180093f49  call    cs:__imp_GlobalFree
0x180093f4f  xor     eax, eax
0x180093f51  jmp     loc_180094167
0x180093f56  call    cs:__imp_GlobalUnlock
0x180093f5c  mov     [rdi+8], rbx
0x180093f60  mov     dword ptr [rdi], 20h ; ' '
0x180093f66  jmp     loc_180094162
0x180093f6b  mov     dword ptr [rdi], 10h
0x180093f71  jmp     loc_180093EA9
0x180093f76  mov     rcx, [r8+8]
0x180093f7a  mov     [rdi+8], rcx
0x180093f7e  mov     rax, [rcx]
0x180093f81  mov     rax, [rax+8]
0x180093f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f8a  mov     dword ptr [rdi], 8
0x180093f90  jmp     loc_180094162
0x180093f95  mov     rcx, [r8+8]
0x180093f99  mov     [rdi+8], rcx
0x180093f9d  mov     rax, [rcx]
0x180093fa0  mov     rax, [rax+8]
0x180093fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093fa9  mov     dword ptr [rdi], 4
0x180093faf  jmp     loc_180094162
0x180093fb4  mov     dword ptr [rdi], 2
0x180093fba  mov     rcx, [r8+8]; unsigned __int16 *
0x180093fbe  test    rcx, rcx
0x180093fc1  jz      short loc_180093F4F
0x180093fc3  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180093fc8  lea     ebx, [rax+1]
0x180093fcb  add     rbx, rbx
0x180093fce  mov     rcx, rbx; cb
0x180093fd1  call    cs:__imp_CoTaskMemAlloc
0x180093fd7  mov     [rdi+8], rax
0x180093fdb  test    rax, rax
0x180093fde  jz      loc_180093F4F
0x180093fe4  mov     rdx, [rsi+8]; Src
0x180093fe8  mov     r8, rbx; Size
0x180093feb  mov     rcx, rax; void *
0x180093fee  call    memcpy_0
0x180093ff3  jmp     loc_180094162
0x180093ff8  mov     rdx, [rdi+8]
0x180093ffc  test    rdx, rdx
0x180093fff  jz      loc_180093F4F
0x180094005  mov     rcx, [r8+8]
0x180094009  test    rcx, rcx
0x18009400c  jz      loc_180093F4F
0x180094012  mov     rax, [rcx]
0x180094015  xor     r9d, r9d
0x180094018  mov     [rsp+0B8h+var_98], rdx
0x18009401d  xor     r8d, r8d
0x180094020  xor     edx, edx
0x180094022  mov     rax, [rax+38h]
0x180094026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009402b  test    eax, eax
0x18009402d  jnz     loc_180093F4F
0x180094033  jmp     loc_180094162
0x180094038  cmp     qword ptr [rdi+8], 0
0x18009403d  jz      loc_180093F4F
0x180094043  mov     rbx, [r8+8]
0x180094047  test    rbx, rbx
0x18009404a  jz      loc_180093F4F
0x180094050  xor     edx, edx; Val
0x180094052  lea     rcx, [rsp+0B8h+var_78]; void *
0x180094057  lea     r8d, [rdx+50h]; Size
0x18009405b  call    memset_0
0x180094060  mov     rax, [rbx]
0x180094063  lea     rdx, [rsp+0B8h+var_78]
0x180094068  mov     r8d, 1
0x18009406e  mov     rcx, rbx
0x180094071  mov     rax, [rax+60h]
0x180094075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009407a  test    eax, eax
0x18009407c  jnz     loc_180093F4F
0x180094082  mov     rcx, [rdi+8]
0x180094086  xor     r9d, r9d
0x180094089  mov     [rsp+0B8h+var_88], 0
0x180094092  xor     r8d, r8d
0x180094095  mov     rbx, [rsp+0B8h+var_88]
0x18009409a  mov     rdx, rbx
0x18009409d  mov     rax, [rcx]
0x1800940a0  mov     rax, [rax+28h]
0x1800940a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940a9  mov     rcx, [rsi+8]
0x1800940ad  xor     r9d, r9d
0x1800940b0  xor     r8d, r8d
0x1800940b3  mov     rdx, rbx
0x1800940b6  mov     rax, [rcx]
0x1800940b9  mov     rax, [rax+28h]
0x1800940bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940c2  mov     rcx, [rsi+8]
0x1800940c6  xor     r9d, r9d
0x1800940c9  mov     r8, [rsp+0B8h+var_68]
0x1800940ce  mov     rdx, [rdi+8]
0x1800940d2  mov     [rsp+0B8h+var_98], 0
0x1800940db  mov     rax, [rcx]
0x1800940de  mov     rax, [rax+38h]
0x1800940e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940e7  test    eax, eax
0x1800940e9  jnz     loc_180093F4F
0x1800940ef  mov     rcx, [rdi+8]
0x1800940f3  xor     r9d, r9d
0x1800940f6  xor     r8d, r8d
0x1800940f9  mov     rdx, rbx
0x1800940fc  mov     rax, [rcx]
0x1800940ff  mov     rax, [rax+28h]
0x180094103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094108  mov     rcx, [rsi+8]
0x18009410c  xor     r9d, r9d
0x18009410f  xor     r8d, r8d
0x180094112  mov     rdx, rbx
0x180094115  mov     rax, [rcx]
0x180094118  mov     rax, [rax+28h]
0x18009411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094121  jmp     short loc_180094162
0x180094123  mov     rcx, [r8+8]; lpExistingFileName
0x180094127  test    rcx, rcx
0x18009412a  jz      loc_180093F4F
0x180094130  mov     rdx, [rdi+8]; lpNewFileName
0x180094134  test    rdx, rdx
0x180094137  jz      loc_180093F4F
0x18009413d  xor     r8d, r8d; bFailIfExists
0x180094140  call    cs:__imp_CopyFileW
0x180094146  jmp     short loc_180094167
0x180094148  mov     rdx, [r8+8]; HGLOBAL
0x18009414c  mov     rcx, [rdi+8]; hMem
0x180094150  call    ?_AfxCopyGlobalMemory@@YAPEAXPEAX0@Z; _AfxCopyGlobalMemory(void *,void *)
0x180094155  test    rax, rax
0x180094158  jz      loc_180093F4F
0x18009415e  mov     [rdi+8], rax
0x180094162  mov     eax, 1
0x180094167  mov     rcx, [rsp+0B8h+var_28]
0x18009416f  xor     rcx, rsp; StackCookie
0x180094172  call    __security_check_cookie
0x180094177  add     rsp, 0A0h
0x18009417e  pop     rdi
0x18009417f  pop     rsi
0x180094180  pop     rbx
0x180094181  retn
```
