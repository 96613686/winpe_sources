# Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(ulong,ulong,void *,void *)

- ea: `0x180009d10`
- end: `0x180009d5e`
- name: `?HandlerExStatic@?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z`
- size: `78`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009d44`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009d44`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009d3a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009d3a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  SERVICE_STATUS_HANDLE v5; // rcx

  if ( dwControl == 1 )
  {
    if ( ((*((_DWORD *)lpContext + 5) - 1) & 0xFFFFFFFD) != 0 )
    {
      v5 = (SERVICE_STATUS_HANDLE)*((_QWORD *)lpContext + 1);
      *((_DWORD *)lpContext + 5) = 3;
      SetServiceStatus(v5, (LPSERVICE_STATUS)(lpContext + 16));
    }
    SetEvent(*((HANDLE *)lpContext + 6));
    return 0;
  }
  if ( dwControl == 4 )
    return 0;
  return 120;
}

```

## disassembly

```asm
0x180009d10  push    rbx
0x180009d12  sub     rsp, 20h
0x180009d16  mov     rbx, r9
0x180009d19  cmp     ecx, 1
0x180009d1c  jnz     short loc_180009D52
0x180009d1e  lea     rdx, [r9+10h]; lpServiceStatus
0x180009d22  mov     eax, [rdx+4]
0x180009d25  dec     eax
0x180009d27  test    eax, 0FFFFFFFDh
0x180009d2c  jz      short loc_180009D40
0x180009d2e  mov     rcx, [r9+8]; hServiceStatus
0x180009d32  mov     dword ptr [r9+14h], 3
0x180009d3a  call    cs:__imp_SetServiceStatus
0x180009d40  mov     rcx, [rbx+30h]; hEvent
0x180009d44  call    cs:__imp_SetEvent
0x180009d4a  xor     eax, eax
0x180009d4c  add     rsp, 20h
0x180009d50  pop     rbx
0x180009d51  retn
0x180009d52  cmp     ecx, 4
0x180009d55  jz      short loc_180009D4A
0x180009d57  mov     eax, 78h ; 'x'
0x180009d5c  jmp     short loc_180009D4C
```
