# Control_EP_WasDoorbellRungSinceMappingStart

- ea: `0x14004c000`
- end: `0x14004c0b0`
- name: `Control_EP_WasDoorbellRungSinceMappingStart`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14003e79c`
- `0x14004c000`
- `0x140057db0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004c034`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004c034`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004c016`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004c016`

## string_xrefs

- `0x14004c084`: `BUGBUG: Mapping state is not stopped before issuing Stop Endpoint command in ESM`

## pseudocode

```c
char __fastcall Control_EP_WasDoorbellRungSinceMappingStart(__int64 a1)
{
  KIRQL v2; // al
  unsigned int v3; // esi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r8

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v3 = *(_DWORD *)(a1 + 368) & 1;
  *(_BYTE *)(a1 + 104) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v2);
  IsEnabledDeviceUsageNoInline = Feature_ATFUR__private_IsEnabledDeviceUsageNoInline();
  v5 = 0;
  if ( IsEnabledDeviceUsageNoInline )
  {
    _m_prefetchw((const void *)(a1 + 108));
    if ( _InterlockedOr((volatile signed __int32 *)(a1 + 108), 0) )
    {
      v6 = *(_QWORD *)(a1 + 40);
      if ( *(_DWORD *)(v6 + 644) == 1 )
        v5 = *(unsigned __int16 *)(v6 + 652) | (*(unsigned __int16 *)(v6 + 648) << 16);
      v7 = v3;
      LODWORD(v7) = v3 | 0x200;
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        "USBXHCI.SYS",
        v5,
        v7,
        "BUGBUG: Mapping state is not stopped before issuing Stop Endpoint command in ESM");
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14004c000  mov     [rsp+arg_0], rbx
0x14004c005  mov     [rsp+arg_8], rsi
0x14004c00a  push    rdi
0x14004c00b  sub     rsp, 20h
0x14004c00f  mov     rdi, rcx
0x14004c012  add     rcx, 60h ; '`'; SpinLock
0x14004c016  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004c01d  nop     dword ptr [rax+rax+00h]
0x14004c022  mov     esi, [rdi+170h]
0x14004c028  lea     rcx, [rdi+60h]; SpinLock
0x14004c02c  and     esi, 1
0x14004c02f  mov     [rdi+68h], al
0x14004c032  mov     dl, al; NewIrql
0x14004c034  call    cs:__imp_KeReleaseSpinLock
0x14004c03b  nop     dword ptr [rax+rax+00h]
0x14004c040  call    Feature_ATFUR__private_IsEnabledDeviceUsageNoInline
0x14004c045  xor     edx, edx
0x14004c047  test    eax, eax
0x14004c049  jz      short loc_14004C09C
0x14004c04b  prefetchw byte ptr [rdi+6Ch]
0x14004c04f  mov     eax, [rdi+6Ch]
0x14004c052  mov     ecx, eax
0x14004c054  or      ecx, edx
0x14004c056  lock cmpxchg [rdi+6Ch], ecx
0x14004c05b  jnz     short loc_14004C052
0x14004c05d  test    eax, eax
0x14004c05f  jz      short loc_14004C09C
0x14004c061  mov     rax, [rdi+28h]; __annotation("Debug", "TelemetryAssert", "FALSE", "BUGBUG: Mapping state is not stopped before issuing Stop Endpoint command in ESM")
0x14004c065  cmp     dword ptr [rax+284h], 1
0x14004c06c  jnz     short loc_14004C081
0x14004c06e  movzx   edx, word ptr [rax+288h]
0x14004c075  movzx   eax, word ptr [rax+28Ch]
0x14004c07c  shl     edx, 10h
0x14004c07f  or      edx, eax
0x14004c081  mov     r8d, esi
0x14004c084  lea     r9, aBugbugMappingS; "BUGBUG: Mapping state is not stopped be"...
0x14004c08b  bts     r8d, 9
0x14004c090  lea     rcx, aUsbxhciSys_0; "USBXHCI.SYS"
0x14004c097  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14004c09c  mov     rbx, [rsp+28h+arg_0]
0x14004c0a1  mov     al, sil
0x14004c0a4  mov     rsi, [rsp+28h+arg_8]
0x14004c0a9  add     rsp, 20h
0x14004c0ad  pop     rdi
0x14004c0ae  retn
```
