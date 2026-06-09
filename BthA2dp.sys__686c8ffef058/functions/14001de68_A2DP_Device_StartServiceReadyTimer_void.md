# A2DP_Device::StartServiceReadyTimer(void)

- ea: `0x14001de68`
- end: `0x14001df4c`
- name: `?StartServiceReadyTimer@A2DP_Device@@AEAAXXZ`
- size: `228`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400320a8`

## callees

- `0x140003530`
- `0x14000e240`
- `0x14001de68`
- `0x14001df54`
- `0x14001df98`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x14001df2f`
- `ntoskrnl!KeSetTimer` at `0x14001df2f`

## string_xrefs

- `0x14001df0b`: `StartServiceReadyTimer`

## pseudocode

```c
void __fastcall A2DP_Device::StartServiceReadyTimer(A2DP_Device *this)
{
  bool v2; // dl
  __int64 v3; // [rsp+60h] [rbp+8h] BYREF

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
      39,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this);
  wil::operation_guard::acquire((char *)this + 3376, &v3);
  if ( v3 )
  {
    v3 = 0;
    A2DP_Device::AddRef(this, 1, "StartServiceReadyTimer");
    KeSetTimer((PKTIMER)((char *)this + 3152), (LARGE_INTEGER)-100000000LL, (PKDPC)((char *)this + 3216));
  }
  __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v3);
}

```

## disassembly

```asm
0x14001de68  push    rbx
0x14001de6a  sub     rsp, 50h
0x14001de6e  mov     rbx, rcx
0x14001de71  mov     rcx, cs:WPP_GLOBAL_Control
0x14001de78  lea     rax, WPP_GLOBAL_Control
0x14001de7f  cmp     rcx, rax
0x14001de82  jz      short loc_14001DE95
0x14001de84  mov     eax, [rcx+2Ch]
0x14001de87  test    al, 10h
0x14001de89  jz      short loc_14001DE95
0x14001de8b  cmp     byte ptr [rcx+29h], 4
0x14001de8f  jb      short loc_14001DE95
0x14001de91  mov     dl, 1
0x14001de93  jmp     short loc_14001DE97
0x14001de95  xor     dl, dl
0x14001de97  lea     rax, WPP_RECORDER_INITIALIZED
0x14001de9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dea5  setnz   r8b
0x14001dea9  test    dl, dl
0x14001deab  jnz     short loc_14001DEB2
0x14001dead  test    r8b, r8b
0x14001deb0  jz      short loc_14001DEE4
0x14001deb2  mov     r9, [rcx+40h]
0x14001deb6  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001debd  mov     rcx, [rcx+18h]
0x14001dec1  mov     [rsp+58h+var_18], rbx
0x14001dec6  mov     [rsp+58h+var_20], rax
0x14001decb  mov     [rsp+58h+var_28], 27h ; '''
0x14001ded2  mov     [rsp+58h+var_30], 5
0x14001deda  mov     [rsp+58h+var_38], 4
0x14001dedf  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001dee4  lea     rcx, [rbx+0D30h]
0x14001deeb  lea     rdx, [rsp+58h+arg_0]
0x14001def0  call    ?acquire@operation_guard@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x14001def5  cmp     [rsp+58h+arg_0], 0
0x14001defb  jz      short loc_14001DF3B
0x14001defd  mov     edx, 1; __int16
0x14001df02  mov     [rsp+58h+arg_0], 0
0x14001df0b  lea     r8, aStartservicere; "StartServiceReadyTimer"
0x14001df12  mov     rcx, rbx; this
0x14001df15  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x14001df1a  lea     r8, [rbx+0C90h]; Dpc
0x14001df21  mov     rdx, 0FFFFFFFFFA0A1F00h; DueTime
0x14001df28  lea     rcx, [rbx+0C50h]; Timer
0x14001df2f  call    cs:__imp_KeSetTimer
0x14001df36  nop     dword ptr [rax+rax+00h]
0x14001df3b  lea     rcx, [rsp+58h+arg_0]
0x14001df40  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001df45  add     rsp, 50h
0x14001df49  pop     rbx
0x14001df4a  retn
```
