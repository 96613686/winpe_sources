# VerifyCABIntegrityImp(wchar_t const *)

- ea: `0x14002a8b4`
- end: `0x14002aa61`
- name: `?VerifyCABIntegrityImp@@YAJPEB_W@Z`
- size: `429`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14002bd6c`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000e4d0`
- `0x14000fab0`
- `0x14002a8b4`
- `0x14002e624`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002aa24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002aa33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002aa24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002aa33`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14002aa16`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14002aa16`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14002a9ae`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14002a9ae`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14002a985`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14002a985`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14002a91f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14002a91f`

## pseudocode

```c
__int64 __fastcall VerifyCABIntegrityImp(const wchar_t *a1, __int64 a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  HANDLE FileMappingW; // rbx
  unsigned __int8 *v5; // rdi
  void *FileRetryIfSharingViolation; // rax
  const char *v7; // r9
  void *v8; // rbp
  __int64 v9; // rdx
  int LastError; // eax
  DWORD LowPart; // esi
  unsigned __int8 *v12; // rax
  unsigned int v13; // esi
  int Header; // eax
  unsigned int dwMaximumSizeLow; // [rsp+20h] [rbp-68h]
  int dwMaximumSizeLowa; // [rsp+20h] [rbp-68h]
  void *v18; // [rsp+30h] [rbp-58h]
  unsigned int v19; // [rsp+38h] [rbp-50h]
  void *v20; // [rsp+40h] [rbp-48h]
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileMappingW = 0;
  v5 = 0;
  FileSize.QuadPart = 0;
  FileRetryIfSharingViolation = SusCreateFileRetryIfSharingViolation(a1, 0x80000000, 5u, a4, 3u, 0, v18, v19, v20, 0, 0);
  v8 = FileRetryIfSharingViolation;
  if ( FileRetryIfSharingViolation == (void *)-1LL )
  {
    v9 = 181;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
                  v7);
    goto LABEL_16;
  }
  if ( !GetFileSizeEx(FileRetryIfSharingViolation, &FileSize) )
  {
    v9 = 184;
    goto LABEL_15;
  }
  if ( !FileSize.QuadPart )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xBE,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
                  (const char *)0xDE,
                  dwMaximumSizeLow);
LABEL_16:
    v13 = LastError;
    goto LABEL_19;
  }
  LowPart = 104;
  if ( FileSize.LowPart < 0x68 )
    LowPart = FileSize.LowPart;
  if ( FileSize.HighPart )
    LowPart = 104;
  FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, LowPart, 0);
  if ( !FileMappingW )
  {
    v9 = 204;
    goto LABEL_15;
  }
  v12 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, LowPart);
  v5 = v12;
  if ( !v12 )
  {
    v9 = 212;
    goto LABEL_15;
  }
  Header = StrictReadHeader(v12, LowPart, FileSize.QuadPart);
  v13 = Header;
  if ( Header < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\wutrust\\lib\\trust.cpp",
      (const char *)(unsigned int)Header,
      dwMaximumSizeLowa);
LABEL_19:
    if ( !v5 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v13 = 0;
LABEL_22:
  UnmapViewOfFile(v5);
LABEL_23:
  if ( FileMappingW )
    CloseHandle(FileMappingW);
  if ( v8 != (void *)-1LL )
    CloseHandle(v8);
  return v13;
}

```

## disassembly

```asm
0x14002a8b4  mov     r11, rsp
0x14002a8b7  mov     [r11+10h], rbx
0x14002a8bb  mov     [r11+18h], rbp
0x14002a8bf  mov     [r11+20h], rsi
0x14002a8c3  push    rdi
0x14002a8c4  sub     rsp, 80h
0x14002a8cb  mov     rax, cs:__security_cookie
0x14002a8d2  xor     rax, rsp
0x14002a8d5  mov     [rsp+88h+var_18], rax
0x14002a8da  xor     ebx, ebx
0x14002a8dc  mov     edx, 80000000h; dwDesiredAccess
0x14002a8e1  mov     [rsp+88h+var_38], ebx; unsigned int
0x14002a8e5  xor     edi, edi
0x14002a8e7  mov     [rsp+88h+var_40], ebx; int
0x14002a8eb  mov     dword ptr [rsp+88h+lpName], ebx; DWORD
0x14002a8ef  lea     r8d, [rbx+5]; dwShareMode
0x14002a8f3  mov     [r11-20h], rbx
0x14002a8f7  mov     [rsp+88h+dwMaximumSizeLow], 3; unsigned int
0x14002a8ff  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x14002a904  mov     rbp, rax
0x14002a907  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002a90b  jnz     short loc_14002A917
0x14002a90d  mov     edx, 0B5h
0x14002a912  jmp     loc_14002A9C1
0x14002a917  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x14002a91c  mov     rcx, rbp; hFile
0x14002a91f  call    cs:__imp_GetFileSizeEx
0x14002a925  test    eax, eax
0x14002a927  jnz     short loc_14002A933
0x14002a929  mov     edx, 0B8h
0x14002a92e  jmp     loc_14002A9C1
0x14002a933  mov     rax, qword ptr [rsp+88h+FileSize]
0x14002a938  test    rax, rax
0x14002a93b  jnz     short loc_14002A95D
0x14002a93d  mov     rcx, [rsp+88h]; this
0x14002a945  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x14002a94c  mov     r9d, 0DEh; char *
0x14002a952  lea     edx, [r9-20h]; void *
0x14002a956  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14002a95b  jmp     short loc_14002A9D5
0x14002a95d  mov     ecx, 68h ; 'h'
0x14002a962  mov     [rsp+88h+lpName], rbx; lpName
0x14002a967  cmp     eax, ecx
0x14002a969  mov     esi, ecx
0x14002a96b  cmovb   esi, eax
0x14002a96e  cmp     dword ptr [rsp+88h+FileSize+4], ebx
0x14002a972  lea     r8d, [rcx-66h]; flProtect
0x14002a976  cmovnz  esi, ecx
0x14002a979  xor     r9d, r9d; dwMaximumSizeHigh
0x14002a97c  xor     edx, edx; lpFileMappingAttributes
0x14002a97e  mov     [rsp+88h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x14002a982  mov     rcx, rbp; hFile
0x14002a985  call    cs:__imp_CreateFileMappingW
0x14002a98b  mov     rbx, rax
0x14002a98e  test    rax, rax
0x14002a991  jnz     short loc_14002A99A
0x14002a993  mov     edx, 0CCh
0x14002a998  jmp     short loc_14002A9C1
0x14002a99a  xor     r9d, r9d; dwFileOffsetLow
0x14002a99d  mov     eax, esi
0x14002a99f  xor     r8d, r8d; dwFileOffsetHigh
0x14002a9a2  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rax; int
0x14002a9a7  mov     rcx, rbx; hFileMappingObject
0x14002a9aa  lea     edx, [r9+4]; dwDesiredAccess
0x14002a9ae  call    cs:__imp_MapViewOfFile
0x14002a9b4  mov     rdi, rax
0x14002a9b7  test    rax, rax
0x14002a9ba  jnz     short loc_14002A9D9
0x14002a9bc  mov     edx, 0D4h; void *
0x14002a9c1  mov     rcx, [rsp+88h]; this
0x14002a9c9  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x14002a9d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002a9d5  mov     esi, eax
0x14002a9d7  jmp     short loc_14002AA0A
0x14002a9d9  mov     r8, qword ptr [rsp+88h+FileSize]; __int64
0x14002a9de  mov     edx, esi; unsigned int
0x14002a9e0  mov     rcx, rax; unsigned __int8 *
0x14002a9e3  call    ?StrictReadHeader@@YAJQEAEK_J@Z; StrictReadHeader(uchar * const,ulong,__int64)
0x14002a9e8  mov     esi, eax
0x14002a9ea  test    eax, eax
0x14002a9ec  jns     short loc_14002AA11
0x14002a9ee  mov     rcx, [rsp+88h]; this
0x14002a9f6  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x14002a9fd  mov     r9d, eax; char *
0x14002aa00  mov     edx, 0D6h; void *
0x14002aa05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002aa0a  test    rdi, rdi
0x14002aa0d  jz      short loc_14002AA1C
0x14002aa0f  jmp     short loc_14002AA13
0x14002aa11  xor     esi, esi
0x14002aa13  mov     rcx, rdi; lpBaseAddress
0x14002aa16  call    cs:__imp_UnmapViewOfFile
0x14002aa1c  test    rbx, rbx
0x14002aa1f  jz      short loc_14002AA2A
0x14002aa21  mov     rcx, rbx; hObject
0x14002aa24  call    cs:__imp_CloseHandle
0x14002aa2a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14002aa2e  jz      short loc_14002AA39
0x14002aa30  mov     rcx, rbp; hObject
0x14002aa33  call    cs:__imp_CloseHandle
0x14002aa39  mov     eax, esi
0x14002aa3b  mov     rcx, [rsp+88h+var_18]
0x14002aa40  xor     rcx, rsp; StackCookie
0x14002aa43  call    __security_check_cookie
0x14002aa48  lea     r11, [rsp+88h+var_8]
0x14002aa50  mov     rbx, [r11+18h]
0x14002aa54  mov     rbp, [r11+20h]
0x14002aa58  mov     rsi, [r11+28h]
0x14002aa5c  mov     rsp, r11
0x14002aa5f  pop     rdi
0x14002aa60  retn
```
