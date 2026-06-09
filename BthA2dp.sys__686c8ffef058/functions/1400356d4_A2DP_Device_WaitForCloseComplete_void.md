# A2DP_Device::WaitForCloseComplete(void)

- ea: `0x1400356d4`
- end: `0x140035862`
- name: `?WaitForCloseComplete@A2DP_Device@@AEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140032d7c`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x14001bd20`
- `0x1400355fc`
- `0x1400356d4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003578a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400357df`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003578a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400357df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035770`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035770`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400357b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400357b2`

## string_xrefs

- `0x1400357c7`: `Waited for close to complete for over 10 seconds`

## pseudocode

```c
__int64 __fastcall A2DP_Device::WaitForCloseComplete(KSPIN_LOCK *this)
{
  char v2; // bl
  bool v3; // dl
  KIRQL v4; // al
  KSPIN_LOCK *v5; // rcx
  int v6; // edx
  unsigned int v7; // esi
  int v8; // r8d
  union _LARGE_INTEGER Timeout; // [rsp+80h] [rbp+8h] BYREF

  Timeout.QuadPart = -100000000;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      6,
      14,
      (__int64)WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids);
  v4 = KeAcquireSpinLockRaiseToDpc(this + 87);
  v5 = this + 87;
  if ( *((_BYTE *)this + 818) )
  {
    KeReleaseSpinLock(v5, v4);
    v7 = KeWaitForSingleObject(this + 99, Executive, 0, 0, &Timeout);
    if ( v7 == 258 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Waited for close to complete for over 10 seconds");
      A2DP_Device::SetCloseCompleteEvent((A2DP_Device *)this);
    }
  }
  else
  {
    v7 = 0;
    KeReleaseSpinLock(v5, v4);
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v2 = 0;
  }
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = v2;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      6,
      15,
      (__int64)WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1400356d4  mov     rax, rsp
0x1400356d7  mov     [rax+10h], rbx
0x1400356db  mov     [rax+18h], rbp
0x1400356df  push    rsi
0x1400356e0  push    rdi
0x1400356e1  push    r13
0x1400356e3  push    r14
0x1400356e5  push    r15
0x1400356e7  sub     rsp, 50h
0x1400356eb  mov     rdi, rcx
0x1400356ee  mov     qword ptr [rax+8], 0FFFFFFFFFA0A1F00h
0x1400356f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400356fd  lea     r14, WPP_GLOBAL_Control
0x140035704  mov     bl, 1
0x140035706  cmp     rcx, r14
0x140035709  jz      short loc_14003571C
0x14003570b  mov     eax, [rcx+2Ch]
0x14003570e  test    al, 20h
0x140035710  jz      short loc_14003571C
0x140035712  cmp     byte ptr [rcx+29h], 4
0x140035716  jb      short loc_14003571C
0x140035718  mov     dl, bl
0x14003571a  jmp     short loc_14003571E
0x14003571c  xor     dl, dl
0x14003571e  lea     r15, WPP_RECORDER_INITIALIZED
0x140035725  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003572c  lea     r13, WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids
0x140035733  setnz   r8b
0x140035737  test    dl, dl
0x140035739  jnz     short loc_140035740
0x14003573b  test    r8b, r8b
0x14003573e  jz      short loc_140035766
0x140035740  mov     r9, [rcx+40h]
0x140035744  mov     rcx, [rcx+18h]
0x140035748  mov     [rsp+78h+var_40], r13
0x14003574d  mov     [rsp+78h+var_48], 0Eh
0x140035754  mov     [rsp+78h+var_50], 6
0x14003575c  mov     byte ptr [rsp+78h+Timeout], 4
0x140035761  call    WPP_RECORDER_AND_TRACE_SF_
0x140035766  lea     rbp, [rdi+2B8h]
0x14003576d  mov     rcx, rbp; SpinLock
0x140035770  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035777  nop     dword ptr [rax+rax+00h]
0x14003577c  cmp     byte ptr [rdi+332h], 0
0x140035783  mov     rcx, rbp; SpinLock
0x140035786  mov     dl, al; NewIrql
0x140035788  jz      short loc_1400357DD
0x14003578a  call    cs:__imp_KeReleaseSpinLock
0x140035791  nop     dword ptr [rax+rax+00h]
0x140035796  lea     rax, [rsp+78h+arg_0]
0x14003579e  xor     r9d, r9d; Alertable
0x1400357a1  lea     rcx, [rdi+318h]; Object
0x1400357a8  mov     [rsp+78h+Timeout], rax; Timeout
0x1400357ad  xor     r8d, r8d; WaitMode
0x1400357b0  xor     edx, edx; WaitReason
0x1400357b2  call    cs:__imp_KeWaitForSingleObject
0x1400357b9  nop     dword ptr [rax+rax+00h]
0x1400357be  mov     esi, eax
0x1400357c0  cmp     eax, 102h
0x1400357c5  jnz     short loc_1400357EB
0x1400357c7  lea     rcx, aWaitedForClose; "Waited for close to complete for over 1"...
0x1400357ce  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400357d3  mov     rcx, rdi; this
0x1400357d6  call    ?SetCloseCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetCloseCompleteEvent(void)
0x1400357db  jmp     short loc_1400357EB
0x1400357dd  xor     esi, esi
0x1400357df  call    cs:__imp_KeReleaseSpinLock
0x1400357e6  nop     dword ptr [rax+rax+00h]
0x1400357eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357f2  cmp     rcx, r14
0x1400357f5  jz      short loc_140035804
0x1400357f7  mov     eax, [rcx+2Ch]
0x1400357fa  test    al, 20h
0x1400357fc  jz      short loc_140035804
0x1400357fe  cmp     byte ptr [rcx+29h], 4
0x140035802  jnb     short loc_140035806
0x140035804  xor     bl, bl
0x140035806  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14003580d  setnz   r8b
0x140035811  test    bl, bl
0x140035813  jnz     short loc_14003581A
0x140035815  test    r8b, r8b
0x140035818  jz      short loc_140035846
0x14003581a  mov     r9, [rcx+40h]
0x14003581e  mov     dl, bl
0x140035820  mov     rcx, [rcx+18h]
0x140035824  mov     [rsp+78h+var_38], esi
0x140035828  mov     [rsp+78h+var_40], r13
0x14003582d  mov     [rsp+78h+var_48], 0Fh
0x140035834  mov     [rsp+78h+var_50], 6
0x14003583c  mov     byte ptr [rsp+78h+Timeout], 4
0x140035841  call    WPP_RECORDER_AND_TRACE_SF_d
0x140035846  lea     r11, [rsp+78h+var_28]
0x14003584b  mov     eax, esi
0x14003584d  mov     rbx, [r11+38h]
0x140035851  mov     rbp, [r11+40h]
0x140035855  mov     rsp, r11
0x140035858  pop     r15
0x14003585a  pop     r14
0x14003585c  pop     r13
0x14003585e  pop     rdi
0x14003585f  pop     rsi
0x140035860  retn
```
