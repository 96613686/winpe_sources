# std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *> *>,std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *> * const)

- ea: `0x18000d6fc`
- end: `0x18000d925`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000bdd0`
- `0x180015728`
- `0x180015888`
- `0x18001b9b4`

## callees

- `0x18000d6fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
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
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x18000d6fc  mov     [rsp+arg_0], rbx
0x18000d701  inc     qword ptr [rcx+8]
0x18000d705  mov     r11, rcx
0x18000d708  mov     r10, [rcx]
0x18000d70b  mov     rax, [rdx]
0x18000d70e  mov     [r8+8], rax
0x18000d712  cmp     rax, r10
0x18000d715  jnz     short loc_18000D72C
0x18000d717  mov     [r10], r8
0x18000d71a  mov     [r10+8], r8
0x18000d71e  mov     [r10+10h], r8
0x18000d722  mov     byte ptr [r8+18h], 1
0x18000d727  jmp     loc_18000D91C
0x18000d72c  xor     ebx, ebx
0x18000d72e  cmp     [rdx+8], ebx
0x18000d731  jnz     short loc_18000D743
0x18000d733  mov     [rax+10h], r8
0x18000d737  cmp     rax, [r10+10h]
0x18000d73b  jnz     short loc_18000D74E
0x18000d73d  mov     [r10+10h], r8
0x18000d741  jmp     short loc_18000D74E
0x18000d743  mov     [rax], r8
0x18000d746  cmp     rax, [r10]
0x18000d749  jnz     short loc_18000D74E
0x18000d74b  mov     [r10], r8
0x18000d74e  mov     rax, [r8+8]
0x18000d752  mov     rdx, r8
0x18000d755  jmp     loc_18000D90B
0x18000d75a  mov     rcx, [rdx+8]
0x18000d75e  mov     r9, [rcx+8]
0x18000d762  mov     rax, [r9]
0x18000d765  cmp     rcx, rax
0x18000d768  jnz     loc_18000D82F
0x18000d76e  mov     rax, [r9+10h]
0x18000d772  cmp     [rax+18h], bl
0x18000d775  jz      loc_18000D834
0x18000d77b  mov     r9, [rcx+10h]
0x18000d77f  cmp     rdx, r9
0x18000d782  jnz     short loc_18000D7CA
0x18000d784  mov     rax, [r9]
0x18000d787  mov     rdx, rcx
0x18000d78a  mov     [rcx+10h], rax
0x18000d78e  mov     rax, [r9]
0x18000d791  cmp     [rax+19h], bl
0x18000d794  jnz     short loc_18000D79A
0x18000d796  mov     [rax+8], rcx
0x18000d79a  mov     rax, [rcx+8]
0x18000d79e  mov     [r9+8], rax
0x18000d7a2  mov     rax, [r11]
0x18000d7a5  cmp     rcx, [rax+8]
0x18000d7a9  jnz     short loc_18000D7B1
0x18000d7ab  mov     [rax+8], r9
0x18000d7af  jmp     short loc_18000D7C3
0x18000d7b1  mov     rax, [rcx+8]
0x18000d7b5  cmp     rcx, [rax]
0x18000d7b8  jnz     short loc_18000D7BF
0x18000d7ba  mov     [rax], r9
0x18000d7bd  jmp     short loc_18000D7C3
0x18000d7bf  mov     [rax+10h], r9
0x18000d7c3  mov     [r9], rcx
0x18000d7c6  mov     [rcx+8], r9
0x18000d7ca  mov     rax, [rdx+8]
0x18000d7ce  mov     byte ptr [rax+18h], 1
0x18000d7d2  mov     rax, [rdx+8]
0x18000d7d6  mov     rcx, [rax+8]
0x18000d7da  mov     [rcx+18h], bl
0x18000d7dd  mov     rax, [rdx+8]
0x18000d7e1  mov     rcx, [rax+8]
0x18000d7e5  mov     r9, [rcx]
0x18000d7e8  mov     rax, [r9+10h]
0x18000d7ec  mov     [rcx], rax
0x18000d7ef  mov     rax, [r9+10h]
0x18000d7f3  cmp     [rax+19h], bl
0x18000d7f6  jnz     short loc_18000D7FC
0x18000d7f8  mov     [rax+8], rcx
0x18000d7fc  mov     rax, [rcx+8]
0x18000d800  mov     [r9+8], rax
0x18000d804  mov     rax, [r11]
0x18000d807  cmp     rcx, [rax+8]
0x18000d80b  jnz     short loc_18000D813
0x18000d80d  mov     [rax+8], r9
0x18000d811  jmp     short loc_18000D826
0x18000d813  mov     rax, [rcx+8]
0x18000d817  cmp     rcx, [rax+10h]
0x18000d81b  jnz     short loc_18000D823
0x18000d81d  mov     [rax+10h], r9
0x18000d821  jmp     short loc_18000D826
0x18000d823  mov     [rax], r9
0x18000d826  mov     [r9+10h], rcx
0x18000d82a  jmp     loc_18000D903
0x18000d82f  cmp     [rax+18h], bl
0x18000d832  jnz     short loc_18000D854
0x18000d834  mov     byte ptr [rcx+18h], 1
0x18000d838  mov     byte ptr [rax+18h], 1
0x18000d83c  mov     rax, [rdx+8]
0x18000d840  mov     rcx, [rax+8]
0x18000d844  mov     [rcx+18h], bl
0x18000d847  mov     rax, [rdx+8]
0x18000d84b  mov     rdx, [rax+8]
0x18000d84f  jmp     loc_18000D907
0x18000d854  mov     r9, [rcx]
0x18000d857  cmp     rdx, r9
0x18000d85a  jnz     short loc_18000D8A5
0x18000d85c  mov     rax, [r9+10h]
0x18000d860  mov     rdx, rcx
0x18000d863  mov     [rcx], rax
0x18000d866  mov     rax, [r9+10h]
0x18000d86a  cmp     [rax+19h], bl
0x18000d86d  jnz     short loc_18000D873
0x18000d86f  mov     [rax+8], rcx
0x18000d873  mov     rax, [rcx+8]
0x18000d877  mov     [r9+8], rax
0x18000d87b  mov     rax, [r11]
0x18000d87e  cmp     rcx, [rax+8]
0x18000d882  jnz     short loc_18000D88A
0x18000d884  mov     [rax+8], r9
0x18000d888  jmp     short loc_18000D89D
0x18000d88a  mov     rax, [rcx+8]
0x18000d88e  cmp     rcx, [rax+10h]
0x18000d892  jnz     short loc_18000D89A
0x18000d894  mov     [rax+10h], r9
0x18000d898  jmp     short loc_18000D89D
0x18000d89a  mov     [rax], r9
0x18000d89d  mov     [r9+10h], rcx
0x18000d8a1  mov     [rcx+8], r9
0x18000d8a5  mov     rax, [rdx+8]
0x18000d8a9  mov     byte ptr [rax+18h], 1
0x18000d8ad  mov     rax, [rdx+8]
0x18000d8b1  mov     rcx, [rax+8]
0x18000d8b5  mov     [rcx+18h], bl
0x18000d8b8  mov     rax, [rdx+8]
0x18000d8bc  mov     rcx, [rax+8]
0x18000d8c0  mov     r9, [rcx+10h]
0x18000d8c4  mov     rax, [r9]
0x18000d8c7  mov     [rcx+10h], rax
0x18000d8cb  mov     rax, [r9]
0x18000d8ce  cmp     [rax+19h], bl
0x18000d8d1  jnz     short loc_18000D8D7
0x18000d8d3  mov     [rax+8], rcx
0x18000d8d7  mov     rax, [rcx+8]
0x18000d8db  mov     [r9+8], rax
0x18000d8df  mov     rax, [r11]
0x18000d8e2  cmp     rcx, [rax+8]
0x18000d8e6  jnz     short loc_18000D8EE
0x18000d8e8  mov     [rax+8], r9
0x18000d8ec  jmp     short loc_18000D900
0x18000d8ee  mov     rax, [rcx+8]
0x18000d8f2  cmp     rcx, [rax]
0x18000d8f5  jnz     short loc_18000D8FC
0x18000d8f7  mov     [rax], r9
0x18000d8fa  jmp     short loc_18000D900
0x18000d8fc  mov     [rax+10h], r9
0x18000d900  mov     [r9], rcx
0x18000d903  mov     [rcx+8], r9
0x18000d907  mov     rax, [rdx+8]
0x18000d90b  cmp     [rax+18h], bl
0x18000d90e  jz      loc_18000D75A
0x18000d914  mov     rax, [r10+8]
0x18000d918  mov     byte ptr [rax+18h], 1
0x18000d91c  mov     rbx, [rsp+arg_0]
0x18000d921  mov     rax, r8
0x18000d924  retn
```
