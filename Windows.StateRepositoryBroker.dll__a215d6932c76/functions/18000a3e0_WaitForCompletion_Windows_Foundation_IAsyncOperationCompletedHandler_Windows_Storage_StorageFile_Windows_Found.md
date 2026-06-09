# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::Invoke(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x18000a3e0`
- end: `0x18000a3f9`
- name: `?Invoke@FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@UEAAJ0W4AsyncStatus@34ABI@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a3ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a3ec`

## pseudocode

```c
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::Invoke(
        __int64 a1,
        __int64 a2,
        int a3)
{
  *(_DWORD *)(a1 + 48) = a3;
  SetEvent(*(HANDLE *)(a1 + 56));
  return 0;
}

```

## disassembly

```asm
0x18000a3e0  sub     rsp, 28h
0x18000a3e4  mov     [rcx+30h], r8d
0x18000a3e8  mov     rcx, [rcx+38h]; hEvent
0x18000a3ec  call    cs:__imp_SetEvent
0x18000a3f2  xor     eax, eax
0x18000a3f4  add     rsp, 28h
0x18000a3f8  retn
```
