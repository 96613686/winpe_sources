# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vector deleting destructor'(uint)

- ea: `0x180004b20`
- end: `0x180004b9d`
- name: `??_EFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004b20`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004b82`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004b82`
- `KERNEL32!CloseHandle` at `0x180004b48`
- `KERNEL32!CloseHandle` at `0x180004b48`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>'::`2'::FTMEventDelegate::`vector deleting destructor'(
        void *a1,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)a1 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)a1 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CloseHandle(*((HANDLE *)a1 + 7));
  *((_DWORD *)a1 + 11) = -1073741823;
  v4 = *((_QWORD *)a1 + 4);
  if ( v4 )
  {
    *((_QWORD *)a1 + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004b20  mov     [rsp+arg_0], rbx
0x180004b25  push    rdi
0x180004b26  sub     rsp, 20h
0x180004b2a  mov     edi, edx
0x180004b2c  mov     rbx, rcx
0x180004b2f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>'}
0x180004b36  mov     [rcx], rax
0x180004b39  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180004b40  mov     [rcx+8], rax
0x180004b44  mov     rcx, [rcx+38h]; hObject
0x180004b48  call    cs:__imp_CloseHandle
0x180004b4f  nop     dword ptr [rax+rax+00h]
0x180004b54  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180004b5b  mov     rcx, [rbx+20h]
0x180004b5f  test    rcx, rcx
0x180004b62  jz      short loc_180004B79
0x180004b64  mov     qword ptr [rbx+20h], 0
0x180004b6c  mov     rax, [rcx]
0x180004b6f  mov     rax, [rax+10h]
0x180004b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b78  nop
0x180004b79  test    dil, 1
0x180004b7d  jz      short loc_180004B8E
0x180004b7f  mov     rcx, rbx
0x180004b82  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004b89  nop     dword ptr [rax+rax+00h]
0x180004b8e  mov     rax, rbx
0x180004b91  mov     rbx, [rsp+28h+arg_0]
0x180004b96  add     rsp, 20h
0x180004b9a  pop     rdi
0x180004b9b  retn
```
