# Windows::Compat::Inventory::InventoryWatchdog::Initialize(void)

- ea: `0x18002c490`
- end: `0x18002c6f4`
- name: `?Initialize@InventoryWatchdog@Inventory@Compat@Windows@@QEAAJXZ`
- size: `612`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c6fc`

## callees

- `0x180010fd4`
- `0x180010ffc`
- `0x18001a2f4`
- `0x18002c490`
- `0x18002f458`
- `0x1800307d0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18002c5ca`
- `KERNEL32!CreateThread` at `0x18002c5ca`
- `KERNEL32!CloseHandle` at `0x18002c5ef`
- `KERNEL32!CloseHandle` at `0x18002c5ef`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002c4b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002c4b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c6e3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002c6e3`
- `KERNEL32!GetLastError` at `0x18002c5e4`
- `KERNEL32!GetLastError` at `0x18002c610`
- `KERNEL32!GetLastError` at `0x18002c671`
- `KERNEL32!GetLastError` at `0x18002c698`
- `KERNEL32!GetLastError` at `0x18002c5e4`
- `KERNEL32!GetLastError` at `0x18002c610`
- `KERNEL32!GetLastError` at `0x18002c671`
- `KERNEL32!GetLastError` at `0x18002c698`
- `KERNEL32!WaitForSingleObject` at `0x18002c4ce`
- `KERNEL32!WaitForSingleObject` at `0x18002c660`
- `KERNEL32!WaitForSingleObject` at `0x18002c4ce`
- `KERNEL32!WaitForSingleObject` at `0x18002c660`
- `KERNEL32!SetLastError` at `0x18002c5f7`
- `KERNEL32!SetLastError` at `0x18002c5f7`

## string_xrefs

- `0x18002c4f5`: `CreateEvent failed [%#x]`
- `0x18002c52f`: `CreateEvent failed [%#x]`
- `0x18002c569`: `CreateEvent failed [%#x]`
- `0x18002c593`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x18002c63c`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x18002c61a`: `CreateThread failed [%d]`
- `0x18002c502`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18002c53c`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18002c576`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18002c627`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18002c688`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18002c6b3`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::Initialize(
        Windows::Compat::Inventory::InventoryWatchdog *this)
{
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  DWORD v2; // ebx
  __int64 v3; // rdx
  int v4; // eax
  int v5; // eax
  HANDLE Thread; // rdi
  HANDLE v7; // rsi
  DWORD LastError; // ebx
  DWORD v9; // eax
  const char *v10; // r9
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  AcquireSRWLockExclusive(&stru_1802CA9C8);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && WaitForSingleObject(hObject, 0) == 258 )
    goto LABEL_20;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&hEvent);
  v2 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      78,
      "CreateEvent failed [%#x]",
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    v3 = 79;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
      (const char *)v2,
      dwCreationFlags);
    goto LABEL_21;
  }
  v4 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&unk_1802CA9E0);
  v2 = v4;
  if ( v4 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 85, "CreateEvent failed [%#x]", v4);
    v3 = 86;
    goto LABEL_9;
  }
  v5 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&qword_1802CA9E8);
  v2 = v5;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 92, "CreateEvent failed [%#x]", v5);
    v3 = 93;
    goto LABEL_9;
  }
  Thread = CreateThread(
             0,
             1u,
             Windows::Compat::Inventory::InventoryWatchdog::ThreadProc,
             &Windows::Compat::Appraiser::WicaEngine::WatchDogTimer,
             0,
             0);
  v7 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v7);
    SetLastError(LastError);
  }
  hObject = Thread;
  if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v9 = GetLastError();
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 99, "CreateThread failed [%d]", v9);
    v2 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x64,
           (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
           v10);
    goto LABEL_21;
  }
  v11 = WaitForSingleObject(qword_1802CA9E8, 0x2710u);
  v2 = v11;
  if ( !v11 )
  {
LABEL_20:
    v2 = 0;
    goto LABEL_21;
  }
  if ( v11 == -1 )
  {
    v12 = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      108,
      "WaitForSingleObject failed [%d]",
      v12);
    v2 = GetLastError();
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      113,
      "WaitForSingleObject returned [%d]",
      v11);
  }
  Windows::Compat::Inventory::InventoryWatchdog::Stop((Windows::Compat::Inventory::InventoryWatchdog *)&Windows::Compat::Appraiser::WicaEngine::WatchDogTimer);
  if ( (int)v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
LABEL_21:
  ReleaseSRWLockExclusive(&stru_1802CA9C8);
  return v2;
}

```

## disassembly

```asm
0x18002c490  mov     [rsp+arg_0], rcx
0x18002c495  push    rbx
0x18002c496  push    rbp
0x18002c497  push    rsi
0x18002c498  push    rdi
0x18002c499  sub     rsp, 48h
0x18002c49d  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18002c4a6  lea     rbp, stru_1802CA9C8
0x18002c4ad  mov     rcx, rbp; SRWLock
0x18002c4b0  call    cs:__imp_AcquireSRWLockExclusive
0x18002c4b6  mov     [rsp+68h+arg_0], rbp
0x18002c4bb  mov     rcx, cs:hObject; hHandle
0x18002c4c2  lea     rax, [rcx-1]
0x18002c4c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c4ca  ja      short loc_18002C4DF
0x18002c4cc  xor     edx, edx; dwMilliseconds
0x18002c4ce  call    cs:__imp_WaitForSingleObject
0x18002c4d4  cmp     eax, 102h
0x18002c4d9  jz      loc_18002C6DE
0x18002c4df  lea     rcx, hEvent
0x18002c4e6  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002c4eb  mov     ebx, eax
0x18002c4ed  test    eax, eax
0x18002c4ef  jns     short loc_18002C519
0x18002c4f1  mov     [rsp+68h+dwCreationFlags], eax
0x18002c4f5  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18002c4fc  mov     r8d, 4Eh ; 'N'
0x18002c502  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18002c509  lea     ecx, [r8-4Dh]
0x18002c50d  call    AslLogCallPrintf
0x18002c512  mov     edx, 4Fh ; 'O'
0x18002c517  jmp     short loc_18002C58B
0x18002c519  lea     rcx, unk_1802CA9E0
0x18002c520  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002c525  mov     ebx, eax
0x18002c527  test    eax, eax
0x18002c529  jns     short loc_18002C553
0x18002c52b  mov     [rsp+68h+dwCreationFlags], eax
0x18002c52f  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18002c536  mov     r8d, 55h ; 'U'
0x18002c53c  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18002c543  lea     ecx, [r8-54h]
0x18002c547  call    AslLogCallPrintf
0x18002c54c  mov     edx, 56h ; 'V'
0x18002c551  jmp     short loc_18002C58B
0x18002c553  lea     rcx, qword_1802CA9E8
0x18002c55a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002c55f  mov     ebx, eax
0x18002c561  test    eax, eax
0x18002c563  jns     short loc_18002C5A4
0x18002c565  mov     [rsp+68h+dwCreationFlags], eax; int
0x18002c569  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18002c570  mov     r8d, 5Ch ; '\'
0x18002c576  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18002c57d  lea     ecx, [r8-5Bh]
0x18002c581  call    AslLogCallPrintf
0x18002c586  mov     edx, 5Dh ; ']'; void *
0x18002c58b  mov     rcx, [rsp+68h]; this
0x18002c590  mov     r9d, ebx; char *
0x18002c593  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18002c59a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c59f  jmp     loc_18002C6E0
0x18002c5a4  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18002c5ad  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18002c5b5  lea     r9, ?WatchDogTimer@WicaEngine@Appraiser@Compat@Windows@@0VInventoryWatchdog@Inventory@34@A; lpParameter
0x18002c5bc  lea     r8, ?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x18002c5c3  mov     edx, 1; dwStackSize
0x18002c5c8  xor     ecx, ecx; lpThreadAttributes
0x18002c5ca  call    cs:__imp_CreateThread
0x18002c5d0  mov     rdi, rax
0x18002c5d3  mov     rsi, cs:hObject
0x18002c5da  lea     rdx, [rsi-1]
0x18002c5de  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002c5e2  ja      short loc_18002C5FD
0x18002c5e4  call    cs:__imp_GetLastError
0x18002c5ea  mov     ebx, eax
0x18002c5ec  mov     rcx, rsi; hObject
0x18002c5ef  call    cs:__imp_CloseHandle
0x18002c5f5  mov     ecx, ebx; dwErrCode
0x18002c5f7  call    cs:__imp_SetLastError
0x18002c5fd  mov     cs:hObject, rdi
0x18002c604  lea     rax, [rdi+1]
0x18002c608  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002c60e  jnz     short loc_18002C654
0x18002c610  call    cs:__imp_GetLastError
0x18002c616  mov     [rsp+68h+dwCreationFlags], eax
0x18002c61a  lea     r9, aCreatethreadFa_0; "CreateThread failed [%d]"
0x18002c621  mov     r8d, 63h ; 'c'
0x18002c627  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18002c62e  lea     ecx, [r8-62h]
0x18002c632  call    AslLogCallPrintf
0x18002c637  mov     rcx, [rsp+68h]; this
0x18002c63c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18002c643  mov     edx, 64h ; 'd'; void *
0x18002c648  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c64d  mov     ebx, eax
0x18002c64f  jmp     loc_18002C6E0
0x18002c654  mov     edx, 2710h; dwMilliseconds
0x18002c659  mov     rcx, cs:qword_1802CA9E8; hHandle
0x18002c660  call    cs:__imp_WaitForSingleObject
0x18002c666  mov     ebx, eax
0x18002c668  test    eax, eax
0x18002c66a  jz      short loc_18002C6DE
0x18002c66c  cmp     eax, 0FFFFFFFFh
0x18002c66f  jnz     short loc_18002C6A2
0x18002c671  call    cs:__imp_GetLastError
0x18002c677  mov     [rsp+68h+dwCreationFlags], eax
0x18002c67b  lea     r9, aWaitforsingleo_1; "WaitForSingleObject failed [%d]"
0x18002c682  mov     r8d, 6Ch ; 'l'
0x18002c688  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18002c68f  lea     ecx, [r8-6Bh]
0x18002c693  call    AslLogCallPrintf
0x18002c698  call    cs:__imp_GetLastError
0x18002c69e  mov     ebx, eax
0x18002c6a0  jmp     short loc_18002C6C3
0x18002c6a2  mov     [rsp+68h+dwCreationFlags], eax
0x18002c6a6  lea     r9, aWaitforsingleo_2; "WaitForSingleObject returned [%d]"
0x18002c6ad  mov     r8d, 71h ; 'q'
0x18002c6b3  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18002c6ba  lea     ecx, [r8-70h]
0x18002c6be  call    AslLogCallPrintf
0x18002c6c3  lea     rcx, ?WatchDogTimer@WicaEngine@Appraiser@Compat@Windows@@0VInventoryWatchdog@Inventory@34@A; this
0x18002c6ca  call    ?Stop@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::Stop(void)
0x18002c6cf  test    ebx, ebx
0x18002c6d1  jle     short loc_18002C6E0
0x18002c6d3  movzx   ebx, bx
0x18002c6d6  or      ebx, 80070000h
0x18002c6dc  jmp     short loc_18002C6E0
0x18002c6de  xor     ebx, ebx
0x18002c6e0  mov     rcx, rbp; SRWLock
0x18002c6e3  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c6e9  mov     eax, ebx
0x18002c6eb  add     rsp, 48h
0x18002c6ef  pop     rdi
0x18002c6f0  pop     rsi
0x18002c6f1  pop     rbp
0x18002c6f2  pop     rbx
0x18002c6f3  retn
```
