# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)

- ea: `0x180018f70`
- end: `0x1800190bf`
- name: `?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@_KQEAU32@1@Z`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016100`

## callees

- `0x180015b30`
- `0x180018f70`

## pseudocode

```c
__int64 std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Insert_new_node_before(
        _QWORD *a1,
        __int64 a2,
        ...)
{
  _QWORD *v3; // [rsp+20h] [rbp-38h]
  _QWORD *v4; // [rsp+28h] [rbp-30h] BYREF
  _QWORD *v5; // [rsp+30h] [rbp-28h]
  __int64 v6; // [rsp+38h] [rbp-20h]
  __int64 v7; // [rsp+40h] [rbp-18h]
  __int64 v8; // [rsp+48h] [rbp-10h]
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  va_list va; // [rsp+70h] [rbp+18h]
  __int64 v13; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, _QWORD);
  v4 = *(_QWORD **)(v11 + 8);
  ++a1[2];
  std::_Construct_in_place<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const &>(
    v13,
    (__int64 *)va);
  std::_Construct_in_place<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const &>(
    v13 + 8,
    &v4);
  *v4 = v13;
  *(_QWORD *)(v11 + 8) = v13;
  v8 = a1[1];
  v7 = a1[3];
  v6 = a1[6] & a2;
  v3 = (_QWORD *)(v7 + 16 * v6);
  v5 = v3 + 1;
  if ( *v3 == v8 )
  {
    *v3 = v13;
    *v5 = v13;
  }
  else if ( *v3 == v11 )
  {
    *v3 = v13;
  }
  else if ( (_QWORD *)*v5 == v4 )
  {
    *v5 = v13;
  }
  return v13;
}

```

## disassembly

```asm
0x180018f70  mov     [rsp+arg_18], r9
0x180018f75  mov     [rsp+arg_10], r8
0x180018f7a  mov     [rsp+arg_8], rdx
0x180018f7f  mov     [rsp+arg_0], rcx
0x180018f84  sub     rsp, 58h
0x180018f88  mov     rax, [rsp+58h+arg_10]
0x180018f8d  mov     rax, [rax+8]
0x180018f91  mov     [rsp+58h+var_30], rax
0x180018f96  mov     rax, [rsp+58h+arg_0]
0x180018f9b  mov     rax, [rax+10h]
0x180018f9f  inc     rax
0x180018fa2  mov     rcx, [rsp+58h+arg_0]
0x180018fa7  mov     [rcx+10h], rax
0x180018fab  mov     rax, [rsp+58h+arg_18]
0x180018fb0  lea     rdx, [rsp+58h+arg_10]
0x180018fb5  mov     rcx, rax
0x180018fb8  call    ??$_Construct_in_place@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@AEBQEAU12@@std@@YAXAEAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@0@AEBQEAU10@@Z; std::_Construct_in_place<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const &>(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * &,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const &)
0x180018fbd  mov     rax, [rsp+58h+arg_18]
0x180018fc2  add     rax, 8
0x180018fc6  lea     rdx, [rsp+58h+var_30]
0x180018fcb  mov     rcx, rax
0x180018fce  call    ??$_Construct_in_place@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@AEBQEAU12@@std@@YAXAEAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@0@AEBQEAU10@@Z; std::_Construct_in_place<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const &>(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * &,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const &)
0x180018fd3  mov     rax, [rsp+58h+var_30]
0x180018fd8  mov     rcx, [rsp+58h+arg_18]
0x180018fdd  mov     [rax], rcx
0x180018fe0  mov     rax, [rsp+58h+arg_10]
0x180018fe5  mov     rcx, [rsp+58h+arg_18]
0x180018fea  mov     [rax+8], rcx
0x180018fee  mov     rax, [rsp+58h+arg_0]
0x180018ff3  mov     rax, [rax+8]
0x180018ff7  mov     [rsp+58h+var_10], rax
0x180018ffc  mov     rax, [rsp+58h+arg_0]
0x180019001  mov     rax, [rax+18h]
0x180019005  mov     [rsp+58h+var_18], rax
0x18001900a  mov     rax, [rsp+58h+arg_0]
0x18001900f  mov     rax, [rax+30h]
0x180019013  mov     rcx, [rsp+58h+arg_8]
0x180019018  and     rcx, rax
0x18001901b  mov     rax, rcx
0x18001901e  mov     [rsp+58h+var_20], rax
0x180019023  mov     rax, [rsp+58h+var_20]
0x180019028  shl     rax, 1
0x18001902b  mov     rcx, [rsp+58h+var_18]
0x180019030  lea     rax, [rcx+rax*8]
0x180019034  mov     [rsp+58h+var_38], rax
0x180019039  mov     rax, [rsp+58h+var_20]
0x18001903e  shl     rax, 1
0x180019041  mov     rcx, [rsp+58h+var_18]
0x180019046  lea     rax, [rcx+rax*8+8]
0x18001904b  mov     [rsp+58h+var_28], rax
0x180019050  mov     rax, [rsp+58h+var_38]
0x180019055  mov     rcx, [rsp+58h+var_10]
0x18001905a  cmp     [rax], rcx
0x18001905d  jnz     short loc_18001907B
0x18001905f  mov     rax, [rsp+58h+var_38]
0x180019064  mov     rcx, [rsp+58h+arg_18]
0x180019069  mov     [rax], rcx
0x18001906c  mov     rax, [rsp+58h+var_28]
0x180019071  mov     rcx, [rsp+58h+arg_18]
0x180019076  mov     [rax], rcx
0x180019079  jmp     short loc_1800190B5
0x18001907b  mov     rax, [rsp+58h+var_38]
0x180019080  mov     rcx, [rsp+58h+arg_10]
0x180019085  cmp     [rax], rcx
0x180019088  jnz     short loc_180019099
0x18001908a  mov     rax, [rsp+58h+var_38]
0x18001908f  mov     rcx, [rsp+58h+arg_18]
0x180019094  mov     [rax], rcx
0x180019097  jmp     short loc_1800190B5
0x180019099  mov     rax, [rsp+58h+var_28]
0x18001909e  mov     rcx, [rsp+58h+var_30]
0x1800190a3  cmp     [rax], rcx
0x1800190a6  jnz     short loc_1800190B5
0x1800190a8  mov     rax, [rsp+58h+var_28]
0x1800190ad  mov     rcx, [rsp+58h+arg_18]
0x1800190b2  mov     [rax], rcx
0x1800190b5  mov     rax, [rsp+58h+arg_18]
0x1800190ba  add     rsp, 58h
0x1800190be  retn
```
