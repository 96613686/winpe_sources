# A2dpRole::UpdateDataRange(void)

- ea: `0x14002d0a0`
- end: `0x14002d161`
- name: `?UpdateDataRange@A2dpRole@@QEAAXXZ`
- size: `193`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14001b270`
- `0x14002ff10`

## callees

- `0x14000e240`
- `0x14001df54`
- `0x14001df98`
- `0x14002b978`
- `0x14002d0a0`
- `0x14002d8e8`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x14002d136`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002d136`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002d0fa`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002d0fa`

## string_xrefs

- `0x14002d112`: `UpdateDataRange`

## pseudocode

```c
void __fastcall A2dpRole::UpdateDataRange(char *Context)
{
  __int64 v2; // rax
  struct _IO_WORKITEM *WorkItem; // rdi
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF
  char v5; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  if ( !(unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline(Context)
    || (v2 = wil::operation_guard::acquire(Context + 272, &v5),
        __4__unique_any_t_V__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
          &v4,
          v2),
        __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v5),
        v4) )
  {
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*((_QWORD *)Context + 9) + 384LL));
    if ( WorkItem )
    {
      A2DP_Device::AddRef(*((A2DP_Device **)Context + 9), 7, "UpdateDataRange");
      IoQueueWorkItemEx(
        WorkItem,
        (PIO_WORKITEM_ROUTINE_EX)A2dpRole::UpdateFilterDescriptorChannelsAndSamplerateWorkItem,
        DelayedWorkQueue,
        Context);
      v4 = 0;
    }
  }
  __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v4);
}

```

## disassembly

```asm
0x14002d0a0  mov     [rsp+arg_0], rbx
0x14002d0a5  push    rdi
0x14002d0a6  sub     rsp, 20h
0x14002d0aa  mov     rbx, rcx
0x14002d0ad  mov     [rsp+28h+arg_8], 0
0x14002d0b6  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x14002d0bb  test    eax, eax
0x14002d0bd  jz      short loc_14002D0EF
0x14002d0bf  lea     rcx, [rbx+110h]
0x14002d0c6  lea     rdx, [rsp+28h+arg_10]
0x14002d0cb  call    ?acquire@operation_guard@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x14002d0d0  mov     rdx, rax
0x14002d0d3  lea     rcx, [rsp+28h+arg_8]
0x14002d0d8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x14002d0dd  lea     rcx, [rsp+28h+arg_10]
0x14002d0e2  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d0e7  cmp     [rsp+28h+arg_8], 0
0x14002d0ed  jz      short loc_14002D14B
0x14002d0ef  mov     rcx, [rbx+48h]
0x14002d0f3  mov     rcx, [rcx+180h]; DeviceObject
0x14002d0fa  call    cs:__imp_IoAllocateWorkItem
0x14002d101  nop     dword ptr [rax+rax+00h]
0x14002d106  mov     rdi, rax
0x14002d109  test    rax, rax
0x14002d10c  jz      short loc_14002D14B
0x14002d10e  mov     rcx, [rbx+48h]; this
0x14002d112  lea     r8, aUpdatedatarang; "UpdateDataRange"
0x14002d119  mov     edx, 7; __int16
0x14002d11e  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x14002d123  mov     r9, rbx; Context
0x14002d126  lea     rdx, ?UpdateFilterDescriptorChannelsAndSamplerateWorkItem@A2dpRole@@_C2PAGE@@AXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14002d12d  mov     r8d, 1; QueueType
0x14002d133  mov     rcx, rdi; IoWorkItem
0x14002d136  call    cs:__imp_IoQueueWorkItemEx
0x14002d13d  nop     dword ptr [rax+rax+00h]
0x14002d142  mov     [rsp+28h+arg_8], 0
0x14002d14b  lea     rcx, [rsp+28h+arg_8]
0x14002d150  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d155  mov     rbx, [rsp+28h+arg_0]
0x14002d15a  add     rsp, 20h
0x14002d15e  pop     rdi
0x14002d15f  retn
```
