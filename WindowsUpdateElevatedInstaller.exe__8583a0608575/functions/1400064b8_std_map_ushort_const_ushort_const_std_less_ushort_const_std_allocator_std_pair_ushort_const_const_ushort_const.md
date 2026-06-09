# std::map<ushort const *,ushort const *,std::less<ushort const *>,std::allocator<std::pair<ushort const * const,ushort const *>>>::operator[](ushort const * const &)

- ea: `0x1400064b8`
- end: `0x1400065a2`
- name: `??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z`
- size: `234`
- prototype: `char *__fastcall(__int64, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140006038`
- `0x1400065a8`
- `0x1400068b4`

## callees

- `0x140001ee0`
- `0x1400064b8`
- `0x140006d50`
- `0x140006f80`

## pseudocode

```c
char *__fastcall std::map<unsigned short const *,unsigned short const *>::operator[](__int64 a1, unsigned __int64 *a2)
{
  void *v3; // rsi
  _QWORD *v4; // rbp
  unsigned int v5; // ebx
  _BYTE *inserted; // rcx
  _QWORD *v7; // rax
  unsigned __int64 v8; // rdx
  _QWORD *v9; // rax
  void **v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h]

  v3 = RegistryManager::s_defaultRedirectionMap;
  v4 = (_QWORD *)*((_QWORD *)RegistryManager::s_defaultRedirectionMap + 1);
  v5 = 0;
  inserted = RegistryManager::s_defaultRedirectionMap;
  v7 = v4;
  if ( !*((_BYTE *)v4 + 25) )
  {
    v8 = *a2;
    do
    {
      v4 = v7;
      if ( v7[4] >= v8 )
      {
        v5 = 1;
        inserted = v7;
        v7 = (_QWORD *)*v7;
      }
      else
      {
        v5 = 0;
        v7 = (_QWORD *)v7[2];
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( inserted[25] || *a2 < *((_QWORD *)inserted + 4) )
  {
    if ( qword_14000D3F0 == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v11 = &RegistryManager::s_defaultRedirectionMap;
    v12 = 0;
    v9 = operator new(0x30u);
    v9[4] = *a2;
    v9[5] = 0;
    *v9 = v3;
    v9[1] = v3;
    v9[2] = v3;
    *((_WORD *)v9 + 12) = 0;
    v11 = (void **)v4;
    v12 = v5;
    inserted = (_BYTE *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,unsigned short const *>>>::_Insert_node(
                          &RegistryManager::s_defaultRedirectionMap,
                          &v11);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x1400064b8  push    rbx
0x1400064ba  push    rbp
0x1400064bb  push    rsi
0x1400064bc  push    rdi
0x1400064bd  push    r12
0x1400064bf  push    r14
0x1400064c1  sub     rsp, 38h
0x1400064c5  mov     rdi, rdx
0x1400064c8  mov     rsi, cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x1400064cf  mov     rbp, [rsi+8]
0x1400064d3  xor     ebx, ebx
0x1400064d5  xor     r12d, r12d
0x1400064d8  mov     rcx, rsi
0x1400064db  mov     rax, rbp
0x1400064de  cmp     [rbp+19h], bl
0x1400064e1  jnz     short loc_140006508
0x1400064e3  mov     rdx, [rdx]
0x1400064e6  mov     rbp, rax
0x1400064e9  cmp     [rax+20h], rdx
0x1400064ed  jnb     short loc_1400064F7
0x1400064ef  xor     ebx, ebx
0x1400064f1  mov     rax, [rax+10h]
0x1400064f5  jmp     short loc_140006502
0x1400064f7  mov     ebx, 1
0x1400064fc  mov     rcx, rax
0x1400064ff  mov     rax, [rax]
0x140006502  cmp     [rax+19h], r12b
0x140006506  jz      short loc_1400064E6
0x140006508  cmp     [rcx+19h], r12b
0x14000650c  jnz     short loc_140006517
0x14000650e  mov     rax, [rcx+20h]
0x140006512  cmp     [rdi], rax
0x140006515  jnb     short loc_14000658B
0x140006517  mov     rax, 555555555555555h
0x140006521  cmp     cs:qword_14000D3F0, rax
0x140006528  jz      short loc_14000659C
0x14000652a  lea     r14, ?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x140006531  mov     [rsp+68h+var_48], r14
0x140006536  mov     [rsp+68h+var_40], 0
0x14000653f  mov     ecx, 30h ; '0'; Size
0x140006544  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006549  mov     r8, rax
0x14000654c  mov     rax, [rdi]
0x14000654f  mov     [r8+20h], rax
0x140006553  mov     qword ptr [r8+28h], 0
0x14000655b  mov     [r8], rsi
0x14000655e  mov     [r8+8], rsi
0x140006562  mov     [r8+10h], rsi
0x140006566  mov     word ptr [r8+18h], 0
0x14000656d  mov     [rsp+68h+var_48], rbp
0x140006572  mov     dword ptr [rsp+68h+var_40], ebx
0x140006576  mov     dword ptr [rsp+68h+var_40+4], r12d
0x14000657b  lea     rdx, [rsp+68h+var_48]
0x140006580  mov     rcx, r14
0x140006583  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBG@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,ushort const *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *> *>,std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *> * const)
0x140006588  mov     rcx, rax
0x14000658b  lea     rax, [rcx+28h]
0x14000658f  add     rsp, 38h
0x140006593  pop     r14
0x140006595  pop     r12
0x140006597  pop     rdi
0x140006598  pop     rsi
0x140006599  pop     rbp
0x14000659a  pop     rbx
0x14000659b  retn
0x14000659c  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
