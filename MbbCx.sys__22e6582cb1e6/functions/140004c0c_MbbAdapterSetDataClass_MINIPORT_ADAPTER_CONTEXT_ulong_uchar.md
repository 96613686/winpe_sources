# MbbAdapterSetDataClass(_MINIPORT_ADAPTER_CONTEXT *,ulong,uchar)

- ea: `0x140004c0c`
- end: `0x140004c6a`
- name: `?MbbAdapterSetDataClass@@YAXPEAU_MINIPORT_ADAPTER_CONTEXT@@KE@Z`
- size: `94`
- prototype: `void __fastcall(PKSPIN_LOCK SpinLock, unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14002be90`
- `0x14002c394`
- `0x14002c9e0`

## callees

- `0x140004c0c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004c4d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c4d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004c23`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004c23`

## pseudocode

```c
void __fastcall MbbAdapterSetDataClass(PKSPIN_LOCK SpinLock, int a2, char a3)
{
  KIRQL v6; // al
  bool v7; // zf

  v6 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v7 = *((_BYTE *)SpinLock + 1080) == 0;
  *((_BYTE *)SpinLock + 8) = v6;
  if ( v7 )
  {
    *((_BYTE *)SpinLock + 1080) = a3;
    *((_DWORD *)SpinLock + 271) = a2;
  }
  KeReleaseSpinLock(SpinLock, v6);
}

```

## disassembly

```asm
0x140004c0c  mov     [rsp+arg_0], rbx
0x140004c11  mov     [rsp+arg_8], rsi
0x140004c16  push    rdi
0x140004c17  sub     rsp, 20h
0x140004c1b  mov     dil, r8b
0x140004c1e  mov     esi, edx
0x140004c20  mov     rbx, rcx
0x140004c23  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004c2a  nop     dword ptr [rax+rax+00h]
0x140004c2f  cmp     byte ptr [rbx+438h], 0
0x140004c36  mov     [rbx+8], al
0x140004c39  jnz     short loc_140004C48
0x140004c3b  mov     [rbx+438h], dil
0x140004c42  mov     [rbx+43Ch], esi
0x140004c48  mov     dl, al; NewIrql
0x140004c4a  mov     rcx, rbx; SpinLock
0x140004c4d  call    cs:__imp_KeReleaseSpinLock
0x140004c54  nop     dword ptr [rax+rax+00h]
0x140004c59  mov     rbx, [rsp+28h+arg_0]
0x140004c5e  mov     rsi, [rsp+28h+arg_8]
0x140004c63  add     rsp, 20h
0x140004c67  pop     rdi
0x140004c68  retn
```
