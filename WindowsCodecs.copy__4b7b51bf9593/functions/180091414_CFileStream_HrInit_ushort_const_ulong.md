# CFileStream::HrInit(ushort const *,ulong)

- ea: `0x180091414`
- end: `0x1800915de`
- name: `?HrInit@CFileStream@@QEAAJPEBGK@Z`
- size: `458`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180090e80`
- `0x180090f40`

## callees

- `0x180091384`
- `0x180091414`
- `0x1800915e4`
- `0x1800916e0`
- `0x1800bb784`
- `0x1800e4172`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800914b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009154c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800915a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800914b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009154c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800915a3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800915ba`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800915ba`

## pseudocode

```c
__int64 __fastcall CFileStream::HrInit(CFileStream *this, LPCWSTR lpFileName, int a3)
{
  char *v3; // rsi
  unsigned int v7; // ebx
  int v8; // ecx
  int v9; // r14d
  unsigned int v10; // ebx
  int Win32HRESULT; // eax
  HANDLE FileW; // rax

  v3 = (char *)this + 16;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 112LL))((char *)this + 16);
  if ( lpFileName )
  {
    v9 = 0;
    CFileStream::HrClose(this);
    v10 = a3 & 0xC0000000;
    switch ( v10 )
    {
      case 0x40000000u:
        *((_DWORD *)this + 42) = 1;
        FileW = CreateFileW(lpFileName, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
        *((_QWORD *)this + 15) = FileW;
        if ( FileW != (HANDLE)-1LL && !SetEndOfFile(FileW) )
        {
          CloseHandle_0(*((HANDLE *)this + 15));
          *((_QWORD *)this + 15) = -1;
        }
        break;
      case 0x80000000:
        *((_DWORD *)this + 42) = 0;
        *((_QWORD *)this + 15) = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        v9 = 1;
        break;
      case 0xC0000000:
        *((_DWORD *)this + 42) = 2;
        *((_QWORD *)this + 15) = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 4u, 0x80u, 0);
        break;
    }
    if ( *((_QWORD *)this + 15) == -1 )
    {
      Win32HRESULT = GetWin32HRESULT();
      v7 = Win32HRESULT;
      if ( Win32HRESULT < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_5;
        goto LABEL_13;
      }
    }
    else
    {
      *((_BYTE *)this + 112) = 1;
      *((_DWORD *)this + 38) = v9;
    }
    Win32HRESULT = CFileStream::HrCacheFileStats(this, 0);
    v7 = Win32HRESULT;
    if ( Win32HRESULT >= 0 )
      goto LABEL_15;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_5;
LABEL_13:
    v8 = Win32HRESULT;
    goto LABEL_4;
  }
  v7 = -2147024809;
  if ( (_DWORD)g_doStackCaptures )
  {
    v8 = -2147024809;
LABEL_4:
    DoStackCapture(v8);
  }
LABEL_5:
  CFileStream::HrClose(this);
LABEL_15:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 120LL))(v3);
  return v7;
}

```

## disassembly

```asm
0x180091414  push    rbx
0x180091416  push    rbp
0x180091417  push    rsi
0x180091418  push    rdi
0x180091419  push    r14
0x18009141b  sub     rsp, 40h
0x18009141f  lea     rsi, [rcx+10h]
0x180091423  mov     rdi, rcx
0x180091426  mov     rax, [rsi]
0x180091429  mov     rcx, rsi
0x18009142c  mov     ebx, r8d
0x18009142f  mov     rbp, rdx
0x180091432  mov     rax, [rax+70h]
0x180091436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009143b  test    rbp, rbp
0x18009143e  jnz     short loc_180091461
0x180091440  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180091446  mov     ebx, 80070057h
0x18009144b  jz      short loc_180091454
0x18009144d  mov     ecx, ebx; int
0x18009144f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180091454  mov     rcx, rdi; this
0x180091457  call    ?HrClose@CFileStream@@AEAAJXZ; CFileStream::HrClose(void)
0x18009145c  jmp     loc_180091503
0x180091461  mov     rcx, rdi; this
0x180091464  xor     r14d, r14d
0x180091467  call    ?HrClose@CFileStream@@AEAAJXZ; CFileStream::HrClose(void)
0x18009146c  mov     edx, 0C0000000h; dwDesiredAccess
0x180091471  mov     eax, 40000000h
0x180091476  and     ebx, edx
0x180091478  cmp     ebx, eax
0x18009147a  jz      loc_180091578
0x180091480  mov     eax, 80000000h
0x180091485  cmp     ebx, eax
0x180091487  jnz     loc_18009151F
0x18009148d  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180091492  lea     r8d, [r14+1]; dwShareMode
0x180091496  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009149e  xor     r9d, r9d; lpSecurityAttributes
0x1800914a1  mov     edx, eax; dwDesiredAccess
0x1800914a3  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800914ab  mov     rcx, rbp; lpFileName
0x1800914ae  mov     [rdi+0A8h], r14d
0x1800914b5  call    cs:__imp_CreateFileW
0x1800914bb  mov     [rdi+78h], rax
0x1800914bf  mov     r14d, 1
0x1800914c5  cmp     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x1800914ca  jz      loc_18009155B
0x1800914d0  mov     byte ptr [rdi+70h], 1
0x1800914d4  mov     [rdi+98h], r14d
0x1800914db  xor     edx, edx; int
0x1800914dd  mov     rcx, rdi; this
0x1800914e0  call    ?HrCacheFileStats@CFileStream@@AEAAJH@Z; CFileStream::HrCacheFileStats(int)
0x1800914e5  mov     ebx, eax
0x1800914e7  test    eax, eax
0x1800914e9  jns     short loc_180091503
0x1800914eb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800914f2  jz      short loc_1800914FB
0x1800914f4  mov     ecx, eax
0x1800914f6  jmp     loc_18009144F
0x1800914fb  test    eax, eax
0x1800914fd  js      loc_180091454
0x180091503  mov     rdx, [rsi]
0x180091506  mov     rcx, rsi
0x180091509  mov     rax, [rdx+78h]
0x18009150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091512  mov     eax, ebx
0x180091514  add     rsp, 40h
0x180091518  pop     r14
0x18009151a  pop     rdi
0x18009151b  pop     rsi
0x18009151c  pop     rbp
0x18009151d  pop     rbx
0x18009151e  retn
0x18009151f  cmp     ebx, edx
0x180091521  jnz     short loc_1800914C5
0x180091523  xor     r9d, r9d; lpSecurityAttributes
0x180091526  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x18009152b  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180091533  mov     rcx, rbp; lpFileName
0x180091536  mov     dword ptr [rdi+0A8h], 2
0x180091540  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180091548  lea     r8d, [r9+3]; dwShareMode
0x18009154c  call    cs:__imp_CreateFileW
0x180091552  mov     [rdi+78h], rax
0x180091556  jmp     loc_1800914C5
0x18009155b  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x180091560  mov     ebx, eax
0x180091562  test    eax, eax
0x180091564  jns     loc_1800914DB
0x18009156a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180091571  jnz     short loc_1800914F4
0x180091573  jmp     loc_180091454
0x180091578  xor     r9d, r9d; lpSecurityAttributes
0x18009157b  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180091580  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180091588  mov     edx, eax; dwDesiredAccess
0x18009158a  mov     rcx, rbp; lpFileName
0x18009158d  mov     dword ptr [rdi+0A8h], 1
0x180091597  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x18009159f  lea     r8d, [r9+3]; dwShareMode
0x1800915a3  call    cs:__imp_CreateFileW
0x1800915a9  mov     [rdi+78h], rax
0x1800915ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800915b1  jz      loc_1800914C5
0x1800915b7  mov     rcx, rax; hFile
0x1800915ba  call    cs:__imp_SetEndOfFile
0x1800915c0  test    eax, eax
0x1800915c2  jnz     loc_1800914C5
0x1800915c8  mov     rcx, [rdi+78h]; hObject
0x1800915cc  call    CloseHandle_0
0x1800915d1  mov     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x1800915d9  jmp     loc_1800914C5
```
