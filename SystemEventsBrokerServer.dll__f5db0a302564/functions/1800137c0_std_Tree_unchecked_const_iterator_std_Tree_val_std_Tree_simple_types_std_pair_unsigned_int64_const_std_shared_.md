# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>>,std::_Iterator_base0>::operator++(void)

- ea: `0x1800137c0`
- end: `0x180013814`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `84`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013520`
- `0x180018754`
- `0x180018d7c`
- `0x1800190b0`
- `0x1800198e0`

## callees

- `0x1800137c0`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(
        __int64 *a1)
{
  __int64 v1; // r8
  __int64 **v2; // rdx
  __int64 *j; // r8
  __int64 i; // rax

  v1 = *a1;
  v2 = *(__int64 ***)(*a1 + 16);
  if ( *((_BYTE *)v2 + 25) )
  {
    for ( i = *(_QWORD *)(v1 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
    {
      if ( v1 != *(_QWORD *)(i + 16) )
        break;
      *a1 = i;
      v1 = i;
    }
    *a1 = i;
    return a1;
  }
  else
  {
    for ( j = *v2; !*((_BYTE *)j + 25); j = (__int64 *)*j )
      v2 = (__int64 **)j;
    *a1 = (__int64)v2;
    return a1;
  }
}

```

## disassembly

```asm
0x1800137c0  mov     r8, [rcx]
0x1800137c3  mov     rdx, [r8+10h]
0x1800137c7  cmp     byte ptr [rdx+19h], 0
0x1800137cb  jnz     short loc_1800137ED
0x1800137cd  mov     r8, [rdx]
0x1800137d0  cmp     byte ptr [r8+19h], 0
0x1800137d5  jnz     short loc_1800137E6
0x1800137d7  mov     rax, [r8]
0x1800137da  mov     rdx, r8
0x1800137dd  mov     r8, rax
0x1800137e0  cmp     byte ptr [rax+19h], 0
0x1800137e4  jz      short loc_1800137D7
0x1800137e6  mov     [rcx], rdx
0x1800137e9  mov     rax, rcx
0x1800137ec  retn
0x1800137ed  mov     rax, [r8+8]
0x1800137f1  cmp     byte ptr [rax+19h], 0
0x1800137f5  jnz     short loc_18001380D
0x1800137f7  cmp     r8, [rax+10h]
0x1800137fb  jnz     short loc_18001380D
0x1800137fd  mov     [rcx], rax
0x180013800  mov     r8, rax
0x180013803  mov     rax, [rax+8]
0x180013807  cmp     byte ptr [rax+19h], 0
0x18001380b  jz      short loc_1800137F7
0x18001380d  mov     [rcx], rax
0x180013810  mov     rax, rcx
0x180013813  retn
```
