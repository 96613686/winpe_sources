# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)

- ea: `0x180005070`
- end: `0x1800050c4`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `84`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002e88`
- `0x180003760`
- `0x180003a60`
- `0x180004fa0`
- `0x180005be4`
- `0x180006210`
- `0x18000a3a0`
- `0x18000efc4`
- `0x18001343c`
- `0x1800144cc`
- `0x180014558`

## callees

- `0x180005070`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(
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
0x180005070  mov     r8, [rcx]
0x180005073  mov     rdx, [r8+10h]
0x180005077  cmp     byte ptr [rdx+19h], 0
0x18000507b  jnz     short loc_18000509D
0x18000507d  mov     r8, [rdx]
0x180005080  cmp     byte ptr [r8+19h], 0
0x180005085  jnz     short loc_180005096
0x180005087  mov     rax, [r8]
0x18000508a  mov     rdx, r8
0x18000508d  mov     r8, rax
0x180005090  cmp     byte ptr [rax+19h], 0
0x180005094  jz      short loc_180005087
0x180005096  mov     [rcx], rdx
0x180005099  mov     rax, rcx
0x18000509c  retn
0x18000509d  mov     rax, [r8+8]
0x1800050a1  cmp     byte ptr [rax+19h], 0
0x1800050a5  jnz     short loc_1800050BD
0x1800050a7  cmp     r8, [rax+10h]
0x1800050ab  jnz     short loc_1800050BD
0x1800050ad  mov     [rcx], rax
0x1800050b0  mov     r8, rax
0x1800050b3  mov     rax, [rax+8]
0x1800050b7  cmp     byte ptr [rax+19h], 0
0x1800050bb  jz      short loc_1800050A7
0x1800050bd  mov     [rcx], rax
0x1800050c0  mov     rax, rcx
0x1800050c3  retn
```
