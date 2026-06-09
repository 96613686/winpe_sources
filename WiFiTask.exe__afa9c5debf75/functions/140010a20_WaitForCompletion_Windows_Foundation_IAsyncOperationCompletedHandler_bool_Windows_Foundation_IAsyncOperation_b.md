# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::Invoke(Windows::Foundation::IAsyncOperation<bool> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x140010a20`
- end: `0x140010a39`
- name: `?Invoke@FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@UEAAJ0W4AsyncStatus@34ABI@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140010a2c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140010a2c`

## pseudocode

```c
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::Invoke(
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
0x140010a20  sub     rsp, 28h
0x140010a24  mov     [rcx+30h], r8d
0x140010a28  mov     rcx, [rcx+38h]; hEvent
0x140010a2c  call    cs:__imp_SetEvent
0x140010a32  xor     eax, eax
0x140010a34  add     rsp, 28h
0x140010a38  retn
```
