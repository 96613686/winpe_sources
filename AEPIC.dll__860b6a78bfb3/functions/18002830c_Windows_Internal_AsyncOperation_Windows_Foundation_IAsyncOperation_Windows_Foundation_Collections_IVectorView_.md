# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *>>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x18002830c`
- end: `0x180028370`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@23@V?$CMarshaledInterfaceResult@U?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180028378`
- `0x180028578`

## callees

- `0x180025720`
- `0x18002830c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028346`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180028350`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180028350`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *>>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 344);
  *(_QWORD *)(a1 + 264) = 0;
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  return Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18002830c  mov     [rsp+arg_0], rbx
0x180028311  push    rdi
0x180028312  sub     rsp, 20h
0x180028316  mov     rdi, rcx
0x180028319  mov     rcx, [rcx+108h]
0x180028320  test    rcx, rcx
0x180028323  jz      short loc_180028335
0x180028325  mov     rax, [rcx]
0x180028328  mov     edx, 1
0x18002832d  mov     rax, [rax]
0x180028330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028335  mov     ebx, [rdi+158h]
0x18002833b  mov     qword ptr [rdi+108h], 0
0x180028346  call    cs:__imp_GetCurrentThreadId
0x18002834c  cmp     eax, ebx
0x18002834e  jz      short loc_180028356
0x180028350  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180028356  lock inc dword ptr [rdi+110h]
0x18002835d  lea     rcx, [rdi+8]
0x180028361  mov     rbx, [rsp+28h+arg_0]
0x180028366  add     rsp, 20h
0x18002836a  pop     rdi
0x18002836b  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
