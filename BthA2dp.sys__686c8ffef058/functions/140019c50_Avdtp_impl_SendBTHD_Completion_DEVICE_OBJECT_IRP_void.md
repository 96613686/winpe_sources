# Avdtp_impl::SendBTHD_Completion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140019c50`
- end: `0x140019f55`
- name: `?SendBTHD_Completion@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `773`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000f300`
- `0x14000f7e0`
- `0x140019c50`
- `0x14001e284`
- `0x14002d890`
- `0x140049a40`
- `0x14004a244`
- `0x14004f964`
- `0x140053688`
- `0x140053b24`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019e65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019eee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019eee`
- `ntoskrnl!IoFreeIrp` at `0x140019eda`
- `ntoskrnl!IoFreeIrp` at `0x140019eda`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019eaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019eaf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019e7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019e7b`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::SendBTHD_Completion(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        KSPIN_LOCK *Context,
        __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // edx
  int FullCreateOptions_high; // edx
  int v15; // r14d
  void (__fastcall *CompletionRoutine)(PDEVICE_OBJECT, PIRP, KSPIN_LOCK); // rax
  KSPIN_LOCK *v17; // rbx
  void *v18; // rcx
  KIRQL v19; // r9
  KSPIN_LOCK *v20; // rcx
  KSPIN_LOCK *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  KSPIN_LOCK **v26; // rax
  __int64 v28; // [rsp+80h] [rbp-58h] BYREF
  char v29; // [rsp+90h] [rbp-48h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(DeviceObject, Irp, Context, a4) )
  {
    GetBtAddressAndChannelHandle(&v28, SecurityContext);
    if ( v29 )
    {
      LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        FullCreateOptions_high = HIWORD(SecurityContext->FullCreateOptions);
        LOBYTE(FullCreateOptions_high) = v10;
        WPP_RECORDER_AND_TRACE_SF_Lbth_addrqddqq(
          WPP_GLOBAL_Control->AttachedDevice,
          FullCreateOptions_high,
          v11,
          WPP_GLOBAL_Control->DeviceExtension);
      }
    }
    else
    {
      LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = v10;
        WPP_RECORDER_AND_TRACE_SF_Lddqq(
          WPP_GLOBAL_Control->AttachedDevice,
          v9,
          v11,
          WPP_GLOBAL_Control->DeviceExtension);
      }
    }
  }
  else
  {
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = HIWORD(SecurityContext->FullCreateOptions);
      LOBYTE(v13) = v10;
      WPP_RECORDER_AND_TRACE_SF_LdD(WPP_GLOBAL_Control->AttachedDevice, v13, v11, WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v10, v9, v11, v12) )
    v15 = Avdtp_impl::GetRemoveLockClient(HIWORD(SecurityContext->FullCreateOptions));
  else
    v15 = 0;
  CompletionRoutine = (void (__fastcall *)(PDEVICE_OBJECT, PIRP, KSPIN_LOCK))CurrentStackLocation->CompletionRoutine;
  v17 = (KSPIN_LOCK *)CurrentStackLocation->Context;
  if ( CompletionRoutine )
    CompletionRoutine(DeviceObject, Irp, v17[4]);
  v18 = (void *)v17[5];
  if ( v18 )
    ExFreePoolWithTag(v18, 0x41564433u);
  v19 = KeAcquireSpinLockRaiseToDpc(Context + 222);
  v20 = (KSPIN_LOCK *)Context[220];
  if ( v20 != Context + 220 )
  {
    while ( 1 )
    {
      v21 = (KSPIN_LOCK *)*v20;
      if ( v20 == v17 )
        break;
      v20 = (KSPIN_LOCK *)*v20;
      if ( v21 == Context + 220 )
        goto LABEL_37;
    }
    if ( (KSPIN_LOCK *)v21[1] != v20 || (v26 = (KSPIN_LOCK **)v20[1], *v26 != v20) )
      __fastfail(3u);
    *v26 = v21;
    v21[1] = (KSPIN_LOCK)v26;
  }
LABEL_37:
  KeReleaseSpinLock(Context + 222, v19);
  ((void (__fastcall *)(PIO_SECURITY_CONTEXT))Context[132])(SecurityContext);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 6, 0xFFFFFFFF) == 1 )
  {
    IoFreeIrp(Irp);
    ExFreePoolWithTag(v17, 0x41564454u);
  }
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v23, v22, v24, v25) )
    Avdtp_impl::ReleaseRemoveLock((__int64)Context, v15);
  else
    Avdtp_impl::ReleaseRemoveLock((Avdtp_impl *)Context);
  Avdtp_impl::InterfaceDereference((Avdtp_impl *)Context, Irp);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140019c50  push    rbx
0x140019c52  push    rbp
0x140019c53  push    rsi
0x140019c54  push    rdi
0x140019c55  push    r14
0x140019c57  push    r15
0x140019c59  sub     rsp, 0A8h
0x140019c60  mov     rbx, [rdx+0B8h]
0x140019c67  mov     rdi, r8
0x140019c6a  mov     rbp, rdx
0x140019c6d  mov     r15, rcx
0x140019c70  mov     rsi, [rbx+8]
0x140019c74  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140019c79  test    eax, eax
0x140019c7b  jnz     short loc_140019CEF
0x140019c7d  mov     r10, cs:WPP_GLOBAL_Control
0x140019c84  lea     rax, WPP_GLOBAL_Control
0x140019c8b  cmp     r10, rax
0x140019c8e  jz      short loc_140019CA3
0x140019c90  mov     eax, [r10+2Ch]
0x140019c94  test    al, 8
0x140019c96  jz      short loc_140019CA3
0x140019c98  cmp     byte ptr [r10+29h], 4
0x140019c9d  jb      short loc_140019CA3
0x140019c9f  mov     cl, 1
0x140019ca1  jmp     short loc_140019CA5
0x140019ca3  xor     cl, cl
0x140019ca5  lea     rax, WPP_RECORDER_INITIALIZED
0x140019cac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019cb3  setnz   r8b
0x140019cb7  test    cl, cl
0x140019cb9  jnz     short loc_140019CC4
0x140019cbb  test    r8b, r8b
0x140019cbe  jz      loc_140019E21
0x140019cc4  movzx   eax, byte ptr [rsi+20h]
0x140019cc8  movzx   edx, word ptr [rsi+16h]
0x140019ccc  mov     r9, [r10+40h]
0x140019cd0  mov     dword ptr [rsp+0D8h+var_88], eax
0x140019cd4  mov     eax, [rsi+1Ch]
0x140019cd7  mov     dword ptr [rsp+0D8h+var_90], eax
0x140019cdb  mov     [rsp+0D8h+var_98], edx
0x140019cdf  mov     dl, cl
0x140019ce1  mov     rcx, [r10+18h]
0x140019ce5  call    WPP_RECORDER_AND_TRACE_SF_LdD
0x140019cea  jmp     loc_140019E21
0x140019cef  mov     rdx, rsi
0x140019cf2  lea     rcx, [rsp+0D8h+var_58]
0x140019cfa  call    ?GetBtAddressAndChannelHandle@@YA?AV?$optional@U?$pair@_KPEAX@utl@@@utl@@PEAU_BRB@@@Z; GetBtAddressAndChannelHandle(_BRB *)
0x140019cff  cmp     [rsp+0D8h+var_48], 0
0x140019d07  jz      loc_140019DA6
0x140019d0d  mov     r10, cs:WPP_GLOBAL_Control
0x140019d14  lea     rax, WPP_GLOBAL_Control
0x140019d1b  cmp     r10, rax
0x140019d1e  jz      short loc_140019D33
0x140019d20  mov     eax, [r10+2Ch]
0x140019d24  test    al, 8
0x140019d26  jz      short loc_140019D33
0x140019d28  cmp     byte ptr [r10+29h], 4
0x140019d2d  jb      short loc_140019D33
0x140019d2f  mov     cl, 1
0x140019d31  jmp     short loc_140019D35
0x140019d33  xor     cl, cl
0x140019d35  lea     rax, WPP_RECORDER_INITIALIZED
0x140019d3c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019d43  setnz   r8b
0x140019d47  test    cl, cl
0x140019d49  jnz     short loc_140019D54
0x140019d4b  test    r8b, r8b
0x140019d4e  jz      loc_140019E21
0x140019d54  mov     eax, [rsi+1Ch]
0x140019d57  movzx   edx, word ptr [rsi+16h]
0x140019d5b  mov     r9, [r10+40h]
0x140019d5f  mov     [rsp+0D8h+var_68], rdi
0x140019d64  mov     [rsp+0D8h+var_70], rsi
0x140019d69  mov     dword ptr [rsp+0D8h+var_78], eax
0x140019d6d  mov     eax, [rbp+30h]
0x140019d70  mov     dword ptr [rsp+0D8h+var_80], eax
0x140019d74  mov     rax, [rsp+0D8h+var_50]
0x140019d7c  mov     [rsp+0D8h+var_88], rax
0x140019d81  mov     rax, [rsp+0D8h+var_58]
0x140019d89  mov     [rsp+0D8h+var_90], rax
0x140019d8e  mov     [rsp+0D8h+var_98], edx
0x140019d92  mov     dl, cl
0x140019d94  mov     rcx, [r10+18h]
0x140019d98  mov     [rsp+0D8h+var_A8], 3Dh ; '='
0x140019d9f  call    WPP_RECORDER_AND_TRACE_SF_Lbth_addrqddqq
0x140019da4  jmp     short loc_140019E21
0x140019da6  mov     r10, cs:WPP_GLOBAL_Control
0x140019dad  lea     rax, WPP_GLOBAL_Control
0x140019db4  cmp     r10, rax
0x140019db7  jz      short loc_140019DCC
0x140019db9  mov     eax, [r10+2Ch]
0x140019dbd  test    al, 8
0x140019dbf  jz      short loc_140019DCC
0x140019dc1  cmp     byte ptr [r10+29h], 4
0x140019dc6  jb      short loc_140019DCC
0x140019dc8  mov     cl, 1
0x140019dca  jmp     short loc_140019DCE
0x140019dcc  xor     cl, cl
0x140019dce  lea     rax, WPP_RECORDER_INITIALIZED
0x140019dd5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019ddc  setnz   r8b
0x140019de0  test    cl, cl
0x140019de2  jnz     short loc_140019DE9
0x140019de4  test    r8b, r8b
0x140019de7  jz      short loc_140019E21
0x140019de9  mov     eax, [rsi+1Ch]
0x140019dec  mov     dl, cl
0x140019dee  movzx   r9d, word ptr [rsi+16h]
0x140019df3  mov     rcx, [r10+18h]
0x140019df7  mov     [rsp+0D8h+var_78], rdi
0x140019dfc  mov     [rsp+0D8h+var_80], rsi
0x140019e01  mov     dword ptr [rsp+0D8h+var_88], eax
0x140019e05  mov     eax, [rbp+30h]
0x140019e08  mov     dword ptr [rsp+0D8h+var_90], eax
0x140019e0c  mov     [rsp+0D8h+var_98], r9d
0x140019e11  mov     r9, [r10+40h]
0x140019e15  mov     [rsp+0D8h+var_A8], 3Eh ; '>'
0x140019e1c  call    WPP_RECORDER_AND_TRACE_SF_Lddqq
0x140019e21  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140019e26  test    eax, eax
0x140019e28  jnz     short loc_140019E2F
0x140019e2a  xor     r14d, r14d
0x140019e2d  jmp     short loc_140019E3B
0x140019e2f  movzx   ecx, word ptr [rsi+16h]
0x140019e33  call    ?GetRemoveLockClient@Avdtp_impl@@CA?AW4RemoveLockClient@1@G@Z; Avdtp_impl::GetRemoveLockClient(ushort)
0x140019e38  mov     r14d, eax
0x140019e3b  mov     rax, [rbx+38h]
0x140019e3f  mov     rbx, [rbx+40h]
0x140019e43  test    rax, rax
0x140019e46  jz      short loc_140019E57
0x140019e48  mov     r8, [rbx+20h]
0x140019e4c  mov     rdx, rbp
0x140019e4f  mov     rcx, r15
0x140019e52  call    _guard_dispatch_icall
0x140019e57  mov     rcx, [rbx+28h]; P
0x140019e5b  test    rcx, rcx
0x140019e5e  jz      short loc_140019E71
0x140019e60  mov     edx, 41564433h; Tag
0x140019e65  call    cs:__imp_ExFreePoolWithTag
0x140019e6c  nop     dword ptr [rax+rax+00h]
0x140019e71  lea     r15, [rdi+6F0h]
0x140019e78  mov     rcx, r15; SpinLock
0x140019e7b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019e82  nop     dword ptr [rax+rax+00h]
0x140019e87  lea     r8, [rdi+6E0h]
0x140019e8e  mov     r9b, al
0x140019e91  mov     rcx, [r8]
0x140019e94  cmp     rcx, r8
0x140019e97  jz      short loc_140019EA9
0x140019e99  mov     rdx, [rcx]
0x140019e9c  cmp     rcx, rbx
0x140019e9f  jz      short loc_140019F0D
0x140019ea1  mov     rcx, rdx
0x140019ea4  cmp     rdx, r8
0x140019ea7  jnz     short loc_140019E99
0x140019ea9  mov     dl, r9b; NewIrql
0x140019eac  mov     rcx, r15; SpinLock
0x140019eaf  call    cs:__imp_KeReleaseSpinLock
0x140019eb6  nop     dword ptr [rax+rax+00h]
0x140019ebb  mov     rax, [rdi+420h]
0x140019ec2  mov     rcx, rsi
0x140019ec5  call    _guard_dispatch_icall
0x140019eca  or      eax, 0FFFFFFFFh
0x140019ecd  lock xadd [rbx+18h], eax
0x140019ed2  cmp     eax, 1
0x140019ed5  jnz     short loc_140019EFA
0x140019ed7  mov     rcx, rbp; Irp
0x140019eda  call    cs:__imp_IoFreeIrp
0x140019ee1  nop     dword ptr [rax+rax+00h]
0x140019ee6  mov     edx, 41564454h; Tag
0x140019eeb  mov     rcx, rbx; P
0x140019eee  call    cs:__imp_ExFreePoolWithTag
0x140019ef5  nop     dword ptr [rax+rax+00h]
0x140019efa  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140019eff  mov     rcx, rdi; this
0x140019f02  test    eax, eax
0x140019f04  jnz     short loc_140019F2C
0x140019f06  call    ?ReleaseRemoveLock@Avdtp_impl@@QEAAXXZ; Avdtp_impl::ReleaseRemoveLock(void)
0x140019f0b  jmp     short loc_140019F34
0x140019f0d  cmp     [rdx+8], rcx
0x140019f11  jnz     short loc_140019F25
0x140019f13  mov     rax, [rcx+8]
0x140019f17  cmp     [rax], rcx
0x140019f1a  jnz     short loc_140019F25
0x140019f1c  mov     [rax], rdx
0x140019f1f  mov     [rdx+8], rax
0x140019f23  jmp     short loc_140019EA9
0x140019f25  mov     ecx, 3
0x140019f2a  int     29h; Win8: RtlFailFast(ecx)
0x140019f2c  mov     edx, r14d
0x140019f2f  call    ?ReleaseRemoveLock@Avdtp_impl@@QEAAXW4RemoveLockClient@1@@Z; Avdtp_impl::ReleaseRemoveLock(Avdtp_impl::RemoveLockClient)
0x140019f34  mov     rdx, rbp; void *
0x140019f37  mov     rcx, rdi; this
0x140019f3a  call    ?InterfaceDereference@Avdtp_impl@@AEAAXPEAX@Z; Avdtp_impl::InterfaceDereference(void *)
0x140019f3f  mov     eax, 0C0000016h
0x140019f44  add     rsp, 0A8h
0x140019f4b  pop     r15
0x140019f4d  pop     r14
0x140019f4f  pop     rdi
0x140019f50  pop     rsi
0x140019f51  pop     rbp
0x140019f52  pop     rbx
0x140019f53  retn
```
