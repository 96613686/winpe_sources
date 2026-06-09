# Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun(void)

- ea: `0x1400138a4`
- end: `0x14001390c`
- name: `?CleanUpFromRun@?$VmServiceModule@VService@Svc@CExec@@@Vml@@QEAAXXZ`
- size: `104`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400141b4`
- `0x140022bea`

## callees

- `0x140010240`
- `0x1400138a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400138c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400138c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400138fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400138fb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400138f1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400138f1`

## pseudocode

```c
void __fastcall Vml::VmServiceModule<CExec::Svc::Service>::CleanUpFromRun(__int64 a1)
{
  SERVICE_STATUS_HANDLE v2; // rcx

  CExec::Svc::Service::CleanUpFromRunSelf((CExec::Svc::Service *)a1);
  if ( *(_QWORD *)(a1 + 136) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    if ( *(_DWORD *)(a1 + 108) != 1 )
      *(_QWORD *)(a1 + 124) = 0;
    v2 = *(SERVICE_STATUS_HANDLE *)(a1 + 136);
    *(_DWORD *)(a1 + 108) = 1;
    *(_DWORD *)(a1 + 116) = 0;
    SetServiceStatus(v2, (LPSERVICE_STATUS)(a1 + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
}

```

## disassembly

```asm
0x1400138a4  mov     [rsp+arg_8], rbx
0x1400138a9  push    rdi
0x1400138aa  sub     rsp, 20h
0x1400138ae  mov     rbx, rcx
0x1400138b1  call    ?CleanUpFromRunSelf@Service@Svc@CExec@@QEAAXXZ; CExec::Svc::Service::CleanUpFromRunSelf(void)
0x1400138b6  cmp     qword ptr [rbx+88h], 0
0x1400138be  jz      short loc_140013901
0x1400138c0  lea     rcx, [rbx+28h]; lpCriticalSection
0x1400138c4  call    cs:__imp_EnterCriticalSection
0x1400138ca  lea     rdx, [rbx+68h]; lpServiceStatus
0x1400138ce  cmp     dword ptr [rdx+4], 1
0x1400138d2  jz      short loc_1400138DC
0x1400138d4  mov     qword ptr [rbx+7Ch], 0
0x1400138dc  mov     rcx, [rbx+88h]; hServiceStatus
0x1400138e3  mov     dword ptr [rbx+6Ch], 1
0x1400138ea  mov     dword ptr [rbx+74h], 0
0x1400138f1  call    cs:__imp_SetServiceStatus
0x1400138f7  lea     rcx, [rbx+28h]; lpCriticalSection
0x1400138fb  call    cs:__imp_LeaveCriticalSection
0x140013901  mov     rbx, [rsp+28h+arg_8]
0x140013906  add     rsp, 20h
0x14001390a  pop     rdi
0x14001390b  retn
```
