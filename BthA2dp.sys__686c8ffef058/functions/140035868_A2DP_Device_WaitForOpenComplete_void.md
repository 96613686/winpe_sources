# A2DP_Device::WaitForOpenComplete(void)

- ea: `0x140035868`
- end: `0x1400359f6`
- name: `?WaitForOpenComplete@A2DP_Device@@AEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140032f78`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x14001bd20`
- `0x140035678`
- `0x140035868`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003591e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035973`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003591e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035973`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035904`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035904`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035946`
- `ntoskrnl!KeWaitForSingleObject` at `0x140035946`

## string_xrefs

- `0x14003595b`: `Waited for open to complete for over 30 seconds`

## pseudocode

```c
__int64 __fastcall A2DP_Device::WaitForOpenComplete(KSPIN_LOCK *this)
{
  char v2; // bl
  bool v3; // dl
  KIRQL v4; // al
  KSPIN_LOCK *v5; // rcx
  int v6; // edx
  unsigned int v7; // esi
  int v8; // r8d
  union _LARGE_INTEGER Timeout; // [rsp+80h] [rbp+8h] BYREF

  Timeout.QuadPart = -300000000;
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
      12,
      (__int64)WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids);
  v4 = KeAcquireSpinLockRaiseToDpc(this + 87);
  v5 = this + 87;
  if ( *((_BYTE *)this + 817) )
  {
    KeReleaseSpinLock(v5, v4);
    v7 = KeWaitForSingleObject(this + 96, Executive, 0, 0, &Timeout);
    if ( v7 == 258 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Waited for open to complete for over 30 seconds");
      A2DP_Device::SetOpenCompleteEvent((A2DP_Device *)this);
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
      13,
      (__int64)WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140035868  mov     rax, rsp
0x14003586b  mov     [rax+10h], rbx
0x14003586f  mov     [rax+18h], rbp
0x140035873  push    rsi
0x140035874  push    rdi
0x140035875  push    r13
0x140035877  push    r14
0x140035879  push    r15
0x14003587b  sub     rsp, 50h
0x14003587f  mov     rdi, rcx
0x140035882  mov     qword ptr [rax+8], 0FFFFFFFFEE1E5D00h
0x14003588a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035891  lea     r14, WPP_GLOBAL_Control
0x140035898  mov     bl, 1
0x14003589a  cmp     rcx, r14
0x14003589d  jz      short loc_1400358B0
0x14003589f  mov     eax, [rcx+2Ch]
0x1400358a2  test    al, 20h
0x1400358a4  jz      short loc_1400358B0
0x1400358a6  cmp     byte ptr [rcx+29h], 4
0x1400358aa  jb      short loc_1400358B0
0x1400358ac  mov     dl, bl
0x1400358ae  jmp     short loc_1400358B2
0x1400358b0  xor     dl, dl
0x1400358b2  lea     r15, WPP_RECORDER_INITIALIZED
0x1400358b9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400358c0  lea     r13, WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids
0x1400358c7  setnz   r8b
0x1400358cb  test    dl, dl
0x1400358cd  jnz     short loc_1400358D4
0x1400358cf  test    r8b, r8b
0x1400358d2  jz      short loc_1400358FA
0x1400358d4  mov     r9, [rcx+40h]
0x1400358d8  mov     rcx, [rcx+18h]
0x1400358dc  mov     [rsp+78h+var_40], r13
0x1400358e1  mov     [rsp+78h+var_48], 0Ch
0x1400358e8  mov     [rsp+78h+var_50], 6
0x1400358f0  mov     byte ptr [rsp+78h+Timeout], 4
0x1400358f5  call    WPP_RECORDER_AND_TRACE_SF_
0x1400358fa  lea     rbp, [rdi+2B8h]
0x140035901  mov     rcx, rbp; SpinLock
0x140035904  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003590b  nop     dword ptr [rax+rax+00h]
0x140035910  cmp     byte ptr [rdi+331h], 0
0x140035917  mov     rcx, rbp; SpinLock
0x14003591a  mov     dl, al; NewIrql
0x14003591c  jz      short loc_140035971
0x14003591e  call    cs:__imp_KeReleaseSpinLock
0x140035925  nop     dword ptr [rax+rax+00h]
0x14003592a  lea     rax, [rsp+78h+arg_0]
0x140035932  xor     r9d, r9d; Alertable
0x140035935  lea     rcx, [rdi+300h]; Object
0x14003593c  mov     [rsp+78h+Timeout], rax; Timeout
0x140035941  xor     r8d, r8d; WaitMode
0x140035944  xor     edx, edx; WaitReason
0x140035946  call    cs:__imp_KeWaitForSingleObject
0x14003594d  nop     dword ptr [rax+rax+00h]
0x140035952  mov     esi, eax
0x140035954  cmp     eax, 102h
0x140035959  jnz     short loc_14003597F
0x14003595b  lea     rcx, aWaitedForOpenT; "Waited for open to complete for over 30"...
0x140035962  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140035967  mov     rcx, rdi; this
0x14003596a  call    ?SetOpenCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetOpenCompleteEvent(void)
0x14003596f  jmp     short loc_14003597F
0x140035971  xor     esi, esi
0x140035973  call    cs:__imp_KeReleaseSpinLock
0x14003597a  nop     dword ptr [rax+rax+00h]
0x14003597f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035986  cmp     rcx, r14
0x140035989  jz      short loc_140035998
0x14003598b  mov     eax, [rcx+2Ch]
0x14003598e  test    al, 20h
0x140035990  jz      short loc_140035998
0x140035992  cmp     byte ptr [rcx+29h], 4
0x140035996  jnb     short loc_14003599A
0x140035998  xor     bl, bl
0x14003599a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400359a1  setnz   r8b
0x1400359a5  test    bl, bl
0x1400359a7  jnz     short loc_1400359AE
0x1400359a9  test    r8b, r8b
0x1400359ac  jz      short loc_1400359DA
0x1400359ae  mov     r9, [rcx+40h]
0x1400359b2  mov     dl, bl
0x1400359b4  mov     rcx, [rcx+18h]
0x1400359b8  mov     [rsp+78h+var_38], esi
0x1400359bc  mov     [rsp+78h+var_40], r13
0x1400359c1  mov     [rsp+78h+var_48], 0Dh
0x1400359c8  mov     [rsp+78h+var_50], 6
0x1400359d0  mov     byte ptr [rsp+78h+Timeout], 4
0x1400359d5  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400359da  lea     r11, [rsp+78h+var_28]
0x1400359df  mov     eax, esi
0x1400359e1  mov     rbx, [r11+38h]
0x1400359e5  mov     rbp, [r11+40h]
0x1400359e9  mov     rsp, r11
0x1400359ec  pop     r15
0x1400359ee  pop     r14
0x1400359f0  pop     r13
0x1400359f2  pop     rdi
0x1400359f3  pop     rsi
0x1400359f4  retn
```
