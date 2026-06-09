# Concurrency::details::InternalContextBase::Dispatch(Concurrency::DispatchState *)

- ea: `0x1803229f0`
- end: `0x180322bbc`
- name: `?Dispatch@InternalContextBase@details@Concurrency@@UEAAXPEAUDispatchState@3@@Z`
- size: `460`
- prototype: `void __fastcall(Concurrency::details::InternalContextBase *__hidden this, struct Concurrency::DispatchState *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180026210`
- `0x1803104b0`
- `0x180312b78`
- `0x1803164f4`
- `0x18031a89c`
- `0x18031b250`
- `0x18031ced0`
- `0x18031cf04`
- `0x18031fb54`
- `0x18031fb78`
- `0x180321434`
- `0x1803229c8`
- `0x1803229f0`
- `0x180322bbc`
- `0x180322c14`
- `0x1803230fc`
- `0x180323844`
- `0x180323b60`
- `0x180323cb4`
- `0x18032b080`
- `0x180358070`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180322a15`
- `KERNEL32!GetCurrentThreadId` at `0x180322a15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::InternalContextBase::Dispatch(
        Concurrency::details::InternalContextBase *this,
        struct Concurrency::DispatchState *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  bool v7; // r14
  bool IsVirtualProcessorRetired; // di
  _DWORD v9[4]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v10; // [rsp+38h] [rbp-28h]
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp-20h] BYREF
  char v12; // [rsp+90h] [rbp+30h] BYREF

  *((_DWORD *)this + 36) = GetCurrentThreadId();
  Concurrency::details::ContextBase::SetAsCurrentTls((Concurrency::details::InternalContextBase *)((char *)this + 16));
  v3 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 9) + 24LL))(*((_QWORD *)this + 9), &v12);
  v7 = !(unsigned int)Concurrency::SchedulerPolicy::GetPolicyValue(v3, 9)
    && (unsigned int)Concurrency::GetOSVersion(v5, v4, v6) == 6;
  Concurrency::SchedulerPolicy::~SchedulerPolicy((Concurrency::SchedulerPolicy *)&v12);
  if ( v7 )
    Concurrency::details::WinRT::RoInitialize(1);
  apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt((char *)this + 16);
  *((_DWORD *)this + 72) = 0;
  IsVirtualProcessorRetired = 0;
  if ( !Concurrency::details::InternalContextBase::ExecutedAssociatedChore(this)
    || !(IsVirtualProcessorRetired = Concurrency::details::InternalContextBase::IsVirtualProcessorRetired(this)) )
  {
    do
    {
      v9[0] = 0;
      v10 = 0;
      *((_BYTE *)this + 295) &= ~2u;
      if ( !*((_QWORD *)this + 33) )
      {
        apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt((char *)this + 16);
        Concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach((Concurrency::nested_scheduler_missing_detach *)pExceptionObject);
        throw (Concurrency::nested_scheduler_missing_detach *)pExceptionObject;
      }
      if ( !*((_BYTE *)this + 294)
        && Concurrency::details::VirtualProcessor::SafePoint(*((Concurrency::details::VirtualProcessor **)this + 33)) )
      {
        apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt((char *)this + 16);
        Concurrency::details::SchedulerBase::CommitSafePoints(*((Concurrency::details::SchedulerBase **)this + 9));
        apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt((char *)this + 16);
      }
      if ( Concurrency::details::InternalContextBase::WorkWasFound(this, (struct Concurrency::details::WorkItem *)v9) )
      {
        if ( v9[0] == 1 )
        {
          Concurrency::details::InternalContextBase::SwitchTo(this, v10, 0);
LABEL_20:
          IsVirtualProcessorRetired = 1;
          continue;
        }
        Concurrency::details::InternalContextBase::ExecuteChoreInline(this, (struct Concurrency::details::WorkItem *)v9);
        IsVirtualProcessorRetired = Concurrency::details::InternalContextBase::IsVirtualProcessorRetired(this);
      }
      else
      {
        if ( Concurrency::details::InternalContextBase::IsVirtualProcessorRetired(this) )
          goto LABEL_20;
        Concurrency::details::InternalContextBase::WaitForWork(this);
        if ( *((_BYTE *)this + 292) )
        {
          Concurrency::details::InternalContextBase::CleanupDispatchedContextOnCancel(this);
          goto LABEL_20;
        }
      }
    }
    while ( !IsVirtualProcessorRetired );
  }
  if ( v7 )
    Concurrency::details::WinRT::RoUninitialize();
  Concurrency::details::ContextBase::ClearContextTls((Concurrency::details::InternalContextBase *)((char *)this + 16));
}

```

## disassembly

```asm
0x1803229f0  mov     rax, rsp
0x1803229f3  push    rbp
0x1803229f4  push    rdi
0x1803229f5  push    r14
0x1803229f7  mov     rbp, rsp
0x1803229fa  sub     rsp, 60h
0x1803229fe  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180322a06  mov     [rax+10h], rbx
0x180322a0a  mov     [rax+20h], rsi
0x180322a0e  mov     rbx, rcx
0x180322a11  and     [rbp+arg_0], 0
0x180322a15  call    cs:__imp_GetCurrentThreadId
0x180322a1b  mov     [rbx+90h], eax
0x180322a21  lea     rsi, [rbx+10h]
0x180322a25  mov     rcx, rsi; this
0x180322a28  call    ?SetAsCurrentTls@ContextBase@details@Concurrency@@IEAAXXZ; Concurrency::details::ContextBase::SetAsCurrentTls(void)
0x180322a2d  mov     rcx, [rbx+48h]
0x180322a31  mov     rax, [rcx]
0x180322a34  lea     rdx, [rbp+arg_10]
0x180322a38  mov     rax, [rax+18h]
0x180322a3c  call    cs:__guard_dispatch_icall_fptr
0x180322a42  nop
0x180322a43  mov     [rbp+arg_0], 1
0x180322a4a  mov     edx, 9
0x180322a4f  mov     rcx, rax
0x180322a52  call    ?GetPolicyValue@SchedulerPolicy@Concurrency@@QEBAIW4PolicyElementKey@2@@Z; Concurrency::SchedulerPolicy::GetPolicyValue(Concurrency::PolicyElementKey)
0x180322a57  test    eax, eax
0x180322a59  jnz     short loc_180322A6A
0x180322a5b  call    ?GetOSVersion@Concurrency@@YA?AW4OSVersion@IResourceManager@1@XZ; Concurrency::GetOSVersion(void)
0x180322a60  cmp     eax, 6
0x180322a63  jnz     short loc_180322A6A
0x180322a65  mov     r14b, 1
0x180322a68  jmp     short loc_180322A6D
0x180322a6a  xor     r14b, r14b
0x180322a6d  lea     rcx, [rbp+arg_10]; this
0x180322a71  call    ??1SchedulerPolicy@Concurrency@@QEAA@XZ; Concurrency::SchedulerPolicy::~SchedulerPolicy(void)
0x180322a76  test    r14b, r14b
0x180322a79  jz      short loc_180322A85
0x180322a7b  mov     ecx, 1
0x180322a80  call    ?RoInitialize@WinRT@details@Concurrency@@SAJW4RO_INIT_TYPE@@@Z; Concurrency::details::WinRT::RoInitialize(RO_INIT_TYPE)
0x180322a85  mov     rcx, rsi
0x180322a88  call    ?readMapEnd_virt@?$TVirtualProtocol@V?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@VTProtocolDefaults@234@@protocol@thrift@apache@@UEAAIXZ; apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt(void)
0x180322a8d  and     dword ptr [rbx+120h], 0
0x180322a94  xor     dil, dil
0x180322a97  mov     rcx, rbx; this
0x180322a9a  call    ?ExecutedAssociatedChore@InternalContextBase@details@Concurrency@@IEAA_NXZ; Concurrency::details::InternalContextBase::ExecutedAssociatedChore(void)
0x180322a9f  test    al, al
0x180322aa1  jz      short loc_180322AB6
0x180322aa3  mov     rcx, rbx; this
0x180322aa6  call    ?IsVirtualProcessorRetired@InternalContextBase@details@Concurrency@@IEAA_NXZ; Concurrency::details::InternalContextBase::IsVirtualProcessorRetired(void)
0x180322aab  mov     dil, al
0x180322aae  test    al, al
0x180322ab0  jnz     loc_180322B74
0x180322ab6  and     [rbp+var_38], 0
0x180322aba  and     [rbp+var_28], 0
0x180322abf  and     byte ptr [rbx+127h], 0FDh
0x180322ac6  mov     rcx, [rbx+108h]
0x180322acd  test    rcx, rcx
0x180322ad0  jz      loc_180322B9A
0x180322ad6  cmp     byte ptr [rbx+126h], 0
0x180322add  jnz     short loc_180322B08
0x180322adf  mov     rcx, [rbx+108h]; this
0x180322ae6  call    ?SafePoint@VirtualProcessor@details@Concurrency@@QEAA_NXZ; Concurrency::details::VirtualProcessor::SafePoint(void)
0x180322aeb  test    al, al
0x180322aed  jz      short loc_180322B08
0x180322aef  mov     rcx, rsi
0x180322af2  call    ?readMapEnd_virt@?$TVirtualProtocol@V?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@VTProtocolDefaults@234@@protocol@thrift@apache@@UEAAIXZ; apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt(void)
0x180322af7  mov     rcx, [rbx+48h]; this
0x180322afb  call    ?CommitSafePoints@SchedulerBase@details@Concurrency@@QEAAXXZ; Concurrency::details::SchedulerBase::CommitSafePoints(void)
0x180322b00  mov     rcx, rsi
0x180322b03  call    ?readMapEnd_virt@?$TVirtualProtocol@V?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@VTProtocolDefaults@234@@protocol@thrift@apache@@UEAAIXZ; apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt(void)
0x180322b08  lea     rdx, [rbp+var_38]; struct Concurrency::details::WorkItem *
0x180322b0c  mov     rcx, rbx; this
0x180322b0f  call    ?WorkWasFound@InternalContextBase@details@Concurrency@@IEAA_NPEAVWorkItem@23@@Z; Concurrency::details::InternalContextBase::WorkWasFound(Concurrency::details::WorkItem *)
0x180322b14  mov     rcx, rbx; this
0x180322b17  test    al, al
0x180322b19  jz      short loc_180322B45
0x180322b1b  cmp     [rbp+var_38], 1
0x180322b1f  jnz     short loc_180322B2F
0x180322b21  xor     r8d, r8d
0x180322b24  mov     rdx, [rbp+var_28]
0x180322b28  call    ?SwitchTo@InternalContextBase@details@Concurrency@@IEAAXPEAV123@W4ReasonForSwitch@123@@Z; Concurrency::details::InternalContextBase::SwitchTo(Concurrency::details::InternalContextBase *,Concurrency::details::InternalContextBase::ReasonForSwitch)
0x180322b2d  jmp     short loc_180322B68
0x180322b2f  lea     rdx, [rbp+var_38]; struct Concurrency::details::WorkItem *
0x180322b33  call    ?ExecuteChoreInline@InternalContextBase@details@Concurrency@@IEAAXPEAVWorkItem@23@@Z; Concurrency::details::InternalContextBase::ExecuteChoreInline(Concurrency::details::WorkItem *)
0x180322b38  mov     rcx, rbx; this
0x180322b3b  call    ?IsVirtualProcessorRetired@InternalContextBase@details@Concurrency@@IEAA_NXZ; Concurrency::details::InternalContextBase::IsVirtualProcessorRetired(void)
0x180322b40  mov     dil, al
0x180322b43  jmp     short loc_180322B6B
0x180322b45  call    ?IsVirtualProcessorRetired@InternalContextBase@details@Concurrency@@IEAA_NXZ; Concurrency::details::InternalContextBase::IsVirtualProcessorRetired(void)
0x180322b4a  test    al, al
0x180322b4c  jnz     short loc_180322B68
0x180322b4e  mov     rcx, rbx; this
0x180322b51  call    ?WaitForWork@InternalContextBase@details@Concurrency@@IEAAXXZ; Concurrency::details::InternalContextBase::WaitForWork(void)
0x180322b56  mov     al, [rbx+124h]
0x180322b5c  test    al, al
0x180322b5e  jz      short loc_180322B6B
0x180322b60  mov     rcx, rbx; this
0x180322b63  call    ?CleanupDispatchedContextOnCancel@InternalContextBase@details@Concurrency@@IEAAXXZ; Concurrency::details::InternalContextBase::CleanupDispatchedContextOnCancel(void)
0x180322b68  mov     dil, 1
0x180322b6b  test    dil, dil
0x180322b6e  jz      loc_180322AB6
0x180322b74  test    r14b, r14b
0x180322b77  jz      short loc_180322B7E
0x180322b79  call    ?RoUninitialize@WinRT@details@Concurrency@@SAXXZ; Concurrency::details::WinRT::RoUninitialize(void)
0x180322b7e  mov     rcx, rsi; this
0x180322b81  lea     r11, [rsp+60h+var_s0]
0x180322b86  mov     rbx, [r11+28h]
0x180322b8a  mov     rsi, [r11+38h]
0x180322b8e  mov     rsp, r11
0x180322b91  pop     r14
0x180322b93  pop     rdi
0x180322b94  pop     rbp
0x180322b95  jmp     ?ClearContextTls@ContextBase@details@Concurrency@@AEAAXXZ; Concurrency::details::ContextBase::ClearContextTls(void)
0x180322b9a  mov     rcx, rsi
0x180322b9d  call    ?readMapEnd_virt@?$TVirtualProtocol@V?$TCompactProtocolT@VTTransport@transport@thrift@apache@@@protocol@thrift@apache@@VTProtocolDefaults@234@@protocol@thrift@apache@@UEAAIXZ; apache::thrift::protocol::TVirtualProtocol<apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TTransport>,apache::thrift::protocol::TProtocolDefaults>::readMapEnd_virt(void)
0x180322ba2  lea     rcx, [rbp+pExceptionObject]; this
0x180322ba6  call    ??0nested_scheduler_missing_detach@Concurrency@@QEAA@XZ; Concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach(void)
0x180322bab  lea     rdx, _TI2?AVnested_scheduler_missing_detach@Concurrency@@; pThrowInfo
0x180322bb2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180322bb6  call    _CxxThrowException
```
