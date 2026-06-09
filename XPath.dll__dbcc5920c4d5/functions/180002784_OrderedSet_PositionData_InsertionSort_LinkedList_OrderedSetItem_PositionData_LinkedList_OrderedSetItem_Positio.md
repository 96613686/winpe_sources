# OrderedSet<PositionData>::InsertionSort(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)

- ea: `0x180002784`
- end: `0x180002834`
- name: `?InsertionSort@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@0@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000284c`

## callees

- `0x1800023d4`
- `0x180002524`
- `0x180002784`
- `0x180002aac`
- `0x180002ad8`

## pseudocode

```c
__int64 __fastcall OrderedSet<PositionData>::InsertionSort(__int64 a1, __int64 a2)
{
  __int64 *v4; // rbx
  __int64 *v5; // r14
  struct PositionData *v6; // rcx
  int v7; // esi
  __int64 v8; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]
  __int64 v12; // [rsp+40h] [rbp-28h]
  int v13; // [rsp+70h] [rbp+8h] BYREF

  v10[0] = a2;
  v11 = 0;
  v10[1] = a1;
  v12 = 0;
  while ( *(_DWORD *)a1 )
  {
    v4 = *(__int64 **)(a2 + 8);
    v5 = 0;
    while ( v4 )
    {
      v6 = (struct PositionData *)(*(_QWORD *)(a1 + 8) + 16LL);
      v13 = 0;
      v7 = PositionData::Compare(v6, (struct PositionData *)(v4 + 2), &v13);
      if ( v7 < 0 )
        goto LABEL_10;
      if ( v13 < 0 )
        break;
      v5 = v4;
      v4 = (__int64 *)*v4;
    }
    v8 = LinkedList<OrderedSetItem<PositionData>>::PopHead(a1);
    LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(a2, v5, v8);
  }
  v7 = 0;
LABEL_10:
  AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002784  mov     rax, rsp
0x180002787  mov     [rax+10h], rbx
0x18000278b  mov     [rax+18h], rbp
0x18000278f  push    rsi
0x180002790  push    rdi
0x180002791  push    r14
0x180002793  sub     rsp, 50h
0x180002797  xorps   xmm0, xmm0
0x18000279a  mov     [rax-48h], rdx
0x18000279e  movdqu  xmmword ptr [rax-38h], xmm0
0x1800027a3  mov     rbp, rdx
0x1800027a6  mov     [rax-40h], rcx
0x1800027aa  mov     rdi, rcx
0x1800027ad  mov     qword ptr [rax-28h], 0
0x1800027b5  cmp     dword ptr [rdi], 0
0x1800027b8  jz      short loc_180002811
0x1800027ba  mov     rbx, [rbp+8]
0x1800027be  xor     r14d, r14d
0x1800027c1  test    rbx, rbx
0x1800027c4  jz      short loc_1800027F9
0x1800027c6  mov     rcx, [rdi+8]
0x1800027ca  lea     rdx, [rbx+10h]; struct PositionData *
0x1800027ce  add     rcx, 10h; struct PositionData *
0x1800027d2  mov     [rsp+68h+arg_0], 0
0x1800027da  lea     r8, [rsp+68h+arg_0]; int *
0x1800027df  call    ?Compare@PositionData@@SAJAEAV1@0PEAJ@Z; PositionData::Compare(PositionData &,PositionData &,long *)
0x1800027e4  mov     esi, eax
0x1800027e6  test    eax, eax
0x1800027e8  js      short loc_180002813
0x1800027ea  cmp     [rsp+68h+arg_0], 0
0x1800027ef  jl      short loc_1800027F9
0x1800027f1  mov     r14, rbx
0x1800027f4  mov     rbx, [rbx]
0x1800027f7  jmp     short loc_1800027C1
0x1800027f9  mov     rcx, rdi
0x1800027fc  call    ?PopHead@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@XZ; LinkedList<OrderedSetItem<PositionData>>::PopHead(void)
0x180002801  mov     r8, rax
0x180002804  mov     rdx, r14
0x180002807  mov     rcx, rbp
0x18000280a  call    ?PushHeadOrInsertAfter@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@AEAAXPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@0@Z; LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(LinkedListItem<OrderedSetItem<PositionData>> *,LinkedListItem<OrderedSetItem<PositionData>> *)
0x18000280f  jmp     short loc_1800027B5
0x180002811  xor     esi, esi
0x180002813  lea     rcx, [rsp+68h+var_48]
0x180002818  call    ??1?$AutoListMerger@V?$OrderedSetItem@VPositionData@@@@@@QEAA@XZ; AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(void)
0x18000281d  lea     r11, [rsp+68h+var_18]
0x180002822  mov     eax, esi
0x180002824  mov     rbx, [r11+28h]
0x180002828  mov     rbp, [r11+30h]
0x18000282c  mov     rsp, r11
0x18000282f  pop     r14
0x180002831  pop     rdi
0x180002832  pop     rsi
0x180002833  retn
```
