# Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Create(HCS_SYSTEM__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18017651c`
- end: `0x1801767a3`
- name: `?Create@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@QEAAXPEAUHCS_SYSTEM__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(void *context, HCS_SYSTEM computeSystem, PCWSTR processParameters)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18017fde4`

## callees

- `0x18002e2b4`
- `0x1800491e8`
- `0x1801260f0`
- `0x18017651c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801765f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801765f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801766b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801766b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176640`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017665f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017665f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801766cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801766e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180176703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801766cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801766e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180176703`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180176545`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180176545`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180176729`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180176729`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176651`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176719`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176651`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176719`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateProcess` at `0x18017658c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateProcess` at `0x18017658c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x180176613`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x180176613`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x1801765bc`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x1801765bc`

## string_xrefs

- `0x180176755`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180176767`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x18017677c`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180176791`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Create(
        RTL_SRWLOCK *context,
        HCS_SYSTEM computeSystem,
        const WCHAR *processParameters)
{
  HCS_OPERATION Operation; // rbx
  const char *v7; // r9
  HRESULT v8; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  HCS_PROCESS v11; // r12
  HCS_PROCESS Ptr; // r14
  DWORD LastError; // edi
  int process; // [rsp+20h] [rbp-60h]
  HCS_PROCESS v15; // [rsp+30h] [rbp-50h] BYREF
  HANDLE StdOutput; // [rsp+38h] [rbp-48h] BYREF
  HANDLE v17[3]; // [rsp+40h] [rbp-40h] BYREF
  HCS_PROCESS_INFORMATION processInformation; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HANDLE hObject; // [rsp+C8h] [rbp+48h] BYREF

  Operation = HcsCreateOperation(0, 0);
  v17[1] = Operation;
  if ( !Operation )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      v7);
  v15 = 0;
  if ( *((_QWORD *)processParameters + 3) > 7u )
    processParameters = *(const WCHAR **)processParameters;
  v8 = HcsCreateProcess(computeSystem, processParameters, Operation, 0, &v15);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v8,
      process);
  memset(&processInformation, 0, sizeof(processInformation));
  v9 = HcsWaitForOperationResultAndProcessInfo(Operation, 0xFFFFFFFF, &processInformation, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v9,
      process);
  v17[0] = processInformation.StdInput;
  StdOutput = processInformation.StdOutput;
  hObject = processInformation.StdError;
  AcquireSRWLockExclusive(context + 5);
  v17[2] = &context[5];
  v10 = HcsSetProcessCallback(
          v15,
          HcsEventOptionNone,
          context,
          Container::Manager::Hcs::Details::ComputeSystemProcessImpl::OnProcessEvent);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v10,
      process);
  if ( context != (RTL_SRWLOCK *)&v15 )
  {
    v11 = v15;
    Ptr = (HCS_PROCESS)context->Ptr;
    if ( context->Ptr )
    {
      LastError = GetLastError();
      HcsCloseProcess(Ptr);
      SetLastError(LastError);
    }
    context->Ptr = v11;
    v15 = 0;
  }
  LODWORD(context[1].Ptr) = processInformation.ProcessId;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &context[2],
    v17);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &context[3],
    &StdOutput);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &context[4],
    &hObject);
  LODWORD(context[6].Ptr) = 1;
  if ( context != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(context + 5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)StdOutput - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(StdOutput);
  if ( (unsigned __int64)v17[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v17[0]);
  if ( v15 )
    HcsCloseProcess(v15);
  HcsCloseOperation(Operation);
}

```

## disassembly

```asm
0x18017651c  mov     [rsp-28h+arg_0], rbx
0x180176521  mov     [rsp-28h+arg_8], rsi
0x180176526  push    rbp
0x180176527  push    rdi
0x180176528  push    r12
0x18017652a  push    r14
0x18017652c  push    r15
0x18017652e  mov     rbp, rsp
0x180176531  sub     rsp, 80h
0x180176538  mov     rdi, r8
0x18017653b  mov     r14, rdx
0x18017653e  mov     rsi, rcx
0x180176541  xor     edx, edx; callback
0x180176543  xor     ecx, ecx; context
0x180176545  call    cs:__imp_HcsCreateOperation
0x18017654c  nop     dword ptr [rax+rax+00h]
0x180176551  mov     rbx, rax
0x180176554  mov     [rbp+var_38], rax
0x180176558  mov     rcx, [rbp+28h]; this
0x18017655c  test    rax, rax
0x18017655f  jz      loc_180176767
0x180176565  mov     [rbp+var_50], 0
0x18017656d  cmp     qword ptr [rdi+18h], 7
0x180176572  jbe     short loc_180176577
0x180176574  mov     rdi, [rdi]
0x180176577  lea     rax, [rbp+var_50]
0x18017657b  mov     qword ptr [rsp+80h+process], rax; int
0x180176580  xor     r9d, r9d; securityDescriptor
0x180176583  mov     r8, rbx; operation
0x180176586  mov     rdx, rdi; processParameters
0x180176589  mov     rcx, r14; computeSystem
0x18017658c  call    cs:__imp_HcsCreateProcess
0x180176593  nop     dword ptr [rax+rax+00h]
0x180176598  mov     rcx, [rbp+28h]; this
0x18017659c  test    eax, eax
0x18017659e  js      loc_180176779
0x1801765a4  xorps   xmm0, xmm0
0x1801765a7  movups  xmmword ptr [rbp+processInformation.ProcessId], xmm0
0x1801765ab  movups  xmmword ptr [rbp+processInformation.StdOutput], xmm0
0x1801765af  xor     r9d, r9d; resultDocument
0x1801765b2  lea     r8, [rbp+processInformation]; processInformation
0x1801765b6  or      edx, 0FFFFFFFFh; timeoutMs
0x1801765b9  mov     rcx, rbx; operation
0x1801765bc  call    cs:__imp_HcsWaitForOperationResultAndProcessInfo
0x1801765c3  nop     dword ptr [rax+rax+00h]
0x1801765c8  mov     rcx, [rbp+28h]; this
0x1801765cc  test    eax, eax
0x1801765ce  js      loc_18017678E
0x1801765d4  mov     rax, [rbp+processInformation.StdInput]
0x1801765d8  mov     [rbp+var_40], rax
0x1801765dc  mov     rax, [rbp+processInformation.StdOutput]
0x1801765e0  mov     [rbp+var_48], rax
0x1801765e4  mov     rax, [rbp+processInformation.StdError]
0x1801765e8  mov     [rbp+hObject], rax
0x1801765ec  lea     r15, [rsi+28h]
0x1801765f0  mov     rcx, r15; SRWLock
0x1801765f3  call    cs:__imp_AcquireSRWLockExclusive
0x1801765fa  nop     dword ptr [rax+rax+00h]
0x1801765ff  mov     [rbp+var_30], r15
0x180176603  lea     r9, ?OnProcessEvent@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x18017660a  mov     r8, rsi; context
0x18017660d  xor     edx, edx; callbackOptions
0x18017660f  mov     rcx, [rbp+var_50]; process
0x180176613  call    cs:__imp_HcsSetProcessCallback
0x18017661a  nop     dword ptr [rax+rax+00h]
0x18017661f  mov     rcx, [rbp+28h]; this
0x180176623  test    eax, eax
0x180176625  js      loc_180176752
0x18017662b  lea     rax, [rbp+var_50]
0x18017662f  cmp     rsi, rax
0x180176632  jz      short loc_180176676
0x180176634  mov     r12, [rbp+var_50]
0x180176638  mov     r14, [rsi]
0x18017663b  test    r14, r14
0x18017663e  jz      short loc_18017666B
0x180176640  call    cs:__imp_GetLastError
0x180176647  nop     dword ptr [rax+rax+00h]
0x18017664c  mov     edi, eax
0x18017664e  mov     rcx, r14; process
0x180176651  call    cs:__imp_HcsCloseProcess
0x180176658  nop     dword ptr [rax+rax+00h]
0x18017665d  mov     ecx, edi; dwErrCode
0x18017665f  call    cs:__imp_SetLastError
0x180176666  nop     dword ptr [rax+rax+00h]
0x18017666b  mov     [rsi], r12
0x18017666e  mov     [rbp+var_50], 0
0x180176676  mov     eax, [rbp+processInformation.ProcessId]
0x180176679  mov     [rsi+8], eax
0x18017667c  lea     rcx, [rsi+10h]
0x180176680  lea     rdx, [rbp+var_40]
0x180176684  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180176689  lea     rcx, [rsi+18h]
0x18017668d  lea     rdx, [rbp+var_48]
0x180176691  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180176696  lea     rcx, [rsi+20h]
0x18017669a  lea     rdx, [rbp+hObject]
0x18017669e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801766a3  mov     dword ptr [rsi+30h], 1
0x1801766aa  test    r15, r15
0x1801766ad  jz      short loc_1801766BF
0x1801766af  mov     rcx, r15; SRWLock
0x1801766b2  call    cs:__imp_ReleaseSRWLockExclusive
0x1801766b9  nop     dword ptr [rax+rax+00h]
0x1801766be  nop
0x1801766bf  mov     rcx, [rbp+hObject]; hObject
0x1801766c3  lea     rax, [rcx-1]
0x1801766c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801766cb  ja      short loc_1801766DA
0x1801766cd  call    cs:__imp_CloseHandle
0x1801766d4  nop     dword ptr [rax+rax+00h]
0x1801766d9  nop
0x1801766da  mov     rcx, [rbp+var_48]; hObject
0x1801766de  lea     rax, [rcx-1]
0x1801766e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801766e6  ja      short loc_1801766F5
0x1801766e8  call    cs:__imp_CloseHandle
0x1801766ef  nop     dword ptr [rax+rax+00h]
0x1801766f4  nop
0x1801766f5  mov     rcx, [rbp+var_40]; hObject
0x1801766f9  lea     rax, [rcx-1]
0x1801766fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180176701  ja      short loc_180176710
0x180176703  call    cs:__imp_CloseHandle
0x18017670a  nop     dword ptr [rax+rax+00h]
0x18017670f  nop
0x180176710  mov     rcx, [rbp+var_50]; process
0x180176714  test    rcx, rcx
0x180176717  jz      short loc_180176726
0x180176719  call    cs:__imp_HcsCloseProcess
0x180176720  nop     dword ptr [rax+rax+00h]
0x180176725  nop
0x180176726  mov     rcx, rbx; operation
0x180176729  call    cs:__imp_HcsCloseOperation
0x180176730  nop     dword ptr [rax+rax+00h]
0x180176735  lea     r11, [rsp+80h+var_s0]
0x18017673d  mov     rbx, [r11+30h]
0x180176741  mov     rsi, [r11+38h]
0x180176745  mov     rsp, r11
0x180176748  pop     r15
0x18017674a  pop     r14
0x18017674c  pop     r12
0x18017674e  pop     rdi
0x18017674f  pop     rbp
0x180176750  retn
0x180176752  mov     r9d, eax; char *
0x180176755  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017675c  mov     edx, 87h; void *
0x180176761  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180176767  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017676e  mov     edx, 67h ; 'g'; void *
0x180176773  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180176779  mov     r9d, eax; char *
0x18017677c  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180176783  mov     edx, 6Fh ; 'o'; void *
0x180176788  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017678e  mov     r9d, eax; char *
0x180176791  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180176798  mov     edx, 76h ; 'v'; void *
0x18017679d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
