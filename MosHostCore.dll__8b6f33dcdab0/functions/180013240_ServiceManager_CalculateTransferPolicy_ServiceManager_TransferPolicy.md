# ServiceManager::CalculateTransferPolicy(ServiceManager::TransferPolicy *)

- ea: `0x180013240`
- end: `0x18001332d`
- name: `?CalculateTransferPolicy@ServiceManager@@AEAAJPEAW4TransferPolicy@1@@Z`
- size: `237`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, enum ServiceManager::TransferPolicy *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001db8c`

## callees

- `0x180009b74`
- `0x180013240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800132d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800132d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001331e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001331e`
- `mapsbtsvc!MapsBackgroundTransferService_GetIsAnyJobWaiting` at `0x18001328c`
- `mapsbtsvc!MapsBackgroundTransferService_GetIsAnyJobWaiting` at `0x18001328c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800132a8`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800132a8`

## string_xrefs

- `0x180013299`: `ServiceManager::CalculateTransferPolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::CalculateTransferPolicy(
        ServiceManager *this,
        enum ServiceManager::TransferPolicy *a2)
{
  unsigned int v2; // r14d
  int v5; // eax
  bool v6; // di
  int IsAnyJobWaiting; // eax
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  BOOL HasClientsInForeground; // ebp
  int v11; // ebx
  char v12; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  *(_DWORD *)a2 = 0;
  if ( *((_DWORD *)this + 882) == 3 )
  {
    *(_DWORD *)a2 = 3;
  }
  else
  {
    v5 = *((_DWORD *)this + 881);
    v12 = 1;
    v6 = (unsigned int)(v5 - 3) <= 1;
    IsAnyJobWaiting = MapsBackgroundTransferService_GetIsAnyJobWaiting((bool *)&v12);
    if ( IsAnyJobWaiting >= 0 )
    {
      if ( v6 && !v12 )
      {
        v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 4208);
        HasClientsInForeground = ClientsTracker::HasClientsInForeground((LPCRITICAL_SECTION)((char *)this + 3816));
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4208));
        if ( *((_BYTE *)this + 4248) )
        {
          v11 = *((_DWORD *)this + 1068);
          if ( v8 )
            LeaveCriticalSection(v8);
          if ( v11 == 1 )
          {
            *(_DWORD *)a2 = HasClientsInForeground;
            return v2;
          }
        }
        else if ( this != (ServiceManager *)-4208LL )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4208));
        }
        *(_DWORD *)a2 = HasClientsInForeground + 2;
      }
    }
    else
    {
      return (unsigned int)ZTraceReportPropagation(
                             IsAnyJobWaiting,
                             "ServiceManager::CalculateTransferPolicy",
                             3180,
                             this);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180013240  mov     [rsp+arg_8], rbx
0x180013245  mov     [rsp+arg_10], rbp
0x18001324a  push    rsi
0x18001324b  push    rdi
0x18001324c  push    r14
0x18001324e  sub     rsp, 20h
0x180013252  xor     r14d, r14d
0x180013255  mov     rsi, rdx
0x180013258  mov     [rdx], r14d
0x18001325b  mov     rbx, rcx
0x18001325e  cmp     dword ptr [rcx+0DC8h], 3
0x180013265  jnz     short loc_180013272
0x180013267  mov     dword ptr [rdx], 3
0x18001326d  jmp     loc_1800132FA
0x180013272  mov     eax, [rcx+0DC4h]
0x180013278  lea     rcx, [rsp+38h+arg_0]
0x18001327d  sub     eax, 3
0x180013280  mov     [rsp+38h+arg_0], 1
0x180013285  cmp     eax, 1
0x180013288  setbe   dil
0x18001328c  call    cs:__imp_?MapsBackgroundTransferService_GetIsAnyJobWaiting@@YAJPEA_N@Z; MapsBackgroundTransferService_GetIsAnyJobWaiting(bool *)
0x180013292  test    eax, eax
0x180013294  jns     short loc_1800132B3
0x180013296  mov     r9, rbx
0x180013299  lea     rdx, aServicemanager_49; "ServiceManager::CalculateTransferPolicy"
0x1800132a0  mov     r8d, 0C6Ch
0x1800132a6  mov     ecx, eax
0x1800132a8  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800132ae  mov     r14d, eax
0x1800132b1  jmp     short loc_1800132FA
0x1800132b3  test    dil, dil
0x1800132b6  jz      short loc_1800132FA
0x1800132b8  cmp     [rsp+38h+arg_0], r14b
0x1800132bd  jnz     short loc_1800132FA
0x1800132bf  lea     rcx, [rbx+0EE8h]; lpCriticalSection
0x1800132c6  call    ?HasClientsInForeground@ClientsTracker@@QEAA_NXZ; ClientsTracker::HasClientsInForeground(void)
0x1800132cb  lea     rdi, [rbx+1070h]
0x1800132d2  movzx   ebp, al
0x1800132d5  mov     rcx, rdi; lpCriticalSection
0x1800132d8  call    cs:__imp_EnterCriticalSection
0x1800132de  cmp     [rbx+1098h], r14b
0x1800132e5  jnz     short loc_180013310
0x1800132e7  test    rdi, rdi
0x1800132ea  jz      short loc_1800132F5
0x1800132ec  mov     rcx, rdi; lpCriticalSection
0x1800132ef  call    cs:__imp_LeaveCriticalSection
0x1800132f5  lea     eax, [rbp+2]
0x1800132f8  mov     [rsi], eax
0x1800132fa  mov     rbx, [rsp+38h+arg_8]
0x1800132ff  mov     eax, r14d
0x180013302  mov     rbp, [rsp+38h+arg_10]
0x180013307  add     rsp, 20h
0x18001330b  pop     r14
0x18001330d  pop     rdi
0x18001330e  pop     rsi
0x18001330f  retn
0x180013310  mov     ebx, [rbx+10B0h]
0x180013316  test    rdi, rdi
0x180013319  jz      short loc_180013324
0x18001331b  mov     rcx, rdi; lpCriticalSection
0x18001331e  call    cs:__imp_LeaveCriticalSection
0x180013324  cmp     ebx, 1
0x180013327  jnz     short loc_1800132F5
0x180013329  mov     [rsi], ebp
0x18001332b  jmp     short loc_1800132FA
```
