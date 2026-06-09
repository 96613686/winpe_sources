# ProvisioningHandler::FreeRpcInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,ulong)

- ea: `0x18005061c`
- end: `0x1800506b6`
- name: `?FreeRpcInterfaceTemplates@ProvisioningHandler@@QEAAXPEAURPC_INTERFACE_TEMPLATEW@@K@Z`
- size: `154`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct RPC_INTERFACE_TEMPLATEW *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180050610`

## callees

- `0x18005061c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005066e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005066e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050633`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800506aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050686`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180050649`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180050649`

## pseudocode

```c
void __fastcall ProvisioningHandler::FreeRpcInterfaceTemplates(
        LPCRITICAL_SECTION lpCriticalSection,
        struct RPC_INTERFACE_TEMPLATEW *a2)
{
  void *v4; // rcx
  void *v5; // rcx

  if ( *((_QWORD *)a2 + 9) )
  {
    EnterCriticalSection(lpCriticalSection);
    v4 = (void *)*((_QWORD *)a2 + 9);
    if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
      FreeTransientObjectSecurityDescriptor(v4);
    else
      LocalFree(v4);
    *((_QWORD *)a2 + 9) = 0;
    LeaveCriticalSection(lpCriticalSection);
  }
  v5 = (void *)*((_QWORD *)a2 + 19);
  if ( v5 )
  {
    LocalFree(v5);
    *((_QWORD *)a2 + 19) = 0;
  }
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x18005061c  mov     [rsp+arg_0], rbx
0x180050621  push    rdi
0x180050622  sub     rsp, 20h
0x180050626  cmp     qword ptr [rdx+48h], 0
0x18005062b  mov     rbx, rdx
0x18005062e  mov     rdi, rcx
0x180050631  jz      short loc_18005067A
0x180050633  call    cs:__imp_EnterCriticalSection
0x18005063a  nop     dword ptr [rax+rax+00h]
0x18005063f  cmp     byte ptr [rdi+28h], 0
0x180050643  mov     rcx, [rbx+48h]; hMem
0x180050647  jz      short loc_180050657
0x180050649  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180050650  nop     dword ptr [rax+rax+00h]
0x180050655  jmp     short loc_180050663
0x180050657  call    cs:__imp_LocalFree
0x18005065e  nop     dword ptr [rax+rax+00h]
0x180050663  mov     rcx, rdi; lpCriticalSection
0x180050666  mov     qword ptr [rbx+48h], 0
0x18005066e  call    cs:__imp_LeaveCriticalSection
0x180050675  nop     dword ptr [rax+rax+00h]
0x18005067a  mov     rcx, [rbx+98h]; hMem
0x180050681  test    rcx, rcx
0x180050684  jz      short loc_18005069D
0x180050686  call    cs:__imp_LocalFree
0x18005068d  nop     dword ptr [rax+rax+00h]
0x180050692  mov     qword ptr [rbx+98h], 0
0x18005069d  mov     rcx, rbx
0x1800506a0  mov     rbx, [rsp+28h+arg_0]
0x1800506a5  add     rsp, 20h
0x1800506a9  pop     rdi
0x1800506aa  jmp     cs:__imp_CoTaskMemFree
```
