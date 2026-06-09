# A2DP_Device::AVDT_Close_Ind(long,void *,void *,uchar)

- ea: `0x14002f4a0`
- end: `0x14002f607`
- name: `?AVDT_Close_Ind@A2DP_Device@@CAJJPEAX0E@Z`
- size: `359`
- prototype: `static int(int, void *, void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x140007374`
- `0x1400077e0`
- `0x14001bd20`
- `0x140020a70`
- `0x14002bdbc`
- `0x14002f4a0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002f5b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f5b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f580`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f580`

## string_xrefs

- `0x14002f55d`: `Codec is not get configured even though there is matching SEID`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Close_Ind(unsigned int a1, void *a2, void *a3, char a4)
{
  int Timer_high; // edx
  struct A2DP_Device *v7; // rbx
  __int64 v8; // r8
  A2dpRole *v9; // rcx
  char v10; // bp
  KIRQL v11; // al
  __int64 v12; // rdi
  KIRQL v13; // r14
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8

  v7 = A2DP_Device::CheckCallbackParms(a2, a3);
  LOBYTE(Timer_high) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer), (Timer_high & 0x10) != 0)
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)Timer_high || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      Timer_high,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      135,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v7);
  A2DP_Device::SetLastAvdtpActivity(v7, 39, v8);
  v9 = (A2dpRole *)*((_QWORD *)v7 + 1);
  if ( a4 == *((_BYTE *)v9 + 105) )
  {
    v10 = 0;
    if ( !A2dpRole::IsCodecConfigured(v9) )
      MicrosoftTelemetryAssertTriggeredMsgKM("Codec is not get configured even though there is matching SEID");
    A2DP_Device::SetConnectionClosedUnlocked(v7);
  }
  else
  {
    v10 = 18;
  }
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 87);
  v12 = *((_QWORD *)v7 + 50);
  v13 = v11;
  if ( v12 )
    (*((void (__fastcall **)(_QWORD))v7 + 53))(*((_QWORD *)v7 + 50));
  KeReleaseSpinLock((PKSPIN_LOCK)v7 + 87, v13);
  if ( v12 )
  {
    A2DP_Device::SetLastAvdtpActivity(v7, 40, v14);
    LOBYTE(v15) = v10;
    LOBYTE(v16) = a4;
    (*((void (__fastcall **)(_QWORD, __int64, __int64, __int64))v7 + 79))(a1, v12, v16, v15);
    (*((void (__fastcall **)(__int64))v7 + 54))(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x14002f4a0  push    rbx
0x14002f4a2  push    rbp
0x14002f4a3  push    rsi
0x14002f4a4  push    rdi
0x14002f4a5  push    r12
0x14002f4a7  push    r14
0x14002f4a9  push    r15
0x14002f4ab  sub     rsp, 50h
0x14002f4af  mov     rax, rdx
0x14002f4b2  mov     r12d, ecx
0x14002f4b5  mov     rcx, rax; void *
0x14002f4b8  mov     rdx, r8; void *
0x14002f4bb  mov     r15b, r9b
0x14002f4be  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x14002f4c3  mov     rbx, rax
0x14002f4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f4cd  lea     rax, WPP_GLOBAL_Control
0x14002f4d4  cmp     rcx, rax
0x14002f4d7  jz      short loc_14002F4EB
0x14002f4d9  mov     edx, [rcx+2Ch]
0x14002f4dc  test    dl, 10h
0x14002f4df  jz      short loc_14002F4EB
0x14002f4e1  cmp     byte ptr [rcx+29h], 4
0x14002f4e5  jb      short loc_14002F4EB
0x14002f4e7  mov     dl, 1
0x14002f4e9  jmp     short loc_14002F4ED
0x14002f4eb  xor     dl, dl
0x14002f4ed  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f4f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f4fb  setnz   r8b
0x14002f4ff  test    dl, dl
0x14002f501  jnz     short loc_14002F508
0x14002f503  test    r8b, r8b
0x14002f506  jz      short loc_14002F53A
0x14002f508  mov     r9, [rcx+40h]
0x14002f50c  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14002f513  mov     rcx, [rcx+18h]
0x14002f517  mov     [rsp+88h+var_48], rbx
0x14002f51c  mov     [rsp+88h+var_50], rax
0x14002f521  mov     [rsp+88h+var_58], 87h
0x14002f528  mov     [rsp+88h+var_60], 5
0x14002f530  mov     [rsp+88h+var_68], 4
0x14002f535  call    WPP_RECORDER_AND_TRACE_SF_q
0x14002f53a  mov     edx, 27h ; '''
0x14002f53f  mov     rcx, rbx
0x14002f542  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14002f547  mov     rcx, [rbx+8]; this
0x14002f54b  cmp     r15b, [rcx+69h]
0x14002f54f  jnz     short loc_14002F573
0x14002f551  xor     bpl, bpl
0x14002f554  call    ?IsCodecConfigured@A2dpRole@@QEAA_NXZ; A2dpRole::IsCodecConfigured(void)
0x14002f559  test    al, al
0x14002f55b  jnz     short loc_14002F569
0x14002f55d  lea     rcx, aCodecIsNotGetC; "Codec is not get configured even though"...
0x14002f564  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002f569  mov     rcx, rbx; this
0x14002f56c  call    ?SetConnectionClosedUnlocked@A2DP_Device@@AEAAXXZ; A2DP_Device::SetConnectionClosedUnlocked(void)
0x14002f571  jmp     short loc_14002F576
0x14002f573  mov     bpl, 12h
0x14002f576  lea     rsi, [rbx+2B8h]
0x14002f57d  mov     rcx, rsi; SpinLock
0x14002f580  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f587  nop     dword ptr [rax+rax+00h]
0x14002f58c  mov     rdi, [rbx+190h]
0x14002f593  mov     r14b, al
0x14002f596  test    rdi, rdi
0x14002f599  jz      short loc_14002F5AA
0x14002f59b  mov     rax, [rbx+1A8h]
0x14002f5a2  mov     rcx, rdi
0x14002f5a5  call    _guard_dispatch_icall
0x14002f5aa  mov     dl, r14b; NewIrql
0x14002f5ad  mov     rcx, rsi; SpinLock
0x14002f5b0  call    cs:__imp_KeReleaseSpinLock
0x14002f5b7  nop     dword ptr [rax+rax+00h]
0x14002f5bc  test    rdi, rdi
0x14002f5bf  jz      short loc_14002F5F5
0x14002f5c1  mov     edx, 28h ; '('
0x14002f5c6  mov     rcx, rbx
0x14002f5c9  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x14002f5ce  mov     rax, [rbx+278h]
0x14002f5d5  mov     r9b, bpl
0x14002f5d8  mov     r8b, r15b
0x14002f5db  mov     rdx, rdi
0x14002f5de  mov     ecx, r12d
0x14002f5e1  call    _guard_dispatch_icall
0x14002f5e6  mov     rax, [rbx+1B0h]
0x14002f5ed  mov     rcx, rdi
0x14002f5f0  call    _guard_dispatch_icall
0x14002f5f5  xor     eax, eax
0x14002f5f7  add     rsp, 50h
0x14002f5fb  pop     r15
0x14002f5fd  pop     r14
0x14002f5ff  pop     r12
0x14002f601  pop     rdi
0x14002f602  pop     rsi
0x14002f603  pop     rbp
0x14002f604  pop     rbx
0x14002f605  retn
```
