# Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)

- ea: `0x18000b4fc`
- end: `0x18000b536`
- name: `?StopAsync@?$Service@VConnectedStorageService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009db0`
- `0x18000c110`
- `0x18000c130`

## callees

- `0x18000b4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b52f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b520`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b520`

## pseudocode

```c
BOOL __fastcall Windows::Internal::Service<ConnectedStorageService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(
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
0x18000b4fc  push    rbx
0x18000b4fe  sub     rsp, 20h
0x18000b502  lea     rdx, [rcx+10h]; lpServiceStatus
0x18000b506  mov     rbx, rcx
0x18000b509  mov     eax, [rdx+4]
0x18000b50c  dec     eax
0x18000b50e  test    eax, 0FFFFFFFDh
0x18000b513  jz      short loc_18000B526
0x18000b515  mov     dword ptr [rcx+14h], 3
0x18000b51c  mov     rcx, [rcx+8]; hServiceStatus
0x18000b520  call    cs:__imp_SetServiceStatus
0x18000b526  mov     rcx, [rbx+30h]
0x18000b52a  add     rsp, 20h
0x18000b52e  pop     rbx
0x18000b52f  jmp     cs:__imp_SetEvent
```
