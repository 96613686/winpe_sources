# std::_Tree<std::_Tmap_traits<_tagSIDArray,ulong,SidCmp,std::allocator<std::pair<_tagSIDArray const,ulong>>,0>>::_Emplace<std::pair<_tagSIDArray,int>>(std::pair<_tagSIDArray,int> &&)

- ea: `0x180029278`
- end: `0x1800293e0`
- name: `??$_Emplace@U?$pair@U_tagSIDArray@@H@std@@@?$_Tree@V?$_Tmap_traits@U_tagSIDArray@@KUSidCmp@@V?$allocator@U?$pair@$$CBU_tagSIDArray@@K@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_tagSIDArray@@H@1@@Z`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180024ebc`

## callees

- `0x180029278`
- `0x1800293f0`
- `0x180037e58`
- `0x18003bb9c`
- `0x1800414ec`
- `0x18004b430`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800293d9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800293d9`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<_tagSIDArray,unsigned long,SidCmp,std::allocator<std::pair<_tagSIDArray const,unsigned long>>,0>>::_Emplace<std::pair<_tagSIDArray,int>>(
        _QWORD *a1,
        __int64 a2,
        const void *a3)
{
  __int64 *v6; // r13
  __int64 *v7; // rbx
  int v8; // ebp
  __int64 *v9; // rsi
  __int64 *v10; // r12
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 *v18; // [rsp+20h] [rbp-48h] BYREF
  int v19; // [rsp+28h] [rbp-40h]
  int v20; // [rsp+2Ch] [rbp-3Ch]
  __int64 *v21; // [rsp+70h] [rbp+8h] BYREF
  __int64 v22; // [rsp+80h] [rbp+18h]

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8LL);
  v8 = 0;
  v22 = 0;
  v9 = v6;
  if ( *((_BYTE *)v7 + 25) )
  {
    v10 = v7;
  }
  else
  {
    do
    {
      v10 = v7;
      if ( memcmp_0((char *)v7 + 28, a3, 0x44u) >= 0 )
      {
        v8 = 1;
        v9 = v7;
      }
      else
      {
        v8 = 0;
        v7 += 2;
      }
      v7 = (__int64 *)*v7;
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( *((_BYTE *)v9 + 25) || memcmp_0(a3, (char *)v9 + 28, 0x44u) < 0 )
  {
    if ( a1[1] == 0x276276276276276LL )
      std::_Xlength_error("map/set too long");
    v21 = v6;
    v11 = std::_Allocate<16,std::_Default_allocate_traits>(0x68u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_tagSIDArray const,unsigned long>,void *>>>::construct<std::pair<_tagSIDArray const,unsigned long>,std::pair<_tagSIDArray,int>>(
      v12,
      (char *)v11 + 28,
      a3,
      v11,
      a1,
      0);
    std::_Construct_in_place<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(
      v13,
      &v21);
    std::_Construct_in_place<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(
      v14 + 8,
      &v21);
    std::_Construct_in_place<std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(
      v15 + 16,
      &v21);
    *(_WORD *)(v16 + 24) = 0;
    v18 = v10;
    v19 = v8;
    v20 = v22;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<_tagSIDArray const,unsigned long>>>::_Insert_node(
                      a1,
                      &v18,
                      v16);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180029278  mov     [rsp+arg_8], rbx
0x18002927d  push    rbp
0x18002927e  push    rsi
0x18002927f  push    rdi
0x180029280  push    r12
0x180029282  push    r13
0x180029284  push    r14
0x180029286  push    r15
0x180029288  sub     rsp, 30h
0x18002928c  mov     r15, r8
0x18002928f  mov     rdi, rdx
0x180029292  mov     r14, rcx
0x180029295  mov     r13, [rcx]
0x180029298  mov     rbx, [r13+8]
0x18002929c  xor     ebp, ebp
0x18002929e  xor     eax, eax
0x1800292a0  mov     [rsp+68h+arg_10], rax
0x1800292a8  mov     rsi, r13
0x1800292ab  cmp     [rbx+19h], al
0x1800292ae  jnz     loc_1800293CA
0x1800292b4  mov     r12, rbx
0x1800292b7  lea     rcx, [rbx+1Ch]; Buf1
0x1800292bb  mov     r8d, 44h ; 'D'; Size
0x1800292c1  mov     rdx, r15; Buf2
0x1800292c4  call    memcmp_0
0x1800292c9  test    eax, eax
0x1800292cb  jns     loc_1800293B4
0x1800292d1  xor     ebp, ebp
0x1800292d3  add     rbx, 10h
0x1800292d7  mov     rbx, [rbx]
0x1800292da  cmp     byte ptr [rbx+19h], 0
0x1800292de  jz      short loc_1800292B4
0x1800292e0  cmp     byte ptr [rsi+19h], 0
0x1800292e4  jnz     short loc_180029300
0x1800292e6  lea     rdx, [rsi+1Ch]; Buf2
0x1800292ea  mov     r8d, 44h ; 'D'; Size
0x1800292f0  mov     rcx, r15; Buf1
0x1800292f3  call    memcmp_0
0x1800292f8  test    eax, eax
0x1800292fa  jns     loc_1800293C1
0x180029300  mov     rax, 276276276276276h
0x18002930a  cmp     [r14+8], rax
0x18002930e  jz      loc_1800293D2
0x180029314  mov     [rsp+68h+arg_0], r13
0x180029319  mov     [rsp+68h+var_48], r14
0x18002931e  mov     [rsp+68h+var_40], 0
0x180029327  mov     ecx, 68h ; 'h'
0x18002932c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180029331  mov     r9, rax
0x180029334  lea     rdx, [rax+1Ch]
0x180029338  mov     r8, r15
0x18002933b  call    ??$construct@U?$pair@$$CBU_tagSIDArray@@K@std@@U?$pair@U_tagSIDArray@@H@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@@1@QEAU?$pair@$$CBU_tagSIDArray@@K@1@$$QEAU?$pair@U_tagSIDArray@@H@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *>>>::construct<std::pair<_tagSIDArray const,ulong>,std::pair<_tagSIDArray,int>>(std::allocator<std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *>> &,std::pair<_tagSIDArray const,ulong> * const,std::pair<_tagSIDArray,int> &&)
0x180029340  lea     rdx, [rsp+68h+arg_0]
0x180029345  mov     rcx, r9
0x180029348  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &)
0x18002934d  lea     rcx, [r9+8]
0x180029351  lea     rdx, [rsp+68h+arg_0]
0x180029356  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &)
0x18002935b  lea     rcx, [r9+10h]
0x18002935f  lea     rdx, [rsp+68h+arg_0]
0x180029364  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@U_VAULT_CAUB@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> *,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &>(std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &,std::_Tree_node<std::pair<VAULT_SCHEMA_ELEMENT_ID const,_VAULT_CAUB>,void *> * &)
0x180029369  mov     word ptr [r9+18h], 0
0x180029370  mov     [rsp+68h+var_48], r12
0x180029375  mov     dword ptr [rsp+68h+var_40], ebp
0x180029379  mov     rax, [rsp+68h+arg_10]
0x180029381  mov     dword ptr [rsp+68h+var_40+4], eax
0x180029385  mov     r8, r9
0x180029388  lea     rdx, [rsp+68h+var_48]
0x18002938d  mov     rcx, r14
0x180029390  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_tagSIDArray@@K@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_tagSIDArray const,ulong>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *> *>,std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *> * const)
0x180029395  mov     [rdi], rax
0x180029398  mov     byte ptr [rdi+8], 1
0x18002939c  mov     rax, rdi
0x18002939f  mov     rbx, [rsp+68h+arg_8]
0x1800293a4  add     rsp, 30h
0x1800293a8  pop     r15
0x1800293aa  pop     r14
0x1800293ac  pop     r13
0x1800293ae  pop     r12
0x1800293b0  pop     rdi
0x1800293b1  pop     rsi
0x1800293b2  pop     rbp
0x1800293b3  retn
0x1800293b4  mov     ebp, 1
0x1800293b9  mov     rsi, rbx
0x1800293bc  jmp     loc_1800292D7
0x1800293c1  mov     [rdi], rsi
0x1800293c4  mov     byte ptr [rdi+8], 0
0x1800293c8  jmp     short loc_18002939C
0x1800293ca  mov     r12, rbx
0x1800293cd  jmp     loc_1800292E0
0x1800293d2  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800293d9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
