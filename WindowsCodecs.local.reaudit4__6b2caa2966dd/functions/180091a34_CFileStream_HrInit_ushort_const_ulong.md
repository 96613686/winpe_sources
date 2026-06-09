# CFileStream::HrInit(ushort const *,ulong)

- ea: `0x180091a34`
- end: `0x180091c1b`
- name: `?HrInit@CFileStream@@QEAAJPEBGK@Z`
- size: `487`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800914a0`
- `0x180091560`

## callees

- `0x1800919a4`
- `0x180091a34`
- `0x180091c24`
- `0x180091d24`
- `0x1800bd9d4`
- `0x1800e7062`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091ad5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091b73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091bd4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091ad5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091b73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091bd4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180091bf1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180091bf1`

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
0x180091a34  push    rbx
0x180091a36  push    rbp
0x180091a37  push    rsi
0x180091a38  push    rdi
0x180091a39  push    r14
0x180091a3b  sub     rsp, 40h
0x180091a3f  lea     rsi, [rcx+10h]
0x180091a43  mov     rdi, rcx
0x180091a46  mov     rax, [rsi]
0x180091a49  mov     rcx, rsi
0x180091a4c  mov     ebx, r8d
0x180091a4f  mov     rbp, rdx
0x180091a52  mov     rax, [rax+70h]
0x180091a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a5b  test    rbp, rbp
0x180091a5e  jnz     short loc_180091A81
0x180091a60  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180091a66  mov     ebx, 80070057h
0x180091a6b  jz      short loc_180091A74
0x180091a6d  mov     ecx, ebx; int
0x180091a6f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180091a74  mov     rcx, rdi; this
0x180091a77  call    ?HrClose@CFileStream@@AEAAJXZ; CFileStream::HrClose(void)
0x180091a7c  jmp     loc_180091B29
0x180091a81  mov     rcx, rdi; this
0x180091a84  xor     r14d, r14d
0x180091a87  call    ?HrClose@CFileStream@@AEAAJXZ; CFileStream::HrClose(void)
0x180091a8c  mov     edx, 0C0000000h; dwDesiredAccess
0x180091a91  mov     eax, 40000000h
0x180091a96  and     ebx, edx
0x180091a98  cmp     ebx, eax
0x180091a9a  jz      loc_180091BA9
0x180091aa0  mov     eax, 80000000h
0x180091aa5  cmp     ebx, eax
0x180091aa7  jnz     loc_180091B46
0x180091aad  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180091ab2  lea     r8d, [r14+1]; dwShareMode
0x180091ab6  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180091abe  xor     r9d, r9d; lpSecurityAttributes
0x180091ac1  mov     edx, eax; dwDesiredAccess
0x180091ac3  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180091acb  mov     rcx, rbp; lpFileName
0x180091ace  mov     [rdi+0A8h], r14d
0x180091ad5  call    cs:__imp_CreateFileW
0x180091adc  nop     dword ptr [rax+rax+00h]
0x180091ae1  mov     [rdi+78h], rax
0x180091ae5  mov     r14d, 1
0x180091aeb  cmp     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x180091af0  jz      loc_180091B88
0x180091af6  mov     byte ptr [rdi+70h], 1
0x180091afa  mov     [rdi+98h], r14d
0x180091b01  xor     edx, edx; int
0x180091b03  mov     rcx, rdi; this
0x180091b06  call    ?HrCacheFileStats@CFileStream@@AEAAJH@Z; CFileStream::HrCacheFileStats(int)
0x180091b0b  mov     ebx, eax
0x180091b0d  test    eax, eax
0x180091b0f  jns     short loc_180091B29
0x180091b11  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180091b18  jz      short loc_180091B21
0x180091b1a  mov     ecx, eax
0x180091b1c  jmp     loc_180091A6F
0x180091b21  test    eax, eax
0x180091b23  js      loc_180091A74
0x180091b29  mov     rdx, [rsi]
0x180091b2c  mov     rcx, rsi
0x180091b2f  mov     rax, [rdx+78h]
0x180091b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b38  mov     eax, ebx
0x180091b3a  add     rsp, 40h
0x180091b3e  pop     r14
0x180091b40  pop     rdi
0x180091b41  pop     rsi
0x180091b42  pop     rbp
0x180091b43  pop     rbx
0x180091b44  retn
0x180091b46  cmp     ebx, edx
0x180091b48  jnz     short loc_180091AEB
0x180091b4a  xor     r9d, r9d; lpSecurityAttributes
0x180091b4d  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180091b52  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180091b5a  mov     rcx, rbp; lpFileName
0x180091b5d  mov     dword ptr [rdi+0A8h], 2
0x180091b67  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180091b6f  lea     r8d, [r9+3]; dwShareMode
0x180091b73  call    cs:__imp_CreateFileW
0x180091b7a  nop     dword ptr [rax+rax+00h]
0x180091b7f  mov     [rdi+78h], rax
0x180091b83  jmp     loc_180091AEB
0x180091b88  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x180091b8d  mov     ebx, eax
0x180091b8f  test    eax, eax
0x180091b91  jns     loc_180091B01
0x180091b97  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180091b9e  jnz     loc_180091B1A
0x180091ba4  jmp     loc_180091A74
0x180091ba9  xor     r9d, r9d; lpSecurityAttributes
0x180091bac  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x180091bb1  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180091bb9  mov     edx, eax; dwDesiredAccess
0x180091bbb  mov     rcx, rbp; lpFileName
0x180091bbe  mov     dword ptr [rdi+0A8h], 1
0x180091bc8  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180091bd0  lea     r8d, [r9+3]; dwShareMode
0x180091bd4  call    cs:__imp_CreateFileW
0x180091bdb  nop     dword ptr [rax+rax+00h]
0x180091be0  mov     [rdi+78h], rax
0x180091be4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180091be8  jz      loc_180091AEB
0x180091bee  mov     rcx, rax; hFile
0x180091bf1  call    cs:__imp_SetEndOfFile
0x180091bf8  nop     dword ptr [rax+rax+00h]
0x180091bfd  test    eax, eax
0x180091bff  jnz     loc_180091AEB
0x180091c05  mov     rcx, [rdi+78h]; hObject
0x180091c09  call    CloseHandle_0
0x180091c0e  mov     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x180091c16  jmp     loc_180091AEB
```
