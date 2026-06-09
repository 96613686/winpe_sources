# ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags_&_

- ea: `0x1400cb04c`
- end: `0x1400cb263`
- name: `ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags_&_`
- size: `535`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cae58`

## callees

- `0x1400315a8`
- `0x14005159c`
- `0x1400ca820`
- `0x1400cb04c`
- `0x1400cbf20`
- `0x140132940`
- `0x140132970`
- `0x1401335fc`
- `0x1401339fc`
- `0x140281080`
- `0x14028382c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb1bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb1bf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb1ae`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cb1ae`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb12d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cb12d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb1fb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cb1fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_85c9e02f24e13dfa4db09b9da0195f41___::ExecuteVDevTransitionsWithManagedThreads_enum_VmbResumeFlags___(
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
               (LPTHREAD_START_ROUTINE)lambda_664edb7134184b7e2576fb6f05eaacc8_::_lambda_invoker_cdecl_,
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
0x1400cb04c  push    rbp
0x1400cb04e  push    rbx
0x1400cb04f  push    rsi
0x1400cb050  push    rdi
0x1400cb051  push    r14
0x1400cb053  push    r15
0x1400cb055  lea     rbp, [rsp-2B8h]
0x1400cb05d  sub     rsp, 3B8h
0x1400cb064  mov     rax, cs:__security_cookie
0x1400cb06b  xor     rax, rsp
0x1400cb06e  mov     [rbp+2E0h+var_40], rax
0x1400cb075  mov     rdi, r8
0x1400cb078  mov     rbx, rdx
0x1400cb07b  mov     rsi, rcx
0x1400cb07e  xor     edx, edx; Val
0x1400cb080  mov     r8d, 150h; Size
0x1400cb086  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cb08d  call    memset_0
0x1400cb092  lea     r8, [rsi+60h]
0x1400cb096  lea     rdx, [rsi+50h]
0x1400cb09a  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb0a1  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cb0a6  xor     eax, eax
0x1400cb0a8  xchg    al, [rsi+8]
0x1400cb0ab  xor     eax, eax
0x1400cb0ad  xchg    eax, [rsi+1Ch]
0x1400cb0b0  mov     dword ptr [rsi+20h], 0
0x1400cb0b7  mov     [rsi+38h], rbx
0x1400cb0bb  mov     [rsp+3E0h+Parameter], rsi
0x1400cb0c0  mov     [rsp+3E0h+var_3A0], rdi
0x1400cb0c5  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cb0cc  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cb0d1  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cb0d8  mov     edx, 8; unsigned __int64
0x1400cb0dd  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb0e1  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb0e5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cb0ea  nop
0x1400cb0eb  xor     edx, edx; Val
0x1400cb0ed  mov     r8d, 100h; Size
0x1400cb0f3  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cb0f8  call    memset_0
0x1400cb0fd  xor     edi, edi
0x1400cb0ff  xor     r14d, r14d
0x1400cb102  cmp     r14d, [rsi+24h]
0x1400cb106  jge     loc_1400CB19F
0x1400cb10c  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cb115  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cb11d  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cb122  lea     r8, _lambda_664edb7134184b7e2576fb6f05eaacc8____lambda_invoker_cdecl_; lpStartAddress
0x1400cb129  xor     edx, edx; dwStackSize
0x1400cb12b  xor     ecx, ecx; lpThreadAttributes
0x1400cb12d  call    cs:__imp_CreateThread
0x1400cb134  nop     dword ptr [rax+rax+00h]
0x1400cb139  mov     [rsp+3E0h+var_3B0], rax
0x1400cb13e  movsxd  r15, r14d
0x1400cb141  lea     rbx, [rbp+2E0h+var_290]
0x1400cb145  lea     rbx, [rbx+r15*8]
0x1400cb149  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cb14e  mov     rcx, rbx
0x1400cb151  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cb156  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cb15b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cb160  mov     rcx, [rbx]
0x1400cb163  lea     rax, [rcx-1]
0x1400cb167  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cb16b  ja      short loc_1400CB179
0x1400cb16d  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cb172  inc     edi
0x1400cb174  inc     r14d
0x1400cb177  jmp     short loc_1400CB102
0x1400cb179  call    cs:__imp_GetLastError
0x1400cb180  nop     dword ptr [rax+rax+00h]
0x1400cb185  test    eax, eax
0x1400cb187  jle     short loc_1400CB191
0x1400cb189  movzx   eax, ax
0x1400cb18c  or      eax, 80070000h
0x1400cb191  mov     edx, eax
0x1400cb193  mov     rcx, rsi
0x1400cb196  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb19b  mov     byte ptr [rsi+8], 1
0x1400cb19f  xor     ebx, ebx
0x1400cb1a1  test    edi, edi
0x1400cb1a3  jz      short loc_1400CB207
0x1400cb1a5  or      r14d, 0FFFFFFFFh
0x1400cb1a9  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cb1ae  call    cs:__imp_ResumeThread
0x1400cb1b5  nop     dword ptr [rax+rax+00h]
0x1400cb1ba  cmp     eax, r14d
0x1400cb1bd  jnz     short loc_1400CB1E5
0x1400cb1bf  call    cs:__imp_GetLastError
0x1400cb1c6  nop     dword ptr [rax+rax+00h]
0x1400cb1cb  test    eax, eax
0x1400cb1cd  jle     short loc_1400CB1D7
0x1400cb1cf  movzx   eax, ax
0x1400cb1d2  or      eax, 80070000h
0x1400cb1d7  mov     edx, eax
0x1400cb1d9  mov     rcx, rsi
0x1400cb1dc  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cb1e1  mov     byte ptr [rsi+8], 1
0x1400cb1e5  inc     ebx
0x1400cb1e7  cmp     ebx, edi
0x1400cb1e9  jb      short loc_1400CB1A9
0x1400cb1eb  mov     r9d, r14d; dwMilliseconds
0x1400cb1ee  mov     r8d, 1; bWaitAll
0x1400cb1f4  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cb1f9  mov     ecx, edi; nCount
0x1400cb1fb  call    cs:__imp_WaitForMultipleObjects
0x1400cb202  nop     dword ptr [rax+rax+00h]
0x1400cb207  mov     edx, [rsi+1Ch]
0x1400cb20a  nop
0x1400cb20b  lea     rcx, [rbp+2E0h+var_190]
0x1400cb212  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cb217  mov     ebx, [rsi+1Ch]
0x1400cb21a  nop
0x1400cb21b  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cb222  mov     edx, 8; unsigned __int64
0x1400cb227  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cb22b  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cb22f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cb234  nop
0x1400cb235  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cb23c  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cb241  mov     eax, ebx
0x1400cb243  mov     rcx, [rbp+2E0h+var_40]
0x1400cb24a  xor     rcx, rsp; StackCookie
0x1400cb24d  call    __security_check_cookie
0x1400cb252  add     rsp, 3B8h
0x1400cb259  pop     r15
0x1400cb25b  pop     r14
0x1400cb25d  pop     rdi
0x1400cb25e  pop     rsi
0x1400cb25f  pop     rbx
0x1400cb260  pop     rbp
0x1400cb261  retn
```
