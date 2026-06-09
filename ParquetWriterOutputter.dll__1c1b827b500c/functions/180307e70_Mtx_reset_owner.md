# _Mtx_reset_owner

- ea: `0x180307e70`
- end: `0x180307e8b`
- name: `_Mtx_reset_owner`
- size: `27`
- prototype: `void __cdecl(_Mtx_t)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180309eac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180307e79`
- `KERNEL32!GetCurrentThreadId` at `0x180307e79`

## pseudocode

```c
void __cdecl Mtx_reset_owner(_Mtx_t a1)
{
  DWORD CurrentThreadId; // eax

  CurrentThreadId = GetCurrentThreadId();
  ++*((_DWORD *)a1 + 19);
  *((_DWORD *)a1 + 18) = CurrentThreadId;
}

```

## disassembly

```asm
0x180307e70  push    rbx
0x180307e72  sub     rsp, 20h
0x180307e76  mov     rbx, rcx
0x180307e79  call    cs:__imp_GetCurrentThreadId
0x180307e7f  inc     dword ptr [rbx+4Ch]
0x180307e82  mov     [rbx+48h], eax
0x180307e85  add     rsp, 20h
0x180307e89  pop     rbx
0x180307e8a  retn
```
