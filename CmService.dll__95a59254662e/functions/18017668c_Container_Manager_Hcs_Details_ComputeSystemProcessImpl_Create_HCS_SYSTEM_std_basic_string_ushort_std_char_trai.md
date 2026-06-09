# Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Create(HCS_SYSTEM__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18017668c`
- end: `0x180176913`
- name: `?Create@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@QEAAXPEAUHCS_SYSTEM__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(void *context, HCS_SYSTEM computeSystem, PCWSTR processParameters)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18017ff54`

## callees

- `0x18002e2b4`
- `0x1800491e8`
- `0x1801260f0`
- `0x18017668c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180176763`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180176763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180176822`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180176822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801767b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801767b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801767cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801767cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017683d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180176858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180176873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18017683d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180176858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180176873`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x1801766b5`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x1801766b5`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180176899`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180176899`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x1801767c1`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176889`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x1801767c1`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176889`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateProcess` at `0x1801766fc`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateProcess` at `0x1801766fc`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x180176783`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x180176783`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x18017672c`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x18017672c`

## string_xrefs

- `0x1801768c5`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x1801768d7`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x1801768ec`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180176901`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`

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
0x18017668c  mov     [rsp-28h+arg_0], rbx
0x180176691  mov     [rsp-28h+arg_8], rsi
0x180176696  push    rbp
0x180176697  push    rdi
0x180176698  push    r12
0x18017669a  push    r14
0x18017669c  push    r15
0x18017669e  mov     rbp, rsp
0x1801766a1  sub     rsp, 80h
0x1801766a8  mov     rdi, r8
0x1801766ab  mov     r14, rdx
0x1801766ae  mov     rsi, rcx
0x1801766b1  xor     edx, edx; callback
0x1801766b3  xor     ecx, ecx; context
0x1801766b5  call    cs:__imp_HcsCreateOperation
0x1801766bc  nop     dword ptr [rax+rax+00h]
0x1801766c1  mov     rbx, rax
0x1801766c4  mov     [rbp+var_38], rax
0x1801766c8  mov     rcx, [rbp+28h]; this
0x1801766cc  test    rax, rax
0x1801766cf  jz      loc_1801768D7
0x1801766d5  mov     [rbp+var_50], 0
0x1801766dd  cmp     qword ptr [rdi+18h], 7
0x1801766e2  jbe     short loc_1801766E7
0x1801766e4  mov     rdi, [rdi]
0x1801766e7  lea     rax, [rbp+var_50]
0x1801766eb  mov     qword ptr [rsp+80h+process], rax; int
0x1801766f0  xor     r9d, r9d; securityDescriptor
0x1801766f3  mov     r8, rbx; operation
0x1801766f6  mov     rdx, rdi; processParameters
0x1801766f9  mov     rcx, r14; computeSystem
0x1801766fc  call    cs:__imp_HcsCreateProcess
0x180176703  nop     dword ptr [rax+rax+00h]
0x180176708  mov     rcx, [rbp+28h]; this
0x18017670c  test    eax, eax
0x18017670e  js      loc_1801768E9
0x180176714  xorps   xmm0, xmm0
0x180176717  movups  xmmword ptr [rbp+processInformation.ProcessId], xmm0
0x18017671b  movups  xmmword ptr [rbp+processInformation.StdOutput], xmm0
0x18017671f  xor     r9d, r9d; resultDocument
0x180176722  lea     r8, [rbp+processInformation]; processInformation
0x180176726  or      edx, 0FFFFFFFFh; timeoutMs
0x180176729  mov     rcx, rbx; operation
0x18017672c  call    cs:__imp_HcsWaitForOperationResultAndProcessInfo
0x180176733  nop     dword ptr [rax+rax+00h]
0x180176738  mov     rcx, [rbp+28h]; this
0x18017673c  test    eax, eax
0x18017673e  js      loc_1801768FE
0x180176744  mov     rax, [rbp+processInformation.StdInput]
0x180176748  mov     [rbp+var_40], rax
0x18017674c  mov     rax, [rbp+processInformation.StdOutput]
0x180176750  mov     [rbp+var_48], rax
0x180176754  mov     rax, [rbp+processInformation.StdError]
0x180176758  mov     [rbp+hObject], rax
0x18017675c  lea     r15, [rsi+28h]
0x180176760  mov     rcx, r15; SRWLock
0x180176763  call    cs:__imp_AcquireSRWLockExclusive
0x18017676a  nop     dword ptr [rax+rax+00h]
0x18017676f  mov     [rbp+var_30], r15
0x180176773  lea     r9, ?OnProcessEvent@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x18017677a  mov     r8, rsi; context
0x18017677d  xor     edx, edx; callbackOptions
0x18017677f  mov     rcx, [rbp+var_50]; process
0x180176783  call    cs:__imp_HcsSetProcessCallback
0x18017678a  nop     dword ptr [rax+rax+00h]
0x18017678f  mov     rcx, [rbp+28h]; this
0x180176793  test    eax, eax
0x180176795  js      loc_1801768C2
0x18017679b  lea     rax, [rbp+var_50]
0x18017679f  cmp     rsi, rax
0x1801767a2  jz      short loc_1801767E6
0x1801767a4  mov     r12, [rbp+var_50]
0x1801767a8  mov     r14, [rsi]
0x1801767ab  test    r14, r14
0x1801767ae  jz      short loc_1801767DB
0x1801767b0  call    cs:__imp_GetLastError
0x1801767b7  nop     dword ptr [rax+rax+00h]
0x1801767bc  mov     edi, eax
0x1801767be  mov     rcx, r14; process
0x1801767c1  call    cs:__imp_HcsCloseProcess
0x1801767c8  nop     dword ptr [rax+rax+00h]
0x1801767cd  mov     ecx, edi; dwErrCode
0x1801767cf  call    cs:__imp_SetLastError
0x1801767d6  nop     dword ptr [rax+rax+00h]
0x1801767db  mov     [rsi], r12
0x1801767de  mov     [rbp+var_50], 0
0x1801767e6  mov     eax, [rbp+processInformation.ProcessId]
0x1801767e9  mov     [rsi+8], eax
0x1801767ec  lea     rcx, [rsi+10h]
0x1801767f0  lea     rdx, [rbp+var_40]
0x1801767f4  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801767f9  lea     rcx, [rsi+18h]
0x1801767fd  lea     rdx, [rbp+var_48]
0x180176801  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180176806  lea     rcx, [rsi+20h]
0x18017680a  lea     rdx, [rbp+hObject]
0x18017680e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180176813  mov     dword ptr [rsi+30h], 1
0x18017681a  test    r15, r15
0x18017681d  jz      short loc_18017682F
0x18017681f  mov     rcx, r15; SRWLock
0x180176822  call    cs:__imp_ReleaseSRWLockExclusive
0x180176829  nop     dword ptr [rax+rax+00h]
0x18017682e  nop
0x18017682f  mov     rcx, [rbp+hObject]; hObject
0x180176833  lea     rax, [rcx-1]
0x180176837  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18017683b  ja      short loc_18017684A
0x18017683d  call    cs:__imp_CloseHandle
0x180176844  nop     dword ptr [rax+rax+00h]
0x180176849  nop
0x18017684a  mov     rcx, [rbp+var_48]; hObject
0x18017684e  lea     rax, [rcx-1]
0x180176852  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180176856  ja      short loc_180176865
0x180176858  call    cs:__imp_CloseHandle
0x18017685f  nop     dword ptr [rax+rax+00h]
0x180176864  nop
0x180176865  mov     rcx, [rbp+var_40]; hObject
0x180176869  lea     rax, [rcx-1]
0x18017686d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180176871  ja      short loc_180176880
0x180176873  call    cs:__imp_CloseHandle
0x18017687a  nop     dword ptr [rax+rax+00h]
0x18017687f  nop
0x180176880  mov     rcx, [rbp+var_50]; process
0x180176884  test    rcx, rcx
0x180176887  jz      short loc_180176896
0x180176889  call    cs:__imp_HcsCloseProcess
0x180176890  nop     dword ptr [rax+rax+00h]
0x180176895  nop
0x180176896  mov     rcx, rbx; operation
0x180176899  call    cs:__imp_HcsCloseOperation
0x1801768a0  nop     dword ptr [rax+rax+00h]
0x1801768a5  lea     r11, [rsp+80h+var_s0]
0x1801768ad  mov     rbx, [r11+30h]
0x1801768b1  mov     rsi, [r11+38h]
0x1801768b5  mov     rsp, r11
0x1801768b8  pop     r15
0x1801768ba  pop     r14
0x1801768bc  pop     r12
0x1801768be  pop     rdi
0x1801768bf  pop     rbp
0x1801768c0  retn
0x1801768c2  mov     r9d, eax; char *
0x1801768c5  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x1801768cc  mov     edx, 87h; void *
0x1801768d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801768d7  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x1801768de  mov     edx, 67h ; 'g'; void *
0x1801768e3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1801768e9  mov     r9d, eax; char *
0x1801768ec  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x1801768f3  mov     edx, 6Fh ; 'o'; void *
0x1801768f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801768fe  mov     r9d, eax; char *
0x180176901  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180176908  mov     edx, 76h ; 'v'; void *
0x18017690d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
