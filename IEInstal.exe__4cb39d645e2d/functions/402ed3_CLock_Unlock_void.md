# CLock::Unlock(void)

- ea: `0x402ed3`
- end: `0x402ee7`
- name: `?Unlock@CLock@@QAEHXZ`
- size: `20`
- prototype: `int __thiscall(CLock *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x4035e8`
- `0x40373b`
- `0x403d84`
- `0x403ffd`
- `0x404214`
- `0x4044ae`
- `0x40494e`
- `0x404a9b`
- `0x404c02`
- `0x405304`
- `0x405628`
- `0x40576c`
- `0x405849`
- `0x4058f8`
- `0x405966`

## callees

- `0x402ed3`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x402edd`
- `KERNEL32!LeaveCriticalSection` at `0x402edd`

## pseudocode

```c
int __thiscall CLock::Unlock(CLock *this)
{
  int result; // eax

  result = 0;
  if ( *(_DWORD *)this )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4));
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x402ed3  xor     eax, eax
0x402ed5  cmp     [ecx], eax
0x402ed7  jz      short locret_402EE6
0x402ed9  lea     eax, [ecx+4]
0x402edc  push    eax; lpCriticalSection
0x402edd  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x402ee3  xor     eax, eax
0x402ee5  inc     eax
0x402ee6  retn
```
