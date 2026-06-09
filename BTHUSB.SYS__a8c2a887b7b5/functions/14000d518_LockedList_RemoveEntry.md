# LockedList_RemoveEntry

- ea: `0x14000d518`
- end: `0x14000d579`
- name: `LockedList_RemoveEntry`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140018f10`

## callees

- `0x14000d518`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d55c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d55c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d528`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d528`

## pseudocode

```c
_QWORD *__fastcall LockedList_RemoveEntry(__int64 a1, _QWORD *a2)
{
  KIRQL v3; // al
  __int64 v4; // rdx
  _QWORD *v5; // rcx

  v3 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v4 = *a2;
  if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v5 = (_QWORD *)a2[1], (_QWORD *)*v5 != a2) )
    __fastfail(3u);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  --dword_1400132F8;
  KeReleaseSpinLock(SpinLock, v3);
  return a2;
}

```

## disassembly

```asm
0x14000d518  push    rbx
0x14000d51a  sub     rsp, 20h
0x14000d51e  mov     rcx, cs:SpinLock; SpinLock
0x14000d525  mov     rbx, rdx
0x14000d528  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d52f  nop     dword ptr [rax+rax+00h]
0x14000d534  mov     rdx, [rbx]
0x14000d537  cmp     [rdx+8], rbx
0x14000d53b  jnz     short loc_14000D572
0x14000d53d  mov     rcx, [rbx+8]
0x14000d541  cmp     [rcx], rbx
0x14000d544  jnz     short loc_14000D572
0x14000d546  mov     [rcx], rdx
0x14000d549  mov     [rdx+8], rcx
0x14000d54d  mov     dl, al; NewIrql
0x14000d54f  dec     cs:dword_1400132F8
0x14000d555  mov     rcx, cs:SpinLock; SpinLock
0x14000d55c  call    cs:__imp_KeReleaseSpinLock
0x14000d563  nop     dword ptr [rax+rax+00h]
0x14000d568  mov     rax, rbx
0x14000d56b  add     rsp, 20h
0x14000d56f  pop     rbx
0x14000d570  retn
0x14000d572  mov     ecx, 3
0x14000d577  int     29h; Win8: RtlFailFast(ecx)
```
