# Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)

- ea: `0x180004320`
- end: `0x180004344`
- name: `?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z`
- size: `36`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003460`
- `0x1800051d0`
- `0x180005820`

## callees

- `0x180004320`

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
0x180004320  mov     eax, [rcx]
0x180004322  cmp     eax, 7FFFFFFFh
0x180004327  jz      short loc_18000433B
0x180004329  lea     edx, [rax+1]
0x18000432c  lock cmpxchg [rcx], edx
0x180004330  jz      short loc_180004341
0x180004332  mov     eax, [rcx]
0x180004334  cmp     eax, 7FFFFFFFh
0x180004339  jnz     short loc_180004329
0x18000433b  mov     eax, 7FFFFFFFh
0x180004340  retn
0x180004341  mov     eax, edx
0x180004343  retn
```
