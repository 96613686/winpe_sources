# Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180003c60`
- end: `0x180003c82`
- name: `?GetRuntimeClassName@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003c90`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003c72`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003c72`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = 0;
  RoOriginateError(2147483662LL, 0);
  return 2147483662LL;
}

```

## disassembly

```asm
0x180003c60  sub     rsp, 28h
0x180003c64  mov     qword ptr [rdx], 0
0x180003c6b  mov     ecx, 8000000Eh
0x180003c70  xor     edx, edx
0x180003c72  call    cs:__imp_RoOriginateError
0x180003c78  mov     eax, 8000000Eh
0x180003c7d  add     rsp, 28h
0x180003c81  retn
```
