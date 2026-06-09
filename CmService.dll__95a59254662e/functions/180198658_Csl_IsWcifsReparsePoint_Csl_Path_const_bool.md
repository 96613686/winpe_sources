# Csl::IsWcifsReparsePoint(Csl::Path const &,bool &)

- ea: `0x180198658`
- end: `0x180198bf8`
- name: `?IsWcifsReparsePoint@Csl@@YAJAEBVPath@1@AEA_N@Z`
- size: `1440`
- prototype: `__int64 __fastcall(Csl *__hidden this, const struct Path *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path`

## callers

- `0x1800ca424`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x180016774`
- `0x18002f8ac`
- `0x18002fc68`
- `0x180198658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180198992`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18019876d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18019876d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180198721`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801988d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180198721`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801988d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801987a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198a22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198a4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198ae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198b14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198b8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801987a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198a22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198a4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198ae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198b14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180198b8c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019897e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019897e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180198838`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180198838`

## pseudocode

```c
__int64 __fastcall Csl::IsWcifsReparsePoint(Csl *this, const struct Path *a2, struct Path *a3)
{
  int v4; // eax
  unsigned int LastError; // ebx
  WCHAR *v6; // rcx
  HANDLE FileW; // rsi
  const char *v9; // r9
  const char *v10; // r9
  __int64 nFileIndexHigh; // rbx
  __int64 nFileIndexLow; // r15
  _QWORD *v13; // rax
  const char *v14; // r9
  __int64 v15; // rdx
  HANDLE v16; // r14
  unsigned __int64 v17; // r12
  char v18; // r13
  unsigned int *v19; // rax
  unsigned int *v20; // rbx
  const char *v21; // r9
  const char *v22; // r9
  unsigned int *v23; // rax
  const struct std::nothrow_t *v24; // rdx
  unsigned int *v25; // r15
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  unsigned int v28; // r15d
  char *i; // rdx
  char *v30; // rcx
  __int64 v31; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v36[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszVolumeMountPoint[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v38[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  const struct Path *v40; // [rsp+88h] [rbp-78h]
  _QWORD v41[2]; // [rsp+90h] [rbp-70h] BYREF
  char v42[16]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD InBuffer[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h]
  __int64 v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR szVolumeName[56]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v40 = a2;
  lpFileName[0] = v36;
  lpFileName[1] = v36;
  v36[0] = 0;
  v4 = Csl::ConvertToLongPath(this, (const struct Path *)lpFileName, a3);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
    goto LABEL_3;
  }
  FileW = CreateFileW(lpFileName[0], 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x13A,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
                  v9);
    goto LABEL_3;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x140,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
                  v10);
    if ( FileW )
      CloseHandle(FileW);
LABEL_3:
    v6 = (WCHAR *)lpFileName[0];
    if ( lpFileName[0] == v36 )
      return LastError;
LABEL_4:
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  nFileIndexHigh = FileInformation.nFileIndexHigh;
  nFileIndexLow = FileInformation.nFileIndexLow;
  lpszVolumeMountPoint[0] = v38;
  v38[0] = 0;
  lpszVolumeMountPoint[1] = v38;
  v41[0] = this;
  v41[1] = 0;
  v13 = (_QWORD *)Csl::Path::Iterator::operator*(v41, v42);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpszVolumeMountPoint,
                           *v13,
                           v13[1]) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
LABEL_69:
    if ( lpszVolumeMountPoint[0] != v38 )
      operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( FileW )
      CloseHandle(FileW);
    if ( lpFileName[0] != v36 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint[0], szVolumeName, 0x32u) )
  {
    v15 = 332;
    goto LABEL_15;
  }
  szVolumeName[48] = 0;
  v16 = CreateFileW(szVolumeName, 0x80000000, 3u, 0, 3u, 0x2000080u, 0);
  if ( v16 == (HANDLE)-1LL )
  {
    v15 = 347;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
                  v14);
    if ( lpszVolumeMountPoint[0] != v38 )
      operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( FileW )
      CloseHandle(FileW);
    v6 = (WCHAR *)lpFileName[0];
    if ( lpFileName[0] == v36 )
      return LastError;
    goto LABEL_4;
  }
  v44 = 2;
  v17 = 1024;
  v45 = nFileIndexLow | (nFileIndexHigh << 32);
  v18 = 1;
  v46 = v45;
  InBuffer[1] = 16549;
  InBuffer[0] = 1;
  v19 = (unsigned int *)operator new[](0x400u, (const struct std::nothrow_t *)&std::nothrow);
  v20 = v19;
  if ( !v19 )
  {
    v26 = 373;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositionb);
    if ( v16 )
      CloseHandle(v16);
    goto LABEL_69;
  }
  memset_0(v19, 0, 0x400u);
  while ( 1 )
  {
    BytesReturned = 0;
    if ( DeviceIoControl(v16, 0x90277u, InBuffer, 0x20u, v20, v17, &BytesReturned, 0) )
      break;
    if ( GetLastError() != 122 )
    {
      v28 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x191,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
              v22);
      if ( v20 )
        operator delete(v20, v27);
      if ( v16 )
        CloseHandle(v16);
      if ( lpszVolumeMountPoint[0] != v38 )
        operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( FileW )
        CloseHandle(FileW);
      if ( lpFileName[0] != v36 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      return v28;
    }
    v17 *= 2LL;
    v23 = (unsigned int *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
    v25 = v23;
    if ( v23 )
      memset_0(v23, 0, v17);
    else
      v25 = 0;
    if ( v20 )
      operator delete(v20, v24);
    if ( !v25 )
    {
      v26 = 397;
      goto LABEL_67;
    }
    v20 = v25;
  }
  for ( i = (char *)v20 + v20[1] + *(unsigned int *)((char *)v20 + v20[1] + 28);
        *((_DWORD *)i + 1);
        i += *((unsigned int *)i + 1) )
  {
    if ( *((_DWORD *)i + 9) == 192 )
      goto LABEL_52;
  }
  if ( *((_DWORD *)i + 9) != 192 )
  {
    *(_BYTE *)v40 = 0;
    goto LABEL_57;
  }
LABEL_52:
  if ( (i[8] & 0x10) == 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslwcifs.cpp",
      v21);
  v30 = &i[*((unsigned int *)i + 8)];
  v31 = *((unsigned int *)v30 + 4);
  if ( *(_DWORD *)&v30[v31] != -2147483624 && *(_DWORD *)&v30[v31] != -1879044072 )
    v18 = 0;
  *(_BYTE *)v40 = v18;
LABEL_57:
  operator delete(v20, (const struct std::nothrow_t *)i);
  if ( v16 )
    CloseHandle(v16);
  if ( lpszVolumeMountPoint[0] != v38 )
    operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FileW )
    CloseHandle(FileW);
  if ( lpFileName[0] != v36 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180198658  mov     [rsp-8+arg_10], rbx
0x18019865d  push    rbp
0x18019865e  push    rsi
0x18019865f  push    rdi
0x180198660  push    r12
0x180198662  push    r13
0x180198664  push    r14
0x180198666  push    r15
0x180198668  lea     rbp, [rsp-90h]
0x180198670  sub     rsp, 190h
0x180198677  mov     rax, cs:__security_cookie
0x18019867e  xor     rax, rsp
0x180198681  mov     [rbp+0C0h+var_40], rax
0x180198688  lea     rax, [rsp+1C0h+var_170]
0x18019868d  mov     [rbp+0C0h+var_138], rdx
0x180198691  mov     [rsp+1C0h+lpFileName], rax
0x180198696  lea     rdx, [rsp+1C0h+lpFileName]; struct Path *
0x18019869b  lea     rax, [rsp+1C0h+var_170]
0x1801986a0  xor     r12d, r12d
0x1801986a3  mov     [rsp+1C0h+var_178], rax
0x1801986a8  mov     rdi, rcx
0x1801986ab  mov     [rsp+1C0h+var_170], r12w
0x1801986b1  call    ?ConvertToLongPath@Csl@@YAJAEBVPath@1@AEAV21@@Z; Csl::ConvertToLongPath(Csl::Path const &,Csl::Path &)
0x1801986b6  mov     ebx, eax
0x1801986b8  test    eax, eax
0x1801986ba  jns     short loc_1801986F9
0x1801986bc  mov     rcx, [rbp+0C8h]; this
0x1801986c3  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801986ca  mov     r9d, eax; char *
0x1801986cd  mov     edx, 12Eh; void *
0x1801986d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801986d7  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x1801986dc  lea     rax, [rsp+1C0h+var_170]
0x1801986e1  cmp     rcx, rax
0x1801986e4  jz      short loc_1801986F2
0x1801986e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801986ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801986f2  mov     eax, ebx
0x1801986f4  jmp     loc_180198BB4
0x1801986f9  mov     rcx, [rsp+1C0h+lpFileName]; lpFileName
0x1801986fe  mov     r14d, 3
0x180198704  mov     [rsp+1C0h+hTemplateFile], r12; hTemplateFile
0x180198709  xor     r9d, r9d; lpSecurityAttributes
0x18019870c  mov     [rsp+1C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180198714  mov     [rsp+1C0h+dwCreationDisposition], r14d; int
0x180198719  lea     edx, [r14+7Dh]; dwDesiredAccess
0x18019871d  lea     r8d, [r14+4]; dwShareMode
0x180198721  call    cs:__imp_CreateFileW
0x180198728  nop     dword ptr [rax+rax+00h]
0x18019872d  mov     rsi, rax
0x180198730  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180198734  jnz     short loc_180198752
0x180198736  mov     rcx, [rbp+0C8h]; this
0x18019873d  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198744  mov     edx, 13Ah; void *
0x180198749  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019874e  mov     ebx, eax
0x180198750  jmp     short loc_1801986D7
0x180198752  xorps   xmm0, xmm0
0x180198755  lea     rdx, [rbp+0C0h+FileInformation]; lpFileInformation
0x180198759  xor     eax, eax
0x18019875b  mov     rcx, rsi; hFile
0x18019875e  movups  xmmword ptr [rbp+0C0h+FileInformation.dwFileAttributes], xmm0
0x180198762  mov     [rbp+0C0h+FileInformation.nFileIndexLow], eax
0x180198765  movups  xmmword ptr [rbp+0C0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180198769  movups  xmmword ptr [rbp+0C0h+FileInformation.nFileSizeHigh], xmm0
0x18019876d  call    cs:__imp_GetFileInformationByHandle
0x180198774  nop     dword ptr [rax+rax+00h]
0x180198779  test    eax, eax
0x18019877b  jnz     short loc_1801987B4
0x18019877d  mov     rcx, [rbp+0C8h]; this
0x180198784  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019878b  mov     edx, 140h; void *
0x180198790  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180198795  mov     ebx, eax
0x180198797  test    rsi, rsi
0x18019879a  jz      loc_1801986D7
0x1801987a0  mov     rcx, rsi; hObject
0x1801987a3  call    cs:__imp_CloseHandle
0x1801987aa  nop     dword ptr [rax+rax+00h]
0x1801987af  jmp     loc_1801986D7
0x1801987b4  mov     ebx, [rbp+0C0h+FileInformation.nFileIndexHigh]
0x1801987b7  lea     rax, [rsp+1C0h+var_150]
0x1801987bc  mov     r15d, [rbp+0C0h+FileInformation.nFileIndexLow]
0x1801987c0  lea     rdx, [rbp+0C0h+var_120]
0x1801987c4  mov     [rsp+1C0h+lpszVolumeMountPoint], rax
0x1801987c9  lea     rcx, [rbp+0C0h+var_130]
0x1801987cd  lea     rax, [rsp+1C0h+var_150]
0x1801987d2  mov     [rsp+1C0h+var_150], r12w
0x1801987d8  mov     [rsp+1C0h+var_158], rax
0x1801987dd  mov     [rbp+0C0h+var_130], rdi
0x1801987e1  mov     [rbp+0C0h+var_128], r12
0x1801987e5  call    ??DIterator@Path@Csl@@QEBA?AV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@XZ; Csl::Path::Iterator::operator*(void)
0x1801987ea  lea     rcx, [rsp+1C0h+lpszVolumeMountPoint]
0x1801987ef  mov     r8, [rax+8]
0x1801987f3  mov     rdx, [rax]
0x1801987f6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1801987fb  test    al, al
0x1801987fd  jnz     short loc_180198829
0x1801987ff  mov     rcx, [rbp+0C8h]; this
0x180198806  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019880d  mov     r9d, 8007000Eh; char *
0x180198813  mov     edx, 147h; void *
0x180198818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019881d  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180198824  jmp     loc_180198B6D
0x180198829  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x18019882e  lea     rdx, [rbp+0C0h+szVolumeName]; lpszVolumeName
0x180198832  mov     r8d, 32h ; '2'; cchBufferLength
0x180198838  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18019883f  nop     dword ptr [rax+rax+00h]
0x180198844  test    eax, eax
0x180198846  jnz     short loc_1801988AF
0x180198848  mov     edx, 14Ch; void *
0x18019884d  mov     rcx, [rbp+0C8h]; this
0x180198854  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019885b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180198860  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; void *
0x180198865  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18019886c  mov     ebx, eax
0x18019886e  lea     rax, [rsp+1C0h+var_150]
0x180198873  cmp     rcx, rax
0x180198876  jz      short loc_180198880
0x180198878  mov     rdx, rdi; struct std::nothrow_t *
0x18019887b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198880  test    rsi, rsi
0x180198883  jz      short loc_180198894
0x180198885  mov     rcx, rsi; hObject
0x180198888  call    cs:__imp_CloseHandle
0x18019888f  nop     dword ptr [rax+rax+00h]
0x180198894  mov     rcx, [rsp+1C0h+lpFileName]
0x180198899  lea     rax, [rsp+1C0h+var_170]
0x18019889e  cmp     rcx, rax
0x1801988a1  jz      loc_1801986F2
0x1801988a7  mov     rdx, rdi
0x1801988aa  jmp     loc_1801986ED
0x1801988af  mov     [rsp+1C0h+hTemplateFile], r12; hTemplateFile
0x1801988b4  lea     rcx, [rbp+0C0h+szVolumeName]; lpFileName
0x1801988b8  mov     [rsp+1C0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1801988c0  xor     r9d, r9d; lpSecurityAttributes
0x1801988c3  mov     r8d, r14d; dwShareMode
0x1801988c6  mov     [rsp+1C0h+dwCreationDisposition], r14d; int
0x1801988cb  mov     edx, 80000000h; dwDesiredAccess
0x1801988d0  mov     [rbp+0C0h+var_50], r12w
0x1801988d5  call    cs:__imp_CreateFileW
0x1801988dc  nop     dword ptr [rax+rax+00h]
0x1801988e1  mov     r14, rax
0x1801988e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801988e8  jnz     short loc_1801988F4
0x1801988ea  mov     edx, 15Bh
0x1801988ef  jmp     loc_18019884D
0x1801988f4  shl     rbx, 20h
0x1801988f8  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801988ff  or      rbx, r15
0x180198902  mov     [rbp+0C0h+var_108], 2
0x18019890a  mov     r12d, 400h
0x180198910  mov     [rbp+0C0h+var_100], rbx
0x180198914  mov     r13d, 1
0x18019891a  mov     [rbp+0C0h+var_F8], rbx
0x18019891e  mov     rdx, rdi; struct std::nothrow_t *
0x180198921  mov     [rbp+0C0h+var_10C], 40A5h
0x180198928  mov     ecx, r12d; unsigned __int64
0x18019892b  mov     [rbp+0C0h+InBuffer], r13d
0x18019892f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180198934  xor     r15d, r15d
0x180198937  mov     rbx, rax
0x18019893a  test    rax, rax
0x18019893d  jz      loc_180198B3B
0x180198943  mov     r8d, r12d; Size
0x180198946  xor     edx, edx; Val
0x180198948  mov     rcx, rax; void *
0x18019894b  call    memset_0
0x180198950  mov     [rsp+1C0h+lpOverlapped], r15; lpOverlapped
0x180198955  lea     rax, [rbp+0C0h+BytesReturned]
0x180198959  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x18019895e  lea     r8, [rbp+0C0h+InBuffer]; lpInBuffer
0x180198962  mov     [rsp+1C0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x180198967  mov     r9d, 20h ; ' '; nInBufferSize
0x18019896d  mov     edx, 90277h; dwIoControlCode
0x180198972  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rbx; lpOutBuffer
0x180198977  mov     rcx, r14; hDevice
0x18019897a  mov     [rbp+0C0h+BytesReturned], r15d
0x18019897e  call    cs:__imp_DeviceIoControl
0x180198985  nop     dword ptr [rax+rax+00h]
0x18019898a  test    eax, eax
0x18019898c  jnz     loc_180198A78
0x180198992  call    cs:__imp_GetLastError
0x180198999  nop     dword ptr [rax+rax+00h]
0x18019899e  cmp     eax, 7Ah ; 'z'
0x1801989a1  jnz     short loc_1801989F2
0x1801989a3  add     r12, r12
0x1801989a6  mov     rdx, rdi; struct std::nothrow_t *
0x1801989a9  mov     rcx, r12; unsigned __int64
0x1801989ac  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801989b1  mov     r15, rax
0x1801989b4  test    rax, rax
0x1801989b7  jz      short loc_1801989C8
0x1801989b9  mov     r8, r12; Size
0x1801989bc  xor     edx, edx; Val
0x1801989be  mov     rcx, rax; void *
0x1801989c1  call    memset_0
0x1801989c6  jmp     short loc_1801989CB
0x1801989c8  xor     r15d, r15d
0x1801989cb  test    rbx, rbx
0x1801989ce  jz      short loc_1801989D8
0x1801989d0  mov     rcx, rbx; void *
0x1801989d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801989d8  test    r15, r15
0x1801989db  jz      short loc_1801989E8
0x1801989dd  mov     rbx, r15
0x1801989e0  xor     r15d, r15d
0x1801989e3  jmp     loc_180198950
0x1801989e8  mov     edx, 18Dh
0x1801989ed  jmp     loc_180198B40
0x1801989f2  mov     rcx, [rbp+0C8h]; this
0x1801989f9  lea     r8, aOnecoreBaseGen_81; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180198a00  mov     edx, 191h; void *
0x180198a05  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180198a0a  mov     r15d, eax
0x180198a0d  test    rbx, rbx
0x180198a10  jz      short loc_180198A1A
0x180198a12  mov     rcx, rbx; void *
0x180198a15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198a1a  test    r14, r14
0x180198a1d  jz      short loc_180198A2E
0x180198a1f  mov     rcx, r14; hObject
0x180198a22  call    cs:__imp_CloseHandle
0x180198a29  nop     dword ptr [rax+rax+00h]
0x180198a2e  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; void *
0x180198a33  lea     rax, [rsp+1C0h+var_150]
0x180198a38  cmp     rcx, rax
0x180198a3b  jz      short loc_180198A45
0x180198a3d  mov     rdx, rdi; struct std::nothrow_t *
0x180198a40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198a45  test    rsi, rsi
0x180198a48  jz      short loc_180198A59
0x180198a4a  mov     rcx, rsi; hObject
0x180198a4d  call    cs:__imp_CloseHandle
0x180198a54  nop     dword ptr [rax+rax+00h]
0x180198a59  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x180198a5e  lea     rax, [rsp+1C0h+var_170]
0x180198a63  cmp     rcx, rax
0x180198a66  jz      short loc_180198A70
0x180198a68  mov     rdx, rdi; struct std::nothrow_t *
0x180198a6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198a70  mov     eax, r15d
0x180198a73  jmp     loc_180198BB4
0x180198a78  mov     ecx, [rbx+4]
0x180198a7b  add     rcx, rbx
0x180198a7e  mov     edx, [rcx+1Ch]
0x180198a81  add     rdx, rcx
0x180198a84  mov     ecx, 0C0h
0x180198a89  jmp     short loc_180198A96
0x180198a8b  cmp     [rdx+24h], ecx
0x180198a8e  jz      short loc_180198AAA
0x180198a90  mov     eax, [rdx+4]
0x180198a93  add     rdx, rax; struct std::nothrow_t *
0x180198a96  cmp     [rdx+4], r15d
0x180198a9a  jnz     short loc_180198A8B
0x180198a9c  cmp     [rdx+24h], ecx
0x180198a9f  jz      short loc_180198AAA
0x180198aa1  mov     rax, [rbp+0C0h+var_138]
0x180198aa5  mov     [rax], r15b
0x180198aa8  jmp     short loc_180198AD9
0x180198aaa  test    byte ptr [rdx+8], 10h
0x180198aae  jz      loc_180198BDF
0x180198ab4  mov     ecx, [rdx+20h]
0x180198ab7  add     rcx, rdx
0x180198aba  mov     eax, [rcx+10h]
0x180198abd  cmp     dword ptr [rax+rcx], 80000018h
0x180198ac4  jz      short loc_180198AD2
0x180198ac6  cmp     dword ptr [rax+rcx], 90001018h
0x180198acd  jz      short loc_180198AD2
0x180198acf  mov     r13b, r15b
0x180198ad2  mov     rax, [rbp+0C0h+var_138]
0x180198ad6  mov     [rax], r13b
0x180198ad9  mov     rcx, rbx; void *
0x180198adc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198ae1  test    r14, r14
0x180198ae4  jz      short loc_180198AF5
0x180198ae6  mov     rcx, r14; hObject
0x180198ae9  call    cs:__imp_CloseHandle
0x180198af0  nop     dword ptr [rax+rax+00h]
0x180198af5  mov     rcx, [rsp+1C0h+lpszVolumeMountPoint]; void *
0x180198afa  lea     rax, [rsp+1C0h+var_150]
0x180198aff  cmp     rcx, rax
0x180198b02  jz      short loc_180198B0C
0x180198b04  mov     rdx, rdi; struct std::nothrow_t *
0x180198b07  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180198b0c  test    rsi, rsi
0x180198b0f  jz      short loc_180198B20
0x180198b11  mov     rcx, rsi; hObject
0x180198b14  call    cs:__imp_CloseHandle
0x180198b1b  nop     dword ptr [rax+rax+00h]
0x180198b20  mov     rcx, [rsp+1C0h+lpFileName]; void *
0x180198b25  lea     rax, [rsp+1C0h+var_170]
0x180198b2a  cmp     rcx, rax
0x180198b2d  jz      short loc_180198B37
0x180198b2f  mov     rdx, rdi; struct std::nothrow_t *
0x180198b32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
  ... truncated ...
```
