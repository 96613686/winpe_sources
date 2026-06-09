# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::insert(_EVENT_DESCRIPTOR const &)

- ea: `0x180018bb0`
- end: `0x180018cf3`
- name: `?insert@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@_N@2@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017b30`

## callees

- `0x18000ebf4`
- `0x180018bb0`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdx
  __int64 v6; // rsi
  __int64 *v7; // r10
  char v8; // r8
  __int64 *v9; // r9
  unsigned __int16 v10; // di
  __int64 v11; // rax
  unsigned __int8 v12; // al
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  __int64 i; // rcx
  unsigned __int8 v17; // cl
  __int64 *v18; // rax
  __int64 v20; // [rsp+40h] [rbp+8h] BYREF

  v5 = *(__int64 **)(a1 + 8);
  v6 = a1;
  v7 = v5;
  v8 = 1;
  v9 = (__int64 *)v5[1];
  if ( !*((_BYTE *)v9 + 41) )
  {
    v10 = *(_WORD *)a3;
    while ( 1 )
    {
      v7 = v9;
      if ( v10 < *((_WORD *)v9 + 12) )
        break;
      if ( v10 > *((_WORD *)v9 + 12) )
        goto LABEL_6;
      v12 = *((_BYTE *)v9 + 26);
      if ( *(_BYTE *)(a3 + 2) < v12 )
        break;
      if ( *(_BYTE *)(a3 + 2) > v12 )
        goto LABEL_6;
      v13 = v9[3];
      if ( *(_QWORD *)a3 < v13 )
        break;
      if ( *(_QWORD *)a3 > v13 )
      {
LABEL_6:
        v8 = 0;
      }
      else
      {
        v14 = v9[4];
        v8 = *(_QWORD *)(a3 + 8) < v14;
        if ( *(_QWORD *)(a3 + 8) < v14 )
          goto LABEL_17;
      }
      v9 = (__int64 *)v9[2];
LABEL_8:
      if ( *((_BYTE *)v9 + 41) )
        goto LABEL_9;
    }
    v8 = 1;
LABEL_17:
    v9 = (__int64 *)*v9;
    goto LABEL_8;
  }
LABEL_9:
  v11 = (__int64)v7;
  if ( v8 )
  {
    if ( v7 == (__int64 *)*v5 )
    {
      v8 = 1;
LABEL_38:
      v18 = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(
              a1,
              &v20,
              v8,
              v7,
              a3);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = *v18;
      return a2;
    }
    if ( *((_BYTE *)v7 + 41) )
    {
      v11 = v7[2];
    }
    else
    {
      v15 = *v7;
      if ( *(_BYTE *)(*v7 + 41) )
      {
        for ( i = v7[1]; !*(_BYTE *)(i + 41) && v11 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
          v11 = i;
        if ( !*(_BYTE *)(v11 + 41) )
          v11 = i;
      }
      else
      {
        do
        {
          v11 = v15;
          v15 = *(_QWORD *)(v15 + 16);
        }
        while ( !*(_BYTE *)(v15 + 41) );
      }
    }
  }
  if ( *(_WORD *)(v11 + 24) < *(_WORD *)a3
    || *(_WORD *)(v11 + 24) <= *(_WORD *)a3
    && ((v17 = *(_BYTE *)(a3 + 2), *(_BYTE *)(v11 + 26) < v17)
     || *(_BYTE *)(v11 + 26) <= v17
     && (*(_QWORD *)(v11 + 24) < *(_QWORD *)a3
      || *(_QWORD *)(v11 + 24) <= *(_QWORD *)a3 && *(_QWORD *)(v11 + 32) < *(_QWORD *)(a3 + 8))) )
  {
    a1 = v6;
    goto LABEL_38;
  }
  *(_QWORD *)a2 = v11;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180018bb0  mov     [rsp+arg_8], rbx
0x180018bb5  mov     [rsp+arg_10], rsi
0x180018bba  push    rdi
0x180018bbb  sub     rsp, 30h
0x180018bbf  mov     rbx, rdx
0x180018bc2  mov     r11, r8
0x180018bc5  mov     rdx, [rcx+8]
0x180018bc9  mov     rsi, rcx
0x180018bcc  mov     r10, rdx
0x180018bcf  mov     r8b, 1
0x180018bd2  mov     r9, [rdx+8]
0x180018bd6  cmp     byte ptr [r9+29h], 0
0x180018bdb  jnz     short loc_180018C00
0x180018bdd  movzx   edi, word ptr [r11]
0x180018be1  mov     r10, r9
0x180018be4  cmp     di, [r9+18h]
0x180018be9  jnb     short loc_180018BF0
0x180018beb  mov     r8b, 1
0x180018bee  jmp     short loc_180018C3D
0x180018bf0  jbe     short loc_180018C15
0x180018bf2  xor     r8b, r8b
0x180018bf5  mov     r9, [r9+10h]
0x180018bf9  cmp     byte ptr [r9+29h], 0
0x180018bfe  jz      short loc_180018BE1
0x180018c00  mov     rax, r10
0x180018c03  test    r8b, r8b
0x180018c06  jz      short loc_180018C87
0x180018c08  cmp     r10, [rdx]
0x180018c0b  jnz     short loc_180018C42
0x180018c0d  mov     r8b, 1
0x180018c10  jmp     loc_180018CC4
0x180018c15  mov     al, [r9+1Ah]
0x180018c19  cmp     [r11+2], al
0x180018c1d  jb      short loc_180018BEB
0x180018c1f  ja      short loc_180018BF2
0x180018c21  mov     rax, [r9+18h]
0x180018c25  cmp     [r11], rax
0x180018c28  jb      short loc_180018BEB
0x180018c2a  ja      short loc_180018BF2
0x180018c2c  mov     rax, [r9+20h]
0x180018c30  cmp     [r11+8], rax
0x180018c34  setb    r8b
0x180018c38  test    r8b, r8b
0x180018c3b  jz      short loc_180018BF5
0x180018c3d  mov     r9, [r9]
0x180018c40  jmp     short loc_180018BF9
0x180018c42  cmp     byte ptr [r10+29h], 0
0x180018c47  jz      short loc_180018C4F
0x180018c49  mov     rax, [r10+10h]
0x180018c4d  jmp     short loc_180018C87
0x180018c4f  mov     rcx, [r10]
0x180018c52  cmp     byte ptr [rcx+29h], 0
0x180018c56  jnz     short loc_180018C67
0x180018c58  mov     rax, rcx
0x180018c5b  mov     rcx, [rcx+10h]
0x180018c5f  cmp     byte ptr [rcx+29h], 0
0x180018c63  jz      short loc_180018C58
0x180018c65  jmp     short loc_180018C87
0x180018c67  mov     rcx, [r10+8]
0x180018c6b  jmp     short loc_180018C79
0x180018c6d  cmp     rax, [rcx]
0x180018c70  jnz     short loc_180018C7F
0x180018c72  mov     rax, rcx
0x180018c75  mov     rcx, [rcx+8]
0x180018c79  cmp     byte ptr [rcx+29h], 0
0x180018c7d  jz      short loc_180018C6D
0x180018c7f  cmp     byte ptr [rax+29h], 0
0x180018c83  cmovz   rax, rcx
0x180018c87  movzx   ecx, word ptr [r11]
0x180018c8b  cmp     [rax+18h], cx
0x180018c8f  jb      short loc_180018CC1
0x180018c91  ja      short loc_180018CB8
0x180018c93  mov     cl, [r11+2]
0x180018c97  cmp     [rax+1Ah], cl
0x180018c9a  jb      short loc_180018CC1
0x180018c9c  ja      short loc_180018CB8
0x180018c9e  mov     rcx, [r11]
0x180018ca1  cmp     [rax+18h], rcx
0x180018ca5  jb      short loc_180018CC1
0x180018ca7  ja      short loc_180018CB8
0x180018ca9  mov     rcx, [r11+8]
0x180018cad  cmp     [rax+20h], rcx
0x180018cb1  setb    cl
0x180018cb4  test    cl, cl
0x180018cb6  jnz     short loc_180018CC1
0x180018cb8  mov     [rbx], rax
0x180018cbb  mov     byte ptr [rbx+8], 0
0x180018cbf  jmp     short loc_180018CE0
0x180018cc1  mov     rcx, rsi
0x180018cc4  mov     r9, r10
0x180018cc7  mov     [rsp+38h+var_18], r11
0x180018ccc  lea     rdx, [rsp+38h+arg_0]
0x180018cd1  call    ?_Insert@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &)
0x180018cd6  mov     byte ptr [rbx+8], 1
0x180018cda  mov     rcx, [rax]
0x180018cdd  mov     [rbx], rcx
0x180018ce0  mov     rsi, [rsp+38h+arg_10]
0x180018ce5  mov     rax, rbx
0x180018ce8  mov     rbx, [rsp+38h+arg_8]
0x180018ced  add     rsp, 30h
0x180018cf1  pop     rdi
0x180018cf2  retn
```
