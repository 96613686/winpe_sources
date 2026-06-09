# ChannelBasedServerConnectionManager::OnEventSignal(void *,ushort const *)

- ea: `0x1801091e0`
- end: `0x180109664`
- name: `?OnEventSignal@ChannelBasedServerConnectionManager@@EEAAJPEAXPEBG@Z`
- size: `1156`
- prototype: `__int64 __fastcall(ChannelBasedServerConnectionManager *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x18002f580`
- `0x180076c30`
- `0x180091b98`
- `0x180092df4`
- `0x180092e10`
- `0x180093cfc`
- `0x1800984e0`
- `0x1801091e0`
- `0x18010966c`
- `0x180109738`
- `0x180109764`
- `0x1801334b8`
- `0x1801e8320`
- `0x1801e8380`
- `0x1801ef320`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801094ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801094ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010961f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010961f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeServerProcessId` at `0x180109314`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeServerProcessId` at `0x180109314`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801092c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801095ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801092c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801095ae`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x1801092f6`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x1801092f6`

## string_xrefs

- `0x180109265`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x180109351`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x180109414`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18010944d`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x180109494`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18010950c`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18010955f`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1801095d7`: `CreateFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ChannelBasedServerConnectionManager::OnEventSignal(
        ChannelBasedServerConnectionManager *this,
        void *a2,
        const unsigned __int16 *a3)
{
  int v3; // edi
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  char *FileW; // rbx
  ChannelBasedServerConnection *v12; // rax
  ChannelBasedServerConnection *v13; // rax
  ChannelBasedServerConnection *v14; // rdi
  int v15; // eax
  unsigned int v16; // esi
  ULONG v17; // esi
  __int64 ServerVersionExchangePayload; // rax
  int v19; // eax
  unsigned int v20; // ebx
  DWORD CurrentProcessId; // eax
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  HANDLE v26; // rax
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-2F88h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-2F88h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-2F88h]
  DWORD Mode; // [rsp+50h] [rbp-2F58h] BYREF
  char *v33; // [rsp+58h] [rbp-2F50h] BYREF
  ULONG ServerProcessId; // [rsp+60h] [rbp-2F48h] BYREF
  char *v35; // [rsp+68h] [rbp-2F40h] BYREF
  ChannelBasedServerConnection *v36; // [rsp+70h] [rbp-2F38h] BYREF
  int v37[2]; // [rsp+78h] [rbp-2F30h] BYREF
  __int64 v38; // [rsp+80h] [rbp-2F28h] BYREF
  char v39[24]; // [rsp+88h] [rbp-2F20h] BYREF
  unsigned __int16 v40[2000]; // [rsp+A0h] [rbp-2F08h] BYREF
  WCHAR FileName[2000]; // [rsp+1040h] [rbp-1F68h] BYREF
  unsigned __int16 v42[2000]; // [rsp+1FE0h] [rbp-FC8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2FA8h] [rbp+0h]

  v3 = (int)a3;
  v5 = StringCchPrintfW(v40, 0x7D0u, L"\\\\.\\PIPE\\%ws", a3);
  try
  {
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FE,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)(unsigned int)v5,
        dwCreationDisposition);
      return v6;
    }
    v7 = StringCchPrintfW(FileName, 0x7D0u, v40, L"UIA_PIPE");
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FF,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)(unsigned int)v7,
        dwCreationDisposition);
      return v8;
    }
    FileW = (char *)CreateFileW(FileName, 0xC0000000, 0, 0, 3u, 0x40010000u, 0);
    v33 = FileW;
    if ( FileW != (char *)-1LL )
      goto LABEL_6;
    CurrentProcessId = GetCurrentProcessId();
    if ( (int)GetObjectPathForProcess(CurrentProcessId, 0x7D0u, v42, 0, 0) < 0 )
      goto LABEL_22;
    v22 = StringCchPrintfW(v40, 0x7D0u, L"\\\\.\\PIPE\\LOCAL\\%ws\\%ws", v42);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x613,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)(unsigned int)v22,
        v3);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
      return v23;
    }
    v24 = StringCchPrintfW(FileName, 0x7D0u, v40, L"UIA_PIPE");
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x614,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)(unsigned int)v24,
        v3);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
      return v25;
    }
    v26 = CreateFileW(FileName, 0xC0000000, 0, 0, 3u, 0x40010000u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v33,
      v26);
    FileW = v33;
    if ( v33 == (char *)-1LL )
    {
LABEL_22:
      v27 = Error::Win32Error(L"CreateFile", L"Connecting to client");
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
      result = v27;
    }
    else
    {
LABEL_6:
      Mode = 2;
      if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
      {
        ServerProcessId = 0;
        GetNamedPipeServerProcessId(FileW, &ServerProcessId);
        v12 = (ChannelBasedServerConnection *)operator new(0xC8u);
        v13 = ChannelBasedServerConnection::ChannelBasedServerConnection(v12, this, ServerProcessId);
        v14 = v13;
        v36 = v13;
        if ( v13 )
        {
          v15 = ChannelBasedServerConnection::Init(v13);
          v16 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x644,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
              (const char *)(unsigned int)v15,
              dwCreationDispositiona);
            (**((void (__fastcall ***)(__int64, __int64))v14 + 13))((__int64)v14 + 104, 1);
            if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(FileW);
            result = v16;
          }
          else
          {
            *(_QWORD *)v37 = 0;
            v17 = ServerProcessId;
            ServerVersionExchangePayload = anonymous_namespace_::MakeServerVersionExchangePayload(v39);
            v38 = 0;
            v35 = FileW;
            v33 = 0;
            v19 = OverlappedIOManager::AddReadWriteChannel(
                    (int)this + 144,
                    (unsigned int)&v35,
                    (unsigned int)&v38,
                    (int)v14 + 120,
                    (__int64)v37,
                    ServerVersionExchangePayload,
                    0,
                    v17,
                    0);
            v20 = v19;
            if ( v19 >= 0 )
            {
              *((_QWORD *)v14 + 17) = *(_QWORD *)v37;
              v36 = 0;
              std::unique_ptr<ChannelBasedServerConnection>::~unique_ptr<ChannelBasedServerConnection>(&v36);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x64F,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
                (const char *)(unsigned int)v19,
                dwCreationDispositionb);
              (**((void (__fastcall ***)(__int64, __int64))v14 + 13))((__int64)v14 + 104, 1);
              result = v20;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x643,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
            (const char *)0x8007000ELL,
            dwCreationDispositiona);
          std::unique_ptr<ChannelBasedServerConnection>::~unique_ptr<ChannelBasedServerConnection>(&v36);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
          result = 2147942414LL;
        }
      }
      else
      {
        v28 = Error::Win32Error(L"SetNamedPipeHandleState", L"Connecting to client");
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
        result = v28;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x656,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1801091e0  mov     [rsp+arg_8], rbx
0x1801091e5  push    rsi
0x1801091e6  push    rdi
0x1801091e7  push    r14
0x1801091e9  mov     eax, 2F90h
0x1801091ee  call    _alloca_probe
0x1801091f3  sub     rsp, rax
0x1801091f6  mov     rax, cs:__security_cookie
0x1801091fd  xor     rax, rsp
0x180109200  mov     [rsp+2FA8h+var_28], rax
0x180109208  mov     rdi, r8
0x18010920b  mov     r14, rcx
0x18010920e  mov     r9, r8
0x180109211  lea     r8, aPipeWs; "\\\\.\\PIPE\\%ws"
0x180109218  mov     esi, 7D0h
0x18010921d  mov     edx, esi; unsigned __int64
0x18010921f  lea     rcx, [rsp+2FA8h+var_2F08]; unsigned __int16 *
0x180109227  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010922c  mov     ebx, eax
0x18010922e  test    eax, eax
0x180109230  js      loc_180109489
0x180109236  lea     r9, aUiaPipe; "UIA_PIPE"
0x18010923d  lea     r8, [rsp+2FA8h+var_2F08]; unsigned __int16 *
0x180109245  mov     edx, esi; unsigned __int64
0x180109247  lea     rcx, [rsp+2FA8h+FileName]; unsigned __int16 *
0x18010924f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180109254  mov     ebx, eax
0x180109256  test    eax, eax
0x180109258  jns     short loc_18010929C
0x18010925a  mov     rcx, [rsp+2FA8h]; this
0x180109262  mov     r9d, eax; char *
0x180109265  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18010926c  mov     edx, 5FFh; void *
0x180109271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109276  mov     eax, ebx
0x180109278  mov     rcx, [rsp+2FA8h+var_28]
0x180109280  xor     rcx, rsp; StackCookie
0x180109283  call    __security_check_cookie
0x180109288  mov     rbx, [rsp+2FA8h+arg_8]
0x180109290  add     rsp, 2F90h
0x180109297  pop     r14
0x180109299  pop     rdi
0x18010929a  pop     rsi
0x18010929b  retn
0x18010929c  mov     [rsp+2FA8h+hTemplateFile], 0; hTemplateFile
0x1801092a5  mov     [rsp+2FA8h+dwFlagsAndAttributes], 40010000h; dwFlagsAndAttributes
0x1801092ad  mov     [rsp+2FA8h+dwCreationDisposition], 3; int
0x1801092b5  xor     r9d, r9d; lpSecurityAttributes
0x1801092b8  xor     r8d, r8d; dwShareMode
0x1801092bb  mov     edx, 0C0000000h; dwDesiredAccess
0x1801092c0  lea     rcx, [rsp+2FA8h+FileName]; lpFileName
0x1801092c8  call    cs:__imp_CreateFileW
0x1801092ce  mov     rbx, rax
0x1801092d1  mov     [rsp+2FA8h+var_2F50], rax
0x1801092d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801092da  jz      loc_1801094AC
0x1801092e0  mov     [rsp+2FA8h+Mode], 2
0x1801092e8  xor     r9d, r9d; lpCollectDataTimeout
0x1801092eb  xor     r8d, r8d; lpMaxCollectionCount
0x1801092ee  lea     rdx, [rsp+2FA8h+Mode]; lpMode
0x1801092f3  mov     rcx, rbx; hNamedPipe
0x1801092f6  call    cs:__imp_SetNamedPipeHandleState
0x1801092fc  test    eax, eax
0x1801092fe  jz      loc_1801095F6
0x180109304  mov     [rsp+2FA8h+ServerProcessId], 0
0x18010930c  lea     rdx, [rsp+2FA8h+ServerProcessId]; ServerProcessId
0x180109311  mov     rcx, rbx; Pipe
0x180109314  call    cs:__imp_GetNamedPipeServerProcessId
0x18010931a  mov     ecx, 0C8h; Size
0x18010931f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180109324  mov     r8d, [rsp+2FA8h+ServerProcessId]; unsigned int
0x180109329  mov     rdx, r14; struct ChannelBasedServerConnectionManager *
0x18010932c  mov     rcx, rax; this
0x18010932f  call    ??0ChannelBasedServerConnection@@QEAA@PEAVChannelBasedServerConnectionManager@@K@Z; ChannelBasedServerConnection::ChannelBasedServerConnection(ChannelBasedServerConnectionManager *,ulong)
0x180109334  mov     rdi, rax
0x180109337  mov     [rsp+2FA8h+var_2F38], rax
0x18010933c  test    rax, rax
0x18010933f  jnz     short loc_18010937F
0x180109341  mov     rcx, [rsp+2FA8h]; this
0x180109349  mov     ebx, 8007000Eh
0x18010934e  mov     r9d, ebx; char *
0x180109351  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x180109358  mov     edx, 643h; void *
0x18010935d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109362  nop
0x180109363  lea     rcx, [rsp+2FA8h+var_2F38]
0x180109368  call    ??1?$unique_ptr@VChannelBasedServerConnection@@U?$default_delete@VChannelBasedServerConnection@@@std@@@std@@QEAA@XZ; std::unique_ptr<ChannelBasedServerConnection>::~unique_ptr<ChannelBasedServerConnection>(void)
0x18010936d  nop
0x18010936e  lea     rcx, [rsp+2FA8h+var_2F50]
0x180109373  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180109378  mov     eax, ebx
0x18010937a  jmp     loc_180109278
0x18010937f  mov     rcx, rdi; this
0x180109382  call    ?Init@ChannelBasedServerConnection@@QEAAJXZ; ChannelBasedServerConnection::Init(void)
0x180109387  mov     esi, eax
0x180109389  test    eax, eax
0x18010938b  js      loc_180109442
0x180109391  mov     qword ptr [rsp+2FA8h+var_2F30], 0
0x18010939a  mov     esi, [rsp+2FA8h+ServerProcessId]
0x18010939e  lea     rcx, [rsp+2FA8h+var_2F20]
0x1801093a6  call    _anonymous_namespace___MakeServerVersionExchangePayload
0x1801093ab  mov     [rsp+2FA8h+var_2F28], 0
0x1801093b7  mov     [rsp+2FA8h+var_2F40], rbx
0x1801093bc  mov     [rsp+2FA8h+var_2F50], 0
0x1801093c5  lea     r9, [rdi+78h]
0x1801093c9  mov     [rsp+2FA8h+var_2F68], 0
0x1801093ce  mov     [rsp+2FA8h+var_2F70], esi
0x1801093d2  mov     byte ptr [rsp+2FA8h+hTemplateFile], 0
0x1801093d7  mov     qword ptr [rsp+2FA8h+dwFlagsAndAttributes], rax
0x1801093dc  lea     rax, [rsp+2FA8h+var_2F30]
0x1801093e1  mov     qword ptr [rsp+2FA8h+dwCreationDisposition], rax; int
0x1801093e6  lea     r8, [rsp+2FA8h+var_2F28]
0x1801093ee  lea     rdx, [rsp+2FA8h+var_2F40]
0x1801093f3  lea     rcx, [r14+90h]
0x1801093fa  call    ?AddReadWriteChannel@OverlappedIOManager@@QEAAJV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@std@@PEAUIReadWriteChannelCallback@@PEAPEAUIReadWriteChannel@@V?$vector@EV?$allocator@E@std@@@5@_NI5@Z; OverlappedIOManager::AddReadWriteChannel(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard>,IReadWriteChannelCallback *,IReadWriteChannel * *,std::vector<uchar>,bool,uint,bool)
0x1801093ff  mov     ebx, eax
0x180109401  test    eax, eax
0x180109403  jns     loc_18010962A
0x180109409  mov     rcx, [rsp+2FA8h]; this
0x180109411  mov     r9d, eax; char *
0x180109414  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18010941b  mov     edx, 64Fh; void *
0x180109420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109425  nop
0x180109426  lea     rcx, [rdi+68h]
0x18010942a  mov     rdx, [rcx]
0x18010942d  mov     rax, [rdx]
0x180109430  mov     edx, 1
0x180109435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010943a  nop
0x18010943b  mov     eax, ebx
0x18010943d  jmp     loc_180109278
0x180109442  mov     rcx, [rsp+2FA8h]; this
0x18010944a  mov     r9d, esi; char *
0x18010944d  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x180109454  mov     edx, 644h; void *
0x180109459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010945e  nop
0x18010945f  lea     rcx, [rdi+68h]
0x180109463  mov     rdx, [rcx]
0x180109466  mov     rax, [rdx]
0x180109469  mov     edx, 1
0x18010946e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109473  nop
0x180109474  lea     rax, [rbx-1]
0x180109478  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010947c  jbe     loc_18010961C
0x180109482  mov     eax, esi
0x180109484  jmp     loc_180109278
0x180109489  mov     rcx, [rsp+2FA8h]; this
0x180109491  mov     r9d, ebx; char *
0x180109494  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18010949b  mov     edx, 5FEh; void *
0x1801094a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801094a5  mov     eax, ebx
0x1801094a7  jmp     loc_180109278
0x1801094ac  call    cs:__imp_GetCurrentProcessId
0x1801094b2  mov     ecx, eax; unsigned int
0x1801094b4  mov     qword ptr [rsp+2FA8h+dwCreationDisposition], 0; pszDest
0x1801094bd  xor     r9d, r9d; cchDest
0x1801094c0  lea     r8, [rsp+2FA8h+var_FC8]; unsigned __int16 *
0x1801094c8  mov     edx, esi; unsigned int
0x1801094ca  call    ?GetObjectPathForProcess@@YAJKKPEAGK0@Z; GetObjectPathForProcess(ulong,ulong,ushort *,ulong,ushort *)
0x1801094cf  test    eax, eax
0x1801094d1  js      loc_1801095D0
0x1801094d7  mov     qword ptr [rsp+2FA8h+dwCreationDisposition], rdi; int
0x1801094dc  lea     r9, [rsp+2FA8h+var_FC8]
0x1801094e4  lea     r8, aPipeLocalWsWs; "\\\\.\\PIPE\\LOCAL\\%ws\\%ws"
0x1801094eb  mov     rdx, rsi; unsigned __int64
0x1801094ee  lea     rcx, [rsp+2FA8h+var_2F08]; unsigned __int16 *
0x1801094f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801094fb  mov     ebx, eax
0x1801094fd  test    eax, eax
0x1801094ff  jns     short loc_18010952F
0x180109501  mov     rcx, [rsp+2FA8h]; this
0x180109509  mov     r9d, eax; char *
0x18010950c  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x180109513  mov     edx, 613h; void *
0x180109518  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010951d  nop
0x18010951e  lea     rcx, [rsp+2FA8h+var_2F50]
0x180109523  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180109528  mov     eax, ebx
0x18010952a  jmp     loc_180109278
0x18010952f  lea     r9, aUiaPipe; "UIA_PIPE"
0x180109536  lea     r8, [rsp+2FA8h+var_2F08]; unsigned __int16 *
0x18010953e  mov     rdx, rsi; unsigned __int64
0x180109541  lea     rcx, [rsp+2FA8h+FileName]; unsigned __int16 *
0x180109549  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010954e  mov     ebx, eax
0x180109550  test    eax, eax
0x180109552  jns     short loc_180109582
0x180109554  mov     rcx, [rsp+2FA8h]; this
0x18010955c  mov     r9d, eax; char *
0x18010955f  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x180109566  mov     edx, 614h; void *
0x18010956b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109570  nop
0x180109571  lea     rcx, [rsp+2FA8h+var_2F50]
0x180109576  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010957b  mov     eax, ebx
0x18010957d  jmp     loc_180109278
0x180109582  mov     [rsp+2FA8h+hTemplateFile], 0; hTemplateFile
0x18010958b  mov     [rsp+2FA8h+dwFlagsAndAttributes], 40010000h; dwFlagsAndAttributes
0x180109593  mov     [rsp+2FA8h+dwCreationDisposition], 3; dwCreationDisposition
0x18010959b  xor     r9d, r9d; lpSecurityAttributes
0x18010959e  xor     r8d, r8d; dwShareMode
0x1801095a1  mov     edx, 0C0000000h; dwDesiredAccess
0x1801095a6  lea     rcx, [rsp+2FA8h+FileName]; lpFileName
0x1801095ae  call    cs:__imp_CreateFileW
0x1801095b4  mov     rdx, rax
0x1801095b7  lea     rcx, [rsp+2FA8h+var_2F50]
0x1801095bc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801095c1  mov     rbx, [rsp+2FA8h+var_2F50]
0x1801095c6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801095ca  jnz     loc_1801092E0
0x1801095d0  lea     rdx, aConnectingToCl; "Connecting to client"
0x1801095d7  lea     rcx, aCreatefile; "CreateFile"
0x1801095de  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x1801095e3  mov     ebx, eax
0x1801095e5  lea     rcx, [rsp+2FA8h+var_2F50]
0x1801095ea  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801095ef  mov     eax, ebx
0x1801095f1  jmp     loc_180109278
0x1801095f6  lea     rdx, aConnectingToCl; "Connecting to client"
0x1801095fd  lea     rcx, aSetnamedpipeha; "SetNamedPipeHandleState"
0x180109604  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x180109609  mov     ebx, eax
0x18010960b  lea     rcx, [rsp+2FA8h+var_2F50]
0x180109610  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180109615  mov     eax, ebx
0x180109617  jmp     loc_180109278
0x18010961c  mov     rcx, rbx; hObject
0x18010961f  call    cs:__imp_CloseHandle
0x180109625  jmp     loc_180109482
0x18010962a  mov     rax, qword ptr [rsp+2FA8h+var_2F30]
0x18010962f  mov     [rdi+88h], rax
0x180109636  mov     [rsp+2FA8h+var_2F38], 0
0x18010963f  lea     rcx, [rsp+2FA8h+var_2F38]
0x180109644  call    ??1?$unique_ptr@VChannelBasedServerConnection@@U?$default_delete@VChannelBasedServerConnection@@@std@@@std@@QEAA@XZ; std::unique_ptr<ChannelBasedServerConnection>::~unique_ptr<ChannelBasedServerConnection>(void)
0x180109649  nop
0x18010964a  lea     rcx, [rsp+2FA8h+var_2F50]
0x18010964f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180109654  xor     eax, eax
0x180109656  jmp     loc_180109278
0x18010965b  mov     eax, [rsp+2FA8h+Mode]
0x18010965f  jmp     loc_180109278
```
