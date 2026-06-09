# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RBDeleteFixup(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)

- ea: `0x180005208`
- end: `0x18000537f`
- name: `?RBDeleteFixup@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAXPEAVCNode@12@@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005fbc`

## callees

- `0x180002420`
- `0x180004960`
- `0x180005208`
- `0x1800061f8`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RBDeleteFixup(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *v2; // r10
  _QWORD *v3; // r9
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r11
  __int64 result; // rax
  __int64 v9; // r11

  v2 = a1;
  if ( !a2 )
    ATL::BaseAtlThrow(-2147467259);
  if ( a2 != *a1 )
  {
    do
    {
      if ( *(_DWORD *)(a2 + 8) != 1 )
        break;
      v3 = (_QWORD *)(a2 + 32);
      v4 = *(_QWORD *)(a2 + 32);
      v5 = *(_QWORD *)(v4 + 16);
      if ( a2 == v5 )
      {
        v6 = *(_QWORD *)(v4 + 24);
        if ( !*(_DWORD *)(v6 + 8) )
        {
          *(_DWORD *)(v6 + 8) = 1;
          *(_DWORD *)(*(_QWORD *)(v6 + 32) + 8LL) = 0;
          ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::LeftRotate(
            v2,
            *v3);
          v4 = *v3;
          v6 = *(_QWORD *)(*v3 + 24LL);
        }
        v7 = *(_QWORD *)(v6 + 16);
        if ( *(_DWORD *)(v7 + 8) != 1 || (result = *(_QWORD *)(v6 + 24), *(_DWORD *)(result + 8) != 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v6 + 24) + 8LL) == 1 )
          {
            *(_DWORD *)(v7 + 8) = 1;
            *(_DWORD *)(v6 + 8) = 0;
            ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RightRotate(
              v2,
              v6);
            v4 = *v3;
            v6 = *(_QWORD *)(*v3 + 24LL);
          }
          *(_DWORD *)(v6 + 8) = *(_DWORD *)(v4 + 8);
          *(_DWORD *)(*v3 + 8LL) = 1;
          *(_DWORD *)(*(_QWORD *)(v6 + 24) + 8LL) = 1;
          result = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::LeftRotate(
                     v2,
                     *v3);
LABEL_21:
          v3 = v2;
          goto LABEL_22;
        }
        *(_DWORD *)(v6 + 8) = 0;
      }
      else
      {
        if ( !*(_DWORD *)(v5 + 8) )
        {
          *(_DWORD *)(v5 + 8) = 1;
          *(_DWORD *)(*(_QWORD *)(v5 + 32) + 8LL) = 0;
          ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RightRotate(
            v2,
            *v3);
          v4 = *v3;
          v5 = *(_QWORD *)(*v3 + 16LL);
        }
        v9 = *(_QWORD *)(v5 + 24);
        if ( *(_DWORD *)(v9 + 8) != 1 || (result = *(_QWORD *)(v5 + 16), *(_DWORD *)(result + 8) != 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v5 + 16) + 8LL) == 1 )
          {
            *(_DWORD *)(v9 + 8) = 1;
            *(_DWORD *)(v5 + 8) = 0;
            ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::LeftRotate(
              v2,
              v5);
            v4 = *v3;
            v5 = *(_QWORD *)(*v3 + 16LL);
          }
          *(_DWORD *)(v5 + 8) = *(_DWORD *)(v4 + 8);
          *(_DWORD *)(*v3 + 8LL) = 1;
          *(_DWORD *)(*(_QWORD *)(v5 + 16) + 8LL) = 1;
          result = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RightRotate(
                     v2,
                     *v3);
          goto LABEL_21;
        }
        *(_DWORD *)(v5 + 8) = 0;
      }
LABEL_22:
      a2 = *v3;
    }
    while ( *v3 != *v2 );
  }
  *(_DWORD *)(a2 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x180005208  push    rbx
0x18000520a  sub     rsp, 20h
0x18000520e  mov     r10, rcx
0x180005211  test    rdx, rdx
0x180005214  jz      loc_180005374
0x18000521a  mov     ebx, 1
0x18000521f  cmp     rdx, [rcx]
0x180005222  jz      loc_18000536B
0x180005228  cmp     [rdx+8], ebx
0x18000522b  jnz     loc_18000536B
0x180005231  lea     r9, [rdx+20h]
0x180005235  mov     r8, [r9]
0x180005238  mov     rcx, [r8+10h]
0x18000523c  cmp     rdx, rcx
0x18000523f  jnz     loc_1800052D5
0x180005245  mov     rdx, [r8+18h]
0x180005249  cmp     dword ptr [rdx+8], 0
0x18000524d  jnz     short loc_18000526F
0x18000524f  mov     [rdx+8], ebx
0x180005252  mov     rax, [rdx+20h]
0x180005256  mov     dword ptr [rax+8], 0
0x18000525d  mov     rdx, [r9]
0x180005260  mov     rcx, r10
0x180005263  call    ?LeftRotate@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::LeftRotate(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x180005268  mov     r8, [r9]
0x18000526b  mov     rdx, [r8+18h]
0x18000526f  mov     r11, [rdx+10h]
0x180005273  cmp     [r11+8], ebx
0x180005277  jnz     short loc_18000528E
0x180005279  mov     rax, [rdx+18h]
0x18000527d  cmp     [rax+8], ebx
0x180005280  jnz     short loc_18000528E
0x180005282  mov     dword ptr [rdx+8], 0
0x180005289  jmp     loc_18000535F
0x18000528e  mov     rax, [rdx+18h]
0x180005292  cmp     [rax+8], ebx
0x180005295  jnz     short loc_1800052B1
0x180005297  mov     [r11+8], ebx
0x18000529b  mov     dword ptr [rdx+8], 0
0x1800052a2  mov     rcx, r10
0x1800052a5  call    ?RightRotate@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RightRotate(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x1800052aa  mov     r8, [r9]
0x1800052ad  mov     rdx, [r8+18h]
0x1800052b1  mov     eax, [r8+8]
0x1800052b5  mov     [rdx+8], eax
0x1800052b8  mov     rax, [r9]
0x1800052bb  mov     [rax+8], ebx
0x1800052be  mov     rax, [rdx+18h]
0x1800052c2  mov     [rax+8], ebx
0x1800052c5  mov     rdx, [r9]
0x1800052c8  mov     rcx, r10
0x1800052cb  call    ?LeftRotate@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::LeftRotate(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x1800052d0  jmp     loc_18000535C
0x1800052d5  cmp     dword ptr [rcx+8], 0
0x1800052d9  jnz     short loc_1800052FB
0x1800052db  mov     [rcx+8], ebx
0x1800052de  mov     rax, [rcx+20h]
0x1800052e2  mov     dword ptr [rax+8], 0
0x1800052e9  mov     rdx, [r9]
0x1800052ec  mov     rcx, r10
0x1800052ef  call    ?RightRotate@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RightRotate(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x1800052f4  mov     r8, [r9]
0x1800052f7  mov     rcx, [r8+10h]
0x1800052fb  mov     r11, [rcx+18h]
0x1800052ff  cmp     [r11+8], ebx
0x180005303  jnz     short loc_180005317
0x180005305  mov     rax, [rcx+10h]
0x180005309  cmp     [rax+8], ebx
0x18000530c  jnz     short loc_180005317
0x18000530e  mov     dword ptr [rcx+8], 0
0x180005315  jmp     short loc_18000535F
0x180005317  mov     rax, [rcx+10h]
0x18000531b  cmp     [rax+8], ebx
0x18000531e  jnz     short loc_18000533D
0x180005320  mov     [r11+8], ebx
0x180005324  mov     dword ptr [rcx+8], 0
0x18000532b  mov     rdx, rcx
0x18000532e  mov     rcx, r10
0x180005331  call    ?LeftRotate@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::LeftRotate(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x180005336  mov     r8, [r9]
0x180005339  mov     rcx, [r8+10h]
0x18000533d  mov     eax, [r8+8]
0x180005341  mov     [rcx+8], eax
0x180005344  mov     rax, [r9]
0x180005347  mov     [rax+8], ebx
0x18000534a  mov     rax, [rcx+10h]
0x18000534e  mov     [rax+8], ebx
0x180005351  mov     rdx, [r9]
0x180005354  mov     rcx, r10
0x180005357  call    ?RightRotate@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RightRotate(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x18000535c  mov     r9, r10
0x18000535f  mov     rdx, [r9]
0x180005362  cmp     rdx, [r10]
0x180005365  jnz     loc_180005228
0x18000536b  mov     [rdx+8], ebx
0x18000536e  add     rsp, 20h
0x180005372  pop     rbx
0x180005373  retn
0x180005374  mov     ecx, 80004005h; int
0x180005379  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
