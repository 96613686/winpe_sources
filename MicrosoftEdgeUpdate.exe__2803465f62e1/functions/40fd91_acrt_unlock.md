# ___acrt_unlock

- ea: `0x40fd91`
- end: `0x40fda8`
- name: `___acrt_unlock`
- size: `23`
- prototype: `void __cdecl(int)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x40e238`
- `0x40eab4`
- `0x40ede6`
- `0x40ef40`
- `0x40ef9b`
- `0x40f660`
- `0x40f6b2`
- `0x40f71d`
- `0x40f772`
- `0x41057c`
- `0x4109f4`
- `0x411024`
- `0x411390`
- `0x411ad9`
- `0x4120e3`
- `0x4121f6`
- `0x412475`
- `0x4141ec`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x40fda0`
- `KERNEL32!LeaveCriticalSection` at `0x40fda0`

## pseudocode

```c
void __cdecl __acrt_unlock(int a1)
{
  LeaveCriticalSection(&stru_418028 + a1);
}

```

## disassembly

```asm
0x40fd91  mov     edi, edi
0x40fd93  push    ebp
0x40fd94  mov     ebp, esp
0x40fd96  imul    eax, [ebp+arg_0], 18h
0x40fd9a  add     eax, offset stru_418028
0x40fd9f  push    eax; lpCriticalSection
0x40fda0  call    ds:LeaveCriticalSection
0x40fda6  pop     ebp
0x40fda7  retn
```
