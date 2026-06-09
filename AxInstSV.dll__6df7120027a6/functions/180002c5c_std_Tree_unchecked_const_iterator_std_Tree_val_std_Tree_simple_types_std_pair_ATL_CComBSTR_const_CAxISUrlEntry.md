# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(void)

- ea: `0x180002c5c`
- end: `0x180002ca1`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `69`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000383c`
- `0x180004318`
- `0x180004afc`
- `0x180004f80`
- `0x180011e5c`

## callees

- `0x180002c5c`
- `0x180004f08`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(
        __int64 *a1)
{
  __int64 *v1; // r8
  __int64 v2; // rcx
  __int64 i; // rax

  v1 = a1;
  v2 = *a1;
  if ( *(_BYTE *)(*(_QWORD *)(v2 + 16) + 25LL) )
  {
    for ( i = *(_QWORD *)(v2 + 8); !*(_BYTE *)(i + 25) && v2 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
    {
      v2 = i;
      *v1 = i;
    }
  }
  else
  {
    i = std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Min(*(_QWORD *)(v2 + 16), 0, v1);
  }
  *v1 = i;
  return v1;
}

```

## disassembly

```asm
0x180002c5c  sub     rsp, 28h
0x180002c60  mov     r8, rcx
0x180002c63  xor     edx, edx
0x180002c65  mov     rcx, [rcx]
0x180002c68  mov     rax, [rcx+10h]
0x180002c6c  cmp     [rax+19h], dl
0x180002c6f  jz      short loc_180002C8E
0x180002c71  mov     rax, [rcx+8]
0x180002c75  jmp     short loc_180002C87
0x180002c77  cmp     rcx, [rax+10h]
0x180002c7b  jnz     short loc_180002C96
0x180002c7d  mov     rcx, rax
0x180002c80  mov     [r8], rax
0x180002c83  mov     rax, [rax+8]
0x180002c87  cmp     [rax+19h], dl
0x180002c8a  jz      short loc_180002C77
0x180002c8c  jmp     short loc_180002C96
0x180002c8e  mov     rcx, rax
0x180002c91  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@SAPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Min(std::_Tree_node<CPolicyEntry *,void *> *)
0x180002c96  mov     [r8], rax
0x180002c99  mov     rax, r8
0x180002c9c  add     rsp, 28h
0x180002ca0  retn
```
