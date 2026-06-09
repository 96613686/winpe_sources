# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::Invoke(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x180014d20`
- end: `0x180014d39`
- name: `?Invoke@FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@UEAAJ0W4AsyncStatus@34ABI@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014d2c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014d2c`

## pseudocode

```c
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::Invoke(
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
0x180014d20  sub     rsp, 28h
0x180014d24  mov     [rcx+30h], r8d
0x180014d28  mov     rcx, [rcx+38h]; hEvent
0x180014d2c  call    cs:__imp_SetEvent
0x180014d32  xor     eax, eax
0x180014d34  add     rsp, 28h
0x180014d38  retn
```
