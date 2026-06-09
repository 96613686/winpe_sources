# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(_SHELLEXECUTEINFOW *)

- ea: `0x180034f98`
- end: `0x1800350e8`
- name: `?ExecuteAndWait@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(SHELLEXECUTEINFOW *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180032188`

## callees

- `0x18000eaac`
- `0x18000eacc`
- `0x18001a3c4`
- `0x180034f98`
- `0x18003633c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180035032`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180035032`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180035080`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180035080`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800350a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800350a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003508f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003508f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800350ba`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800350ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800350cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800350cb`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x180034fb3`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x180034fb3`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(
        SHELLEXECUTEINFOW *a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  HANDLE Event; // rax
  const char *v5; // r9
  DWORD ProcessId; // eax
  HANDLE hProcess; // rcx
  BOOL bAlertable; // [rsp+20h] [rbp-28h]
  BOOL bAlertablea; // [rsp+20h] [rbp-28h]
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v14; // [rsp+58h] [rbp+10h] BYREF

  a1->fMask |= 0x540u;
  a1->nShow = 1;
  if ( ShellExecuteExW(a1) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_6:
    v3 = -2147418113;
    if ( a1->hProcess )
    {
      Event = CreateEventExW(0, L"Local\\SystemSettings_DataModel_CloseAdminFlow", 1u, 0x100000u);
      v14 = Event;
      if ( Event )
      {
        Handles[0] = a1->hProcess;
        Handles[1] = Event;
        if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) == 1 )
        {
          ProcessId = GetProcessId(a1->hProcess);
          SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ProcessId);
          WaitForSingleObject(a1->hProcess, 0xFFFFFFFF);
        }
        hProcess = a1->hProcess;
        ExitCode = 0;
        if ( GetExitCodeProcess(hProcess, &ExitCode) )
          v3 = ExitCode;
        CloseHandle(a1->hProcess);
      }
      else
      {
        v3 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x32,
               (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingExternalFlowUtilities.h",
               v5);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)v3,
      bAlertable);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)v3,
      bAlertablea);
  }
  return v3;
}

```

## disassembly

```asm
0x180034f98  mov     [rsp+arg_10], rbx
0x180034f9d  push    rdi
0x180034f9e  sub     rsp, 40h
0x180034fa2  or      dword ptr [rcx+4], 540h
0x180034fa9  mov     rdi, rcx
0x180034fac  mov     dword ptr [rcx+30h], 1
0x180034fb3  call    cs:__imp_ShellExecuteExW
0x180034fb9  test    eax, eax
0x180034fbb  jnz     short loc_18003500D
0x180034fbd  call    cs:__imp_GetLastError
0x180034fc3  mov     ebx, eax
0x180034fc5  test    eax, eax
0x180034fc7  jle     short loc_180034FD2
0x180034fc9  movzx   ebx, ax
0x180034fcc  or      ebx, 80070000h
0x180034fd2  test    ebx, ebx
0x180034fd4  jns     short loc_18003500D
0x180034fd6  mov     rcx, [rsp+48h]; this
0x180034fdb  lea     r8, aOnecoreuapInte_2; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x180034fe2  mov     r9d, ebx; char *
0x180034fe5  mov     edx, 22h ; '"'; void *
0x180034fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034fef  mov     rcx, [rsp+48h]; this
0x180034ff4  lea     r8, aOnecoreuapInte_2; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x180034ffb  mov     r9d, ebx; char *
0x180034ffe  mov     edx, 2Ch ; ','; void *
0x180035003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035008  jmp     loc_1800350DB
0x18003500d  cmp     qword ptr [rdi+68h], 0
0x180035012  mov     ebx, 8000FFFFh
0x180035017  jz      loc_1800350DB
0x18003501d  mov     r9d, 100000h; dwDesiredAccess
0x180035023  lea     rdx, Name; "Local\\SystemSettings_DataModel_CloseAd"...
0x18003502a  mov     r8d, 1; dwFlags
0x180035030  xor     ecx, ecx; lpEventAttributes
0x180035032  call    cs:__imp_CreateEventExW
0x180035038  mov     [rsp+48h+arg_8], rax
0x18003503d  test    rax, rax
0x180035040  jnz     short loc_18003505A
0x180035042  mov     rcx, [rsp+48h]; this
0x180035047  lea     r8, aOnecoreuapInte_2; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18003504e  lea     edx, [rax+32h]; void *
0x180035051  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035056  mov     ebx, eax
0x180035058  jmp     short loc_1800350D1
0x18003505a  mov     rcx, [rdi+68h]
0x18003505e  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180035063  xor     r8d, r8d; bWaitAll
0x180035066  mov     [rsp+48h+Handles], rcx
0x18003506b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18003506f  mov     [rsp+48h+var_10], rax
0x180035074  mov     [rsp+48h+bAlertable], 0; bAlertable
0x18003507c  lea     ecx, [r8+2]; nCount
0x180035080  call    cs:__imp_WaitForMultipleObjectsEx
0x180035086  cmp     eax, 1
0x180035089  jnz     short loc_1800350A9
0x18003508b  mov     rcx, [rdi+68h]; Process
0x18003508f  call    cs:__imp_GetProcessId
0x180035095  mov     ecx, eax
0x180035097  call    ?GracefullyTerminateProcess@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAJK@Z; SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ulong)
0x18003509c  mov     rcx, [rdi+68h]; hHandle
0x1800350a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800350a3  call    cs:__imp_WaitForSingleObject
0x1800350a9  mov     rcx, [rdi+68h]; hProcess
0x1800350ad  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1800350b2  mov     [rsp+48h+ExitCode], 0
0x1800350ba  call    cs:__imp_GetExitCodeProcess
0x1800350c0  mov     rcx, [rdi+68h]; hObject
0x1800350c4  test    eax, eax
0x1800350c6  cmovnz  ebx, [rsp+48h+ExitCode]
0x1800350cb  call    cs:__imp_CloseHandle
0x1800350d1  lea     rcx, [rsp+48h+arg_8]
0x1800350d6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800350db  mov     eax, ebx
0x1800350dd  mov     rbx, [rsp+48h+arg_10]
0x1800350e2  add     rsp, 40h
0x1800350e6  pop     rdi
0x1800350e7  retn
```
