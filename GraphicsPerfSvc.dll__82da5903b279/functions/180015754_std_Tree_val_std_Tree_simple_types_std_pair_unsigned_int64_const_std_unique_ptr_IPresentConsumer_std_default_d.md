# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>>,void *> * const)

- ea: `0x180015754`
- end: `0x18001587d`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180014318`
- `0x180016fe4`
- `0x1800170dc`
- `0x1800171c8`
- `0x1800274b8`
- `0x1800275c8`
- `0x18002767c`
- `0x180027798`
- `0x1800278ac`
- `0x180027974`
- `0x180027a58`
- `0x180027f38`
- `0x18002802c`
- `0x180028120`

## callees

- `0x180015754`
- `0x180015884`
- `0x180015900`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Insert_node(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  _QWORD *v4; // r11
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 i; // r10
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax

  ++*(_QWORD *)(a1 + 8);
  v3 = a3;
  v4 = *(_QWORD **)a1;
  v6 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v6 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v6 = a3;
      if ( v6 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v6[2] = a3;
      if ( v6 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v7 = *(_QWORD *)(a3 + 8);
    for ( i = a3; ; v7 = *(_QWORD *)(i + 8) )
    {
      if ( *(_BYTE *)(v7 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return v3;
      }
      v9 = *(_QWORD *)(i + 8);
      v10 = *(__int64 **)(v9 + 8);
      v11 = *v10;
      if ( v9 == *v10 )
      {
        v11 = v10[2];
        if ( !*(_BYTE *)(v11 + 24) )
          goto LABEL_15;
        if ( i == *(_QWORD *)(v9 + 16) )
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Lrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>::_Rrotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL));
      }
      else
      {
        if ( !*(_BYTE *)(v11 + 24) )
        {
LABEL_15:
          *(_BYTE *)(v9 + 24) = 1;
          *(_BYTE *)(v11 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
          i = *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL);
          continue;
        }
        if ( i == *(_QWORD *)v9 )
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>::_Rrotate(
            a1,
            v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Lrotate(a1);
      }
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return v3;
}

```

## disassembly

```asm
0x180015754  push    rbx
0x180015756  sub     rsp, 20h
0x18001575a  inc     qword ptr [rcx+8]
0x18001575e  mov     r9, r8
0x180015761  mov     r11, [rcx]
0x180015764  mov     rbx, rcx
0x180015767  mov     rax, [rdx]
0x18001576a  mov     [r8+8], rax
0x18001576e  cmp     rax, r11
0x180015771  jnz     short loc_180015788
0x180015773  mov     [r11], r8
0x180015776  mov     [r11+8], r8
0x18001577a  mov     [r11+10h], r8
0x18001577e  mov     byte ptr [r8+18h], 1
0x180015783  jmp     loc_180015874
0x180015788  cmp     dword ptr [rdx+8], 0
0x18001578c  jnz     short loc_18001579E
0x18001578e  mov     [rax+10h], r9
0x180015792  cmp     rax, [r11+10h]
0x180015796  jnz     short loc_1800157A9
0x180015798  mov     [r11+10h], r9
0x18001579c  jmp     short loc_1800157A9
0x18001579e  mov     [rax], r9
0x1800157a1  cmp     rax, [r11]
0x1800157a4  jnz     short loc_1800157A9
0x1800157a6  mov     [r11], r9
0x1800157a9  mov     rax, [r8+8]
0x1800157ad  mov     r10, r9
0x1800157b0  jmp     loc_180015862
0x1800157b5  mov     rdx, [r10+8]
0x1800157b9  mov     rcx, [rdx+8]
0x1800157bd  mov     rax, [rcx]
0x1800157c0  cmp     rdx, rax
0x1800157c3  jnz     short loc_180015806
0x1800157c5  mov     rax, [rcx+10h]
0x1800157c9  cmp     byte ptr [rax+18h], 0
0x1800157cd  jz      short loc_18001580C
0x1800157cf  cmp     r10, [rdx+10h]
0x1800157d3  jnz     short loc_1800157E0
0x1800157d5  mov     rcx, rbx
0x1800157d8  mov     r10, rdx
0x1800157db  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *)
0x1800157e0  mov     rax, [r10+8]
0x1800157e4  mov     byte ptr [rax+18h], 1
0x1800157e8  mov     rax, [r10+8]
0x1800157ec  mov     rcx, [rax+8]
0x1800157f0  mov     byte ptr [rcx+18h], 0
0x1800157f4  mov     rcx, rbx
0x1800157f7  mov     rdx, [r10+8]
0x1800157fb  mov     rdx, [rdx+8]
0x1800157ff  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>::_Rrotate(std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *> *)
0x180015804  jmp     short loc_18001585E
0x180015806  cmp     byte ptr [rax+18h], 0
0x18001580a  jnz     short loc_18001582A
0x18001580c  mov     byte ptr [rdx+18h], 1
0x180015810  mov     byte ptr [rax+18h], 1
0x180015814  mov     rax, [r10+8]
0x180015818  mov     rcx, [rax+8]
0x18001581c  mov     byte ptr [rcx+18h], 0
0x180015820  mov     rax, [r10+8]
0x180015824  mov     r10, [rax+8]
0x180015828  jmp     short loc_18001585E
0x18001582a  cmp     r10, [rdx]
0x18001582d  jnz     short loc_18001583A
0x18001582f  mov     rcx, rbx
0x180015832  mov     r10, rdx
0x180015835  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>::_Rrotate(std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *> *)
0x18001583a  mov     rax, [r10+8]
0x18001583e  mov     byte ptr [rax+18h], 1
0x180015842  mov     rax, [r10+8]
0x180015846  mov     rcx, [rax+8]
0x18001584a  mov     byte ptr [rcx+18h], 0
0x18001584e  mov     rcx, rbx
0x180015851  mov     rdx, [r10+8]
0x180015855  mov     rdx, [rdx+8]
0x180015859  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *)
0x18001585e  mov     rax, [r10+8]
0x180015862  cmp     byte ptr [rax+18h], 0
0x180015866  jz      loc_1800157B5
0x18001586c  mov     rax, [r11+8]
0x180015870  mov     byte ptr [rax+18h], 1
0x180015874  mov     rax, r9
0x180015877  add     rsp, 20h
0x18001587b  pop     rbx
0x18001587c  retn
```
