# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemoveAt(__POSITION *)

- ea: `0x180005fbc`
- end: `0x1800060c7`
- name: `?RemoveAt@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAXPEAU__POSITION@@@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003aec`

## callees

- `0x180002420`
- `0x180005208`
- `0x180005fbc`
- `0x180006c78`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemoveAt(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax

  if ( a2 )
  {
    v4 = a1[5];
    if ( *(_QWORD *)(a2 + 16) == v4 || *(_QWORD *)(a2 + 24) == v4 )
      v5 = a2;
    else
      v5 = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Successor();
    v6 = *(_QWORD *)(v5 + 16);
    if ( v6 == v4 )
      v6 = *(_QWORD *)(v5 + 24);
    *(_QWORD *)(v6 + 32) = *(_QWORD *)(v5 + 32);
    v7 = *(_QWORD *)(v5 + 32);
    if ( v7 == a1[5] )
    {
      *a1 = v6;
    }
    else if ( v5 == *(_QWORD *)(v7 + 16) )
    {
      *(_QWORD *)(v7 + 16) = v6;
    }
    else
    {
      *(_QWORD *)(v7 + 24) = v6;
    }
    if ( *(_DWORD *)(v5 + 8) == 1 )
      ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RBDeleteFixup(
        a1,
        v6);
    if ( v5 != a2 )
    {
      *(_QWORD *)(v5 + 32) = *(_QWORD *)(a2 + 32);
      v8 = *(_QWORD *)(a2 + 32);
      if ( *(_QWORD *)(v8 + 16) == a2 )
        *(_QWORD *)(v8 + 16) = v5;
      else
        *(_QWORD *)(v8 + 24) = v5;
      v9 = *(_QWORD *)(a2 + 24);
      *(_QWORD *)(v5 + 24) = v9;
      *(_QWORD *)(v5 + 16) = *(_QWORD *)(a2 + 16);
      *(_DWORD *)(v5 + 8) = *(_DWORD *)(a2 + 8);
      *(_QWORD *)(v9 + 32) = v5;
      *(_QWORD *)(*(_QWORD *)(v5 + 16) + 32LL) = v5;
      if ( *a1 == a2 )
        *a1 = v5;
    }
    v10 = *a1;
    if ( *a1 )
    {
      if ( v10 == -32 )
        ATL::BaseAtlThrow(-2147467259);
      *(_QWORD *)(v10 + 32) = a1[5];
    }
    *(_QWORD *)(a2 + 16) = a1[2];
    a1[2] = a2;
    --a1[1];
  }
}

```

## disassembly

```asm
0x180005fbc  test    rdx, rdx
0x180005fbf  jz      locret_1800060BB
0x180005fc5  mov     [rsp+arg_0], rbx
0x180005fca  mov     [rsp+arg_8], rsi
0x180005fcf  push    rdi
0x180005fd0  sub     rsp, 20h
0x180005fd4  mov     rsi, rdx
0x180005fd7  mov     rdi, rcx
0x180005fda  mov     r9, [rcx+28h]
0x180005fde  cmp     [rdx+10h], r9
0x180005fe2  jz      short loc_180005FF4
0x180005fe4  cmp     [rdx+18h], r9
0x180005fe8  jz      short loc_180005FF4
0x180005fea  call    ?Successor@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Successor(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x180005fef  mov     rbx, rax
0x180005ff2  jmp     short loc_180005FF7
0x180005ff4  mov     rbx, rsi
0x180005ff7  mov     rdx, [rbx+10h]
0x180005ffb  cmp     rdx, r9
0x180005ffe  jnz     short loc_180006004
0x180006000  mov     rdx, [rbx+18h]
0x180006004  mov     rax, [rbx+20h]
0x180006008  mov     [rdx+20h], rax
0x18000600c  mov     rax, [rbx+20h]
0x180006010  cmp     rax, [rdi+28h]
0x180006014  jnz     short loc_18000601B
0x180006016  mov     [rdi], rdx
0x180006019  jmp     short loc_18000602B
0x18000601b  cmp     rbx, [rax+10h]
0x18000601f  jnz     short loc_180006027
0x180006021  mov     [rax+10h], rdx
0x180006025  jmp     short loc_18000602B
0x180006027  mov     [rax+18h], rdx
0x18000602b  cmp     dword ptr [rbx+8], 1
0x18000602f  jnz     short loc_180006039
0x180006031  mov     rcx, rdi
0x180006034  call    ?RBDeleteFixup@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RBDeleteFixup(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x180006039  cmp     rbx, rsi
0x18000603c  jz      short loc_180006084
0x18000603e  mov     rax, [rsi+20h]
0x180006042  mov     [rbx+20h], rax
0x180006046  mov     rax, [rsi+20h]
0x18000604a  cmp     [rax+10h], rsi
0x18000604e  jnz     short loc_180006056
0x180006050  mov     [rax+10h], rbx
0x180006054  jmp     short loc_18000605A
0x180006056  mov     [rax+18h], rbx
0x18000605a  mov     rcx, [rsi+18h]
0x18000605e  mov     [rbx+18h], rcx
0x180006062  mov     rax, [rsi+10h]
0x180006066  mov     [rbx+10h], rax
0x18000606a  mov     eax, [rsi+8]
0x18000606d  mov     [rbx+8], eax
0x180006070  mov     [rcx+20h], rbx
0x180006074  mov     rax, [rbx+10h]
0x180006078  mov     [rax+20h], rbx
0x18000607c  cmp     [rdi], rsi
0x18000607f  jnz     short loc_180006084
0x180006081  mov     [rdi], rbx
0x180006084  mov     rax, [rdi]
0x180006087  test    rax, rax
0x18000608a  jz      short loc_18000609C
0x18000608c  lea     rcx, [rax+20h]
0x180006090  test    rcx, rcx
0x180006093  jz      short loc_1800060BC
0x180006095  mov     rax, [rdi+28h]
0x180006099  mov     [rcx], rax
0x18000609c  mov     rax, [rdi+10h]
0x1800060a0  mov     [rsi+10h], rax
0x1800060a4  mov     [rdi+10h], rsi
0x1800060a8  dec     qword ptr [rdi+8]
0x1800060ac  mov     rbx, [rsp+28h+arg_0]
0x1800060b1  mov     rsi, [rsp+28h+arg_8]
0x1800060b6  add     rsp, 20h
0x1800060ba  pop     rdi
0x1800060bb  retn
0x1800060bc  mov     ecx, 80004005h; int
0x1800060c1  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
