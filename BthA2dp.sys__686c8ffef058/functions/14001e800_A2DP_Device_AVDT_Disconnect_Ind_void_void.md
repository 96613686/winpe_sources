# A2DP_Device::AVDT_Disconnect_Ind(void *,void *)

- ea: `0x14001e800`
- end: `0x14001e93a`
- name: `?AVDT_Disconnect_Ind@A2DP_Device@@CAJPEAX0@Z`
- size: `314`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x140003530`
- `0x140006410`
- `0x140007374`
- `0x1400077e0`
- `0x14001e800`
- `0x14001eb08`
- `0x14001ee94`
- `0x14001f2b8`
- `0x14001f32c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001e8bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e8bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e8a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e8a4`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14001e8ff`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14001e8ff`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Disconnect_Ind(void *a1, void *a2)
{
  int v2; // edx
  KSPIN_LOCK *v3; // rsi
  __int64 v4; // r8
  KIRQL v5; // bl
  __int64 v6; // r8
  _QWORD *v8; // [rsp+50h] [rbp-18h] BYREF
  utl::_RefCountBase *v9; // [rsp+58h] [rbp-10h]

  v3 = (KSPIN_LOCK *)A2DP_Device::CheckCallbackParms(a1, a2);
  LOBYTE(v2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      v4,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      95,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v3);
  A2DP_Device::SetLastAvdtpActivity(v3, 7, v4);
  v5 = KeAcquireSpinLockRaiseToDpc(v3 + 87);
  A2DP_Device::SetConnectionClosedLocked((A2DP_Device *)v3);
  KeReleaseSpinLock(v3 + 87, v5);
  A2DP_Device::ResetAllOnDisconnect((A2DP_Device *)v3);
  A2DP_Device::SetAvdtpConnectionStatus(v3, 2);
  A2DP_Device::GetMPMContext(v3, &v8);
  if ( v8 )
    BtaMpmUpdateConnectionStatus(*v8, 0, 0);
  if ( v9 )
    utl::_RefCountBase::_DecStrong(v9);
  A2DP_Device::SetLastAvdtpActivity(v3, 8, v6);
  return 0;
}

```

## disassembly

```asm
0x14001e800  mov     [rsp+arg_0], rbx
0x14001e805  mov     [rsp+arg_8], rsi
0x14001e80a  push    rdi
0x14001e80b  sub     rsp, 60h
0x14001e80f  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x14001e814  mov     rsi, rax
0x14001e817  mov     r10, cs:WPP_GLOBAL_Control
0x14001e81e  lea     rax, WPP_GLOBAL_Control
0x14001e825  cmp     r10, rax
0x14001e828  jz      short loc_14001E83E
0x14001e82a  mov     ecx, [r10+2Ch]
0x14001e82e  test    cl, 10h
0x14001e831  jz      short loc_14001E83E
0x14001e833  cmp     byte ptr [r10+29h], 4
0x14001e838  jb      short loc_14001E83E
0x14001e83a  mov     dl, 1
0x14001e83c  jmp     short loc_14001E840
0x14001e83e  xor     dl, dl
0x14001e840  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e847  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e84e  setnz   r8b
0x14001e852  test    dl, dl
0x14001e854  jnz     short loc_14001E85B
0x14001e856  test    r8b, r8b
0x14001e859  jz      short loc_14001E88D
0x14001e85b  mov     r9, [r10+40h]
0x14001e85f  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001e866  mov     rcx, [r10+18h]
0x14001e86a  mov     [rsp+68h+var_28], rsi
0x14001e86f  mov     [rsp+68h+var_30], rax
0x14001e874  mov     [rsp+68h+var_38], 5Fh ; '_'
0x14001e87b  mov     [rsp+68h+var_40], 5
0x14001e883  mov     [rsp+68h+var_48], 4
0x14001e888  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001e88d  mov     edx, 7
0x14001e892  mov     rcx, rsi
0x14001e895  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14001e89a  lea     rdi, [rsi+2B8h]
0x14001e8a1  mov     rcx, rdi; SpinLock
0x14001e8a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001e8ab  nop     dword ptr [rax+rax+00h]
0x14001e8b0  mov     rcx, rsi; this
0x14001e8b3  mov     bl, al
0x14001e8b5  call    ?SetConnectionClosedLocked@A2DP_Device@@AEAAXXZ; A2DP_Device::SetConnectionClosedLocked(void)
0x14001e8ba  mov     dl, bl; NewIrql
0x14001e8bc  mov     rcx, rdi; SpinLock
0x14001e8bf  call    cs:__imp_KeReleaseSpinLock
0x14001e8c6  nop     dword ptr [rax+rax+00h]
0x14001e8cb  mov     rcx, rsi; this
0x14001e8ce  call    ?ResetAllOnDisconnect@A2DP_Device@@AEAAXXZ; A2DP_Device::ResetAllOnDisconnect(void)
0x14001e8d3  mov     edx, 2
0x14001e8d8  mov     rcx, rsi
0x14001e8db  call    ?SetAvdtpConnectionStatus@A2DP_Device@@QEAAXW4ConnectionStatus@@@Z; A2DP_Device::SetAvdtpConnectionStatus(ConnectionStatus)
0x14001e8e0  lea     rdx, [rsp+68h+var_18]
0x14001e8e5  mov     rcx, rsi
0x14001e8e8  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001e8ed  mov     rcx, [rsp+68h+var_18]
0x14001e8f2  test    rcx, rcx
0x14001e8f5  jz      short loc_14001E90B
0x14001e8f7  mov     rcx, [rcx]
0x14001e8fa  xor     r8d, r8d
0x14001e8fd  xor     edx, edx
0x14001e8ff  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x14001e906  nop     dword ptr [rax+rax+00h]
0x14001e90b  mov     rcx, [rsp+68h+var_10]; this
0x14001e910  test    rcx, rcx
0x14001e913  jz      short loc_14001E91A
0x14001e915  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001e91a  mov     edx, 8
0x14001e91f  mov     rcx, rsi
0x14001e922  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14001e927  mov     rbx, [rsp+68h+arg_0]
0x14001e92c  xor     eax, eax
0x14001e92e  mov     rsi, [rsp+68h+arg_8]
0x14001e933  add     rsp, 60h
0x14001e937  pop     rdi
0x14001e938  retn
```
