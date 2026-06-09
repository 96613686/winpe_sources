# ServiceManager::HandleMapsInstallJobSustainedPause(MAPSBTSVC_JOB_TYPE)

- ea: `0x1800169a4`
- end: `0x180016a4b`
- name: `?HandleMapsInstallJobSustainedPause@ServiceManager@@AEAAJW4MAPSBTSVC_JOB_TYPE@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1800166a8`

## callees

- `0x180009c04`
- `0x180010d54`
- `0x1800134b8`
- `0x1800169a4`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016a40`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016a40`

## string_xrefs

- `0x180016a37`: `ServiceManager::HandleMapsInstallJobSustainedPause`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::HandleMapsInstallJobSustainedPause(__int64 a1)
{
  unsigned int v2; // ebx
  int v4; // eax
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock(a1 + 3400, v5);
  if ( (unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, 2) )
  {
    PackageManager::SetCurrentOperationInfoFlag(a1 + 3568, 64);
    if ( (unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, 1) )
    {
      *(_BYTE *)(a1 + 4313) = 1;
    }
    else
    {
      v4 = ServiceManager::CancelOperationAndWait((struct _RTL_CRITICAL_SECTION *)a1, 2);
      if ( v4 < 0 )
      {
        v2 = ZTraceReportPropagation(v4, "ServiceManager::HandleMapsInstallJobSustainedPause", 2310, (const void *)a1);
        goto LABEL_5;
      }
    }
  }
  v2 = 0;
LABEL_5:
  RelockableGate::~RelockableGate((RelockableGate *)v5);
  return v2;
}

```

## disassembly

```asm
0x1800169a4  mov     [rsp+arg_0], rbx
0x1800169a9  push    rdi
0x1800169aa  sub     rsp, 30h
0x1800169ae  mov     rbx, rcx
0x1800169b1  add     rcx, 0D48h
0x1800169b8  lea     rdx, [rsp+38h+var_18]
0x1800169bd  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800169c2  nop
0x1800169c3  lea     rdi, [rbx+0EE8h]
0x1800169ca  mov     edx, 2
0x1800169cf  mov     rcx, rdi
0x1800169d2  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x1800169d7  test    al, al
0x1800169d9  jz      short loc_180016A04
0x1800169db  lea     rcx, [rbx+0DF0h]
0x1800169e2  mov     edx, 40h ; '@'
0x1800169e7  call    ?SetCurrentOperationInfoFlag@PackageManager@@QEAAXW4__MIDL_odmlapi_0003@@@Z; PackageManager::SetCurrentOperationInfoFlag(__MIDL_odmlapi_0003)
0x1800169ec  mov     edx, 1
0x1800169f1  mov     rcx, rdi
0x1800169f4  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x1800169f9  test    al, al
0x1800169fb  jz      short loc_180016A1D
0x1800169fd  mov     byte ptr [rbx+10D9h], 1
0x180016a04  xor     ebx, ebx
0x180016a06  lea     rcx, [rsp+38h+var_18]; this
0x180016a0b  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180016a10  mov     eax, ebx
0x180016a12  mov     rbx, [rsp+38h+arg_0]
0x180016a17  add     rsp, 30h
0x180016a1b  pop     rdi
0x180016a1c  retn
0x180016a1d  mov     edx, 2
0x180016a22  mov     rcx, rbx
0x180016a25  call    ?CancelOperationAndWait@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperationAndWait(ServiceManager::CANCELLATION_TYPE)
0x180016a2a  test    eax, eax
0x180016a2c  jns     short loc_180016A04
0x180016a2e  mov     r9, rbx
0x180016a31  mov     r8d, 906h
0x180016a37  lea     rdx, aServicemanager_8; "ServiceManager::HandleMapsInstallJobSus"...
0x180016a3e  mov     ecx, eax
0x180016a40  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016a46  mov     ebx, eax
0x180016a48  jmp     short loc_180016A06
```
