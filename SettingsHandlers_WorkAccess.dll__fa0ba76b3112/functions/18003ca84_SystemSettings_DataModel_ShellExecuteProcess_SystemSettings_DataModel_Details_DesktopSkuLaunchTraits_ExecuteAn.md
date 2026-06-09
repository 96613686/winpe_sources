# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(_SHELLEXECUTEINFOW *)

- ea: `0x18003ca84`
- end: `0x18003cc08`
- name: `?ExecuteAndWait@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18003aca8`

## callees

- `0x1800096cc`
- `0x1800096ec`
- `0x18002eccc`
- `0x18003ca84`
- `0x18003ebdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003cb2a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003cb2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003cbb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003cbb0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18003cb81`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18003cb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003caaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003caaf`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003cbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003cbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003cb96`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003cb96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cbe4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cbe4`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18003ca9f`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18003ca9f`

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
               (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingExternalFlowUtilities.h",
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
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)v3,
      bAlertable);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingExternalFlowUtilities.h",
      (const char *)v3,
      bAlertablea);
  }
  return v3;
}

```

## disassembly

```asm
0x18003ca84  mov     [rsp+arg_10], rbx
0x18003ca89  push    rdi
0x18003ca8a  sub     rsp, 40h
0x18003ca8e  or      dword ptr [rcx+4], 540h
0x18003ca95  mov     rdi, rcx
0x18003ca98  mov     dword ptr [rcx+30h], 1
0x18003ca9f  call    cs:__imp_ShellExecuteExW
0x18003caa6  nop     dword ptr [rax+rax+00h]
0x18003caab  test    eax, eax
0x18003caad  jnz     short loc_18003CB05
0x18003caaf  call    cs:__imp_GetLastError
0x18003cab6  nop     dword ptr [rax+rax+00h]
0x18003cabb  mov     ebx, eax
0x18003cabd  test    eax, eax
0x18003cabf  jle     short loc_18003CACA
0x18003cac1  movzx   ebx, ax
0x18003cac4  or      ebx, 80070000h
0x18003caca  test    ebx, ebx
0x18003cacc  jns     short loc_18003CB05
0x18003cace  mov     rcx, [rsp+48h]; this
0x18003cad3  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003cada  mov     r9d, ebx; char *
0x18003cadd  mov     edx, 22h ; '"'; void *
0x18003cae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cae7  mov     rcx, [rsp+48h]; this
0x18003caec  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003caf3  mov     r9d, ebx; char *
0x18003caf6  mov     edx, 2Ch ; ','; void *
0x18003cafb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb00  jmp     loc_18003CBFA
0x18003cb05  cmp     qword ptr [rdi+68h], 0
0x18003cb0a  mov     ebx, 8000FFFFh
0x18003cb0f  jz      loc_18003CBFA
0x18003cb15  mov     r9d, 100000h; dwDesiredAccess
0x18003cb1b  lea     rdx, Name; "Local\\SystemSettings_DataModel_CloseAd"...
0x18003cb22  mov     r8d, 1; dwFlags
0x18003cb28  xor     ecx, ecx; lpEventAttributes
0x18003cb2a  call    cs:__imp_CreateEventExW
0x18003cb31  nop     dword ptr [rax+rax+00h]
0x18003cb36  mov     [rsp+48h+arg_8], rax
0x18003cb3b  test    rax, rax
0x18003cb3e  jnz     short loc_18003CB5B
0x18003cb40  mov     rcx, [rsp+48h]; this
0x18003cb45  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003cb4c  lea     edx, [rax+32h]; void *
0x18003cb4f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003cb54  mov     ebx, eax
0x18003cb56  jmp     loc_18003CBF0
0x18003cb5b  mov     rcx, [rdi+68h]
0x18003cb5f  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18003cb64  xor     r8d, r8d; bWaitAll
0x18003cb67  mov     [rsp+48h+Handles], rcx
0x18003cb6c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18003cb70  mov     [rsp+48h+var_10], rax
0x18003cb75  mov     [rsp+48h+bAlertable], 0; bAlertable
0x18003cb7d  lea     ecx, [r8+2]; nCount
0x18003cb81  call    cs:__imp_WaitForMultipleObjectsEx
0x18003cb88  nop     dword ptr [rax+rax+00h]
0x18003cb8d  cmp     eax, 1
0x18003cb90  jnz     short loc_18003CBBC
0x18003cb92  mov     rcx, [rdi+68h]; Process
0x18003cb96  call    cs:__imp_GetProcessId
0x18003cb9d  nop     dword ptr [rax+rax+00h]
0x18003cba2  mov     ecx, eax
0x18003cba4  call    ?GracefullyTerminateProcess@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAJK@Z; SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ulong)
0x18003cba9  mov     rcx, [rdi+68h]; hHandle
0x18003cbad  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003cbb0  call    cs:__imp_WaitForSingleObject
0x18003cbb7  nop     dword ptr [rax+rax+00h]
0x18003cbbc  mov     rcx, [rdi+68h]; hProcess
0x18003cbc0  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x18003cbc5  mov     [rsp+48h+ExitCode], 0
0x18003cbcd  call    cs:__imp_GetExitCodeProcess
0x18003cbd4  nop     dword ptr [rax+rax+00h]
0x18003cbd9  mov     rcx, [rdi+68h]; hObject
0x18003cbdd  test    eax, eax
0x18003cbdf  cmovnz  ebx, [rsp+48h+ExitCode]
0x18003cbe4  call    cs:__imp_CloseHandle
0x18003cbeb  nop     dword ptr [rax+rax+00h]
0x18003cbf0  lea     rcx, [rsp+48h+arg_8]
0x18003cbf5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cbfa  mov     eax, ebx
0x18003cbfc  mov     rbx, [rsp+48h+arg_10]
0x18003cc01  add     rsp, 40h
0x18003cc05  pop     rdi
0x18003cc06  retn
```
