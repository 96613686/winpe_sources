# SystemSettings::StorageSenseHandlers::AgentToolList::GetUnfilteredMcpClientInfo(std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition,std::allocator<SystemSettings::StorageSenseHandlers::McpClientDefinition>> &)

- ea: `0x18002f474`
- end: `0x18002f9aa`
- name: `?GetUnfilteredMcpClientInfo@AgentToolList@StorageSenseHandlers@SystemSettings@@CAJAEAV?$vector@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@@Z`
- size: `1334`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b2f0`
- `0x18002d11c`

## callees

- `0x180001a9c`
- `0x180006e50`
- `0x180007a00`
- `0x180009b2f`
- `0x18000e6ac`
- `0x180014940`
- `0x180016ef4`
- `0x18001fe08`
- `0x180023578`
- `0x180023928`
- `0x1800259ac`
- `0x180027138`
- `0x180029264`
- `0x180029288`
- `0x18002f474`
- `0x180031410`
- `0x180034d64`
- `0x1800353a4`
- `0x1800359cc`
- `0x180035b90`
- `0x180035bd4`
- `0x1800dba40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6a1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002f693`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002f693`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18002f568`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18002f568`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18002f51d`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18002f51d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002f7ab`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002f7ab`

## string_xrefs

- `0x18002f52f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\agenttoollist.cpp`
- `0x18002f57a`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\agenttoollist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::AgentToolList::GetUnfilteredMcpClientInfo(_QWORD *a1)
{
  void **v2; // rbx
  void **v3; // rax
  const char *v4; // r9
  unsigned int v5; // ebx
  int v7; // edx
  __int64 v8; // rcx
  int v9; // r8d
  const char *v10; // r9
  unsigned int v11; // ebx
  int value_nothrow; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  WCHAR *v15; // rax
  signed int LastError; // ebx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rsi
  __int64 v20; // rcx
  __int128 *p_Src; // rbx
  char *v22; // rbx
  _QWORD *v23; // rbx
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  void *v27; // [rsp+50h] [rbp-1188h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-1180h] BYREF
  HANDLE hProcess; // [rsp+60h] [rbp-1178h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-1170h] BYREF
  __int64 v31; // [rsp+70h] [rbp-1168h] BYREF
  const WCHAR *hThread; // [rsp+78h] [rbp-1160h] BYREF
  _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+80h] [rbp-1158h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-1140h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-1128h] BYREF
  __int128 Src; // [rsp+120h] [rbp-10B8h] BYREF
  __int64 v37; // [rsp+130h] [rbp-10A8h]
  unsigned __int64 v38; // [rsp+138h] [rbp-10A0h]
  _BYTE v39[32]; // [rsp+140h] [rbp-1098h] BYREF
  _BYTE v40[32]; // [rsp+160h] [rbp-1078h] BYREF
  _BYTE v41[32]; // [rsp+180h] [rbp-1058h] BYREF
  _BYTE Buffer[4096]; // [rsp+1A0h] [rbp-1038h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+11D8h] [rbp+0h]

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 256;
  *(_QWORD *)&PipeAttributes.nLength = 24;
  *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
  PipeAttributes.lpSecurityDescriptor = 0;
  hObject = 0;
  v27 = 0;
  v2 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v27);
  v3 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hObject);
  if ( CreatePipe(v3, v2, &PipeAttributes, 0) )
  {
    if ( SetHandleInformation(hObject, 1u, 0) )
    {
      StartupInfo.hStdOutput = v27;
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      v31 = 0;
      value_nothrow = wil::reg::get_value_nothrow(v8, v7, v9, (int)&v31);
      if ( value_nothrow >= 0 && v31 )
      {
        v13 = std::wstring::wstring(v41);
        v14 = std::operator+<unsigned short>(v40, v13, L" ");
        std::operator+<unsigned short>(v39, v14, L"management listclients");
        std::wstring::_Tidy_deallocate(v40);
        std::wstring::_Tidy_deallocate(v41);
        v15 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
        if ( CreateProcessW(0, v15, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          hProcess = ProcessInformation.hProcess;
          hThread = (const WCHAR *)ProcessInformation.hThread;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v27,
            0);
          Src = 0;
          v37 = 0;
          v38 = 15;
          LOBYTE(Src) = 0;
          NumberOfBytesRead = 0;
          while ( ReadFile(hObject, Buffer, 0x1000u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
          {
            v19 = NumberOfBytesRead;
            v20 = v37;
            if ( NumberOfBytesRead > v38 - v37 )
            {
              std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
                &Src,
                NumberOfBytesRead);
            }
            else
            {
              v37 += NumberOfBytesRead;
              p_Src = &Src;
              if ( v38 > 0xF )
                p_Src = (__int128 *)Src;
              v22 = (char *)p_Src + v20;
              memmove_0(v22, Buffer, NumberOfBytesRead);
              v22[v19] = 0;
            }
          }
          v23 = (_QWORD *)SystemSettings::StorageSenseHandlers::AgentToolList::ParseMcpClientDefinitions(v40, &Src);
          if ( a1 != v23 )
          {
            std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::_Tidy(a1);
            *a1 = *v23;
            a1[1] = v23[1];
            a1[2] = v23[2];
            *v23 = 0;
            v23[1] = 0;
            v23[2] = 0;
          }
          std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::_Tidy(v40);
          if ( v38 > 0xF )
            std::_Deallocate<16>(Src, v38 + 1);
          v37 = 0;
          v38 = 15;
          LOBYTE(Src) = 0;
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
          std::wstring::_Tidy_deallocate(v39);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
          return 0;
        }
        else
        {
          LastError = GetLastError();
          if ( *(_DWORD *)SettingsHandlersStorageSenseLogging::Provider() > 3u )
          {
            hThread = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            LODWORD(hProcess) = LastError;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v17,
              (unsigned int)&unk_18014F7B3,
              v17,
              v18,
              (__int64)&hProcess,
              (__int64)&hThread);
          }
          std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::clear(a1);
          std::wstring::_Tidy_deallocate(v39);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
          return 0;
        }
      }
      else
      {
        v24 = SettingsHandlersStorageSenseLogging::Provider();
        if ( *(_DWORD *)v24 > 3u )
        {
          hThread = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Mcp";
          LODWORD(hProcess) = value_nothrow;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v24,
            (unsigned int)&unk_18014F813,
            v25,
            v26,
            (__int64)&hProcess,
            (__int64)&hThread);
        }
        std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::clear(a1);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        return 0;
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xF6,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\agenttoollist.cpp",
              v10);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return v11;
    }
  }
  else
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0xF5,
           (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\agenttoollist.cpp",
           v4);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return v5;
  }
}

```

## disassembly

```asm
0x18002f474  push    rbx
0x18002f476  push    rsi
0x18002f477  push    rdi
0x18002f478  push    r14
0x18002f47a  mov     eax, 11B8h
0x18002f47f  call    _alloca_probe
0x18002f484  sub     rsp, rax
0x18002f487  mov     rax, cs:__security_cookie
0x18002f48e  xor     rax, rsp
0x18002f491  mov     [rsp+11D8h+var_38], rax
0x18002f499  mov     rdi, rcx
0x18002f49c  mov     ebx, 68h ; 'h'
0x18002f4a1  mov     r8d, ebx; Size
0x18002f4a4  xor     edx, edx; Val
0x18002f4a6  lea     rcx, [rsp+11D8h+StartupInfo]; void *
0x18002f4ae  call    memset_0
0x18002f4b3  mov     [rsp+11D8h+StartupInfo.cb], ebx
0x18002f4ba  mov     [rsp+11D8h+StartupInfo.dwFlags], 100h
0x18002f4c5  xor     r14d, r14d
0x18002f4c8  mov     qword ptr [rsp+11D8h+PipeAttributes.nLength], 18h
0x18002f4d4  mov     qword ptr [rsp+11D8h+PipeAttributes.bInheritHandle], 1
0x18002f4e0  lea     esi, [rbx-67h]
0x18002f4e3  mov     [rsp+11D8h+PipeAttributes.lpSecurityDescriptor], r14
0x18002f4eb  mov     [rsp+11D8h+hObject], r14
0x18002f4f0  mov     [rsp+11D8h+var_1188], r14
0x18002f4f5  lea     rcx, [rsp+11D8h+var_1188]
0x18002f4fa  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18002f4ff  mov     rbx, rax
0x18002f502  lea     rcx, [rsp+11D8h+hObject]
0x18002f507  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18002f50c  xor     r9d, r9d; nSize
0x18002f50f  lea     r8, [rsp+11D8h+PipeAttributes]; lpPipeAttributes
0x18002f517  mov     rdx, rbx; hWritePipe
0x18002f51a  mov     rcx, rax; hReadPipe
0x18002f51d  call    cs:__imp_CreatePipe
0x18002f523  test    eax, eax
0x18002f525  jnz     short loc_18002F55E
0x18002f527  mov     rcx, [rsp+11D8h]; this
0x18002f52f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\coresettinghandlers"...
0x18002f536  mov     edx, 0F5h; void *
0x18002f53b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f540  mov     ebx, eax
0x18002f542  lea     rcx, [rsp+11D8h+var_1188]
0x18002f547  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f54c  nop
0x18002f54d  lea     rcx, [rsp+11D8h+hObject]
0x18002f552  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f557  mov     eax, ebx
0x18002f559  jmp     loc_18002F98C
0x18002f55e  xor     r8d, r8d; dwFlags
0x18002f561  mov     edx, esi; dwMask
0x18002f563  mov     rcx, [rsp+11D8h+hObject]; hObject
0x18002f568  call    cs:__imp_SetHandleInformation
0x18002f56e  test    eax, eax
0x18002f570  jnz     short loc_18002F5A9
0x18002f572  mov     rcx, [rsp+11D8h]; this
0x18002f57a  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\coresettinghandlers"...
0x18002f581  mov     edx, 0F6h; void *
0x18002f586  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f58b  mov     ebx, eax
0x18002f58d  lea     rcx, [rsp+11D8h+var_1188]
0x18002f592  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f597  nop
0x18002f598  lea     rcx, [rsp+11D8h+hObject]
0x18002f59d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f5a2  mov     eax, ebx
0x18002f5a4  jmp     loc_18002F98C
0x18002f5a9  mov     rax, [rsp+11D8h+var_1188]
0x18002f5ae  mov     [rsp+11D8h+StartupInfo.hStdOutput], rax
0x18002f5b6  xorps   xmm0, xmm0
0x18002f5b9  xor     eax, eax
0x18002f5bb  movups  xmmword ptr [rsp+11D8h+ProcessInformation.hProcess], xmm0
0x18002f5c3  mov     qword ptr [rsp+11D8h+ProcessInformation.dwProcessId], rax
0x18002f5cb  mov     [rsp+11D8h+var_1168], r14
0x18002f5d0  lea     r9, [rsp+11D8h+var_1168]
0x18002f5d5  call    ?get_value_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBG1AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z; wil::reg::get_value_nothrow(HKEY__ *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002f5da  mov     ebx, eax
0x18002f5dc  test    eax, eax
0x18002f5de  js      loc_18002F91C
0x18002f5e4  mov     rdx, [rsp+11D8h+var_1168]
0x18002f5e9  test    rdx, rdx
0x18002f5ec  jz      loc_18002F91C
0x18002f5f2  lea     rcx, [rsp+11D8h+var_1058]
0x18002f5fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f5ff  nop
0x18002f600  lea     r8, asc_180108014; " "
0x18002f607  mov     rdx, rax
0x18002f60a  lea     rcx, [rsp+11D8h+var_1078]
0x18002f612  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002f617  nop
0x18002f618  lea     r8, aManagementList; "management listclients"
0x18002f61f  mov     rdx, rax
0x18002f622  lea     rcx, [rsp+11D8h+var_1098]
0x18002f62a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002f62f  nop
0x18002f630  lea     rcx, [rsp+11D8h+var_1078]
0x18002f638  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f63d  nop
0x18002f63e  lea     rcx, [rsp+11D8h+var_1058]
0x18002f646  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f64b  lea     rcx, [rsp+11D8h+var_1098]
0x18002f653  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f658  mov     rdx, rax; lpCommandLine
0x18002f65b  lea     rax, [rsp+11D8h+ProcessInformation]
0x18002f663  mov     [rsp+11D8h+lpProcessInformation], rax; lpProcessInformation
0x18002f668  lea     rax, [rsp+11D8h+StartupInfo]
0x18002f670  mov     [rsp+11D8h+lpStartupInfo], rax; lpStartupInfo
0x18002f675  mov     [rsp+11D8h+lpCurrentDirectory], r14; lpCurrentDirectory
0x18002f67a  mov     [rsp+11D8h+lpEnvironment], r14; lpEnvironment
0x18002f67f  mov     [rsp+11D8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18002f687  mov     [rsp+11D8h+bInheritHandles], esi; bInheritHandles
0x18002f68b  xor     r9d, r9d; lpThreadAttributes
0x18002f68e  xor     r8d, r8d; lpProcessAttributes
0x18002f691  xor     ecx, ecx; lpApplicationName
0x18002f693  call    cs:__imp_CreateProcessW
0x18002f699  test    eax, eax
0x18002f69b  jnz     loc_18002F73C
0x18002f6a1  call    cs:__imp_GetLastError
0x18002f6a7  mov     ebx, eax
0x18002f6a9  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18002f6ae  mov     r8, rax
0x18002f6b1  mov     ecx, [rax]
0x18002f6b3  cmp     ecx, 3
0x18002f6b6  jbe     short loc_18002F6FE
0x18002f6b8  lea     rcx, [rsp+11D8h+var_1098]
0x18002f6c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f6c5  mov     [rsp+11D8h+var_1160], rax
0x18002f6ca  test    ebx, ebx
0x18002f6cc  jle     short loc_18002F6D7
0x18002f6ce  movzx   ebx, bx
0x18002f6d1  or      ebx, 80070000h
0x18002f6d7  mov     dword ptr [rsp+11D8h+var_1178], ebx
0x18002f6db  lea     rax, [rsp+11D8h+var_1160]
0x18002f6e0  mov     qword ptr [rsp+11D8h+dwCreationFlags], rax
0x18002f6e5  lea     rax, [rsp+11D8h+var_1178]
0x18002f6ea  mov     qword ptr [rsp+11D8h+bInheritHandles], rax
0x18002f6ef  lea     rdx, unk_18014F7B3
0x18002f6f6  mov     rcx, r8
0x18002f6f9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002f6fe  mov     rcx, rdi
0x18002f701  call    ?clear@?$vector@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@QEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::clear(void)
0x18002f706  nop
0x18002f707  lea     rcx, [rsp+11D8h+var_1098]
0x18002f70f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f714  nop
0x18002f715  lea     rcx, [rsp+11D8h+var_1168]
0x18002f71a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002f71f  nop
0x18002f720  lea     rcx, [rsp+11D8h+var_1188]
0x18002f725  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f72a  nop
0x18002f72b  lea     rcx, [rsp+11D8h+hObject]
0x18002f730  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f735  xor     eax, eax
0x18002f737  jmp     loc_18002F98C
0x18002f73c  mov     rax, [rsp+11D8h+ProcessInformation.hProcess]
0x18002f744  mov     [rsp+11D8h+var_1178], rax
0x18002f749  mov     rax, [rsp+11D8h+ProcessInformation.hThread]
0x18002f751  mov     [rsp+11D8h+var_1160], rax
0x18002f756  xor     edx, edx
0x18002f758  lea     rcx, [rsp+11D8h+var_1188]
0x18002f75d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002f762  xorps   xmm0, xmm0
0x18002f765  movups  [rsp+11D8h+Src], xmm0
0x18002f76d  mov     [rsp+11D8h+var_10A8], r14
0x18002f775  mov     [rsp+11D8h+var_10A0], 0Fh
0x18002f781  mov     byte ptr [rsp+11D8h+Src], r14b
0x18002f789  mov     [rsp+11D8h+NumberOfBytesRead], r14d
0x18002f78e  mov     qword ptr [rsp+11D8h+bInheritHandles], r14; lpOverlapped
0x18002f793  lea     r9, [rsp+11D8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002f798  mov     r8d, 1000h; nNumberOfBytesToRead
0x18002f79e  lea     rdx, [rsp+11D8h+Buffer]; lpBuffer
0x18002f7a6  mov     rcx, [rsp+11D8h+hObject]; hFile
0x18002f7ab  call    cs:__imp_ReadFile
0x18002f7b1  test    eax, eax
0x18002f7b3  jz      loc_18002F846
0x18002f7b9  mov     eax, [rsp+11D8h+NumberOfBytesRead]
0x18002f7bd  test    eax, eax
0x18002f7bf  jz      loc_18002F846
0x18002f7c5  mov     esi, eax
0x18002f7c7  mov     rcx, [rsp+11D8h+var_10A8]
0x18002f7cf  mov     rax, [rsp+11D8h+var_10A0]
0x18002f7d7  sub     rax, rcx
0x18002f7da  cmp     rsi, rax
0x18002f7dd  ja      short loc_18002F824
0x18002f7df  lea     rax, [rsi+rcx]
0x18002f7e3  mov     [rsp+11D8h+var_10A8], rax
0x18002f7eb  lea     rbx, [rsp+11D8h+Src]
0x18002f7f3  cmp     [rsp+11D8h+var_10A0], 0Fh
0x18002f7fc  cmova   rbx, qword ptr [rsp+11D8h+Src]
0x18002f805  add     rbx, rcx
0x18002f808  mov     r8d, esi; Size
0x18002f80b  lea     rdx, [rsp+11D8h+Buffer]; Src
0x18002f813  mov     rcx, rbx; void *
0x18002f816  call    memmove_0
0x18002f81b  mov     [rbx+rsi], r14b
0x18002f81f  jmp     loc_18002F78E
0x18002f824  mov     qword ptr [rsp+11D8h+bInheritHandles], rsi; Size
0x18002f829  lea     r9, [rsp+11D8h+Buffer]
0x18002f831  mov     rdx, rsi
0x18002f834  lea     rcx, [rsp+11D8h+Src]; Src
0x18002f83c  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18002f841  jmp     loc_18002F78E
0x18002f846  lea     rdx, [rsp+11D8h+Src]
0x18002f84e  lea     rcx, [rsp+11D8h+var_1078]
0x18002f856  call    ?ParseMcpClientDefinitions@AgentToolList@StorageSenseHandlers@SystemSettings@@CA?AV?$vector@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; SystemSettings::StorageSenseHandlers::AgentToolList::ParseMcpClientDefinitions(std::string const &)
0x18002f85b  mov     rbx, rax
0x18002f85e  cmp     rdi, rax
0x18002f861  jz      short loc_18002F88C
0x18002f863  mov     rcx, rdi
0x18002f866  call    ?_Tidy@?$vector@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::_Tidy(void)
0x18002f86b  mov     rcx, [rbx]
0x18002f86e  mov     [rdi], rcx
0x18002f871  mov     rcx, [rbx+8]
0x18002f875  mov     [rdi+8], rcx
0x18002f879  mov     rcx, [rbx+10h]
0x18002f87d  mov     [rdi+10h], rcx
0x18002f881  mov     [rbx], r14
0x18002f884  mov     [rbx+8], r14
0x18002f888  mov     [rbx+10h], r14
0x18002f88c  lea     rcx, [rsp+11D8h+var_1078]
0x18002f894  call    ?_Tidy@?$vector@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::_Tidy(void)
0x18002f899  nop
0x18002f89a  mov     rdx, [rsp+11D8h+var_10A0]
0x18002f8a2  cmp     rdx, 0Fh
0x18002f8a6  jbe     short loc_18002F8B8
0x18002f8a8  inc     rdx
0x18002f8ab  mov     rcx, qword ptr [rsp+11D8h+Src]
0x18002f8b3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f8b8  mov     [rsp+11D8h+var_10A8], r14
0x18002f8c0  mov     [rsp+11D8h+var_10A0], 0Fh
0x18002f8cc  mov     byte ptr [rsp+11D8h+Src], r14b
0x18002f8d4  lea     rcx, [rsp+11D8h+var_1160]
0x18002f8d9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f8de  nop
0x18002f8df  lea     rcx, [rsp+11D8h+var_1178]
0x18002f8e4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f8e9  nop
0x18002f8ea  lea     rcx, [rsp+11D8h+var_1098]
0x18002f8f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f8f7  nop
0x18002f8f8  lea     rcx, [rsp+11D8h+var_1168]
0x18002f8fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002f902  nop
0x18002f903  lea     rcx, [rsp+11D8h+var_1188]
0x18002f908  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f90d  nop
0x18002f90e  lea     rcx, [rsp+11D8h+hObject]
0x18002f913  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f918  xor     eax, eax
0x18002f91a  jmp     short loc_18002F98C
0x18002f91c  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x18002f921  mov     ecx, [rax]
0x18002f923  cmp     ecx, 3
0x18002f926  jbe     short loc_18002F95B
0x18002f928  lea     rcx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002f92f  mov     [rsp+11D8h+var_1160], rcx
0x18002f934  mov     dword ptr [rsp+11D8h+var_1178], ebx
0x18002f938  lea     rcx, [rsp+11D8h+var_1160]
0x18002f93d  mov     qword ptr [rsp+11D8h+dwCreationFlags], rcx
0x18002f942  lea     rcx, [rsp+11D8h+var_1178]
0x18002f947  mov     qword ptr [rsp+11D8h+bInheritHandles], rcx
0x18002f94c  lea     rdx, unk_18014F813
0x18002f953  mov     rcx, rax
0x18002f956  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002f95b  mov     rcx, rdi
0x18002f95e  call    ?clear@?$vector@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpClientDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@QEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::McpClientDefinition>::clear(void)
0x18002f963  nop
0x18002f964  lea     rcx, [rsp+11D8h+var_1168]
0x18002f969  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002f96e  nop
0x18002f96f  lea     rcx, [rsp+11D8h+var_1188]
0x18002f974  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f979  nop
0x18002f97a  lea     rcx, [rsp+11D8h+hObject]
0x18002f97f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f984  xor     eax, eax
0x18002f986  jmp     short loc_18002F98C
0x18002f988  mov     eax, dword ptr [rsp+11D8h+var_1178]
0x18002f98c  mov     rcx, [rsp+11D8h+var_38]
0x18002f994  xor     rcx, rsp; StackCookie
0x18002f997  call    __security_check_cookie
0x18002f99c  add     rsp, 11B8h
0x18002f9a3  pop     r14
0x18002f9a5  pop     rdi
0x18002f9a6  pop     rsi
0x18002f9a7  pop     rbx
0x18002f9a8  retn
```
