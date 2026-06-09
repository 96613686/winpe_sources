# EapDeleteAggregatedEventCondition

- ea: `0x1800088d0`
- end: `0x180008931`
- name: `EapDeleteAggregatedEventCondition`
- size: `97`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002000`
- `0x1800085c4`

## callees

- `0x180001970`
- `0x1800088d0`

## pseudocode

```c
__int64 __fastcall EapDeleteAggregatedEventCondition(__int64 a1, int a2)
{
  __int64 result; // rax
  _QWORD v3[7]; // [rsp+20h] [rbp-38h] BYREF
  int v4; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  if ( !a1 )
    return 3221225485LL;
  v3[2] = 0;
  v3[0] = &v4;
  v3[3] = 0;
  v3[1] = EaiAggregationConditionNextChild;
  v3[4] = EapDeleteAggregatedEventConditionVisitNode;
  result = EapTreeTraverse(v3, a1);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp+arg_8], edx
0x1800088d4  sub     rsp, 58h
0x1800088d8  test    rcx, rcx
0x1800088db  jnz     short loc_1800088E4
0x1800088dd  mov     eax, 0C000000Dh
0x1800088e2  jmp     short loc_18000892C
0x1800088e4  lea     rax, [rsp+58h+arg_8]
0x1800088e9  mov     [rsp+58h+var_28], 0
0x1800088f2  mov     [rsp+58h+var_38], rax
0x1800088f7  mov     rdx, rcx
0x1800088fa  lea     rax, EaiAggregationConditionNextChild
0x180008901  mov     [rsp+58h+var_20], 0
0x18000890a  mov     [rsp+58h+var_30], rax
0x18000890f  lea     rcx, [rsp+58h+var_38]
0x180008914  lea     rax, EapDeleteAggregatedEventConditionVisitNode
0x18000891b  mov     [rsp+58h+var_18], rax
0x180008920  call    EapTreeTraverse
0x180008925  xor     ecx, ecx
0x180008927  test    eax, eax
0x180008929  cmovns  eax, ecx
0x18000892c  add     rsp, 58h
0x180008930  retn
```
