# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(_SHELLEXECUTEINFOW *)

- ea: `0x1800b49c8`
- end: `0x1800b4b18`
- name: `?ExecuteAndWait@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(SHELLEXECUTEINFOW *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800b2e04`

## callees

- `0x180011e84`
- `0x180011ea4`
- `0x1800a8718`
- `0x1800b49c8`
- `0x1800b5be8`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800b4ab0`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800b4ab0`
- `KERNEL32!GetProcessId` at `0x1800b4abf`
- `KERNEL32!GetProcessId` at `0x1800b4abf`
- `KERNEL32!GetExitCodeProcess` at `0x1800b4aea`
- `KERNEL32!GetExitCodeProcess` at `0x1800b4aea`
- `KERNEL32!CreateEventExW` at `0x1800b4a62`
- `KERNEL32!CreateEventExW` at `0x1800b4a62`
- `KERNEL32!CloseHandle` at `0x1800b4afb`
- `KERNEL32!CloseHandle` at `0x1800b4afb`
- `KERNEL32!GetLastError` at `0x1800b49ed`
- `KERNEL32!GetLastError` at `0x1800b49ed`
- `KERNEL32!WaitForSingleObject` at `0x1800b4ad3`
- `KERNEL32!WaitForSingleObject` at `0x1800b4ad3`
- `SHELL32!ShellExecuteExW` at `0x1800b49e3`
- `SHELL32!ShellExecuteExW` at `0x1800b49e3`

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
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
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
0x1800b49c8  mov     [rsp+arg_10], rbx
0x1800b49cd  push    rdi
0x1800b49ce  sub     rsp, 40h
0x1800b49d2  or      dword ptr [rcx+4], 540h
0x1800b49d9  mov     rdi, rcx
0x1800b49dc  mov     dword ptr [rcx+30h], 1
0x1800b49e3  call    cs:__imp_ShellExecuteExW
0x1800b49e9  test    eax, eax
0x1800b49eb  jnz     short loc_1800B4A3D
0x1800b49ed  call    cs:__imp_GetLastError
0x1800b49f3  mov     ebx, eax
0x1800b49f5  test    eax, eax
0x1800b49f7  jle     short loc_1800B4A02
0x1800b49f9  movzx   ebx, ax
0x1800b49fc  or      ebx, 80070000h
0x1800b4a02  test    ebx, ebx
0x1800b4a04  jns     short loc_1800B4A3D
0x1800b4a06  mov     rcx, [rsp+48h]; this
0x1800b4a0b  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800b4a12  mov     r9d, ebx; char *
0x1800b4a15  mov     edx, 22h ; '"'; void *
0x1800b4a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4a1f  mov     rcx, [rsp+48h]; this
0x1800b4a24  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800b4a2b  mov     r9d, ebx; char *
0x1800b4a2e  mov     edx, 2Ch ; ','; void *
0x1800b4a33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4a38  jmp     loc_1800B4B0B
0x1800b4a3d  cmp     qword ptr [rdi+68h], 0
0x1800b4a42  mov     ebx, 8000FFFFh
0x1800b4a47  jz      loc_1800B4B0B
0x1800b4a4d  mov     r9d, 100000h; dwDesiredAccess
0x1800b4a53  lea     rdx, Name; "Local\\SystemSettings_DataModel_CloseAd"...
0x1800b4a5a  mov     r8d, 1; dwFlags
0x1800b4a60  xor     ecx, ecx; lpEventAttributes
0x1800b4a62  call    cs:__imp_CreateEventExW
0x1800b4a68  mov     [rsp+48h+arg_8], rax
0x1800b4a6d  test    rax, rax
0x1800b4a70  jnz     short loc_1800B4A8A
0x1800b4a72  mov     rcx, [rsp+48h]; this
0x1800b4a77  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800b4a7e  lea     edx, [rax+32h]; void *
0x1800b4a81  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b4a86  mov     ebx, eax
0x1800b4a88  jmp     short loc_1800B4B01
0x1800b4a8a  mov     rcx, [rdi+68h]
0x1800b4a8e  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800b4a93  xor     r8d, r8d; bWaitAll
0x1800b4a96  mov     [rsp+48h+Handles], rcx
0x1800b4a9b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800b4a9f  mov     [rsp+48h+var_10], rax
0x1800b4aa4  mov     [rsp+48h+bAlertable], 0; bAlertable
0x1800b4aac  lea     ecx, [r8+2]; nCount
0x1800b4ab0  call    cs:__imp_WaitForMultipleObjectsEx
0x1800b4ab6  cmp     eax, 1
0x1800b4ab9  jnz     short loc_1800B4AD9
0x1800b4abb  mov     rcx, [rdi+68h]; Process
0x1800b4abf  call    cs:__imp_GetProcessId
0x1800b4ac5  mov     ecx, eax
0x1800b4ac7  call    ?GracefullyTerminateProcess@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAJK@Z; SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::GracefullyTerminateProcess(ulong)
0x1800b4acc  mov     rcx, [rdi+68h]; hHandle
0x1800b4ad0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b4ad3  call    cs:__imp_WaitForSingleObject
0x1800b4ad9  mov     rcx, [rdi+68h]; hProcess
0x1800b4add  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1800b4ae2  mov     [rsp+48h+ExitCode], 0
0x1800b4aea  call    cs:__imp_GetExitCodeProcess
0x1800b4af0  mov     rcx, [rdi+68h]; hObject
0x1800b4af4  test    eax, eax
0x1800b4af6  cmovnz  ebx, [rsp+48h+ExitCode]
0x1800b4afb  call    cs:__imp_CloseHandle
0x1800b4b01  lea     rcx, [rsp+48h+arg_8]
0x1800b4b06  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4b0b  mov     eax, ebx
0x1800b4b0d  mov     rbx, [rsp+48h+arg_10]
0x1800b4b12  add     rsp, 40h
0x1800b4b16  pop     rdi
0x1800b4b17  retn
```
