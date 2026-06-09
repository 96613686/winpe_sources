# ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbRestoreFlags_&_

- ea: `0x1400cbcf8`
- end: `0x1400cbf1a`
- name: `ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository___&_enum_VmbRestoreFlags_&_`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400cb26c`

## callees

- `0x1400315a8`
- `0x14005159c`
- `0x1400ca820`
- `0x1400cbcf8`
- `0x1400cbf20`
- `0x140132940`
- `0x140132970`
- `0x1401335fc`
- `0x1401339fc`
- `0x140281080`
- `0x14028382c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cbe73`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbe63`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400cbe63`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbde3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400cbde3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbeb0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400cbeb0`

## pseudocode

```c
__int64 __fastcall ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::ExecuteVDevTransitionsWithManagedThreads_VmRepository_____enum_VmbRestoreFlags___(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  DWORD v8; // edi
  int i; // esi
  char *v10; // rcx
  signed int LastError; // eax
  __int64 v12; // rbx
  signed int v13; // eax
  unsigned int v14; // ebx
  HANDLE Thread; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Parameter[3]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hThread[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v20[336]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v20, 0, sizeof(v20));
  VmPerf::StartRelatedActivity_VmWorkerTrace::ExecuteVDevTransitionsParallel__GUID___((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v20);
  *(_BYTE *)(a1 + 8) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  Parameter[0] = a1;
  Parameter[1] = a4;
  Parameter[2] = a3;
  `eh vector constructor iterator'(
    v19,
    8u,
    0x20u,
    (void (*)(void *))HyperVGuestLoader::IsolatedVm::FileFormat::DeviceTreeParameter::DeviceTreeParameter,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  memset_0(hThread, 0, sizeof(hThread));
  v8 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 36); ++i )
  {
    Thread = CreateThread(0, 0, lambda_c545ec023c3ec298a21eb2d3e6fb5d2d_::_lambda_invoker_cdecl_, Parameter, 4u, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v19[i],
      &Thread);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    v10 = (char *)v19[i];
    if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
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
    hThread[i] = v10;
    ++v8;
  }
  v12 = 0;
  if ( v8 )
  {
    do
    {
      if ( ResumeThread(hThread[v12]) == -1 )
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(a1, (unsigned int)v13);
        *(_BYTE *)(a1 + 8) = 1;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < v8 );
    WaitForMultipleObjects(v8, hThread, 1, 0xFFFFFFFF);
  }
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, *(unsigned int *)(a1 + 28));
  v14 = *(_DWORD *)(a1 + 28);
  `eh vector destructor iterator'(
    v19,
    8u,
    0x20u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
  VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel((VmWorkerTrace::ExecuteVDevTransitionsParallel *)v20);
  return v14;
}

```

## disassembly

```asm
0x1400cbcf8  push    rbp
0x1400cbcfa  push    rbx
0x1400cbcfb  push    rsi
0x1400cbcfc  push    rdi
0x1400cbcfd  push    r14
0x1400cbcff  push    r15
0x1400cbd01  lea     rbp, [rsp-2B8h]
0x1400cbd09  sub     rsp, 3B8h
0x1400cbd10  mov     rax, cs:__security_cookie
0x1400cbd17  xor     rax, rsp
0x1400cbd1a  mov     [rbp+2E0h+var_40], rax
0x1400cbd21  mov     rdi, r9
0x1400cbd24  mov     rsi, r8
0x1400cbd27  mov     rbx, rdx
0x1400cbd2a  mov     r14, rcx
0x1400cbd2d  xor     edx, edx; Val
0x1400cbd2f  mov     r8d, 150h; Size
0x1400cbd35  lea     rcx, [rbp+2E0h+var_190]; void *
0x1400cbd3c  call    memset_0
0x1400cbd41  lea     r8, [r14+60h]
0x1400cbd45  lea     rdx, [r14+50h]
0x1400cbd49  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbd50  call    VmPerf__StartRelatedActivity_VmWorkerTrace__ExecuteVDevTransitionsParallel__GUID___
0x1400cbd55  xor     eax, eax
0x1400cbd57  xchg    al, [r14+8]
0x1400cbd5b  xor     eax, eax
0x1400cbd5d  xchg    eax, [r14+1Ch]
0x1400cbd61  mov     dword ptr [r14+20h], 0
0x1400cbd69  mov     [r14+38h], rbx
0x1400cbd6d  mov     [rsp+3E0h+Parameter], r14
0x1400cbd72  mov     [rsp+3E0h+var_3A0], rdi
0x1400cbd77  mov     [rsp+3E0h+var_398], rsi
0x1400cbd7c  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1400cbd83  mov     qword ptr [rsp+3E0h+dwCreationFlags], r15; void (*)(void *)
0x1400cbd88  lea     r9, ??0DeviceTreeParameter@FileFormat@IsolatedVm@HyperVGuestLoader@@QEAA@XZ; void (*)(void *)
0x1400cbd8f  mov     edx, 8; unsigned __int64
0x1400cbd94  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbd98  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbd9c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400cbda1  nop
0x1400cbda2  xor     edx, edx; Val
0x1400cbda4  mov     r8d, 100h; Size
0x1400cbdaa  lea     rcx, [rsp+3E0h+hThread]; void *
0x1400cbdaf  call    memset_0
0x1400cbdb4  xor     edi, edi
0x1400cbdb6  xor     esi, esi
0x1400cbdb8  cmp     esi, [r14+24h]
0x1400cbdbc  jge     loc_1400CBE55
0x1400cbdc2  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x1400cbdcb  mov     [rsp+3E0h+dwCreationFlags], 4; dwCreationFlags
0x1400cbdd3  lea     r9, [rsp+3E0h+Parameter]; lpParameter
0x1400cbdd8  lea     r8, _lambda_c545ec023c3ec298a21eb2d3e6fb5d2d____lambda_invoker_cdecl_; lpStartAddress
0x1400cbddf  xor     edx, edx; dwStackSize
0x1400cbde1  xor     ecx, ecx; lpThreadAttributes
0x1400cbde3  call    cs:__imp_CreateThread
0x1400cbdea  nop     dword ptr [rax+rax+00h]
0x1400cbdef  mov     [rsp+3E0h+var_3B0], rax
0x1400cbdf4  movsxd  r15, esi
0x1400cbdf7  lea     rbx, [rbp+2E0h+var_290]
0x1400cbdfb  lea     rbx, [rbx+r15*8]
0x1400cbdff  lea     rdx, [rsp+3E0h+var_3B0]
0x1400cbe04  mov     rcx, rbx
0x1400cbe07  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400cbe0c  lea     rcx, [rsp+3E0h+var_3B0]
0x1400cbe11  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400cbe16  mov     rcx, [rbx]
0x1400cbe19  lea     rax, [rcx-1]
0x1400cbe1d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400cbe21  ja      short loc_1400CBE2E
0x1400cbe23  mov     [rsp+r15*8+3E0h+hThread], rcx
0x1400cbe28  inc     edi
0x1400cbe2a  inc     esi
0x1400cbe2c  jmp     short loc_1400CBDB8
0x1400cbe2e  call    cs:__imp_GetLastError
0x1400cbe35  nop     dword ptr [rax+rax+00h]
0x1400cbe3a  test    eax, eax
0x1400cbe3c  jle     short loc_1400CBE46
0x1400cbe3e  movzx   eax, ax
0x1400cbe41  or      eax, 80070000h
0x1400cbe46  mov     edx, eax
0x1400cbe48  mov     rcx, r14
0x1400cbe4b  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbe50  mov     byte ptr [r14+8], 1
0x1400cbe55  xor     ebx, ebx
0x1400cbe57  test    edi, edi
0x1400cbe59  jz      short loc_1400CBEBC
0x1400cbe5b  or      esi, 0FFFFFFFFh
0x1400cbe5e  mov     rcx, [rsp+rbx*8+3E0h+hThread]; hThread
0x1400cbe63  call    cs:__imp_ResumeThread
0x1400cbe6a  nop     dword ptr [rax+rax+00h]
0x1400cbe6f  cmp     eax, esi
0x1400cbe71  jnz     short loc_1400CBE9A
0x1400cbe73  call    cs:__imp_GetLastError
0x1400cbe7a  nop     dword ptr [rax+rax+00h]
0x1400cbe7f  test    eax, eax
0x1400cbe81  jle     short loc_1400CBE8B
0x1400cbe83  movzx   eax, ax
0x1400cbe86  or      eax, 80070000h
0x1400cbe8b  mov     edx, eax
0x1400cbe8d  mov     rcx, r14
0x1400cbe90  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x1400cbe95  mov     byte ptr [r14+8], 1
0x1400cbe9a  inc     ebx
0x1400cbe9c  cmp     ebx, edi
0x1400cbe9e  jb      short loc_1400CBE5E
0x1400cbea0  mov     r9d, esi; dwMilliseconds
0x1400cbea3  mov     r8d, 1; bWaitAll
0x1400cbea9  lea     rdx, [rsp+3E0h+hThread]; lpHandles
0x1400cbeae  mov     ecx, edi; nCount
0x1400cbeb0  call    cs:__imp_WaitForMultipleObjects
0x1400cbeb7  nop     dword ptr [rax+rax+00h]
0x1400cbebc  mov     edx, [r14+1Ch]
0x1400cbec0  nop
0x1400cbec1  lea     rcx, [rbp+2E0h+var_190]
0x1400cbec8  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400cbecd  mov     ebx, [r14+1Ch]
0x1400cbed1  nop
0x1400cbed2  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1400cbed9  mov     edx, 8; unsigned __int64
0x1400cbede  lea     r8d, [rdx+18h]; unsigned __int64
0x1400cbee2  lea     rcx, [rbp+2E0h+var_290]; void *
0x1400cbee6  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400cbeeb  nop
0x1400cbeec  lea     rcx, [rbp+2E0h+var_190]; this
0x1400cbef3  call    ??1ExecuteVDevTransitionsParallel@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::ExecuteVDevTransitionsParallel::~ExecuteVDevTransitionsParallel(void)
0x1400cbef8  mov     eax, ebx
0x1400cbefa  mov     rcx, [rbp+2E0h+var_40]
0x1400cbf01  xor     rcx, rsp; StackCookie
0x1400cbf04  call    __security_check_cookie
0x1400cbf09  add     rsp, 3B8h
0x1400cbf10  pop     r15
0x1400cbf12  pop     r14
0x1400cbf14  pop     rdi
0x1400cbf15  pop     rsi
0x1400cbf16  pop     rbx
0x1400cbf17  pop     rbp
0x1400cbf18  retn
```
