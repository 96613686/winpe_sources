# std::map<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,0>(std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>> &&)

- ea: `0x18000e91c`
- end: `0x18000ea33`
- name: `??$insert@U?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@$0A@@?$map@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@1@@Z`
- size: `279`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f9f0`

## callees

- `0x18000214c`
- `0x18000e91c`
- `0x180011b20`
- `0x180011d78`

## pseudocode

```c
__int64 __fastcall std::map<unsigned __int64,std::unique_ptr<IPxlatInterface>>::insert<std::pair<unsigned __int64,std::unique_ptr<IPxlatInterface>>,0>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v6; // r15
  __int64 v7; // rax
  unsigned int v8; // ebp
  __int64 inserted; // r9
  char v10; // di
  __int64 *v11; // r12
  __int64 *v12; // r8
  __int64 v13; // rax
  __int64 *v15; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+28h] [rbp-30h]

  v6 = *a1;
  v7 = *(_QWORD *)(*a1 + 8);
  v8 = 0;
  inserted = *a1;
  v10 = 1;
  if ( *(_BYTE *)(v7 + 25) )
  {
    v11 = *(__int64 **)(*a1 + 8);
  }
  else
  {
    do
    {
      v11 = (__int64 *)v7;
      if ( *(_QWORD *)(v7 + 32) >= (unsigned __int64)*a3 )
      {
        v8 = 1;
        inserted = v7;
        v7 = *(_QWORD *)v7;
      }
      else
      {
        v8 = 0;
        v7 = *(_QWORD *)(v7 + 16);
      }
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) || (unsigned __int64)*a3 < *(_QWORD *)(inserted + 32) )
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v15 = a1;
    v16 = 0;
    v12 = (__int64 *)operator new(0x30u);
    v12[4] = *a3;
    v13 = a3[1];
    a3[1] = 0;
    v12[5] = v13;
    *v12 = v6;
    v12[1] = v6;
    v12[2] = v6;
    *((_WORD *)v12 + 12) = 0;
    v15 = v11;
    v16 = v8;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Insert_node(
                 a1,
                 &v15);
  }
  else
  {
    v10 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v10;
  return a2;
}

```

## disassembly

```asm
0x18000e91c  mov     [rsp+arg_8], rbx
0x18000e921  mov     [rsp+arg_10], rbp
0x18000e926  push    rsi
0x18000e927  push    rdi
0x18000e928  push    r12
0x18000e92a  push    r14
0x18000e92c  push    r15
0x18000e92e  sub     rsp, 30h
0x18000e932  mov     rsi, r8
0x18000e935  mov     rbx, rdx
0x18000e938  mov     r14, rcx
0x18000e93b  mov     r15, [rcx]
0x18000e93e  mov     rax, [r15+8]
0x18000e942  xor     ebp, ebp
0x18000e944  xor     ecx, ecx
0x18000e946  mov     [rsp+58h+arg_0], rcx
0x18000e94b  mov     r9, r15
0x18000e94e  lea     edi, [rbp+1]
0x18000e951  cmp     [rax+19h], cl
0x18000e954  jnz     short loc_18000E97A
0x18000e956  mov     rcx, [r8]
0x18000e959  mov     r12, rax
0x18000e95c  cmp     [rax+20h], rcx
0x18000e960  jnb     short loc_18000E96A
0x18000e962  xor     ebp, ebp
0x18000e964  mov     rax, [rax+10h]
0x18000e968  jmp     short loc_18000E972
0x18000e96a  mov     ebp, edi
0x18000e96c  mov     r9, rax
0x18000e96f  mov     rax, [rax]
0x18000e972  cmp     byte ptr [rax+19h], 0
0x18000e976  jz      short loc_18000E959
0x18000e978  jmp     short loc_18000E97D
0x18000e97a  mov     r12, rax
0x18000e97d  cmp     byte ptr [r9+19h], 0
0x18000e982  jnz     short loc_18000E992
0x18000e984  mov     rax, [r9+20h]
0x18000e988  cmp     [r8], rax
0x18000e98b  jb      short loc_18000E992
0x18000e98d  xor     dil, dil
0x18000e990  jmp     short loc_18000EA0C
0x18000e992  mov     rax, 555555555555555h
0x18000e99c  cmp     [r14+8], rax
0x18000e9a0  jz      loc_18000EA2D
0x18000e9a6  mov     [rsp+58h+var_38], r14
0x18000e9ab  mov     [rsp+58h+var_30], 0
0x18000e9b4  mov     ecx, 30h ; '0'; Size
0x18000e9b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e9be  mov     r8, rax
0x18000e9c1  mov     rax, [rsi]
0x18000e9c4  mov     [r8+20h], rax
0x18000e9c8  mov     rax, [rsi+8]
0x18000e9cc  mov     qword ptr [rsi+8], 0
0x18000e9d4  mov     [r8+28h], rax
0x18000e9d8  mov     [r8], r15
0x18000e9db  mov     [r8+8], r15
0x18000e9df  mov     [r8+10h], r15
0x18000e9e3  mov     word ptr [r8+18h], 0
0x18000e9ea  mov     [rsp+58h+var_38], r12
0x18000e9ef  mov     dword ptr [rsp+58h+var_30], ebp
0x18000e9f3  mov     rax, [rsp+58h+arg_0]
0x18000e9f8  mov     dword ptr [rsp+58h+var_30+4], eax
0x18000e9fc  lea     rdx, [rsp+58h+var_38]
0x18000ea01  mov     rcx, r14
0x18000ea04  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *> * const)
0x18000ea09  mov     r9, rax
0x18000ea0c  mov     [rbx], r9
0x18000ea0f  mov     [rbx+8], dil
0x18000ea13  mov     rax, rbx
0x18000ea16  mov     rbx, [rsp+58h+arg_8]
0x18000ea1b  mov     rbp, [rsp+58h+arg_10]
0x18000ea20  add     rsp, 30h
0x18000ea24  pop     r15
0x18000ea26  pop     r14
0x18000ea28  pop     r12
0x18000ea2a  pop     rdi
0x18000ea2b  pop     rsi
0x18000ea2c  retn
0x18000ea2d  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
