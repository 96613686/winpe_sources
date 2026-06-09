# A2DP_Device::DiscoveryTimerWorker(void)

- ea: `0x140030abc`
- end: `0x140030ba3`
- name: `?DiscoveryTimerWorker@A2DP_Device@@AEAAXXZ`
- size: `231`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140030bb0`

## callees

- `0x1400077e0`
- `0x140030abc`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140030b8d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140030b8d`
- `ntoskrnl!KeResetEvent` at `0x140030b42`
- `ntoskrnl!KeResetEvent` at `0x140030b42`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030b02`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030b02`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030ad2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030ad2`

## pseudocode

```c
void __fastcall A2DP_Device::DiscoveryTimerWorker(A2DP_Device *this)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // al
  __int64 v4; // rdi
  KIRQL v5; // bp
  __int64 v6; // rax
  __int64 v7; // r8

  v1 = (KSPIN_LOCK *)((char *)this + 696);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 87);
  v4 = *((_QWORD *)this + 50);
  v5 = v3;
  if ( v4 )
    (*((void (__fastcall **)(_QWORD))this + 53))(*((_QWORD *)this + 50));
  KeReleaseSpinLock(v1, v5);
  if ( v4 )
  {
    if ( !*((_DWORD *)this + 98) && !*((_BYTE *)this + 817) )
    {
      v6 = *((_QWORD *)this + 1);
      if ( !v6 || !*(_BYTE *)(v6 + 90) )
      {
        *((_BYTE *)this + 817) = 1;
        KeResetEvent((PRKEVENT)this + 32);
        A2DP_Device::SetLastAvdtpActivity(this, 9, v7);
        (*((void (__fastcall **)(__int64))this + 62))(v4);
      }
    }
    (*((void (__fastcall **)(__int64))this + 54))(v4);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 824), A2DP_Device::DiscoveryTimerDpc, 0x20u);
}

```

## disassembly

```asm
0x140030abc  push    rbx
0x140030abe  push    rbp
0x140030abf  push    rsi
0x140030ac0  push    rdi
0x140030ac1  sub     rsp, 28h
0x140030ac5  lea     rsi, [rcx+2B8h]
0x140030acc  mov     rbx, rcx
0x140030acf  mov     rcx, rsi; SpinLock
0x140030ad2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030ad9  nop     dword ptr [rax+rax+00h]
0x140030ade  mov     rdi, [rbx+190h]
0x140030ae5  mov     bpl, al
0x140030ae8  test    rdi, rdi
0x140030aeb  jz      short loc_140030AFC
0x140030aed  mov     rax, [rbx+1A8h]
0x140030af4  mov     rcx, rdi
0x140030af7  call    _guard_dispatch_icall
0x140030afc  mov     dl, bpl; NewIrql
0x140030aff  mov     rcx, rsi; SpinLock
0x140030b02  call    cs:__imp_KeReleaseSpinLock
0x140030b09  nop     dword ptr [rax+rax+00h]
0x140030b0e  test    rdi, rdi
0x140030b11  jz      short loc_140030B79
0x140030b13  cmp     dword ptr [rbx+188h], 0
0x140030b1a  jnz     short loc_140030B6A
0x140030b1c  cmp     byte ptr [rbx+331h], 0
0x140030b23  jnz     short loc_140030B6A
0x140030b25  mov     rax, [rbx+8]
0x140030b29  test    rax, rax
0x140030b2c  jz      short loc_140030B34
0x140030b2e  cmp     byte ptr [rax+5Ah], 0
0x140030b32  jnz     short loc_140030B6A
0x140030b34  lea     rcx, [rbx+300h]; Event
0x140030b3b  mov     byte ptr [rbx+331h], 1
0x140030b42  call    cs:__imp_KeResetEvent
0x140030b49  nop     dword ptr [rax+rax+00h]
0x140030b4e  mov     edx, 9
0x140030b53  mov     rcx, rbx
0x140030b56  call    ?SetLastAvdtpActivity@A2DP_Device@@AEAAXW4LastAvdtpActivity@@@Z; A2DP_Device::SetLastAvdtpActivity(LastAvdtpActivity)
0x140030b5b  mov     rax, [rbx+1F0h]
0x140030b62  mov     rcx, rdi
0x140030b65  call    _guard_dispatch_icall
0x140030b6a  mov     rax, [rbx+1B0h]
0x140030b71  mov     rcx, rdi
0x140030b74  call    _guard_dispatch_icall
0x140030b79  lea     rcx, [rbx+338h]; RemoveLock
0x140030b80  mov     r8d, 20h ; ' '; RemlockSize
0x140030b86  lea     rdx, ?DiscoveryTimerDpc@A2DP_Device@@CAXPEAU_KDPC@@PEAX11@Z; Tag
0x140030b8d  call    cs:__imp_IoReleaseRemoveLockEx
0x140030b94  nop     dword ptr [rax+rax+00h]
0x140030b99  add     rsp, 28h
0x140030b9d  pop     rdi
0x140030b9e  pop     rsi
0x140030b9f  pop     rbp
0x140030ba0  pop     rbx
0x140030ba1  retn
```
