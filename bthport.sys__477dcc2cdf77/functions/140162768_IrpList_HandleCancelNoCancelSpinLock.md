# IrpList_HandleCancelNoCancelSpinLock

- ea: `0x140162768`
- end: `0x140162816`
- name: `IrpList_HandleCancelNoCancelSpinLock`
- size: `174`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14007df50`
- `0x1400dab10`
- `0x1400db790`
- `0x140162718`

## callees

- `0x140162768`
- `0x140165580`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1401627f9`
- `ntoskrnl!IofCompleteRequest` at `0x1401627f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140162784`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140162784`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401627be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401627be`

## pseudocode

```c
void __fastcall IrpList_HandleCancelNoCancelSpinLock(__int64 a1, __int64 a2, IRP *a3)
{
  KIRQL v6; // al
  _LIST_ENTRY *p_ListEntry; // rcx
  IRP *Flink; // r8
  _LIST_ENTRY *Blink; // rdx
  void (__fastcall *v10)(__int64, IRP *, __int64); // rax

  v6 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a1 + 24));
  p_ListEntry = &a3->Tail.Overlay.ListEntry;
  Flink = (IRP *)a3->Tail.Overlay.ListEntry.Flink;
  if ( Flink != (IRP *)(&a3->Tail.CompletionKey + 6) )
  {
    if ( (_LIST_ENTRY *)Flink->MdlAddress != p_ListEntry
      || (Blink = a3->Tail.Overlay.ListEntry.Blink, Blink->Flink != p_ListEntry) )
    {
      __fastfail(3u);
    }
    Blink->Flink = (_LIST_ENTRY *)Flink;
    Flink->MdlAddress = (_MDL *)Blink;
    --*(_DWORD *)(a1 + 32);
  }
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a1 + 24), v6);
  v10 = *(void (__fastcall **)(__int64, IRP *, __int64))(a1 + 48);
  if ( v10 )
  {
    v10(a2, a3, 3221225760LL);
  }
  else
  {
    a3->IoStatus.Status = -1073741536;
    IofCompleteRequest(a3, 0);
  }
}

```

## disassembly

```asm
0x140162768  mov     [rsp+arg_0], rbx
0x14016276d  mov     [rsp+arg_8], rsi
0x140162772  push    rdi
0x140162773  sub     rsp, 20h
0x140162777  mov     rbx, rcx
0x14016277a  mov     rdi, r8
0x14016277d  mov     rcx, [rcx+18h]; SpinLock
0x140162781  mov     rsi, rdx
0x140162784  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14016278b  nop     dword ptr [rax+rax+00h]
0x140162790  lea     rcx, [rdi+0A8h]
0x140162797  mov     r8, [rcx]
0x14016279a  cmp     r8, rcx
0x14016279d  jz      short loc_1401627B8
0x14016279f  cmp     [r8+8], rcx
0x1401627a3  jnz     short loc_1401627E6
0x1401627a5  mov     rdx, [rcx+8]
0x1401627a9  cmp     [rdx], rcx
0x1401627ac  jnz     short loc_1401627E6
0x1401627ae  mov     [rdx], r8
0x1401627b1  mov     [r8+8], rdx
0x1401627b5  dec     dword ptr [rbx+20h]
0x1401627b8  mov     rcx, [rbx+18h]; SpinLock
0x1401627bc  mov     dl, al; NewIrql
0x1401627be  call    cs:__imp_KeReleaseSpinLock
0x1401627c5  nop     dword ptr [rax+rax+00h]
0x1401627ca  mov     rax, [rbx+30h]
0x1401627ce  test    rax, rax
0x1401627d1  jz      short loc_1401627ED
0x1401627d3  mov     r8d, 0C0000120h
0x1401627d9  mov     rdx, rdi
0x1401627dc  mov     rcx, rsi
0x1401627df  call    _guard_dispatch_icall
0x1401627e4  jmp     short loc_140162805
0x1401627e6  mov     ecx, 3
0x1401627eb  int     29h; Win8: RtlFailFast(ecx)
0x1401627ed  xor     edx, edx; PriorityBoost
0x1401627ef  mov     dword ptr [rdi+30h], 0C0000120h
0x1401627f6  mov     rcx, rdi; Irp
0x1401627f9  call    cs:__imp_IofCompleteRequest
0x140162800  nop     dword ptr [rax+rax+00h]
0x140162805  mov     rbx, [rsp+28h+arg_0]
0x14016280a  mov     rsi, [rsp+28h+arg_8]
0x14016280f  add     rsp, 20h
0x140162813  pop     rdi
0x140162814  retn
```
