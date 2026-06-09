# BthEnumDeleteProtocol

- ea: `0x140002b64`
- end: `0x140002db7`
- name: `BthEnumDeleteProtocol`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019058`

## callees

- `0x140001328`
- `0x140001ab8`
- `0x140002b64`
- `0x14000442c`
- `0x140007d40`
- `0x14001e034`
- `0x14001e160`
- `0x14001f1ac`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140002c57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002c57`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002c6d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140002c6d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002cb4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002d48`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002cb4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140002d48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002cc0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002d54`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002cc0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002d54`
- `ntoskrnl!IofCompleteRequest` at `0x140002c4b`
- `ntoskrnl!IofCompleteRequest` at `0x140002c4b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002bc9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002bc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c0a`
- `ntoskrnl!IoDeleteDevice` at `0x140002d6c`
- `ntoskrnl!IoDeleteDevice` at `0x140002d6c`
- `ntoskrnl!RtlRbRemoveNode` at `0x140002d33`
- `ntoskrnl!RtlRbRemoveNode` at `0x140002d33`

## pseudocode

```c
void __fastcall BthEnumDeleteProtocol(__int64 a1, __int64 a2)
{
  void (__fastcall *v2)(_QWORD, _QWORD, __int64); // rbp
  __int64 v3; // rdi
  __int64 v4; // rbx
  KIRQL v6; // al
  __int64 v7; // rdx
  KIRQL v8; // r11
  int v9; // edx
  unsigned __int64 v10; // rbx
  int v11; // ebp
  int v12; // eax
  unsigned __int64 v13; // rax
  int v14; // edx

  v2 = 0;
  v3 = a2;
  v4 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      4,
      12,
      (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
      a1,
      a2);
  LOBYTE(a2) = 1;
  BthEnumUnregisterDeviceInterface(v3, a2);
  v6 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a1 + 88));
  v7 = *(_QWORD *)(v3 + 168);
  v8 = v6;
  if ( v7 )
  {
    if ( (unsigned __int8)IrpList_DequeueIrpLocked(a1 + 64, v7) )
      v4 = *(_QWORD *)(v3 + 168);
    *(_QWORD *)(v3 + 168) = 0;
    v2 = *(void (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 48);
  }
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a1 + 88), v8);
  if ( v2 )
    v2(*(_QWORD *)(a1 + 40), *(_QWORD *)(v3 + 192), 2);
  if ( v4 )
  {
    _InterlockedExchange64((volatile __int64 *)(v4 + 120), 0);
    *(_DWORD *)(v4 + 48) = -1073741667;
    IofCompleteRequest((PIRP)v4, 0);
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 152));
  if ( *(_DWORD *)(v3 + 176) == 3 )
  {
    v10 = *(_QWORD *)(a1 + 136);
    if ( (*(_BYTE *)(a1 + 144) & 1) != 0 && v10 )
      v10 ^= a1 + 136;
    v11 = *(_BYTE *)(a1 + 144) & 1;
    if ( v10 )
    {
      do
      {
        v12 = BthEnumChildCompare(v3, v10);
        if ( v12 >= 0 )
        {
          if ( v12 <= 0 )
            break;
          v13 = *(_QWORD *)(v10 + 8);
        }
        else
        {
          v13 = *(_QWORD *)v10;
        }
        if ( v11 && v13 )
          v10 ^= v13;
        else
          v10 = v13;
      }
      while ( v10 );
      if ( v10 )
      {
        RtlRbRemoveNode(a1 + 136, v3 + 80);
        --*(_DWORD *)(a1 + 252);
      }
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 152));
    KeLeaveCriticalRegion();
    BthEnumDestroyPdoExt(v3);
    IoDeleteDevice(*(PDEVICE_OBJECT *)(v3 + 16));
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        4,
        14,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        4,
        13,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 152));
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140002b64  push    rbx
0x140002b66  push    rbp
0x140002b67  push    rsi
0x140002b68  push    rdi
0x140002b69  push    r12
0x140002b6b  push    r14
0x140002b6d  push    r15
0x140002b6f  sub     rsp, 40h
0x140002b73  xor     ebp, ebp
0x140002b75  mov     rdi, rdx
0x140002b78  xor     ebx, ebx
0x140002b7a  mov     rsi, rcx
0x140002b7d  lea     r12, WPP_RECORDER_INITIALIZED
0x140002b84  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002b8b  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140002b92  jz      short loc_140002BBB
0x140002b94  mov     [rsp+78h+var_48], rdx
0x140002b99  lea     r9d, [rbp+0Ch]
0x140002b9d  mov     [rsp+78h+var_50], rcx
0x140002ba2  lea     r8d, [rbp+4]
0x140002ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x140002bad  mov     [rsp+78h+var_58], rax
0x140002bb2  mov     rcx, [rcx+40h]
0x140002bb6  call    WPP_RECORDER_SF_qq
0x140002bbb  mov     dl, 1
0x140002bbd  mov     rcx, rdi
0x140002bc0  call    BthEnumUnregisterDeviceInterface
0x140002bc5  mov     rcx, [rsi+58h]; SpinLock
0x140002bc9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002bd0  nop     dword ptr [rax+rax+00h]
0x140002bd5  mov     rdx, [rdi+0A8h]
0x140002bdc  mov     r11b, al
0x140002bdf  test    rdx, rdx
0x140002be2  jz      short loc_140002C03
0x140002be4  lea     rcx, [rsi+40h]
0x140002be8  call    IrpList_DequeueIrpLocked
0x140002bed  test    al, al
0x140002bef  jz      short loc_140002BF8
0x140002bf1  mov     rbx, [rdi+0A8h]
0x140002bf8  mov     [rdi+0A8h], rbp
0x140002bff  mov     rbp, [rsi+30h]
0x140002c03  mov     rcx, [rsi+58h]; SpinLock
0x140002c07  mov     dl, r11b; NewIrql
0x140002c0a  call    cs:__imp_KeReleaseSpinLock
0x140002c11  nop     dword ptr [rax+rax+00h]
0x140002c16  test    rbp, rbp
0x140002c19  jz      short loc_140002C34
0x140002c1b  mov     rdx, [rdi+0C0h]
0x140002c22  mov     r8d, 2
0x140002c28  mov     rcx, [rsi+28h]
0x140002c2c  mov     rax, rbp
0x140002c2f  call    _guard_dispatch_icall
0x140002c34  test    rbx, rbx
0x140002c37  jz      short loc_140002C57
0x140002c39  xor     eax, eax
0x140002c3b  xor     edx, edx; PriorityBoost
0x140002c3d  xchg    rax, [rbx+78h]
0x140002c41  mov     rcx, rbx; Irp
0x140002c44  mov     dword ptr [rbx+30h], 0C000009Dh
0x140002c4b  call    cs:__imp_IofCompleteRequest
0x140002c52  nop     dword ptr [rax+rax+00h]
0x140002c57  call    cs:__imp_KeEnterCriticalRegion
0x140002c5e  nop     dword ptr [rax+rax+00h]
0x140002c63  lea     r15, [rsi+98h]
0x140002c6a  mov     rcx, r15; FastMutex
0x140002c6d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140002c74  nop     dword ptr [rax+rax+00h]
0x140002c79  cmp     dword ptr [rdi+0B0h], 3
0x140002c80  jz      short loc_140002CD1
0x140002c82  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002c89  jz      short loc_140002CB1
0x140002c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c92  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140002c99  mov     r9d, 0Dh
0x140002c9f  mov     [rsp+78h+var_58], rax
0x140002ca4  mov     rcx, [rcx+40h]
0x140002ca8  lea     r8d, [r9-9]
0x140002cac  call    WPP_RECORDER_SF_
0x140002cb1  mov     rcx, r15; FastMutex
0x140002cb4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140002cbb  nop     dword ptr [rax+rax+00h]
0x140002cc0  call    cs:__imp_KeLeaveCriticalRegion
0x140002cc7  nop     dword ptr [rax+rax+00h]
0x140002ccc  jmp     loc_140002DA7
0x140002cd1  lea     r14, [rsi+88h]
0x140002cd8  test    byte ptr [r14+8], 1
0x140002cdd  mov     rbx, [r14]
0x140002ce0  jz      short loc_140002CEA
0x140002ce2  test    rbx, rbx
0x140002ce5  jz      short loc_140002CEA
0x140002ce7  xor     rbx, r14
0x140002cea  movzx   ebp, byte ptr [r14+8]
0x140002cef  and     ebp, 1
0x140002cf2  test    rbx, rbx
0x140002cf5  jz      short loc_140002D45
0x140002cf7  mov     rdx, rbx
0x140002cfa  mov     rcx, rdi
0x140002cfd  call    BthEnumChildCompare
0x140002d02  test    eax, eax
0x140002d04  jns     short loc_140002D0B
0x140002d06  mov     rax, [rbx]
0x140002d09  jmp     short loc_140002D11
0x140002d0b  jle     short loc_140002D27
0x140002d0d  mov     rax, [rbx+8]
0x140002d11  test    ebp, ebp
0x140002d13  jz      short loc_140002D1F
0x140002d15  test    rax, rax
0x140002d18  jz      short loc_140002D1F
0x140002d1a  xor     rbx, rax
0x140002d1d  jmp     short loc_140002D22
0x140002d1f  mov     rbx, rax
0x140002d22  test    rbx, rbx
0x140002d25  jnz     short loc_140002CF7
0x140002d27  test    rbx, rbx
0x140002d2a  jz      short loc_140002D45
0x140002d2c  lea     rdx, [rdi+50h]
0x140002d30  mov     rcx, r14
0x140002d33  call    cs:__imp_RtlRbRemoveNode
0x140002d3a  nop     dword ptr [rax+rax+00h]
0x140002d3f  dec     dword ptr [rsi+0FCh]
0x140002d45  mov     rcx, r15; FastMutex
0x140002d48  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140002d4f  nop     dword ptr [rax+rax+00h]
0x140002d54  call    cs:__imp_KeLeaveCriticalRegion
0x140002d5b  nop     dword ptr [rax+rax+00h]
0x140002d60  mov     rcx, rdi
0x140002d63  call    BthEnumDestroyPdoExt
0x140002d68  mov     rcx, [rdi+10h]; DeviceObject
0x140002d6c  call    cs:__imp_IoDeleteDevice
0x140002d73  nop     dword ptr [rax+rax+00h]
0x140002d78  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002d7f  jz      short loc_140002DA7
0x140002d81  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d88  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x140002d8f  mov     r9d, 0Eh
0x140002d95  mov     [rsp+78h+var_58], rax
0x140002d9a  mov     rcx, [rcx+40h]
0x140002d9e  lea     r8d, [r9-0Ah]
0x140002da2  call    WPP_RECORDER_SF_
0x140002da7  add     rsp, 40h
0x140002dab  pop     r15
0x140002dad  pop     r14
0x140002daf  pop     r12
0x140002db1  pop     rdi
0x140002db2  pop     rsi
0x140002db3  pop     rbp
0x140002db4  pop     rbx
0x140002db5  retn
```
