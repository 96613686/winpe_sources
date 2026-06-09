# A2DP_Device::AVDT_Disconnect_Cfm(void *,void *)

- ea: `0x14001e940`
- end: `0x14001ea83`
- name: `?AVDT_Disconnect_Cfm@A2DP_Device@@CAJPEAX0@Z`
- size: `323`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003530`
- `0x140006410`
- `0x140007374`
- `0x1400077e0`
- `0x14001e940`
- `0x14001ea8c`
- `0x14001eb08`
- `0x14001ee94`
- `0x14001f2b8`
- `0x14001f32c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001ea09`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ea09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e9e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e9e4`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14001ea52`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14001ea52`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Disconnect_Cfm(void *a1, void *a2)
{
  int v2; // edx
  struct A2DP_Device *v3; // rsi
  __int64 v4; // r8
  KIRQL v5; // al
  KIRQL v6; // bl
  _QWORD *v8; // [rsp+50h] [rbp-18h] BYREF
  utl::_RefCountBase *v9; // [rsp+58h] [rbp-10h]

  v3 = A2DP_Device::CheckCallbackParms(a1, a2);
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
      96,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v3);
  A2DP_Device::SetLastAvdtpActivity(v3, 6, v4);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 87);
  *((_DWORD *)v3 + 98) = 1;
  v6 = v5;
  A2DP_Device::SetConnectionClosedLocked(v3);
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 87, v6);
  A2DP_Device::ResetAllOnDisconnect(v3);
  A2DP_Device::SetAvdtpConnectionStatus(v3, 1);
  A2DP_Device::SetDisconnectCompleteEvent(v3);
  A2DP_Device::GetMPMContext(v3, &v8);
  if ( v8 )
    BtaMpmUpdateConnectionStatus(*v8, 0, 1);
  if ( v9 )
    utl::_RefCountBase::_DecStrong(v9);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14001e940  mov     [rsp+arg_0], rbx
0x14001e945  mov     [rsp+arg_8], rsi
0x14001e94a  push    rdi
0x14001e94b  sub     rsp, 60h
0x14001e94f  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x14001e954  mov     rsi, rax
0x14001e957  mov     r10, cs:WPP_GLOBAL_Control
0x14001e95e  lea     rax, WPP_GLOBAL_Control
0x14001e965  cmp     r10, rax
0x14001e968  jz      short loc_14001E97E
0x14001e96a  mov     ecx, [r10+2Ch]
0x14001e96e  test    cl, 10h
0x14001e971  jz      short loc_14001E97E
0x14001e973  cmp     byte ptr [r10+29h], 4
0x14001e978  jb      short loc_14001E97E
0x14001e97a  mov     dl, 1
0x14001e97c  jmp     short loc_14001E980
0x14001e97e  xor     dl, dl
0x14001e980  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e987  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e98e  setnz   r8b
0x14001e992  test    dl, dl
0x14001e994  jnz     short loc_14001E99B
0x14001e996  test    r8b, r8b
0x14001e999  jz      short loc_14001E9CD
0x14001e99b  mov     r9, [r10+40h]
0x14001e99f  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001e9a6  mov     rcx, [r10+18h]
0x14001e9aa  mov     [rsp+68h+var_28], rsi
0x14001e9af  mov     [rsp+68h+var_30], rax
0x14001e9b4  mov     [rsp+68h+var_38], 60h ; '`'
0x14001e9bb  mov     [rsp+68h+var_40], 5
0x14001e9c3  mov     [rsp+68h+var_48], 4
0x14001e9c8  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001e9cd  mov     edx, 6
0x14001e9d2  mov     rcx, rsi
0x14001e9d5  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14001e9da  lea     rdi, [rsi+2B8h]
0x14001e9e1  mov     rcx, rdi; SpinLock
0x14001e9e4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001e9eb  nop     dword ptr [rax+rax+00h]
0x14001e9f0  mov     rcx, rsi; this
0x14001e9f3  mov     dword ptr [rsi+188h], 1
0x14001e9fd  mov     bl, al
0x14001e9ff  call    ?SetConnectionClosedLocked@A2DP_Device@@AEAAXXZ; A2DP_Device::SetConnectionClosedLocked(void)
0x14001ea04  mov     dl, bl; NewIrql
0x14001ea06  mov     rcx, rdi; SpinLock
0x14001ea09  call    cs:__imp_KeReleaseSpinLock
0x14001ea10  nop     dword ptr [rax+rax+00h]
0x14001ea15  mov     rcx, rsi; this
0x14001ea18  call    ?ResetAllOnDisconnect@A2DP_Device@@AEAAXXZ; A2DP_Device::ResetAllOnDisconnect(void)
0x14001ea1d  mov     edx, 1
0x14001ea22  mov     rcx, rsi
0x14001ea25  call    ?SetAvdtpConnectionStatus@A2DP_Device@@QEAAXW4ConnectionStatus@@@Z; A2DP_Device::SetAvdtpConnectionStatus(ConnectionStatus)
0x14001ea2a  mov     rcx, rsi; this
0x14001ea2d  call    ?SetDisconnectCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetDisconnectCompleteEvent(void)
0x14001ea32  lea     rdx, [rsp+68h+var_18]
0x14001ea37  mov     rcx, rsi
0x14001ea3a  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001ea3f  mov     rcx, [rsp+68h+var_18]
0x14001ea44  test    rcx, rcx
0x14001ea47  jz      short loc_14001EA5E
0x14001ea49  mov     rcx, [rcx]
0x14001ea4c  xor     edx, edx
0x14001ea4e  lea     r8d, [rdx+1]
0x14001ea52  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x14001ea59  nop     dword ptr [rax+rax+00h]
0x14001ea5e  mov     rcx, [rsp+68h+var_10]; this
0x14001ea63  test    rcx, rcx
0x14001ea66  jz      short loc_14001EA6D
0x14001ea68  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001ea6d  mov     rbx, [rsp+68h+arg_0]
0x14001ea72  mov     eax, 0C000009Ah
0x14001ea77  mov     rsi, [rsp+68h+arg_8]
0x14001ea7c  add     rsp, 60h
0x14001ea80  pop     rdi
0x14001ea81  retn
```
