# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemovePostOrder(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)

- ea: `0x1800061a8`
- end: `0x1800061ef`
- name: `?RemovePostOrder@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f54`
- `0x1800061a8`

## callees

- `0x1800061a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemovePostOrder(
        _QWORD *a1,
        __int64 a2)
{
  __int64 result; // rax

  if ( a2 != a1[5] )
  {
    ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemovePostOrder(
      a1,
      *(_QWORD *)(a2 + 16));
    ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemovePostOrder(
      a1,
      *(_QWORD *)(a2 + 24));
    result = a1[2];
    *(_QWORD *)(a2 + 16) = result;
    a1[2] = a2;
    --a1[1];
  }
  return result;
}

```

## disassembly

```asm
0x1800061a8  mov     [rsp+arg_0], rbx
0x1800061ad  push    rdi
0x1800061ae  sub     rsp, 20h
0x1800061b2  mov     rdi, rdx
0x1800061b5  mov     rbx, rcx
0x1800061b8  cmp     rdx, [rcx+28h]
0x1800061bc  jz      short loc_1800061E4
0x1800061be  mov     rdx, [rdx+10h]
0x1800061c2  call    ?RemovePostOrder@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemovePostOrder(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x1800061c7  mov     rdx, [rdi+18h]
0x1800061cb  mov     rcx, rbx
0x1800061ce  call    ?RemovePostOrder@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemovePostOrder(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x1800061d3  nop
0x1800061d4  mov     rax, [rbx+10h]
0x1800061d8  mov     [rdi+10h], rax
0x1800061dc  mov     [rbx+10h], rdi
0x1800061e0  dec     qword ptr [rbx+8]
0x1800061e4  mov     rbx, [rsp+28h+arg_0]
0x1800061e9  add     rsp, 20h
0x1800061ed  pop     rdi
0x1800061ee  retn
```
