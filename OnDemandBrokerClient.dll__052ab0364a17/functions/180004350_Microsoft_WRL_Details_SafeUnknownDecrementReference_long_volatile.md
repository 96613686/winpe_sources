# Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)

- ea: `0x180004350`
- end: `0x180004375`
- name: `?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `37`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, volatile int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002710`
- `0x180006010`

## callees

- `0x180004350`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::SafeUnknownDecrementReference(
        Microsoft::WRL::Details *this,
        volatile int *a2)
{
  signed __int32 i; // edx

  for ( i = *(_DWORD *)this; *(_DWORD *)this != 0x7FFFFFFF; i = *(_DWORD *)this )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)this, i - 1, i) )
      break;
  }
  return (unsigned int)(i - 1);
}

```

## disassembly

```asm
0x180004350  mov     edx, [rcx]
0x180004352  cmp     edx, 7FFFFFFFh
0x180004358  jz      short loc_180004371
0x18000435a  lea     r8d, [rdx-1]
0x18000435e  mov     eax, edx
0x180004360  lock cmpxchg [rcx], r8d
0x180004365  jz      short loc_180004371
0x180004367  mov     edx, [rcx]
0x180004369  cmp     edx, 7FFFFFFFh
0x18000436f  jnz     short loc_18000435A
0x180004371  lea     eax, [rdx-1]
0x180004374  retn
```
