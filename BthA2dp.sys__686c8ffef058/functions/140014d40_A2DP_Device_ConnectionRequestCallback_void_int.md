# A2DP_Device::ConnectionRequestCallback(void *,int)

- ea: `0x140014d40`
- end: `0x140015059`
- name: `?ConnectionRequestCallback@A2DP_Device@@CAJPEAXH@Z`
- size: `793`
- prototype: `__int64 __fastcall(A2DP_Device *this, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140006410`
- `0x1400077e0`
- `0x14000f570`
- `0x140014d40`
- `0x14001d2b0`
- `0x14001ea8c`
- `0x14001f2b8`
- `0x14001f56c`
- `0x14002bc34`
- `0x14002bdbc`
- `0x14002ccf0`
- `0x140032d7c`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140014e94`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001500a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014e94`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001500a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014e64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014fda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014e64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014fda`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x140014e0b`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x140014f80`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x140014e0b`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x140014f80`

## pseudocode

```c
__int64 __fastcall A2DP_Device::ConnectionRequestCallback(KSPIN_LOCK *this, __int64 a2, __int64 a3)
{
  int v3; // esi
  char v5; // di
  unsigned int v7; // r14d
  int AvdtpConnectionStatus; // eax
  int v9; // edx
  int v10; // r8d
  A2dpRole *v11; // rcx
  KIRQL v12; // al
  KSPIN_LOCK v13; // rsi
  KIRQL v14; // r15
  __int64 v15; // r8
  A2dpRole *v16; // rcx
  A2dpRole *v17; // rcx
  KIRQL v18; // al
  KSPIN_LOCK v19; // rdi
  KIRQL v20; // bp
  __int64 v21; // r8
  _QWORD *v22; // [rsp+50h] [rbp-48h] BYREF
  utl::_RefCountBase *v23; // [rsp+58h] [rbp-40h]

  v3 = a2;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qs(WPP_GLOBAL_Control->AttachedDevice, a2, a3, WPP_GLOBAL_Control->DeviceExtension);
  if ( !this )
    return 3221225485LL;
  v7 = 0;
  AvdtpConnectionStatus = A2DP_Device::GetAvdtpConnectionStatus(this, a2, a3);
  if ( v3 )
  {
    if ( AvdtpConnectionStatus )
    {
      if ( *((_BYTE *)this + 3408)
        && (v11 = (A2dpRole *)this[1]) != 0
        && (!*((_BYTE *)v11 + 89) || A2dpRole::GetSinkIsConnecting(v11)) )
      {
        v12 = KeAcquireSpinLockRaiseToDpc(this + 87);
        v13 = this[50];
        v14 = v12;
        if ( v13 )
          ((void (__fastcall *)(KSPIN_LOCK))this[53])(this[50]);
        KeReleaseSpinLock(this + 87, v14);
        if ( v13 )
        {
          A2DP_Device::SetLastAvdtpActivity(this, 1, v15);
          ((void (__fastcall *)(KSPIN_LOCK))this[59])(v13);
          ((void (__fastcall *)(KSPIN_LOCK))this[54])(v13);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          v5 = 0;
        }
        if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = v5;
          LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v9,
            v10,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            9,
            159,
            (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids);
        }
        v7 = -1073741436;
      }
    }
    else
    {
      A2DP_Device::GetMPMContext(this, &v22);
      if ( v22 )
        BtaMpmUpdateConnectionStatus(*v22, 1, 1);
      if ( v23 )
        utl::_RefCountBase::_DecStrong(v23);
    }
    v16 = (A2dpRole *)this[1];
    if ( v16 )
    {
      if ( *((_BYTE *)v16 + 89) )
        A2dpRole::SetSinkIsConnectingUnlocked(v16, 0);
    }
  }
  else if ( AvdtpConnectionStatus )
  {
    A2DP_Device::GetMPMContext(this, &v22);
    if ( v22 )
      BtaMpmUpdateConnectionStatus(*v22, 0, 1);
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    A2DP_Device::SetDisconnectCompleteEvent((A2DP_Device *)this);
  }
  else
  {
    v17 = (A2dpRole *)this[1];
    if ( v17 )
    {
      if ( A2dpRole::IsCodecConfigured(v17) || *(_BYTE *)(this[1] + 88) )
        A2DP_Device::RequestStreamClose((A2DP_Device *)this);
      v18 = KeAcquireSpinLockRaiseToDpc(this + 87);
      v19 = this[50];
      v20 = v18;
      if ( v19 )
        ((void (__fastcall *)(KSPIN_LOCK))this[53])(this[50]);
      KeReleaseSpinLock(this + 87, v20);
      if ( v19 )
      {
        A2DP_Device::SetLastAvdtpActivity(this, 5, v21);
        ((void (__fastcall *)(KSPIN_LOCK))this[60])(v19);
        ((void (__fastcall *)(KSPIN_LOCK))this[54])(v19);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140014d40  push    rbx
0x140014d42  push    rbp
0x140014d43  push    rsi
0x140014d44  push    rdi
0x140014d45  push    r13
0x140014d47  push    r14
0x140014d49  push    r15
0x140014d4b  sub     rsp, 60h
0x140014d4f  mov     esi, edx
0x140014d51  mov     rbx, rcx
0x140014d54  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d5b  lea     r15, WPP_GLOBAL_Control
0x140014d62  mov     edi, 1
0x140014d67  cmp     rcx, r15
0x140014d6a  jz      short loc_140014D7E
0x140014d6c  bt      dword ptr [rcx+2Ch], 8
0x140014d71  jnb     short loc_140014D7E
0x140014d73  cmp     byte ptr [rcx+29h], 4
0x140014d77  jb      short loc_140014D7E
0x140014d79  mov     dl, dil
0x140014d7c  jmp     short loc_140014D80
0x140014d7e  xor     dl, dl
0x140014d80  lea     r13, WPP_RECORDER_INITIALIZED
0x140014d87  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140014d8e  setnz   r8b
0x140014d92  test    dl, dl
0x140014d94  jnz     short loc_140014D9B
0x140014d96  test    r8b, r8b
0x140014d99  jz      short loc_140014DC6
0x140014d9b  test    esi, esi
0x140014d9d  lea     r9, aDisconnect; "Disconnect"
0x140014da4  lea     rax, aConnect; "Connect"
0x140014dab  cmovz   rax, r9
0x140014daf  mov     r9, [rcx+40h]
0x140014db3  mov     rcx, [rcx+18h]
0x140014db7  mov     [rsp+98h+var_50], rax
0x140014dbc  mov     [rsp+98h+var_58], rbx
0x140014dc1  call    WPP_RECORDER_AND_TRACE_SF_qs
0x140014dc6  test    rbx, rbx
0x140014dc9  jnz     short loc_140014DD5
0x140014dcb  mov     eax, 0C000000Dh
0x140014dd0  jmp     loc_140015049
0x140014dd5  mov     rcx, rbx
0x140014dd8  xor     r14d, r14d
0x140014ddb  call    ?GetAvdtpConnectionStatus@A2DP_Device@@QEBA?AW4ConnectionStatus@@XZ; A2DP_Device::GetAvdtpConnectionStatus(void)
0x140014de0  test    esi, esi
0x140014de2  jz      loc_140014F5D
0x140014de8  test    eax, eax
0x140014dea  jnz     short loc_140014E2F
0x140014dec  lea     rdx, [rsp+98h+var_48]
0x140014df1  mov     rcx, rbx
0x140014df4  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x140014df9  mov     rcx, [rsp+98h+var_48]
0x140014dfe  test    rcx, rcx
0x140014e01  jz      short loc_140014E17
0x140014e03  mov     rcx, [rcx]
0x140014e06  mov     r8d, edi
0x140014e09  mov     edx, edi
0x140014e0b  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x140014e12  nop     dword ptr [rax+rax+00h]
0x140014e17  mov     rcx, [rsp+98h+var_40]; this
0x140014e1c  test    rcx, rcx
0x140014e1f  jz      loc_140014F3A
0x140014e25  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140014e2a  jmp     loc_140014F3A
0x140014e2f  mov     al, [rbx+0D50h]
0x140014e35  nop
0x140014e36  test    al, al
0x140014e38  jz      loc_140014ED3
0x140014e3e  mov     rcx, [rbx+8]; this
0x140014e42  test    rcx, rcx
0x140014e45  jz      loc_140014ED3
0x140014e4b  cmp     [rcx+59h], r14b
0x140014e4f  jz      short loc_140014E5A
0x140014e51  call    ?GetSinkIsConnecting@A2dpRole@@QEBA_NXZ; A2dpRole::GetSinkIsConnecting(void)
0x140014e56  test    al, al
0x140014e58  jz      short loc_140014ED3
0x140014e5a  lea     rbp, [rbx+2B8h]
0x140014e61  mov     rcx, rbp; SpinLock
0x140014e64  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014e6b  nop     dword ptr [rax+rax+00h]
0x140014e70  mov     rsi, [rbx+190h]
0x140014e77  mov     r15b, al
0x140014e7a  test    rsi, rsi
0x140014e7d  jz      short loc_140014E8E
0x140014e7f  mov     rax, [rbx+1A8h]
0x140014e86  mov     rcx, rsi
0x140014e89  call    _guard_dispatch_icall
0x140014e8e  mov     dl, r15b; NewIrql
0x140014e91  mov     rcx, rbp; SpinLock
0x140014e94  call    cs:__imp_KeReleaseSpinLock
0x140014e9b  nop     dword ptr [rax+rax+00h]
0x140014ea0  test    rsi, rsi
0x140014ea3  jz      loc_140014F3A
0x140014ea9  mov     edx, edi
0x140014eab  mov     rcx, rbx
0x140014eae  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140014eb3  mov     rax, [rbx+1D8h]
0x140014eba  mov     rcx, rsi
0x140014ebd  call    _guard_dispatch_icall
0x140014ec2  mov     rax, [rbx+1B0h]
0x140014ec9  mov     rcx, rsi
0x140014ecc  call    _guard_dispatch_icall
0x140014ed1  jmp     short loc_140014F3A
0x140014ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eda  cmp     rcx, r15
0x140014edd  jz      short loc_140014EEC
0x140014edf  bt      dword ptr [rcx+2Ch], 8
0x140014ee4  jnb     short loc_140014EEC
0x140014ee6  cmp     byte ptr [rcx+29h], 3
0x140014eea  jnb     short loc_140014EEF
0x140014eec  xor     dil, dil
0x140014eef  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140014ef6  setnz   r8b
0x140014efa  test    dil, dil
0x140014efd  jnz     short loc_140014F04
0x140014eff  test    r8b, r8b
0x140014f02  jz      short loc_140014F34
0x140014f04  mov     r9, [rcx+40h]
0x140014f08  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140014f0f  mov     rcx, [rcx+18h]
0x140014f13  mov     dl, dil
0x140014f16  mov     [rsp+98h+var_60], rax
0x140014f1b  mov     [rsp+98h+var_68], 9Fh
0x140014f22  mov     [rsp+98h+var_70], 9
0x140014f2a  mov     [rsp+98h+var_78], 3
0x140014f2f  call    WPP_RECORDER_AND_TRACE_SF_
0x140014f34  mov     r14d, 0C0000184h
0x140014f3a  mov     rcx, [rbx+8]; this
0x140014f3e  test    rcx, rcx
0x140014f41  jz      loc_140015046
0x140014f47  cmp     byte ptr [rcx+59h], 0
0x140014f4b  jz      loc_140015046
0x140014f51  xor     edx, edx; bool
0x140014f53  call    ?SetSinkIsConnectingUnlocked@A2dpRole@@QEAAX_N@Z; A2dpRole::SetSinkIsConnectingUnlocked(bool)
0x140014f58  jmp     loc_140015046
0x140014f5d  test    eax, eax
0x140014f5f  jz      short loc_140014FA8
0x140014f61  lea     rdx, [rsp+98h+var_48]
0x140014f66  mov     rcx, rbx
0x140014f69  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x140014f6e  mov     rcx, [rsp+98h+var_48]
0x140014f73  test    rcx, rcx
0x140014f76  jz      short loc_140014F8C
0x140014f78  mov     rcx, [rcx]
0x140014f7b  mov     r8d, edi
0x140014f7e  xor     edx, edx
0x140014f80  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x140014f87  nop     dword ptr [rax+rax+00h]
0x140014f8c  mov     rcx, [rsp+98h+var_40]; this
0x140014f91  test    rcx, rcx
0x140014f94  jz      short loc_140014F9B
0x140014f96  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140014f9b  mov     rcx, rbx; this
0x140014f9e  call    ?SetDisconnectCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetDisconnectCompleteEvent(void)
0x140014fa3  jmp     loc_140015046
0x140014fa8  mov     rcx, [rbx+8]; this
0x140014fac  test    rcx, rcx
0x140014faf  jz      loc_140015046
0x140014fb5  call    ?IsCodecConfigured@A2dpRole@@QEAA_NXZ; A2dpRole::IsCodecConfigured(void)
0x140014fba  test    al, al
0x140014fbc  jnz     short loc_140014FC8
0x140014fbe  mov     rax, [rbx+8]
0x140014fc2  cmp     [rax+58h], r14b
0x140014fc6  jz      short loc_140014FD0
0x140014fc8  mov     rcx, rbx; this
0x140014fcb  call    ?RequestStreamClose@A2DP_Device@@QEAAXXZ; A2DP_Device::RequestStreamClose(void)
0x140014fd0  lea     rsi, [rbx+2B8h]
0x140014fd7  mov     rcx, rsi; SpinLock
0x140014fda  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014fe1  nop     dword ptr [rax+rax+00h]
0x140014fe6  mov     rdi, [rbx+190h]
0x140014fed  mov     bpl, al
0x140014ff0  test    rdi, rdi
0x140014ff3  jz      short loc_140015004
0x140014ff5  mov     rax, [rbx+1A8h]
0x140014ffc  mov     rcx, rdi
0x140014fff  call    _guard_dispatch_icall
0x140015004  mov     dl, bpl; NewIrql
0x140015007  mov     rcx, rsi; SpinLock
0x14001500a  call    cs:__imp_KeReleaseSpinLock
0x140015011  nop     dword ptr [rax+rax+00h]
0x140015016  test    rdi, rdi
0x140015019  jz      short loc_140015046
0x14001501b  mov     edx, 5
0x140015020  mov     rcx, rbx
0x140015023  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140015028  mov     rax, [rbx+1E0h]
0x14001502f  mov     rcx, rdi
0x140015032  call    _guard_dispatch_icall
0x140015037  mov     rax, [rbx+1B0h]
0x14001503e  mov     rcx, rdi
0x140015041  call    _guard_dispatch_icall
0x140015046  mov     eax, r14d
0x140015049  add     rsp, 60h
0x14001504d  pop     r15
0x14001504f  pop     r14
0x140015051  pop     r13
0x140015053  pop     rdi
0x140015054  pop     rsi
0x140015055  pop     rbp
0x140015056  pop     rbx
0x140015057  retn
```
