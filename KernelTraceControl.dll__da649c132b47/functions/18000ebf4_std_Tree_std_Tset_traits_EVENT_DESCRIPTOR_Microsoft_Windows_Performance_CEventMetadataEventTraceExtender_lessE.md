# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &)

- ea: `0x18000ebf4`
- end: `0x18000eee1`
- name: `?_Insert@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `749`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e058`
- `0x18000eee4`
- `0x180018bb0`

## callees

- `0x1800022e4`
- `0x18000ebf4`
- `0x18000fd3c`
- `0x180013178`
- `0x180026e30`
- `0x180026f66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(
        __int64 a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 i; // r8
  __int64 *v15; // rax
  __int64 *v16; // r10
  __int64 v17; // rcx
  __int64 *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // rax
  _BYTE v33[40]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-78h] BYREF

  if ( *(_QWORD *)(a1 + 16) >= 0xFFFFFFFFFFFFFFEuLL )
  {
    std::string::string(v33, "map/set<T> too long");
    std::length_error::length_error(pExceptionObject, v33);
    throw (std::length_error *)pExceptionObject;
  }
  v9 = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Buynode(
         -2,
         *(_QWORD *)(a1 + 8),
         (_DWORD)a4,
         *(_QWORD *)(a1 + 8),
         a5,
         0,
         -2);
  ++*(_QWORD *)(a1 + 16);
  v10 = *(__int64 **)(a1 + 8);
  if ( a4 == v10 )
  {
    v10[1] = v9;
    **(_QWORD **)(a1 + 8) = v9;
    v11 = *(_QWORD *)(a1 + 8);
LABEL_9:
    *(_QWORD *)(v11 + 16) = v9;
    goto LABEL_10;
  }
  if ( !a3 )
  {
    a4[2] = v9;
    v11 = *(_QWORD *)(a1 + 8);
    if ( a4 != *(__int64 **)(v11 + 16) )
      goto LABEL_10;
    goto LABEL_9;
  }
  *a4 = v9;
  v12 = *(__int64 **)(a1 + 8);
  if ( a4 == (__int64 *)*v12 )
    *v12 = v9;
LABEL_10:
  v13 = v9;
  for ( i = v9 + 8; !*(_BYTE *)(*(_QWORD *)(v13 + 8) + 40LL); i = v13 + 8 )
  {
    v15 = *(__int64 **)i;
    v16 = *(__int64 **)(*(_QWORD *)i + 8LL);
    v17 = *v16;
    if ( *(_QWORD *)i == *v16 )
    {
      v17 = v16[2];
      if ( *(_BYTE *)(v17 + 40) )
      {
        if ( v13 == v15[2] )
        {
          v13 = *(_QWORD *)i;
          v18 = (__int64 *)v15[2];
          v15[2] = *v18;
          if ( !*(_BYTE *)(*v18 + 41) )
            *(_QWORD *)(*v18 + 8) = v15;
          i = (__int64)(v15 + 1);
          v18[1] = v15[1];
          v19 = *(_QWORD *)(a1 + 8);
          if ( v13 == *(_QWORD *)(v19 + 8) )
          {
            *(_QWORD *)(v19 + 8) = v18;
          }
          else
          {
            v20 = *(_QWORD **)i;
            if ( v13 == **(_QWORD **)i )
              *v20 = v18;
            else
              v20[2] = v18;
          }
          *v18 = v13;
          *(_QWORD *)i = v18;
        }
        *(_BYTE *)(*(_QWORD *)i + 40LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 40LL) = 0;
        v21 = *(_QWORD **)(*(_QWORD *)i + 8LL);
        v22 = (_QWORD *)*v21;
        *v21 = *(_QWORD *)(*v21 + 16LL);
        v23 = v22[2];
        if ( !*(_BYTE *)(v23 + 41) )
          *(_QWORD *)(v23 + 8) = v21;
        v22[1] = v21[1];
        v24 = *(_QWORD *)(a1 + 8);
        if ( v21 == *(_QWORD **)(v24 + 8) )
        {
          *(_QWORD *)(v24 + 8) = v22;
        }
        else
        {
          v25 = (_QWORD *)v21[1];
          if ( v21 == (_QWORD *)v25[2] )
            v25[2] = v22;
          else
            *v25 = v22;
        }
        v22[2] = v21;
LABEL_49:
        v21[1] = v22;
        continue;
      }
    }
    else if ( *(_BYTE *)(v17 + 40) )
    {
      if ( v13 == *v15 )
      {
        v13 = *(_QWORD *)i;
        v26 = *v15;
        *v15 = *(_QWORD *)(*v15 + 16);
        v27 = *(_QWORD *)(v26 + 16);
        if ( !*(_BYTE *)(v27 + 41) )
          *(_QWORD *)(v27 + 8) = v13;
        i = v13 + 8;
        *(_QWORD *)(v26 + 8) = *(_QWORD *)(v13 + 8);
        v28 = *(_QWORD *)(a1 + 8);
        if ( v13 == *(_QWORD *)(v28 + 8) )
        {
          *(_QWORD *)(v28 + 8) = v26;
        }
        else
        {
          v29 = *(_QWORD **)i;
          if ( v13 == *(_QWORD *)(*(_QWORD *)i + 16LL) )
            v29[2] = v26;
          else
            *v29 = v26;
        }
        *(_QWORD *)(v26 + 16) = v13;
        *(_QWORD *)i = v26;
      }
      *(_BYTE *)(*(_QWORD *)i + 40LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 40LL) = 0;
      v21 = *(_QWORD **)(*(_QWORD *)i + 8LL);
      v22 = (_QWORD *)v21[2];
      v21[2] = *v22;
      if ( !*(_BYTE *)(*v22 + 41LL) )
        *(_QWORD *)(*v22 + 8LL) = v21;
      v22[1] = v21[1];
      v30 = *(_QWORD *)(a1 + 8);
      if ( v21 == *(_QWORD **)(v30 + 8) )
      {
        *(_QWORD *)(v30 + 8) = v22;
      }
      else
      {
        v31 = (_QWORD *)v21[1];
        if ( v21 == (_QWORD *)*v31 )
          *v31 = v22;
        else
          v31[2] = v22;
      }
      *v22 = v21;
      goto LABEL_49;
    }
    *((_BYTE *)v15 + 40) = 1;
    *(_BYTE *)(v17 + 40) = 1;
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 40LL) = 0;
    v13 = *(_QWORD *)(*(_QWORD *)i + 8LL);
  }
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 40LL) = 1;
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x18000ebf4  push    rbx
0x18000ebf6  push    rbp
0x18000ebf7  push    rsi
0x18000ebf8  push    rdi
0x18000ebf9  push    r14
0x18000ebfb  sub     rsp, 0B0h
0x18000ec02  mov     [rsp+0D8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18000ec0b  mov     rax, cs:__security_cookie
0x18000ec12  xor     rax, rsp
0x18000ec15  mov     [rsp+0D8h+var_38], rax
0x18000ec1d  mov     rdi, r9
0x18000ec20  mov     sil, r8b
0x18000ec23  mov     r14, rdx
0x18000ec26  mov     rbx, rcx
0x18000ec29  mov     rax, [rsp+0D8h+arg_20]
0x18000ec31  mov     rcx, 0FFFFFFFFFFFFFFEh
0x18000ec3b  cmp     [rbx+10h], rcx
0x18000ec3f  jb      short loc_18000EC74
0x18000ec41  lea     rdx, aMapSetTTooLong; "map/set<T> too long"
0x18000ec48  lea     rcx, [rsp+0D8h+var_A0]
0x18000ec4d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18000ec52  nop
0x18000ec53  lea     rdx, [rsp+0D8h+var_A0]
0x18000ec58  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18000ec5d  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x18000ec62  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x18000ec69  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000ec6e  call    _CxxThrowException_0
0x18000ec74  mov     rdx, [rbx+8]
0x18000ec78  xor     ebp, ebp
0x18000ec7a  mov     [rsp+0D8h+var_B0], bpl
0x18000ec7f  mov     [rsp+0D8h+var_B8], rax
0x18000ec84  mov     r9, rdx
0x18000ec87  mov     r8, rdi
0x18000ec8a  call    ?_Buynode@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@00AEBU_EVENT_DESCRIPTOR@@D@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Buynode(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &,char)
0x18000ec8f  mov     r9, rax
0x18000ec92  inc     qword ptr [rbx+10h]
0x18000ec96  mov     rax, [rbx+8]
0x18000ec9a  cmp     rdi, rax
0x18000ec9d  jnz     short loc_18000ECB0
0x18000ec9f  mov     [rax+8], r9
0x18000eca3  mov     rax, [rbx+8]
0x18000eca7  mov     [rax], r9
0x18000ecaa  mov     rax, [rbx+8]
0x18000ecae  jmp     short loc_18000ECD4
0x18000ecb0  test    sil, sil
0x18000ecb3  jz      short loc_18000ECC6
0x18000ecb5  mov     [rdi], r9
0x18000ecb8  mov     rax, [rbx+8]
0x18000ecbc  cmp     rdi, [rax]
0x18000ecbf  jnz     short loc_18000ECD8
0x18000ecc1  mov     [rax], r9
0x18000ecc4  jmp     short loc_18000ECD8
0x18000ecc6  mov     [rdi+10h], r9
0x18000ecca  mov     rax, [rbx+8]
0x18000ecce  cmp     rdi, [rax+10h]
0x18000ecd2  jnz     short loc_18000ECD8
0x18000ecd4  mov     [rax+10h], r9
0x18000ecd8  mov     rdx, r9
0x18000ecdb  lea     r8, [r9+8]
0x18000ecdf  mov     rax, [r8]
0x18000ece2  cmp     [rax+28h], bpl
0x18000ece6  jnz     loc_18000EEB1
0x18000ecec  mov     rax, [r8]
0x18000ecef  mov     r10, [rax+8]
0x18000ecf3  mov     rcx, [r10]
0x18000ecf6  cmp     rax, rcx
0x18000ecf9  jnz     loc_18000EDC5
0x18000ecff  mov     rcx, [r10+10h]
0x18000ed03  cmp     [rcx+28h], bpl
0x18000ed07  jz      loc_18000EDCB
0x18000ed0d  cmp     rdx, [rax+10h]
0x18000ed11  jnz     short loc_18000ED60
0x18000ed13  mov     rdx, rax
0x18000ed16  mov     rcx, [rax+10h]
0x18000ed1a  mov     rax, [rcx]
0x18000ed1d  mov     [rdx+10h], rax
0x18000ed21  mov     rax, [rcx]
0x18000ed24  cmp     [rax+29h], bpl
0x18000ed28  jnz     short loc_18000ED2E
0x18000ed2a  mov     [rax+8], rdx
0x18000ed2e  lea     r8, [rdx+8]
0x18000ed32  mov     rax, [r8]
0x18000ed35  mov     [rcx+8], rax
0x18000ed39  mov     rax, [rbx+8]
0x18000ed3d  cmp     rdx, [rax+8]
0x18000ed41  jnz     short loc_18000ED49
0x18000ed43  mov     [rax+8], rcx
0x18000ed47  jmp     short loc_18000ED5A
0x18000ed49  mov     rax, [r8]
0x18000ed4c  cmp     rdx, [rax]
0x18000ed4f  jnz     short loc_18000ED56
0x18000ed51  mov     [rax], rcx
0x18000ed54  jmp     short loc_18000ED5A
0x18000ed56  mov     [rax+10h], rcx
0x18000ed5a  mov     [rcx], rdx
0x18000ed5d  mov     [r8], rcx
0x18000ed60  mov     rax, [r8]
0x18000ed63  mov     byte ptr [rax+28h], 1
0x18000ed67  mov     rax, [r8]
0x18000ed6a  mov     rcx, [rax+8]
0x18000ed6e  mov     [rcx+28h], bpl
0x18000ed72  mov     rax, [r8]
0x18000ed75  mov     rcx, [rax+8]
0x18000ed79  mov     r8, [rcx]
0x18000ed7c  mov     rax, [r8+10h]
0x18000ed80  mov     [rcx], rax
0x18000ed83  mov     rax, [r8+10h]
0x18000ed87  cmp     [rax+29h], bpl
0x18000ed8b  jnz     short loc_18000ED91
0x18000ed8d  mov     [rax+8], rcx
0x18000ed91  mov     rax, [rcx+8]
0x18000ed95  mov     [r8+8], rax
0x18000ed99  mov     rax, [rbx+8]
0x18000ed9d  cmp     rcx, [rax+8]
0x18000eda1  jnz     short loc_18000EDA9
0x18000eda3  mov     [rax+8], r8
0x18000eda7  jmp     short loc_18000EDBC
0x18000eda9  mov     rax, [rcx+8]
0x18000edad  cmp     rcx, [rax+10h]
0x18000edb1  jnz     short loc_18000EDB9
0x18000edb3  mov     [rax+10h], r8
0x18000edb7  jmp     short loc_18000EDBC
0x18000edb9  mov     [rax], r8
0x18000edbc  mov     [r8+10h], rcx
0x18000edc0  jmp     loc_18000EE9C
0x18000edc5  cmp     [rcx+28h], bpl
0x18000edc9  jnz     short loc_18000EDEA
0x18000edcb  mov     byte ptr [rax+28h], 1
0x18000edcf  mov     byte ptr [rcx+28h], 1
0x18000edd3  mov     rax, [r8]
0x18000edd6  mov     rcx, [rax+8]
0x18000edda  mov     [rcx+28h], bpl
0x18000edde  mov     rax, [r8]
0x18000ede1  mov     rdx, [rax+8]
0x18000ede5  jmp     loc_18000EEA0
0x18000edea  cmp     rdx, [rax]
0x18000eded  jnz     short loc_18000EE3E
0x18000edef  mov     rdx, rax
0x18000edf2  mov     rcx, [rax]
0x18000edf5  mov     rax, [rcx+10h]
0x18000edf9  mov     [rdx], rax
0x18000edfc  mov     rax, [rcx+10h]
0x18000ee00  cmp     [rax+29h], bpl
0x18000ee04  jnz     short loc_18000EE0A
0x18000ee06  mov     [rax+8], rdx
0x18000ee0a  lea     r8, [rdx+8]
0x18000ee0e  mov     rax, [r8]
0x18000ee11  mov     [rcx+8], rax
0x18000ee15  mov     rax, [rbx+8]
0x18000ee19  cmp     rdx, [rax+8]
0x18000ee1d  jnz     short loc_18000EE25
0x18000ee1f  mov     [rax+8], rcx
0x18000ee23  jmp     short loc_18000EE37
0x18000ee25  mov     rax, [r8]
0x18000ee28  cmp     rdx, [rax+10h]
0x18000ee2c  jnz     short loc_18000EE34
0x18000ee2e  mov     [rax+10h], rcx
0x18000ee32  jmp     short loc_18000EE37
0x18000ee34  mov     [rax], rcx
0x18000ee37  mov     [rcx+10h], rdx
0x18000ee3b  mov     [r8], rcx
0x18000ee3e  mov     rax, [r8]
0x18000ee41  mov     byte ptr [rax+28h], 1
0x18000ee45  mov     rax, [r8]
0x18000ee48  mov     rcx, [rax+8]
0x18000ee4c  mov     [rcx+28h], bpl
0x18000ee50  mov     rax, [r8]
0x18000ee53  mov     rcx, [rax+8]
0x18000ee57  mov     r8, [rcx+10h]
0x18000ee5b  mov     rax, [r8]
0x18000ee5e  mov     [rcx+10h], rax
0x18000ee62  mov     rax, [r8]
0x18000ee65  cmp     [rax+29h], bpl
0x18000ee69  jnz     short loc_18000EE6F
0x18000ee6b  mov     [rax+8], rcx
0x18000ee6f  mov     rax, [rcx+8]
0x18000ee73  mov     [r8+8], rax
0x18000ee77  mov     rax, [rbx+8]
0x18000ee7b  cmp     rcx, [rax+8]
0x18000ee7f  jnz     short loc_18000EE87
0x18000ee81  mov     [rax+8], r8
0x18000ee85  jmp     short loc_18000EE99
0x18000ee87  mov     rax, [rcx+8]
0x18000ee8b  cmp     rcx, [rax]
0x18000ee8e  jnz     short loc_18000EE95
0x18000ee90  mov     [rax], r8
0x18000ee93  jmp     short loc_18000EE99
0x18000ee95  mov     [rax+10h], r8
0x18000ee99  mov     [r8], rcx
0x18000ee9c  mov     [rcx+8], r8
0x18000eea0  lea     r8, [rdx+8]
0x18000eea4  mov     rcx, [r8]
0x18000eea7  cmp     [rcx+28h], bpl
0x18000eeab  jz      loc_18000ECEC
0x18000eeb1  mov     rcx, [rbx+8]
0x18000eeb5  mov     rdx, [rcx+8]
0x18000eeb9  mov     byte ptr [rdx+28h], 1
0x18000eebd  mov     [r14], r9
0x18000eec0  mov     rax, r14
0x18000eec3  mov     rcx, [rsp+0D8h+var_38]
0x18000eecb  xor     rcx, rsp; StackCookie
0x18000eece  call    __security_check_cookie
0x18000eed3  add     rsp, 0B0h
0x18000eeda  pop     r14
0x18000eedc  pop     rdi
0x18000eedd  pop     rsi
0x18000eede  pop     rbp
0x18000eedf  pop     rbx
0x18000eee0  retn
```
