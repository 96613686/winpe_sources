# std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *)

- ea: `0x180002280`
- end: `0x1800022cf`
- name: `?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@@Z`
- size: `79`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003148`
- `0x180003398`
- `0x180005be4`
- `0x180005ee0`
- `0x180006210`
- `0x18000a3a0`
- `0x18000a694`

## callees

- `0x180002280`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 25LL) )
    *(_QWORD *)(*v2 + 8LL) = a2;
  v2[1] = *(_QWORD *)(a2 + 8);
  result = *(_QWORD **)a1;
  if ( a2 == *(_QWORD *)(*(_QWORD *)a1 + 8LL) )
  {
    result[1] = v2;
    goto LABEL_7;
  }
  result = *(_QWORD **)(a2 + 8);
  if ( a2 != *result )
  {
    result[2] = v2;
LABEL_7:
    *v2 = a2;
    *(_QWORD *)(a2 + 8) = v2;
    return result;
  }
  *result = v2;
  *v2 = a2;
  *(_QWORD *)(a2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x180002280  mov     r8, [rdx+10h]
0x180002284  mov     rax, [r8]
0x180002287  mov     [rdx+10h], rax
0x18000228b  mov     rax, [r8]
0x18000228e  cmp     byte ptr [rax+19h], 0
0x180002292  jnz     short loc_180002298
0x180002294  mov     [rax+8], rdx
0x180002298  mov     rax, [rdx+8]
0x18000229c  mov     [r8+8], rax
0x1800022a0  mov     rax, [rcx]
0x1800022a3  cmp     rdx, [rax+8]
0x1800022a7  jz      short loc_1800022B8
0x1800022a9  mov     rax, [rdx+8]
0x1800022ad  cmp     rdx, [rax]
0x1800022b0  jz      short loc_1800022C4
0x1800022b2  mov     [rax+10h], r8
0x1800022b6  jmp     short loc_1800022BC
0x1800022b8  mov     [rax+8], r8
0x1800022bc  mov     [r8], rdx
0x1800022bf  mov     [rdx+8], r8
0x1800022c3  retn
0x1800022c4  mov     [rax], r8
0x1800022c7  mov     [r8], rdx
0x1800022ca  mov     [rdx+8], r8
0x1800022ce  retn
```
