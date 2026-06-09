# OrderedSet<PositionData>::CombineSortedList(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)

- ea: `0x180002464`
- end: `0x18000251b`
- name: `?CombineSortedList@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@00@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000284c`

## callees

- `0x1800023d4`
- `0x180002464`
- `0x180002524`
- `0x180002aac`
- `0x180002ad8`

## pseudocode

```c
__int64 __fastcall OrderedSet<PositionData>::CombineSortedList(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  struct PositionData *v7; // rdx
  struct PositionData *v8; // rcx
  int v9; // ebp
  __int64 v10; // rax
  _QWORD v12[3]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+38h] [rbp-40h]
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v12[0] = a3;
  v13 = 0;
  v12[1] = a1;
  v12[2] = a2;
  while ( !*(_DWORD *)a1 )
  {
    if ( !*(_DWORD *)a2 )
    {
      AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(v12);
      return 0;
    }
    v6 = a2;
LABEL_11:
    v10 = LinkedList<OrderedSetItem<PositionData>>::PopHead(v6);
    LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(a3, *(_QWORD *)(a3 + 16), v10);
  }
  if ( !*(_DWORD *)a2 )
  {
    v6 = a1;
    goto LABEL_11;
  }
  v7 = (struct PositionData *)(*(_QWORD *)(a2 + 8) + 16LL);
  v8 = (struct PositionData *)(*(_QWORD *)(a1 + 8) + 16LL);
  v14 = 9;
  v9 = PositionData::Compare(v8, v7, &v14);
  if ( v9 >= 0 )
  {
    v6 = a2;
    if ( v14 <= 0 )
      v6 = a1;
    goto LABEL_11;
  }
  AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002464  mov     rax, rsp
0x180002467  push    rbx
0x180002468  push    rbp
0x180002469  push    rsi
0x18000246a  push    rdi
0x18000246b  sub     rsp, 58h
0x18000246f  xorps   xmm0, xmm0
0x180002472  mov     [rax-58h], r8
0x180002476  movdqu  xmmword ptr [rax-40h], xmm0
0x18000247b  mov     rdi, r8
0x18000247e  mov     [rax-50h], rcx
0x180002482  mov     rbx, rdx
0x180002485  mov     [rax-48h], rdx
0x180002489  mov     rsi, rcx
0x18000248c  cmp     dword ptr [rsi], 0
0x18000248f  jnz     short loc_18000249B
0x180002491  cmp     dword ptr [rbx], 0
0x180002494  jz      short loc_1800024F8
0x180002496  mov     rcx, rbx
0x180002499  jmp     short loc_1800024E2
0x18000249b  cmp     dword ptr [rbx], 0
0x18000249e  jz      short loc_1800024DF
0x1800024a0  mov     rdx, [rbx+8]
0x1800024a4  lea     r8, [rsp+78h+arg_0]; int *
0x1800024ac  mov     rcx, [rsi+8]
0x1800024b0  add     rdx, 10h; struct PositionData *
0x1800024b4  add     rcx, 10h; struct PositionData *
0x1800024b8  mov     [rsp+78h+arg_0], 9
0x1800024c3  call    ?Compare@PositionData@@SAJAEAV1@0PEAJ@Z; PositionData::Compare(PositionData &,PositionData &,long *)
0x1800024c8  mov     ebp, eax
0x1800024ca  test    eax, eax
0x1800024cc  js      short loc_180002506
0x1800024ce  cmp     [rsp+78h+arg_0], 0
0x1800024d6  mov     rcx, rbx
0x1800024d9  cmovle  rcx, rsi
0x1800024dd  jmp     short loc_1800024E2
0x1800024df  mov     rcx, rsi
0x1800024e2  call    ?PopHead@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@XZ; LinkedList<OrderedSetItem<PositionData>>::PopHead(void)
0x1800024e7  mov     rdx, [rdi+10h]
0x1800024eb  mov     r8, rax
0x1800024ee  mov     rcx, rdi
0x1800024f1  call    ?PushHeadOrInsertAfter@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@AEAAXPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@0@Z; LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(LinkedListItem<OrderedSetItem<PositionData>> *,LinkedListItem<OrderedSetItem<PositionData>> *)
0x1800024f6  jmp     short loc_18000248C
0x1800024f8  lea     rcx, [rsp+78h+var_58]
0x1800024fd  call    ??1?$AutoListMerger@V?$OrderedSetItem@VPositionData@@@@@@QEAA@XZ; AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(void)
0x180002502  xor     eax, eax
0x180002504  jmp     short loc_180002512
0x180002506  lea     rcx, [rsp+78h+var_58]
0x18000250b  call    ??1?$AutoListMerger@V?$OrderedSetItem@VPositionData@@@@@@QEAA@XZ; AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(void)
0x180002510  mov     eax, ebp
0x180002512  add     rsp, 58h
0x180002516  pop     rdi
0x180002517  pop     rsi
0x180002518  pop     rbp
0x180002519  pop     rbx
0x18000251a  retn
```
