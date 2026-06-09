# MbbWwanReferenceSessionForSessionId(_MINIPORT_ADAPTER_CONTEXT *,ulong)

- ea: `0x140001abc`
- end: `0x140001b2b`
- name: `?MbbWwanReferenceSessionForSessionId@@YAPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_MINIPORT_ADAPTER_CONTEXT@@K@Z`
- size: `111`
- prototype: `struct _MINIPORT_INTERFACE_CONTEXT *__fastcall(PKSPIN_LOCK SpinLock, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031d8`
- `0x1400061b0`
- `0x140007180`
- `0x14000f6c0`
- `0x14002253c`
- `0x140026698`
- `0x140026e44`
- `0x140031e20`
- `0x14003c670`
- `0x14003cdf8`
- `0x14003fa34`
- `0x14003ffbc`

## callees

- `0x140001abc`
- `0x140001cb4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001b0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001ad2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001ad2`

## pseudocode

```c
struct _MINIPORT_INTERFACE_CONTEXT *__fastcall MbbWwanReferenceSessionForSessionId(
        KSPIN_LOCK *SpinLock,
        unsigned int a2)
{
  struct _MINIPORT_INTERFACE_CONTEXT *v4; // rdi
  KSPIN_LOCK v5; // rcx

  v4 = 0;
  *((_BYTE *)SpinLock + 8) = KeAcquireSpinLockRaiseToDpc(SpinLock);
  if ( a2 < *((_DWORD *)SpinLock + 10) )
  {
    v5 = SpinLock[143];
    if ( *(_BYTE *)(v5 + 16LL * a2 + 8) )
    {
      v4 = *(struct _MINIPORT_INTERFACE_CONTEXT **)(v5 + 16LL * a2);
      ReferenceSession(v4);
    }
  }
  KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
  return v4;
}

```

## disassembly

```asm
0x140001abc  mov     [rsp+arg_0], rbx
0x140001ac1  mov     [rsp+arg_8], rsi
0x140001ac6  push    rdi
0x140001ac7  sub     rsp, 20h
0x140001acb  mov     esi, edx
0x140001acd  mov     rbx, rcx
0x140001ad0  xor     edi, edi
0x140001ad2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001ad9  nop     dword ptr [rax+rax+00h]
0x140001ade  mov     [rbx+8], al
0x140001ae1  cmp     esi, [rbx+28h]
0x140001ae4  jnb     short loc_140001B05
0x140001ae6  mov     rcx, [rbx+478h]
0x140001aed  mov     eax, esi
0x140001aef  add     rax, rax
0x140001af2  cmp     [rcx+rax*8+8], dil
0x140001af7  jz      short loc_140001B05
0x140001af9  mov     rdi, [rcx+rax*8]
0x140001afd  mov     rcx, rdi; struct _MINIPORT_INTERFACE_CONTEXT *
0x140001b00  call    ?ReferenceSession@@YAXPEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; ReferenceSession(_MINIPORT_INTERFACE_CONTEXT *)
0x140001b05  mov     dl, [rbx+8]; NewIrql
0x140001b08  mov     rcx, rbx; SpinLock
0x140001b0b  call    cs:__imp_KeReleaseSpinLock
0x140001b12  nop     dword ptr [rax+rax+00h]
0x140001b17  mov     rbx, [rsp+28h+arg_0]
0x140001b1c  mov     rax, rdi
0x140001b1f  mov     rsi, [rsp+28h+arg_8]
0x140001b24  add     rsp, 20h
0x140001b28  pop     rdi
0x140001b29  retn
```
