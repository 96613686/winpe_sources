# CFileMap::MapFile(wchar_t const *,ulong,ulong)

- ea: `0x14005a460`
- end: `0x14005a68a`
- name: `?MapFile@CFileMap@@QEAAJPEB_WKK@Z`
- size: `554`
- prototype: `__int64 __fastcall(CFileMap *__hidden this, LPCWSTR lpFileName, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140038c4c`
- `0x140038d00`

## callees

- `0x14000d544`
- `0x140014ee4`
- `0x14005a460`
- `0x14005a690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a4e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a4e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005a646`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14005a507`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14005a507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a4cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a59f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a4cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005a59f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005a4b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14005a4b3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005a5ec`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14005a5ec`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14005a581`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14005a581`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005a605`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14005a605`

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
0x14005a460  mov     [rsp+arg_0], rbx
0x14005a465  mov     [rsp+arg_8], rsi
0x14005a46a  push    rdi
0x14005a46b  sub     rsp, 40h
0x14005a46f  mov     rsi, rdx
0x14005a472  mov     rdi, rcx
0x14005a475  call    ?UnmapFile@CFileMap@@QEAAXXZ; CFileMap::UnmapFile(void)
0x14005a47a  xor     ebx, ebx
0x14005a47c  mov     rax, [rdi]
0x14005a47f  inc     rax
0x14005a482  cmp     rax, 1
0x14005a486  ja      loc_14005A51C
0x14005a48c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14005a495  xor     r9d, r9d; lpSecurityAttributes
0x14005a498  mov     [rsp+48h+dwFlagsAndAttributes], 8; dwFlagsAndAttributes
0x14005a4a0  xor     r8d, r8d; dwShareMode
0x14005a4a3  mov     edx, 80000000h; dwDesiredAccess
0x14005a4a8  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14005a4b0  mov     rcx, rsi; lpFileName
0x14005a4b3  call    cs:__imp_CreateFileW
0x14005a4ba  nop     dword ptr [rax+rax+00h]
0x14005a4bf  mov     rcx, [rdi]; hObject
0x14005a4c2  mov     [rdi], rax
0x14005a4c5  lea     rax, [rcx+1]
0x14005a4c9  cmp     rax, 1
0x14005a4cd  jbe     short loc_14005A4DB
0x14005a4cf  call    cs:__imp_CloseHandle
0x14005a4d6  nop     dword ptr [rax+rax+00h]
0x14005a4db  mov     rax, [rdi]
0x14005a4de  inc     rax
0x14005a4e1  cmp     rax, 1
0x14005a4e5  ja      short loc_14005A51C
0x14005a4e7  call    cs:__imp_GetLastError
0x14005a4ee  nop     dword ptr [rax+rax+00h]
0x14005a4f3  lea     ecx, [rax-20h]
0x14005a4f6  cmp     ecx, 1
0x14005a4f9  jbe     short loc_14005A500
0x14005a4fb  cmp     eax, 36h ; '6'
0x14005a4fe  jnz     short loc_14005A51C
0x14005a500  mov     ecx, 0FAh; dwMilliseconds
0x14005a505  inc     ebx
0x14005a507  call    cs:__imp_Sleep
0x14005a50e  nop     dword ptr [rax+rax+00h]
0x14005a513  cmp     ebx, 5
0x14005a516  jb      loc_14005A47C
0x14005a51c  mov     rcx, [rdi]; hFile
0x14005a51f  lea     rax, [rcx+1]
0x14005a523  cmp     rax, 1
0x14005a527  ja      short loc_14005A567
0x14005a529  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a530  lea     rax, WPP_GLOBAL_Control
0x14005a537  cmp     rcx, rax
0x14005a53a  jz      loc_14005A646
0x14005a540  test    byte ptr [rcx+1Ch], 1
0x14005a544  jz      loc_14005A646
0x14005a54a  mov     rcx, [rcx+10h]
0x14005a54e  lea     r8, WPP_167d0cd1f28e300fdfc5af1fac4c821a_Traceguids
0x14005a555  mov     edx, 0Ah
0x14005a55a  mov     r9, rsi
0x14005a55d  call    WPP_SF_S
0x14005a562  jmp     loc_14005A646
0x14005a567  xor     r9d, r9d; dwMaximumSizeHigh
0x14005a56a  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x14005a573  xor     edx, edx; lpFileMappingAttributes
0x14005a575  mov     [rsp+48h+dwCreationDisposition], 2000h; dwMaximumSizeLow
0x14005a57d  lea     r8d, [r9+8]; flProtect
0x14005a581  call    cs:__imp_CreateFileMappingW
0x14005a588  nop     dword ptr [rax+rax+00h]
0x14005a58d  mov     rcx, [rdi+8]; hObject
0x14005a591  mov     [rdi+8], rax
0x14005a595  lea     rax, [rcx+1]
0x14005a599  cmp     rax, 1
0x14005a59d  jbe     short loc_14005A5AB
0x14005a59f  call    cs:__imp_CloseHandle
0x14005a5a6  nop     dword ptr [rax+rax+00h]
0x14005a5ab  mov     rcx, [rdi+8]; hFileMappingObject
0x14005a5af  lea     rax, [rcx+1]
0x14005a5b3  cmp     rax, 1
0x14005a5b7  ja      short loc_14005A5D9
0x14005a5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a5c0  lea     rax, WPP_GLOBAL_Control
0x14005a5c7  cmp     rcx, rax
0x14005a5ca  jz      short loc_14005A646
0x14005a5cc  test    byte ptr [rcx+1Ch], 1
0x14005a5d0  jz      short loc_14005A646
0x14005a5d2  mov     edx, 0Bh
0x14005a5d7  jmp     short loc_14005A636
0x14005a5d9  xor     r9d, r9d; dwFileOffsetLow
0x14005a5dc  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x14005a5e5  xor     r8d, r8d; dwFileOffsetHigh
0x14005a5e8  lea     edx, [r9+1]; dwDesiredAccess
0x14005a5ec  call    cs:__imp_MapViewOfFile
0x14005a5f3  nop     dword ptr [rax+rax+00h]
0x14005a5f8  mov     rcx, [rdi+10h]; lpBaseAddress
0x14005a5fc  mov     [rdi+10h], rax
0x14005a600  test    rcx, rcx
0x14005a603  jz      short loc_14005A611
0x14005a605  call    cs:__imp_UnmapViewOfFile
0x14005a60c  nop     dword ptr [rax+rax+00h]
0x14005a611  cmp     qword ptr [rdi+10h], 0
0x14005a616  jnz     short loc_14005A675
0x14005a618  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a61f  lea     rax, WPP_GLOBAL_Control
0x14005a626  cmp     rcx, rax
0x14005a629  jz      short loc_14005A646
0x14005a62b  test    byte ptr [rcx+1Ch], 1
0x14005a62f  jz      short loc_14005A646
0x14005a631  mov     edx, 0Ch
0x14005a636  mov     rcx, [rcx+10h]
0x14005a63a  lea     r8, WPP_167d0cd1f28e300fdfc5af1fac4c821a_Traceguids
0x14005a641  call    WPP_SF_
0x14005a646  call    cs:__imp_GetLastError
0x14005a64d  nop     dword ptr [rax+rax+00h]
0x14005a652  mov     ebx, eax
0x14005a654  test    eax, eax
0x14005a656  jle     short loc_14005A661
0x14005a658  movzx   ebx, ax
0x14005a65b  or      ebx, 80070000h
0x14005a661  test    ebx, ebx
0x14005a663  mov     eax, 80004005h
0x14005a668  mov     rcx, rdi; this
0x14005a66b  cmovns  ebx, eax
0x14005a66e  call    ?UnmapFile@CFileMap@@QEAAXXZ; CFileMap::UnmapFile(void)
0x14005a673  jmp     short loc_14005A677
0x14005a675  xor     ebx, ebx
0x14005a677  mov     rsi, [rsp+48h+arg_8]
0x14005a67c  mov     eax, ebx
0x14005a67e  mov     rbx, [rsp+48h+arg_0]
0x14005a683  add     rsp, 40h
0x14005a687  pop     rdi
0x14005a688  retn
```
