# A2dpRole::UpdateFilterDescriptorChannelsAndSamplerateWorkItem(void *,void *,_IO_WORKITEM *)

- ea: `0x14007a7b0`
- end: `0x14007a8e8`
- name: `?UpdateFilterDescriptorChannelsAndSamplerateWorkItem@A2dpRole@@_C2PAGE@@AXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `312`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140006380`
- `0x140006410`
- `0x140006b70`
- `0x14000f570`
- `0x14001df98`
- `0x14001e4a4`
- `0x14002d8e8`
- `0x14005c870`
- `0x14007a7b0`
- `0x14007d1d8`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14007a8b0`
- `ntoskrnl!IoFreeWorkItem` at `0x14007a8b0`

## string_xrefs

- `0x14007a8c0`: `UpdateFilterDescriptorChannelsAndSamplerateWorkItem`

## pseudocode

```c
void __fastcall A2dpRole::UpdateFilterDescriptorChannelsAndSamplerateWorkItem(
        PVOID IoObject,
        A2dpInbandAudioDevice **Context,
        PIO_WORKITEM IoWorkItem)
{
  int v5; // edx
  int v6; // r8d
  __int64 v7; // rsi
  int v8; // ebx
  int v9; // eax
  __int64 v10; // [rsp+40h] [rbp-38h] BYREF
  utl::_RefCountBase *v11; // [rsp+48h] [rbp-30h]
  __int64 v12; // [rsp+88h] [rbp+10h] BYREF

  v12 = 0;
  if ( (unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline(IoObject) )
    _reset___unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAAXPEAVoperation_guard_3__Z(
      &v12,
      Context + 34);
  A2dpRole::GetCurrentSelectedCodec(Context, &v10);
  v7 = v10;
  if ( v10 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 104LL))(v10);
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 96LL))(v7);
    A2dpInbandAudioDevice::UpdateChannelsAndSamplerate(Context[23], v8, v9);
  }
  else
  {
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v6,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        5,
        65,
        (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids);
    }
  }
  if ( v11 )
    utl::_RefCountBase::_DecStrong(v11);
  IoFreeWorkItem(IoWorkItem);
  A2DP_Device::Release(Context[9], 7, "UpdateFilterDescriptorChannelsAndSamplerateWorkItem");
  __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v12);
}

```

## disassembly

```asm
0x14007a7b0  mov     rax, rsp
0x14007a7b3  push    rbx
0x14007a7b4  push    rbp
0x14007a7b5  push    rsi
0x14007a7b6  push    rdi
0x14007a7b7  sub     rsp, 58h
0x14007a7bb  mov     rbp, r8
0x14007a7be  mov     qword ptr [rax+10h], 0
0x14007a7c6  mov     rdi, rdx
0x14007a7c9  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x14007a7ce  test    eax, eax
0x14007a7d0  jz      short loc_14007A7E6
0x14007a7d2  lea     rdx, [rdi+110h]
0x14007a7d9  lea     rcx, [rsp+78h+arg_8]
0x14007a7e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAVoperation_guard@3@@Z
0x14007a7e6  lea     rdx, [rsp+78h+var_38]
0x14007a7eb  mov     rcx, rdi
0x14007a7ee  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x14007a7f3  mov     rsi, [rsp+78h+var_38]
0x14007a7f8  test    rsi, rsi
0x14007a7fb  jz      short loc_14007A830
0x14007a7fd  mov     rax, [rsi]
0x14007a800  mov     rcx, rsi
0x14007a803  mov     rax, [rax+68h]
0x14007a807  call    _guard_dispatch_icall
0x14007a80c  mov     rdx, [rsi]
0x14007a80f  mov     ebx, eax
0x14007a811  mov     rcx, rsi
0x14007a814  mov     rax, [rdx+60h]
0x14007a818  call    _guard_dispatch_icall
0x14007a81d  mov     rcx, [rdi+0B8h]; this
0x14007a824  mov     r8d, eax; int
0x14007a827  mov     edx, ebx; int
0x14007a829  call    ?UpdateChannelsAndSamplerate@A2dpInbandAudioDevice@@QEAAXHH@Z; A2dpInbandAudioDevice::UpdateChannelsAndSamplerate(int,int)
0x14007a82e  jmp     short loc_14007A89E
0x14007a830  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a837  lea     rax, WPP_GLOBAL_Control
0x14007a83e  cmp     rcx, rax
0x14007a841  jz      short loc_14007A854
0x14007a843  mov     eax, [rcx+2Ch]
0x14007a846  test    al, 10h
0x14007a848  jz      short loc_14007A854
0x14007a84a  cmp     byte ptr [rcx+29h], 3
0x14007a84e  jb      short loc_14007A854
0x14007a850  mov     dl, 1
0x14007a852  jmp     short loc_14007A856
0x14007a854  xor     dl, dl
0x14007a856  lea     rax, WPP_RECORDER_INITIALIZED
0x14007a85d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007a864  setnz   r8b
0x14007a868  test    dl, dl
0x14007a86a  jnz     short loc_14007A871
0x14007a86c  test    r8b, r8b
0x14007a86f  jz      short loc_14007A89E
0x14007a871  mov     r9, [rcx+40h]
0x14007a875  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14007a87c  mov     rcx, [rcx+18h]
0x14007a880  mov     [rsp+78h+var_40], rax
0x14007a885  mov     [rsp+78h+var_48], 41h ; 'A'
0x14007a88c  mov     [rsp+78h+var_50], 5
0x14007a894  mov     [rsp+78h+var_58], 3
0x14007a899  call    WPP_RECORDER_AND_TRACE_SF_
0x14007a89e  mov     rcx, [rsp+78h+var_30]; this
0x14007a8a3  test    rcx, rcx
0x14007a8a6  jz      short loc_14007A8AD
0x14007a8a8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007a8ad  mov     rcx, rbp; IoWorkItem
0x14007a8b0  call    cs:__imp_IoFreeWorkItem
0x14007a8b7  nop     dword ptr [rax+rax+00h]
0x14007a8bc  mov     rcx, [rdi+48h]; this
0x14007a8c0  lea     r8, aUpdatefilterde; "UpdateFilterDescriptorChannelsAndSample"...
0x14007a8c7  mov     edx, 7; __int16
0x14007a8cc  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x14007a8d1  lea     rcx, [rsp+78h+arg_8]
0x14007a8d9  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007a8de  add     rsp, 58h
0x14007a8e2  pop     rdi
0x14007a8e3  pop     rsi
0x14007a8e4  pop     rbp
0x14007a8e5  pop     rbx
0x14007a8e6  retn
```
