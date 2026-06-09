# OrderedSet<PositionData>::MergeSortListRecursive(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)

- ea: `0x18000284c`
- end: `0x1800029a3`
- name: `?MergeSortListRecursive@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@0@Z`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000284c`
- `0x180002e08`

## callees

- `0x1800023d4`
- `0x180002464`
- `0x180002784`
- `0x18000284c`
- `0x1800029ac`
- `0x180002c10`

## pseudocode

```c
__int64 __fastcall OrderedSet<PositionData>::MergeSortListRecursive(unsigned int *a1, __int64 a2)
{
  __int64 v4; // rdx
  int v6; // esi
  int v7; // ebx
  int v8; // [rsp+20h] [rbp-39h] BYREF
  __int128 v9; // [rsp+28h] [rbp-31h]
  int v10; // [rsp+38h] [rbp-21h] BYREF
  __int128 v11; // [rsp+40h] [rbp-19h]
  int v12; // [rsp+50h] [rbp-9h] BYREF
  __int128 v13; // [rsp+58h] [rbp-1h]
  _QWORD v14[9]; // [rsp+68h] [rbp+Fh] BYREF

  v4 = *a1;
  if ( (_DWORD)v4 )
  {
    if ( (_DWORD)v4 == 1 )
    {
      LinkedList<OrderedSetItem<PositionData>>::MoveFirstSpecifiedItemsToOtherList(a1, v4, a2);
    }
    else
    {
      if ( (unsigned int)v4 < 0xA )
        return OrderedSet<PositionData>::InsertionSort(a1, a2);
      v14[1] = &v12;
      v12 = 0;
      v14[2] = &v10;
      v10 = 0;
      v14[4] = &v8;
      v13 = 0;
      v8 = 0;
      v11 = 0;
      v14[0] = a2;
      v9 = 0;
      v14[3] = a1;
      LinkedList<OrderedSetItem<PositionData>>::MoveFirstSpecifiedItemsToOtherList(a1, (unsigned int)v4 >> 1, &v12);
      v6 = OrderedSet<PositionData>::MergeSortListRecursive(&v12, &v10);
      if ( v6 < 0 )
      {
        AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(v14);
        LinkedList<OrderedSetItem<PositionData>>::Reset(&v8);
        LinkedList<OrderedSetItem<PositionData>>::Reset(&v10);
        LinkedList<OrderedSetItem<PositionData>>::Reset(&v12);
        return (unsigned int)v6;
      }
      v7 = OrderedSet<PositionData>::MergeSortListRecursive(a1, &v8);
      if ( v7 < 0 || (v7 = OrderedSet<PositionData>::CombineSortedList(&v10, &v8, a2), v7 < 0) )
      {
        AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(v14);
        LinkedList<OrderedSetItem<PositionData>>::Reset(&v8);
        LinkedList<OrderedSetItem<PositionData>>::Reset(&v10);
        LinkedList<OrderedSetItem<PositionData>>::Reset(&v12);
        return (unsigned int)v7;
      }
      AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(v14);
      LinkedList<OrderedSetItem<PositionData>>::Reset(&v8);
      LinkedList<OrderedSetItem<PositionData>>::Reset(&v10);
      LinkedList<OrderedSetItem<PositionData>>::Reset(&v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000284c  push    rbp
0x18000284e  push    rbx
0x18000284f  push    rsi
0x180002850  push    rdi
0x180002851  lea     rbp, [rsp-3Fh]
0x180002856  sub     rsp, 98h
0x18000285d  mov     rdi, rdx
0x180002860  mov     rbx, rcx
0x180002863  mov     edx, [rcx]
0x180002865  test    edx, edx
0x180002867  jz      loc_180002995
0x18000286d  cmp     edx, 1
0x180002870  jnz     short loc_18000287F
0x180002872  mov     r8, rdi
0x180002875  call    ?MoveFirstSpecifiedItemsToOtherList@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXKPEAV1@@Z; LinkedList<OrderedSetItem<PositionData>>::MoveFirstSpecifiedItemsToOtherList(ulong,LinkedList<OrderedSetItem<PositionData>> *)
0x18000287a  jmp     loc_180002995
0x18000287f  cmp     edx, 0Ah
0x180002882  jnb     short loc_180002891
0x180002884  mov     rdx, rdi
0x180002887  call    ?InsertionSort@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@0@Z; OrderedSet<PositionData>::InsertionSort(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)
0x18000288c  jmp     loc_180002997
0x180002891  lea     rax, [rbp+57h+var_60]
0x180002895  shr     edx, 1
0x180002897  mov     [rbp+57h+var_40], rax
0x18000289b  lea     r8, [rbp+57h+var_60]
0x18000289f  lea     rax, [rbp+57h+var_78]
0x1800028a3  mov     [rbp+57h+var_60], 0
0x1800028aa  mov     [rbp+57h+var_38], rax
0x1800028ae  xorps   xmm0, xmm0
0x1800028b1  lea     rax, [rbp+57h+var_90]
0x1800028b5  mov     [rbp+57h+var_78], 0
0x1800028bc  xorps   xmm1, xmm1
0x1800028bf  mov     [rbp+57h+var_28], rax
0x1800028c3  movdqu  [rbp+57h+var_58], xmm0
0x1800028c8  mov     [rbp+57h+var_90], 0
0x1800028cf  movdqu  [rbp+57h+var_70], xmm1
0x1800028d4  mov     [rbp+57h+var_48], rdi
0x1800028d8  movdqu  [rbp+57h+var_88], xmm0
0x1800028dd  mov     [rbp+57h+var_30], rbx
0x1800028e1  call    ?MoveFirstSpecifiedItemsToOtherList@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXKPEAV1@@Z; LinkedList<OrderedSetItem<PositionData>>::MoveFirstSpecifiedItemsToOtherList(ulong,LinkedList<OrderedSetItem<PositionData>> *)
0x1800028e6  lea     rdx, [rbp+57h+var_78]
0x1800028ea  lea     rcx, [rbp+57h+var_60]
0x1800028ee  call    ?MergeSortListRecursive@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@0@Z; OrderedSet<PositionData>::MergeSortListRecursive(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)
0x1800028f3  mov     esi, eax
0x1800028f5  test    eax, eax
0x1800028f7  jns     short loc_180002921
0x1800028f9  lea     rcx, [rbp+57h+var_48]
0x1800028fd  call    ??1?$AutoListMerger@V?$OrderedSetItem@VPositionData@@@@@@QEAA@XZ; AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(void)
0x180002902  lea     rcx, [rbp+57h+var_90]
0x180002906  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x18000290b  lea     rcx, [rbp+57h+var_78]
0x18000290f  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x180002914  lea     rcx, [rbp+57h+var_60]
0x180002918  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x18000291d  mov     eax, esi
0x18000291f  jmp     short loc_180002997
0x180002921  lea     rdx, [rbp+57h+var_90]
0x180002925  mov     rcx, rbx
0x180002928  call    ?MergeSortListRecursive@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@0@Z; OrderedSet<PositionData>::MergeSortListRecursive(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)
0x18000292d  mov     ebx, eax
0x18000292f  test    eax, eax
0x180002931  jns     short loc_18000295B
0x180002933  lea     rcx, [rbp+57h+var_48]
0x180002937  call    ??1?$AutoListMerger@V?$OrderedSetItem@VPositionData@@@@@@QEAA@XZ; AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(void)
0x18000293c  lea     rcx, [rbp+57h+var_90]
0x180002940  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x180002945  lea     rcx, [rbp+57h+var_78]
0x180002949  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x18000294e  lea     rcx, [rbp+57h+var_60]
0x180002952  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x180002957  mov     eax, ebx
0x180002959  jmp     short loc_180002997
0x18000295b  mov     r8, rdi
0x18000295e  lea     rdx, [rbp+57h+var_90]
0x180002962  lea     rcx, [rbp+57h+var_78]
0x180002966  call    ?CombineSortedList@?$OrderedSet@VPositionData@@@@CAJPEAV?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@00@Z; OrderedSet<PositionData>::CombineSortedList(LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *,LinkedList<OrderedSetItem<PositionData>> *)
0x18000296b  lea     rcx, [rbp+57h+var_48]
0x18000296f  mov     ebx, eax
0x180002971  test    eax, eax
0x180002973  js      short loc_180002937
0x180002975  call    ??1?$AutoListMerger@V?$OrderedSetItem@VPositionData@@@@@@QEAA@XZ; AutoListMerger<OrderedSetItem<PositionData>>::~AutoListMerger<OrderedSetItem<PositionData>>(void)
0x18000297a  lea     rcx, [rbp+57h+var_90]
0x18000297e  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x180002983  lea     rcx, [rbp+57h+var_78]
0x180002987  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x18000298c  lea     rcx, [rbp+57h+var_60]
0x180002990  call    ?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ; LinkedList<OrderedSetItem<PositionData>>::Reset(void)
0x180002995  xor     eax, eax
0x180002997  add     rsp, 98h
0x18000299e  pop     rdi
0x18000299f  pop     rsi
0x1800029a0  pop     rbx
0x1800029a1  pop     rbp
0x1800029a2  retn
```
