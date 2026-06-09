# EaDeleteAggregatedEventParameters

- ea: `0x180009070`
- end: `0x180009103`
- name: `EaDeleteAggregatedEventParameters`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001970`
- `0x180009070`
- `0x18000982c`
- `0x180009c94`
- `0x18000aae8`

## pseudocode

```c
__int64 __fastcall EaDeleteAggregatedEventParameters(void *a1, const GUID *a2)
{
  int v2; // ebx
  _QWORD v4[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v5[6]; // [rsp+30h] [rbp-30h] BYREF
  void *v6; // [rsp+80h] [rbp+20h] BYREF

  v6 = 0;
  v4[1] = 0;
  v4[0] = 0;
  v2 = EapOpenAggregatedEventNode(a1, a2, &v6);
  if ( v2 >= 0 )
  {
    v5[0] = v4;
    v5[3] = 0;
    v5[1] = EaDeleteAggregatedEventParametersNextChild;
    v5[2] = EaDeleteAggregatedEventParametersCloseChild;
    v5[4] = EaDeleteAggregatedEventParametersPostVisitNode;
    v2 = EapTreeTraverse(v5, v6);
  }
  EapCloseAggregatedEventNode(v6);
  EapReclaimKeyEnumBuffer(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009070  mov     [rsp-8+arg_0], rbx
0x180009075  push    rbp
0x180009076  mov     rbp, rsp
0x180009079  sub     rsp, 60h
0x18000907d  lea     r8, [rbp+arg_10]
0x180009081  mov     [rbp+arg_10], 0
0x180009089  mov     [rbp+var_38], 0
0x180009091  mov     [rbp+var_40], 0
0x180009099  call    EapOpenAggregatedEventNode
0x18000909e  mov     ebx, eax
0x1800090a0  test    eax, eax
0x1800090a2  js      short loc_1800090E4
0x1800090a4  mov     rdx, [rbp+arg_10]
0x1800090a8  lea     rax, [rbp+var_40]
0x1800090ac  mov     [rbp+var_30], rax
0x1800090b0  lea     rcx, [rbp+var_30]
0x1800090b4  lea     rax, EaDeleteAggregatedEventParametersNextChild
0x1800090bb  mov     [rbp+var_18], 0
0x1800090c3  mov     [rbp+var_28], rax
0x1800090c7  lea     rax, EaDeleteAggregatedEventParametersCloseChild
0x1800090ce  mov     [rbp+var_20], rax
0x1800090d2  lea     rax, EaDeleteAggregatedEventParametersPostVisitNode
0x1800090d9  mov     [rbp+var_10], rax
0x1800090dd  call    EapTreeTraverse
0x1800090e2  mov     ebx, eax
0x1800090e4  mov     rcx, [rbp+arg_10]
0x1800090e8  call    EapCloseAggregatedEventNode
0x1800090ed  lea     rcx, [rbp+var_40]
0x1800090f1  call    EapReclaimKeyEnumBuffer
0x1800090f6  mov     eax, ebx
0x1800090f8  mov     rbx, [rsp+60h+arg_0]
0x1800090fd  add     rsp, 60h
0x180009101  pop     rbp
0x180009102  retn
```
