# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)

- ea: `0x180006d90`
- end: `0x180006ded`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `93`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005b0c`
- `0x180005cc0`
- `0x180005f30`
- `0x1800060a0`
- `0x180006360`
- `0x180006c50`
- `0x180017700`
- `0x180018754`
- `0x180018c3c`
- `0x1800198e0`

## callees

- `0x180006d90`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(
        __int64 *a1)
{
  __int64 v1; // r8
  __int64 **v2; // rdx
  __int64 *j; // rax
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
0x180006d90  mov     r8, [rcx]
0x180006d93  mov     r9, rcx
0x180006d96  mov     rdx, [r8+10h]
0x180006d9a  cmp     byte ptr [rdx+19h], 0
0x180006d9e  jnz     short loc_180006DC6
0x180006da0  mov     rax, [rdx]
0x180006da3  cmp     byte ptr [rax+19h], 0
0x180006da7  jnz     short loc_180006DBF
0x180006da9  nop     dword ptr [rax+00000000h]
0x180006db0  mov     rcx, [rax]
0x180006db3  mov     rdx, rax
0x180006db6  mov     rax, rcx
0x180006db9  cmp     byte ptr [rcx+19h], 0
0x180006dbd  jz      short loc_180006DB0
0x180006dbf  mov     [r9], rdx
0x180006dc2  mov     rax, r9
0x180006dc5  retn
0x180006dc6  mov     rax, [r8+8]
0x180006dca  cmp     byte ptr [rax+19h], 0
0x180006dce  jnz     short loc_180006DE6
0x180006dd0  cmp     r8, [rax+10h]
0x180006dd4  jnz     short loc_180006DE6
0x180006dd6  mov     [rcx], rax
0x180006dd9  mov     r8, rax
0x180006ddc  mov     rax, [rax+8]
0x180006de0  cmp     byte ptr [rax+19h], 0
0x180006de4  jz      short loc_180006DD0
0x180006de6  mov     [rcx], rax
0x180006de9  mov     rax, r9
0x180006dec  retn
```
