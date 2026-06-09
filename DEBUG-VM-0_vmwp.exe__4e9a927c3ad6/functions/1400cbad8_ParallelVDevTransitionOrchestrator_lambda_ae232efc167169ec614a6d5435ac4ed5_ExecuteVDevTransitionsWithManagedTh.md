# ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags_&_

- ea: `0x1400cbad8`
- end: `0x1400cbcef`
- name: `ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags_&_`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400caa68`

## callees

- `0x1400315a8`
- `0x14005159c`
- `0x1400ca820`
- `0x1400cbad8`
- `0x1400cbf20`
- `0x140132940`
- `0x140132970`
- `0x1401335fc`
- `0x1401339fc`
- `0x140281080`
- `0x14028382c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbc4b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbc3a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbc3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbbb9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbbb9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbc87`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbc87`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_ae232efc167169ec614a6d5435ac4ed5___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbPowerOffFlags___(
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
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v18);
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
    Thread = CreateThread(0, 0, lambda_1beeb3f5b12b17edc670c5c4fb163e90_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
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
0x1400cbad8  push    rbp
0x1400cbada  push    rbx
0x1400cbadb  push    rsi
0x1400cbadc  push    rdi
0x1400cbadd  push    r14
0x1400cbadf  push    r15
0x1400cbae1  lea     rbp, [rsp-2B8h]
0x1400cbae9  sub     rsp, 3B8h
0x1400cbaf0  mov     rax, cs:__security_cookie
0x1400cbaf7  xor     rax, rsp
0x1400cbafa  mov     [rbp+2E0h+var_40], rax
0x1400cbb01  mov     rdi, r8
0x1400cbb04  mov     rbx, rdx
0x1400cbb07  mov     rsi, rcx
0x1400cbb0a  xor     edx, edx; Val
0x1400cbb0c  mov     r8d, 150h; Size
0x1400cbb12  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cbb19  call    memset_0
0x1400cbb1e  lea     r8, [rsi+60h]
0x1400cbb22  lea     rdx, [rsi+50h]
0x1400cbb26  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbb2d  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cbb32  xor     eax, eax
0x1400cbb34  xchg    al, [rsi+8]
0x1400cbb37  xor     eax, eax
0x1400cbb39  xchg    eax, [rsi+1Ch]
0x1400cbb3c  mov     dword ptr [rsi+20h], 0
0x1400cbb43  mov     [rsi+38h], rbx
0x1400cbb47  mov     [rsp+3E0h+Parameter], rsi
0x1400cbb4c  mov     [rsp+3E0h+var_3A0], rdi
0x1400cbb51  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cbb58  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cbb5d  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cbb64  mov     edx, 8; unsigned __int64
0x1400cbb69  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbb6d  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbb71  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cbb76  nop
0x1400cbb77  xor     edx, edx; Val
0x1400cbb79  mov     r8d, 100h; Size
0x1400cbb7f  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cbb84  call    memset_0
0x1400cbb89  xor     edi, edi
0x1400cbb8b  xor     r14d, r14d
0x1400cbb8e  cmp     r14d, [rsi+24h]
0x1400cbb92  jge     loc_1400CBC2B
0x1400cbb98  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cbba1  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cbba9  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cbbae  lea     r8, _lambda_1beeb3f5b12b17edc670c5c4fb163e90____lambda_invoker_cdecl_; lpStartAddress
0x1400cbbb5  xor     edx, edx; dwStackSize
0x1400cbbb7  xor     ecx, ecx; lpThreadAttributes
0x1400cbbb9  call    cs:__imp_CreateThread
0x1400cbbc0  nop     dword ptr [rax+rax+00h]
0x1400cbbc5  mov     [rsp+3E0h+var_3B0], rax
0x1400cbbca  movsxd  r15, r14d
0x1400cbbcd  lea     rbx, [rbp+2E0h+var_290]
0x1400cbbd1  lea     rbx, [rbx+r15*8]
0x1400cbbd5  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cbbda  mov     rcx, rbx
0x1400cbbdd  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cbbe2  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cbbe7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cbbec  mov     rcx, [rbx]
0x1400cbbef  lea     rax, [rcx-1]
0x1400cbbf3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cbbf7  ja      short loc_1400CBC05
0x1400cbbf9  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cbbfe  inc     edi
0x1400cbc00  inc     r14d
0x1400cbc03  jmp     short loc_1400CBB8E
0x1400cbc05  call    cs:__imp_GetLastError
0x1400cbc0c  nop     dword ptr [rax+rax+00h]
0x1400cbc11  test    eax, eax
0x1400cbc13  jle     short loc_1400CBC1D
0x1400cbc15  movzx   eax, ax
0x1400cbc18  or      eax, 80070000h
0x1400cbc1d  mov     edx, eax
0x1400cbc1f  mov     rcx, rsi
0x1400cbc22  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbc27  mov     byte ptr [rsi+8], 1
0x1400cbc2b  xor     ebx, ebx
0x1400cbc2d  test    edi, edi
0x1400cbc2f  jz      short loc_1400CBC93
0x1400cbc31  or      r14d, 0FFFFFFFFh
0x1400cbc35  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cbc3a  call    cs:__imp_ResumeThread
0x1400cbc41  nop     dword ptr [rax+rax+00h]
0x1400cbc46  cmp     eax, r14d
0x1400cbc49  jnz     short loc_1400CBC71
0x1400cbc4b  call    cs:__imp_GetLastError
0x1400cbc52  nop     dword ptr [rax+rax+00h]
0x1400cbc57  test    eax, eax
0x1400cbc59  jle     short loc_1400CBC63
0x1400cbc5b  movzx   eax, ax
0x1400cbc5e  or      eax, 80070000h
0x1400cbc63  mov     edx, eax
0x1400cbc65  mov     rcx, rsi
0x1400cbc68  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbc6d  mov     byte ptr [rsi+8], 1
0x1400cbc71  inc     ebx
0x1400cbc73  cmp     ebx, edi
0x1400cbc75  jb      short loc_1400CBC35
0x1400cbc77  mov     r9d, r14d; dwMilliseconds
0x1400cbc7a  mov     r8d, 1; bWaitAll
0x1400cbc80  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cbc85  mov     ecx, edi; nCount
0x1400cbc87  call    cs:__imp_WaitForMultipleObjects
0x1400cbc8e  nop     dword ptr [rax+rax+00h]
0x1400cbc93  mov     edx, [rsi+1Ch]
0x1400cbc96  nop
0x1400cbc97  lea     rcx, [rbp+2E0h+var_190]
0x1400cbc9e  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cbca3  mov     ebx, [rsi+1Ch]
0x1400cbca6  nop
0x1400cbca7  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cbcae  mov     edx, 8; unsigned __int64
0x1400cbcb3  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbcb7  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbcbb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cbcc0  nop
0x1400cbcc1  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbcc8  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cbccd  mov     eax, ebx
0x1400cbccf  mov     rcx, [rbp+2E0h+var_40]
0x1400cbcd6  xor     rcx, rsp; StackCookie
0x1400cbcd9  call    __security_check_cookie
0x1400cbcde  add     rsp, 3B8h
0x1400cbce5  pop     r15
0x1400cbce7  pop     r14
0x1400cbce9  pop     rdi
0x1400cbcea  pop     rsi
0x1400cbceb  pop     rbx
0x1400cbcec  pop     rbp
0x1400cbced  retn
```
