# ___acrt_unlock

- ea: `0x410261`
- end: `0x410278`
- name: `___acrt_unlock`
- size: `23`
- prototype: `void __cdecl(int)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x40b89d`
- `0x40bbcf`
- `0x40bd35`
- `0x40bd90`
- `0x40e4d2`
- `0x40e524`
- `0x40e58f`
- `0x40e5e4`
- `0x40f765`
- `0x40fbdd`
- `0x410359`
- `0x4106c0`
- `0x411105`
- `0x41178f`
- `0x4117eb`
- `0x4118fe`
- `0x411b7d`
- `0x41484c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x410270`
- `KERNEL32!LeaveCriticalSection` at `0x410270`

## pseudocode

```c
void __cdecl __acrt_unlock(int a1)
{
  LeaveCriticalSection(&stru_426EC0 + a1);
}

```

## disassembly

```asm
0x410261  mov     edi, edi
0x410263  push    ebp
0x410264  mov     ebp, esp
0x410266  imul    eax, [ebp+arg_0], 18h
0x41026a  add     eax, offset stru_426EC0
0x41026f  push    eax; lpCriticalSection
0x410270  call    ds:LeaveCriticalSection
0x410276  pop     ebp
0x410277  retn
```
