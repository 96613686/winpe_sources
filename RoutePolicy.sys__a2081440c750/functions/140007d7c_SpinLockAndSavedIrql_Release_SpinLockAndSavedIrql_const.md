# SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)

- ea: `0x140007d7c`
- end: `0x140007d98`
- name: `?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z`
- size: `28`
- prototype: `void __fastcall(const struct SpinLockAndSavedIrql *)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018cc`
- `0x140001bfc`
- `0x140001d94`
- `0x140001fc0`
- `0x14000225c`
- `0x140002618`
- `0x14000294c`
- `0x1400029f4`
- `0x140002abc`
- `0x140002d00`
- `0x140003340`
- `0x1400037a4`
- `0x140003f18`
- `0x140004330`
- `0x140004800`
- `0x140004a84`
- `0x140005b60`
- `0x14000607c`
- `0x14000664c`
- `0x140007110`
- `0x140007280`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007d86`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d86`

## pseudocode

```c
void __fastcall SpinLockAndSavedIrql::Release(const struct SpinLockAndSavedIrql *a1)
{
  KeReleaseSpinLock(*(PKSPIN_LOCK *)a1, *((_BYTE *)a1 + 8));
}

```

## disassembly

```asm
0x140007d7c  sub     rsp, 28h
0x140007d80  mov     dl, [rcx+8]; NewIrql
0x140007d83  mov     rcx, [rcx]; SpinLock
0x140007d86  call    cs:__imp_KeReleaseSpinLock
0x140007d8d  nop     dword ptr [rax+rax+00h]
0x140007d92  add     rsp, 28h
0x140007d96  retn
```
