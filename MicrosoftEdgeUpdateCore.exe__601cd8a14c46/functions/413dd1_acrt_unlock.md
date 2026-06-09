# ___acrt_unlock

- ea: `0x413dd1`
- end: `0x413de8`
- name: `___acrt_unlock`
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

- `KERNEL32!LeaveCriticalSection` at `0x413de0`
- `KERNEL32!LeaveCriticalSection` at `0x413de0`

## pseudocode

```c
void __cdecl __acrt_unlock(int a1)
{
  LeaveCriticalSection(&stru_43E328 + a1);
}

```

## disassembly

```asm
0x413dd1  mov     edi, edi
0x413dd3  push    ebp
0x413dd4  mov     ebp, esp
0x413dd6  imul    eax, [ebp+arg_0], 18h
0x413dda  add     eax, offset stru_43E328
0x413ddf  push    eax; lpCriticalSection
0x413de0  call    ds:LeaveCriticalSection
0x413de6  pop     ebp
0x413de7  retn
```
