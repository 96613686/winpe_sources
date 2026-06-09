# InvSvcUpdateServiceStatus(ulong)

- ea: `0x18000c880`
- end: `0x18000ca26`
- name: `?InvSvcUpdateServiceStatus@@YAXK@Z`
- size: `422`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180007ff4`
- `0x18000c620`
- `0x18000c820`
- `0x180011720`

## callees

- `0x18000c880`
- `0x1800152d0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9ef`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c9e5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c9e5`

## string_xrefs

- `0x18000c92c`: `SERVICE_PAUSED/STOPPED`
- `0x18000c8bf`: `InvSvcUpdateServiceStatus`
- `0x18000c8f2`: `InvSvcUpdateServiceStatus`
- `0x18000c94e`: `InvSvcUpdateServiceStatus`
- `0x18000c97f`: `InvSvcUpdateServiceStatus`
- `0x18000ca02`: `InvSvcUpdateServiceStatus`
- `0x18000c8db`: `SERVICE_RUNNING`
- `0x18000c909`: `SERVICE_START/STOP_PENDING`
- `0x18000c9fb`: `Failed to set service status [%d]`

## pseudocode

```c
void __fastcall InvSvcUpdateServiceStatus(DWORD a1)
{
  _QWORD *v2; // rbx
  __int64 v3; // rdi
  DWORD LastError; // eax

  switch ( a1 )
  {
    case 1u:
LABEL_10:
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      ServiceStatus.dwControlsAccepted = 5;
      AslLogCallPrintf(3, "InvSvcUpdateServiceStatus", 51, "SERVICE_PAUSED/STOPPED");
      if ( g_tenantVector != (void *)qword_1800FEF70 )
      {
        AslLogCallPrintf(1, "InvSvcUpdateServiceStatus", 56, "Tenant vector not empty [%#x]", -2147418113);
        v2 = g_tenantVector;
        v3 = qword_1800FEF70;
        if ( g_tenantVector != (void *)qword_1800FEF70 )
        {
          do
          {
            if ( *v2 )
              (**(void (__fastcall ***)(_QWORD, __int64))*v2)(*v2, 1);
            ++v2;
          }
          while ( v2 != (_QWORD *)v3 );
          qword_1800FEF70 = (__int64)g_tenantVector;
        }
      }
      break;
    case 2u:
    case 3u:
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwWaitHint = 100;
      ServiceStatus.dwControlsAccepted = 0;
      AslLogCallPrintf(3, "InvSvcUpdateServiceStatus", 73, "SERVICE_START/STOP_PENDING");
      break;
    case 4u:
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      ServiceStatus.dwControlsAccepted = 5;
      AslLogCallPrintf(3, "InvSvcUpdateServiceStatus", 65, "SERVICE_RUNNING");
      break;
    case 7u:
      goto LABEL_10;
    default:
      AslLogCallPrintf(3, "InvSvcUpdateServiceStatus", 77, "default");
      return;
  }
  ServiceStatus.dwCurrentState = a1;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "InvSvcUpdateServiceStatus", 85, "Failed to set service status [%d]", LastError);
  }
}

```

## disassembly

```asm
0x18000c880  mov     [rsp+arg_0], rbx
0x18000c885  mov     [rsp+arg_8], rsi
0x18000c88a  push    rdi
0x18000c88b  sub     rsp, 30h
0x18000c88f  mov     eax, ecx
0x18000c891  mov     esi, ecx
0x18000c893  mov     ecx, 3
0x18000c898  sub     eax, 1
0x18000c89b  jz      loc_18000C92C
0x18000c8a1  sub     eax, 1
0x18000c8a4  jz      short loc_18000C903
0x18000c8a6  sub     eax, 1
0x18000c8a9  jz      short loc_18000C903
0x18000c8ab  sub     eax, 1
0x18000c8ae  jz      short loc_18000C8D0
0x18000c8b0  cmp     eax, ecx
0x18000c8b2  jz      short loc_18000C92C
0x18000c8b4  lea     r9, aDefault; "default"
0x18000c8bb  lea     r8d, [rcx+4Ah]
0x18000c8bf  lea     rdx, aInvsvcupdatese; "InvSvcUpdateServiceStatus"
0x18000c8c6  call    AslLogCallPrintf
0x18000c8cb  jmp     loc_18000CA16
0x18000c8d0  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x18000c8db  lea     r9, aServiceRunning; "SERVICE_RUNNING"
0x18000c8e2  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x18000c8ec  mov     r8d, 41h ; 'A'
0x18000c8f2  lea     rdx, aInvsvcupdatese; "InvSvcUpdateServiceStatus"
0x18000c8f9  call    AslLogCallPrintf
0x18000c8fe  jmp     loc_18000C9D1
0x18000c903  inc     cs:ServiceStatus.dwCheckPoint
0x18000c909  lea     r9, aServiceStartSt; "SERVICE_START/STOP_PENDING"
0x18000c910  mov     cs:ServiceStatus.dwWaitHint, 64h ; 'd'
0x18000c91a  mov     r8d, 49h ; 'I'
0x18000c920  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18000c92a  jmp     short loc_18000C8F2
0x18000c92c  lea     r9, aServicePausedS; "SERVICE_PAUSED/STOPPED"
0x18000c933  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x18000c93e  mov     r8d, 33h ; '3'
0x18000c944  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x18000c94e  lea     rdx, aInvsvcupdatese; "InvSvcUpdateServiceStatus"
0x18000c955  call    AslLogCallPrintf
0x18000c95a  mov     rax, cs:qword_1800FEF70
0x18000c961  cmp     cs:?g_tenantVector@@3V?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@A, rax; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>> g_tenantVector
0x18000c968  jz      short loc_18000C9D1
0x18000c96a  mov     r8d, 38h ; '8'
0x18000c970  mov     [rsp+38h+var_18], 8000FFFFh
0x18000c978  lea     r9, aTenantVectorNo; "Tenant vector not empty [%#x]"
0x18000c97f  lea     rdx, aInvsvcupdatese; "InvSvcUpdateServiceStatus"
0x18000c986  lea     ecx, [r8-37h]
0x18000c98a  call    AslLogCallPrintf
0x18000c98f  mov     rbx, cs:?g_tenantVector@@3V?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@A; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>> g_tenantVector
0x18000c996  mov     rdi, cs:qword_1800FEF70
0x18000c99d  cmp     rbx, rdi
0x18000c9a0  jz      short loc_18000C9D1
0x18000c9a2  mov     rcx, [rbx]
0x18000c9a5  test    rcx, rcx
0x18000c9a8  jz      short loc_18000C9BA
0x18000c9aa  mov     rax, [rcx]
0x18000c9ad  mov     edx, 1
0x18000c9b2  mov     rax, [rax]
0x18000c9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ba  add     rbx, 8
0x18000c9be  cmp     rbx, rdi
0x18000c9c1  jnz     short loc_18000C9A2
0x18000c9c3  mov     rbx, cs:?g_tenantVector@@3V?$vector@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VInvSvcTenant@Service@Inventory@Compat@Windows@@U?$default_delete@VInvSvcTenant@Service@Inventory@Compat@Windows@@@std@@@std@@@2@@std@@A; std::vector<std::unique_ptr<Windows::Compat::Inventory::Service::InvSvcTenant>> g_tenantVector
0x18000c9ca  mov     cs:qword_1800FEF70, rbx
0x18000c9d1  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000c9d8  lea     rdx, ServiceStatus; lpServiceStatus
0x18000c9df  mov     cs:ServiceStatus.dwCurrentState, esi
0x18000c9e5  call    cs:__imp_SetServiceStatus
0x18000c9eb  test    eax, eax
0x18000c9ed  jnz     short loc_18000CA16
0x18000c9ef  call    cs:__imp_GetLastError
0x18000c9f5  mov     r8d, 55h ; 'U'
0x18000c9fb  lea     r9, aFailedToSetSer; "Failed to set service status [%d]"
0x18000ca02  lea     rdx, aInvsvcupdatese; "InvSvcUpdateServiceStatus"
0x18000ca09  mov     [rsp+38h+var_18], eax
0x18000ca0d  lea     ecx, [r8-54h]
0x18000ca11  call    AslLogCallPrintf
0x18000ca16  mov     rbx, [rsp+38h+arg_0]
0x18000ca1b  mov     rsi, [rsp+38h+arg_8]
0x18000ca20  add     rsp, 30h
0x18000ca24  pop     rdi
0x18000ca25  retn
```
