# Windows::Compat::Inventory::InventoryWatchdog::Initialize(void)

- ea: `0x1800cdb78`
- end: `0x1800cdd90`
- name: `?Initialize@InventoryWatchdog@Inventory@Compat@Windows@@QEAAJXZ`
- size: `536`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cdd98`

## callees

- `0x180008570`
- `0x18000c35c`
- `0x18000c37c`
- `0x1800295dc`
- `0x1800c99cc`
- `0x1800cdb78`
- `0x1800cdf04`
- `0x1800ce8f4`
- `0x1800cfd8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cdcf8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cdcf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cdb91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cdb91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdcab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdd30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdcab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cdd30`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cdc8a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cdc8a`

## string_xrefs

- `0x1800cdbbf`: `CreateEvent failed [%#x]`
- `0x1800cdbf6`: `CreateEvent failed [%#x]`
- `0x1800cdc2d`: `CreateEvent failed [%#x]`
- `0x1800cdc57`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x1800cdcd7`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x1800cdcb5`: `CreateThread failed [%d]`
- `0x1800cdbcc`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800cdc03`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800cdc3a`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800cdcc2`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800cdd20`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800cdd4b`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::Initialize(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  DWORD v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // eax
  HANDLE Thread; // rax
  DWORD LastError; // eax
  const char *v10; // r9
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp+8h] BYREF

  v2 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  v16 = v2;
  if ( Windows::Compat::Inventory::InventoryWatchdog::IsRunning((Windows::Compat::Inventory::InventoryWatchdog *)this) )
    goto LABEL_17;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[5]);
  v4 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      78,
      "CreateEvent failed [%#x]",
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
    v5 = 79;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
      (const char *)v4,
      dwCreationFlags);
    goto LABEL_18;
  }
  v6 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[6]);
  v4 = v6;
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 85, "CreateEvent failed [%#x]", v6);
    v5 = 86;
    goto LABEL_8;
  }
  v7 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[7]);
  v4 = v7;
  if ( v7 < 0 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::InventoryWatchdog::Initialize", 92, "CreateEvent failed [%#x]", v7);
    v5 = 93;
    goto LABEL_8;
  }
  Thread = CreateThread(0, 1u, Windows::Compat::Inventory::InventoryWatchdog::ThreadProc, this, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &this[4],
    Thread);
  if ( (((unsigned __int64)this[4].Ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      99,
      "CreateThread failed [%d]",
      LastError);
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x64,
           (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
           v10);
    goto LABEL_18;
  }
  v11 = WaitForSingleObject(this[7].Ptr, 0x2710u);
  v4 = v11;
  if ( !v11 )
  {
LABEL_17:
    v4 = 0;
    goto LABEL_18;
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
    v4 = GetLastError();
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
  Windows::Compat::Inventory::InventoryWatchdog::Stop((Windows::Compat::Inventory::InventoryWatchdog *)this);
  if ( (int)v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  return v4;
}

```

## disassembly

```asm
0x1800cdb78  mov     [rsp+arg_8], rbx
0x1800cdb7d  mov     [rsp+arg_10], rsi
0x1800cdb82  push    rdi
0x1800cdb83  sub     rsp, 30h
0x1800cdb87  mov     rdi, rcx
0x1800cdb8a  lea     rbx, [rcx+18h]
0x1800cdb8e  mov     rcx, rbx; SRWLock
0x1800cdb91  call    cs:__imp_AcquireSRWLockExclusive
0x1800cdb97  mov     [rsp+38h+arg_0], rbx
0x1800cdb9c  mov     rcx, rdi; this
0x1800cdb9f  call    ?IsRunning@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::IsRunning(void)
0x1800cdba4  test    al, al
0x1800cdba6  jnz     loc_1800CDD72
0x1800cdbac  lea     rcx, [rdi+28h]
0x1800cdbb0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800cdbb5  mov     ebx, eax
0x1800cdbb7  test    eax, eax
0x1800cdbb9  jns     short loc_1800CDBE3
0x1800cdbbb  mov     [rsp+38h+dwCreationFlags], eax
0x1800cdbbf  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x1800cdbc6  mov     r8d, 4Eh ; 'N'
0x1800cdbcc  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800cdbd3  lea     ecx, [r8-4Dh]
0x1800cdbd7  call    AslLogCallPrintf
0x1800cdbdc  mov     edx, 4Fh ; 'O'
0x1800cdbe1  jmp     short loc_1800CDC4F
0x1800cdbe3  lea     rcx, [rdi+30h]
0x1800cdbe7  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800cdbec  mov     ebx, eax
0x1800cdbee  test    eax, eax
0x1800cdbf0  jns     short loc_1800CDC1A
0x1800cdbf2  mov     [rsp+38h+dwCreationFlags], eax
0x1800cdbf6  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x1800cdbfd  mov     r8d, 55h ; 'U'
0x1800cdc03  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800cdc0a  lea     ecx, [r8-54h]
0x1800cdc0e  call    AslLogCallPrintf
0x1800cdc13  mov     edx, 56h ; 'V'
0x1800cdc18  jmp     short loc_1800CDC4F
0x1800cdc1a  lea     rcx, [rdi+38h]
0x1800cdc1e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800cdc23  mov     ebx, eax
0x1800cdc25  test    eax, eax
0x1800cdc27  jns     short loc_1800CDC68
0x1800cdc29  mov     [rsp+38h+dwCreationFlags], eax; int
0x1800cdc2d  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x1800cdc34  mov     r8d, 5Ch ; '\'
0x1800cdc3a  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800cdc41  lea     ecx, [r8-5Bh]
0x1800cdc45  call    AslLogCallPrintf
0x1800cdc4a  mov     edx, 5Dh ; ']'; void *
0x1800cdc4f  mov     rcx, [rsp+38h]; this
0x1800cdc54  mov     r9d, ebx; char *
0x1800cdc57  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800cdc5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cdc63  jmp     loc_1800CDD74
0x1800cdc68  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800cdc71  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800cdc79  mov     r9, rdi; lpParameter
0x1800cdc7c  lea     r8, ?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x1800cdc83  mov     edx, 1; dwStackSize
0x1800cdc88  xor     ecx, ecx; lpThreadAttributes
0x1800cdc8a  call    cs:__imp_CreateThread
0x1800cdc90  mov     rdx, rax
0x1800cdc93  lea     rcx, [rdi+20h]
0x1800cdc97  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cdc9c  mov     rax, [rdi+20h]
0x1800cdca0  inc     rax
0x1800cdca3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800cdca9  jnz     short loc_1800CDCEF
0x1800cdcab  call    cs:__imp_GetLastError
0x1800cdcb1  mov     [rsp+38h+dwCreationFlags], eax
0x1800cdcb5  lea     r9, aCreatethreadFa; "CreateThread failed [%d]"
0x1800cdcbc  mov     r8d, 63h ; 'c'
0x1800cdcc2  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800cdcc9  lea     ecx, [r8-62h]
0x1800cdccd  call    AslLogCallPrintf
0x1800cdcd2  mov     rcx, [rsp+38h]; this
0x1800cdcd7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800cdcde  mov     edx, 64h ; 'd'; void *
0x1800cdce3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cdce8  mov     ebx, eax
0x1800cdcea  jmp     loc_1800CDD74
0x1800cdcef  mov     edx, 2710h; dwMilliseconds
0x1800cdcf4  mov     rcx, [rdi+38h]; hHandle
0x1800cdcf8  call    cs:__imp_WaitForSingleObject
0x1800cdcfe  mov     ebx, eax
0x1800cdd00  test    eax, eax
0x1800cdd02  jz      short loc_1800CDD72
0x1800cdd04  cmp     eax, 0FFFFFFFFh
0x1800cdd07  jnz     short loc_1800CDD3A
0x1800cdd09  call    cs:__imp_GetLastError
0x1800cdd0f  mov     [rsp+38h+dwCreationFlags], eax
0x1800cdd13  lea     r9, aWaitforsingleo_0; "WaitForSingleObject failed [%d]"
0x1800cdd1a  mov     r8d, 6Ch ; 'l'
0x1800cdd20  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800cdd27  lea     ecx, [r8-6Bh]
0x1800cdd2b  call    AslLogCallPrintf
0x1800cdd30  call    cs:__imp_GetLastError
0x1800cdd36  mov     ebx, eax
0x1800cdd38  jmp     short loc_1800CDD5B
0x1800cdd3a  mov     [rsp+38h+dwCreationFlags], eax
0x1800cdd3e  lea     r9, aWaitforsingleo_1; "WaitForSingleObject returned [%d]"
0x1800cdd45  mov     r8d, 71h ; 'q'
0x1800cdd4b  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800cdd52  lea     ecx, [r8-70h]
0x1800cdd56  call    AslLogCallPrintf
0x1800cdd5b  mov     rcx, rdi; this
0x1800cdd5e  call    ?Stop@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::Stop(void)
0x1800cdd63  test    ebx, ebx
0x1800cdd65  jle     short loc_1800CDD74
0x1800cdd67  movzx   ebx, bx
0x1800cdd6a  or      ebx, 80070000h
0x1800cdd70  jmp     short loc_1800CDD74
0x1800cdd72  xor     ebx, ebx
0x1800cdd74  lea     rcx, [rsp+38h+arg_0]
0x1800cdd79  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cdd7e  mov     eax, ebx
0x1800cdd80  mov     rbx, [rsp+38h+arg_8]
0x1800cdd85  mov     rsi, [rsp+38h+arg_10]
0x1800cdd8a  add     rsp, 30h
0x1800cdd8e  pop     rdi
0x1800cdd8f  retn
```
