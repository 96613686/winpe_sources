# Microsoft::Diagnostics::IdleDiskResource::SetupHandle(void)

- ea: `0x1801b1240`
- end: `0x1801b15c5`
- name: `?SetupHandle@IdleDiskResource@Diagnostics@Microsoft@@EEAAXXZ`
- size: `901`
- prototype: `void __fastcall(Microsoft::Diagnostics::IdleDiskResource *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001b510`
- `0x18002b9c0`
- `0x18002df00`
- `0x1800b1300`
- `0x1800bc658`
- `0x1800f7b34`
- `0x1800fbba0`
- `0x1801a9494`
- `0x1801b1240`
- `0x1801b1838`
- `0x1801b2084`
- `0x18020aac0`
- `0x18020afa4`
- `0x18020d8b8`
- `0x1802a8344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1379`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b12f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b14a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b12f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b14a3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b136b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b1407`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b136b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b1407`

## string_xrefs

- `0x1801b12be`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x1801b1317`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x1801b13a7`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x1801b1415`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x1801b159e`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x1801b15b3`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::Diagnostics::IdleDiskResource::SetupHandle(Microsoft::Diagnostics::IdleDiskResource *this)
{
  WCHAR *v2; // rax
  wchar_t *v3; // rcx
  int v4; // eax
  const WCHAR *v5; // rcx
  char *FileW; // rbx
  const char *v7; // r9
  unsigned int *v8; // rdi
  const struct std::nothrow_t *v9; // rdx
  signed int LastError; // eax
  char v11; // cl
  const struct std::nothrow_t *v12; // rdx
  unsigned int *v13; // rsi
  unsigned int *v14; // rcx
  const char *v15; // r9
  unsigned int i; // ebx
  wchar_t *v17; // rax
  int v18; // eax
  const WCHAR *v19; // rcx
  const char *v20; // r9
  const wchar_t *v21; // rax
  __int64 v22; // rcx
  int v23; // ecx
  int dwCreationDisposition; // [rsp+20h] [rbp-A9h]
  char *dwCreationDispositiona; // [rsp+20h] [rbp-A9h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-A9h]
  DWORD BytesReturned; // [rsp+40h] [rbp-89h] BYREF
  LPVOID lpOutBuffer; // [rsp+48h] [rbp-81h] BYREF
  char *v29; // [rsp+50h] [rbp-79h] BYREF
  char *v30; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR v31[2]; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v32; // [rsp+70h] [rbp-59h]
  unsigned __int64 v33; // [rsp+78h] [rbp-51h]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int64 v35; // [rsp+90h] [rbp-39h]
  unsigned __int64 v36; // [rsp+98h] [rbp-31h]
  WCHAR Buffer[12]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v38; // [rsp+B8h] [rbp-11h]
  char v39; // [rsp+C0h] [rbp-9h] BYREF
  const wchar_t *v40; // [rsp+D0h] [rbp+7h]
  int v41; // [rsp+D8h] [rbp+Fh]
  int v42; // [rsp+DCh] [rbp+13h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  Microsoft::Diagnostics::Utils::FileSystem::GetSystemPath(Buffer);
  std::wstring::wstring(lpFileName, 10, 0);
  v2 = Buffer;
  if ( v38 > 7 )
    v2 = *(WCHAR **)Buffer;
  v3 = (wchar_t *)lpFileName;
  if ( v36 > 7 )
    v3 = (wchar_t *)lpFileName[0];
  v4 = StringCchPrintfW(v3, (unsigned int)v35, L"\\\\.\\%c:", *v2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
  v5 = (const WCHAR *)lpFileName;
  if ( v36 > 7 )
    v5 = lpFileName[0];
  FileW = (char *)CreateFileW(v5, 0, 3u, 0, 3u, 0, 0);
  v30 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
      v7);
  std::make_unique<unsigned char [0],0>(&lpOutBuffer, 32);
  BytesReturned = 0;
  v8 = (unsigned int *)lpOutBuffer;
  if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, lpOutBuffer, 0x20u, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 122 || (v11 = 1, LastError == 234) )
      v11 = 0;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        (const char *)(unsigned int)LastError,
        (int)dwCreationDispositiona);
    v13 = (unsigned int *)operator new[](BytesReturned);
    v14 = v8;
    v8 = v13;
    lpOutBuffer = v13;
    if ( v14 )
      operator delete(v14, v12);
    if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, v13, BytesReturned, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        v15);
  }
  for ( i = 0; i < *v8; ++i )
  {
    std::wstring::wstring(v31, 260, 0);
    v17 = (wchar_t *)v31;
    if ( v33 > 7 )
      v17 = (wchar_t *)v31[0];
    v18 = StringCchPrintfW(v17, (unsigned int)v32, L"\\\\.\\PhysicalDrive%u", v8[6 * i + 2], dwCreationDispositiona);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDispositionb);
    v19 = (const WCHAR *)v31;
    if ( v33 > 7 )
      v19 = v31[0];
    v29 = (char *)CreateFileW(v19, 0, 3u, 0, 3u, 0, 0);
    if ( (unsigned __int64)(v29 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        v20);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
      (char *)this + 56,
      &v29);
    if ( (Microsoft_Windows_Diagnostics_PerfTrackEnableBits & 8) != 0 )
    {
      v21 = (const wchar_t *)v31;
      if ( v33 > 7 )
        v21 = v31[0];
      if ( v21 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v21[v22] );
        v23 = 2 * v22 + 2;
      }
      else
      {
        v21 = L"NULL";
        v23 = 10;
      }
      v40 = v21;
      v41 = v23;
      v42 = 0;
      dwCreationDispositiona = &v39;
      McGenEventWrite_EventWriteTransfer(PerfTrackScenarioProvider_Context, IdleDetection_Disk_OpenedDisk);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
    std::wstring::_Tidy_deallocate(v31);
  }
  std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpOutBuffer, v9);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
  std::wstring::_Tidy_deallocate(lpFileName);
  std::wstring::_Tidy_deallocate(Buffer);
}

```

## disassembly

```asm
0x1801b1240  push    rbp
0x1801b1242  push    rbx
0x1801b1243  push    rsi
0x1801b1244  push    rdi
0x1801b1245  push    r14
0x1801b1247  push    r15
0x1801b1249  lea     rbp, [rsp-2Fh]
0x1801b124e  sub     rsp, 0F8h
0x1801b1255  mov     rax, cs:__security_cookie
0x1801b125c  xor     rax, rsp
0x1801b125f  mov     [rbp+57h+var_40], rax
0x1801b1263  mov     r14, rcx
0x1801b1266  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1801b126a  call    ?GetSystemPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetSystemPath(void)
0x1801b126f  nop
0x1801b1270  xor     r8d, r8d
0x1801b1273  lea     edx, [r8+0Ah]
0x1801b1277  lea     rcx, [rbp+57h+lpFileName]
0x1801b127b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801b1280  nop
0x1801b1281  lea     rax, [rbp+57h+Buffer]
0x1801b1285  cmp     [rbp+57h+var_68], 7
0x1801b128a  cmova   rax, qword ptr [rbp+57h+Buffer]
0x1801b128f  movzx   r9d, word ptr [rax]
0x1801b1293  mov     edx, dword ptr [rbp+57h+var_90]; unsigned __int64
0x1801b1296  lea     rcx, [rbp+57h+lpFileName]
0x1801b129a  cmp     [rbp+57h+var_88], 7
0x1801b129f  cmova   rcx, [rbp+57h+lpFileName]; wchar_t *
0x1801b12a4  lea     r8, aC; "\\\\.\\%c:"
0x1801b12ab  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b12b0  mov     rcx, [rbp+5Fh]; this
0x1801b12b4  xor     r15d, r15d
0x1801b12b7  test    eax, eax
0x1801b12b9  jns     short loc_1801B12CF
0x1801b12bb  mov     r9d, eax; char *
0x1801b12be  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x1801b12c5  lea     edx, [r15+27h]; void *
0x1801b12c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b12cf  lea     rcx, [rbp+57h+lpFileName]
0x1801b12d3  cmp     [rbp+57h+var_88], 7
0x1801b12d8  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801b12dd  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x1801b12e2  mov     [rsp+120h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801b12e7  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x1801b12ef  xor     r9d, r9d; lpSecurityAttributes
0x1801b12f2  xor     edx, edx; dwDesiredAccess
0x1801b12f4  lea     r8d, [r9+3]; dwShareMode
0x1801b12f8  call    cs:__imp_CreateFileW
0x1801b12fe  mov     rbx, rax
0x1801b1301  mov     [rbp+57h+var_C8], rax
0x1801b1305  dec     rax
0x1801b1308  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801b130c  setnbe  al
0x1801b130f  mov     rcx, [rbp+5Fh]; this
0x1801b1313  test    al, al
0x1801b1315  jz      short loc_1801B1329
0x1801b1317  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x1801b131e  mov     edx, 2Bh ; '+'; void *
0x1801b1323  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801b1329  mov     edi, 20h ; ' '
0x1801b132e  mov     edx, edi
0x1801b1330  lea     rcx, [rsp+120h+lpOutBuffer]
0x1801b1335  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1801b133a  nop
0x1801b133b  mov     [rsp+120h+BytesReturned], r15d
0x1801b1340  mov     [rsp+120h+lpOverlapped], r15; lpOverlapped
0x1801b1345  lea     rax, [rsp+120h+BytesReturned]
0x1801b134a  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x1801b134f  mov     [rsp+120h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1801b1353  mov     rdi, [rsp+120h+lpOutBuffer]
0x1801b1358  mov     qword ptr [rsp+120h+dwCreationDisposition], rdi; int
0x1801b135d  xor     r9d, r9d; nInBufferSize
0x1801b1360  xor     r8d, r8d; lpInBuffer
0x1801b1363  mov     edx, 560000h; dwIoControlCode
0x1801b1368  mov     rcx, rbx; hDevice
0x1801b136b  call    cs:__imp_DeviceIoControl
0x1801b1371  test    eax, eax
0x1801b1373  jnz     loc_1801B1425
0x1801b1379  call    cs:__imp_GetLastError
0x1801b137f  cmp     eax, 7Ah ; 'z'
0x1801b1382  jz      short loc_1801B138D
0x1801b1384  cmp     eax, 0EAh
0x1801b1389  mov     cl, 1
0x1801b138b  jnz     short loc_1801B1390
0x1801b138d  mov     cl, r15b
0x1801b1390  test    eax, eax
0x1801b1392  jle     short loc_1801B139C
0x1801b1394  movzx   eax, ax
0x1801b1397  or      eax, 80070000h
0x1801b139c  mov     r10, [rbp+5Fh]
0x1801b13a0  test    cl, cl
0x1801b13a2  jz      short loc_1801B13BC
0x1801b13a4  mov     r9d, eax; char *
0x1801b13a7  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x1801b13ae  mov     edx, 33h ; '3'; void *
0x1801b13b3  mov     rcx, r10; this
0x1801b13b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b13bc  mov     ecx, [rsp+120h+BytesReturned]; unsigned __int64
0x1801b13c0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801b13c5  mov     rsi, rax
0x1801b13c8  mov     rcx, rdi; void *
0x1801b13cb  mov     rdi, rax
0x1801b13ce  mov     [rsp+120h+lpOutBuffer], rax
0x1801b13d3  test    rcx, rcx
0x1801b13d6  jz      short loc_1801B13DD
0x1801b13d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b13dd  mov     ecx, [rsp+120h+BytesReturned]
0x1801b13e1  mov     [rsp+120h+lpOverlapped], r15; lpOverlapped
0x1801b13e6  lea     rax, [rsp+120h+BytesReturned]
0x1801b13eb  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x1801b13f0  mov     [rsp+120h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1801b13f4  mov     qword ptr [rsp+120h+dwCreationDisposition], rsi; lpOutBuffer
0x1801b13f9  xor     r9d, r9d; nInBufferSize
0x1801b13fc  xor     r8d, r8d; lpInBuffer
0x1801b13ff  mov     edx, 560000h; dwIoControlCode
0x1801b1404  mov     rcx, rbx; hDevice
0x1801b1407  call    cs:__imp_DeviceIoControl
0x1801b140d  test    eax, eax
0x1801b140f  jnz     short loc_1801B1425
0x1801b1411  mov     rcx, [rbp+5Fh]; this
0x1801b1415  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x1801b141c  lea     edx, [rax+39h]; void *
0x1801b141f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801b1425  mov     ebx, r15d
0x1801b1428  cmp     [rdi], r15d
0x1801b142b  jbe     loc_1801B155A
0x1801b1431  xor     r8d, r8d
0x1801b1434  mov     edx, 104h
0x1801b1439  lea     rcx, [rbp+57h+var_C0]
0x1801b143d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801b1442  nop
0x1801b1443  mov     eax, ebx
0x1801b1445  lea     rcx, [rax+rax*2]
0x1801b1449  mov     edx, dword ptr [rbp+57h+var_B0]; unsigned __int64
0x1801b144c  lea     rax, [rbp+57h+var_C0]
0x1801b1450  cmp     [rbp+57h+var_A8], 7
0x1801b1455  cmova   rax, [rbp+57h+var_C0]
0x1801b145a  mov     r9d, [rdi+rcx*8+8]
0x1801b145f  lea     r8, aPhysicaldriveU; "\\\\.\\PhysicalDrive%u"
0x1801b1466  mov     rcx, rax; wchar_t *
0x1801b1469  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b146e  mov     rcx, [rbp+5Fh]; this
0x1801b1472  test    eax, eax
0x1801b1474  js      loc_1801B15B0
0x1801b147a  lea     rcx, [rbp+57h+var_C0]
0x1801b147e  cmp     [rbp+57h+var_A8], 7
0x1801b1483  cmova   rcx, [rbp+57h+var_C0]; lpFileName
0x1801b1488  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x1801b148d  mov     [rsp+120h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801b1492  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x1801b149a  xor     r9d, r9d; lpSecurityAttributes
0x1801b149d  xor     edx, edx; dwDesiredAccess
0x1801b149f  lea     r8d, [r9+3]; dwShareMode
0x1801b14a3  call    cs:__imp_CreateFileW
0x1801b14a9  mov     [rbp+57h+var_D0], rax
0x1801b14ad  dec     rax
0x1801b14b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801b14b4  setnbe  al
0x1801b14b7  mov     rcx, [rbp+5Fh]; this
0x1801b14bb  test    al, al
0x1801b14bd  jnz     loc_1801B159E
0x1801b14c3  lea     rcx, [r14+38h]
0x1801b14c7  lea     rdx, [rbp+57h+var_D0]
0x1801b14cb  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801b14d0  test    cs:Microsoft_Windows_Diagnostics_PerfTrackEnableBits, 8
0x1801b14d7  jz      short loc_1801B153D
0x1801b14d9  lea     rax, [rbp+57h+var_C0]
0x1801b14dd  cmp     [rbp+57h+var_A8], 7
0x1801b14e2  cmova   rax, [rbp+57h+var_C0]
0x1801b14e7  test    rax, rax
0x1801b14ea  jz      short loc_1801B1503
0x1801b14ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801b14f0  inc     rcx
0x1801b14f3  cmp     [rax+rcx*2], r15w
0x1801b14f8  jnz     short loc_1801B14F0
0x1801b14fa  lea     ecx, ds:2[rcx*2]
0x1801b1501  jmp     short loc_1801B150F
0x1801b1503  lea     rax, aNull_1; "NULL"
0x1801b150a  mov     ecx, 0Ah
0x1801b150f  mov     [rbp+57h+var_50], rax
0x1801b1513  mov     [rbp+57h+var_48], ecx
0x1801b1516  mov     [rbp+57h+var_44], r15d
0x1801b151a  lea     rax, [rbp+57h+var_60]
0x1801b151e  mov     qword ptr [rsp+120h+dwCreationDisposition], rax
0x1801b1523  mov     r9d, 2
0x1801b1529  lea     rdx, IdleDetection_Disk_OpenedDisk
0x1801b1530  lea     rcx, PerfTrackScenarioProvider_Context
0x1801b1537  call    McGenEventWrite_EventWriteTransfer
0x1801b153c  nop
0x1801b153d  lea     rcx, [rbp+57h+var_D0]
0x1801b1541  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801b1546  nop
0x1801b1547  lea     rcx, [rbp+57h+var_C0]
0x1801b154b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b1550  inc     ebx
0x1801b1552  cmp     ebx, [rdi]
0x1801b1554  jb      loc_1801B1431
0x1801b155a  lea     rcx, [rsp+120h+lpOutBuffer]
0x1801b155f  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801b1564  nop
0x1801b1565  lea     rcx, [rbp+57h+var_C8]
0x1801b1569  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801b156e  nop
0x1801b156f  lea     rcx, [rbp+57h+lpFileName]
0x1801b1573  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b1578  nop
0x1801b1579  lea     rcx, [rbp+57h+Buffer]
0x1801b157d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b1582  mov     rcx, [rbp+57h+var_40]
0x1801b1586  xor     rcx, rsp; StackCookie
0x1801b1589  call    __security_check_cookie
0x1801b158e  add     rsp, 0F8h
0x1801b1595  pop     r15
0x1801b1597  pop     r14
0x1801b1599  pop     rdi
0x1801b159a  pop     rsi
0x1801b159b  pop     rbx
0x1801b159c  pop     rbp
0x1801b159d  retn
0x1801b159e  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x1801b15a5  mov     edx, 47h ; 'G'; void *
0x1801b15aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801b15b0  mov     r9d, eax; char *
0x1801b15b3  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x1801b15ba  mov     edx, 43h ; 'C'; void *
0x1801b15bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
