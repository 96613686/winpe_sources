# HttpResponse::DownloadResponseToFileWithProgress(ushort const *,int *)

- ea: `0x1801dc654`
- end: `0x1801dca63`
- name: `?DownloadResponseToFileWithProgress@HttpResponse@@QEAA_KPEBGPEAH@Z`
- size: `1039`
- prototype: `unsigned __int64(HttpResponse *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18007f214`

## callees

- `0x18000ab18`
- `0x180010b54`
- `0x18002ec10`
- `0x18002ec2c`
- `0x18003748c`
- `0x180072420`
- `0x1801dc654`
- `0x180215010`

## import_xrefs

- `WINHTTP!WinHttpQueryHeaders` at `0x1801dc722`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801dc722`
- `WINHTTP!WinHttpReadData` at `0x1801dc817`
- `WINHTTP!WinHttpReadData` at `0x1801dc817`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801dc901`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801dc901`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801dc6c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801dc6c2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801dc77d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801dc7c7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801dc77d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801dc7c7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1801dc796`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1801dc796`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801dc879`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801dc879`

## string_xrefs

- `0x1801dc913`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dc992`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dc9a4`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dc9b6`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dc9cb`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dc9e0`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dca00`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dca11`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dca28`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dca39`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x1801dca50`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
union _LARGE_INTEGER __fastcall HttpResponse::DownloadResponseToFileWithProgress(
        HINTERNET *this,
        const unsigned __int16 *a2,
        int *a3)
{
  char *FileW; // rbx
  const char *v7; // r9
  bool v8; // zf
  unsigned int v9; // eax
  union _LARGE_INTEGER v10; // r12
  void (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void *v12; // rdi
  const char *v13; // r9
  const char *v14; // r9
  union _LARGE_INTEGER v15; // r13
  const char *v17; // r9
  const char *v19; // r9
  char v20; // al
  const char *v21; // r9
  int v22; // edx
  unsigned __int64 v23; // rax
  BOOL v24; // eax
  const char *v25; // r9
  __int64 LastError; // rbx
  union _LARGE_INTEGER v28; // rbx
  void (__fastcall *v29)(HINTERNET, __int64, union _LARGE_INTEGER, union _LARGE_INTEGER); // rax
  wil *v30; // rcx
  unsigned int v31; // eax
  unsigned int v32; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-78h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-78h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-78h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-58h] BYREF
  char *v37; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v38[9]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  wil::details::in1diag3 *Buffer; // [rsp+B0h] [rbp+18h] BYREF
  DWORD dwBufferLength; // [rsp+B8h] [rbp+20h] BYREF

  if ( a3 && *a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3CA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      (const char *)0x80004004LL,
      dwCreationDispositiona);
  FileW = (char *)CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v37 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v7);
  LODWORD(Buffer) = 0;
  dwBufferLength = 4;
  v8 = !WinHttpQueryHeaders(this[6], 0x20000005u, 0, &Buffer, &dwBufferLength, 0);
  v9 = 0;
  if ( !v8 )
    v9 = (unsigned int)Buffer;
  v10.QuadPart = v9;
  v11 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))this[7];
  if ( v11 )
    v11(this[8], 0, v10.LowPart, 0);
  v12 = operator new[](0x400000u);
  v38[0] = v12;
  FileSize = v10;
  if ( !SetFilePointerEx(FileW, v10, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v13);
  if ( !SetEndOfFile(FileW) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3E0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v14);
  v15.QuadPart = 0;
  FileSize.QuadPart = 0;
  Buffer = retaddr;
  if ( !SetFilePointerEx(FileW, 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      Buffer,
      (void *)0x3E4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v17);
  LODWORD(Buffer) = 0;
  try
  {
    do
    {
      if ( a3 && *a3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3EB,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          (const char *)0x80004004LL,
          dwCreationDispositionb);
      if ( !WinHttpReadData(this[6], v12, 0x400000u, (LPDWORD)&Buffer) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x3EC,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          v19);
      if ( !(_DWORD)Buffer )
        break;
      if ( a3 )
      {
        v20 = 1;
        if ( *a3 )
          continue;
      }
      v20 = 0;
      if ( v20 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3EF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          (const char *)0x80004004LL,
          dwCreationDispositionb);
      dwBufferLength = 0;
      if ( !WriteFile(FileW, v12, (DWORD)Buffer, &dwBufferLength, 0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x3F2,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          v21);
      v22 = (int)Buffer;
      if ( dwBufferLength != (_DWORD)Buffer )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F4,
          (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
          (const char *)0xD,
          dwCreationDispositionb);
      v15.QuadPart += (unsigned int)Buffer;
      if ( this[7] )
      {
        if ( v10.QuadPart >= (unsigned __int64)v15.QuadPart )
        {
          v23 = (unsigned __int64)(100 * v15.QuadPart) / v10.QuadPart;
          if ( !(_DWORD)v23 )
            LODWORD(v23) = 1;
        }
        else
        {
          LODWORD(v23) = 0;
          v10 = v15;
        }
        ((void (__fastcall *)(_QWORD, _QWORD, union _LARGE_INTEGER, _QWORD))this[7])(
          this[8],
          (unsigned int)v23,
          v10,
          (union _LARGE_INTEGER)v15.QuadPart);
        v22 = (int)Buffer;
      }
    }
    while ( v22 );
    v24 = GetFileSizeEx(FileW, &FileSize);
  }
  catch ( ... )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v37,
      -1);
    DeleteFileW(a2);
    v31 = wil::ResultFromCaughtException(v30);
    v32 = wil::verify_hresult<long>(v31);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x420,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      (const char *)v32,
      dwCreationDisposition);
  }
  if ( v24 )
  {
    v28 = FileSize;
    v29 = (void (__fastcall *)(HINTERNET, __int64, union _LARGE_INTEGER, union _LARGE_INTEGER))this[7];
    if ( v29 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v29)(
        this[8],
        100,
        (union _LARGE_INTEGER)FileSize.QuadPart,
        (union _LARGE_INTEGER)FileSize.QuadPart);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v38);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
    return v28;
  }
  else
  {
    LastError = (int)wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x40F,
                       (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
                       v25);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v38);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v37);
    return (union _LARGE_INTEGER)LastError;
  }
}

```

## disassembly

```asm
0x1801dc654  mov     [rsp+arg_8], rdx
0x1801dc659  push    rbx
0x1801dc65a  push    rsi
0x1801dc65b  push    rdi
0x1801dc65c  push    r12
0x1801dc65e  push    r13
0x1801dc660  push    r14
0x1801dc662  push    r15
0x1801dc664  sub     rsp, 60h
0x1801dc668  mov     r14, r8
0x1801dc66b  mov     r10, rdx
0x1801dc66e  mov     rsi, rcx
0x1801dc671  xor     edi, edi
0x1801dc673  test    r8, r8
0x1801dc676  jz      short loc_1801DC686
0x1801dc678  cmp     [r8], edi
0x1801dc67b  jz      short loc_1801DC686
0x1801dc67d  lea     r15d, [rdi+1]
0x1801dc681  mov     al, r15b
0x1801dc684  jmp     short loc_1801DC68F
0x1801dc686  mov     al, dil
0x1801dc689  mov     r15d, 1
0x1801dc68f  mov     rcx, [rsp+98h]; this
0x1801dc697  test    al, al
0x1801dc699  jnz     loc_1801DC98C
0x1801dc69f  mov     [rsp+98h+hTemplateFile], rdi; hTemplateFile
0x1801dc6a4  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801dc6ac  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x1801dc6b4  xor     r9d, r9d; lpSecurityAttributes
0x1801dc6b7  xor     r8d, r8d; dwShareMode
0x1801dc6ba  mov     edx, 40000000h; dwDesiredAccess
0x1801dc6bf  mov     rcx, r10; lpFileName
0x1801dc6c2  call    cs:__imp_CreateFileW
0x1801dc6c8  mov     rbx, rax
0x1801dc6cb  mov     [rsp+98h+var_50], rax
0x1801dc6d0  dec     rax
0x1801dc6d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801dc6d7  setnbe  al
0x1801dc6da  mov     rcx, [rsp+98h]; this
0x1801dc6e2  test    al, al
0x1801dc6e4  jnz     loc_1801DC9A4
0x1801dc6ea  mov     dword ptr [rsp+98h+Buffer], edi
0x1801dc6f1  mov     [rsp+98h+dwBufferLength], 4
0x1801dc6fc  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rdi; lpdwIndex
0x1801dc701  lea     rax, [rsp+98h+dwBufferLength]
0x1801dc709  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; int
0x1801dc70e  lea     r9, [rsp+98h+Buffer]; lpBuffer
0x1801dc716  xor     r8d, r8d; pwszName
0x1801dc719  mov     edx, 20000005h; dwInfoLevel
0x1801dc71e  mov     rcx, [rsi+30h]; hRequest
0x1801dc722  call    cs:__imp_WinHttpQueryHeaders
0x1801dc728  test    eax, eax
0x1801dc72a  mov     eax, edi
0x1801dc72c  jz      short loc_1801DC735
0x1801dc72e  mov     eax, dword ptr [rsp+98h+Buffer]
0x1801dc735  mov     r12d, eax
0x1801dc738  mov     rax, [rsi+38h]
0x1801dc73c  test    rax, rax
0x1801dc73f  jz      short loc_1801DC752
0x1801dc741  xor     r9d, r9d
0x1801dc744  mov     r8d, r12d
0x1801dc747  xor     edx, edx
0x1801dc749  mov     rcx, [rsi+40h]
0x1801dc74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dc752  mov     ecx, 400000h; unsigned __int64
0x1801dc757  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801dc75c  mov     rdi, rax
0x1801dc75f  mov     [rsp+98h+var_48], rax
0x1801dc764  mov     qword ptr [rsp+98h+FileSize], r12
0x1801dc769  mov     r13, [rsp+98h]
0x1801dc771  xor     r9d, r9d; dwMoveMethod
0x1801dc774  xor     r8d, r8d; lpNewFilePointer
0x1801dc777  mov     rdx, r12; liDistanceToMove
0x1801dc77a  mov     rcx, rbx; hFile
0x1801dc77d  call    cs:__imp_SetFilePointerEx
0x1801dc783  test    eax, eax
0x1801dc785  jz      loc_1801DC9B6
0x1801dc78b  mov     r13, [rsp+98h]
0x1801dc793  mov     rcx, rbx; hFile
0x1801dc796  call    cs:__imp_SetEndOfFile
0x1801dc79c  test    eax, eax
0x1801dc79e  jz      loc_1801DC9CB
0x1801dc7a4  xor     r13d, r13d
0x1801dc7a7  mov     qword ptr [rsp+98h+FileSize], r13
0x1801dc7ac  xor     edx, edx; liDistanceToMove
0x1801dc7ae  mov     rax, [rsp+98h]
0x1801dc7b6  mov     [rsp+98h+Buffer], rax
0x1801dc7be  xor     r9d, r9d; dwMoveMethod
0x1801dc7c1  xor     r8d, r8d; lpNewFilePointer
0x1801dc7c4  mov     rcx, rbx; hFile
0x1801dc7c7  call    cs:__imp_SetFilePointerEx
0x1801dc7cd  test    eax, eax
0x1801dc7cf  jz      loc_1801DC9E0
0x1801dc7d5  mov     dword ptr [rsp+98h+Buffer], 0
0x1801dc7e0  test    r14, r14
0x1801dc7e3  jz      short loc_1801DC7F0
0x1801dc7e5  cmp     dword ptr [r14], 0
0x1801dc7e9  jz      short loc_1801DC7F0
0x1801dc7eb  mov     al, r15b
0x1801dc7ee  jmp     short loc_1801DC7F2
0x1801dc7f0  xor     al, al
0x1801dc7f2  mov     rcx, [rsp+98h]; this
0x1801dc7fa  test    al, al
0x1801dc7fc  jnz     loc_1801DC9FA
0x1801dc802  lea     r9, [rsp+98h+Buffer]; lpdwNumberOfBytesRead
0x1801dc80a  mov     r8d, 400000h; dwNumberOfBytesToRead
0x1801dc810  mov     rdx, rdi; lpBuffer
0x1801dc813  mov     rcx, [rsi+30h]; hRequest
0x1801dc817  call    cs:__imp_WinHttpReadData
0x1801dc81d  mov     rcx, [rsp+98h]; this
0x1801dc825  xor     edx, edx
0x1801dc827  test    eax, eax
0x1801dc829  jz      loc_1801DCA11
0x1801dc82f  mov     r8d, dword ptr [rsp+98h+Buffer]; nNumberOfBytesToWrite
0x1801dc837  test    r8d, r8d
0x1801dc83a  jz      loc_1801DC8F9
0x1801dc840  test    r14, r14
0x1801dc843  jz      short loc_1801DC84D
0x1801dc845  cmp     [r14], edx
0x1801dc848  mov     al, r15b
0x1801dc84b  jnz     short loc_1801DC84F
0x1801dc84d  mov     al, dl
0x1801dc84f  mov     rcx, [rsp+98h]; this
0x1801dc857  test    al, al
0x1801dc859  jnz     loc_1801DCA22
0x1801dc85f  mov     [rsp+98h+dwBufferLength], edx
0x1801dc866  mov     qword ptr [rsp+98h+dwCreationDisposition], rdx; int
0x1801dc86b  lea     r9, [rsp+98h+dwBufferLength]; lpNumberOfBytesWritten
0x1801dc873  mov     rdx, rdi; lpBuffer
0x1801dc876  mov     rcx, rbx; hFile
0x1801dc879  call    cs:__imp_WriteFile
0x1801dc87f  mov     rcx, [rsp+98h]; this
0x1801dc887  test    eax, eax
0x1801dc889  jz      loc_1801DCA39
0x1801dc88f  mov     edx, dword ptr [rsp+98h+Buffer]
0x1801dc896  cmp     [rsp+98h+dwBufferLength], edx
0x1801dc89d  setnz   al
0x1801dc8a0  mov     rcx, [rsp+98h]; this
0x1801dc8a8  test    al, al
0x1801dc8aa  jnz     loc_1801DCA4A
0x1801dc8b0  add     r13, rdx
0x1801dc8b3  cmp     qword ptr [rsi+38h], 0
0x1801dc8b8  jz      short loc_1801DC8F1
0x1801dc8ba  cmp     r12, r13
0x1801dc8bd  jnb     short loc_1801DC8C6
0x1801dc8bf  xor     eax, eax
0x1801dc8c1  mov     r12, r13
0x1801dc8c4  jmp     short loc_1801DC8D5
0x1801dc8c6  imul    rax, r13, 64h ; 'd'
0x1801dc8ca  xor     edx, edx
0x1801dc8cc  div     r12
0x1801dc8cf  test    eax, eax
0x1801dc8d1  cmovz   eax, r15d
0x1801dc8d5  mov     r9, r13
0x1801dc8d8  mov     r8, r12
0x1801dc8db  mov     edx, eax
0x1801dc8dd  mov     rcx, [rsi+40h]
0x1801dc8e1  mov     rax, [rsi+38h]
0x1801dc8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dc8ea  mov     edx, dword ptr [rsp+98h+Buffer]
0x1801dc8f1  test    edx, edx
0x1801dc8f3  jnz     loc_1801DC7E0
0x1801dc8f9  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x1801dc8fe  mov     rcx, rbx; hFile
0x1801dc901  call    cs:__imp_GetFileSizeEx
0x1801dc907  test    eax, eax
0x1801dc909  jnz     short loc_1801DC941
0x1801dc90b  mov     rcx, [rsp+98h]; this
0x1801dc913  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dc91a  mov     edx, 40Fh; void *
0x1801dc91f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dc924  movsxd  rbx, eax
0x1801dc927  lea     rcx, [rsp+98h+var_48]
0x1801dc92c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801dc931  nop
0x1801dc932  lea     rcx, [rsp+98h+var_50]
0x1801dc937  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801dc93c  mov     rax, rbx
0x1801dc93f  jmp     short loc_1801DC97C
0x1801dc941  mov     rbx, qword ptr [rsp+98h+FileSize]
0x1801dc946  mov     rax, [rsi+38h]
0x1801dc94a  test    rax, rax
0x1801dc94d  jz      short loc_1801DC964
0x1801dc94f  mov     r9, rbx
0x1801dc952  mov     r8, rbx
0x1801dc955  mov     edx, 64h ; 'd'
0x1801dc95a  mov     rcx, [rsi+40h]
0x1801dc95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dc963  nop
0x1801dc964  lea     rcx, [rsp+98h+var_48]
0x1801dc969  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1801dc96e  nop
0x1801dc96f  lea     rcx, [rsp+98h+var_50]
0x1801dc974  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801dc979  mov     rax, rbx
0x1801dc97c  add     rsp, 60h
0x1801dc980  pop     r15
0x1801dc982  pop     r14
0x1801dc984  pop     r13
0x1801dc986  pop     r12
0x1801dc988  pop     rdi
0x1801dc989  pop     rsi
0x1801dc98a  pop     rbx
0x1801dc98b  retn
0x1801dc98c  mov     r9d, 80004004h; char *
0x1801dc992  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dc999  mov     edx, 3CAh; void *
0x1801dc99e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801dc9a4  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dc9ab  mov     edx, 3CEh; void *
0x1801dc9b0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801dc9b6  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dc9bd  mov     edx, 3DFh; void *
0x1801dc9c2  mov     rcx, r13; this
0x1801dc9c5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801dc9cb  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dc9d2  mov     edx, 3E0h; void *
0x1801dc9d7  mov     rcx, r13; this
0x1801dc9da  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801dc9e0  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dc9e7  mov     edx, 3E4h; void *
0x1801dc9ec  mov     rcx, [rsp+98h+Buffer]; this
0x1801dc9f4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801dc9fa  mov     r9d, 80004004h; char *
0x1801dca00  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dca07  mov     edx, 3EBh; void *
0x1801dca0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801dca11  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dca18  mov     edx, 3ECh; void *
0x1801dca1d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801dca22  mov     r9d, 80004004h; char *
0x1801dca28  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dca2f  mov     edx, 3EFh; void *
0x1801dca34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801dca39  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dca40  mov     edx, 3F2h; void *
0x1801dca45  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801dca4a  mov     r9d, 0Dh; char *
0x1801dca50  lea     r8, aOnecoreuapEndu_74; "onecoreuap\\enduser\\winstore\\services"...
0x1801dca57  mov     edx, 3F4h; void *
0x1801dca5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
