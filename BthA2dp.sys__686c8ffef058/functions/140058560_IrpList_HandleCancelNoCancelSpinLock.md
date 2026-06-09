# IrpList_HandleCancelNoCancelSpinLock

- ea: `0x140058560`
- end: `0x14005860e`
- name: `IrpList_HandleCancelNoCancelSpinLock`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140058510`

## callees

- `0x140058560`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400585f1`
- `ntoskrnl!IofCompleteRequest` at `0x1400585f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400585b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400585b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005857c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005857c`

## pseudocode

```c
void __fastcall IrpList_HandleCancelNoCancelSpinLock(__int64 a1, __int64 a2, IRP *a3)
{
  KIRQL v6; // al
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rcx
  IRP *Flink; // r8
  struct _LIST_ENTRY *Blink; // rdx
  void (__fastcall *v10)(__int64, IRP *, __int64); // rax

  v6 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a1 + 24));
  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a3->Tail.Overlay.ListEntry;
  Flink = (IRP *)a3->Tail.Overlay.ListEntry.Flink;
  if ( Flink != (IRP *)(&a3->Tail.CompletionKey + 6) )
  {
    if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Flink->MdlAddress != p_ListEntry
      || (Blink = a3->Tail.Overlay.ListEntry.Blink,
          (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
    {
      __fastfail(3u);
    }
    Blink->Flink = (struct _LIST_ENTRY *)Flink;
    Flink->MdlAddress = (PMDL)Blink;
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
0x140058560  mov     [rsp+arg_0], rbx
0x140058565  mov     [rsp+arg_8], rsi
0x14005856a  push    rdi
0x14005856b  sub     rsp, 20h
0x14005856f  mov     rbx, rcx
0x140058572  mov     rdi, r8
0x140058575  mov     rcx, [rcx+18h]; SpinLock
0x140058579  mov     rsi, rdx
0x14005857c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140058583  nop     dword ptr [rax+rax+00h]
0x140058588  lea     rcx, [rdi+0A8h]
0x14005858f  mov     r8, [rcx]
0x140058592  cmp     r8, rcx
0x140058595  jz      short loc_1400585B0
0x140058597  cmp     [r8+8], rcx
0x14005859b  jnz     short loc_1400585DE
0x14005859d  mov     rdx, [rcx+8]
0x1400585a1  cmp     [rdx], rcx
0x1400585a4  jnz     short loc_1400585DE
0x1400585a6  mov     [rdx], r8
0x1400585a9  mov     [r8+8], rdx
0x1400585ad  dec     dword ptr [rbx+20h]
0x1400585b0  mov     rcx, [rbx+18h]; SpinLock
0x1400585b4  mov     dl, al; NewIrql
0x1400585b6  call    cs:__imp_KeReleaseSpinLock
0x1400585bd  nop     dword ptr [rax+rax+00h]
0x1400585c2  mov     rax, [rbx+30h]
0x1400585c6  test    rax, rax
0x1400585c9  jz      short loc_1400585E5
0x1400585cb  mov     r8d, 0C0000120h
0x1400585d1  mov     rdx, rdi
0x1400585d4  mov     rcx, rsi
0x1400585d7  call    _guard_dispatch_icall
0x1400585dc  jmp     short loc_1400585FD
0x1400585de  mov     ecx, 3
0x1400585e3  int     29h; Win8: RtlFailFast(ecx)
0x1400585e5  xor     edx, edx; PriorityBoost
0x1400585e7  mov     dword ptr [rdi+30h], 0C0000120h
0x1400585ee  mov     rcx, rdi; Irp
0x1400585f1  call    cs:__imp_IofCompleteRequest
0x1400585f8  nop     dword ptr [rax+rax+00h]
0x1400585fd  mov     rbx, [rsp+28h+arg_0]
0x140058602  mov     rsi, [rsp+28h+arg_8]
0x140058607  add     rsp, 20h
0x14005860b  pop     rdi
0x14005860c  retn
```
