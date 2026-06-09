# A2DP_Device::WaitForDisconnectComplete(void)

- ea: `0x140011bcc`
- end: `0x140011d5a`
- name: `?WaitForDisconnectComplete@A2DP_Device@@AEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(A2DP_Device *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140032564`
- `0x1400329ec`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x140011bcc`
- `0x14001bd20`
- `0x14001ea8c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011c82`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011cd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c82`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011cd7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c68`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c68`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011caa`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011caa`

## string_xrefs

- `0x140011cbf`: `Waited for disconnect to complete for over 10 seconds`

## pseudocode

```c
__int64 __fastcall A2DP_Device::WaitForDisconnectComplete(KSPIN_LOCK *this)
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
      10,
      (__int64)WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids);
  v4 = KeAcquireSpinLockRaiseToDpc(this + 87);
  v5 = this + 87;
  if ( *((_BYTE *)this + 816) )
  {
    KeReleaseSpinLock(v5, v4);
    v7 = KeWaitForSingleObject(this + 93, Executive, 0, 0, &Timeout);
    if ( v7 == 258 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Waited for disconnect to complete for over 10 seconds");
      A2DP_Device::SetDisconnectCompleteEvent((A2DP_Device *)this);
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
      11,
      (__int64)WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140011bcc  mov     rax, rsp
0x140011bcf  mov     [rax+10h], rbx
0x140011bd3  mov     [rax+18h], rbp
0x140011bd7  push    rsi
0x140011bd8  push    rdi
0x140011bd9  push    r13
0x140011bdb  push    r14
0x140011bdd  push    r15
0x140011bdf  sub     rsp, 50h
0x140011be3  mov     rdi, rcx
0x140011be6  mov     qword ptr [rax+8], 0FFFFFFFFFA0A1F00h
0x140011bee  mov     rcx, cs:WPP_GLOBAL_Control
0x140011bf5  lea     r14, WPP_GLOBAL_Control
0x140011bfc  mov     bl, 1
0x140011bfe  cmp     rcx, r14
0x140011c01  jz      short loc_140011C14
0x140011c03  mov     eax, [rcx+2Ch]
0x140011c06  test    al, 20h
0x140011c08  jz      short loc_140011C14
0x140011c0a  cmp     byte ptr [rcx+29h], 4
0x140011c0e  jb      short loc_140011C14
0x140011c10  mov     dl, bl
0x140011c12  jmp     short loc_140011C16
0x140011c14  xor     dl, dl
0x140011c16  lea     r15, WPP_RECORDER_INITIALIZED
0x140011c1d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140011c24  lea     r13, WPP_55000c8fcd04389f5f51c0c529de9a35_Traceguids
0x140011c2b  setnz   r8b
0x140011c2f  test    dl, dl
0x140011c31  jnz     short loc_140011C38
0x140011c33  test    r8b, r8b
0x140011c36  jz      short loc_140011C5E
0x140011c38  mov     r9, [rcx+40h]
0x140011c3c  mov     rcx, [rcx+18h]
0x140011c40  mov     [rsp+78h+var_40], r13
0x140011c45  mov     [rsp+78h+var_48], 0Ah
0x140011c4c  mov     [rsp+78h+var_50], 6
0x140011c54  mov     byte ptr [rsp+78h+Timeout], 4
0x140011c59  call    WPP_RECORDER_AND_TRACE_SF_
0x140011c5e  lea     rbp, [rdi+2B8h]
0x140011c65  mov     rcx, rbp; SpinLock
0x140011c68  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011c6f  nop     dword ptr [rax+rax+00h]
0x140011c74  cmp     byte ptr [rdi+330h], 0
0x140011c7b  mov     rcx, rbp; SpinLock
0x140011c7e  mov     dl, al; NewIrql
0x140011c80  jz      short loc_140011CD5
0x140011c82  call    cs:__imp_KeReleaseSpinLock
0x140011c89  nop     dword ptr [rax+rax+00h]
0x140011c8e  lea     rax, [rsp+78h+arg_0]
0x140011c96  xor     r9d, r9d; Alertable
0x140011c99  lea     rcx, [rdi+2E8h]; Object
0x140011ca0  mov     [rsp+78h+Timeout], rax; Timeout
0x140011ca5  xor     r8d, r8d; WaitMode
0x140011ca8  xor     edx, edx; WaitReason
0x140011caa  call    cs:__imp_KeWaitForSingleObject
0x140011cb1  nop     dword ptr [rax+rax+00h]
0x140011cb6  mov     esi, eax
0x140011cb8  cmp     eax, 102h
0x140011cbd  jnz     short loc_140011CE3
0x140011cbf  lea     rcx, aWaitedForDisco; "Waited for disconnect to complete for o"...
0x140011cc6  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140011ccb  mov     rcx, rdi; this
0x140011cce  call    ?SetDisconnectCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetDisconnectCompleteEvent(void)
0x140011cd3  jmp     short loc_140011CE3
0x140011cd5  xor     esi, esi
0x140011cd7  call    cs:__imp_KeReleaseSpinLock
0x140011cde  nop     dword ptr [rax+rax+00h]
0x140011ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cea  cmp     rcx, r14
0x140011ced  jz      short loc_140011CFC
0x140011cef  mov     eax, [rcx+2Ch]
0x140011cf2  test    al, 20h
0x140011cf4  jz      short loc_140011CFC
0x140011cf6  cmp     byte ptr [rcx+29h], 4
0x140011cfa  jnb     short loc_140011CFE
0x140011cfc  xor     bl, bl
0x140011cfe  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140011d05  setnz   r8b
0x140011d09  test    bl, bl
0x140011d0b  jnz     short loc_140011D12
0x140011d0d  test    r8b, r8b
0x140011d10  jz      short loc_140011D3E
0x140011d12  mov     r9, [rcx+40h]
0x140011d16  mov     dl, bl
0x140011d18  mov     rcx, [rcx+18h]
0x140011d1c  mov     [rsp+78h+var_38], esi
0x140011d20  mov     [rsp+78h+var_40], r13
0x140011d25  mov     [rsp+78h+var_48], 0Bh
0x140011d2c  mov     [rsp+78h+var_50], 6
0x140011d34  mov     byte ptr [rsp+78h+Timeout], 4
0x140011d39  call    WPP_RECORDER_AND_TRACE_SF_d
0x140011d3e  lea     r11, [rsp+78h+var_28]
0x140011d43  mov     eax, esi
0x140011d45  mov     rbx, [r11+38h]
0x140011d49  mov     rbp, [r11+40h]
0x140011d4d  mov     rsp, r11
0x140011d50  pop     r15
0x140011d52  pop     r14
0x140011d54  pop     r13
0x140011d56  pop     rdi
0x140011d57  pop     rsi
0x140011d58  retn
```
