# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180003c70`
- end: `0x180003c92`
- name: `?GetRuntimeClassName@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003ca0`
- `0x18000b5d0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003c82`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003c82`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = 0;
  RoOriginateError(2147483662LL);
  return 2147483662LL;
}

```

## disassembly

```asm
0x180003c70  sub     rsp, 28h
0x180003c74  mov     qword ptr [rdx], 0
0x180003c7b  mov     ecx, 8000000Eh
0x180003c80  xor     edx, edx
0x180003c82  call    cs:__imp_RoOriginateError
0x180003c88  mov     eax, 8000000Eh
0x180003c8d  add     rsp, 28h
0x180003c91  retn
```
