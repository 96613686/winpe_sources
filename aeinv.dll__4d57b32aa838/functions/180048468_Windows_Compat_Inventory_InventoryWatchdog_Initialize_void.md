# Windows::Compat::Inventory::InventoryWatchdog::Initialize(void)

- ea: `0x180048468`
- end: `0x18004868a`
- name: `?Initialize@InventoryWatchdog@Inventory@Compat@Windows@@QEAAJXZ`
- size: `546`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventoryWatchdog *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800482d0`
- `0x180061288`

## callees

- `0x18000a43c`
- `0x1800197d4`
- `0x18003f184`
- `0x18003f424`
- `0x180048468`
- `0x18004869c`
- `0x1800486bc`
- `0x180048ad0`
- `0x180067bb8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180048584`
- `KERNEL32!CreateThread` at `0x180048584`
- `KERNEL32!WaitForSingleObject` at `0x1800485f2`
- `KERNEL32!WaitForSingleObject` at `0x1800485f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004848b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004848b`
- `KERNEL32!GetLastError` at `0x1800485a5`
- `KERNEL32!GetLastError` at `0x180048603`
- `KERNEL32!GetLastError` at `0x18004862a`
- `KERNEL32!GetLastError` at `0x1800485a5`
- `KERNEL32!GetLastError` at `0x180048603`
- `KERNEL32!GetLastError` at `0x18004862a`

## string_xrefs

- `0x1800485af`: `CreateThread failed [%d]`
- `0x1800484c6`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800484fd`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x180048534`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x1800485bc`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x18004861a`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x180048645`: `Windows::Compat::Inventory::InventoryWatchdog::Initialize`
- `0x180048551`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x1800485d1`: `onecore\internal\base\inc\appcompat\inventory\InventoryWatchdog.h`
- `0x1800484b9`: `CreateEvent failed [%#x]`
- `0x1800484f0`: `CreateEvent failed [%#x]`
- `0x180048527`: `CreateEvent failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InventoryWatchdog::Initialize(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  DWORD LastError; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // eax
  HANDLE Thread; // rax
  const char *v9; // r9
  DWORD v10; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  RTL_SRWLOCK *v14; // [rsp+50h] [rbp+8h] BYREF

  v2 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  v14 = v2;
  if ( Windows::Compat::Inventory::InventoryWatchdog::IsRunning((Windows::Compat::Inventory::InventoryWatchdog *)this) )
    goto LABEL_17;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[5]);
  LastError = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    dwCreationFlags = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      78,
      (unsigned int)"CreateEvent failed [%#x]");
    v5 = 79;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
      (const char *)LastError,
      dwCreationFlags);
    goto LABEL_18;
  }
  v6 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[6]);
  LastError = v6;
  if ( v6 < 0 )
  {
    dwCreationFlags = v6;
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      85,
      (unsigned int)"CreateEvent failed [%#x]");
    v5 = 86;
    goto LABEL_8;
  }
  v7 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&this[7]);
  LastError = v7;
  if ( v7 < 0 )
  {
    dwCreationFlags = v7;
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      92,
      (unsigned int)"CreateEvent failed [%#x]");
    v5 = 93;
    goto LABEL_8;
  }
  Thread = CreateThread(0, 1u, Windows::Compat::Inventory::InventoryWatchdog::ThreadProc, this, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &this[4],
    Thread);
  if ( (((unsigned __int64)this[4].Ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      99,
      (unsigned int)"CreateThread failed [%d]");
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x64,
                  (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\InventoryWatchdog.h",
                  v9);
    goto LABEL_18;
  }
  v10 = WaitForSingleObject(this[7].Ptr, 0x2710u);
  LastError = v10;
  if ( !v10 )
  {
LABEL_17:
    LastError = 0;
    goto LABEL_18;
  }
  if ( v10 == -1 )
  {
    GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      108,
      (unsigned int)"WaitForSingleObject failed [%d]");
    LastError = GetLastError();
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::InventoryWatchdog::Initialize",
      113,
      (unsigned int)"WaitForSingleObject returned [%d]");
  }
  Windows::Compat::Inventory::InventoryWatchdog::Stop((Windows::Compat::Inventory::InventoryWatchdog *)this);
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  return LastError;
}

```

## disassembly

```asm
0x180048468  push    rdi
0x18004846a  sub     rsp, 40h
0x18004846e  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180048477  mov     [rsp+48h+arg_8], rbx
0x18004847c  mov     [rsp+48h+arg_10], rsi
0x180048481  mov     rdi, rcx
0x180048484  lea     rbx, [rcx+18h]
0x180048488  mov     rcx, rbx; SRWLock
0x18004848b  call    cs:__imp_AcquireSRWLockExclusive
0x180048491  mov     [rsp+48h+arg_0], rbx
0x180048496  mov     rcx, rdi; this
0x180048499  call    ?IsRunning@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::IsRunning(void)
0x18004849e  test    al, al
0x1800484a0  jnz     loc_18004866C
0x1800484a6  lea     rcx, [rdi+28h]
0x1800484aa  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800484af  mov     ebx, eax
0x1800484b1  test    eax, eax
0x1800484b3  jns     short loc_1800484DD
0x1800484b5  mov     [rsp+48h+dwCreationFlags], eax
0x1800484b9  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x1800484c0  mov     r8d, 4Eh ; 'N'
0x1800484c6  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800484cd  lea     ecx, [r8-4Dh]
0x1800484d1  call    AslLogCallPrintf
0x1800484d6  mov     edx, 4Fh ; 'O'
0x1800484db  jmp     short loc_180048549
0x1800484dd  lea     rcx, [rdi+30h]
0x1800484e1  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800484e6  mov     ebx, eax
0x1800484e8  test    eax, eax
0x1800484ea  jns     short loc_180048514
0x1800484ec  mov     [rsp+48h+dwCreationFlags], eax
0x1800484f0  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x1800484f7  mov     r8d, 55h ; 'U'
0x1800484fd  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x180048504  lea     ecx, [r8-54h]
0x180048508  call    AslLogCallPrintf
0x18004850d  mov     edx, 56h ; 'V'
0x180048512  jmp     short loc_180048549
0x180048514  lea     rcx, [rdi+38h]
0x180048518  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004851d  mov     ebx, eax
0x18004851f  test    eax, eax
0x180048521  jns     short loc_180048562
0x180048523  mov     [rsp+48h+dwCreationFlags], eax; int
0x180048527  lea     r9, aCreateeventFai; "CreateEvent failed [%#x]"
0x18004852e  mov     r8d, 5Ch ; '\'
0x180048534  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18004853b  lea     ecx, [r8-5Bh]
0x18004853f  call    AslLogCallPrintf
0x180048544  mov     edx, 5Dh ; ']'; void *
0x180048549  mov     rcx, [rsp+48h]; this
0x18004854e  mov     r9d, ebx; char *
0x180048551  lea     r8, aOnecoreInterna_8; "onecore\\internal\\base\\inc\\appcompat"...
0x180048558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004855d  jmp     loc_18004866E
0x180048562  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x18004856b  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180048573  mov     r9, rdi; lpParameter
0x180048576  lea     r8, ?ThreadProc@InventoryWatchdog@Inventory@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x18004857d  mov     edx, 1; dwStackSize
0x180048582  xor     ecx, ecx; lpThreadAttributes
0x180048584  call    cs:__imp_CreateThread
0x18004858a  mov     rdx, rax
0x18004858d  lea     rcx, [rdi+20h]
0x180048591  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180048596  mov     rax, [rdi+20h]
0x18004859a  inc     rax
0x18004859d  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800485a3  jnz     short loc_1800485E9
0x1800485a5  call    cs:__imp_GetLastError
0x1800485ab  mov     [rsp+48h+dwCreationFlags], eax
0x1800485af  lea     r9, aCreatethreadFa; "CreateThread failed [%d]"
0x1800485b6  mov     r8d, 63h ; 'c'
0x1800485bc  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x1800485c3  lea     ecx, [r8-62h]
0x1800485c7  call    AslLogCallPrintf
0x1800485cc  mov     rcx, [rsp+48h]; this
0x1800485d1  lea     r8, aOnecoreInterna_8; "onecore\\internal\\base\\inc\\appcompat"...
0x1800485d8  mov     edx, 64h ; 'd'; void *
0x1800485dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800485e2  mov     ebx, eax
0x1800485e4  jmp     loc_18004866E
0x1800485e9  mov     edx, 2710h; dwMilliseconds
0x1800485ee  mov     rcx, [rdi+38h]; hHandle
0x1800485f2  call    cs:__imp_WaitForSingleObject
0x1800485f8  mov     ebx, eax
0x1800485fa  test    eax, eax
0x1800485fc  jz      short loc_18004866C
0x1800485fe  cmp     eax, 0FFFFFFFFh
0x180048601  jnz     short loc_180048634
0x180048603  call    cs:__imp_GetLastError
0x180048609  mov     [rsp+48h+dwCreationFlags], eax
0x18004860d  lea     r9, aWaitforsingleo_0; "WaitForSingleObject failed [%d]"
0x180048614  mov     r8d, 6Ch ; 'l'
0x18004861a  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x180048621  lea     ecx, [r8-6Bh]
0x180048625  call    AslLogCallPrintf
0x18004862a  call    cs:__imp_GetLastError
0x180048630  mov     ebx, eax
0x180048632  jmp     short loc_180048655
0x180048634  mov     [rsp+48h+dwCreationFlags], eax
0x180048638  lea     r9, aWaitforsingleo_1; "WaitForSingleObject returned [%d]"
0x18004863f  mov     r8d, 71h ; 'q'
0x180048645  lea     rdx, aWindowsCompatI_5; "Windows::Compat::Inventory::InventoryWa"...
0x18004864c  lea     ecx, [r8-70h]
0x180048650  call    AslLogCallPrintf
0x180048655  mov     rcx, rdi; this
0x180048658  call    ?Stop@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::Stop(void)
0x18004865d  test    ebx, ebx
0x18004865f  jle     short loc_18004866E
0x180048661  movzx   ebx, bx
0x180048664  or      ebx, 80070000h
0x18004866a  jmp     short loc_18004866E
0x18004866c  xor     ebx, ebx
0x18004866e  lea     rcx, [rsp+48h+arg_0]
0x180048673  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180048678  mov     eax, ebx
0x18004867a  mov     rbx, [rsp+48h+arg_8]
0x18004867f  mov     rsi, [rsp+48h+arg_10]
0x180048684  add     rsp, 40h
0x180048688  pop     rdi
0x180048689  retn
```
