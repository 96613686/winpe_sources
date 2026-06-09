# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>,void *> * const)

- ea: `0x1800133f0`
- end: `0x180013519`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018928`
- `0x180018e54`

## callees

- `0x1800115f8`
- `0x180011648`
- `0x1800133f0`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Insert_node(
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
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(
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
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(
            a1,
            v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(a1);
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
0x1800133f0  push    rbx
0x1800133f2  sub     rsp, 20h
0x1800133f6  inc     qword ptr [rcx+8]
0x1800133fa  mov     r9, r8
0x1800133fd  mov     r11, [rcx]
0x180013400  mov     rbx, rcx
0x180013403  mov     rax, [rdx]
0x180013406  mov     [r8+8], rax
0x18001340a  cmp     rax, r11
0x18001340d  jnz     short loc_180013424
0x18001340f  mov     [r11], r8
0x180013412  mov     [r11+8], r8
0x180013416  mov     [r11+10h], r8
0x18001341a  mov     byte ptr [r8+18h], 1
0x18001341f  jmp     loc_180013510
0x180013424  cmp     dword ptr [rdx+8], 0
0x180013428  jnz     short loc_18001343A
0x18001342a  mov     [rax+10h], r9
0x18001342e  cmp     rax, [r11+10h]
0x180013432  jnz     short loc_180013445
0x180013434  mov     [r11+10h], r9
0x180013438  jmp     short loc_180013445
0x18001343a  mov     [rax], r9
0x18001343d  cmp     rax, [r11]
0x180013440  jnz     short loc_180013445
0x180013442  mov     [r11], r9
0x180013445  mov     rax, [r8+8]
0x180013449  mov     r10, r9
0x18001344c  jmp     loc_1800134FE
0x180013451  mov     rdx, [r10+8]
0x180013455  mov     rcx, [rdx+8]
0x180013459  mov     rax, [rcx]
0x18001345c  cmp     rdx, rax
0x18001345f  jnz     short loc_1800134A2
0x180013461  mov     rax, [rcx+10h]
0x180013465  cmp     byte ptr [rax+18h], 0
0x180013469  jz      short loc_1800134A8
0x18001346b  cmp     r10, [rdx+10h]
0x18001346f  jnz     short loc_18001347C
0x180013471  mov     rcx, rbx
0x180013474  mov     r10, rdx
0x180013477  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x18001347c  mov     rax, [r10+8]
0x180013480  mov     byte ptr [rax+18h], 1
0x180013484  mov     rax, [r10+8]
0x180013488  mov     rcx, [rax+8]
0x18001348c  mov     byte ptr [rcx+18h], 0
0x180013490  mov     rcx, rbx
0x180013493  mov     rdx, [r10+8]
0x180013497  mov     rdx, [rdx+8]
0x18001349b  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800134a0  jmp     short loc_1800134FA
0x1800134a2  cmp     byte ptr [rax+18h], 0
0x1800134a6  jnz     short loc_1800134C6
0x1800134a8  mov     byte ptr [rdx+18h], 1
0x1800134ac  mov     byte ptr [rax+18h], 1
0x1800134b0  mov     rax, [r10+8]
0x1800134b4  mov     rcx, [rax+8]
0x1800134b8  mov     byte ptr [rcx+18h], 0
0x1800134bc  mov     rax, [r10+8]
0x1800134c0  mov     r10, [rax+8]
0x1800134c4  jmp     short loc_1800134FA
0x1800134c6  cmp     r10, [rdx]
0x1800134c9  jnz     short loc_1800134D6
0x1800134cb  mov     rcx, rbx
0x1800134ce  mov     r10, rdx
0x1800134d1  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Rrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800134d6  mov     rax, [r10+8]
0x1800134da  mov     byte ptr [rax+18h], 1
0x1800134de  mov     rax, [r10+8]
0x1800134e2  mov     rcx, [rax+8]
0x1800134e6  mov     byte ptr [rcx+18h], 0
0x1800134ea  mov     rcx, rbx
0x1800134ed  mov     rdx, [r10+8]
0x1800134f1  mov     rdx, [rdx+8]
0x1800134f5  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Lrotate(std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *)
0x1800134fa  mov     rax, [r10+8]
0x1800134fe  cmp     byte ptr [rax+18h], 0
0x180013502  jz      loc_180013451
0x180013508  mov     rax, [r11+8]
0x18001350c  mov     byte ptr [rax+18h], 1
0x180013510  mov     rax, r9
0x180013513  add     rsp, 20h
0x180013517  pop     rbx
0x180013518  retn
```
