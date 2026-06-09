# Execution::ExecutionServices::Stop(void)

- ea: `0x18009acc0`
- end: `0x18009addd`
- name: `?Stop@ExecutionServices@Execution@@UEAAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(Execution::ExecutionServices *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010a34`
- `0x18004841c`
- `0x18005b37c`
- `0x18009acc0`
- `0x18009b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ad5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ad5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ad88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ad88`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009adb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009adb3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009ad74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009ad74`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18009ad95`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18009ad95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009ad9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009ad9d`

## pseudocode

```c
__int64 __fastcall Execution::ExecutionServices::Stop(Execution::ExecutionServices *this)
{
  _QWORD *v2; // rax
  unsigned int v3; // ebx
  DWORD ThreadId; // ebx
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  v2 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    *v2 = &Execution::ExecutionServices::WorkerThreadItem::`vftable';
    v2[2] = 0;
    v2[3] = 0;
    v2[4] = 0;
    *((_DWORD *)v2 + 10) = 0;
    v2[6] = 0;
    v2[7] = 0;
    *((_DWORD *)v2 + 16) = 0;
    *((_DWORD *)v2 + 17) = 1;
  }
  Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>::Attach(&v6, v2);
  if ( v6 )
  {
    *(_DWORD *)(v6 + 8) = 6;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::push_back(
      (char *)this + 64,
      &v6);
    SetEvent(*((HANDLE *)this + 15));
    *((_DWORD *)this + 34) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    ThreadId = GetThreadId(*((HANDLE *)this + 16));
    if ( GetCurrentThreadId() == ThreadId || !WaitForSingleObject(*((HANDLE *)this + 16), 0xEA60u) )
      v3 = 0;
    else
      v3 = -2147467259;
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v6);
  return v3;
}

```

## disassembly

```asm
0x18009acc0  mov     [rsp+arg_0], rbx
0x18009acc5  push    rdi
0x18009acc6  sub     rsp, 20h
0x18009acca  mov     rdi, rcx
0x18009accd  mov     [rsp+28h+arg_8], 0
0x18009acd6  mov     ecx, 48h ; 'H'; unsigned __int64
0x18009acdb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009ace2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009ace7  test    rax, rax
0x18009acea  jz      short loc_18009AD33
0x18009acec  lea     rcx, ??_7WorkerThreadItem@ExecutionServices@Execution@@6B@; const Execution::ExecutionServices::WorkerThreadItem::`vftable'
0x18009acf3  mov     [rax], rcx
0x18009acf6  mov     qword ptr [rax+10h], 0
0x18009acfe  mov     qword ptr [rax+18h], 0
0x18009ad06  mov     qword ptr [rax+20h], 0
0x18009ad0e  mov     dword ptr [rax+28h], 0
0x18009ad15  mov     qword ptr [rax+30h], 0
0x18009ad1d  mov     qword ptr [rax+38h], 0
0x18009ad25  mov     dword ptr [rax+40h], 0
0x18009ad2c  mov     dword ptr [rax+44h], 1
0x18009ad33  mov     rdx, rax
0x18009ad36  lea     rcx, [rsp+28h+arg_8]
0x18009ad3b  call    ?Attach@?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@QEAAXPEAVWorkerThreadItem@ExecutionServices@Execution@@@Z; Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>::Attach(Execution::ExecutionServices::WorkerThreadItem *)
0x18009ad40  mov     rax, [rsp+28h+arg_8]
0x18009ad45  test    rax, rax
0x18009ad48  jnz     short loc_18009AD51
0x18009ad4a  mov     ebx, 8007000Eh
0x18009ad4f  jmp     short loc_18009ADC6
0x18009ad51  lea     rcx, [rdi+10h]; lpCriticalSection
0x18009ad55  mov     dword ptr [rax+8], 6
0x18009ad5c  call    cs:__imp_EnterCriticalSection
0x18009ad62  lea     rcx, [rdi+40h]
0x18009ad66  lea     rdx, [rsp+28h+arg_8]
0x18009ad6b  call    ?push_back@?$list@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@@utl@@@utl@@QEAA_NAEBV?$ComPtr@VWorkerThreadItem@ExecutionServices@Execution@@@WRL@Microsoft@@@Z; utl::list<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>,utl::allocator<Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem>>>::push_back(Microsoft::WRL::ComPtr<Execution::ExecutionServices::WorkerThreadItem> const &)
0x18009ad70  mov     rcx, [rdi+78h]; hEvent
0x18009ad74  call    cs:__imp_SetEvent
0x18009ad7a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18009ad7e  mov     dword ptr [rdi+88h], 0
0x18009ad88  call    cs:__imp_LeaveCriticalSection
0x18009ad8e  mov     rcx, [rdi+80h]; Thread
0x18009ad95  call    cs:__imp_GetThreadId
0x18009ad9b  mov     ebx, eax
0x18009ad9d  call    cs:__imp_GetCurrentThreadId
0x18009ada3  cmp     eax, ebx
0x18009ada5  jz      short loc_18009ADC4
0x18009ada7  mov     rcx, [rdi+80h]; hHandle
0x18009adae  mov     edx, 0EA60h; dwMilliseconds
0x18009adb3  call    cs:__imp_WaitForSingleObject
0x18009adb9  test    eax, eax
0x18009adbb  jz      short loc_18009ADC4
0x18009adbd  mov     ebx, 80004005h
0x18009adc2  jmp     short loc_18009ADC6
0x18009adc4  xor     ebx, ebx
0x18009adc6  lea     rcx, [rsp+28h+arg_8]
0x18009adcb  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x18009add0  mov     eax, ebx
0x18009add2  mov     rbx, [rsp+28h+arg_0]
0x18009add7  add     rsp, 20h
0x18009addb  pop     rdi
0x18009addc  retn
```
