# ServerResponseParser::ParseValueListNode(dsreg::CJsonValue *,struct_dsreg_server_response *)

- ea: `0x18009b86c`
- end: `0x18009baae`
- name: `?ParseValueListNode@ServerResponseParser@@CAJPEAVCJsonValue@dsreg@@PEAUstruct_dsreg_server_response@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct CJsonValue *, struct struct_dsreg_server_response *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009afb8`

## callees

- `0x1800873bc`
- `0x18008aa28`
- `0x18008aad8`
- `0x1800945f4`
- `0x1800946a4`
- `0x1800947a4`
- `0x180094850`
- `0x180094c30`
- `0x180094ee4`
- `0x18009b86c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009b8cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009b8d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009ba92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009b8cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009b8d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009ba92`

## string_xrefs

- `0x18009b926`: `%s: CJsonValue::GetJsonArray returns NULL for the node %s.`
- `0x18009ba68`: `%s: StringCompareIgnoreCase failed for item "%s". Error code 0x%08x. Ignore this error.`
- `0x18009b9a7`: `%s: Failed to read the node: "%s". ServerResponseParser::AssignJsonPropertyTo failed with error code 0x%08x. Ignore this node.`
- `0x18009b9df`: `%s: Failed to read value for item: "%s". ServerResponseParser::AssignJsonPropertyTo failed with error code 0x%08x. Ignore this node.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServerResponseParser::ParseValueListNode(
        struct CJsonValue *a1,
        struct struct_dsreg_server_response *a2)
{
  __int64 v4; // rdi
  unsigned __int16 *v5; // r14
  unsigned int v6; // esi
  __int64 v7; // r15
  __int64 v8; // rcx
  _QWORD ***v10; // rdx
  __int64 v11; // rcx
  __int64 *v12; // rbx
  int v13; // eax
  int v14; // eax
  unsigned __int64 v15; // r12
  int v16; // eax
  void **v17; // rdi
  unsigned __int16 *v18[2]; // [rsp+20h] [rbp-40h] BYREF
  const unsigned __int16 *v19; // [rsp+30h] [rbp-30h]
  __int64 v20[2]; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-18h]
  int v22; // [rsp+A0h] [rbp+40h] BYREF
  void *Block; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v24; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  v24 = 0;
  Block = 0;
  std::list<dsreg::CJsonValue *>::list<dsreg::CJsonValue *>(v20);
  if ( *(_DWORD *)a1 == 4 )
  {
    v10 = (_QWORD ***)*((_QWORD *)a1 + 9);
    if ( !v10 )
    {
      Logger::TraceError(
        L"%s: CJsonValue::GetJsonArray returns NULL for the node %s.",
        L"ServerResponseParser::ParseValueListNode",
        L"values");
      goto LABEL_3;
    }
    v6 = 0;
    *(_OWORD *)v18 = 0;
    std::list<dsreg::CJsonValue *>::_Construct_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<dsreg::CJsonValue *>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<dsreg::CJsonValue *>>,std::_Iterator_base0>>(
      v18,
      **v10,
      *v10);
    std::list<dsreg::CJsonValue *>::operator=(v20, (__int64 *)v18);
    std::_List_node<dsreg::CJsonValue *,void *>::_Free_non_head<std::allocator<std::_List_node<dsreg::CJsonValue *,void *>>>(
      v11,
      (__int64)v18[0]);
    std::_Deallocate<16>(v18[0], 24);
    v7 = v20[0];
    v12 = *(__int64 **)v20[0];
LABEL_8:
    if ( v12 == (__int64 *)v7 )
      goto LABEL_4;
    v13 = ServerResponseParser::AssignJsonPropertyTo(
            (struct CJsonValue *)v12[2],
            L"item",
            (const unsigned __int16 **)&v24);
    v5 = v24;
    if ( v13 < 0 )
    {
      Logger::TraceWarning(
        L"%s: Failed to read the node: \"%s\". ServerResponseParser::AssignJsonPropertyTo failed with error code 0x%08x. I"
         "gnore this node.",
        L"ServerResponseParser::ParseValueListNode",
        L"item",
        (unsigned int)v13,
        v18[0]);
LABEL_11:
      v6 = 0;
      goto LABEL_23;
    }
    v14 = ServerResponseParser::AssignJsonPropertyTo(
            (struct CJsonValue *)v12[2],
            L"value",
            (const unsigned __int16 **)&Block);
    if ( v14 < 0 )
    {
      Logger::TraceWarning(
        L"%s: Failed to read value for item: \"%s\". ServerResponseParser::AssignJsonPropertyTo failed with error code 0x%"
         "08x. Ignore this node.",
        L"ServerResponseParser::ParseValueListNode",
        v5,
        (unsigned int)v14,
        v18[0]);
      goto LABEL_11;
    }
    v18[0] = L"subcode";
    v18[1] = L"date";
    v19 = L"requestid";
    v21[0] = (char *)a2 + 32;
    v21[1] = (char *)a2 + 8;
    v21[2] = a2;
    if ( !*(_QWORD *)a2 || (v15 = 2, !**(_WORD **)a2) )
      v15 = 3;
    while ( 1 )
    {
      v22 = 0;
      v16 = StringCompare(v5, v18[v4], 0x30001u, &v22);
      v6 = v16;
      if ( v16 >= 0 )
      {
        if ( v22 )
        {
          v17 = (void **)v21[v4];
          free(*v17);
          *v17 = Block;
          v4 = 0;
          Block = 0;
LABEL_23:
          v12 = (__int64 *)*v12;
          goto LABEL_8;
        }
      }
      else
      {
        Logger::TraceWarning(
          L"%s: StringCompareIgnoreCase failed for item \"%s\". Error code 0x%08x. Ignore this error.",
          L"ServerResponseParser::ParseValueListNode",
          v5,
          (unsigned int)v16,
          v18[0],
          v18[1],
          v19);
        v6 = 0;
      }
      if ( ++v4 >= v15 )
      {
        v4 = 0;
        goto LABEL_23;
      }
    }
  }
  Logger::TraceError(
    L"%s: Node \"%s\" is not of type array. The type is %d.",
    L"ServerResponseParser::ParseValueListNode",
    L"values");
LABEL_3:
  v6 = -2145647639;
  v7 = v20[0];
LABEL_4:
  free(v5);
  free(Block);
  std::_List_node<dsreg::CJsonValue *,void *>::_Free_non_head<std::allocator<std::_List_node<dsreg::CJsonValue *,void *>>>(
    v8,
    v7);
  std::_Deallocate<16>(v7, 24);
  return v6;
}

```

## disassembly

```asm
0x18009b86c  mov     [rsp-38h+arg_8], rbx
0x18009b871  push    rbp
0x18009b872  push    rsi
0x18009b873  push    rdi
0x18009b874  push    r12
0x18009b876  push    r13
0x18009b878  push    r14
0x18009b87a  push    r15
0x18009b87c  mov     rbp, rsp
0x18009b87f  sub     rsp, 60h
0x18009b883  mov     r13, rdx
0x18009b886  mov     rbx, rcx
0x18009b889  xor     edi, edi
0x18009b88b  mov     r14d, edi
0x18009b88e  mov     [rbp+arg_18], rdi
0x18009b892  mov     [rbp+Block], rdi
0x18009b896  lea     rcx, [rbp+var_28]
0x18009b89a  call    ??0?$list@PEAVCJsonValue@dsreg@@V?$allocator@PEAVCJsonValue@dsreg@@@std@@@std@@QEAA@XZ; std::list<dsreg::CJsonValue *>::list<dsreg::CJsonValue *>(void)
0x18009b89f  nop
0x18009b8a0  mov     r9d, [rbx]
0x18009b8a3  cmp     r9d, 4
0x18009b8a7  jz      short loc_18009B90F
0x18009b8a9  lea     r8, aValues; "values"
0x18009b8b0  lea     rdx, aServerresponse_8; "ServerResponseParser::ParseValueListNod"...
0x18009b8b7  lea     rcx, aSNodeSIsNotOfT; "%s: Node \"%s\" is not of type array. T"...
0x18009b8be  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009b8c3  mov     esi, 801C03E9h
0x18009b8c8  mov     r15, [rbp+var_28]
0x18009b8cc  mov     rcx, r14; Block
0x18009b8cf  call    cs:__imp_free
0x18009b8d5  mov     rcx, [rbp+Block]; Block
0x18009b8d9  call    cs:__imp_free
0x18009b8df  nop
0x18009b8e0  mov     rdx, r15
0x18009b8e3  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAVCJsonValue@dsreg@@PEAX@std@@@std@@@?$_List_node@PEAVCJsonValue@dsreg@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAVCJsonValue@dsreg@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<dsreg::CJsonValue *,void *>::_Free_non_head<std::allocator<std::_List_node<dsreg::CJsonValue *,void *>>>(std::allocator<std::_List_node<dsreg::CJsonValue *,void *>> &,std::_List_node<dsreg::CJsonValue *,void *> *)
0x18009b8e8  mov     edx, 18h
0x18009b8ed  mov     rcx, r15
0x18009b8f0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009b8f5  mov     eax, esi
0x18009b8f7  mov     rbx, [rsp+60h+arg_8]
0x18009b8ff  add     rsp, 60h
0x18009b903  pop     r15
0x18009b905  pop     r14
0x18009b907  pop     r13
0x18009b909  pop     r12
0x18009b90b  pop     rdi
0x18009b90c  pop     rsi
0x18009b90d  pop     rbp
0x18009b90e  retn
0x18009b90f  mov     rdx, [rbx+48h]
0x18009b913  test    rdx, rdx
0x18009b916  jnz     short loc_18009B934
0x18009b918  lea     r8, aValues; "values"
0x18009b91f  lea     rdx, aServerresponse_8; "ServerResponseParser::ParseValueListNod"...
0x18009b926  lea     rcx, aSCjsonvalueGet; "%s: CJsonValue::GetJsonArray returns NU"...
0x18009b92d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009b932  jmp     short loc_18009B8C3
0x18009b934  mov     esi, edi
0x18009b936  xorps   xmm0, xmm0
0x18009b939  movdqu  xmmword ptr [rbp+var_40], xmm0
0x18009b93e  mov     rdx, [rdx]
0x18009b941  mov     r8, rdx
0x18009b944  mov     rdx, [rdx]
0x18009b947  lea     rcx, [rbp+var_40]
0x18009b94b  call    ??$_Construct_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCJsonValue@dsreg@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$list@PEAVCJsonValue@dsreg@@V?$allocator@PEAVCJsonValue@dsreg@@@std@@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCJsonValue@dsreg@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<dsreg::CJsonValue *>::_Construct_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<dsreg::CJsonValue *>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<dsreg::CJsonValue *>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<dsreg::CJsonValue *>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<dsreg::CJsonValue *>>,std::_Iterator_base0>)
0x18009b950  lea     rdx, [rbp+var_40]
0x18009b954  lea     rcx, [rbp+var_28]
0x18009b958  call    ??4?$list@PEAVCJsonValue@dsreg@@V?$allocator@PEAVCJsonValue@dsreg@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::list<dsreg::CJsonValue *>::operator=(std::list<dsreg::CJsonValue *> &&)
0x18009b95d  mov     rdx, [rbp+var_40]
0x18009b961  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAVCJsonValue@dsreg@@PEAX@std@@@std@@@?$_List_node@PEAVCJsonValue@dsreg@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAVCJsonValue@dsreg@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<dsreg::CJsonValue *,void *>::_Free_non_head<std::allocator<std::_List_node<dsreg::CJsonValue *,void *>>>(std::allocator<std::_List_node<dsreg::CJsonValue *,void *>> &,std::_List_node<dsreg::CJsonValue *,void *> *)
0x18009b966  mov     edx, 18h
0x18009b96b  mov     rcx, [rbp+var_40]
0x18009b96f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009b974  mov     r15, [rbp+var_28]
0x18009b978  mov     rbx, [r15]
0x18009b97b  cmp     rbx, r15
0x18009b97e  jz      loc_18009B8CC
0x18009b984  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18009b988  lea     rdx, aItem; "item"
0x18009b98f  mov     rcx, [rbx+10h]; struct CJsonValue *
0x18009b993  call    ?AssignJsonPropertyTo@ServerResponseParser@@CAJPEAVCJsonValue@dsreg@@PEBGAEAPEBG@Z; ServerResponseParser::AssignJsonPropertyTo(dsreg::CJsonValue *,ushort const *,ushort const * &)
0x18009b998  mov     r14, [rbp+arg_18]
0x18009b99c  test    eax, eax
0x18009b99e  jns     short loc_18009B9C4
0x18009b9a0  lea     r8, aItem; "item"
0x18009b9a7  lea     rcx, aSFailedToReadT; "%s: Failed to read the node: \"%s\". Se"...
0x18009b9ae  lea     rdx, aServerresponse_8; "ServerResponseParser::ParseValueListNod"...
0x18009b9b5  mov     r9d, eax
0x18009b9b8  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18009b9bd  mov     esi, edi
0x18009b9bf  jmp     loc_18009BAA5
0x18009b9c4  lea     r8, [rbp+Block]; unsigned __int16 **
0x18009b9c8  lea     rdx, aValue_0; "value"
0x18009b9cf  mov     rcx, [rbx+10h]; struct CJsonValue *
0x18009b9d3  call    ?AssignJsonPropertyTo@ServerResponseParser@@CAJPEAVCJsonValue@dsreg@@PEBGAEAPEBG@Z; ServerResponseParser::AssignJsonPropertyTo(dsreg::CJsonValue *,ushort const *,ushort const * &)
0x18009b9d8  test    eax, eax
0x18009b9da  jns     short loc_18009B9E8
0x18009b9dc  mov     r8, r14
0x18009b9df  lea     rcx, aSFailedToReadV; "%s: Failed to read value for item: \"%s"...
0x18009b9e6  jmp     short loc_18009B9AE
0x18009b9e8  lea     rax, aSubcode_0; "subcode"
0x18009b9ef  mov     [rbp+var_40], rax
0x18009b9f3  lea     rax, aDate; "date"
0x18009b9fa  mov     [rbp+var_40+8], rax
0x18009b9fe  lea     rax, aRequestid_0; "requestid"
0x18009ba05  mov     [rbp+var_30], rax
0x18009ba09  lea     rax, [r13+20h]
0x18009ba0d  mov     [rbp+var_18], rax
0x18009ba11  lea     rax, [r13+8]
0x18009ba15  mov     [rbp+var_10], rax
0x18009ba19  mov     [rbp+var_8], r13
0x18009ba1d  mov     rax, [r13+0]
0x18009ba21  test    rax, rax
0x18009ba24  jz      short loc_18009BA31
0x18009ba26  cmp     [rax], di
0x18009ba29  mov     r12d, 2
0x18009ba2f  jnz     short loc_18009BA37
0x18009ba31  mov     r12d, 3
0x18009ba37  mov     [rbp+arg_0], 0
0x18009ba3e  lea     r9, [rbp+arg_0]; int *
0x18009ba42  mov     r8d, 30001h; unsigned int
0x18009ba48  mov     rdx, [rbp+rdi*8+var_40]; unsigned __int16 *
0x18009ba4d  mov     rcx, r14; unsigned __int16 *
0x18009ba50  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18009ba55  mov     esi, eax
0x18009ba57  test    eax, eax
0x18009ba59  jns     short loc_18009BA78
0x18009ba5b  mov     r9d, eax
0x18009ba5e  mov     r8, r14
0x18009ba61  lea     rdx, aServerresponse_8; "ServerResponseParser::ParseValueListNod"...
0x18009ba68  lea     rcx, aSStringcompare; "%s: StringCompareIgnoreCase failed for "...
0x18009ba6f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18009ba74  xor     esi, esi
0x18009ba76  jmp     short loc_18009BA7E
0x18009ba78  cmp     [rbp+arg_0], 0
0x18009ba7c  jnz     short loc_18009BA8A
0x18009ba7e  inc     rdi
0x18009ba81  cmp     rdi, r12
0x18009ba84  jb      short loc_18009BA37
0x18009ba86  xor     edi, edi
0x18009ba88  jmp     short loc_18009BAA5
0x18009ba8a  mov     rdi, [rbp+rdi*8+var_18]
0x18009ba8f  mov     rcx, [rdi]; Block
0x18009ba92  call    cs:__imp_free
0x18009ba98  mov     rax, [rbp+Block]
0x18009ba9c  mov     [rdi], rax
0x18009ba9f  xor     edi, edi
0x18009baa1  mov     [rbp+Block], rdi
0x18009baa5  mov     rbx, [rbx]
0x18009baa8  jmp     loc_18009B97B
```
