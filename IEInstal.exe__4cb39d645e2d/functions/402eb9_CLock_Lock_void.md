# CLock::Lock(void)

- ea: `0x402eb9`
- end: `0x402ecd`
- name: `?Lock@CLock@@QAEHXZ`
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

- `0x402eb9`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x402ec3`
- `KERNEL32!EnterCriticalSection` at `0x402ec3`

## pseudocode

```c
int __thiscall CLock::Lock(CLock *this)
{
  int result; // eax

  result = 0;
  if ( *(_DWORD *)this )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4));
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x402eb9  xor     eax, eax
0x402ebb  cmp     [ecx], eax
0x402ebd  jz      short locret_402ECC
0x402ebf  lea     eax, [ecx+4]
0x402ec2  push    eax; lpCriticalSection
0x402ec3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x402ec9  xor     eax, eax
0x402ecb  inc     eax
0x402ecc  retn
```
