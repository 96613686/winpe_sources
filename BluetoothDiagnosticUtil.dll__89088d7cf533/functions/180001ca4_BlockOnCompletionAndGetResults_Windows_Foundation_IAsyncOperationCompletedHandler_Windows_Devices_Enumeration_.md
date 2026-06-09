# BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Devices::Enumeration::IDeviceInformation>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceInformation>>,tagCOWAIT_FLAGS,void *)

- ea: `0x180001ca4`
- end: `0x180001cfa`
- name: `??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@UIDeviceInformation@Enumeration@Devices@3@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIDeviceInformation@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b08`
- `0x180004210`

## callees

- `0x180001ca4`
- `0x180002df8`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Devices::Enumeration::IDeviceInformation>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        __int64 *a2,
        __int64 a3)
{
  __int64 v5; // rcx
  __int64 result; // rax

  v5 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  result = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(
             a1,
             (HRESULT)a2,
             a3);
  if ( (int)result >= 0 )
    return ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))(*a1)[8])(a1, a2);
  return result;
}

```

## disassembly

```asm
0x180001ca4  mov     [rsp+arg_0], rbx
0x180001ca9  push    rdi
0x180001caa  sub     rsp, 20h
0x180001cae  mov     rbx, rdx
0x180001cb1  mov     rdi, rcx
0x180001cb4  mov     rcx, [rdx]
0x180001cb7  test    rcx, rcx
0x180001cba  jz      short loc_180001CD0
0x180001cbc  mov     qword ptr [rdx], 0
0x180001cc3  mov     rax, [rcx]
0x180001cc6  mov     rax, [rax+10h]
0x180001cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ccf  nop
0x180001cd0  mov     rcx, rdi
0x180001cd3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,void *)
0x180001cd8  test    eax, eax
0x180001cda  js      short loc_180001CEE
0x180001cdc  mov     rax, [rdi]
0x180001cdf  mov     rdx, rbx
0x180001ce2  mov     rcx, rdi
0x180001ce5  mov     rax, [rax+40h]
0x180001ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cee  mov     rbx, [rsp+28h+arg_0]
0x180001cf3  add     rsp, 20h
0x180001cf7  pop     rdi
0x180001cf8  retn
```
