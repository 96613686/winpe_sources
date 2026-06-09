# std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *>,std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> * const)

- ea: `0x180002330`
- end: `0x1800025be`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003000`

## callees

- `0x180002330`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r9
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  __int64 v7; // rax
  __int64 *v8; // r10
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // r10
  _QWORD *v12; // rcx
  __int64 result; // rax
  _QWORD *v14; // r10
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // r10
  _QWORD *v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 == v4 )
  {
    *v4 = a3;
    result = a3;
    v4[1] = a3;
    v4[2] = a3;
    *(_BYTE *)(a3 + 24) = 1;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = (_QWORD *)a3;
    if ( !*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) )
    {
      while ( 1 )
      {
        v7 = v6[1];
        v8 = *(__int64 **)(v7 + 8);
        v9 = *v8;
        if ( v7 == *v8 )
          break;
        if ( *(_BYTE *)(v9 + 24) )
        {
          v14 = *(_QWORD **)v7;
          if ( v6 == *(_QWORD **)v7 )
          {
            v6 = (_QWORD *)v6[1];
            *(_QWORD *)v7 = v14[2];
            v15 = v14[2];
            if ( !*(_BYTE *)(v15 + 25) )
              *(_QWORD *)(v15 + 8) = v7;
            v14[1] = *(_QWORD *)(v7 + 8);
            if ( v7 == *(_QWORD *)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v14;
            }
            else
            {
              v16 = *(_QWORD **)(v7 + 8);
              if ( v7 == v16[2] )
                v16[2] = v14;
              else
                *v16 = v14;
            }
            v14[2] = v7;
            *(_QWORD *)(v7 + 8) = v14;
          }
          *(_BYTE *)(v6[1] + 24LL) = 1;
          *(_BYTE *)(*(_QWORD *)(v6[1] + 8LL) + 24LL) = 0;
          v17 = *(_QWORD **)(v6[1] + 8LL);
          v18 = (_QWORD *)v17[2];
          v17[2] = *v18;
          if ( !*(_BYTE *)(*v18 + 25LL) )
            *(_QWORD *)(*v18 + 8LL) = v17;
          v18[1] = v17[1];
          if ( v17 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v18;
            *v18 = v17;
          }
          else
          {
            v19 = (_QWORD *)v17[1];
            if ( v17 == (_QWORD *)*v19 )
              *v19 = v18;
            else
              v19[2] = v18;
            *v18 = v17;
          }
LABEL_18:
          v17[1] = v18;
          goto LABEL_19;
        }
        *(_BYTE *)(v7 + 24) = 1;
        *(_BYTE *)(v9 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(v6[1] + 8LL) + 24LL) = 0;
        v6 = *(_QWORD **)(v6[1] + 8LL);
LABEL_19:
        if ( *(_BYTE *)(v6[1] + 24LL) )
          goto LABEL_20;
      }
      v10 = v8[2];
      if ( !*(_BYTE *)(v10 + 24) )
      {
        *(_BYTE *)(v7 + 24) = 1;
        *(_BYTE *)(v10 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(v6[1] + 8LL) + 24LL) = 0;
        v6 = *(_QWORD **)(v6[1] + 8LL);
        goto LABEL_19;
      }
      v11 = *(_QWORD **)(v7 + 16);
      if ( v6 == v11 )
      {
        v6 = (_QWORD *)v6[1];
        *(_QWORD *)(v7 + 16) = *v11;
        if ( !*(_BYTE *)(*v11 + 25LL) )
          *(_QWORD *)(*v11 + 8LL) = v7;
        v11[1] = *(_QWORD *)(v7 + 8);
        if ( v7 == *(_QWORD *)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v11;
        }
        else
        {
          v12 = *(_QWORD **)(v7 + 8);
          if ( v7 == *v12 )
            *v12 = v11;
          else
            v12[2] = v11;
        }
        *v11 = v7;
        *(_QWORD *)(v7 + 8) = v11;
      }
      *(_BYTE *)(v6[1] + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v6[1] + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(v6[1] + 8LL);
      v18 = (_QWORD *)*v17;
      *v17 = *(_QWORD *)(*v17 + 16LL);
      v20 = v18[2];
      if ( !*(_BYTE *)(v20 + 25) )
        *(_QWORD *)(v20 + 8) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v21 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)v21[2] )
          v21[2] = v18;
        else
          *v21 = v18;
      }
      v18[2] = v17;
      goto LABEL_18;
    }
LABEL_20:
    *(_BYTE *)(v4[1] + 24LL) = 1;
    return a3;
  }
  return result;
}

```

## disassembly

```asm
0x180002330  inc     qword ptr [rcx+8]
0x180002334  mov     r11, rcx
0x180002337  mov     r9, [rcx]
0x18000233a  mov     rax, [rdx]
0x18000233d  mov     [r8+8], rax
0x180002341  cmp     rax, r9
0x180002344  jz      loc_18000242E
0x18000234a  cmp     dword ptr [rdx+8], 0
0x18000234e  jnz     loc_180002442
0x180002354  mov     [rax+10h], r8
0x180002358  cmp     rax, [r9+10h]
0x18000235c  jnz     short loc_180002362
0x18000235e  mov     [r9+10h], r8
0x180002362  mov     rax, [r8+8]
0x180002366  mov     rdx, r8
0x180002369  cmp     byte ptr [rax+18h], 0
0x18000236d  jnz     loc_180002422
0x180002373  mov     rax, [rdx+8]
0x180002377  mov     r10, [rax+8]
0x18000237b  mov     rcx, [r10]
0x18000237e  cmp     rax, rcx
0x180002381  jnz     short loc_1800023E0
0x180002383  mov     rcx, [r10+10h]
0x180002387  cmp     byte ptr [rcx+18h], 0
0x18000238b  jz      loc_180002456
0x180002391  mov     r10, [rax+10h]
0x180002395  cmp     rdx, r10
0x180002398  jnz     loc_18000252E
0x18000239e  mov     rcx, [r10]
0x1800023a1  mov     rdx, rax
0x1800023a4  mov     [rax+10h], rcx
0x1800023a8  mov     rcx, [r10]
0x1800023ab  cmp     byte ptr [rcx+19h], 0
0x1800023af  jnz     short loc_1800023B5
0x1800023b1  mov     [rcx+8], rax
0x1800023b5  mov     rcx, [rax+8]
0x1800023b9  mov     [r10+8], rcx
0x1800023bd  mov     rcx, [r11]
0x1800023c0  cmp     rax, [rcx+8]
0x1800023c4  jz      loc_180002589
0x1800023ca  mov     rcx, [rax+8]
0x1800023ce  cmp     rax, [rcx]
0x1800023d1  jz      loc_180002524
0x1800023d7  mov     [rcx+10h], r10
0x1800023db  jmp     loc_180002527
0x1800023e0  cmp     byte ptr [rcx+18h], 0
0x1800023e4  jnz     loc_180002474
0x1800023ea  mov     byte ptr [rax+18h], 1
0x1800023ee  mov     byte ptr [rcx+18h], 1
0x1800023f2  mov     rax, [rdx+8]
0x1800023f6  mov     rcx, [rax+8]
0x1800023fa  mov     byte ptr [rcx+18h], 0
0x1800023fe  mov     rax, [rdx+8]
0x180002402  mov     rdx, [rax+8]
0x180002406  jmp     short loc_180002414
0x180002408  mov     [rax+10h], r10
0x18000240c  mov     [r10+10h], rcx
0x180002410  mov     [rcx+8], r10
0x180002414  mov     rax, [rdx+8]
0x180002418  cmp     byte ptr [rax+18h], 0
0x18000241c  jz      loc_180002373
0x180002422  mov     rax, [r9+8]
0x180002426  mov     byte ptr [rax+18h], 1
0x18000242a  mov     rax, r8
0x18000242d  retn
0x18000242e  mov     [r9], r8
0x180002431  mov     rax, r8
0x180002434  mov     [r9+8], r8
0x180002438  mov     [r9+10h], r8
0x18000243c  mov     byte ptr [r8+18h], 1
0x180002441  retn
0x180002442  mov     [rax], r8
0x180002445  cmp     rax, [r9]
0x180002448  jnz     loc_180002362
0x18000244e  mov     [r9], r8
0x180002451  jmp     loc_180002362
0x180002456  mov     byte ptr [rax+18h], 1
0x18000245a  mov     byte ptr [rcx+18h], 1
0x18000245e  mov     rax, [rdx+8]
0x180002462  mov     rcx, [rax+8]
0x180002466  mov     byte ptr [rcx+18h], 0
0x18000246a  mov     rax, [rdx+8]
0x18000246e  mov     rdx, [rax+8]
0x180002472  jmp     short loc_180002414
0x180002474  mov     r10, [rax]
0x180002477  cmp     rdx, r10
0x18000247a  jnz     short loc_1800024C3
0x18000247c  mov     rcx, [r10+10h]
0x180002480  mov     rdx, rax
0x180002483  mov     [rax], rcx
0x180002486  mov     rcx, [r10+10h]
0x18000248a  cmp     byte ptr [rcx+19h], 0
0x18000248e  jnz     short loc_180002494
0x180002490  mov     [rcx+8], rax
0x180002494  mov     rcx, [rax+8]
0x180002498  mov     [r10+8], rcx
0x18000249c  mov     rcx, [r11]
0x18000249f  cmp     rax, [rcx+8]
0x1800024a3  jz      loc_180002598
0x1800024a9  mov     rcx, [rax+8]
0x1800024ad  cmp     rax, [rcx+10h]
0x1800024b1  jnz     loc_1800025A1
0x1800024b7  mov     [rcx+10h], r10
0x1800024bb  mov     [r10+10h], rax
0x1800024bf  mov     [rax+8], r10
0x1800024c3  mov     rax, [rdx+8]
0x1800024c7  mov     byte ptr [rax+18h], 1
0x1800024cb  mov     rax, [rdx+8]
0x1800024cf  mov     rcx, [rax+8]
0x1800024d3  mov     byte ptr [rcx+18h], 0
0x1800024d7  mov     rax, [rdx+8]
0x1800024db  mov     rcx, [rax+8]
0x1800024df  mov     r10, [rcx+10h]
0x1800024e3  mov     rax, [r10]
0x1800024e6  mov     [rcx+10h], rax
0x1800024ea  mov     rax, [r10]
0x1800024ed  cmp     byte ptr [rax+19h], 0
0x1800024f1  jnz     short loc_1800024F7
0x1800024f3  mov     [rax+8], rcx
0x1800024f7  mov     rax, [rcx+8]
0x1800024fb  mov     [r10+8], rax
0x1800024ff  mov     rax, [r11]
0x180002502  cmp     rcx, [rax+8]
0x180002506  jz      loc_1800025A9
0x18000250c  mov     rax, [rcx+8]
0x180002510  cmp     rcx, [rax]
0x180002513  jnz     loc_1800025B5
0x180002519  mov     [rax], r10
0x18000251c  mov     [r10], rcx
0x18000251f  jmp     loc_180002410
0x180002524  mov     [rcx], r10
0x180002527  mov     [r10], rax
0x18000252a  mov     [rax+8], r10
0x18000252e  mov     rax, [rdx+8]
0x180002532  mov     byte ptr [rax+18h], 1
0x180002536  mov     rax, [rdx+8]
0x18000253a  mov     rcx, [rax+8]
0x18000253e  mov     byte ptr [rcx+18h], 0
0x180002542  mov     rax, [rdx+8]
0x180002546  mov     rcx, [rax+8]
0x18000254a  mov     r10, [rcx]
0x18000254d  mov     rax, [r10+10h]
0x180002551  mov     [rcx], rax
0x180002554  mov     rax, [r10+10h]
0x180002558  cmp     byte ptr [rax+19h], 0
0x18000255c  jnz     short loc_180002562
0x18000255e  mov     [rax+8], rcx
0x180002562  mov     rax, [rcx+8]
0x180002566  mov     [r10+8], rax
0x18000256a  mov     rax, [r11]
0x18000256d  cmp     rcx, [rax+8]
0x180002571  jz      short loc_18000258F
0x180002573  mov     rax, [rcx+8]
0x180002577  cmp     rcx, [rax+10h]
0x18000257b  jz      loc_180002408
0x180002581  mov     [rax], r10
0x180002584  jmp     loc_18000240C
0x180002589  mov     [rcx+8], r10
0x18000258d  jmp     short loc_180002527
0x18000258f  mov     [rax+8], r10
0x180002593  jmp     loc_18000240C
0x180002598  mov     [rcx+8], r10
0x18000259c  jmp     loc_1800024BB
0x1800025a1  mov     [rcx], r10
0x1800025a4  jmp     loc_1800024BB
0x1800025a9  mov     [rax+8], r10
0x1800025ad  mov     [r10], rcx
0x1800025b0  jmp     loc_180002410
0x1800025b5  mov     [rax+10h], r10
0x1800025b9  jmp     loc_18000251C
```
