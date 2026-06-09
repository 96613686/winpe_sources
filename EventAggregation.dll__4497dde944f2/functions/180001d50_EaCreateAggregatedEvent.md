# EaCreateAggregatedEvent

- ea: `0x180001d50`
- end: `0x180001df0`
- name: `EaCreateAggregatedEvent`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, __int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001d50`
- `0x180001e00`
- `0x180002000`
- `0x180002ae0`

## pseudocode

```c
__int64 __fastcall EaCreateAggregatedEvent(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  int AggregatedEvent; // eax
  PVOID v12; // rdi
  unsigned int v13; // ebx
  __int64 result; // rax
  PVOID P[7]; // [rsp+40h] [rbp-38h] BYREF

  P[0] = 0;
  AggregatedEvent = EapCreateAggregatedEvent(a1, a2, P);
  v12 = P[0];
  v13 = AggregatedEvent;
  if ( AggregatedEvent < 0
    || (result = EaiCreateAggregation(P[0], a3, a4, a5, a6, a7, a8, a9), v13 = result, (int)result < 0) )
  {
    if ( v12 )
      EapDeleteAggregatedEvent(v12);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180001d50  push    rbx
0x180001d52  push    rbp
0x180001d53  push    rsi
0x180001d54  push    rdi
0x180001d55  push    r14
0x180001d57  sub     rsp, 50h
0x180001d5b  mov     r14, r8
0x180001d5e  mov     [rsp+78h+P], 0
0x180001d67  lea     r8, [rsp+78h+P]
0x180001d6c  mov     rbp, r9
0x180001d6f  mov     esi, edx
0x180001d71  call    EapCreateAggregatedEvent
0x180001d76  mov     rdi, [rsp+78h+P]
0x180001d7b  mov     ebx, eax
0x180001d7d  test    eax, eax
0x180001d7f  js      short loc_180001DCF
0x180001d81  mov     rax, [rsp+78h+arg_40]
0x180001d89  mov     r8, rbp
0x180001d8c  mov     r9, [rsp+78h+arg_20]
0x180001d94  mov     rdx, r14
0x180001d97  mov     [rsp+78h+var_40], rax
0x180001d9c  mov     rcx, rdi
0x180001d9f  mov     eax, [rsp+78h+arg_38]
0x180001da6  mov     [rsp+78h+var_48], eax
0x180001daa  mov     rax, [rsp+78h+arg_30]
0x180001db2  mov     [rsp+78h+var_50], rax
0x180001db7  mov     rax, [rsp+78h+arg_28]
0x180001dbf  mov     [rsp+78h+var_58], rax
0x180001dc4  call    EaiCreateAggregation
0x180001dc9  mov     ebx, eax
0x180001dcb  test    eax, eax
0x180001dcd  jns     short loc_180001DD6
0x180001dcf  test    rdi, rdi
0x180001dd2  jnz     short loc_180001DE1
0x180001dd4  mov     eax, ebx
0x180001dd6  add     rsp, 50h
0x180001dda  pop     r14
0x180001ddc  pop     rdi
0x180001ddd  pop     rsi
0x180001dde  pop     rbp
0x180001ddf  pop     rbx
0x180001de0  retn
0x180001de1  and     esi, 1
0x180001de4  mov     rcx, rdi; P
0x180001de7  mov     edx, esi
0x180001de9  call    EapDeleteAggregatedEvent
0x180001dee  jmp     short loc_180001DD4
```
