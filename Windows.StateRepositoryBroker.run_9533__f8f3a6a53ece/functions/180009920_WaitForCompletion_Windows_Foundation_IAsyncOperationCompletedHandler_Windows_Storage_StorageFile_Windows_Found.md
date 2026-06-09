# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::~FTMEventDelegate(void)

- ea: `0x180009920`
- end: `0x18000995f`
- name: `??1FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAA@XZ`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800099c0`

## callees

- `0x18000539c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009942`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::~FTMEventDelegate(
        __int64 a1)
{
  *(_QWORD *)a1 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CloseHandle(*(HANDLE *)(a1 + 56));
  *(_DWORD *)(a1 + 44) = -1073741823;
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 32));
}

```

## disassembly

```asm
0x180009920  push    rbx
0x180009922  sub     rsp, 20h
0x180009926  mov     rbx, rcx
0x180009929  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x180009930  mov     [rcx], rax
0x180009933  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000993a  mov     [rcx+8], rax
0x18000993e  mov     rcx, [rcx+38h]; hObject
0x180009942  call    cs:__imp_CloseHandle
0x180009948  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000994f  lea     rcx, [rbx+20h]
0x180009953  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009958  nop
0x180009959  add     rsp, 20h
0x18000995d  pop     rbx
0x18000995e  retn
```
