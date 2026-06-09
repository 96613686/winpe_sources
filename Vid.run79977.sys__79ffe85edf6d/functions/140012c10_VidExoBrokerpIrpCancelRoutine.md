# VidExoBrokerpIrpCancelRoutine

- ea: `0x140012c10`
- end: `0x140012cb1`
- name: `VidExoBrokerpIrpCancelRoutine`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012c10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140012c8d`
- `ntoskrnl!IofCompleteRequest` at `0x140012c8d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012c28`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012c28`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012c3f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012c3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c75`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c75`

## pseudocode

```c
void __fastcall VidExoBrokerpIrpCancelRoutine(__int64 a1, IRP *a2)
{
  KIRQL CancelIrql; // si
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v5; // r9
  struct _LIST_ENTRY *Blink; // r8

  CancelIrql = a2->CancelIrql;
  IoReleaseCancelSpinLock(2u);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&Flink[754]);
  v5 = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)v5->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = v5;
  v5->Blink = Blink;
  KeReleaseSpinLock((PKSPIN_LOCK)&Flink[754], CancelIrql);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x140012c10  mov     [rsp+arg_0], rbx
0x140012c15  mov     [rsp+arg_8], rsi
0x140012c1a  push    rdi
0x140012c1b  sub     rsp, 20h
0x140012c1f  mov     sil, [rdx+45h]
0x140012c23  mov     cl, 2; Irql
0x140012c25  mov     rbx, rdx
0x140012c28  call    cs:__imp_IoReleaseCancelSpinLock
0x140012c2f  nop     dword ptr [rax+rax+00h]
0x140012c34  mov     rdi, [rbx+78h]
0x140012c38  lea     rcx, [rdi+2F20h]; SpinLock
0x140012c3f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012c46  nop     dword ptr [rax+rax+00h]
0x140012c4b  lea     rax, [rbx+0A8h]
0x140012c52  mov     r9, [rax]
0x140012c55  cmp     [r9+8], rax
0x140012c59  jnz     short loc_140012CAA
0x140012c5b  mov     r8, [rax+8]
0x140012c5f  cmp     [r8], rax
0x140012c62  jnz     short loc_140012CAA
0x140012c64  mov     [r8], r9
0x140012c67  lea     rcx, [rdi+2F20h]; SpinLock
0x140012c6e  mov     dl, sil; NewIrql
0x140012c71  mov     [r9+8], r8
0x140012c75  call    cs:__imp_KeReleaseSpinLock
0x140012c7c  nop     dword ptr [rax+rax+00h]
0x140012c81  xor     edx, edx; PriorityBoost
0x140012c83  mov     dword ptr [rbx+30h], 0C0000120h
0x140012c8a  mov     rcx, rbx; Irp
0x140012c8d  call    cs:__imp_IofCompleteRequest
0x140012c94  nop     dword ptr [rax+rax+00h]
0x140012c99  mov     rbx, [rsp+28h+arg_0]
0x140012c9e  mov     rsi, [rsp+28h+arg_8]
0x140012ca3  add     rsp, 20h
0x140012ca7  pop     rdi
0x140012ca8  retn
0x140012caa  mov     ecx, 3
0x140012caf  int     29h; Win8: RtlFailFast(ecx)
```
