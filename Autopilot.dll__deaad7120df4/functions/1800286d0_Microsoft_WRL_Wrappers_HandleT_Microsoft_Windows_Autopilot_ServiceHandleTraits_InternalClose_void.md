# Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)

- ea: `0x1800286d0`
- end: `0x1800286ec`
- name: `?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `28`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028470`
- `0x1800286f4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800286d8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800286d8`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(
        __int64 a1)
{
  CloseServiceHandle(*(SC_HANDLE *)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x1800286d0  sub     rsp, 28h
0x1800286d4  mov     rcx, [rcx+8]; hSCObject
0x1800286d8  call    cs:__imp_CloseServiceHandle
0x1800286df  nop     dword ptr [rax+rax+00h]
0x1800286e4  mov     al, 1
0x1800286e6  add     rsp, 28h
0x1800286ea  retn
```
