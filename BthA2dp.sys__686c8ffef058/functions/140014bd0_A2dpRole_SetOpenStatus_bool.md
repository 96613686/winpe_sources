# A2dpRole::SetOpenStatus(bool)

- ea: `0x140014bd0`
- end: `0x140014d05`
- name: `?SetOpenStatus@A2dpRole@@QEAAX_N@Z`
- size: `309`
- prototype: `void __fastcall(PVOID Context, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x14001f32c`
- `0x140030350`

## callees

- `0x140006410`
- `0x14000e240`
- `0x14001071c`
- `0x140013b7c`
- `0x140014bd0`
- `0x14001df54`
- `0x14001df98`
- `0x14002b978`
- `0x14002d168`
- `0x14002d8e8`
- `0x14003897c`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x140014cda`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140014cda`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014c9e`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014c9e`

## string_xrefs

- `0x140014cb6`: `SetOpenStatus`

## pseudocode

```c
void __fastcall A2dpRole::SetOpenStatus(A2DP_Device **Context, char a2)
{
  bool v3; // zf
  A2dpStreamDispositionController *v4; // rcx
  A2DP_Device *v5; // rbx
  unsigned int v6; // eax
  __int64 v7; // rax
  struct _IO_WORKITEM *WorkItem; // rbx
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  utl::_RefCountBase *v10; // [rsp+28h] [rbp-10h]
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  char v12; // [rsp+50h] [rbp+18h] BYREF

  if ( *((_BYTE *)Context + 90) != a2 )
  {
    v3 = *((_BYTE *)Context + 89) == 0;
    *((_BYTE *)Context + 90) = a2;
    if ( v3 )
      A2dpRole::UpdateJackConnectionStatus((A2dpRole *)Context);
    v4 = Context[25];
    if ( v4 )
    {
      if ( *((_BYTE *)Context + 90) )
      {
        utl::shared_ptr<A2dpAudioCodec>::shared_ptr<A2dpAudioCodec>(&v9, Context + 14);
        if ( v9 )
        {
          v5 = Context[25];
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          A2dpStreamDispositionController::OnCodecConfigured(v5, v6);
        }
        if ( v10 )
          utl::_RefCountBase::_DecStrong(v10);
      }
      else
      {
        A2dpStreamDispositionController::OnAvdtpDisconnected(v4);
      }
    }
    v11 = 0;
    if ( !(unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline()
      || (v7 = wil::operation_guard::acquire(Context + 34, &v12),
          __4__unique_any_t_V__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
            &v11,
            v7),
          __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v12),
          v11) )
    {
      WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)Context[9] + 48));
      if ( WorkItem )
      {
        A2DP_Device::AddRef(Context[9], 5, "SetOpenStatus");
        IoQueueWorkItemEx(WorkItem, A2dpRole::SetConnectionPropertiesWorker, DelayedWorkQueue, Context);
        v11 = 0;
      }
    }
    __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  }
}

```

## disassembly

```asm
0x140014bd0  mov     [rsp+arg_8], rbx
0x140014bd5  push    rdi
0x140014bd6  sub     rsp, 30h
0x140014bda  mov     rdi, rcx
0x140014bdd  cmp     [rcx+5Ah], dl
0x140014be0  jz      loc_140014CF9
0x140014be6  cmp     byte ptr [rcx+59h], 0
0x140014bea  mov     [rcx+5Ah], dl
0x140014bed  jnz     short loc_140014BF4
0x140014bef  call    ?UpdateJackConnectionStatus@A2dpRole@@QEAAXXZ; A2dpRole::UpdateJackConnectionStatus(void)
0x140014bf4  mov     rcx, [rdi+0C8h]; this
0x140014bfb  test    rcx, rcx
0x140014bfe  jz      short loc_140014C51
0x140014c00  cmp     byte ptr [rdi+5Ah], 0
0x140014c04  jz      short loc_140014C4C
0x140014c06  lea     rdx, [rdi+70h]
0x140014c0a  lea     rcx, [rsp+38h+var_18]
0x140014c0f  call    ??0?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAA@AEBV01@@Z; utl::shared_ptr<A2dpAudioCodec>::shared_ptr<A2dpAudioCodec>(utl::shared_ptr<A2dpAudioCodec> const &)
0x140014c14  mov     rcx, [rsp+38h+var_18]
0x140014c19  test    rcx, rcx
0x140014c1c  jz      short loc_140014C3B
0x140014c1e  mov     rax, [rcx]
0x140014c21  mov     rbx, [rdi+0C8h]
0x140014c28  mov     rax, [rax+10h]
0x140014c2c  call    _guard_dispatch_icall
0x140014c31  mov     edx, eax
0x140014c33  mov     rcx, rbx
0x140014c36  call    ?OnCodecConfigured@A2dpStreamDispositionController@@QEAAXW4CodecProviderKind@@@Z; A2dpStreamDispositionController::OnCodecConfigured(CodecProviderKind)
0x140014c3b  mov     rcx, [rsp+38h+var_10]; this
0x140014c40  test    rcx, rcx
0x140014c43  jz      short loc_140014C51
0x140014c45  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140014c4a  jmp     short loc_140014C51
0x140014c4c  call    ?OnAvdtpDisconnected@A2dpStreamDispositionController@@QEAAXXZ; A2dpStreamDispositionController::OnAvdtpDisconnected(void)
0x140014c51  mov     [rsp+38h+arg_0], 0
0x140014c5a  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x140014c5f  test    eax, eax
0x140014c61  jz      short loc_140014C93
0x140014c63  lea     rcx, [rdi+110h]
0x140014c6a  lea     rdx, [rsp+38h+arg_10]
0x140014c6f  call    ?acquire@operation_guard@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x140014c74  mov     rdx, rax
0x140014c77  lea     rcx, [rsp+38h+arg_0]
0x140014c7c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x140014c81  lea     rcx, [rsp+38h+arg_10]
0x140014c86  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140014c8b  cmp     [rsp+38h+arg_0], 0
0x140014c91  jz      short loc_140014CEF
0x140014c93  mov     rcx, [rdi+48h]
0x140014c97  mov     rcx, [rcx+180h]; DeviceObject
0x140014c9e  call    cs:__imp_IoAllocateWorkItem
0x140014ca5  nop     dword ptr [rax+rax+00h]
0x140014caa  mov     rbx, rax
0x140014cad  test    rax, rax
0x140014cb0  jz      short loc_140014CEF
0x140014cb2  mov     rcx, [rdi+48h]; this
0x140014cb6  lea     r8, aSetopenstatus; "SetOpenStatus"
0x140014cbd  mov     edx, 5; __int16
0x140014cc2  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x140014cc7  mov     r9, rdi; Context
0x140014cca  lea     rdx, ?SetConnectionPropertiesWorker@A2dpRole@@CAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x140014cd1  mov     r8d, 1; QueueType
0x140014cd7  mov     rcx, rbx; IoWorkItem
0x140014cda  call    cs:__imp_IoQueueWorkItemEx
0x140014ce1  nop     dword ptr [rax+rax+00h]
0x140014ce6  mov     [rsp+38h+arg_0], 0
0x140014cef  lea     rcx, [rsp+38h+arg_0]
0x140014cf4  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140014cf9  mov     rbx, [rsp+38h+arg_8]
0x140014cfe  add     rsp, 30h
0x140014d02  pop     rdi
0x140014d03  retn
```
