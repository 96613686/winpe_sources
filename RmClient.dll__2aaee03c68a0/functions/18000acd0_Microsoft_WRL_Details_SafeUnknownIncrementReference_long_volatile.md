# Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)

- ea: `0x18000acd0`
- end: `0x18000acf4`
- name: `?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `36`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, volatile int *)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a4b4`
- `0x18000a7ec`
- `0x18000a810`
- `0x18000ac20`
- `0x18000ac30`
- `0x18000ac80`
- `0x180010520`
- `0x1800133b0`
- `0x180018160`
- `0x1800185d0`
- `0x180018670`
- `0x180018710`

## callees

- `0x18000acd0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::SafeUnknownIncrementReference(
        Microsoft::WRL::Details *this,
        volatile int *a2)
{
  signed __int32 v2; // eax

  v2 = *(_DWORD *)this;
  if ( *(_DWORD *)this == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, v2 + 1, v2) )
  {
    v2 = *(_DWORD *)this;
    if ( *(_DWORD *)this == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x18000acd0  mov     eax, [rcx]
0x18000acd2  cmp     eax, 7FFFFFFFh
0x18000acd7  jz      short loc_18000ACEE
0x18000acd9  lea     edx, [rax+1]
0x18000acdc  lock cmpxchg [rcx], edx
0x18000ace0  jnz     short loc_18000ACE5
0x18000ace2  mov     eax, edx
0x18000ace4  retn
0x18000ace5  mov     eax, [rcx]
0x18000ace7  cmp     eax, 7FFFFFFFh
0x18000acec  jnz     short loc_18000ACD9
0x18000acee  mov     eax, 7FFFFFFFh
0x18000acf3  retn
```
