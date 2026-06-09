# CCbsPublicFacadeClassFactory::CreateInstanceFromProtectedProcess(IClassFactory * *)

- ea: `0x1400148e8`
- end: `0x140014d58`
- name: `?CreateInstanceFromProtectedProcess@CCbsPublicFacadeClassFactory@@CAJPEAPEAUIClassFactory@@@Z`
- size: `1136`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001524c`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x140002de4`
- `0x1400148e8`
- `0x140017658`
- `0x14001c7a8`
- `0x14001c9a0`
- `0x14001cfc4`
- `0x14001dc7c`
- `0x140026b00`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140014b3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140014b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400149fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400149fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014bbe`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140014c73`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140014c73`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140014bb4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140014bb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014cee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014cee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014d03`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x140014c3e`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x140014c3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001497d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400149f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001497d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400149f1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x140014c05`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x140014c05`

## string_xrefs

- `0x1400149c4`: `Failed to allocate memory for system dir path`
- `0x140014a12`: `Failed to get system directory`
- `0x140014a40`: `Failed to backslash-terminate system directory: %S`
- `0x140014aaa`: `Failed to get temp path`
- `0x140014aea`: `%s TEMP="%s\" -Embedding`
- `0x140014ae3`: `%s TEMP="%s" -Embedding`
- `0x140014b0c`: `Failed to alloc command line string`
- `0x140014b5f`: `Failed to create genvalobj activation event`
- `0x140014bd5`: `Could not create protected process GenValObj.exe`

## pseudocode

```c
__int64 __fastcall CCbsPublicFacadeClassFactory::CreateInstanceFromProtectedProcess(LPVOID *a1)
{
  HANDLE EventW; // r12
  LPWSTR v3; // rsi
  const WCHAR *v4; // r14
  LPWSTR v5; // r15
  signed int v6; // ebx
  unsigned __int64 v7; // rdx
  UINT SystemDirectoryW; // eax
  UINT v9; // edi
  signed int LastError; // eax
  const char *v11; // r9
  int v12; // eax
  signed int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int TemporaryPath; // eax
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax
  const wchar_t *v21; // rdx
  int v22; // eax
  const char *v23; // r9
  __int64 v24; // rdx
  signed int v25; // eax
  signed int v26; // eax
  DWORD v27; // eax
  HRESULT ClassObject; // eax
  BOOL bInheritHandles[2]; // [rsp+20h] [rbp-E0h]
  LPWSTR lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpApplicationName; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR lpCommandLine; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  DWORD ExitCode; // [rsp+88h] [rbp-78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Handles[2]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR v39[264]; // [rsp+110h] [rbp+10h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  ppv = 0;
  EventW = 0;
  lpBuffer = 0;
  v3 = 0;
  lpApplicationName = 0;
  v4 = 0;
  lpCommandLine = 0;
  v5 = 0;
  ExitCode = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)Handles = 0;
  if ( !a1 )
  {
    v6 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "No class factory result specified");
    goto LABEL_57;
  }
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v9 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v11 = "Failed to get size of system dir";
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_56;
  }
  v12 = SczAlloc(&lpBuffer, SystemDirectoryW);
  v6 = v12;
  if ( v12 < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)v12, 1, "Failed to allocate memory for system dir path");
    v3 = lpBuffer;
    goto LABEL_57;
  }
  v3 = lpBuffer;
  if ( !GetSystemDirectoryW(lpBuffer, v9) )
  {
    v13 = GetLastError();
    v6 = v13;
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
    v11 = "Failed to get system directory";
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_56;
  }
  v14 = SczEnsureBackslashTerminated(&lpBuffer);
  v3 = lpBuffer;
  v6 = v14;
  if ( v14 < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)v14, 1, "Failed to backslash-terminate system directory: %S", lpBuffer);
    goto LABEL_57;
  }
  v15 = SczAllocConcat2Sz(&lpApplicationName, lpBuffer, L"GenValObj.exe");
  v6 = v15;
  if ( v15 < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)v15, 1, "Failed to alloc program string");
LABEL_21:
    v4 = lpApplicationName;
    goto LABEL_57;
  }
  TemporaryPath = GetTemporaryPath(v16, v39);
  v6 = TemporaryPath;
  if ( TemporaryPath < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)TemporaryPath, 1, "Failed to get temp path");
    goto LABEL_21;
  }
  v4 = lpApplicationName;
  v18 = -1;
  do
    ++v18;
  while ( v39[v18] );
  if ( !v18 || (v19 = *((_WORD *)&Handles[1] + v18 + 3) == 92, v20 = 1, !v19) )
    v20 = 0;
  v21 = L"%s TEMP=\"%s\\\" -Embedding";
  if ( !v20 )
    v21 = L"%s TEMP=\"%s\" -Embedding";
  v22 = SczAllocFormatted(&lpCommandLine, v21, lpApplicationName, v39);
  v6 = v22;
  if ( v22 < 0 )
  {
    v23 = "Failed to alloc command line string";
    v24 = (unsigned int)v22;
LABEL_33:
    CBSWdsLogLight(0x4000000, v24, 1, v23);
    v5 = lpCommandLine;
    goto LABEL_57;
  }
  EventW = CreateEventW(0, 1, 0, L"Local\\{2ADA1CEA-5D4C-406E-A72D-173CD7698257}");
  if ( !EventW )
  {
    v25 = GetLastError();
    v6 = v25;
    if ( v25 > 0 )
      v6 = (unsigned __int16)v25 | 0x80070000;
    v23 = "Failed to create genvalobj activation event";
    if ( v6 >= 0 )
      v6 = -2147467259;
    v24 = (unsigned int)v6;
    goto LABEL_33;
  }
  StartupInfo.cb = 104;
  v5 = lpCommandLine;
  if ( !CreateProcessW(v4, lpCommandLine, 0, 0, 0, 0x40000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v26 = GetLastError();
    v6 = v26;
    if ( v26 > 0 )
      v6 = (unsigned __int16)v26 | 0x80070000;
    v11 = "Could not create protected process GenValObj.exe";
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_56;
  }
  Handles[0] = ProcessInformation.hProcess;
  Handles[1] = EventW;
  v27 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( !v27 )
  {
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      v6 = -2147418113;
      bInheritHandles[0] = ExitCode;
      CBSWdsLogLight(
        0x4000000,
        2147549183LL,
        1,
        "GenValObj.exe died unexpectedly. exitcode: %d",
        *(_QWORD *)bInheritHandles);
      goto LABEL_57;
    }
    v11 = "GenValObj.exe died unexpectedly";
    goto LABEL_55;
  }
  if ( v27 != 1 )
  {
    v11 = "failed to signal genvalobj registration event";
LABEL_55:
    v6 = -2147418113;
LABEL_56:
    CBSWdsLogLight(0x4000000, (unsigned int)v6, 1, v11);
    goto LABEL_57;
  }
  ClassObject = CoGetClassObject(&CLSID_GenValObj_Inner, 0x15u, 0, &IID_IClassFactory, &ppv);
  v6 = ClassObject;
  if ( ClassObject >= 0 )
  {
    *a1 = ppv;
    ppv = 0;
LABEL_60:
    if ( EventW != (HANDLE)-1LL )
      CloseHandle(EventW);
    goto LABEL_62;
  }
  CBSWdsLogLight(0x4000000, (unsigned int)ClassObject, 1, "failed to get genvalobj classfactory");
LABEL_57:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( EventW )
    goto LABEL_60;
LABEL_62:
  if ( (unsigned __int64)ProcessInformation.hProcess - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(ProcessInformation.hProcess);
  if ( (unsigned __int64)ProcessInformation.hThread - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(ProcessInformation.hThread);
  if ( v3 )
    operator delete(v3 - 4, v7);
  if ( v4 )
    operator delete((void *)(v4 - 4), v7);
  if ( v5 )
    operator delete(v5 - 4, v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400148e8  push    rbp
0x1400148ea  push    rbx
0x1400148eb  push    rsi
0x1400148ec  push    rdi
0x1400148ed  push    r12
0x1400148ef  push    r13
0x1400148f1  push    r14
0x1400148f3  push    r15
0x1400148f5  lea     rbp, [rsp-238h]
0x1400148fd  sub     rsp, 338h
0x140014904  mov     rax, cs:__security_cookie
0x14001490b  xor     rax, rsp
0x14001490e  mov     [rbp+270h+var_50], rax
0x140014915  xor     edx, edx; Val
0x140014917  mov     r13, rcx
0x14001491a  lea     rcx, [rbp+270h+StartupInfo]; void *
0x14001491e  lea     r8d, [rdx+68h]; Size
0x140014922  call    memset_0
0x140014927  xor     ebx, ebx
0x140014929  xor     eax, eax
0x14001492b  mov     qword ptr [rbp+270h+ProcessInformation.dwProcessId], rax
0x14001492f  xorps   xmm0, xmm0
0x140014932  mov     [rsp+370h+ppv], rbx
0x140014937  mov     r12d, ebx
0x14001493a  mov     [rsp+370h+lpBuffer], rbx
0x14001493f  mov     esi, ebx
0x140014941  mov     [rsp+370h+lpApplicationName], rbx
0x140014946  mov     r14d, ebx
0x140014949  mov     [rsp+370h+lpCommandLine], rbx
0x14001494e  mov     r15d, ebx
0x140014951  mov     [rbp+270h+ExitCode], ebx
0x140014954  movups  xmmword ptr [rsp+370h+ProcessInformation.hProcess], xmm0
0x140014959  movups  xmmword ptr [rbp+270h+Handles], xmm0
0x14001495d  test    r13, r13
0x140014960  jnz     short loc_140014979
0x140014962  mov     ebx, 80004003h
0x140014967  lea     r9, aNoClassFactory; "No class factory result specified"
0x14001496e  mov     r8d, 1
0x140014974  jmp     loc_140014CA9
0x140014979  xor     edx, edx; uSize
0x14001497b  xor     ecx, ecx; lpBuffer
0x14001497d  call    cs:__imp_GetSystemDirectoryW
0x140014983  mov     edi, eax
0x140014985  test    eax, eax
0x140014987  jnz     short loc_1400149B1
0x140014989  call    cs:__imp_GetLastError
0x14001498f  mov     ebx, eax
0x140014991  test    eax, eax
0x140014993  jle     short loc_14001499E
0x140014995  movzx   ebx, ax
0x140014998  or      ebx, 80070000h
0x14001499e  test    ebx, ebx
0x1400149a0  lea     r9, aFailedToGetSiz; "Failed to get size of system dir"
0x1400149a7  mov     eax, 80004005h
0x1400149ac  cmovns  ebx, eax
0x1400149af  jmp     short loc_14001496E
0x1400149b1  mov     rdx, rdi
0x1400149b4  lea     rcx, [rsp+370h+lpBuffer]
0x1400149b9  call    SczAlloc
0x1400149be  mov     ebx, eax
0x1400149c0  test    eax, eax
0x1400149c2  jns     short loc_1400149E7
0x1400149c4  lea     r9, aFailedToAlloca_16; "Failed to allocate memory for system di"...
0x1400149cb  mov     r8d, 1
0x1400149d1  mov     edx, eax
0x1400149d3  mov     ecx, 4000000h
0x1400149d8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400149dd  mov     rsi, [rsp+370h+lpBuffer]
0x1400149e2  jmp     loc_140014CB5
0x1400149e7  mov     rsi, [rsp+370h+lpBuffer]
0x1400149ec  mov     edx, edi; uSize
0x1400149ee  mov     rcx, rsi; lpBuffer
0x1400149f1  call    cs:__imp_GetSystemDirectoryW
0x1400149f7  test    eax, eax
0x1400149f9  jnz     short loc_140014A26
0x1400149fb  call    cs:__imp_GetLastError
0x140014a01  mov     ebx, eax
0x140014a03  test    eax, eax
0x140014a05  jle     short loc_140014A10
0x140014a07  movzx   ebx, ax
0x140014a0a  or      ebx, 80070000h
0x140014a10  test    ebx, ebx
0x140014a12  lea     r9, aFailedToGetSys; "Failed to get system directory"
0x140014a19  mov     eax, 80004005h
0x140014a1e  cmovns  ebx, eax
0x140014a21  jmp     loc_14001496E
0x140014a26  lea     rcx, [rsp+370h+lpBuffer]
0x140014a2b  call    SczEnsureBackslashTerminated
0x140014a30  mov     rsi, [rsp+370h+lpBuffer]
0x140014a35  mov     ebx, eax
0x140014a37  test    eax, eax
0x140014a39  jns     short loc_140014A5E
0x140014a3b  mov     qword ptr [rsp+370h+bInheritHandles], rsi
0x140014a40  lea     r9, aFailedToBacksl; "Failed to backslash-terminate system di"...
0x140014a47  mov     r8d, 1
0x140014a4d  mov     edx, eax
0x140014a4f  mov     ecx, 4000000h
0x140014a54  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014a59  jmp     loc_140014CB5
0x140014a5e  lea     r8, aGenvalobjExe; "GenValObj.exe"
0x140014a65  mov     rdx, rsi
0x140014a68  lea     rcx, [rsp+370h+lpApplicationName]
0x140014a6d  call    SczAllocConcat2Sz
0x140014a72  mov     ebx, eax
0x140014a74  test    eax, eax
0x140014a76  jns     short loc_140014A9B
0x140014a78  lea     r9, aFailedToAllocP; "Failed to alloc program string"
0x140014a7f  mov     r8d, 1
0x140014a85  mov     edx, eax
0x140014a87  mov     ecx, 4000000h
0x140014a8c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014a91  mov     r14, [rsp+370h+lpApplicationName]
0x140014a96  jmp     loc_140014CB5
0x140014a9b  lea     rdx, [rbp+270h+var_260]
0x140014a9f  call    GetTemporaryPath
0x140014aa4  mov     ebx, eax
0x140014aa6  test    eax, eax
0x140014aa8  jns     short loc_140014AB3
0x140014aaa  lea     r9, aFailedToGetTem; "Failed to get temp path"
0x140014ab1  jmp     short loc_140014A7F
0x140014ab3  mov     r14, [rsp+370h+lpApplicationName]
0x140014ab8  lea     rcx, [rbp+270h+var_260]
0x140014abc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014ac0  inc     rax
0x140014ac3  cmp     [rcx+rax*2], r15w
0x140014ac8  jnz     short loc_140014AC0
0x140014aca  mov     edi, 1
0x140014acf  test    rax, rax
0x140014ad2  jz      short loc_140014ADE
0x140014ad4  cmp     word ptr [rbp+rax*2+270h+Handles+0Eh], 5Ch ; '\'
0x140014ada  mov     eax, edi
0x140014adc  jz      short loc_140014AE1
0x140014ade  mov     eax, r15d
0x140014ae1  test    eax, eax
0x140014ae3  lea     rcx, aSTempSEmbeddin; "%s TEMP=\"%s\" -Embedding"
0x140014aea  lea     rdx, aSTempSEmbeddin_0; "%s TEMP=\"%s\\\" -Embedding"
0x140014af1  mov     r8, r14
0x140014af4  cmovz   rdx, rcx
0x140014af8  lea     r9, [rbp+270h+var_260]
0x140014afc  lea     rcx, [rsp+370h+lpCommandLine]
0x140014b01  call    SczAllocFormatted
0x140014b06  mov     ebx, eax
0x140014b08  test    eax, eax
0x140014b0a  jns     short loc_140014B2C
0x140014b0c  lea     r9, aFailedToAllocC; "Failed to alloc command line string"
0x140014b13  mov     edx, eax
0x140014b15  mov     r8d, edi
0x140014b18  mov     ecx, 4000000h
0x140014b1d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014b22  mov     r15, [rsp+370h+lpCommandLine]
0x140014b27  jmp     loc_140014CB5
0x140014b2c  lea     r9, Name; "Local\\{2ADA1CEA-5D4C-406E-A72D-173CD76"...
0x140014b33  xor     r8d, r8d; bInitialState
0x140014b36  mov     edx, edi; bManualReset
0x140014b38  xor     ecx, ecx; lpEventAttributes
0x140014b3a  call    cs:__imp_CreateEventW
0x140014b40  mov     r12, rax
0x140014b43  test    rax, rax
0x140014b46  jnz     short loc_140014B72
0x140014b48  call    cs:__imp_GetLastError
0x140014b4e  mov     ebx, eax
0x140014b50  test    eax, eax
0x140014b52  jle     short loc_140014B5D
0x140014b54  movzx   ebx, ax
0x140014b57  or      ebx, 80070000h
0x140014b5d  test    ebx, ebx
0x140014b5f  lea     r9, aFailedToCreate_13; "Failed to create genvalobj activation e"...
0x140014b66  mov     eax, 80004005h
0x140014b6b  cmovns  ebx, eax
0x140014b6e  mov     edx, ebx
0x140014b70  jmp     short loc_140014B15
0x140014b72  lea     rax, [rsp+370h+ProcessInformation]
0x140014b77  mov     [rbp+270h+StartupInfo.cb], 68h ; 'h'
0x140014b7e  mov     [rsp+370h+lpProcessInformation], rax; lpProcessInformation
0x140014b83  xor     r9d, r9d; lpThreadAttributes
0x140014b86  lea     rax, [rbp+270h+StartupInfo]
0x140014b8a  xor     r8d, r8d; lpProcessAttributes
0x140014b8d  mov     [rsp+370h+lpStartupInfo], rax; lpStartupInfo
0x140014b92  mov     rcx, r14; lpApplicationName
0x140014b95  mov     [rsp+370h+lpCurrentDirectory], r15; lpCurrentDirectory
0x140014b9a  mov     [rsp+370h+lpEnvironment], r15; lpEnvironment
0x140014b9f  mov     [rsp+370h+dwCreationFlags], 40000h; dwCreationFlags
0x140014ba7  mov     [rsp+370h+bInheritHandles], r15d; bInheritHandles
0x140014bac  mov     r15, [rsp+370h+lpCommandLine]
0x140014bb1  mov     rdx, r15; lpCommandLine
0x140014bb4  call    cs:__imp_CreateProcessW
0x140014bba  test    eax, eax
0x140014bbc  jnz     short loc_140014BE9
0x140014bbe  call    cs:__imp_GetLastError
0x140014bc4  mov     ebx, eax
0x140014bc6  test    eax, eax
0x140014bc8  jle     short loc_140014BD3
0x140014bca  movzx   ebx, ax
0x140014bcd  or      ebx, 80070000h
0x140014bd3  test    ebx, ebx
0x140014bd5  lea     r9, aCouldNotCreate; "Could not create protected process GenV"...
0x140014bdc  mov     eax, 80004005h
0x140014be1  cmovns  ebx, eax
0x140014be4  jmp     loc_140014CA6
0x140014be9  mov     rax, [rsp+370h+ProcessInformation.hProcess]
0x140014bee  lea     rdx, [rbp+270h+Handles]; lpHandles
0x140014bf2  xor     r8d, r8d; bWaitAll
0x140014bf5  mov     [rbp+270h+Handles], rax
0x140014bf9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140014bfd  mov     [rbp+270h+Handles+8], r12
0x140014c01  lea     ecx, [r8+2]; nCount
0x140014c05  call    cs:__imp_WaitForMultipleObjects
0x140014c0b  test    eax, eax
0x140014c0d  jz      short loc_140014C6A
0x140014c0f  cmp     eax, edi
0x140014c11  jz      short loc_140014C1F
0x140014c13  lea     r9, aFailedToSignal; "failed to signal genvalobj registration"...
0x140014c1a  jmp     loc_140014CA1
0x140014c1f  xor     r8d, r8d; pvReserved
0x140014c22  lea     rax, [rsp+370h+ppv]
0x140014c27  lea     r9, IID_IClassFactory; riid
0x140014c2e  mov     qword ptr [rsp+370h+bInheritHandles], rax; ppv
0x140014c33  lea     rcx, CLSID_GenValObj_Inner; rclsid
0x140014c3a  lea     edx, [r8+15h]; dwClsContext
0x140014c3e  call    cs:__imp_CoGetClassObject
0x140014c44  mov     ebx, eax
0x140014c46  test    eax, eax
0x140014c48  jns     short loc_140014C58
0x140014c4a  lea     r9, aFailedToGetGen; "failed to get genvalobj classfactory"
0x140014c51  mov     r8d, edi
0x140014c54  mov     edx, eax
0x140014c56  jmp     short loc_140014CAB
0x140014c58  mov     rax, [rsp+370h+ppv]
0x140014c5d  xor     edi, edi
0x140014c5f  mov     [r13+0], rax
0x140014c63  mov     [rsp+370h+ppv], rdi
0x140014c68  jmp     short loc_140014CD0
0x140014c6a  mov     rcx, [rsp+370h+ProcessInformation.hProcess]; hProcess
0x140014c6f  lea     rdx, [rbp+270h+ExitCode]; lpExitCode
0x140014c73  call    cs:__imp_GetExitCodeProcess
0x140014c79  test    eax, eax
0x140014c7b  jz      short loc_140014C9A
0x140014c7d  mov     eax, [rbp+270h+ExitCode]
0x140014c80  lea     r9, aGenvalobjExeDi_0; "GenValObj.exe died unexpectedly. exitco"...
0x140014c87  mov     ebx, 8000FFFFh
0x140014c8c  mov     [rsp+370h+bInheritHandles], eax
0x140014c90  mov     edx, ebx
0x140014c92  mov     r8d, edi
0x140014c95  jmp     loc_140014A4F
0x140014c9a  lea     r9, aGenvalobjExeDi; "GenValObj.exe died unexpectedly"
0x140014ca1  mov     ebx, 8000FFFFh
0x140014ca6  mov     r8d, edi
0x140014ca9  mov     edx, ebx
0x140014cab  mov     ecx, 4000000h
0x140014cb0  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140014cb5  mov     rcx, [rsp+370h+ppv]
0x140014cba  test    rcx, rcx
0x140014cbd  jz      short loc_140014CCB
0x140014cbf  mov     rax, [rcx]
0x140014cc2  mov     rax, [rax+10h]
0x140014cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ccb  test    r12, r12
0x140014cce  jz      short loc_140014CDF
0x140014cd0  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140014cd4  jz      short loc_140014CDF
0x140014cd6  mov     rcx, r12; hObject
0x140014cd9  call    cs:__imp_CloseHandle
0x140014cdf  mov     rcx, [rsp+370h+ProcessInformation.hProcess]; hObject
0x140014ce4  lea     rax, [rcx-1]
0x140014ce8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140014cec  ja      short loc_140014CF4
0x140014cee  call    cs:__imp_CloseHandle
0x140014cf4  mov     rcx, [rsp+370h+ProcessInformation.hThread]; hObject
0x140014cf9  lea     rax, [rcx-1]
0x140014cfd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140014d01  ja      short loc_140014D09
0x140014d03  call    cs:__imp_CloseHandle
0x140014d09  test    rsi, rsi
0x140014d0c  jz      short loc_140014D17
0x140014d0e  lea     rcx, [rsi-8]; void *
0x140014d12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140014d17  test    r14, r14
0x140014d1a  jz      short loc_140014D25
0x140014d1c  lea     rcx, [r14-8]; void *
0x140014d20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140014d25  test    r15, r15
0x140014d28  jz      short loc_140014D33
0x140014d2a  lea     rcx, [r15-8]; void *
0x140014d2e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140014d33  mov     eax, ebx
0x140014d35  mov     rcx, [rbp+270h+var_50]
0x140014d3c  xor     rcx, rsp; StackCookie
0x140014d3f  call    __security_check_cookie
0x140014d44  add     rsp, 338h
0x140014d4b  pop     r15
0x140014d4d  pop     r14
0x140014d4f  pop     r13
0x140014d51  pop     r12
0x140014d53  pop     rdi
0x140014d54  pop     rsi
0x140014d55  pop     rbx
0x140014d56  pop     rbp
0x140014d57  retn
```
