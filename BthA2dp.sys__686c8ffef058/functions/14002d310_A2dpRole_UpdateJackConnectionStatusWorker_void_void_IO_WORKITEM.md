# A2dpRole::UpdateJackConnectionStatusWorker(void *,void *,_IO_WORKITEM *)

- ea: `0x14002d310`
- end: `0x14002d385`
- name: `?UpdateJackConnectionStatusWorker@A2dpRole@@CAXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `117`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x140006b70`
- `0x14001df98`
- `0x14001e4a4`
- `0x14002d168`
- `0x14002d310`
- `0x14002d8e8`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14002d34e`
- `ntoskrnl!IoFreeWorkItem` at `0x14002d34e`

## string_xrefs

- `0x14002d35e`: `UpdateJackConnectionStatusWorker`

## pseudocode

```c
void __fastcall A2dpRole::UpdateJackConnectionStatusWorker(
        PVOID IoObject,
        A2DP_Device **Context,
        PIO_WORKITEM IoWorkItem)
{
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  if ( (unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline(IoObject) )
    _reset___unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAAXPEAVoperation_guard_3__Z(
      &v5,
      Context + 34);
  A2dpRole::UpdateJackConnectionStatus((A2dpRole *)Context);
  IoFreeWorkItem(IoWorkItem);
  A2DP_Device::Release(Context[9], 6, "UpdateJackConnectionStatusWorker");
  __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v5);
}

```

## disassembly

```asm
0x14002d310  mov     [rsp+arg_0], rbx
0x14002d315  push    rdi
0x14002d316  sub     rsp, 20h
0x14002d31a  mov     rdi, r8
0x14002d31d  mov     [rsp+28h+arg_8], 0
0x14002d326  mov     rbx, rdx
0x14002d329  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x14002d32e  test    eax, eax
0x14002d330  jz      short loc_14002D343
0x14002d332  lea     rdx, [rbx+110h]
0x14002d339  lea     rcx, [rsp+28h+arg_8]
0x14002d33e  call    ?reset@?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAVoperation_guard@3@@Z
0x14002d343  mov     rcx, rbx; this
0x14002d346  call    ?UpdateJackConnectionStatus@A2dpRole@@QEAAXXZ; A2dpRole::UpdateJackConnectionStatus(void)
0x14002d34b  mov     rcx, rdi; IoWorkItem
0x14002d34e  call    cs:__imp_IoFreeWorkItem
0x14002d355  nop     dword ptr [rax+rax+00h]
0x14002d35a  mov     rcx, [rbx+48h]; this
0x14002d35e  lea     r8, aUpdatejackconn; "UpdateJackConnectionStatusWorker"
0x14002d365  mov     edx, 6; __int16
0x14002d36a  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x14002d36f  lea     rcx, [rsp+28h+arg_8]
0x14002d374  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d379  mov     rbx, [rsp+28h+arg_0]
0x14002d37e  add     rsp, 20h
0x14002d382  pop     rdi
0x14002d383  retn
```
