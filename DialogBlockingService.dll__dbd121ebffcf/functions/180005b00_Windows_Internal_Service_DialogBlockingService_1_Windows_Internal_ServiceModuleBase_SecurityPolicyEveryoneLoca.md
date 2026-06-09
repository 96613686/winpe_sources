# Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(ulong,ulong,void *,void *)

- ea: `0x180005b00`
- end: `0x180005b61`
- name: `?HandlerExStatic@?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z`
- size: `97`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, _DWORD *lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005b00`
- `0x180006248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005b34`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005b34`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b2a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b2a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(
        DWORD dwControl,
        DWORD dwEventType,
        _DWORD *lpEventData,
        char *lpContext)
{
  SERVICE_STATUS_HANDLE v5; // rcx
  __int64 result; // rax

  if ( dwControl == 1 )
  {
    if ( ((*((_DWORD *)lpContext + 5) - 1) & 0xFFFFFFFD) != 0 )
    {
      v5 = (SERVICE_STATUS_HANDLE)*((_QWORD *)lpContext + 1);
      *((_DWORD *)lpContext + 5) = 3;
      SetServiceStatus(v5, (LPSERVICE_STATUS)(lpContext + 16));
    }
    SetEvent(*((HANDLE *)lpContext + 6));
  }
  else if ( dwControl == 33 )
  {
    DialogBlockingService::OnSessionUserChanged(
      (DialogBlockingService *)lpContext,
      dwEventType,
      lpEventData[1],
      (unsigned __int64)lpContext);
  }
  else
  {
    result = 120;
    if ( dwControl != 4 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180005b00  push    rbx
0x180005b02  sub     rsp, 20h
0x180005b06  mov     rbx, r9
0x180005b09  cmp     ecx, 1
0x180005b0c  jnz     short loc_180005B3C
0x180005b0e  lea     rdx, [r9+10h]; lpServiceStatus
0x180005b12  mov     eax, [rdx+4]
0x180005b15  dec     eax
0x180005b17  test    eax, 0FFFFFFFDh
0x180005b1c  jz      short loc_180005B30
0x180005b1e  mov     rcx, [r9+8]; hServiceStatus
0x180005b22  mov     dword ptr [r9+14h], 3
0x180005b2a  call    cs:__imp_SetServiceStatus
0x180005b30  mov     rcx, [rbx+30h]; hEvent
0x180005b34  call    cs:__imp_SetEvent
0x180005b3a  jmp     short loc_180005B59
0x180005b3c  cmp     ecx, 21h ; '!'
0x180005b3f  jnz     short loc_180005B4F
0x180005b41  mov     r8d, [r8+4]; unsigned int
0x180005b45  mov     rcx, rbx; this
0x180005b48  call    ?OnSessionUserChanged@DialogBlockingService@@QEAAXKK_K@Z; DialogBlockingService::OnSessionUserChanged(ulong,ulong,unsigned __int64)
0x180005b4d  jmp     short loc_180005B59
0x180005b4f  mov     eax, 78h ; 'x'
0x180005b54  cmp     ecx, 4
0x180005b57  jnz     short loc_180005B5B
0x180005b59  xor     eax, eax
0x180005b5b  add     rsp, 20h
0x180005b5f  pop     rbx
0x180005b60  retn
```
