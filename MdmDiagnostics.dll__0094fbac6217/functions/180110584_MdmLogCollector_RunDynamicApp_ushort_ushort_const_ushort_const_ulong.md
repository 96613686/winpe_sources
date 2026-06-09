# MdmLogCollector::RunDynamicApp(ushort *,ushort const *,ushort const *,ulong)

- ea: `0x180110584`
- end: `0x18011073b`
- name: `?RunDynamicApp@MdmLogCollector@@AEAAJPEAGPEBG1K@Z`
- size: `439`
- prototype: `int(MdmLogCollector *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180109400`
- `0x1801095b0`
- `0x18010a4a0`
- `0x18010b4d8`

## callees

- `0x180019fc4`
- `0x1800ece3c`
- `0x1800f9534`
- `0x1801043d4`
- `0x1801089c0`
- `0x180110584`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801105c1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801105cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801105c1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801105cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180110636`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180110636`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801106fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801106fc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1801106cd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1801106cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110710`

## string_xrefs

- `0x1801106e0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
__int64 __fastcall MdmLogCollector::RunDynamicApp(
        MdmLogCollector *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwMilliseconds)
{
  HANDLE v10; // rax
  const char *v11; // r9
  void *v12; // rbx
  __int64 v13; // rdx
  unsigned int LastError; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-61h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-49h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]
  void *v19; // [rsp+110h] [rbp+5Fh] BYREF

  if ( *((_QWORD *)this + 28) != -1 )
    return 1;
  DeleteFileW(a3);
  if ( a4 )
    DeleteFileW(a4);
  MdmLogCollector::AddEntry((__int64)a3, (__int64 *)this + 4);
  if ( a4 )
    MdmLogCollector::AddEntry((__int64)a4, (__int64 *)this + 4);
  *(_OWORD *)&SecurityAttributes.nLength = 0;
  *(&SecurityAttributes.bInheritHandle + 1) = 0;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 1;
  v19 = 0;
  v10 = CreateFileW(a3, 0x40000000u, 3u, &SecurityAttributes, 2u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v19,
    v10);
  v12 = v19;
  if ( v19 == (void *)-1LL )
  {
    v13 = 1221;
  }
  else
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 256;
    StartupInfo.hStdOutput = v12;
    StartupInfo.hStdError = v12;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, a2, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( ProcessInformation.hProcess )
      {
        WaitForSingleObject(ProcessInformation.hProcess, dwMilliseconds);
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
      }
      LastError = 0;
      goto LABEL_15;
    }
    v13 = 1242;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v13,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                v11);
LABEL_15:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  return LastError;
}

```

## disassembly

```asm
0x180110584  mov     [rsp-8+arg_8], rbx
0x180110589  mov     [rsp-8+arg_10], rsi
0x18011058e  push    rbp
0x18011058f  push    rdi
0x180110590  push    r14
0x180110592  lea     rbp, [rsp-3Fh]
0x180110597  sub     rsp, 0F0h
0x18011059e  cmp     qword ptr [rcx+0E0h], 0FFFFFFFFFFFFFFFFh
0x1801105a6  mov     rbx, r9
0x1801105a9  mov     rdi, r8
0x1801105ac  mov     r14, rdx
0x1801105af  mov     rsi, rcx
0x1801105b2  jz      short loc_1801105BE
0x1801105b4  mov     eax, 1
0x1801105b9  jmp     loc_180110723
0x1801105be  mov     rcx, rdi; lpFileName
0x1801105c1  call    cs:__imp_DeleteFileW
0x1801105c7  test    rbx, rbx
0x1801105ca  jz      short loc_1801105D5
0x1801105cc  mov     rcx, rbx; lpFileName
0x1801105cf  call    cs:__imp_DeleteFileW
0x1801105d5  lea     rdx, [rsi+20h]
0x1801105d9  mov     rcx, rdi
0x1801105dc  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x1801105e1  test    rbx, rbx
0x1801105e4  jz      short loc_1801105F2
0x1801105e6  lea     rdx, [rsi+20h]
0x1801105ea  mov     rcx, rbx
0x1801105ed  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x1801105f2  xor     eax, eax
0x1801105f4  lea     r9, [rbp+4Fh+SecurityAttributes]; lpSecurityAttributes
0x1801105f8  mov     [rsp+100h+hTemplateFile], rax; hTemplateFile
0x1801105fd  xorps   xmm0, xmm0
0x180110600  movups  xmmword ptr [rbp+4Fh+SecurityAttributes.nLength], xmm0
0x180110604  mov     qword ptr [rbp+4Fh+SecurityAttributes.bInheritHandle], rax
0x180110608  mov     edx, 40000000h; dwDesiredAccess
0x18011060d  lea     r8d, [rax+3]; dwShareMode
0x180110611  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180110619  mov     rcx, rdi; lpFileName
0x18011061c  mov     [rbp+4Fh+SecurityAttributes.nLength], 18h
0x180110623  mov     [rbp+4Fh+SecurityAttributes.bInheritHandle], 1
0x18011062a  mov     [rbp+4Fh+arg_0], rax
0x18011062e  mov     [rsp+100h+dwCreationDisposition], 2; dwCreationDisposition
0x180110636  call    cs:__imp_CreateFileW
0x18011063c  mov     rdx, rax
0x18011063f  lea     rcx, [rbp+4Fh+arg_0]
0x180110643  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180110648  mov     rbx, [rbp+4Fh+arg_0]
0x18011064c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180110650  jnz     short loc_18011065C
0x180110652  mov     edx, 4C5h
0x180110657  jmp     loc_1801106DC
0x18011065c  mov     edi, 68h ; 'h'
0x180110661  lea     rcx, [rbp+4Fh+StartupInfo]; void *
0x180110665  mov     r8d, edi; Size
0x180110668  xor     edx, edx; Val
0x18011066a  call    memset_0
0x18011066f  xor     eax, eax
0x180110671  mov     [rbp+4Fh+StartupInfo.cb], edi
0x180110674  mov     qword ptr [rbp+4Fh+ProcessInformation.dwProcessId], rax
0x180110678  xorps   xmm0, xmm0
0x18011067b  lea     rax, [rbp+4Fh+ProcessInformation]
0x18011067f  mov     [rbp+4Fh+StartupInfo.dwFlags], 100h
0x180110686  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x18011068b  xor     r9d, r9d; lpThreadAttributes
0x18011068e  lea     rax, [rbp+4Fh+StartupInfo]
0x180110692  mov     [rbp+4Fh+StartupInfo.hStdOutput], rbx
0x180110696  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x18011069b  xor     r8d, r8d; lpProcessAttributes
0x18011069e  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1801106a7  mov     rdx, r14; lpCommandLine
0x1801106aa  mov     [rsp+100h+hTemplateFile], 0; lpEnvironment
0x1801106b3  xor     ecx, ecx; lpApplicationName
0x1801106b5  mov     [rsp+100h+dwFlagsAndAttributes], 8000000h; dwCreationFlags
0x1801106bd  mov     [rsp+100h+dwCreationDisposition], 1; bInheritHandles
0x1801106c5  mov     [rbp+4Fh+StartupInfo.hStdError], rbx
0x1801106c9  movups  xmmword ptr [rbp+4Fh+ProcessInformation.hProcess], xmm0
0x1801106cd  call    cs:__imp_CreateProcessW
0x1801106d3  test    eax, eax
0x1801106d5  jnz     short loc_1801106F0
0x1801106d7  mov     edx, 4DAh; void *
0x1801106dc  mov     rcx, [rbp+57h]; this
0x1801106e0  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801106e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801106ec  mov     ebx, eax
0x1801106ee  jmp     short loc_180110718
0x1801106f0  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]; hHandle
0x1801106f4  test    rcx, rcx
0x1801106f7  jz      short loc_180110716
0x1801106f9  mov     edx, [rbp+4Fh+dwMilliseconds]; dwMilliseconds
0x1801106fc  call    cs:__imp_WaitForSingleObject
0x180110702  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]; hObject
0x180110706  call    cs:__imp_CloseHandle
0x18011070c  mov     rcx, [rbp+4Fh+ProcessInformation.hThread]; hObject
0x180110710  call    cs:__imp_CloseHandle
0x180110716  xor     ebx, ebx
0x180110718  lea     rcx, [rbp+4Fh+arg_0]
0x18011071c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180110721  mov     eax, ebx
0x180110723  lea     r11, [rsp+100h+var_10]
0x18011072b  mov     rbx, [r11+28h]
0x18011072f  mov     rsi, [r11+30h]
0x180110733  mov     rsp, r11
0x180110736  pop     r14
0x180110738  pop     rdi
0x180110739  pop     rbp
0x18011073a  retn
```
