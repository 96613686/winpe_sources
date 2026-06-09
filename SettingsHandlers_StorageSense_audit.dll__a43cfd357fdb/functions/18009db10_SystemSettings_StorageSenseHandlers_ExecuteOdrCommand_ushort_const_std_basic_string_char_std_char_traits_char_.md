# SystemSettings::StorageSenseHandlers::ExecuteOdrCommand(ushort const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,ulong *)

- ea: `0x18009db10`
- end: `0x18009e135`
- name: `?ExecuteOdrCommand@StorageSenseHandlers@SystemSettings@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAK@Z`
- size: `1573`
- prototype: `__int64 __fastcall(__int64, _QWORD *, DWORD *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800499b4`
- `0x18009e268`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x180009b2f`
- `0x18000e6ac`
- `0x18000e6cc`
- `0x180016ef4`
- `0x180023578`
- `0x180023928`
- `0x1800259ac`
- `0x180027138`
- `0x180029264`
- `0x180029288`
- `0x1800359cc`
- `0x180035b90`
- `0x180035bd4`
- `0x18009db10`
- `0x1800dba40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009df04`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009df04`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18009ddce`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18009ddce`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18009df84`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18009df84`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18009dc5e`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18009dc5e`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18009dc12`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x18009dc12`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009de88`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009de88`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::ExecuteOdrCommand(__int64 a1, _QWORD *a2, DWORD *a3)
{
  _BYTE *v7; // rax
  void **v8; // rbx
  void **v9; // rax
  const char *v10; // r9
  unsigned int v11; // ebx
  int v12; // edx
  __int64 v13; // rcx
  int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // ebx
  int value_nothrow; // eax
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  WCHAR *v21; // rax
  const char *v22; // r9
  unsigned int v23; // ebx
  HANDLE hProcess; // rbx
  size_t v25; // r14
  __int64 v26; // rcx
  _QWORD *v27; // rax
  char *v28; // rdi
  const char *v29; // r9
  unsigned int LastError; // ebx
  const char *v31; // r9
  unsigned int v32; // ebx
  DWORD v33; // eax
  int bInheritHandles; // [rsp+20h] [rbp-11A8h]
  int bInheritHandlesa; // [rsp+20h] [rbp-11A8h]
  void *v36; // [rsp+50h] [rbp-1178h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-1170h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-1168h] BYREF
  __int64 v39; // [rsp+68h] [rbp-1160h] BYREF
  DWORD ExitCode; // [rsp+70h] [rbp-1158h] BYREF
  HANDLE hThread; // [rsp+78h] [rbp-1150h] BYREF
  HANDLE v42; // [rsp+80h] [rbp-1148h] BYREF
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+88h] [rbp-1140h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-1128h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-1108h] BYREF
  _BYTE v46[32]; // [rsp+130h] [rbp-1098h] BYREF
  _BYTE v47[32]; // [rsp+150h] [rbp-1078h] BYREF
  _BYTE v48[32]; // [rsp+170h] [rbp-1058h] BYREF
  _BYTE Buffer[4096]; // [rsp+190h] [rbp-1038h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+11C8h] [rbp+0h]

  if ( a1 )
  {
    a2[2] = 0;
    if ( a2[3] <= 0xFu )
      v7 = a2;
    else
      v7 = (_BYTE *)*a2;
    *v7 = 0;
    if ( a3 )
      *a3 = 0;
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 256;
    *(_QWORD *)&PipeAttributes.nLength = 24;
    *(_QWORD *)&PipeAttributes.bInheritHandle = 1;
    PipeAttributes.lpSecurityDescriptor = 0;
    hObject = 0;
    v36 = 0;
    v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v36);
    v9 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&hObject);
    if ( CreatePipe(v9, v8, &PipeAttributes, 0) )
    {
      if ( SetHandleInformation(hObject, 1u, 0) )
      {
        StartupInfo.hStdOutput = v36;
        StartupInfo.hStdError = v36;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        v39 = 0;
        value_nothrow = wil::reg::get_value_nothrow(v13, v12, v14, (int)&v39);
        v18 = value_nothrow;
        if ( value_nothrow >= 0 )
        {
          if ( v39 )
          {
            v19 = std::wstring::wstring(v48);
            v20 = std::operator+<unsigned short>(v47, v19, L" ");
            std::operator+<unsigned short>(v46, v20, a1);
            std::wstring::_Tidy_deallocate(v47);
            std::wstring::_Tidy_deallocate(v48);
            v21 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
            if ( CreateProcessW(0, v21, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
            {
              hProcess = ProcessInformation.hProcess;
              v42 = ProcessInformation.hProcess;
              hThread = ProcessInformation.hThread;
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                &v36,
                0);
              memset_0(Buffer, 0, sizeof(Buffer));
              NumberOfBytesRead = 0;
              while ( ReadFile(hObject, Buffer, 0x1000u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
              {
                v25 = NumberOfBytesRead;
                v26 = a2[2];
                if ( NumberOfBytesRead > (unsigned __int64)(a2[3] - v26) )
                {
                  std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
                    a2,
                    NumberOfBytesRead);
                }
                else
                {
                  a2[2] = v26 + NumberOfBytesRead;
                  if ( a2[3] <= 0xFu )
                    v27 = a2;
                  else
                    v27 = (_QWORD *)*a2;
                  v28 = (char *)v27 + v26;
                  memmove_0((char *)v27 + v26, Buffer, v25);
                  v28[v25] = 0;
                }
              }
              if ( WaitForSingleObject(hProcess, 0xFFFFFFFF) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0xD3,
                              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
                              v29);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
                std::wstring::_Tidy_deallocate(v46);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
                return LastError;
              }
              else
              {
                ExitCode = 0;
                if ( GetExitCodeProcess(hProcess, &ExitCode) )
                {
                  v33 = ExitCode;
                  if ( a3 )
                    *a3 = ExitCode;
                  if ( v33 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xDD,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
                      (const char *)0x80004005LL,
                      bInheritHandlesa);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
                    std::wstring::_Tidy_deallocate(v46);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
                    return 2147500037LL;
                  }
                  else
                  {
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
                    std::wstring::_Tidy_deallocate(v46);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
                    return 0;
                  }
                }
                else
                {
                  v32 = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xD6,
                          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
                          v31);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
                  std::wstring::_Tidy_deallocate(v46);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
                  return v32;
                }
              }
            }
            else
            {
              v23 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xBF,
                      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
                      v22);
              std::wstring::_Tidy_deallocate(v46);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
              return v23;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB2,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
              (const char *)0x80070490LL,
              bInheritHandles);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
            return 2147943568LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB1,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
            (const char *)(unsigned int)value_nothrow,
            bInheritHandles);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
          return v18;
        }
      }
      else
      {
        v16 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xA0,
                (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
                v15);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        return v16;
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x9F,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
              v10);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\odrmcplisthelpers.cpp",
      (const char *)0x80070057LL,
      bInheritHandles);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18009db10  mov     [rsp+arg_18], rbx
0x18009db15  push    rsi
0x18009db16  push    rdi
0x18009db17  push    r12
0x18009db19  push    r14
0x18009db1b  push    r15
0x18009db1d  mov     eax, 11A0h
0x18009db22  call    _alloca_probe
0x18009db27  sub     rsp, rax
0x18009db2a  mov     rax, cs:__security_cookie
0x18009db31  xor     rax, rsp
0x18009db34  mov     [rsp+11C8h+var_38], rax
0x18009db3c  mov     r15, r8
0x18009db3f  mov     rsi, rdx
0x18009db42  mov     rdi, rcx
0x18009db45  xor     r12d, r12d
0x18009db48  test    rcx, rcx
0x18009db4b  jnz     short loc_18009DB75
0x18009db4d  mov     rcx, [rsp+11C8h]; this
0x18009db55  mov     ebx, 80070057h
0x18009db5a  mov     r9d, ebx; char *
0x18009db5d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009db64  mov     edx, 8Bh; void *
0x18009db69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009db6e  mov     eax, ebx
0x18009db70  jmp     loc_18009E10C
0x18009db75  mov     [rdx+10h], r12
0x18009db79  cmp     qword ptr [rdx+18h], 0Fh
0x18009db7e  jbe     short loc_18009DB85
0x18009db80  mov     rax, [rdx]
0x18009db83  jmp     short loc_18009DB88
0x18009db85  mov     rax, rsi
0x18009db88  mov     [rax], r12b
0x18009db8b  test    r15, r15
0x18009db8e  jz      short loc_18009DB93
0x18009db90  mov     [r8], r12d
0x18009db93  mov     ebx, 68h ; 'h'
0x18009db98  mov     r8d, ebx; Size
0x18009db9b  xor     edx, edx; Val
0x18009db9d  lea     rcx, [rsp+11C8h+StartupInfo]; void *
0x18009dba5  call    memset_0
0x18009dbaa  mov     [rsp+11C8h+StartupInfo.cb], ebx
0x18009dbb1  mov     [rsp+11C8h+StartupInfo.dwFlags], 100h
0x18009dbbc  mov     qword ptr [rsp+11C8h+PipeAttributes.nLength], 18h
0x18009dbc8  mov     qword ptr [rsp+11C8h+PipeAttributes.bInheritHandle], 1
0x18009dbd4  lea     r14d, [rbx-67h]
0x18009dbd8  mov     [rsp+11C8h+PipeAttributes.lpSecurityDescriptor], r12
0x18009dbe0  mov     [rsp+11C8h+hObject], r12
0x18009dbe5  mov     [rsp+11C8h+var_1178], r12
0x18009dbea  lea     rcx, [rsp+11C8h+var_1178]
0x18009dbef  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18009dbf4  mov     rbx, rax
0x18009dbf7  lea     rcx, [rsp+11C8h+hObject]
0x18009dbfc  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18009dc01  xor     r9d, r9d; nSize
0x18009dc04  lea     r8, [rsp+11C8h+PipeAttributes]; lpPipeAttributes
0x18009dc0c  mov     rdx, rbx; hWritePipe
0x18009dc0f  mov     rcx, rax; hReadPipe
0x18009dc12  call    cs:__imp_CreatePipe
0x18009dc18  test    eax, eax
0x18009dc1a  jnz     short loc_18009DC53
0x18009dc1c  mov     rcx, [rsp+11C8h]; this
0x18009dc24  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009dc2b  mov     edx, 9Fh; void *
0x18009dc30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009dc35  mov     ebx, eax
0x18009dc37  lea     rcx, [rsp+11C8h+var_1178]
0x18009dc3c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dc41  nop
0x18009dc42  lea     rcx, [rsp+11C8h+hObject]
0x18009dc47  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dc4c  mov     eax, ebx
0x18009dc4e  jmp     loc_18009E10C
0x18009dc53  xor     r8d, r8d; dwFlags
0x18009dc56  mov     edx, r14d; dwMask
0x18009dc59  mov     rcx, [rsp+11C8h+hObject]; hObject
0x18009dc5e  call    cs:__imp_SetHandleInformation
0x18009dc64  test    eax, eax
0x18009dc66  jnz     short loc_18009DC9F
0x18009dc68  mov     rcx, [rsp+11C8h]; this
0x18009dc70  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009dc77  mov     edx, 0A0h; void *
0x18009dc7c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009dc81  mov     ebx, eax
0x18009dc83  lea     rcx, [rsp+11C8h+var_1178]
0x18009dc88  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dc8d  nop
0x18009dc8e  lea     rcx, [rsp+11C8h+hObject]
0x18009dc93  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dc98  mov     eax, ebx
0x18009dc9a  jmp     loc_18009E10C
0x18009dc9f  mov     rax, [rsp+11C8h+var_1178]
0x18009dca4  mov     [rsp+11C8h+StartupInfo.hStdOutput], rax
0x18009dcac  mov     [rsp+11C8h+StartupInfo.hStdError], rax
0x18009dcb4  xorps   xmm0, xmm0
0x18009dcb7  xor     eax, eax
0x18009dcb9  movups  xmmword ptr [rsp+11C8h+ProcessInformation.hProcess], xmm0
0x18009dcc1  mov     qword ptr [rsp+11C8h+ProcessInformation.dwProcessId], rax
0x18009dcc9  mov     [rsp+11C8h+var_1160], r12
0x18009dcce  lea     r9, [rsp+11C8h+var_1160]
0x18009dcd3  call    ?get_value_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBG1AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z; wil::reg::get_value_nothrow(HKEY__ *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18009dcd8  mov     ebx, eax
0x18009dcda  test    eax, eax
0x18009dcdc  jns     short loc_18009DD22
0x18009dcde  mov     rcx, [rsp+11C8h]; this
0x18009dce6  mov     r9d, eax; char *
0x18009dce9  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009dcf0  mov     edx, 0B1h; void *
0x18009dcf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009dcfa  nop
0x18009dcfb  lea     rcx, [rsp+11C8h+var_1160]
0x18009dd00  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009dd05  nop
0x18009dd06  lea     rcx, [rsp+11C8h+var_1178]
0x18009dd0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dd10  nop
0x18009dd11  lea     rcx, [rsp+11C8h+hObject]
0x18009dd16  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dd1b  mov     eax, ebx
0x18009dd1d  jmp     loc_18009E10C
0x18009dd22  mov     rdx, [rsp+11C8h+var_1160]
0x18009dd27  test    rdx, rdx
0x18009dd2a  jz      loc_18009E0C2
0x18009dd30  lea     rcx, [rsp+11C8h+var_1058]
0x18009dd38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009dd3d  nop
0x18009dd3e  lea     r8, asc_180108014; " "
0x18009dd45  mov     rdx, rax
0x18009dd48  lea     rcx, [rsp+11C8h+var_1078]
0x18009dd50  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009dd55  nop
0x18009dd56  mov     r8, rdi
0x18009dd59  mov     rdx, rax
0x18009dd5c  lea     rcx, [rsp+11C8h+var_1098]
0x18009dd64  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009dd69  nop
0x18009dd6a  lea     rcx, [rsp+11C8h+var_1078]
0x18009dd72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009dd77  nop
0x18009dd78  lea     rcx, [rsp+11C8h+var_1058]
0x18009dd80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009dd85  lea     rcx, [rsp+11C8h+var_1098]
0x18009dd8d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009dd92  mov     rdx, rax; lpCommandLine
0x18009dd95  lea     rax, [rsp+11C8h+ProcessInformation]
0x18009dd9d  mov     [rsp+11C8h+lpProcessInformation], rax; lpProcessInformation
0x18009dda2  lea     rax, [rsp+11C8h+StartupInfo]
0x18009ddaa  mov     [rsp+11C8h+lpStartupInfo], rax; lpStartupInfo
0x18009ddaf  mov     [rsp+11C8h+lpCurrentDirectory], r12; lpCurrentDirectory
0x18009ddb4  mov     [rsp+11C8h+lpEnvironment], r12; lpEnvironment
0x18009ddb9  mov     [rsp+11C8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18009ddc1  mov     [rsp+11C8h+bInheritHandles], r14d; bInheritHandles
0x18009ddc6  xor     r9d, r9d; lpThreadAttributes
0x18009ddc9  xor     r8d, r8d; lpProcessAttributes
0x18009ddcc  xor     ecx, ecx; lpApplicationName
0x18009ddce  call    cs:__imp_CreateProcessW
0x18009ddd4  test    eax, eax
0x18009ddd6  jnz     short loc_18009DE28
0x18009ddd8  mov     rcx, [rsp+11C8h]; this
0x18009dde0  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009dde7  mov     edx, 0BFh; void *
0x18009ddec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009ddf1  mov     ebx, eax
0x18009ddf3  lea     rcx, [rsp+11C8h+var_1098]
0x18009ddfb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009de00  nop
0x18009de01  lea     rcx, [rsp+11C8h+var_1160]
0x18009de06  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009de0b  nop
0x18009de0c  lea     rcx, [rsp+11C8h+var_1178]
0x18009de11  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009de16  nop
0x18009de17  lea     rcx, [rsp+11C8h+hObject]
0x18009de1c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009de21  mov     eax, ebx
0x18009de23  jmp     loc_18009E10C
0x18009de28  mov     rbx, [rsp+11C8h+ProcessInformation.hProcess]
0x18009de30  mov     [rsp+11C8h+var_1148], rbx
0x18009de38  mov     rax, [rsp+11C8h+ProcessInformation.hThread]
0x18009de40  mov     [rsp+11C8h+var_1150], rax
0x18009de45  xor     edx, edx
0x18009de47  lea     rcx, [rsp+11C8h+var_1178]
0x18009de4c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009de51  xor     edx, edx; Val
0x18009de53  mov     r8d, 1000h; Size
0x18009de59  lea     rcx, [rsp+11C8h+Buffer]; void *
0x18009de61  call    memset_0
0x18009de66  mov     [rsp+11C8h+NumberOfBytesRead], r12d
0x18009de6b  mov     qword ptr [rsp+11C8h+bInheritHandles], r12; int
0x18009de70  lea     r9, [rsp+11C8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009de75  mov     r8d, 1000h; nNumberOfBytesToRead
0x18009de7b  lea     rdx, [rsp+11C8h+Buffer]; lpBuffer
0x18009de83  mov     rcx, [rsp+11C8h+hObject]; hFile
0x18009de88  call    cs:__imp_ReadFile
0x18009de8e  test    eax, eax
0x18009de90  jz      short loc_18009DEFE
0x18009de92  mov     eax, [rsp+11C8h+NumberOfBytesRead]
0x18009de96  test    eax, eax
0x18009de98  jz      short loc_18009DEFE
0x18009de9a  mov     r14d, eax
0x18009de9d  mov     rcx, [rsi+10h]
0x18009dea1  mov     rax, [rsi+18h]
0x18009dea5  sub     rax, rcx
0x18009dea8  cmp     r14, rax
0x18009deab  ja      short loc_18009DEE1
0x18009dead  lea     rax, [rcx+r14]
0x18009deb1  mov     [rsi+10h], rax
0x18009deb5  cmp     qword ptr [rsi+18h], 0Fh
0x18009deba  jbe     short loc_18009DEC1
0x18009debc  mov     rax, [rsi]
0x18009debf  jmp     short loc_18009DEC4
0x18009dec1  mov     rax, rsi
0x18009dec4  lea     rdi, [rcx+rax]
0x18009dec8  mov     r8, r14; Size
0x18009decb  lea     rdx, [rsp+11C8h+Buffer]; Src
0x18009ded3  mov     rcx, rdi; void *
0x18009ded6  call    memmove_0
0x18009dedb  mov     [rdi+r14], r12b
0x18009dedf  jmp     short loc_18009DE6B
0x18009dee1  mov     qword ptr [rsp+11C8h+bInheritHandles], r14; Size
0x18009dee6  lea     r9, [rsp+11C8h+Buffer]
0x18009deee  mov     rdx, r14
0x18009def1  mov     rcx, rsi; Src
0x18009def4  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18009def9  jmp     loc_18009DE6B
0x18009defe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009df01  mov     rcx, rbx; hHandle
0x18009df04  call    cs:__imp_WaitForSingleObject
0x18009df0a  test    eax, eax
0x18009df0c  jz      short loc_18009DF77
0x18009df0e  mov     rcx, [rsp+11C8h]; this
0x18009df16  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009df1d  mov     edx, 0D3h; void *
0x18009df22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009df27  mov     ebx, eax
0x18009df29  lea     rcx, [rsp+11C8h+var_1150]
0x18009df2e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009df33  nop
0x18009df34  lea     rcx, [rsp+11C8h+var_1148]
0x18009df3c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009df41  nop
0x18009df42  lea     rcx, [rsp+11C8h+var_1098]
0x18009df4a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009df4f  nop
0x18009df50  lea     rcx, [rsp+11C8h+var_1160]
0x18009df55  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009df5a  nop
0x18009df5b  lea     rcx, [rsp+11C8h+var_1178]
0x18009df60  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009df65  nop
0x18009df66  lea     rcx, [rsp+11C8h+hObject]
0x18009df6b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009df70  mov     eax, ebx
0x18009df72  jmp     loc_18009E10C
0x18009df77  mov     [rsp+11C8h+ExitCode], r12d
0x18009df7c  lea     rdx, [rsp+11C8h+ExitCode]; lpExitCode
0x18009df81  mov     rcx, rbx; hProcess
0x18009df84  call    cs:__imp_GetExitCodeProcess
0x18009df8a  test    eax, eax
0x18009df8c  jnz     short loc_18009DFF7
0x18009df8e  mov     rcx, [rsp+11C8h]; this
0x18009df96  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009df9d  mov     edx, 0D6h; void *
0x18009dfa2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009dfa7  mov     ebx, eax
0x18009dfa9  lea     rcx, [rsp+11C8h+var_1150]
0x18009dfae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dfb3  nop
0x18009dfb4  lea     rcx, [rsp+11C8h+var_1148]
0x18009dfbc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dfc1  nop
0x18009dfc2  lea     rcx, [rsp+11C8h+var_1098]
0x18009dfca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009dfcf  nop
0x18009dfd0  lea     rcx, [rsp+11C8h+var_1160]
0x18009dfd5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009dfda  nop
0x18009dfdb  lea     rcx, [rsp+11C8h+var_1178]
0x18009dfe0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dfe5  nop
0x18009dfe6  lea     rcx, [rsp+11C8h+hObject]
0x18009dfeb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009dff0  mov     eax, ebx
0x18009dff2  jmp     loc_18009E10C
0x18009dff7  mov     eax, [rsp+11C8h+ExitCode]
0x18009dffb  test    r15, r15
0x18009dffe  jz      short loc_18009E003
0x18009e000  mov     [r15], eax
0x18009e003  test    eax, eax
0x18009e005  jz      short loc_18009E077
0x18009e007  mov     rcx, [rsp+11C8h]; this
0x18009e00f  mov     ebx, 80004005h
0x18009e014  mov     r9d, ebx; char *
0x18009e017  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\coresettinghandlers"...
0x18009e01e  mov     edx, 0DDh; void *
0x18009e023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e028  nop
0x18009e029  lea     rcx, [rsp+11C8h+var_1150]
0x18009e02e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009e033  nop
  ... truncated ...
```
