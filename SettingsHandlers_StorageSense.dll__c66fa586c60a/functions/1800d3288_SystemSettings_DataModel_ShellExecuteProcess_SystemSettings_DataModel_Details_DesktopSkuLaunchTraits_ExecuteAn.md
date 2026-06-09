# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(_SHELLEXECUTEINFOW *)

- ea: `0x1800d3288`
- end: `0x1800d33cf`
- name: `?ExecuteAndWait@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800d11ac`

## callees

- `0x18000e6ac`
- `0x18000e6cc`
- `0x180029264`
- `0x1800d3288`
- `0x1800d48e0`
- `0x1800d6c7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800d3367`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800d3367`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d338a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d338a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800d330a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800d330a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d3376`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d3376`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800d33a1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800d33a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d33b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d33b2`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(
        struct _SHELLEXECUTEINFOW *a1)
{
  int v2; // eax
  DWORD v3; // edi
  HANDLE Event; // rax
  const char *v5; // r9
  unsigned int LastError; // ebx
  DWORD ProcessId; // eax
  HANDLE hProcess; // rcx
  BOOL bAlertable; // [rsp+20h] [rbp-28h]
  BOOL bAlertablea; // [rsp+20h] [rbp-28h]
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v15; // [rsp+58h] [rbp+10h] BYREF

  a1->fMask |= 0x540u;
  a1->nShow = 1;
  v2 = SystemSettings::DataModel::Details::DesktopSkuLaunchTraits::ShellExecuteExe(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = -2147418113;
    if ( a1->hProcess )
    {
      Event = CreateEventExW(0, L"Local\\SystemSettings_DataModel_CloseAdminFlow", 1u, 0x100000u);
      v15 = Event;
      if ( !Event )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x32,
                      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingExternalFlowUtilities.h",
                      v5);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
        return LastError;
      }
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
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)(unsigned int)v2,
      bAlertable);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)v3,
      bAlertablea);
  }
  return v3;
}

```

## disassembly

```asm
0x1800d3288  mov     [rsp+arg_10], rbx
0x1800d328d  push    rdi
0x1800d328e  sub     rsp, 40h
0x1800d3292  or      dword ptr [rcx+4], 540h
0x1800d3299  mov     rbx, rcx
0x1800d329c  mov     dword ptr [rcx+30h], 1
0x1800d32a3  call    ?ShellExecuteExe@DesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z; SystemSettings::DataModel::Details::DesktopSkuLaunchTraits::ShellExecuteExe(_SHELLEXECUTEINFOW *)
0x1800d32a8  mov     edi, eax
0x1800d32aa  test    eax, eax
0x1800d32ac  jns     short loc_1800D32E5
0x1800d32ae  mov     rcx, [rsp+48h]; this
0x1800d32b3  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x1800d32ba  mov     r9d, eax; char *
0x1800d32bd  mov     edx, 22h ; '"'; void *
0x1800d32c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d32c7  mov     rcx, [rsp+48h]; this
0x1800d32cc  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x1800d32d3  mov     r9d, edi; char *
0x1800d32d6  mov     edx, 2Ch ; ','; void *
0x1800d32db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d32e0  jmp     loc_1800D33C2
0x1800d32e5  cmp     qword ptr [rbx+68h], 0
0x1800d32ea  mov     edi, 8000FFFFh
0x1800d32ef  jz      loc_1800D33C2
0x1800d32f5  mov     r9d, 100000h; dwDesiredAccess
0x1800d32fb  lea     rdx, Name; "Local\\SystemSettings_DataModel_CloseAd"...
0x1800d3302  mov     r8d, 1; dwFlags
0x1800d3308  xor     ecx, ecx; lpEventAttributes
0x1800d330a  call    cs:__imp_CreateEventExW
0x1800d3310  mov     [rsp+48h+arg_8], rax
0x1800d3315  test    rax, rax
0x1800d3318  jnz     short loc_1800D3341
0x1800d331a  mov     rcx, [rsp+48h]; this
0x1800d331f  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x1800d3326  lea     edx, [rax+32h]; void *
0x1800d3329  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d332e  lea     rcx, [rsp+48h+arg_8]
0x1800d3333  mov     ebx, eax
0x1800d3335  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d333a  mov     eax, ebx
0x1800d333c  jmp     loc_1800D33C4
0x1800d3341  mov     rcx, [rbx+68h]
0x1800d3345  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800d334a  xor     r8d, r8d; bWaitAll
0x1800d334d  mov     [rsp+48h+Handles], rcx
0x1800d3352  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800d3356  mov     [rsp+48h+var_10], rax
0x1800d335b  mov     [rsp+48h+bAlertable], 0; bAlertable
0x1800d3363  lea     ecx, [r8+2]; nCount
0x1800d3367  call    cs:__imp_WaitForMultipleObjectsEx
0x1800d336d  cmp     eax, 1
0x1800d3370  jnz     short loc_1800D3390
0x1800d3372  mov     rcx, [rbx+68h]; Process
0x1800d3376  call    cs:__imp_GetProcessId
0x1800d337c  mov     ecx, eax
0x1800d337e  call    ?GracefullyTerminateProcess@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAJK@Z; SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ulong)
0x1800d3383  mov     rcx, [rbx+68h]; hHandle
0x1800d3387  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800d338a  call    cs:__imp_WaitForSingleObject
0x1800d3390  mov     rcx, [rbx+68h]; hProcess
0x1800d3394  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1800d3399  mov     [rsp+48h+ExitCode], 0
0x1800d33a1  call    cs:__imp_GetExitCodeProcess
0x1800d33a7  mov     rcx, [rbx+68h]; hObject
0x1800d33ab  test    eax, eax
0x1800d33ad  cmovnz  edi, [rsp+48h+ExitCode]
0x1800d33b2  call    cs:__imp_CloseHandle
0x1800d33b8  lea     rcx, [rsp+48h+arg_8]
0x1800d33bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d33c2  mov     eax, edi
0x1800d33c4  mov     rbx, [rsp+48h+arg_10]
0x1800d33c9  add     rsp, 40h
0x1800d33cd  pop     rdi
0x1800d33ce  retn
```
