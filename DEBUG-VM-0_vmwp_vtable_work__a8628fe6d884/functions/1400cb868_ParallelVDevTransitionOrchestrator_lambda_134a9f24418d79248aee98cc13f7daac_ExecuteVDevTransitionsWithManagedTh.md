# ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__

- ea: `0x1400cb868`
- end: `0x1400cba77`
- name: `ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__`
- size: `527`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cb694`

## callees

- `0x1400315a8`
- `0x14005159c`
- `0x1400ca820`
- `0x1400cb868`
- `0x1400cbf20`
- `0x140132940`
- `0x140132970`
- `0x1401335fc`
- `0x1401339fc`
- `0x140281080`
- `0x14028382c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb9d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb9d3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb9c2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb9c2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb941`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb941`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cba0f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cba0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_134a9f24418d79248aee98cc13f7daac___::ExecuteVDevTransitionsWithManagedThreads__(
        __int64 a1,
        __int64 a2)
{
  DWORD v4; // esi
  int i; // r14d
  char *v6; // rcx
  signed int LastError; // eax
  __int64 v8; // rbx
  signed int v9; // eax
  unsigned int v10; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v16[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v16, 0, sizeof(v16));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___(
    (VmWorkerTrace::ExecuteVDevTransitionsParallel *)v16,
    a1 + 80,
    (const struct _GUID *)(a1 + 96));
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  `eh vector constructor iterator'(
    v15,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v4 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    Thread = CreateThread(
               0,
               0,
               (LPTHREAD_START_ROUTINE)lambda_0d9a039c5a7ca7635e2c060b7202f9f6_::_lambda_invoker_cdecl_,
               Parameter,
               4u,
               0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v15[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v6 = (char *)v15[i];
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(
        a1,
        (unsigned int)LastError);
      *(_BYTE *)(a1 + 8) = 1;
      break;
    }
    hThread[i] = v6;
    ++v4;
  }
  v8 = 0;
  if ( v4 )
  {
    do
    {
      if ( ResumeThread(hThread[v8]) == -1 )
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v9);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < v4 );
    WaitForMultipleObjects(v4, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16, *(unsigned int *)(a1 + 28));
  v10 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v15,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v16);
  return v10;
}

```

## disassembly

```asm
0x1400cb868  push    rbp
0x1400cb86a  push    rbx
0x1400cb86b  push    rsi
0x1400cb86c  push    rdi
0x1400cb86d  push    r14
0x1400cb86f  push    r15
0x1400cb871  lea     rbp, [rsp-2B8h]
0x1400cb879  sub     rsp, 3B8h
0x1400cb880  mov     rax, cs:__security_cookie
0x1400cb887  xor     rax, rsp
0x1400cb88a  mov     [rbp+2E0h+var_40], rax
0x1400cb891  mov     rbx, rdx
0x1400cb894  mov     rdi, rcx
0x1400cb897  xor     edx, edx; Val
0x1400cb899  mov     r8d, 150h; Size
0x1400cb89f  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cb8a6  call    memset_0
0x1400cb8ab  lea     r8, [rdi+60h]
0x1400cb8af  lea     rdx, [rdi+50h]
0x1400cb8b3  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb8ba  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cb8bf  xor     eax, eax
0x1400cb8c1  xchg    al, [rdi+8]
0x1400cb8c4  xor     eax, eax
0x1400cb8c6  xchg    eax, [rdi+1Ch]
0x1400cb8c9  mov     dword ptr [rdi+20h], 0
0x1400cb8d0  mov     [rdi+38h], rbx
0x1400cb8d4  mov     [rsp+3E0h+Parameter], rdi
0x1400cb8d9  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cb8e0  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cb8e5  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cb8ec  mov     edx, 8; unsigned __int64
0x1400cb8f1  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb8f5  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb8f9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cb8fe  nop
0x1400cb8ff  xor     edx, edx; Val
0x1400cb901  mov     r8d, 100h; Size
0x1400cb907  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cb90c  call    memset_0
0x1400cb911  xor     esi, esi
0x1400cb913  xor     r14d, r14d
0x1400cb916  cmp     r14d, [rdi+24h]
0x1400cb91a  jge     loc_1400CB9B3
0x1400cb920  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cb929  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cb931  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cb936  lea     r8, _lambda_0d9a039c5a7ca7635e2c060b7202f9f6____lambda_invoker_cdecl_; lpStartAddress
0x1400cb93d  xor     edx, edx; dwStackSize
0x1400cb93f  xor     ecx, ecx; lpThreadAttributes
0x1400cb941  call    cs:__imp_CreateThread
0x1400cb948  nop     dword ptr [rax+rax+00h]
0x1400cb94d  mov     [rsp+3E0h+var_3B0], rax
0x1400cb952  movsxd  r15, r14d
0x1400cb955  lea     rbx, [rbp+2E0h+var_290]
0x1400cb959  lea     rbx, [rbx+r15*8]
0x1400cb95d  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cb962  mov     rcx, rbx
0x1400cb965  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cb96a  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cb96f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cb974  mov     rcx, [rbx]
0x1400cb977  lea     rax, [rcx-1]
0x1400cb97b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cb97f  ja      short loc_1400CB98D
0x1400cb981  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cb986  inc     esi
0x1400cb988  inc     r14d
0x1400cb98b  jmp     short loc_1400CB916
0x1400cb98d  call    cs:__imp_GetLastError
0x1400cb994  nop     dword ptr [rax+rax+00h]
0x1400cb999  test    eax, eax
0x1400cb99b  jle     short loc_1400CB9A5
0x1400cb99d  movzx   eax, ax
0x1400cb9a0  or      eax, 80070000h
0x1400cb9a5  mov     edx, eax
0x1400cb9a7  mov     rcx, rdi
0x1400cb9aa  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb9af  mov     byte ptr [rdi+8], 1
0x1400cb9b3  xor     ebx, ebx
0x1400cb9b5  test    esi, esi
0x1400cb9b7  jz      short loc_1400CBA1B
0x1400cb9b9  or      r14d, 0FFFFFFFFh
0x1400cb9bd  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cb9c2  call    cs:__imp_ResumeThread
0x1400cb9c9  nop     dword ptr [rax+rax+00h]
0x1400cb9ce  cmp     eax, r14d
0x1400cb9d1  jnz     short loc_1400CB9F9
0x1400cb9d3  call    cs:__imp_GetLastError
0x1400cb9da  nop     dword ptr [rax+rax+00h]
0x1400cb9df  test    eax, eax
0x1400cb9e1  jle     short loc_1400CB9EB
0x1400cb9e3  movzx   eax, ax
0x1400cb9e6  or      eax, 80070000h
0x1400cb9eb  mov     edx, eax
0x1400cb9ed  mov     rcx, rdi
0x1400cb9f0  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb9f5  mov     byte ptr [rdi+8], 1
0x1400cb9f9  inc     ebx
0x1400cb9fb  cmp     ebx, esi
0x1400cb9fd  jb      short loc_1400CB9BD
0x1400cb9ff  mov     r9d, r14d; dwMilliseconds
0x1400cba02  mov     r8d, 1; bWaitAll
0x1400cba08  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cba0d  mov     ecx, esi; nCount
0x1400cba0f  call    cs:__imp_WaitForMultipleObjects
0x1400cba16  nop     dword ptr [rax+rax+00h]
0x1400cba1b  mov     edx, [rdi+1Ch]
0x1400cba1e  nop
0x1400cba1f  lea     rcx, [rbp+2E0h+var_190]
0x1400cba26  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cba2b  mov     ebx, [rdi+1Ch]
0x1400cba2e  nop
0x1400cba2f  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cba36  mov     edx, 8; unsigned __int64
0x1400cba3b  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cba3f  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cba43  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cba48  nop
0x1400cba49  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cba50  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cba55  mov     eax, ebx
0x1400cba57  mov     rcx, [rbp+2E0h+var_40]
0x1400cba5e  xor     rcx, rsp; StackCookie
0x1400cba61  call    __security_check_cookie
0x1400cba66  add     rsp, 3B8h
0x1400cba6d  pop     r15
0x1400cba6f  pop     r14
0x1400cba71  pop     rdi
0x1400cba72  pop     rsi
0x1400cba73  pop     rbx
0x1400cba74  pop     rbp
0x1400cba75  retn
```
