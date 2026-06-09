# LocalFileBroker::MOTWCreateFileW(ushort const *,ulong,ulong,ulong,ulong,unsigned __int64 *)

- ea: `0x18001cf00`
- end: `0x18001d2b2`
- name: `?MOTWCreateFileW@LocalFileBroker@@UEAAJPEBGKKKKPEA_K@Z`
- size: `946`
- prototype: `int(LocalFileBroker *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18000c164`
- `0x18000e428`
- `0x180013ddc`
- `0x18001c770`
- `0x18001cf00`
- `0x18001e08c`
- `0x18001e0b8`
- `0x18001e890`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001d090`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001d090`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001d0a0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001d0a0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001d221`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001d221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d1fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d1fe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d1b3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d1b3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001d067`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001d067`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001cffd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001cffd`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18001d0d6`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18001d0d6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001d18a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001d18a`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18001d15a`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18001d15a`

## string_xrefs

- `0x18001cf7f`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001cfa9`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001d016`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001d0f7`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001d164`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001d194`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001d1d9`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`
- `0x18001d238`: `onecoreuap\inetcore\spartan\desktopbroker\localfilebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LocalFileBroker::MOTWCreateFileW(
        LocalFileBroker *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 *a7)
{
  int PIC; // eax
  unsigned int v11; // ebx
  bool v13; // bl
  char *FileW; // rdi
  __int64 v15; // rdx
  DWORD FinalPathNameByHandleW; // eax
  const WCHAR *ExtensionW; // rax
  char *v18; // rbx
  const char *v19; // r9
  const char *v20; // r9
  HANDLE v21; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE v23; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  unsigned int v27[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int Pid; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TargetHandle; // [rsp+60h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v32; // [rsp+70h] [rbp-90h]
  WCHAR szFilePath[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v32 = a7;
  *a7 = -1;
  v27[0] = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(2, v27);
  v11 = PIC;
  if ( PIC < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      (const char *)(unsigned int)PIC,
      dwCreationDisposition);
    return v11;
  }
  if ( a5 != 3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BF,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      (const char *)0x80070005LL,
      dwCreationDisposition);
    return 2147942405LL;
  }
  if ( (a3 & 0x5FEDFF56) != 0 )
    return 2147942405LL;
  v13 = 1;
  FileW = (char *)CreateFileW(a2, a3, a4 | 1, 0, 3u, a6 & 0xFBFFFFFF, 0);
  *(_QWORD *)v27 = FileW;
  if ( FileW == (char *)-1LL )
  {
    v15 = 725;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      (const char *)0x80070005LL,
      dwCreationDispositiona);
LABEL_10:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
    return 2147942405LL;
  }
  if ( (int)FileAccessAllowedEx(0) >= 0 )
  {
    v13 = 0;
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 0);
    if ( !FinalPathNameByHandleW )
      goto LABEL_10;
    if ( FinalPathNameByHandleW >= 0x104 )
    {
      v15 = 743;
      goto LABEL_9;
    }
    if ( !(unsigned __int8)FileAccessAllowed(szFilePath) )
    {
      ExtensionW = PathFindExtensionW(szFilePath);
      v13 = StrCmpICW(ExtensionW, L".url") == 0;
    }
  }
  if ( !v13 )
    goto LABEL_10;
  if ( (a4 | 1) != a4 )
  {
    v18 = (char *)ReOpenFile(FileW, a3, a4, a6 & 0xFB250048);
    v28 = (__int64)v18;
    if ( v18 == (char *)-1LL )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
        (const char *)0x80070005LL,
        dwCreationDispositiona);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
      goto LABEL_10;
    }
    v28 = -1;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(FileW);
    FileW = v18;
    *(_QWORD *)v27 = v18;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
  }
  Pid = 0;
  Binding = 0;
  if ( RpcServerInqBindingHandle(&Binding) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      v19);
  if ( I_RpcBindingInqLocalClientPID(Binding, &Pid) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2FA,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      v20);
  v21 = OpenProcess(0x40u, 0, Pid);
  v28 = (__int64)v21;
  if ( (((unsigned __int64)v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FC,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      (const char *)0x80070005LL,
      dwCreationDispositiona);
LABEL_31:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
    goto LABEL_10;
  }
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, FileW, v21, &TargetHandle, a3, 0, 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\localfilebroker.cpp",
      (const char *)0x80070005LL,
      dwCreationDispositionb);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
    goto LABEL_31;
  }
  v23 = TargetHandle;
  TargetHandle = 0;
  *v32 = (unsigned __int64)v23;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
  return 0;
}

```

## disassembly

```asm
0x18001cf00  mov     [rsp-8+arg_0], rbx
0x18001cf05  push    rbp
0x18001cf06  push    rsi
0x18001cf07  push    rdi
0x18001cf08  push    r12
0x18001cf0a  push    r13
0x18001cf0c  push    r14
0x18001cf0e  push    r15
0x18001cf10  lea     rbp, [rsp-1A0h]
0x18001cf18  sub     rsp, 2A0h
0x18001cf1f  mov     rax, cs:__security_cookie
0x18001cf26  xor     rax, rsp
0x18001cf29  mov     [rbp+1D0h+var_40], rax
0x18001cf30  mov     r15d, r9d
0x18001cf33  mov     r14d, r8d
0x18001cf36  mov     r13, rdx
0x18001cf39  mov     edi, [rbp+1D0h+arg_20]
0x18001cf3f  mov     esi, [rbp+1D0h+arg_28]
0x18001cf45  mov     rax, [rbp+1D0h+arg_30]
0x18001cf4c  mov     [rsp+2D0h+var_260], rax
0x18001cf51  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18001cf58  mov     [rsp+2D0h+var_288], 0
0x18001cf60  lea     rdx, [rsp+2D0h+var_288]; unsigned int *
0x18001cf65  mov     ecx, 2; unsigned int
0x18001cf6a  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18001cf6f  mov     ebx, eax
0x18001cf71  test    eax, eax
0x18001cf73  jns     short loc_18001CF97
0x18001cf75  mov     rcx, [rbp+1D8h]; this
0x18001cf7c  mov     r9d, eax; char *
0x18001cf7f  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001cf86  mov     edx, 2BDh; void *
0x18001cf8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf90  mov     eax, ebx
0x18001cf92  jmp     loc_18001D288
0x18001cf97  cmp     edi, 3
0x18001cf9a  jz      short loc_18001CFC4
0x18001cf9c  mov     rcx, [rbp+1D8h]; this
0x18001cfa3  mov     r9d, 80070005h; char *
0x18001cfa9  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001cfb0  mov     edx, 2BFh; void *
0x18001cfb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfba  mov     eax, 80070005h
0x18001cfbf  jmp     loc_18001D288
0x18001cfc4  test    r14d, 5FEDFF56h
0x18001cfcb  jnz     short loc_18001CFBA
0x18001cfcd  btr     esi, 1Ah
0x18001cfd1  mov     r12d, r15d
0x18001cfd4  mov     ebx, 1
0x18001cfd9  or      r12d, ebx
0x18001cfdc  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x18001cfe5  mov     [rsp+2D0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001cfe9  mov     [rsp+2D0h+dwCreationDisposition], 3; int
0x18001cff1  xor     r9d, r9d; lpSecurityAttributes
0x18001cff4  mov     r8d, r12d; dwShareMode
0x18001cff7  mov     edx, r14d; dwDesiredAccess
0x18001cffa  mov     rcx, r13; lpFileName
0x18001cffd  call    cs:__imp_CreateFileW
0x18001d003  mov     rdi, rax
0x18001d006  mov     qword ptr [rsp+2D0h+var_288], rax
0x18001d00b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d00f  jnz     short loc_18001D03F
0x18001d011  mov     edx, 2D5h; void *
0x18001d016  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001d01d  mov     r9d, 80070005h; char *
0x18001d023  mov     rcx, [rbp+1D8h]; this
0x18001d02a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d02f  nop
0x18001d030  lea     rcx, [rsp+2D0h+var_288]
0x18001d035  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d03a  jmp     loc_18001CFBA
0x18001d03f  xor     r13d, r13d
0x18001d042  mov     [rsp+2D0h+var_290], r13b
0x18001d047  lea     rdx, [rsp+2D0h+var_290]
0x18001d04c  xor     ecx, ecx; Str
0x18001d04e  call    _FileAccessAllowedEx
0x18001d053  test    eax, eax
0x18001d055  jns     short loc_18001D0AF
0x18001d057  xor     r9d, r9d; dwFlags
0x18001d05a  mov     r8d, 104h; cchFilePath
0x18001d060  lea     rdx, [rbp+1D0h+szFilePath]; lpszFilePath
0x18001d064  mov     rcx, rdi; hFile
0x18001d067  call    cs:__imp_GetFinalPathNameByHandleW
0x18001d06d  test    eax, eax
0x18001d06f  jz      short loc_18001D030
0x18001d071  cmp     eax, 104h
0x18001d076  jb      short loc_18001D07F
0x18001d078  mov     edx, 2E7h
0x18001d07d  jmp     short loc_18001D016
0x18001d07f  lea     rcx, [rbp+1D0h+szFilePath]
0x18001d083  call    _FileAccessAllowed
0x18001d088  test    al, al
0x18001d08a  jnz     short loc_18001D0B3
0x18001d08c  lea     rcx, [rbp+1D0h+szFilePath]; pszPath
0x18001d090  call    cs:__imp_PathFindExtensionW
0x18001d096  lea     rdx, aUrl; ".url"
0x18001d09d  mov     rcx, rax; pszStr1
0x18001d0a0  call    cs:__imp_StrCmpICW
0x18001d0a6  test    eax, eax
0x18001d0a8  jz      short loc_18001D0B3
0x18001d0aa  mov     bl, r13b
0x18001d0ad  jmp     short loc_18001D0B3
0x18001d0af  mov     bl, [rsp+2D0h+var_290]
0x18001d0b3  test    bl, bl
0x18001d0b5  jz      loc_18001D030
0x18001d0bb  cmp     r12d, r15d
0x18001d0be  jz      loc_18001D144
0x18001d0c4  and     esi, 0FF250048h
0x18001d0ca  mov     r9d, esi; dwFlagsAndAttributes
0x18001d0cd  mov     r8d, r15d; dwShareMode
0x18001d0d0  mov     edx, r14d; dwDesiredAccess
0x18001d0d3  mov     rcx, rdi; hOriginalFile
0x18001d0d6  call    cs:__imp_ReOpenFile
0x18001d0dc  mov     rbx, rax
0x18001d0df  mov     [rsp+2D0h+var_280], rax
0x18001d0e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d0e8  jnz     short loc_18001D117
0x18001d0ea  mov     rcx, [rbp+1D8h]; this
0x18001d0f1  mov     r9d, 80070005h; char *
0x18001d0f7  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001d0fe  mov     edx, 2F2h; void *
0x18001d103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d108  lea     rcx, [rsp+2D0h+var_280]
0x18001d10d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d112  jmp     loc_18001D030
0x18001d117  mov     [rsp+2D0h+var_280], 0FFFFFFFFFFFFFFFFh
0x18001d120  lea     rax, [rdi-1]
0x18001d124  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d128  ja      short loc_18001D132
0x18001d12a  mov     rcx, rdi; hObject
0x18001d12d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001d132  mov     rdi, rbx
0x18001d135  mov     qword ptr [rsp+2D0h+var_288], rbx
0x18001d13a  lea     rcx, [rsp+2D0h+var_280]
0x18001d13f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d144  mov     [rsp+2D0h+Pid], r13d
0x18001d149  mov     [rsp+2D0h+Binding], r13
0x18001d14e  mov     rbx, [rbp+1D8h]
0x18001d155  lea     rcx, [rsp+2D0h+Binding]; Binding
0x18001d15a  call    cs:__imp_RpcServerInqBindingHandle
0x18001d160  test    eax, eax
0x18001d162  jz      short loc_18001D179
0x18001d164  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001d16b  mov     edx, 2F9h; void *
0x18001d170  mov     rcx, rbx; this
0x18001d173  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001d179  mov     rbx, [rbp+1D8h]
0x18001d180  lea     rdx, [rsp+2D0h+Pid]; Pid
0x18001d185  mov     rcx, [rsp+2D0h+Binding]; Binding
0x18001d18a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001d190  test    eax, eax
0x18001d192  jz      short loc_18001D1A9
0x18001d194  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001d19b  mov     edx, 2FAh; void *
0x18001d1a0  mov     rcx, rbx; this
0x18001d1a3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001d1a9  mov     r8d, [rsp+2D0h+Pid]; dwProcessId
0x18001d1ae  xor     edx, edx; bInheritHandle
0x18001d1b0  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18001d1b3  call    cs:__imp_OpenProcess
0x18001d1b9  mov     rbx, rax
0x18001d1bc  mov     [rsp+2D0h+var_280], rax
0x18001d1c1  inc     rax
0x18001d1c4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001d1ca  jnz     short loc_18001D1F9
0x18001d1cc  mov     rcx, [rbp+1D8h]; this
0x18001d1d3  mov     r9d, 80070005h; char *
0x18001d1d9  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001d1e0  mov     edx, 2FCh; void *
0x18001d1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1ea  lea     rcx, [rsp+2D0h+var_280]
0x18001d1ef  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d1f4  jmp     loc_18001D030
0x18001d1f9  mov     [rsp+2D0h+TargetHandle], r13
0x18001d1fe  call    cs:__imp_GetCurrentProcess
0x18001d204  mov     dword ptr [rsp+2D0h+hTemplateFile], r13d; dwOptions
0x18001d209  mov     [rsp+2D0h+dwFlagsAndAttributes], r13d; bInheritHandle
0x18001d20e  mov     [rsp+2D0h+dwCreationDisposition], r14d; int
0x18001d213  lea     r9, [rsp+2D0h+TargetHandle]; lpTargetHandle
0x18001d218  mov     r8, rbx; hTargetProcessHandle
0x18001d21b  mov     rdx, rdi; hSourceHandle
0x18001d21e  mov     rcx, rax; hSourceProcessHandle
0x18001d221  call    cs:__imp_DuplicateHandle
0x18001d227  test    eax, eax
0x18001d229  jnz     short loc_18001D255
0x18001d22b  mov     rcx, [rbp+1D8h]; this
0x18001d232  mov     r9d, 80070005h; char *
0x18001d238  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001d23f  mov     edx, 2FFh; void *
0x18001d244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d249  lea     rcx, [rsp+2D0h+TargetHandle]
0x18001d24e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d253  jmp     short loc_18001D1EA
0x18001d255  mov     rax, [rsp+2D0h+TargetHandle]
0x18001d25a  mov     [rsp+2D0h+TargetHandle], r13
0x18001d25f  mov     rcx, [rsp+2D0h+var_260]
0x18001d264  mov     [rcx], rax
0x18001d267  lea     rcx, [rsp+2D0h+TargetHandle]
0x18001d26c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d271  lea     rcx, [rsp+2D0h+var_280]
0x18001d276  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d27b  nop
0x18001d27c  lea     rcx, [rsp+2D0h+var_288]
0x18001d281  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d286  xor     eax, eax
0x18001d288  mov     rcx, [rbp+1D0h+var_40]
0x18001d28f  xor     rcx, rsp; StackCookie
0x18001d292  call    __security_check_cookie
0x18001d297  mov     rbx, [rsp+2D0h+arg_0]
0x18001d29f  add     rsp, 2A0h
0x18001d2a6  pop     r15
0x18001d2a8  pop     r14
0x18001d2aa  pop     r13
0x18001d2ac  pop     r12
0x18001d2ae  pop     rdi
0x18001d2af  pop     rsi
0x18001d2b0  pop     rbp
0x18001d2b1  retn
```
