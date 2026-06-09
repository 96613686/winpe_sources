# A2dpRole::UpdateJackConnectionStatus(void)

- ea: `0x14002d168`
- end: `0x14002d302`
- name: `?UpdateJackConnectionStatus@A2dpRole@@QEAAXXZ`
- size: `410`
- prototype: `void __fastcall(A2dpRole *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140014bd0`
- `0x14001f390`
- `0x140021734`
- `0x14002d310`
- `0x14007a9b4`

## callees

- `0x140003530`
- `0x14000e240`
- `0x14001df54`
- `0x14001df98`
- `0x14002b978`
- `0x14002c024`
- `0x14002d168`
- `0x14002d8e8`
- `0x14007cfac`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x14002d2bf`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002d2bf`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d1e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d1e8`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002d283`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002d283`

## string_xrefs

- `0x14002d29b`: `UpdateJackConnectionStatus`

## pseudocode

```c
void __fastcall A2dpRole::UpdateJackConnectionStatus(A2dpRole *this)
{
  bool v2; // dl
  A2dpInbandAudioDevice *v3; // rcx
  __int64 v4; // rax
  struct _IO_WORKITEM *WorkItem; // rdi
  __int64 v6; // [rsp+68h] [rbp+10h] BYREF
  char v7; // [rsp+70h] [rbp+18h] BYREF

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      26,
      (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
      (char)this);
  if ( KeGetCurrentIrql() )
  {
    if ( *((_BYTE *)this + 91) != *((_BYTE *)this + 90)
      || *((_BYTE *)this + 92) != (*(_QWORD *)(*((_QWORD *)this + 9) + 736LL) != 0) )
    {
      v6 = 0;
      if ( !(unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline()
        || (v4 = wil::operation_guard::acquire((char *)this + 272, &v7),
            __4__unique_any_t_V__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
              &v6,
              v4),
            __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v7),
            v6) )
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*((_QWORD *)this + 9) + 384LL));
        if ( WorkItem )
        {
          A2DP_Device::AddRef(*((A2DP_Device **)this + 9), 6, "UpdateJackConnectionStatus");
          IoQueueWorkItemEx(WorkItem, A2dpRole::UpdateJackConnectionStatusWorker, DelayedWorkQueue, this);
          v6 = 0;
        }
        *((_BYTE *)this + 91) = *((_BYTE *)this + 90);
        *((_BYTE *)this + 92) = *(_QWORD *)(*((_QWORD *)this + 9) + 736LL) != 0;
      }
      __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v6);
    }
  }
  else
  {
    v3 = (A2dpInbandAudioDevice *)*((_QWORD *)this + 23);
    if ( v3 )
      A2dpInbandAudioDevice::OnConnectionStateChanged(v3);
    A2dpRole::LogConnectionStatus(this);
  }
}

```

## disassembly

```asm
0x14002d168  mov     [rsp+arg_0], rbx
0x14002d16d  push    rdi
0x14002d16e  sub     rsp, 50h
0x14002d172  mov     rbx, rcx
0x14002d175  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d17c  lea     rax, WPP_GLOBAL_Control
0x14002d183  cmp     rcx, rax
0x14002d186  jz      short loc_14002D199
0x14002d188  mov     eax, [rcx+2Ch]
0x14002d18b  test    al, 10h
0x14002d18d  jz      short loc_14002D199
0x14002d18f  cmp     byte ptr [rcx+29h], 4
0x14002d193  jb      short loc_14002D199
0x14002d195  mov     dl, 1
0x14002d197  jmp     short loc_14002D19B
0x14002d199  xor     dl, dl
0x14002d19b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d1a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d1a9  setnz   r8b
0x14002d1ad  test    dl, dl
0x14002d1af  jnz     short loc_14002D1B6
0x14002d1b1  test    r8b, r8b
0x14002d1b4  jz      short loc_14002D1E8
0x14002d1b6  mov     r9, [rcx+40h]
0x14002d1ba  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14002d1c1  mov     rcx, [rcx+18h]
0x14002d1c5  mov     [rsp+58h+var_18], rbx
0x14002d1ca  mov     [rsp+58h+var_20], rax
0x14002d1cf  mov     [rsp+58h+var_28], 1Ah
0x14002d1d6  mov     [rsp+58h+var_30], 5
0x14002d1de  mov     [rsp+58h+var_38], 4
0x14002d1e3  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002d1e8  call    cs:__imp_KeGetCurrentIrql
0x14002d1ef  nop     dword ptr [rax+rax+00h]
0x14002d1f4  test    al, al
0x14002d1f6  jnz     short loc_14002D216
0x14002d1f8  mov     rcx, [rbx+0B8h]; this
0x14002d1ff  test    rcx, rcx
0x14002d202  jz      short loc_14002D209
0x14002d204  call    ?OnConnectionStateChanged@A2dpInbandAudioDevice@@QEAAXXZ; A2dpInbandAudioDevice::OnConnectionStateChanged(void)
0x14002d209  mov     rcx, rbx; this
0x14002d20c  call    ?LogConnectionStatus@A2dpRole@@AEAAXXZ; A2dpRole::LogConnectionStatus(void)
0x14002d211  jmp     loc_14002D2F6
0x14002d216  mov     al, [rbx+5Ah]
0x14002d219  cmp     [rbx+5Bh], al
0x14002d21c  jnz     short loc_14002D236
0x14002d21e  mov     rax, [rbx+48h]
0x14002d222  cmp     qword ptr [rax+2E0h], 0
0x14002d22a  setnz   al
0x14002d22d  cmp     [rbx+5Ch], al
0x14002d230  jz      loc_14002D2F6
0x14002d236  mov     [rsp+58h+arg_8], 0
0x14002d23f  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x14002d244  test    eax, eax
0x14002d246  jz      short loc_14002D278
0x14002d248  lea     rcx, [rbx+110h]
0x14002d24f  lea     rdx, [rsp+58h+arg_10]
0x14002d254  call    ?acquire@operation_guard@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x14002d259  mov     rdx, rax
0x14002d25c  lea     rcx, [rsp+58h+arg_8]
0x14002d261  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x14002d266  lea     rcx, [rsp+58h+arg_10]
0x14002d26b  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d270  cmp     [rsp+58h+arg_8], 0
0x14002d276  jz      short loc_14002D2EC
0x14002d278  mov     rcx, [rbx+48h]
0x14002d27c  mov     rcx, [rcx+180h]; DeviceObject
0x14002d283  call    cs:__imp_IoAllocateWorkItem
0x14002d28a  nop     dword ptr [rax+rax+00h]
0x14002d28f  mov     rdi, rax
0x14002d292  test    rax, rax
0x14002d295  jz      short loc_14002D2D4
0x14002d297  mov     rcx, [rbx+48h]; this
0x14002d29b  lea     r8, aUpdatejackconn_0; "UpdateJackConnectionStatus"
0x14002d2a2  mov     edx, 6; __int16
0x14002d2a7  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x14002d2ac  mov     r9, rbx; Context
0x14002d2af  lea     rdx, ?UpdateJackConnectionStatusWorker@A2dpRole@@CAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14002d2b6  mov     r8d, 1; QueueType
0x14002d2bc  mov     rcx, rdi; IoWorkItem
0x14002d2bf  call    cs:__imp_IoQueueWorkItemEx
0x14002d2c6  nop     dword ptr [rax+rax+00h]
0x14002d2cb  mov     [rsp+58h+arg_8], 0
0x14002d2d4  mov     al, [rbx+5Ah]
0x14002d2d7  mov     [rbx+5Bh], al
0x14002d2da  mov     rax, [rbx+48h]
0x14002d2de  cmp     qword ptr [rax+2E0h], 0
0x14002d2e6  setnz   al
0x14002d2e9  mov     [rbx+5Ch], al
0x14002d2ec  lea     rcx, [rsp+58h+arg_8]
0x14002d2f1  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14002d2f6  mov     rbx, [rsp+58h+arg_0]
0x14002d2fb  add     rsp, 50h
0x14002d2ff  pop     rdi
0x14002d300  retn
```
