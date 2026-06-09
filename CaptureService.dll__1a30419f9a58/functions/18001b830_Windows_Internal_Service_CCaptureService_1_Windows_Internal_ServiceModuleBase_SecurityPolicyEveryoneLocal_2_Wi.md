# Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)

- ea: `0x18001b830`
- end: `0x18001b86a`
- name: `?StopAsync@?$Service@VCCaptureService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b4b0`

## callees

- `0x18001b830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b863`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001b854`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001b854`

## pseudocode

```c
BOOL __fastcall Windows::Internal::Service<CCaptureService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(
        __int64 a1)
{
  if ( ((*(_DWORD *)(a1 + 20) - 1) & 0xFFFFFFFD) != 0 )
  {
    *(_DWORD *)(a1 + 20) = 3;
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(a1 + 8), (LPSERVICE_STATUS)(a1 + 16));
  }
  return SetEvent(*(HANDLE *)(a1 + 48));
}

```

## disassembly

```asm
0x18001b830  push    rbx
0x18001b832  sub     rsp, 20h
0x18001b836  lea     rdx, [rcx+10h]; lpServiceStatus
0x18001b83a  mov     rbx, rcx
0x18001b83d  mov     eax, [rdx+4]
0x18001b840  dec     eax
0x18001b842  test    eax, 0FFFFFFFDh
0x18001b847  jz      short loc_18001B85A
0x18001b849  mov     dword ptr [rcx+14h], 3
0x18001b850  mov     rcx, [rcx+8]; hServiceStatus
0x18001b854  call    cs:__imp_SetServiceStatus
0x18001b85a  mov     rcx, [rbx+30h]
0x18001b85e  add     rsp, 20h
0x18001b862  pop     rbx
0x18001b863  jmp     cs:__imp_SetEvent
```
