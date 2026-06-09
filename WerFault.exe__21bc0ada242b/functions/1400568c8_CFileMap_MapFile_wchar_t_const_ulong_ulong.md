# CFileMap::MapFile(wchar_t const *,ulong,ulong)

- ea: `0x1400568c8`
- end: `0x140056ab3`
- name: `?MapFile@CFileMap@@QEAAJPEB_WKK@Z`
- size: `491`
- prototype: `__int64 __fastcall(CFileMap *this, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400366a0`
- `0x140036754`

## callees

- `0x14000d28c`
- `0x14001444c`
- `0x1400568c8`
- `0x140056abc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005693f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005693f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056a76`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140056959`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140056959`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005692d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400569e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005692d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400569e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140056917`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140056917`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140056a28`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140056a28`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400569c9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400569c9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140056a3b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140056a3b`

## pseudocode

```c
__int64 __fastcall CFileMap::MapFile(CFileMap *this, LPCWSTR lpFileName)
{
  unsigned int i; // ebx
  HANDLE FileW; // rax
  void *v6; // rcx
  DWORD LastError; // eax
  HANDLE FileMappingW; // rax
  void *v9; // rcx
  void *v10; // rcx
  CUserModeHangReport *v11; // rcx
  __int64 v12; // rdx
  LPVOID v13; // rax
  const void *v14; // rcx
  signed int v15; // eax
  signed int v16; // ebx

  CFileMap::UnmapFile(this);
  for ( i = 0; i < 5; ++i )
  {
    if ( *(_QWORD *)this != -1 && *(_QWORD *)this != 0 )
      break;
    FileW = CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 8u, 0);
    v6 = *(void **)this;
    *(_QWORD *)this = FileW;
    if ( (unsigned __int64)v6 + 1 > 1 )
      CloseHandle(v6);
    if ( *(_QWORD *)this != -1 && *(_QWORD *)this != 0 )
      break;
    LastError = GetLastError();
    if ( LastError - 32 > 1 && LastError != 54 )
      break;
    Sleep(0xFAu);
  }
  if ( (unsigned __int64)(*(_QWORD *)this + 1LL) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_167d0cd1f28e300fdfc5af1fac4c821a_Traceguids, lpFileName);
    }
    goto LABEL_26;
  }
  FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, 8u, 0, 0x2000u, 0);
  v9 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = FileMappingW;
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  v10 = (void *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)v10 + 1 <= 1 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_26;
    }
    v12 = 11;
    goto LABEL_25;
  }
  v13 = MapViewOfFile(v10, 1u, 0, 0, 0);
  v14 = (const void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v13;
  if ( v14 )
    UnmapViewOfFile(v14);
  if ( *((_QWORD *)this + 2) )
    return 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 12;
LABEL_25:
    WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_167d0cd1f28e300fdfc5af1fac4c821a_Traceguids);
  }
LABEL_26:
  v15 = GetLastError();
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  if ( v16 >= 0 )
    v16 = -2147467259;
  CFileMap::UnmapFile(this);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400568c8  mov     [rsp+arg_0], rbx
0x1400568cd  mov     [rsp+arg_8], rsi
0x1400568d2  push    rdi
0x1400568d3  sub     rsp, 40h
0x1400568d7  mov     rsi, rdx
0x1400568da  mov     rdi, rcx
0x1400568dd  call    ?UnmapFile@CFileMap@@QEAAXXZ; CFileMap::UnmapFile(void)
0x1400568e2  xor     ebx, ebx
0x1400568e4  mov     rax, [rdi]
0x1400568e7  inc     rax
0x1400568ea  cmp     rax, 1
0x1400568ee  ja      short loc_140056964
0x1400568f0  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1400568f9  xor     r9d, r9d; lpSecurityAttributes
0x1400568fc  mov     [rsp+48h+dwFlagsAndAttributes], 8; dwFlagsAndAttributes
0x140056904  xor     r8d, r8d; dwShareMode
0x140056907  mov     edx, 80000000h; dwDesiredAccess
0x14005690c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140056914  mov     rcx, rsi; lpFileName
0x140056917  call    cs:__imp_CreateFileW
0x14005691d  mov     rcx, [rdi]; hObject
0x140056920  mov     [rdi], rax
0x140056923  lea     rax, [rcx+1]
0x140056927  cmp     rax, 1
0x14005692b  jbe     short loc_140056933
0x14005692d  call    cs:__imp_CloseHandle
0x140056933  mov     rax, [rdi]
0x140056936  inc     rax
0x140056939  cmp     rax, 1
0x14005693d  ja      short loc_140056964
0x14005693f  call    cs:__imp_GetLastError
0x140056945  lea     ecx, [rax-20h]
0x140056948  cmp     ecx, 1
0x14005694b  jbe     short loc_140056952
0x14005694d  cmp     eax, 36h ; '6'
0x140056950  jnz     short loc_140056964
0x140056952  mov     ecx, 0FAh; dwMilliseconds
0x140056957  inc     ebx
0x140056959  call    cs:__imp_Sleep
0x14005695f  cmp     ebx, 5
0x140056962  jb      short loc_1400568E4
0x140056964  mov     rcx, [rdi]; hFile
0x140056967  lea     rax, [rcx+1]
0x14005696b  cmp     rax, 1
0x14005696f  ja      short loc_1400569AF
0x140056971  mov     rcx, cs:WPP_GLOBAL_Control
0x140056978  lea     rax, WPP_GLOBAL_Control
0x14005697f  cmp     rcx, rax
0x140056982  jz      loc_140056A76
0x140056988  test    byte ptr [rcx+1Ch], 1
0x14005698c  jz      loc_140056A76
0x140056992  mov     rcx, [rcx+10h]
0x140056996  lea     r8, WPP_167d0cd1f28e300fdfc5af1fac4c821a_Traceguids
0x14005699d  mov     edx, 0Ah
0x1400569a2  mov     r9, rsi
0x1400569a5  call    WPP_SF_S
0x1400569aa  jmp     loc_140056A76
0x1400569af  xor     r9d, r9d; dwMaximumSizeHigh
0x1400569b2  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1400569bb  xor     edx, edx; lpFileMappingAttributes
0x1400569bd  mov     [rsp+48h+dwCreationDisposition], 2000h; dwMaximumSizeLow
0x1400569c5  lea     r8d, [r9+8]; flProtect
0x1400569c9  call    cs:__imp_CreateFileMappingW
0x1400569cf  mov     rcx, [rdi+8]; hObject
0x1400569d3  mov     [rdi+8], rax
0x1400569d7  lea     rax, [rcx+1]
0x1400569db  cmp     rax, 1
0x1400569df  jbe     short loc_1400569E7
0x1400569e1  call    cs:__imp_CloseHandle
0x1400569e7  mov     rcx, [rdi+8]; hFileMappingObject
0x1400569eb  lea     rax, [rcx+1]
0x1400569ef  cmp     rax, 1
0x1400569f3  ja      short loc_140056A15
0x1400569f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400569fc  lea     rax, WPP_GLOBAL_Control
0x140056a03  cmp     rcx, rax
0x140056a06  jz      short loc_140056A76
0x140056a08  test    byte ptr [rcx+1Ch], 1
0x140056a0c  jz      short loc_140056A76
0x140056a0e  mov     edx, 0Bh
0x140056a13  jmp     short loc_140056A66
0x140056a15  xor     r9d, r9d; dwFileOffsetLow
0x140056a18  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140056a21  xor     r8d, r8d; dwFileOffsetHigh
0x140056a24  lea     edx, [r9+1]; dwDesiredAccess
0x140056a28  call    cs:__imp_MapViewOfFile
0x140056a2e  mov     rcx, [rdi+10h]; lpBaseAddress
0x140056a32  mov     [rdi+10h], rax
0x140056a36  test    rcx, rcx
0x140056a39  jz      short loc_140056A41
0x140056a3b  call    cs:__imp_UnmapViewOfFile
0x140056a41  cmp     qword ptr [rdi+10h], 0
0x140056a46  jnz     short loc_140056A9F
0x140056a48  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a4f  lea     rax, WPP_GLOBAL_Control
0x140056a56  cmp     rcx, rax
0x140056a59  jz      short loc_140056A76
0x140056a5b  test    byte ptr [rcx+1Ch], 1
0x140056a5f  jz      short loc_140056A76
0x140056a61  mov     edx, 0Ch
0x140056a66  mov     rcx, [rcx+10h]
0x140056a6a  lea     r8, WPP_167d0cd1f28e300fdfc5af1fac4c821a_Traceguids
0x140056a71  call    WPP_SF_
0x140056a76  call    cs:__imp_GetLastError
0x140056a7c  mov     ebx, eax
0x140056a7e  test    eax, eax
0x140056a80  jle     short loc_140056A8B
0x140056a82  movzx   ebx, ax
0x140056a85  or      ebx, 80070000h
0x140056a8b  test    ebx, ebx
0x140056a8d  mov     eax, 80004005h
0x140056a92  mov     rcx, rdi; this
0x140056a95  cmovns  ebx, eax
0x140056a98  call    ?UnmapFile@CFileMap@@QEAAXXZ; CFileMap::UnmapFile(void)
0x140056a9d  jmp     short loc_140056AA1
0x140056a9f  xor     ebx, ebx
0x140056aa1  mov     rsi, [rsp+48h+arg_8]
0x140056aa6  mov     eax, ebx
0x140056aa8  mov     rbx, [rsp+48h+arg_0]
0x140056aad  add     rsp, 40h
0x140056ab1  pop     rdi
0x140056ab2  retn
```
