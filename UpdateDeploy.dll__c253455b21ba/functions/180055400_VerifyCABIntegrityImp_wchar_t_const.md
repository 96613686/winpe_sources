# VerifyCABIntegrityImp(wchar_t const *)

- ea: `0x180055400`
- end: `0x1800555ad`
- name: `?VerifyCABIntegrityImp@@YAJPEB_W@Z`
- size: `429`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800568c4`

## callees

- `0x180002214`
- `0x180003180`
- `0x180009438`
- `0x180049e88`
- `0x180055400`
- `0x1800587c8`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005557f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005557f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800554fa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800554fa`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800554d1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800554d1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180055562`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180055562`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005546b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005546b`

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
0x180055400  mov     r11, rsp
0x180055403  mov     [r11+10h], rbx
0x180055407  mov     [r11+18h], rbp
0x18005540b  mov     [r11+20h], rsi
0x18005540f  push    rdi
0x180055410  sub     rsp, 80h
0x180055417  mov     rax, cs:__security_cookie
0x18005541e  xor     rax, rsp
0x180055421  mov     [rsp+88h+var_18], rax
0x180055426  xor     ebx, ebx
0x180055428  mov     edx, 80000000h; dwDesiredAccess
0x18005542d  mov     [rsp+88h+var_38], ebx; unsigned int
0x180055431  xor     edi, edi
0x180055433  mov     [rsp+88h+var_40], ebx; int
0x180055437  mov     dword ptr [rsp+88h+lpName], ebx; DWORD
0x18005543b  lea     r8d, [rbx+5]; dwShareMode
0x18005543f  mov     [r11-20h], rbx
0x180055443  mov     [rsp+88h+dwMaximumSizeLow], 3; unsigned int
0x18005544b  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x180055450  mov     rbp, rax
0x180055453  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055457  jnz     short loc_180055463
0x180055459  mov     edx, 0B5h
0x18005545e  jmp     loc_18005550D
0x180055463  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x180055468  mov     rcx, rbp; hFile
0x18005546b  call    cs:__imp_GetFileSizeEx
0x180055471  test    eax, eax
0x180055473  jnz     short loc_18005547F
0x180055475  mov     edx, 0B8h
0x18005547a  jmp     loc_18005550D
0x18005547f  mov     rax, qword ptr [rsp+88h+FileSize]
0x180055484  test    rax, rax
0x180055487  jnz     short loc_1800554A9
0x180055489  mov     rcx, [rsp+88h]; this
0x180055491  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x180055498  mov     r9d, 0DEh; char *
0x18005549e  lea     edx, [r9-20h]; void *
0x1800554a2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800554a7  jmp     short loc_180055521
0x1800554a9  mov     ecx, 68h ; 'h'
0x1800554ae  mov     [rsp+88h+lpName], rbx; lpName
0x1800554b3  cmp     eax, ecx
0x1800554b5  mov     esi, ecx
0x1800554b7  cmovb   esi, eax
0x1800554ba  cmp     dword ptr [rsp+88h+FileSize+4], ebx
0x1800554be  lea     r8d, [rcx-66h]; flProtect
0x1800554c2  cmovnz  esi, ecx
0x1800554c5  xor     r9d, r9d; dwMaximumSizeHigh
0x1800554c8  xor     edx, edx; lpFileMappingAttributes
0x1800554ca  mov     [rsp+88h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x1800554ce  mov     rcx, rbp; hFile
0x1800554d1  call    cs:__imp_CreateFileMappingW
0x1800554d7  mov     rbx, rax
0x1800554da  test    rax, rax
0x1800554dd  jnz     short loc_1800554E6
0x1800554df  mov     edx, 0CCh
0x1800554e4  jmp     short loc_18005550D
0x1800554e6  xor     r9d, r9d; dwFileOffsetLow
0x1800554e9  mov     eax, esi
0x1800554eb  xor     r8d, r8d; dwFileOffsetHigh
0x1800554ee  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rax; int
0x1800554f3  mov     rcx, rbx; hFileMappingObject
0x1800554f6  lea     edx, [r9+4]; dwDesiredAccess
0x1800554fa  call    cs:__imp_MapViewOfFile
0x180055500  mov     rdi, rax
0x180055503  test    rax, rax
0x180055506  jnz     short loc_180055525
0x180055508  mov     edx, 0D4h; void *
0x18005550d  mov     rcx, [rsp+88h]; this
0x180055515  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x18005551c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055521  mov     esi, eax
0x180055523  jmp     short loc_180055556
0x180055525  mov     r8, qword ptr [rsp+88h+FileSize]; __int64
0x18005552a  mov     edx, esi; unsigned int
0x18005552c  mov     rcx, rax; unsigned __int8 *
0x18005552f  call    ?StrictReadHeader@@YAJQEAEK_J@Z; StrictReadHeader(uchar * const,ulong,__int64)
0x180055534  mov     esi, eax
0x180055536  test    eax, eax
0x180055538  jns     short loc_18005555D
0x18005553a  mov     rcx, [rsp+88h]; this
0x180055542  lea     r8, aCW1SSrcClientW; "C:\\__w\\1\\s\\src\\Client\\wutrust\\li"...
0x180055549  mov     r9d, eax; char *
0x18005554c  mov     edx, 0D6h; void *
0x180055551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055556  test    rdi, rdi
0x180055559  jz      short loc_180055568
0x18005555b  jmp     short loc_18005555F
0x18005555d  xor     esi, esi
0x18005555f  mov     rcx, rdi; lpBaseAddress
0x180055562  call    cs:__imp_UnmapViewOfFile
0x180055568  test    rbx, rbx
0x18005556b  jz      short loc_180055576
0x18005556d  mov     rcx, rbx; hObject
0x180055570  call    cs:__imp_CloseHandle
0x180055576  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18005557a  jz      short loc_180055585
0x18005557c  mov     rcx, rbp; hObject
0x18005557f  call    cs:__imp_CloseHandle
0x180055585  mov     eax, esi
0x180055587  mov     rcx, [rsp+88h+var_18]
0x18005558c  xor     rcx, rsp; StackCookie
0x18005558f  call    __security_check_cookie
0x180055594  lea     r11, [rsp+88h+var_8]
0x18005559c  mov     rbx, [r11+18h]
0x1800555a0  mov     rbp, [r11+20h]
0x1800555a4  mov     rsi, [r11+28h]
0x1800555a8  mov     rsp, r11
0x1800555ab  pop     rdi
0x1800555ac  retn
```
