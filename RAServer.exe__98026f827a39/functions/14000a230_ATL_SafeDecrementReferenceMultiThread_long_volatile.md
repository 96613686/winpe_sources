# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x14000a230`
- end: `0x14000a252`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005818`
- `0x140005944`
- `0x140005c6c`
- `0x140009d40`
- `0x140009e50`
- `0x140009ed0`
- `0x140009f50`
- `0x140009fb0`
- `0x140009ff0`

## callees

- `0x14000a230`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(volatile int *a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *a1;
  while ( *a1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange(a1, v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x14000a230  mov     r9d, 7FFFFFFFh
0x14000a236  jmp     short loc_14000A245
0x14000a238  lea     edx, [r8-1]
0x14000a23c  mov     eax, r8d
0x14000a23f  lock cmpxchg [rcx], edx
0x14000a243  jz      short loc_14000A24D
0x14000a245  mov     r8d, [rcx]
0x14000a248  cmp     r8d, r9d
0x14000a24b  jnz     short loc_14000A238
0x14000a24d  lea     eax, [r8-1]
0x14000a251  retn
```
