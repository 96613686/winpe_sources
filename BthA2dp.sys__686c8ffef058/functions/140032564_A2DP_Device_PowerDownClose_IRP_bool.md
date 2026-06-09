# A2DP_Device::PowerDownClose(_IRP *,bool)

- ea: `0x140032564`
- end: `0x140032715`
- name: `?PowerDownClose@A2DP_Device@@QEAAXPEAU_IRP@@_N@Z`
- size: `433`
- prototype: `void __fastcall(A2DP_Device *__hidden this, struct _IRP *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140010c30`

## callees

- `0x140003530`
- `0x140006410`
- `0x140011bcc`
- `0x14001ee94`
- `0x14001f2b8`
- `0x140020a70`
- `0x140032564`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x140032632`
- `ntoskrnl!KeResetEvent` at `0x140032632`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032644`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032683`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032644`
- `ntoskrnl!KeReleaseSpinLock` at `0x140032683`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400325ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032653`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400325ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140032653`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x1400326f0`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x1400326f0`

## pseudocode

```c
void __fastcall A2DP_Device::PowerDownClose(A2DP_Device *this, struct _IRP *a2)
{
  bool v3; // dl
  KIRQL v4; // al
  __int64 v5; // rcx
  KIRQL v6; // di
  KIRQL v7; // al
  __int64 v8; // rdi
  KIRQL v9; // bp
  _QWORD *v10; // [rsp+50h] [rbp-38h] BYREF
  utl::_RefCountBase *v11; // [rsp+58h] [rbp-30h]

  v3 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      54,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)this);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  v5 = *((_QWORD *)this + 1);
  v6 = v4;
  if ( v5 && *(_BYTE *)(v5 + 89) )
    *(_BYTE *)(v5 + 312) = 0;
  if ( !*((_DWORD *)this + 98) && !*((_BYTE *)this + 816) )
  {
    *((_BYTE *)this + 816) = 1;
    KeResetEvent((PRKEVENT)this + 31);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v6);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  v8 = *((_QWORD *)this + 50);
  v9 = v7;
  if ( v8 )
    (*((void (__fastcall **)(_QWORD))this + 53))(*((_QWORD *)this + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)this + 87, v9);
  if ( v8 )
  {
    (*((void (__fastcall **)(__int64, _QWORD))this + 56))(v8, 0);
    (*((void (__fastcall **)(__int64))this + 54))(v8);
  }
  A2DP_Device::WaitForDisconnectComplete(this);
  A2DP_Device::SetConnectionClosedUnlocked(this);
  A2DP_Device::SetAvdtpConnectionStatus(this, 1);
  A2DP_Device::GetMPMContext(this, &v10);
  if ( v10 )
    BtaMpmUpdateConnectionStatus(*v10, 0, 0);
  if ( v11 )
    utl::_RefCountBase::_DecStrong(v11);
}

```

## disassembly

```asm
0x140032564  push    rbx
0x140032566  push    rbp
0x140032567  push    rsi
0x140032568  push    rdi
0x140032569  sub     rsp, 68h
0x14003256d  mov     rbx, rcx
0x140032570  mov     rcx, cs:WPP_GLOBAL_Control
0x140032577  lea     rax, WPP_GLOBAL_Control
0x14003257e  cmp     rcx, rax
0x140032581  jz      short loc_140032594
0x140032583  mov     eax, [rcx+2Ch]
0x140032586  test    al, 10h
0x140032588  jz      short loc_140032594
0x14003258a  cmp     byte ptr [rcx+29h], 4
0x14003258e  jb      short loc_140032594
0x140032590  mov     dl, 1
0x140032592  jmp     short loc_140032596
0x140032594  xor     dl, dl
0x140032596  lea     rax, WPP_RECORDER_INITIALIZED
0x14003259d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400325a4  setnz   r8b
0x1400325a8  test    dl, dl
0x1400325aa  jnz     short loc_1400325B1
0x1400325ac  test    r8b, r8b
0x1400325af  jz      short loc_1400325E3
0x1400325b1  mov     r9, [rcx+40h]
0x1400325b5  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x1400325bc  mov     rcx, [rcx+18h]
0x1400325c0  mov     [rsp+88h+var_48], rbx
0x1400325c5  mov     [rsp+88h+var_50], rax
0x1400325ca  mov     [rsp+88h+var_58], 36h ; '6'
0x1400325d1  mov     [rsp+88h+var_60], 5
0x1400325d9  mov     [rsp+88h+var_68], 4
0x1400325de  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400325e3  lea     rsi, [rbx+2B8h]
0x1400325ea  mov     rcx, rsi; SpinLock
0x1400325ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400325f4  nop     dword ptr [rax+rax+00h]
0x1400325f9  mov     rcx, [rbx+8]
0x1400325fd  mov     dil, al
0x140032600  test    rcx, rcx
0x140032603  jz      short loc_140032612
0x140032605  cmp     byte ptr [rcx+59h], 0
0x140032609  jz      short loc_140032612
0x14003260b  mov     byte ptr [rcx+138h], 0
0x140032612  cmp     dword ptr [rbx+188h], 0
0x140032619  jnz     short loc_14003263E
0x14003261b  cmp     byte ptr [rbx+330h], 0
0x140032622  jnz     short loc_14003263E
0x140032624  lea     rcx, [rbx+2E8h]; Event
0x14003262b  mov     byte ptr [rbx+330h], 1
0x140032632  call    cs:__imp_KeResetEvent
0x140032639  nop     dword ptr [rax+rax+00h]
0x14003263e  mov     dl, dil; NewIrql
0x140032641  mov     rcx, rsi; SpinLock
0x140032644  call    cs:__imp_KeReleaseSpinLock
0x14003264b  nop     dword ptr [rax+rax+00h]
0x140032650  mov     rcx, rsi; SpinLock
0x140032653  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003265a  nop     dword ptr [rax+rax+00h]
0x14003265f  mov     rdi, [rbx+190h]
0x140032666  mov     bpl, al
0x140032669  test    rdi, rdi
0x14003266c  jz      short loc_14003267D
0x14003266e  mov     rax, [rbx+1A8h]
0x140032675  mov     rcx, rdi
0x140032678  call    _guard_dispatch_icall
0x14003267d  mov     dl, bpl; NewIrql
0x140032680  mov     rcx, rsi; SpinLock
0x140032683  call    cs:__imp_KeReleaseSpinLock
0x14003268a  nop     dword ptr [rax+rax+00h]
0x14003268f  test    rdi, rdi
0x140032692  jz      short loc_1400326B4
0x140032694  mov     rax, [rbx+1C0h]
0x14003269b  xor     edx, edx
0x14003269d  mov     rcx, rdi
0x1400326a0  call    _guard_dispatch_icall
0x1400326a5  mov     rax, [rbx+1B0h]
0x1400326ac  mov     rcx, rdi
0x1400326af  call    _guard_dispatch_icall
0x1400326b4  mov     rcx, rbx; this
0x1400326b7  call    ?WaitForDisconnectComplete@A2DP_Device@@AEAAJXZ; A2DP_Device::WaitForDisconnectComplete(void)
0x1400326bc  mov     rcx, rbx; this
0x1400326bf  call    ?SetConnectionClosedUnlocked@A2DP_Device@@AEAAXXZ; A2DP_Device::SetConnectionClosedUnlocked(void)
0x1400326c4  mov     edx, 1
0x1400326c9  mov     rcx, rbx
0x1400326cc  call    ?SetAvdtpConnectionStatus@A2DP_Device@@QEAAXW4ConnectionStatus@@@Z; A2DP_Device::SetAvdtpConnectionStatus(ConnectionStatus)
0x1400326d1  lea     rdx, [rsp+88h+var_38]
0x1400326d6  mov     rcx, rbx
0x1400326d9  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x1400326de  mov     rcx, [rsp+88h+var_38]
0x1400326e3  test    rcx, rcx
0x1400326e6  jz      short loc_1400326FC
0x1400326e8  mov     rcx, [rcx]
0x1400326eb  xor     r8d, r8d
0x1400326ee  xor     edx, edx
0x1400326f0  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x1400326f7  nop     dword ptr [rax+rax+00h]
0x1400326fc  mov     rcx, [rsp+88h+var_30]; this
0x140032701  test    rcx, rcx
0x140032704  jz      short loc_14003270B
0x140032706  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003270b  add     rsp, 68h
0x14003270f  pop     rdi
0x140032710  pop     rsi
0x140032711  pop     rbp
0x140032712  pop     rbx
0x140032713  retn
```
