# Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Open(HCS_SYSTEM__ *,ulong)

- ea: `0x18017702c`
- end: `0x1801772d1`
- name: `?Open@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@QEAAXPEAUHCS_SYSTEM__@@K@Z`
- size: `677`
- prototype: `void __fastcall(Container::Manager::Hcs::Details::ComputeSystemProcessImpl *__hidden this, HCS_SYSTEM computeSystem, DWORD processId)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180181fe8`

## callees

- `0x18002e2b4`
- `0x1800491e8`
- `0x1801260f0`
- `0x18017702c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017710f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017710f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801771ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801771ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017715c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017715c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017717b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017717b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801771e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177204`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017721f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801771e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177204`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017721f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetProcessInfo` at `0x1801770a8`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetProcessInfo` at `0x1801770a8`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180177081`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180177081`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017722f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017722f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x18017716d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180177245`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x18017716d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180177245`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenProcess` at `0x180177065`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenProcess` at `0x180177065`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x18017712f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x18017712f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x1801770d8`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x1801770d8`

## string_xrefs

- `0x18017726e`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180177283`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180177295`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x1801772aa`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x1801772bf`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Open(
        RTL_SRWLOCK *this,
        HCS_SYSTEM computeSystem,
        DWORD processId)
{
  HRESULT v4; // eax
  HCS_OPERATION Operation; // rax
  const char *v6; // r9
  HCS_OPERATION v7; // rbx
  HRESULT ProcessInfo; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  HCS_PROCESS v11; // r12
  HCS_PROCESS Ptr; // r14
  DWORD LastError; // edi
  HCS_PROCESS process; // [rsp+20h] [rbp-50h] BYREF
  HANDLE StdOutput; // [rsp+28h] [rbp-48h] BYREF
  HANDLE v16[3]; // [rsp+30h] [rbp-40h] BYREF
  HCS_PROCESS_INFORMATION processInformation; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  HANDLE hObject; // [rsp+B8h] [rbp+48h] BYREF

  process = 0;
  v4 = HcsOpenProcess(computeSystem, processId, 0x10000000u, &process);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v4,
      (int)process);
  Operation = HcsCreateOperation(0, 0);
  v7 = Operation;
  v16[1] = Operation;
  if ( !Operation )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      v6);
  ProcessInfo = HcsGetProcessInfo(process, Operation);
  if ( ProcessInfo < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)ProcessInfo,
      (int)process);
  memset(&processInformation, 0, sizeof(processInformation));
  v9 = HcsWaitForOperationResultAndProcessInfo(v7, 0xFFFFFFFF, &processInformation, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v9,
      (int)process);
  v16[0] = processInformation.StdInput;
  StdOutput = processInformation.StdOutput;
  hObject = processInformation.StdError;
  AcquireSRWLockExclusive(this + 5);
  v16[2] = &this[5];
  v10 = HcsSetProcessCallback(
          process,
          HcsEventOptionNone,
          this,
          Container::Manager::Hcs::Details::ComputeSystemProcessImpl::OnProcessEvent);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v10,
      (int)process);
  if ( this != (RTL_SRWLOCK *)&process )
  {
    v11 = process;
    Ptr = (HCS_PROCESS)this->Ptr;
    if ( this->Ptr )
    {
      LastError = GetLastError();
      HcsCloseProcess(Ptr);
      SetLastError(LastError);
    }
    this->Ptr = v11;
    process = 0;
  }
  LODWORD(this[1].Ptr) = processInformation.ProcessId;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this[2],
    v16);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this[3],
    &StdOutput);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this[4],
    &hObject);
  LODWORD(this[6].Ptr) = 1;
  if ( this != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(this + 5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)StdOutput - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(StdOutput);
  if ( (unsigned __int64)v16[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v16[0]);
  HcsCloseOperation(v7);
  if ( process )
    HcsCloseProcess(process);
}

```

## disassembly

```asm
0x18017702c  mov     [rsp-28h+arg_0], rbx
0x180177031  mov     [rsp-28h+arg_8], rsi
0x180177036  push    rbp
0x180177037  push    rdi
0x180177038  push    r12
0x18017703a  push    r14
0x18017703c  push    r15
0x18017703e  mov     rbp, rsp
0x180177041  sub     rsp, 70h
0x180177045  mov     eax, r8d
0x180177048  mov     r10, rdx
0x18017704b  mov     rsi, rcx
0x18017704e  mov     [rbp+process], 0
0x180177056  lea     r9, [rbp+process]; process
0x18017705a  mov     r8d, 10000000h; requestedAccess
0x180177060  mov     edx, eax; processId
0x180177062  mov     rcx, r10; computeSystem
0x180177065  call    cs:__imp_HcsOpenProcess
0x18017706c  nop     dword ptr [rax+rax+00h]
0x180177071  mov     rcx, [rbp+28h]; this
0x180177075  test    eax, eax
0x180177077  js      loc_180177280
0x18017707d  xor     edx, edx; callback
0x18017707f  xor     ecx, ecx; context
0x180177081  call    cs:__imp_HcsCreateOperation
0x180177088  nop     dword ptr [rax+rax+00h]
0x18017708d  mov     rbx, rax
0x180177090  mov     [rbp+var_38], rax
0x180177094  mov     rcx, [rbp+28h]; this
0x180177098  test    rax, rax
0x18017709b  jz      loc_180177295
0x1801770a1  mov     rdx, rax; operation
0x1801770a4  mov     rcx, [rbp+process]; process
0x1801770a8  call    cs:__imp_HcsGetProcessInfo
0x1801770af  nop     dword ptr [rax+rax+00h]
0x1801770b4  mov     rcx, [rbp+28h]; this
0x1801770b8  test    eax, eax
0x1801770ba  js      loc_1801772A7
0x1801770c0  xorps   xmm0, xmm0
0x1801770c3  movups  xmmword ptr [rbp+processInformation.ProcessId], xmm0
0x1801770c7  movups  xmmword ptr [rbp+processInformation.StdOutput], xmm0
0x1801770cb  xor     r9d, r9d; resultDocument
0x1801770ce  lea     r8, [rbp+processInformation]; processInformation
0x1801770d2  or      edx, 0FFFFFFFFh; timeoutMs
0x1801770d5  mov     rcx, rbx; operation
0x1801770d8  call    cs:__imp_HcsWaitForOperationResultAndProcessInfo
0x1801770df  nop     dword ptr [rax+rax+00h]
0x1801770e4  mov     rcx, [rbp+28h]; this
0x1801770e8  test    eax, eax
0x1801770ea  js      loc_1801772BC
0x1801770f0  mov     rax, [rbp+processInformation.StdInput]
0x1801770f4  mov     [rbp+var_40], rax
0x1801770f8  mov     rax, [rbp+processInformation.StdOutput]
0x1801770fc  mov     [rbp+var_48], rax
0x180177100  mov     rax, [rbp+processInformation.StdError]
0x180177104  mov     [rbp+hObject], rax
0x180177108  lea     r15, [rsi+28h]
0x18017710c  mov     rcx, r15; SRWLock
0x18017710f  call    cs:__imp_AcquireSRWLockExclusive
0x180177116  nop     dword ptr [rax+rax+00h]
0x18017711b  mov     [rbp+var_30], r15
0x18017711f  lea     r9, ?OnProcessEvent@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x180177126  mov     r8, rsi; context
0x180177129  xor     edx, edx; callbackOptions
0x18017712b  mov     rcx, [rbp+process]; process
0x18017712f  call    cs:__imp_HcsSetProcessCallback
0x180177136  nop     dword ptr [rax+rax+00h]
0x18017713b  mov     rcx, [rbp+28h]; this
0x18017713f  test    eax, eax
0x180177141  js      loc_18017726B
0x180177147  lea     rax, [rbp+process]
0x18017714b  cmp     rsi, rax
0x18017714e  jz      short loc_180177192
0x180177150  mov     r12, [rbp+process]
0x180177154  mov     r14, [rsi]
0x180177157  test    r14, r14
0x18017715a  jz      short loc_180177187
0x18017715c  call    cs:__imp_GetLastError
0x180177163  nop     dword ptr [rax+rax+00h]
0x180177168  mov     edi, eax
0x18017716a  mov     rcx, r14; process
0x18017716d  call    cs:__imp_HcsCloseProcess
0x180177174  nop     dword ptr [rax+rax+00h]
0x180177179  mov     ecx, edi; dwErrCode
0x18017717b  call    cs:__imp_SetLastError
0x180177182  nop     dword ptr [rax+rax+00h]
0x180177187  mov     [rsi], r12
0x18017718a  mov     [rbp+process], 0
0x180177192  mov     eax, [rbp+processInformation.ProcessId]
0x180177195  mov     [rsi+8], eax
0x180177198  lea     rcx, [rsi+10h]
0x18017719c  lea     rdx, [rbp+var_40]
0x1801771a0  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801771a5  lea     rcx, [rsi+18h]
0x1801771a9  lea     rdx, [rbp+var_48]
0x1801771ad  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801771b2  lea     rcx, [rsi+20h]
0x1801771b6  lea     rdx, [rbp+hObject]
0x1801771ba  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801771bf  mov     dword ptr [rsi+30h], 1
0x1801771c6  test    r15, r15
0x1801771c9  jz      short loc_1801771DB
0x1801771cb  mov     rcx, r15; SRWLock
0x1801771ce  call    cs:__imp_ReleaseSRWLockExclusive
0x1801771d5  nop     dword ptr [rax+rax+00h]
0x1801771da  nop
0x1801771db  mov     rcx, [rbp+hObject]; hObject
0x1801771df  lea     rax, [rcx-1]
0x1801771e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801771e7  ja      short loc_1801771F6
0x1801771e9  call    cs:__imp_CloseHandle
0x1801771f0  nop     dword ptr [rax+rax+00h]
0x1801771f5  nop
0x1801771f6  mov     rcx, [rbp+var_48]; hObject
0x1801771fa  lea     rax, [rcx-1]
0x1801771fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180177202  ja      short loc_180177211
0x180177204  call    cs:__imp_CloseHandle
0x18017720b  nop     dword ptr [rax+rax+00h]
0x180177210  nop
0x180177211  mov     rcx, [rbp+var_40]; hObject
0x180177215  lea     rax, [rcx-1]
0x180177219  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18017721d  ja      short loc_18017722C
0x18017721f  call    cs:__imp_CloseHandle
0x180177226  nop     dword ptr [rax+rax+00h]
0x18017722b  nop
0x18017722c  mov     rcx, rbx; operation
0x18017722f  call    cs:__imp_HcsCloseOperation
0x180177236  nop     dword ptr [rax+rax+00h]
0x18017723b  nop
0x18017723c  mov     rcx, [rbp+process]; process
0x180177240  test    rcx, rcx
0x180177243  jz      short loc_180177251
0x180177245  call    cs:__imp_HcsCloseProcess
0x18017724c  nop     dword ptr [rax+rax+00h]
0x180177251  lea     r11, [rsp+70h+var_s0]
0x180177256  mov     rbx, [r11+30h]
0x18017725a  mov     rsi, [r11+38h]
0x18017725e  mov     rsp, r11
0x180177261  pop     r15
0x180177263  pop     r14
0x180177265  pop     r12
0x180177267  pop     rdi
0x180177268  pop     rbp
0x180177269  retn
0x18017726b  mov     r9d, eax; char *
0x18017726e  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180177275  mov     edx, 0D4h; void *
0x18017727a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180177280  mov     r9d, eax; char *
0x180177283  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017728a  mov     edx, 0B3h; void *
0x18017728f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180177295  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017729c  mov     edx, 0B7h; void *
0x1801772a1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1801772a7  mov     r9d, eax; char *
0x1801772aa  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x1801772b1  mov     edx, 0BAh; void *
0x1801772b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801772bc  mov     r9d, eax; char *
0x1801772bf  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x1801772c6  mov     edx, 0C1h; void *
0x1801772cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
