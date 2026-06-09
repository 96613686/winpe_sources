# ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags_&_

- ea: `0x1400cb474`
- end: `0x1400cb68b`
- name: `ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags_&_`
- size: `535`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400ca400`

## callees

- `0x1400315a8`
- `0x14005159c`
- `0x1400ca820`
- `0x1400cb474`
- `0x1400cbf20`
- `0x140132940`
- `0x140132970`
- `0x1401335fc`
- `0x1401339fc`
- `0x140281080`
- `0x14028382c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb5e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb5e7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb5d6`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb5d6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb555`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb555`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb623`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb623`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_b37d4be99a1b4a294a8337e4a985c351___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbOptimizationControlFlags___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  DWORD v6; // edi
  int i; // r14d
  char *v8; // rcx
  signed int LastError; // eax
  __int64 v10; // rbx
  signed int v11; // eax
  unsigned int v12; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v18[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v18, 0, sizeof(v18));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___(
    (VmWorkerTrace::ExecuteVDevTransitionsParallel *)v18,
    a1 + 80,
    (const struct _GUID *)(a1 + 96));
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  Parameter[1] = a3;
  `eh vector constructor iterator'(
    v17,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v6 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    Thread = CreateThread(
               0,
               0,
               (LPTHREAD_START_ROUTINE)lambda_7eac78071b17182a680488bd3565b140_::_lambda_invoker_cdecl_,
               Parameter,
               4u,
               0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v17[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v8 = (char *)v17[i];
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v8;
    ++v6;
  }
  v10 = 0;
  if ( v6 )
  {
    do
    {
      if ( ResumeThread(hThread[v10]) == -1 )
      {
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v11);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < v6 );
    WaitForMultipleObjects(v6, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, *(unsigned int *)(a1 + 28));
  v12 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v17,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v18);
  return v12;
}

```

## disassembly

```asm
0x1400cb474  push    rbp
0x1400cb476  push    rbx
0x1400cb477  push    rsi
0x1400cb478  push    rdi
0x1400cb479  push    r14
0x1400cb47b  push    r15
0x1400cb47d  lea     rbp, [rsp-2B8h]
0x1400cb485  sub     rsp, 3B8h
0x1400cb48c  mov     rax, cs:__security_cookie
0x1400cb493  xor     rax, rsp
0x1400cb496  mov     [rbp+2E0h+var_40], rax
0x1400cb49d  mov     rdi, r8
0x1400cb4a0  mov     rbx, rdx
0x1400cb4a3  mov     rsi, rcx
0x1400cb4a6  xor     edx, edx; Val
0x1400cb4a8  mov     r8d, 150h; Size
0x1400cb4ae  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cb4b5  call    memset_0
0x1400cb4ba  lea     r8, [rsi+60h]
0x1400cb4be  lea     rdx, [rsi+50h]
0x1400cb4c2  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb4c9  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cb4ce  xor     eax, eax
0x1400cb4d0  xchg    al, [rsi+8]
0x1400cb4d3  xor     eax, eax
0x1400cb4d5  xchg    eax, [rsi+1Ch]
0x1400cb4d8  mov     dword ptr [rsi+20h], 0
0x1400cb4df  mov     [rsi+38h], rbx
0x1400cb4e3  mov     [rsp+3E0h+Parameter], rsi
0x1400cb4e8  mov     [rsp+3E0h+var_3A0], rdi
0x1400cb4ed  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cb4f4  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cb4f9  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cb500  mov     edx, 8; unsigned __int64
0x1400cb505  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb509  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb50d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cb512  nop
0x1400cb513  xor     edx, edx; Val
0x1400cb515  mov     r8d, 100h; Size
0x1400cb51b  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cb520  call    memset_0
0x1400cb525  xor     edi, edi
0x1400cb527  xor     r14d, r14d
0x1400cb52a  cmp     r14d, [rsi+24h]
0x1400cb52e  jge     loc_1400CB5C7
0x1400cb534  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cb53d  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cb545  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cb54a  lea     r8, _lambda_7eac78071b17182a680488bd3565b140____lambda_invoker_cdecl_; lpStartAddress
0x1400cb551  xor     edx, edx; dwStackSize
0x1400cb553  xor     ecx, ecx; lpThreadAttributes
0x1400cb555  call    cs:__imp_CreateThread
0x1400cb55c  nop     dword ptr [rax+rax+00h]
0x1400cb561  mov     [rsp+3E0h+var_3B0], rax
0x1400cb566  movsxd  r15, r14d
0x1400cb569  lea     rbx, [rbp+2E0h+var_290]
0x1400cb56d  lea     rbx, [rbx+r15*8]
0x1400cb571  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cb576  mov     rcx, rbx
0x1400cb579  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cb57e  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cb583  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cb588  mov     rcx, [rbx]
0x1400cb58b  lea     rax, [rcx-1]
0x1400cb58f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cb593  ja      short loc_1400CB5A1
0x1400cb595  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cb59a  inc     edi
0x1400cb59c  inc     r14d
0x1400cb59f  jmp     short loc_1400CB52A
0x1400cb5a1  call    cs:__imp_GetLastError
0x1400cb5a8  nop     dword ptr [rax+rax+00h]
0x1400cb5ad  test    eax, eax
0x1400cb5af  jle     short loc_1400CB5B9
0x1400cb5b1  movzx   eax, ax
0x1400cb5b4  or      eax, 80070000h
0x1400cb5b9  mov     edx, eax
0x1400cb5bb  mov     rcx, rsi
0x1400cb5be  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb5c3  mov     byte ptr [rsi+8], 1
0x1400cb5c7  xor     ebx, ebx
0x1400cb5c9  test    edi, edi
0x1400cb5cb  jz      short loc_1400CB62F
0x1400cb5cd  or      r14d, 0FFFFFFFFh
0x1400cb5d1  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cb5d6  call    cs:__imp_ResumeThread
0x1400cb5dd  nop     dword ptr [rax+rax+00h]
0x1400cb5e2  cmp     eax, r14d
0x1400cb5e5  jnz     short loc_1400CB60D
0x1400cb5e7  call    cs:__imp_GetLastError
0x1400cb5ee  nop     dword ptr [rax+rax+00h]
0x1400cb5f3  test    eax, eax
0x1400cb5f5  jle     short loc_1400CB5FF
0x1400cb5f7  movzx   eax, ax
0x1400cb5fa  or      eax, 80070000h
0x1400cb5ff  mov     edx, eax
0x1400cb601  mov     rcx, rsi
0x1400cb604  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb609  mov     byte ptr [rsi+8], 1
0x1400cb60d  inc     ebx
0x1400cb60f  cmp     ebx, edi
0x1400cb611  jb      short loc_1400CB5D1
0x1400cb613  mov     r9d, r14d; dwMilliseconds
0x1400cb616  mov     r8d, 1; bWaitAll
0x1400cb61c  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cb621  mov     ecx, edi; nCount
0x1400cb623  call    cs:__imp_WaitForMultipleObjects
0x1400cb62a  nop     dword ptr [rax+rax+00h]
0x1400cb62f  mov     edx, [rsi+1Ch]
0x1400cb632  nop
0x1400cb633  lea     rcx, [rbp+2E0h+var_190]
0x1400cb63a  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cb63f  mov     ebx, [rsi+1Ch]
0x1400cb642  nop
0x1400cb643  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cb64a  mov     edx, 8; unsigned __int64
0x1400cb64f  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb653  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb657  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cb65c  nop
0x1400cb65d  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb664  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cb669  mov     eax, ebx
0x1400cb66b  mov     rcx, [rbp+2E0h+var_40]
0x1400cb672  xor     rcx, rsp; StackCookie
0x1400cb675  call    __security_check_cookie
0x1400cb67a  add     rsp, 3B8h
0x1400cb681  pop     r15
0x1400cb683  pop     r14
0x1400cb685  pop     rdi
0x1400cb686  pop     rsi
0x1400cb687  pop     rbx
0x1400cb688  pop     rbp
0x1400cb689  retn
```
