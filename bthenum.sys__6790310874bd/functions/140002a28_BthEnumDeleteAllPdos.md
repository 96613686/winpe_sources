# BthEnumDeleteAllPdos

- ea: `0x140002a28`
- end: `0x140002b5d`
- name: `BthEnumDeleteAllPdos`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001cf90`

## callees

- `0x1400016fc`
- `0x140002a28`
- `0x14001e160`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140002a3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002b11`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002a3a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002b11`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002a50`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002b20`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002a50`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002b20`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002aa2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002b34`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002aa2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002b34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002aae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002b40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002aae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002b40`
- `ntoskrnl!IoDeleteDevice` at `0x140002b05`
- `ntoskrnl!IoDeleteDevice` at `0x140002b05`
- `ntoskrnl!RtlRbRemoveNode` at `0x140002a93`
- `ntoskrnl!RtlRbRemoveNode` at `0x140002a93`

## pseudocode

```c
void __fastcall BthEnumDeleteAllPdos(__int64 a1)
{
  struct _FAST_MUTEX *v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rbx
  int v7; // edx

  KeEnterCriticalRegion();
  v2 = (struct _FAST_MUTEX *)(a1 + 152);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 152));
  v3 = a1 + 136;
  while ( 1 )
  {
    if ( (*(_BYTE *)(v3 + 8) & 1) != 0 )
    {
      v4 = *(_QWORD *)v3;
      if ( !*(_QWORD *)v3 )
        break;
      v5 = v3 ^ v4;
    }
    else
    {
      v5 = *(_QWORD *)v3;
      v4 = *(_QWORD *)v3;
    }
    if ( !v5 )
      break;
    v6 = v4 - 80;
    RtlRbRemoveNode(v3, v4);
    ExReleaseFastMutexUnsafe(v2);
    KeLeaveCriticalRegion();
    BthEnumDestroyPdoExt(v6);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        4,
        19,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
        *(_QWORD *)(v6 + 16));
    IoDeleteDevice(*(PDEVICE_OBJECT *)(v6 + 16));
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe(v2);
  }
  ExReleaseFastMutexUnsafe(v2);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140002a28  mov     [rsp+arg_0], rbx
0x140002a2d  mov     [rsp+arg_8], rsi
0x140002a32  push    rdi
0x140002a33  sub     rsp, 30h
0x140002a37  mov     rbx, rcx
0x140002a3a  call    cs:__imp_KeEnterCriticalRegion
0x140002a41  nop     dword ptr [rax+rax+00h]
0x140002a46  lea     rsi, [rbx+98h]
0x140002a4d  mov     rcx, rsi; FastMutex
0x140002a50  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140002a57  nop     dword ptr [rax+rax+00h]
0x140002a5c  lea     rdi, [rbx+88h]
0x140002a63  test    byte ptr [rdi+8], 1
0x140002a67  jz      short loc_140002A7D
0x140002a69  mov     rdx, [rdi]
0x140002a6c  test    rdx, rdx
0x140002a6f  jz      loc_140002B31
0x140002a75  mov     rax, rdx
0x140002a78  xor     rax, rdi
0x140002a7b  jmp     short loc_140002A83
0x140002a7d  mov     rax, [rdi]
0x140002a80  mov     rdx, rax
0x140002a83  test    rax, rax
0x140002a86  jz      loc_140002B31
0x140002a8c  mov     rcx, rdi
0x140002a8f  lea     rbx, [rdx-50h]
0x140002a93  call    cs:__imp_RtlRbRemoveNode
0x140002a9a  nop     dword ptr [rax+rax+00h]
0x140002a9f  mov     rcx, rsi; FastMutex
0x140002aa2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140002aa9  nop     dword ptr [rax+rax+00h]
0x140002aae  call    cs:__imp_KeLeaveCriticalRegion
0x140002ab5  nop     dword ptr [rax+rax+00h]
0x140002aba  mov     rcx, rbx
0x140002abd  call    BthEnumDestroyPdoExt
0x140002ac2  lea     rax, WPP_RECORDER_INITIALIZED
0x140002ac9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002ad0  jz      short loc_140002B01
0x140002ad2  mov     rax, [rbx+10h]
0x140002ad6  mov     r9d, 13h
0x140002adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ae3  mov     [rsp+38h+var_10], rax
0x140002ae8  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140002aef  mov     [rsp+38h+var_18], rax
0x140002af4  lea     r8d, [r9-0Fh]
0x140002af8  mov     rcx, [rcx+40h]
0x140002afc  call    WPP_RECORDER_SF_q
0x140002b01  mov     rcx, [rbx+10h]; DeviceObject
0x140002b05  call    cs:__imp_IoDeleteDevice
0x140002b0c  nop     dword ptr [rax+rax+00h]
0x140002b11  call    cs:__imp_KeEnterCriticalRegion
0x140002b18  nop     dword ptr [rax+rax+00h]
0x140002b1d  mov     rcx, rsi; FastMutex
0x140002b20  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140002b27  nop     dword ptr [rax+rax+00h]
0x140002b2c  jmp     loc_140002A63
0x140002b31  mov     rcx, rsi; FastMutex
0x140002b34  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140002b3b  nop     dword ptr [rax+rax+00h]
0x140002b40  call    cs:__imp_KeLeaveCriticalRegion
0x140002b47  nop     dword ptr [rax+rax+00h]
0x140002b4c  mov     rbx, [rsp+38h+arg_0]
0x140002b51  mov     rsi, [rsp+38h+arg_8]
0x140002b56  add     rsp, 30h
0x140002b5a  pop     rdi
0x140002b5b  retn
```
