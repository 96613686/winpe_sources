# StatePaths::CreateWPSystemAndSIDFolders(Common::Deployment::Volume const *,ushort const *)

- ea: `0x18009fd0c`
- end: `0x1800a0052`
- name: `?CreateWPSystemAndSIDFolders@StatePaths@@YAJPEBVVolume@Deployment@Common@@PEBG@Z`
- size: `838`
- prototype: `int(StatePaths *__hidden this, const struct Common::Deployment::Volume *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18009e800`

## callees

- `0x180012964`
- `0x180063820`
- `0x1800926d4`
- `0x180098bf4`
- `0x18009fd0c`
- `0x1800a021c`
- `0x1800f0260`
- `0x1801e7774`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fe3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0024`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fe3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ffcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0024`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009fdd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ff09`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009fdd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009ff09`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18009fe12`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18009ff47`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18009fe12`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18009ff47`

## string_xrefs

- `0x18009fd79`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009fdf0`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009fe23`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009fe62`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009fea0`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009ff24`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009ff58`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009ffa6`: `onecore\admin\appmodel\common\statepaths.cpp`
- `0x18009fff7`: `onecore\admin\appmodel\common\statepaths.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StatePaths::CreateWPSystemAndSIDFolders(
        StatePaths *this,
        const struct Common::Deployment::Volume *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rdx
  int DirectoryIfNecessary; // ebx
  __int64 v7; // rdx
  HANDLE FileW; // rbx
  const char *v10; // r9
  const char *v11; // r9
  int LastError; // edi
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdx
  HANDLE v15; // rdi
  const char *v16; // r9
  const unsigned __int16 *v17; // r8
  const char *v18; // r9
  unsigned int v19; // esi
  int v20; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  _OWORD FileInformation[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+70h] [rbp-90h]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset(FileInformation, 0, sizeof(FileInformation));
  v25 = 0;
  DirectoryIfNecessary = StringCchPrintfW(FileName, 0x104u, L"%s\\WpSystem", *((_QWORD *)this + 5));
  if ( DirectoryIfNecessary < 0 )
  {
    v7 = 792;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)DirectoryIfNecessary,
      dwCreationDisposition);
    return (unsigned int)DirectoryIfNecessary;
  }
  DirectoryIfNecessary = Common::CreateDirectoryIfNecessary((Common *)FileName, v5);
  if ( DirectoryIfNecessary < 0 )
  {
    v7 = 793;
    goto LABEL_3;
  }
  FileW = CreateFileW(FileName, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x31D,
             (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
             v10);
  if ( !GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x31E,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
                  v11);
LABEL_10:
    if ( FileW )
      CloseHandle(FileW);
    return (unsigned int)LastError;
  }
  if ( (FileInformation[0] & 0x400) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationDispositiona);
LABEL_34:
    if ( FileW )
      CloseHandle(FileW);
    return 2147549183LL;
  }
  LastError = StringCchCatW(FileName, 0x104u, L"\\");
  if ( LastError < 0 )
  {
    v13 = 802;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)LastError,
      dwCreationDispositiona);
    goto LABEL_10;
  }
  LastError = StringCchCatW(FileName, 0x104u, (const unsigned __int16 *)a2);
  if ( LastError < 0 )
  {
    v13 = 803;
    goto LABEL_17;
  }
  LastError = Common::CreateDirectoryIfNecessary((Common *)FileName, v14);
  if ( LastError < 0 )
  {
    v13 = 804;
    goto LABEL_17;
  }
  v15 = CreateFileW(FileName, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
  if ( v15 == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x328,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
                  v16);
    goto LABEL_10;
  }
  if ( !GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation) )
  {
    v19 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x329,
            (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
            v18);
LABEL_26:
    if ( v15 )
      CloseHandle(v15);
    if ( FileW )
      CloseHandle(FileW);
    return v19;
  }
  if ( (FileInformation[0] & 0x400) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32A,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)0x8000FFFFLL,
      dwCreationDispositionb);
    if ( v15 )
      CloseHandle(v15);
    goto LABEL_34;
  }
  v20 = StatePaths::ApplyWPSystemAndSIDFoldersACLs(this, a2, v17);
  v19 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecore\\admin\\appmodel\\common\\statepaths.cpp",
      (const char *)(unsigned int)v20,
      dwCreationDispositionb);
    goto LABEL_26;
  }
  if ( v15 )
    CloseHandle(v15);
  if ( FileW )
    CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x18009fd0c  mov     [rsp-8+arg_10], rbx
0x18009fd11  push    rbp
0x18009fd12  push    rsi
0x18009fd13  push    rdi
0x18009fd14  push    r12
0x18009fd16  push    r14
0x18009fd18  lea     rbp, [rsp-1A0h]
0x18009fd20  sub     rsp, 2A0h
0x18009fd27  mov     rax, cs:__security_cookie
0x18009fd2e  xor     rax, rsp
0x18009fd31  mov     [rbp+1C0h+var_30], rax
0x18009fd38  mov     rsi, rdx
0x18009fd3b  mov     r14, rcx
0x18009fd3e  xorps   xmm0, xmm0
0x18009fd41  xor     eax, eax
0x18009fd43  movups  [rsp+2C0h+FileInformation], xmm0
0x18009fd48  movups  [rsp+2C0h+var_260], xmm0
0x18009fd4d  mov     [rsp+2C0h+var_250], eax
0x18009fd51  mov     r9, [rcx+28h]
0x18009fd55  lea     r8, aSWpsystem; "%s\\WpSystem"
0x18009fd5c  mov     r12d, 104h
0x18009fd62  mov     edx, r12d; unsigned __int64
0x18009fd65  lea     rcx, [rbp+1C0h+FileName]; Buffer
0x18009fd69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009fd6e  mov     ebx, eax
0x18009fd70  test    eax, eax
0x18009fd72  jns     short loc_18009FD96
0x18009fd74  mov     edx, 318h; void *
0x18009fd79  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009fd80  mov     r9d, ebx; char *
0x18009fd83  mov     rcx, [rbp+1C8h]; this
0x18009fd8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fd8f  mov     eax, ebx
0x18009fd91  jmp     loc_1800A002C
0x18009fd96  lea     rcx, [rbp+1C0h+FileName]; this
0x18009fd9a  call    ?CreateDirectoryIfNecessary@Common@@YAJPEBG@Z; Common::CreateDirectoryIfNecessary(ushort const *)
0x18009fd9f  mov     ebx, eax
0x18009fda1  test    eax, eax
0x18009fda3  jns     short loc_18009FDAC
0x18009fda5  mov     edx, 319h
0x18009fdaa  jmp     short loc_18009FD79
0x18009fdac  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18009fdb5  mov     [rsp+2C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18009fdbd  mov     [rsp+2C0h+dwCreationDisposition], 3; int
0x18009fdc5  xor     r9d, r9d; lpSecurityAttributes
0x18009fdc8  mov     edx, 80000000h; dwDesiredAccess
0x18009fdcd  lea     r8d, [r9+5]; dwShareMode
0x18009fdd1  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18009fdd5  call    cs:__imp_CreateFileW
0x18009fddb  mov     rbx, rax
0x18009fdde  mov     [rsp+2C0h+var_280], rax
0x18009fde3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009fde7  jnz     short loc_18009FE07
0x18009fde9  mov     rcx, [rbp+1C8h]; this
0x18009fdf0  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009fdf7  mov     edx, 31Dh; void *
0x18009fdfc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009fe01  nop
0x18009fe02  jmp     loc_1800A002C
0x18009fe07  lea     r8, [rsp+2C0h+FileInformation]; lpFileInformation
0x18009fe0c  xor     edx, edx; fInfoLevelId
0x18009fe0e  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18009fe12  call    cs:__imp_GetFileAttributesExW
0x18009fe18  test    eax, eax
0x18009fe1a  jnz     short loc_18009FE4B
0x18009fe1c  mov     rcx, [rbp+1C8h]; this
0x18009fe23  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009fe2a  mov     edx, 31Eh; void *
0x18009fe2f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009fe34  mov     edi, eax
0x18009fe36  test    rbx, rbx
0x18009fe39  jz      short loc_18009FE44
0x18009fe3b  mov     rcx, rbx; hObject
0x18009fe3e  call    cs:__imp_CloseHandle
0x18009fe44  mov     eax, edi
0x18009fe46  jmp     loc_1800A002C
0x18009fe4b  test    dword ptr [rsp+2C0h+FileInformation], 400h
0x18009fe53  jz      short loc_18009FE78
0x18009fe55  mov     rcx, [rbp+1C8h]; this
0x18009fe5c  mov     r9d, 8000FFFFh; char *
0x18009fe62  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009fe69  mov     edx, 31Fh; void *
0x18009fe6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fe73  jmp     loc_18009FFC7
0x18009fe78  lea     r8, asc_1802323F0; "\\"
0x18009fe7f  mov     rdx, r12; unsigned __int64
0x18009fe82  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18009fe86  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009fe8b  mov     edi, eax
0x18009fe8d  test    eax, eax
0x18009fe8f  jns     short loc_18009FEAE
0x18009fe91  mov     edx, 322h; void *
0x18009fe96  mov     rcx, [rbp+1C8h]; this
0x18009fe9d  mov     r9d, edi; char *
0x18009fea0  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009fea7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009feac  jmp     short loc_18009FE36
0x18009feae  mov     r8, rsi; unsigned __int16 *
0x18009feb1  mov     rdx, r12; unsigned __int64
0x18009feb4  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18009feb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009febd  mov     edi, eax
0x18009febf  test    eax, eax
0x18009fec1  jns     short loc_18009FECA
0x18009fec3  mov     edx, 323h
0x18009fec8  jmp     short loc_18009FE96
0x18009feca  lea     rcx, [rbp+1C0h+FileName]; this
0x18009fece  call    ?CreateDirectoryIfNecessary@Common@@YAJPEBG@Z; Common::CreateDirectoryIfNecessary(ushort const *)
0x18009fed3  mov     edi, eax
0x18009fed5  test    eax, eax
0x18009fed7  jns     short loc_18009FEE0
0x18009fed9  mov     edx, 324h
0x18009fede  jmp     short loc_18009FE96
0x18009fee0  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18009fee9  mov     [rsp+2C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18009fef1  mov     [rsp+2C0h+dwCreationDisposition], 3; int
0x18009fef9  xor     r9d, r9d; lpSecurityAttributes
0x18009fefc  mov     edx, 80000000h; dwDesiredAccess
0x18009ff01  lea     r8d, [r9+5]; dwShareMode
0x18009ff05  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18009ff09  call    cs:__imp_CreateFileW
0x18009ff0f  mov     rdi, rax
0x18009ff12  mov     [rsp+2C0h+var_278], rax
0x18009ff17  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009ff1b  jnz     short loc_18009FF3C
0x18009ff1d  mov     rcx, [rbp+1C8h]; this
0x18009ff24  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009ff2b  mov     edx, 328h; void *
0x18009ff30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009ff35  mov     edi, eax
0x18009ff37  jmp     loc_18009FE36
0x18009ff3c  lea     r8, [rsp+2C0h+FileInformation]; lpFileInformation
0x18009ff41  xor     edx, edx; fInfoLevelId
0x18009ff43  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18009ff47  call    cs:__imp_GetFileAttributesExW
0x18009ff4d  test    eax, eax
0x18009ff4f  jnz     short loc_18009FF8F
0x18009ff51  mov     rcx, [rbp+1C8h]; this
0x18009ff58  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009ff5f  mov     edx, 329h; void *
0x18009ff64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009ff69  mov     esi, eax
0x18009ff6b  test    rdi, rdi
0x18009ff6e  jz      short loc_18009FF7A
0x18009ff70  mov     rcx, rdi; hObject
0x18009ff73  call    cs:__imp_CloseHandle
0x18009ff79  nop
0x18009ff7a  test    rbx, rbx
0x18009ff7d  jz      short loc_18009FF88
0x18009ff7f  mov     rcx, rbx; hObject
0x18009ff82  call    cs:__imp_CloseHandle
0x18009ff88  mov     eax, esi
0x18009ff8a  jmp     loc_1800A002C
0x18009ff8f  test    dword ptr [rsp+2C0h+FileInformation], 400h
0x18009ff97  jz      short loc_18009FFDC
0x18009ff99  mov     rcx, [rbp+1C8h]; this
0x18009ffa0  mov     r9d, 8000FFFFh; char *
0x18009ffa6  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009ffad  mov     edx, 32Ah; void *
0x18009ffb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ffb7  nop
0x18009ffb8  test    rdi, rdi
0x18009ffbb  jz      short loc_18009FFC7
0x18009ffbd  mov     rcx, rdi; hObject
0x18009ffc0  call    cs:__imp_CloseHandle
0x18009ffc6  nop
0x18009ffc7  test    rbx, rbx
0x18009ffca  jz      short loc_18009FFD5
0x18009ffcc  mov     rcx, rbx; hObject
0x18009ffcf  call    cs:__imp_CloseHandle
0x18009ffd5  mov     eax, 8000FFFFh
0x18009ffda  jmp     short loc_1800A002C
0x18009ffdc  mov     rdx, rsi; struct Common::Deployment::Volume *
0x18009ffdf  mov     rcx, r14; this
0x18009ffe2  call    ?ApplyWPSystemAndSIDFoldersACLs@StatePaths@@YAJPEBVVolume@Deployment@Common@@PEBG@Z; StatePaths::ApplyWPSystemAndSIDFoldersACLs(Common::Deployment::Volume const *,ushort const *)
0x18009ffe7  mov     esi, eax
0x18009ffe9  test    eax, eax
0x18009ffeb  jns     short loc_1800A000D
0x18009ffed  mov     rcx, [rbp+1C8h]; this
0x18009fff4  mov     r9d, eax; char *
0x18009fff7  lea     r8, aOnecoreAdminAp_53; "onecore\\admin\\appmodel\\common\\state"...
0x18009fffe  mov     edx, 32Ch; void *
0x1800a0003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0008  jmp     loc_18009FF6B
0x1800a000d  test    rdi, rdi
0x1800a0010  jz      short loc_1800A001C
0x1800a0012  mov     rcx, rdi; hObject
0x1800a0015  call    cs:__imp_CloseHandle
0x1800a001b  nop
0x1800a001c  test    rbx, rbx
0x1800a001f  jz      short loc_1800A002A
0x1800a0021  mov     rcx, rbx; hObject
0x1800a0024  call    cs:__imp_CloseHandle
0x1800a002a  xor     eax, eax
0x1800a002c  mov     rcx, [rbp+1C0h+var_30]
0x1800a0033  xor     rcx, rsp; StackCookie
0x1800a0036  call    __security_check_cookie
0x1800a003b  mov     rbx, [rsp+2C0h+arg_10]
0x1800a0043  add     rsp, 2A0h
0x1800a004a  pop     r14
0x1800a004c  pop     r12
0x1800a004e  pop     rdi
0x1800a004f  pop     rsi
0x1800a0050  pop     rbp
0x1800a0051  retn
```
