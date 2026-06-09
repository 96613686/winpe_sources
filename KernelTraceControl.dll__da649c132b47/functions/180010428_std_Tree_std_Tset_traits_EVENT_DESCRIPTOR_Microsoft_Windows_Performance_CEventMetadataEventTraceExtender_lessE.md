# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *)

- ea: `0x180010428`
- end: `0x1800104b2`
- name: `?_Copy@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@0@Z`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000eff0`
- `0x180010428`

## callees

- `0x18000fd3c`
- `0x180010428`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(
        __int64 a1,
        __int64 a2,
        int a3)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  char v8; // [rsp+28h] [rbp-30h]

  v4 = *(_QWORD **)(a1 + 8);
  if ( !*(_BYTE *)(a2 + 41) )
  {
    v8 = *(_BYTE *)(a2 + 40);
    v5 = (_QWORD *)std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Buynode(
                     a1,
                     (_DWORD)v4,
                     a3,
                     (_DWORD)v4,
                     a2 + 24,
                     v8,
                     -2);
    v6 = v5;
    if ( *((_BYTE *)v4 + 41) )
      v4 = v5;
    try
    {
      *v5 = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(
              a1,
              *(_QWORD *)a2,
              v5);
      v6[2] = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(
                a1,
                *(_QWORD *)(a2 + 16),
                v6);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Erase(
        a1,
        v4);
      throw;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180010428  mov     r11, rsp
0x18001042b  mov     [r11+10h], rdx
0x18001042f  mov     [r11+8], rcx
0x180010433  push    rbx
0x180010434  push    rsi
0x180010435  push    rdi
0x180010436  sub     rsp, 40h
0x18001043a  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x180010442  mov     rsi, rcx
0x180010445  mov     rbx, [rcx+8]
0x180010449  cmp     byte ptr [rdx+29h], 0
0x18001044d  jnz     short loc_1800104A7
0x18001044f  lea     r9, [rdx+18h]
0x180010453  mov     al, [rdx+28h]
0x180010456  mov     [rsp+58h+var_30], al
0x18001045a  mov     [r11-38h], r9
0x18001045e  mov     r9, rbx
0x180010461  mov     rdx, rbx
0x180010464  call    ?_Buynode@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@00AEBU_EVENT_DESCRIPTOR@@D@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Buynode(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &,char)
0x180010469  mov     rdi, rax
0x18001046c  cmp     byte ptr [rbx+29h], 0
0x180010470  cmovnz  rbx, rax
0x180010474  mov     [rsp+58h+arg_18], rbx
0x180010479  mov     r8, rax
0x18001047c  mov     rdx, [rsp+58h+arg_8]
0x180010481  mov     rdx, [rdx]
0x180010484  mov     rcx, rsi
0x180010487  call    ?_Copy@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *)
0x18001048c  mov     [rdi], rax
0x18001048f  mov     r8, rdi
0x180010492  mov     rax, [rsp+58h+arg_8]
0x180010497  mov     rdx, [rax+10h]
0x18001049b  mov     rcx, rsi
0x18001049e  call    ?_Copy@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *)
0x1800104a3  mov     [rdi+10h], rax
0x1800104a7  mov     rax, rbx
0x1800104aa  add     rsp, 40h
0x1800104ae  pop     rdi
0x1800104af  pop     rsi
0x1800104b0  pop     rbx
0x1800104b1  retn
```
