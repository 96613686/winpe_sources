# std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)

- ea: `0x180004eb8`
- end: `0x180004f01`
- name: `?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004afc`
- `0x180004d88`

## callees

- `0x180004eb8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(
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
  }
  else
  {
    result = *(_QWORD **)(a2 + 8);
    if ( a2 == *result )
      *result = v2;
    else
      result[2] = v2;
  }
  *v2 = a2;
  *(_QWORD *)(a2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x180004eb8  mov     r8, [rdx+10h]
0x180004ebc  mov     rax, [r8]
0x180004ebf  mov     [rdx+10h], rax
0x180004ec3  mov     rax, [r8]
0x180004ec6  cmp     byte ptr [rax+19h], 0
0x180004eca  jnz     short loc_180004ED0
0x180004ecc  mov     [rax+8], rdx
0x180004ed0  mov     rax, [rdx+8]
0x180004ed4  mov     [r8+8], rax
0x180004ed8  mov     rax, [rcx]
0x180004edb  cmp     rdx, [rax+8]
0x180004edf  jnz     short loc_180004EE7
0x180004ee1  mov     [rax+8], r8
0x180004ee5  jmp     short loc_180004EF9
0x180004ee7  mov     rax, [rdx+8]
0x180004eeb  cmp     rdx, [rax]
0x180004eee  jnz     short loc_180004EF5
0x180004ef0  mov     [rax], r8
0x180004ef3  jmp     short loc_180004EF9
0x180004ef5  mov     [rax+10h], r8
0x180004ef9  mov     [r8], rdx
0x180004efc  mov     [rdx+8], r8
0x180004f00  retn
```
