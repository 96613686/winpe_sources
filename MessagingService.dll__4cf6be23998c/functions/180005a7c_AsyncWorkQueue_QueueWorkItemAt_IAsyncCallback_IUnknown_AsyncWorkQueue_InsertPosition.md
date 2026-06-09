# AsyncWorkQueue::_QueueWorkItemAt(IAsyncCallback *,IUnknown *,AsyncWorkQueue::InsertPosition)

- ea: `0x180005a7c`
- end: `0x180005bce`
- name: `?_QueueWorkItemAt@AsyncWorkQueue@@AEAAJPEAUIAsyncCallback@@PEAUIUnknown@@W4InsertPosition@1@@Z`
- size: `338`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005630`

## callees

- `0x180003da4`
- `0x180005a7c`
- `0x180005c68`
- `0x18000a8e0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005aec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005aec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005afb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005afb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b94`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005b84`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180005b84`

## pseudocode

```c
__int64 __fastcall AsyncWorkQueue::_QueueWorkItemAt(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+28h] [rbp-10h]
  char v9; // [rsp+40h] [rbp+8h] BYREF

  if ( !*(_QWORD *)(a1 + 96) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v7 = a2;
  }
  if ( a3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    v8 = a3;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( *(_DWORD *)(a1 + 92) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    if ( a3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
    ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(&v7);
    return 2147943623LL;
  }
  else if ( *(_QWORD *)((__int64 (__fastcall *)(__int64, char *, __int64, __int64 *))utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::insert)(
                         a1 + 56,
                         &v9,
                         a1 + 56,
                         &v7) )
  {
    if ( !*(_DWORD *)(a1 + 88) )
    {
      SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 96));
      *(_DWORD *)(a1 + 88) = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(&v7);
    return 0;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(&v7);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005a7c  mov     [rsp+arg_8], rbx
0x180005a81  mov     [rsp+arg_10], rsi
0x180005a86  push    rdi
0x180005a87  sub     rsp, 30h
0x180005a8b  mov     rbx, r8
0x180005a8e  mov     rsi, rdx
0x180005a91  mov     rdi, rcx
0x180005a94  cmp     qword ptr [rcx+60h], 0
0x180005a99  jnz     short loc_180005AA1
0x180005a9b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005aa0  nop
0x180005aa1  mov     [rsp+38h+var_18], 0
0x180005aaa  mov     [rsp+38h+var_10], 0
0x180005ab3  test    rsi, rsi
0x180005ab6  jz      short loc_180005ACC
0x180005ab8  mov     rax, [rsi]
0x180005abb  mov     rcx, rsi
0x180005abe  mov     rax, [rax+8]
0x180005ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac7  mov     [rsp+38h+var_18], rsi
0x180005acc  test    rbx, rbx
0x180005acf  jz      short loc_180005AE5
0x180005ad1  mov     rax, [rbx]
0x180005ad4  mov     rcx, rbx
0x180005ad7  mov     rax, [rax+8]
0x180005adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae0  mov     [rsp+38h+var_10], rbx
0x180005ae5  lea     rsi, [rdi+10h]
0x180005ae9  mov     rcx, rsi; lpCriticalSection
0x180005aec  call    cs:__imp_EnterCriticalSection
0x180005af2  cmp     dword ptr [rdi+5Ch], 0
0x180005af6  jz      short loc_180005B2B
0x180005af8  mov     rcx, rsi; lpCriticalSection
0x180005afb  call    cs:__imp_LeaveCriticalSection
0x180005b01  test    rbx, rbx
0x180005b04  jz      short loc_180005B16
0x180005b06  mov     rax, [rbx]
0x180005b09  mov     rcx, rbx
0x180005b0c  mov     rax, [rax+10h]
0x180005b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b15  nop
0x180005b16  lea     rcx, [rsp+38h+var_18]
0x180005b1b  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x180005b20  nop
0x180005b21  mov     eax, 800704C7h
0x180005b26  jmp     loc_180005BBE
0x180005b2b  lea     rcx, [rdi+38h]
0x180005b2f  lea     r9, [rsp+38h+var_18]
0x180005b34  mov     r8, rcx
0x180005b37  lea     rdx, [rsp+38h+arg_0]
0x180005b3c  call    ?insert@?$list@UAsyncWorkItem@AsyncWorkQueue@@V?$allocator@UAsyncWorkItem@AsyncWorkQueue@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UAsyncWorkItem@AsyncWorkQueue@@@utl@@UAsyncWorkItem@AsyncWorkQueue@@@2@V?$_DlistConstIt@U?$_DlistNode@UAsyncWorkItem@AsyncWorkQueue@@@utl@@UAsyncWorkItem@AsyncWorkQueue@@@2@AEBUAsyncWorkItem@AsyncWorkQueue@@@Z; utl::list<AsyncWorkQueue::AsyncWorkItem,utl::allocator<AsyncWorkQueue::AsyncWorkItem>>::insert(utl::_DlistConstIt<utl::_DlistNode<AsyncWorkQueue::AsyncWorkItem>,AsyncWorkQueue::AsyncWorkItem>,AsyncWorkQueue::AsyncWorkItem const &)
0x180005b41  cmp     qword ptr [rax], 0
0x180005b45  jnz     short loc_180005B79
0x180005b47  mov     rcx, rsi; lpCriticalSection
0x180005b4a  call    cs:__imp_LeaveCriticalSection
0x180005b50  mov     rcx, [rsp+38h+var_10]
0x180005b55  test    rcx, rcx
0x180005b58  jz      short loc_180005B67
0x180005b5a  mov     rax, [rcx]
0x180005b5d  mov     rax, [rax+10h]
0x180005b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b66  nop
0x180005b67  lea     rcx, [rsp+38h+var_18]
0x180005b6c  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x180005b71  nop
0x180005b72  mov     eax, 8007000Eh
0x180005b77  jmp     short loc_180005BBE
0x180005b79  mov     eax, [rdi+58h]
0x180005b7c  test    eax, eax
0x180005b7e  jnz     short loc_180005B91
0x180005b80  mov     rcx, [rdi+60h]; pwk
0x180005b84  call    cs:__imp_SubmitThreadpoolWork
0x180005b8a  mov     dword ptr [rdi+58h], 1
0x180005b91  mov     rcx, rsi; lpCriticalSection
0x180005b94  call    cs:__imp_LeaveCriticalSection
0x180005b9a  mov     rcx, [rsp+38h+var_10]
0x180005b9f  test    rcx, rcx
0x180005ba2  jz      short loc_180005BB1
0x180005ba4  mov     rax, [rcx]
0x180005ba7  mov     rax, [rax+10h]
0x180005bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb0  nop
0x180005bb1  lea     rcx, [rsp+38h+var_18]
0x180005bb6  call    ??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)
0x180005bbb  nop
0x180005bbc  xor     eax, eax
0x180005bbe  mov     rbx, [rsp+38h+arg_8]
0x180005bc3  mov     rsi, [rsp+38h+arg_10]
0x180005bc8  add     rsp, 30h
0x180005bcc  pop     rdi
0x180005bcd  retn
```
