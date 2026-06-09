# `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::Invoke(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x14000d4d0`
- end: `0x14000d4e9`
- name: `?Invoke@FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@UEAAJ0W4AsyncStatus@34ABI@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000d4dc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000d4dc`

## pseudocode

```c
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>'::`2'::FTMEventDelegate::Invoke(
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
0x14000d4d0  sub     rsp, 28h
0x14000d4d4  mov     [rcx+30h], r8d
0x14000d4d8  mov     rcx, [rcx+38h]; hEvent
0x14000d4dc  call    cs:__imp_SetEvent
0x14000d4e2  xor     eax, eax
0x14000d4e4  add     rsp, 28h
0x14000d4e8  retn
```
