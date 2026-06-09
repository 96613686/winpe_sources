# Avdtp_impl::Open_Req(void *,uchar)

- ea: `0x14004e240`
- end: `0x14004e418`
- name: `?Open_Req@Avdtp_impl@@CAJPEAXE@Z`
- size: `472`
- prototype: `__int64 __fastcall(Avdtp_impl *this, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002d890`
- `0x1400499ac`
- `0x14004df64`
- `0x14004e240`
- `0x140053e54`
- `0x1400546d0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004e3c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e3c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e390`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e390`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::Open_Req(KSPIN_LOCK *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int8 v4; // di
  int v6; // edx
  int v7; // r8d
  unsigned int EndpointIndexByRemoteSeid_AndReturnState; // eax
  bool v10; // cf
  char v11; // si
  KIRQL v12; // al
  KSPIN_LOCK v13; // rdi
  KIRQL v14; // r14
  __int64 v15; // r8
  int v16; // [rsp+70h] [rbp+8h] BYREF

  v4 = a2;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_avdtp_seidq(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  else
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_avdtp_seid(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  if ( !this )
    return 3221225485LL;
  v16 = 0;
  EndpointIndexByRemoteSeid_AndReturnState = Avdtp_impl::FindEndpointIndexByRemoteSeid_AndReturnState(
                                               (Avdtp_impl *)this,
                                               v4,
                                               (enum TAG_AvdtpSepState *)&v16);
  v10 = EndpointIndexByRemoteSeid_AndReturnState < 4;
  if ( EndpointIndexByRemoteSeid_AndReturnState >= 4 )
    goto LABEL_24;
  if ( v16 != 1 )
  {
    v10 = EndpointIndexByRemoteSeid_AndReturnState < 4;
LABEL_24:
    v11 = v10 ? 49 : 18;
    v12 = KeAcquireSpinLockRaiseToDpc(this + 200);
    v13 = this[143];
    v14 = v12;
    if ( v13 )
      ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
    KeReleaseSpinLock(this + 200, v14);
    if ( v13 )
    {
      LOBYTE(v15) = v11;
      ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, __int64, _QWORD, _DWORD))this[165])(this, v13, v15, 0, 0);
      ((void (__fastcall *)(KSPIN_LOCK))this[147])(v13);
    }
    return 0;
  }
  LOWORD(v16) = 0;
  BYTE2(v16) = 4 * v4;
  Avdtp_impl::LabelAndSendCommand((Avdtp_impl *)this, (struct _SINGLE_PCK_CMD *)&v16, 6, 3u);
  return 0;
}

```

## disassembly

```asm
0x14004e240  mov     [rsp+arg_8], rbx
0x14004e245  mov     [rsp+arg_10], rbp
0x14004e24a  push    rsi
0x14004e24b  push    rdi
0x14004e24c  push    r14
0x14004e24e  sub     rsp, 50h
0x14004e252  mov     dil, dl
0x14004e255  mov     rbx, rcx
0x14004e258  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004e25d  test    eax, eax
0x14004e25f  jz      short loc_14004E2C2
0x14004e261  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e268  lea     rax, WPP_GLOBAL_Control
0x14004e26f  cmp     rcx, rax
0x14004e272  jz      short loc_14004E285
0x14004e274  mov     eax, [rcx+2Ch]
0x14004e277  test    al, 8
0x14004e279  jz      short loc_14004E285
0x14004e27b  cmp     byte ptr [rcx+29h], 4
0x14004e27f  jb      short loc_14004E285
0x14004e281  mov     dl, 1
0x14004e283  jmp     short loc_14004E287
0x14004e285  xor     dl, dl
0x14004e287  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e28e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e295  setnz   r8b
0x14004e299  test    dl, dl
0x14004e29b  jnz     short loc_14004E2A2
0x14004e29d  test    r8b, r8b
0x14004e2a0  jz      short loc_14004E31C
0x14004e2a2  mov     r9, [rcx+40h]
0x14004e2a6  mov     rcx, [rcx+18h]
0x14004e2aa  mov     [rsp+68h+var_20], rbx
0x14004e2af  mov     [rsp+68h+var_28], dil
0x14004e2b4  mov     [rsp+68h+var_38], 72h ; 'r'
0x14004e2bb  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seidq
0x14004e2c0  jmp     short loc_14004E31C
0x14004e2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e2c9  lea     rax, WPP_GLOBAL_Control
0x14004e2d0  cmp     rcx, rax
0x14004e2d3  jz      short loc_14004E2E6
0x14004e2d5  mov     eax, [rcx+2Ch]
0x14004e2d8  test    al, 8
0x14004e2da  jz      short loc_14004E2E6
0x14004e2dc  cmp     byte ptr [rcx+29h], 4
0x14004e2e0  jb      short loc_14004E2E6
0x14004e2e2  mov     dl, 1
0x14004e2e4  jmp     short loc_14004E2E8
0x14004e2e6  xor     dl, dl
0x14004e2e8  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e2ef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e2f6  setnz   r8b
0x14004e2fa  test    dl, dl
0x14004e2fc  jnz     short loc_14004E303
0x14004e2fe  test    r8b, r8b
0x14004e301  jz      short loc_14004E31C
0x14004e303  mov     r9, [rcx+40h]
0x14004e307  mov     rcx, [rcx+18h]
0x14004e30b  mov     [rsp+68h+var_28], dil
0x14004e310  mov     [rsp+68h+var_38], 73h ; 's'
0x14004e317  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seid
0x14004e31c  test    rbx, rbx
0x14004e31f  jnz     short loc_14004E32B
0x14004e321  mov     eax, 0C000000Dh
0x14004e326  jmp     loc_14004E402
0x14004e32b  lea     r8, [rsp+68h+arg_0]; enum TAG_AvdtpSepState *
0x14004e330  mov     [rsp+68h+arg_0], 0
0x14004e338  mov     dl, dil; unsigned __int8
0x14004e33b  mov     rcx, rbx; this
0x14004e33e  call    ?FindEndpointIndexByRemoteSeid_AndReturnState@Avdtp_impl@@AEAAKEAEAW4TAG_AvdtpSepState@@@Z; Avdtp_impl::FindEndpointIndexByRemoteSeid_AndReturnState(uchar,TAG_AvdtpSepState &)
0x14004e343  cmp     eax, 4
0x14004e346  jnb     short loc_14004E37B
0x14004e348  cmp     [rsp+68h+arg_0], 1
0x14004e34d  jnz     short loc_14004E378
0x14004e34f  xor     eax, eax
0x14004e351  shl     dil, 2
0x14004e355  mov     r8b, 6; char
0x14004e358  mov     word ptr [rsp+68h+arg_0], ax
0x14004e35d  lea     rdx, [rsp+68h+arg_0]; struct _SINGLE_PCK_CMD *
0x14004e362  mov     byte ptr [rsp+68h+arg_0+2], dil
0x14004e367  mov     rcx, rbx; this
0x14004e36a  lea     r9d, [rax+3]; unsigned int
0x14004e36e  call    ?LabelAndSendCommand@Avdtp_impl@@AEAAXPEAU_SINGLE_PCK_CMD@@EK@Z; Avdtp_impl::LabelAndSendCommand(_SINGLE_PCK_CMD *,uchar,ulong)
0x14004e373  jmp     loc_14004E400
0x14004e378  cmp     eax, 4
0x14004e37b  sbb     sil, sil
0x14004e37e  lea     rbp, [rbx+640h]
0x14004e385  and     sil, 1Fh
0x14004e389  mov     rcx, rbp; SpinLock
0x14004e38c  add     sil, 12h
0x14004e390  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004e397  nop     dword ptr [rax+rax+00h]
0x14004e39c  mov     rdi, [rbx+478h]
0x14004e3a3  mov     r14b, al
0x14004e3a6  test    rdi, rdi
0x14004e3a9  jz      short loc_14004E3BA
0x14004e3ab  mov     rax, [rbx+490h]
0x14004e3b2  mov     rcx, rdi
0x14004e3b5  call    _guard_dispatch_icall
0x14004e3ba  mov     dl, r14b; NewIrql
0x14004e3bd  mov     rcx, rbp; SpinLock
0x14004e3c0  call    cs:__imp_KeReleaseSpinLock
0x14004e3c7  nop     dword ptr [rax+rax+00h]
0x14004e3cc  test    rdi, rdi
0x14004e3cf  jz      short loc_14004E400
0x14004e3d1  mov     rax, [rbx+528h]
0x14004e3d8  xor     r9d, r9d
0x14004e3db  mov     r8b, sil
0x14004e3de  mov     [rsp+68h+var_48], 0
0x14004e3e6  mov     rdx, rdi
0x14004e3e9  mov     rcx, rbx
0x14004e3ec  call    _guard_dispatch_icall
0x14004e3f1  mov     rax, [rbx+498h]
0x14004e3f8  mov     rcx, rdi
0x14004e3fb  call    _guard_dispatch_icall
0x14004e400  xor     eax, eax
0x14004e402  lea     r11, [rsp+68h+var_18]
0x14004e407  mov     rbx, [r11+28h]
0x14004e40b  mov     rbp, [r11+30h]
0x14004e40f  mov     rsp, r11
0x14004e412  pop     r14
0x14004e414  pop     rdi
0x14004e415  pop     rsi
0x14004e416  retn
```
