# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *>>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x180026cd0`
- end: `0x180026d96`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@23@V?$CMarshaledInterfaceResult@U?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180026cd0`
- `0x1800281ac`
- `0x180028578`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026d07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026d07`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180026d47`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180026d47`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *>>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_5:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      a1,
      v2);
    return v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 336) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 328),
         *(unsigned int *)(a1 + 332),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *>>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
      a1 - 8,
      1,
      v2);
    goto LABEL_5;
  }
  return v2;
}

```

## disassembly

```asm
0x180026cd0  mov     [rsp+arg_0], rbx
0x180026cd5  mov     [rsp+arg_8], rsi
0x180026cda  push    rdi
0x180026cdb  sub     rsp, 30h
0x180026cdf  mov     rdi, rcx
0x180026ce2  xor     r8d, r8d
0x180026ce5  mov     rcx, [rcx+100h]
0x180026cec  xor     edx, edx
0x180026cee  lea     r9, [rdi+118h]
0x180026cf5  mov     rax, [rcx]
0x180026cf8  mov     rax, [rax+8]
0x180026cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d01  mov     ebx, eax
0x180026d03  test    eax, eax
0x180026d05  js      short loc_180026D6C
0x180026d07  call    cs:__imp_GetCurrentThreadId
0x180026d0d  lea     rdx, [rdi+0C8h]
0x180026d14  mov     [rsp+38h+var_10], 0
0x180026d1d  lea     rcx, [rdi-8]
0x180026d21  mov     [rdi+150h], eax
0x180026d27  neg     rcx
0x180026d2a  mov     ecx, [rdi+148h]
0x180026d30  sbb     r8, r8
0x180026d33  xor     r9d, r9d
0x180026d36  and     r8, rdx
0x180026d39  mov     edx, [rdi+14Ch]
0x180026d3f  mov     [rsp+38h+var_18], r8
0x180026d44  mov     r8d, eax
0x180026d47  call    cs:__imp_SHTaskPoolQueueTask
0x180026d4d  mov     ebx, eax
0x180026d4f  test    eax, eax
0x180026d51  jns     short loc_180026D76
0x180026d53  mov     eax, [rdi+0F8h]
0x180026d59  test    eax, eax
0x180026d5b  jnz     short loc_180026D88
0x180026d5d  mov     r8d, ebx
0x180026d60  lea     edx, [rax+1]
0x180026d63  lea     rcx, [rdi-8]
0x180026d67  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@23@V?$CMarshaledInterfaceResult@U?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *>>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x180026d6c  mov     edx, ebx
0x180026d6e  mov     rcx, rdi
0x180026d71  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180026d76  mov     rsi, [rsp+38h+arg_8]
0x180026d7b  mov     eax, ebx
0x180026d7d  mov     rbx, [rsp+38h+arg_0]
0x180026d82  add     rsp, 30h
0x180026d86  pop     rdi
0x180026d87  retn
0x180026d88  mov     edx, ebx
0x180026d8a  mov     rcx, rdi
0x180026d8d  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180026d92  xor     ebx, ebx
0x180026d94  jmp     short loc_180026D76
```
