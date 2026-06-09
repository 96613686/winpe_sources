# Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)

- ea: `0x180027680`
- end: `0x180027695`
- name: `?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027448`
- `0x18002769c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027688`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027688`

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
0x180027680  sub     rsp, 28h
0x180027684  mov     rcx, [rcx+8]; hSCObject
0x180027688  call    cs:__imp_CloseServiceHandle
0x18002768e  mov     al, 1
0x180027690  add     rsp, 28h
0x180027694  retn
```
