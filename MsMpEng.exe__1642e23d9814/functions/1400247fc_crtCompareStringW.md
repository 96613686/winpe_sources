# __crtCompareStringW

- ea: `0x1400247fc`
- end: `0x1400248b9`
- name: `__crtCompareStringW`
- size: `189`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140022f30`

## callees

- `0x140015210`
- `0x14001cf84`
- `0x1400247fc`

## pseudocode

```c
__int64 __fastcall _crtCompareStringW(__int64 a1, unsigned int a2, __int64 a3, int a4, __int64 a5, int a6)
{
  unsigned int v6; // ebx
  int v10; // eax
  __int64 result; // rax
  int v12; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = sub_140015210(a3, a4);
  v10 = a6;
  if ( a6 > 0 )
    v10 = sub_140015210(a5, a6);
  if ( v6 && v10 )
    return sub_14001CF84(a1, a2, a3, v6, a5, v10, 0, 0, 0);
  v12 = v6 - v10;
  result = ((v12 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v12 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x1400247fc  mov     rax, rsp
0x1400247ff  mov     [rax+8], rbx
0x140024803  mov     [rax+10h], rbp
0x140024807  mov     [rax+18h], rsi
0x14002480b  mov     [rax+20h], rdi
0x14002480f  push    r14
0x140024811  sub     rsp, 50h
0x140024815  movsxd  rbx, r9d
0x140024818  mov     rsi, r8
0x14002481b  mov     ebp, edx
0x14002481d  mov     r14, rcx
0x140024820  test    r9d, r9d
0x140024823  jle     short loc_140024833
0x140024825  mov     rdx, rbx
0x140024828  mov     rcx, r8
0x14002482b  call    sub_140015210
0x140024830  mov     rbx, rax
0x140024833  movsxd  rax, [rsp+58h+arg_28]
0x14002483b  mov     rdi, [rsp+58h+arg_20]
0x140024843  test    eax, eax
0x140024845  jle     short loc_140024852
0x140024847  mov     rdx, rax
0x14002484a  mov     rcx, rdi
0x14002484d  call    sub_140015210
0x140024852  test    ebx, ebx
0x140024854  jz      short loc_140024887
0x140024856  test    eax, eax
0x140024858  jz      short loc_140024887
0x14002485a  and     [rsp+58h+var_18], 0
0x140024860  mov     r9d, ebx
0x140024863  and     [rsp+58h+var_20], 0
0x140024869  mov     r8, rsi
0x14002486c  and     [rsp+58h+var_28], 0
0x140024872  mov     edx, ebp
0x140024874  mov     [rsp+58h+var_30], eax
0x140024878  mov     rcx, r14
0x14002487b  mov     [rsp+58h+var_38], rdi
0x140024880  call    sub_14001CF84
0x140024885  jmp     short loc_14002489E
0x140024887  sub     ebx, eax
0x140024889  mov     ecx, 2
0x14002488e  mov     eax, ebx
0x140024890  sar     eax, 1Fh
0x140024893  and     eax, 0FFFFFFFEh
0x140024896  add     eax, 3
0x140024899  test    ebx, ebx
0x14002489b  cmovz   eax, ecx
0x14002489e  mov     rbx, [rsp+58h+arg_0]
0x1400248a3  mov     rbp, [rsp+58h+arg_8]
0x1400248a8  mov     rsi, [rsp+58h+arg_10]
0x1400248ad  mov     rdi, [rsp+58h+arg_18]
0x1400248b2  add     rsp, 50h
0x1400248b6  pop     r14
0x1400248b8  retn
```
