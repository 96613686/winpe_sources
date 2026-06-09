# Windows::Compat::Inventory::InventoryWatchdog::Initialize(void)

- ea: `0x18001e508`
- end: `0x18001e768`
- name: `?Initialize@InventoryWatchdog@Inventory@Compat@Windows@@QEAAJXZ`
- size: `608`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x18000caa4`
- `0x18000cac4`
- `0x18001e508`
- `0x180024d78`
- `0x180027f60`
- `0x18004c020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e51f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e59d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e59d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e753`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e53a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e6ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e53a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e6ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e667`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e67d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e67d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e702`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e63d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001e63d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e65f`

## string_xrefs

- `0x18001e55e`: `CreateEvent failed [%#x]`
- `0x18001e5bd`: `CreateEvent failed [%#x]`
- `0x18001e5f4`: `CreateEvent failed [%#x]`
- `0x18001e687`: `CreateThread failed [%d]`
- `0x18001e588`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x18001e6a9`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x18001e56b`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18001e5ca`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18001e601`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18001e694`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18001e6f2`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18001e71d`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::Initialize(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rdi
  char *Ptr; // rcx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  DWORD v5; // ebx
  __int64 v6; // rdx
  int v8; // eax
  int v9; // eax
  HANDLE Thread; // rbp
  char *v11; // r15
  DWORD LastError; // ebx
  DWORD v13; // eax
  const char *v14; // r9
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  Ptr = (char *)this[4].Ptr;
  if ( (unsigned __int64)(Ptr - 1) > 0xFFFFFFFFFFFFFFFDuLL || WaitForSingleObject(Ptr, 0) != 258 )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[5].Ptr);
    v5 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
        78,
        "CreateEvent failed [%#x]",
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
      v6 = 79;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
        (const char *)v5,
        dwCreationFlags);
LABEL_6:
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      return v5;
    }
    v8 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[6].Ptr);
    v5 = v8;
    if ( v8 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
        85,
        "CreateEvent failed [%#x]",
        v8);
      v6 = 86;
      goto LABEL_5;
    }
    v9 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[7].Ptr);
    v5 = v9;
    if ( v9 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
        92,
        "CreateEvent failed [%#x]",
        v9);
      v6 = 93;
      goto LABEL_5;
    }
    Thread = CreateThread(0, 1u, Windows::Compat::Inventory::InventoryWatchdog::ThreadProc, this, 0, 0);
    v11 = (char *)this[4].Ptr;
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v11);
      SetLastError(LastError);
    }
    this[4].Ptr = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v13 = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
        99,
        "CreateThread failed [%d]",
        v13);
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x64,
             (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
             v14);
      goto LABEL_6;
    }
    v15 = WaitForSingleObject(this[7].Ptr, 0x2710u);
    v5 = v15;
    if ( v15 )
    {
      if ( v15 == -1 )
      {
        v16 = GetLastError();
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
          108,
          "WaitForSingleObject failed [%d]",
          v16);
        v5 = GetLastError();
      }
      else
      {
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::InventoryWatchdog::Initialize",
          113,
          "WaitForSingleObject returned [%d]",
          v15);
      }
      Windows::Compat::Inventory::InventoryWatchdog::Stop((Windows::Compat::Inventory::InventoryWatchdog *)this);
      if ( (int)v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_6;
    }
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 0;
}

```

## disassembly

```asm
0x18001e508  push    rbx
0x18001e50a  push    rbp
0x18001e50b  push    rsi
0x18001e50c  push    rdi
0x18001e50d  push    r14
0x18001e50f  push    r15
0x18001e511  sub     rsp, 38h
0x18001e515  mov     rsi, rcx
0x18001e518  lea     rdi, [rcx+18h]
0x18001e51c  mov     rcx, rdi; SRWLock
0x18001e51f  call    cs:__imp_AcquireSRWLockExclusive
0x18001e525  mov     [rsp+68h+arg_0], rdi
0x18001e52a  mov     rcx, [rsi+20h]; hHandle
0x18001e52e  lea     rax, [rcx-1]
0x18001e532  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e536  ja      short loc_18001E54B
0x18001e538  xor     edx, edx; dwMilliseconds
0x18001e53a  call    cs:__imp_WaitForSingleObject
0x18001e540  cmp     eax, 102h
0x18001e545  jz      loc_18001E74B
0x18001e54b  lea     rcx, [rsi+28h]
0x18001e54f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001e554  mov     ebx, eax
0x18001e556  test    eax, eax
0x18001e558  jns     short loc_18001E5AA
0x18001e55a  mov     [rsp+68h+dwCreationFlags], eax; int
0x18001e55e  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18001e565  mov     r8d, 4Eh ; 'N'
0x18001e56b  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::InventoryWa"...
0x18001e572  lea     ecx, [r8-4Dh]
0x18001e576  call    AslLogCallPrintf
0x18001e57b  mov     edx, 4Fh ; 'O'; void *
0x18001e580  mov     rcx, [rsp+68h]; this
0x18001e585  mov     r9d, ebx; char *
0x18001e588  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x18001e58f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e594  nop
0x18001e595  test    rdi, rdi
0x18001e598  jz      short loc_18001E5A3
0x18001e59a  mov     rcx, rdi; SRWLock
0x18001e59d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e5a3  mov     eax, ebx
0x18001e5a5  jmp     loc_18001E75B
0x18001e5aa  lea     rcx, [rsi+30h]
0x18001e5ae  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001e5b3  mov     ebx, eax
0x18001e5b5  test    eax, eax
0x18001e5b7  jns     short loc_18001E5E1
0x18001e5b9  mov     [rsp+68h+dwCreationFlags], eax
0x18001e5bd  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18001e5c4  mov     r8d, 55h ; 'U'
0x18001e5ca  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::InventoryWa"...
0x18001e5d1  lea     ecx, [r8-54h]
0x18001e5d5  call    AslLogCallPrintf
0x18001e5da  mov     edx, 56h ; 'V'
0x18001e5df  jmp     short loc_18001E580
0x18001e5e1  lea     rcx, [rsi+38h]
0x18001e5e5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001e5ea  mov     ebx, eax
0x18001e5ec  test    eax, eax
0x18001e5ee  jns     short loc_18001E61B
0x18001e5f0  mov     [rsp+68h+dwCreationFlags], eax
0x18001e5f4  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18001e5fb  mov     r8d, 5Ch ; '\'
0x18001e601  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::InventoryWa"...
0x18001e608  lea     ecx, [r8-5Bh]
0x18001e60c  call    AslLogCallPrintf
0x18001e611  mov     edx, 5Dh ; ']'
0x18001e616  jmp     loc_18001E580
0x18001e61b  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18001e624  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18001e62c  mov     r9, rsi; lpParameter
0x18001e62f  lea     r8, ?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x18001e636  mov     edx, 1; dwStackSize
0x18001e63b  xor     ecx, ecx; lpThreadAttributes
0x18001e63d  call    cs:__imp_CreateThread
0x18001e643  mov     rbp, rax
0x18001e646  mov     r15, [rsi+20h]
0x18001e64a  lea     rdx, [r15-1]
0x18001e64e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001e652  ja      short loc_18001E66D
0x18001e654  call    cs:__imp_GetLastError
0x18001e65a  mov     ebx, eax
0x18001e65c  mov     rcx, r15; hObject
0x18001e65f  call    cs:__imp_CloseHandle
0x18001e665  mov     ecx, ebx; dwErrCode
0x18001e667  call    cs:__imp_SetLastError
0x18001e66d  mov     [rsi+20h], rbp
0x18001e671  lea     rax, [rbp+1]
0x18001e675  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001e67b  jnz     short loc_18001E6C1
0x18001e67d  call    cs:__imp_GetLastError
0x18001e683  mov     [rsp+68h+dwCreationFlags], eax
0x18001e687  lea     r9, aCreatethreadFa; "CreateThread failed [%d]"
0x18001e68e  mov     r8d, 63h ; 'c'
0x18001e694  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::InventoryWa"...
0x18001e69b  lea     ecx, [r8-62h]
0x18001e69f  call    AslLogCallPrintf
0x18001e6a4  mov     rcx, [rsp+68h]; this
0x18001e6a9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x18001e6b0  mov     edx, 64h ; 'd'; void *
0x18001e6b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e6ba  mov     ebx, eax
0x18001e6bc  jmp     loc_18001E595
0x18001e6c1  mov     edx, 2710h; dwMilliseconds
0x18001e6c6  mov     rcx, [rsi+38h]; hHandle
0x18001e6ca  call    cs:__imp_WaitForSingleObject
0x18001e6d0  mov     ebx, eax
0x18001e6d2  test    eax, eax
0x18001e6d4  jz      short loc_18001E74B
0x18001e6d6  cmp     eax, 0FFFFFFFFh
0x18001e6d9  jnz     short loc_18001E70C
0x18001e6db  call    cs:__imp_GetLastError
0x18001e6e1  mov     [rsp+68h+dwCreationFlags], eax
0x18001e6e5  lea     r9, aWaitforsingleo_0; "WaitForSingleObject failed [%d]"
0x18001e6ec  mov     r8d, 6Ch ; 'l'
0x18001e6f2  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::InventoryWa"...
0x18001e6f9  lea     ecx, [r8-6Bh]
0x18001e6fd  call    AslLogCallPrintf
0x18001e702  call    cs:__imp_GetLastError
0x18001e708  mov     ebx, eax
0x18001e70a  jmp     short loc_18001E72D
0x18001e70c  mov     [rsp+68h+dwCreationFlags], eax
0x18001e710  lea     r9, aWaitforsingleo_1; "WaitForSingleObject returned [%d]"
0x18001e717  mov     r8d, 71h ; 'q'
0x18001e71d  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::InventoryWa"...
0x18001e724  lea     ecx, [r8-70h]
0x18001e728  call    AslLogCallPrintf
0x18001e72d  mov     rcx, rsi; this
0x18001e730  call    ?Stop@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::Stop(void)
0x18001e735  test    ebx, ebx
0x18001e737  jle     loc_18001E595
0x18001e73d  movzx   ebx, bx
0x18001e740  or      ebx, 80070000h
0x18001e746  jmp     loc_18001E595
0x18001e74b  test    rdi, rdi
0x18001e74e  jz      short loc_18001E759
0x18001e750  mov     rcx, rdi; SRWLock
0x18001e753  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e759  xor     eax, eax
0x18001e75b  add     rsp, 38h
0x18001e75f  pop     r15
0x18001e761  pop     r14
0x18001e763  pop     rdi
0x18001e764  pop     rsi
0x18001e765  pop     rbp
0x18001e766  pop     rbx
0x18001e767  retn
```
