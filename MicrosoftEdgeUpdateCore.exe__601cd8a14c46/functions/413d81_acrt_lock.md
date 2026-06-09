# ___acrt_lock

- ea: `0x413d81`
- end: `0x413d98`
- name: `___acrt_lock`
- size: `23`
- prototype: `void __cdecl(int)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x41061b`
- `0x410e77`
- `0x410ed2`
- `0x4114b1`
- `0x4136ec`
- `0x41373e`
- `0x4137a9`
- `0x4137fe`
- `0x41439c`
- `0x414814`
- `0x4153b0`
- `0x415511`
- `0x41556d`
- `0x415680`
- `0x4158ff`
- `0x415dda`
- `0x416b01`
- `0x419211`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x413d90`
- `KERNEL32!EnterCriticalSection` at `0x413d90`

## pseudocode

```c
void __cdecl __acrt_lock(int a1)
{
  EnterCriticalSection(&stru_43E328 + a1);
}

```

## disassembly

```asm
0x413d81  mov     edi, edi
0x413d83  push    ebp
0x413d84  mov     ebp, esp
0x413d86  imul    eax, [ebp+arg_0], 18h
0x413d8a  add     eax, offset stru_43E328
0x413d8f  push    eax; lpCriticalSection
0x413d90  call    ds:EnterCriticalSection
0x413d96  pop     ebp
0x413d97  retn
```
