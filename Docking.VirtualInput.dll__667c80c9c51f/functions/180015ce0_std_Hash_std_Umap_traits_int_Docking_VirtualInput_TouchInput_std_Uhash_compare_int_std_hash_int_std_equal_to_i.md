# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(int const &,unsigned __int64)

- ea: `0x180015ce0`
- end: `0x180015e22`
- name: `??$_Find_last@H@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@AEBH_K@Z`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015c80`
- `0x180016100`

## callees

- `0x18000b810`
- `0x1800159f0`
- `0x180015ce0`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rax
  _QWORD *v6; // [rsp+20h] [rbp-38h]
  _QWORD *v7; // [rsp+28h] [rbp-30h]
  __int64 v8; // [rsp+30h] [rbp-28h]
  _QWORD *v9; // [rsp+40h] [rbp-18h]

  v8 = a1[6] & a4;
  v6 = *(_QWORD **)(a1[3] + 16 * v8 + 8);
  v7 = (_QWORD *)a1[1];
  if ( v6 == v7 )
  {
    *a2 = v7;
    a2[1] = 0;
    return a2;
  }
  else
  {
    v9 = *(_QWORD **)(a1[3] + 16 * v8);
    while ( 1 )
    {
      v5 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v6 + 2);
      if ( !(unsigned __int8)std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(a1, a3, v5) )
      {
        *a2 = *v6;
        a2[1] = v6;
        return a2;
      }
      if ( v6 == v9 )
        break;
      v6 = (_QWORD *)v6[1];
    }
    *a2 = v6;
    a2[1] = 0;
    return a2;
  }
}

```

## disassembly

```asm
0x180015ce0  mov     [rsp+arg_18], r9
0x180015ce5  mov     [rsp+arg_10], r8
0x180015cea  mov     [rsp+arg_8], rdx
0x180015cef  mov     [rsp+arg_0], rcx
0x180015cf4  sub     rsp, 58h
0x180015cf8  mov     rax, [rsp+58h+arg_0]
0x180015cfd  mov     rax, [rax+30h]
0x180015d01  mov     rcx, [rsp+58h+arg_18]
0x180015d06  and     rcx, rax
0x180015d09  mov     rax, rcx
0x180015d0c  mov     [rsp+58h+var_28], rax
0x180015d11  mov     rax, [rsp+58h+var_28]
0x180015d16  shl     rax, 1
0x180015d19  mov     rcx, [rsp+58h+arg_0]
0x180015d1e  mov     rcx, [rcx+18h]
0x180015d22  mov     rax, [rcx+rax*8+8]
0x180015d27  mov     [rsp+58h+var_38], rax
0x180015d2c  mov     rax, [rsp+58h+arg_0]
0x180015d31  mov     rax, [rax+8]
0x180015d35  mov     [rsp+58h+var_30], rax
0x180015d3a  mov     rax, [rsp+58h+var_30]
0x180015d3f  cmp     [rsp+58h+var_38], rax
0x180015d44  jnz     short loc_180015D6A
0x180015d46  mov     rax, [rsp+58h+arg_8]
0x180015d4b  mov     rcx, [rsp+58h+var_30]
0x180015d50  mov     [rax], rcx
0x180015d53  mov     rax, [rsp+58h+arg_8]
0x180015d58  mov     qword ptr [rax+8], 0
0x180015d60  mov     rax, [rsp+58h+arg_8]
0x180015d65  jmp     loc_180015E1D
0x180015d6a  mov     rax, [rsp+58h+var_28]
0x180015d6f  shl     rax, 1
0x180015d72  mov     rcx, [rsp+58h+arg_0]
0x180015d77  mov     rcx, [rcx+18h]
0x180015d7b  mov     rax, [rcx+rax*8]
0x180015d7f  mov     [rsp+58h+var_18], rax
0x180015d84  mov     rax, [rsp+58h+arg_0]
0x180015d89  mov     [rsp+58h+var_20], rax
0x180015d8e  mov     rax, [rsp+58h+var_38]
0x180015d93  add     rax, 10h
0x180015d97  mov     rcx, rax
0x180015d9a  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180015d9f  mov     r8, rax
0x180015da2  mov     rdx, [rsp+58h+arg_10]
0x180015da7  mov     rcx, [rsp+58h+var_20]
0x180015dac  call    ??$?RHH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_NAEBH0@Z; std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(int const &,int const &)
0x180015db1  movzx   eax, al
0x180015db4  test    eax, eax
0x180015db6  jnz     short loc_180015DDD
0x180015db8  mov     rax, [rsp+58h+arg_8]
0x180015dbd  mov     rcx, [rsp+58h+var_38]
0x180015dc2  mov     rcx, [rcx]
0x180015dc5  mov     [rax], rcx
0x180015dc8  mov     rax, [rsp+58h+arg_8]
0x180015dcd  mov     rcx, [rsp+58h+var_38]
0x180015dd2  mov     [rax+8], rcx
0x180015dd6  mov     rax, [rsp+58h+arg_8]
0x180015ddb  jmp     short loc_180015E1D
0x180015ddd  mov     rax, [rsp+58h+var_18]
0x180015de2  cmp     [rsp+58h+var_38], rax
0x180015de7  jnz     short loc_180015E0A
0x180015de9  mov     rax, [rsp+58h+arg_8]
0x180015dee  mov     rcx, [rsp+58h+var_38]
0x180015df3  mov     [rax], rcx
0x180015df6  mov     rax, [rsp+58h+arg_8]
0x180015dfb  mov     qword ptr [rax+8], 0
0x180015e03  mov     rax, [rsp+58h+arg_8]
0x180015e08  jmp     short loc_180015E1D
0x180015e0a  mov     rax, [rsp+58h+var_38]
0x180015e0f  mov     rax, [rax+8]
0x180015e13  mov     [rsp+58h+var_38], rax
0x180015e18  jmp     loc_180015D84
0x180015e1d  add     rsp, 58h
0x180015e21  retn
```
