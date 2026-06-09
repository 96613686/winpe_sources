# A2DP_Device::AVDT_Connect_Cfm(void *,void *,int)

- ea: `0x140007aa0`
- end: `0x140007c5f`
- name: `?AVDT_Connect_Cfm@A2DP_Device@@CAJPEAX0H@Z`
- size: `447`
- prototype: `__int64 __fastcall(void *, void *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callees

- `0x140006410`
- `0x14000700c`
- `0x140007374`
- `0x1400077e0`
- `0x140007aa0`
- `0x14001ee94`
- `0x14001f2b8`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x140007bd7`
- `ntoskrnl!KeResetEvent` at `0x140007bd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b5a`
- `ntoskrnl!KeCancelTimer` at `0x140007bc4`
- `ntoskrnl!KeCancelTimer` at `0x140007bc4`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x140007c36`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x140007c36`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Connect_Cfm(void *a1, void *a2, int a3)
{
  int v4; // edx
  struct A2DP_Device *v5; // rbx
  __int64 v6; // r8
  KIRQL v7; // al
  __int64 v8; // rdi
  KIRQL v9; // bp
  __int64 v10; // r8
  _QWORD *v12; // [rsp+50h] [rbp-38h] BYREF
  utl::_RefCountBase *v13; // [rsp+58h] [rbp-30h]

  v5 = A2DP_Device::CheckCallbackParms(a1, a2);
  LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v6,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      94,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v5,
      a3);
  A2DP_Device::SetLastAvdtpActivity(v5, 2, v6);
  A2DP_Device::SetAvdtpConnectionStatus(v5, a3 == 0 ? 2 : 0);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5 + 87);
  v8 = *((_QWORD *)v5 + 50);
  v9 = v7;
  if ( v8 )
    (*((void (__fastcall **)(_QWORD))v5 + 53))(*((_QWORD *)v5 + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)v5 + 87, v9);
  if ( v8 )
  {
    if ( !*((_DWORD *)v5 + 98) && !*((_BYTE *)v5 + 817) && *((_BYTE *)v5 + 2808) )
    {
      *((_BYTE *)v5 + 817) = 1;
      KeCancelTimer((PKTIMER)((char *)v5 + 3016));
      KeResetEvent((PRKEVENT)v5 + 32);
      A2DP_Device::SetLastAvdtpActivity(v5, 9, v10);
      (*((void (__fastcall **)(__int64))v5 + 62))(v8);
    }
    (*((void (__fastcall **)(__int64))v5 + 54))(v8);
  }
  A2DP_Device::GetMPMContext(v5, &v12);
  if ( v12 )
    BtaMpmUpdateConnectionStatus(*v12, a3 != 0, 1);
  if ( v13 )
    utl::_RefCountBase::_DecStrong(v13);
  return 0;
}

```

## disassembly

```asm
0x140007aa0  push    rbx
0x140007aa2  push    rbp
0x140007aa3  push    rsi
0x140007aa4  push    rdi
0x140007aa5  push    r14
0x140007aa7  sub     rsp, 60h
0x140007aab  mov     r14d, r8d
0x140007aae  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x140007ab3  mov     rbx, rax
0x140007ab6  mov     rax, cs:WPP_GLOBAL_Control
0x140007abd  lea     rcx, WPP_GLOBAL_Control
0x140007ac4  cmp     rax, rcx
0x140007ac7  jz      short loc_140007ADB
0x140007ac9  mov     ecx, [rax+2Ch]
0x140007acc  test    cl, 10h
0x140007acf  jz      short loc_140007ADB
0x140007ad1  cmp     byte ptr [rax+29h], 4
0x140007ad5  jb      short loc_140007ADB
0x140007ad7  mov     dl, 1
0x140007ad9  jmp     short loc_140007ADD
0x140007adb  xor     dl, dl
0x140007add  lea     rcx, WPP_RECORDER_INITIALIZED
0x140007ae4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140007aeb  setnz   r8b
0x140007aef  test    dl, dl
0x140007af1  jnz     short loc_140007AF8
0x140007af3  test    r8b, r8b
0x140007af6  jz      short loc_140007B2F
0x140007af8  mov     r9, [rax+40h]
0x140007afc  lea     rcx, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140007b03  mov     [rsp+88h+var_40], r14d
0x140007b08  mov     [rsp+88h+var_48], rbx
0x140007b0d  mov     [rsp+88h+var_50], rcx
0x140007b12  mov     rcx, [rax+18h]
0x140007b16  mov     [rsp+88h+var_58], 5Eh ; '^'
0x140007b1d  mov     [rsp+88h+var_60], 5
0x140007b25  mov     [rsp+88h+var_68], 4
0x140007b2a  call    WPP_RECORDER_AND_TRACE_SF_qD
0x140007b2f  mov     edx, 2
0x140007b34  mov     rcx, rbx
0x140007b37  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140007b3c  mov     eax, r14d
0x140007b3f  mov     rcx, rbx
0x140007b42  neg     eax
0x140007b44  sbb     edx, edx
0x140007b46  not     edx
0x140007b48  and     edx, 2
0x140007b4b  call    ?SetAvdtpConnectionStatus@A2DP_Device@@QEAAXW4ConnectionStatus@@@Z; A2DP_Device::SetAvdtpConnectionStatus(ConnectionStatus)
0x140007b50  lea     rsi, [rbx+2B8h]
0x140007b57  mov     rcx, rsi; SpinLock
0x140007b5a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007b61  nop     dword ptr [rax+rax+00h]
0x140007b66  mov     rdi, [rbx+190h]
0x140007b6d  mov     bpl, al
0x140007b70  test    rdi, rdi
0x140007b73  jz      short loc_140007B84
0x140007b75  mov     rax, [rbx+1A8h]
0x140007b7c  mov     rcx, rdi
0x140007b7f  call    _guard_dispatch_icall
0x140007b84  mov     dl, bpl; NewIrql
0x140007b87  mov     rcx, rsi; SpinLock
0x140007b8a  call    cs:__imp_KeReleaseSpinLock
0x140007b91  nop     dword ptr [rax+rax+00h]
0x140007b96  test    rdi, rdi
0x140007b99  jz      short loc_140007C0E
0x140007b9b  cmp     dword ptr [rbx+188h], 0
0x140007ba2  jnz     short loc_140007BFF
0x140007ba4  cmp     byte ptr [rbx+331h], 0
0x140007bab  jnz     short loc_140007BFF
0x140007bad  cmp     byte ptr [rbx+0AF8h], 0
0x140007bb4  jz      short loc_140007BFF
0x140007bb6  lea     rcx, [rbx+0BC8h]; PKTIMER
0x140007bbd  mov     byte ptr [rbx+331h], 1
0x140007bc4  call    cs:__imp_KeCancelTimer
0x140007bcb  nop     dword ptr [rax+rax+00h]
0x140007bd0  lea     rcx, [rbx+300h]; Event
0x140007bd7  call    cs:__imp_KeResetEvent
0x140007bde  nop     dword ptr [rax+rax+00h]
0x140007be3  mov     edx, 9
0x140007be8  mov     rcx, rbx
0x140007beb  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140007bf0  mov     rax, [rbx+1F0h]
0x140007bf7  mov     rcx, rdi
0x140007bfa  call    _guard_dispatch_icall
0x140007bff  mov     rax, [rbx+1B0h]
0x140007c06  mov     rcx, rdi
0x140007c09  call    _guard_dispatch_icall
0x140007c0e  lea     rdx, [rsp+88h+var_38]
0x140007c13  mov     rcx, rbx
0x140007c16  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x140007c1b  mov     rcx, [rsp+88h+var_38]
0x140007c20  test    rcx, rcx
0x140007c23  jz      short loc_140007C42
0x140007c25  mov     rcx, [rcx]
0x140007c28  xor     edx, edx
0x140007c2a  test    r14d, r14d
0x140007c2d  mov     r8d, 1
0x140007c33  setnz   dl
0x140007c36  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x140007c3d  nop     dword ptr [rax+rax+00h]
0x140007c42  mov     rcx, [rsp+88h+var_30]; this
0x140007c47  test    rcx, rcx
0x140007c4a  jz      short loc_140007C51
0x140007c4c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140007c51  xor     eax, eax
0x140007c53  add     rsp, 60h
0x140007c57  pop     r14
0x140007c59  pop     rdi
0x140007c5a  pop     rsi
0x140007c5b  pop     rbp
0x140007c5c  pop     rbx
0x140007c5d  retn
```
