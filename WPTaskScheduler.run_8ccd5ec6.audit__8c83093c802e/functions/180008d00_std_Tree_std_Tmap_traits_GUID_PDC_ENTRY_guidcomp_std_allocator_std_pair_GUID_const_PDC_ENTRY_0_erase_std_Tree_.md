# std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,PDC_ENTRY *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,PDC_ENTRY *>>>>)

- ea: `0x180008d00`
- end: `0x180008db2`
- name: `?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@@std@@@2@0@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800204fc`

## callees

- `0x180008d00`
- `0x180008dc0`
- `0x18000eeb0`

## pseudocode

```c
__int64 **__fastcall std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::erase(
        __int64 ***a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v5; // rbx
  __int64 *v8; // r8
  __int64 *i; // rax
  __int64 **result; // rax
  __int64 *v11; // rcx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v5 = a3;
  if ( a3 != **a1 || a4 != (__int64 *)*a1 )
  {
    while ( 1 )
    {
      if ( v5 == a4 )
      {
        *a2 = v5;
        return a2;
      }
      v8 = v5;
      if ( !*((_BYTE *)v5 + 25) )
      {
        i = (__int64 *)v5[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
          {
            if ( v5 != (__int64 *)i[2] )
              break;
            v5 = i;
          }
LABEL_9:
          v5 = i;
          goto LABEL_14;
        }
        v11 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_9;
        do
        {
          v5 = v11;
          v11 = (__int64 *)*v11;
        }
        while ( !*((_BYTE *)v11 + 25) );
      }
LABEL_14:
      std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::erase(
        a1,
        &v12,
        (_BYTE **)v8);
    }
  }
  std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(a1);
  result = a2;
  *a2 = **a1;
  return result;
}

```

## disassembly

```asm
0x180008d00  push    rbx
0x180008d02  push    rsi
0x180008d03  push    rdi
0x180008d04  push    r14
0x180008d06  sub     rsp, 28h
0x180008d0a  mov     rax, [rcx]
0x180008d0d  mov     rdi, r9
0x180008d10  mov     rbx, r8
0x180008d13  mov     rsi, rdx
0x180008d16  mov     r14, rcx
0x180008d19  cmp     r8, [rax]
0x180008d1c  jnz     short loc_180008D23
0x180008d1e  cmp     r9, rax
0x180008d21  jz      short loc_180008D6D
0x180008d23  cmp     rbx, rdi
0x180008d26  jz      short loc_180008D5D
0x180008d28  cmp     byte ptr [rbx+19h], 0
0x180008d2c  mov     r8, rbx
0x180008d2f  jnz     short loc_180008DA0
0x180008d31  mov     rax, [rbx+10h]
0x180008d35  cmp     byte ptr [rax+19h], 0
0x180008d39  jz      short loc_180008D88
0x180008d3b  mov     rax, [rbx+8]
0x180008d3f  cmp     byte ptr [rax+19h], 0
0x180008d43  jnz     short loc_180008D58
0x180008d45  cmp     rbx, [rax+10h]
0x180008d49  jnz     short loc_180008D58
0x180008d4b  mov     rbx, rax
0x180008d4e  mov     rax, [rax+8]
0x180008d52  cmp     byte ptr [rax+19h], 0
0x180008d56  jz      short loc_180008D45
0x180008d58  mov     rbx, rax
0x180008d5b  jmp     short loc_180008DA0
0x180008d5d  mov     [rsi], rbx
0x180008d60  mov     rax, rsi
0x180008d63  add     rsp, 28h
0x180008d67  pop     r14
0x180008d69  pop     rdi
0x180008d6a  pop     rsi
0x180008d6b  pop     rbx
0x180008d6c  retn
0x180008d6d  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(void)
0x180008d72  mov     rax, [r14]
0x180008d75  mov     rcx, [rax]
0x180008d78  mov     rax, rsi
0x180008d7b  mov     [rsi], rcx
0x180008d7e  add     rsp, 28h
0x180008d82  pop     r14
0x180008d84  pop     rdi
0x180008d85  pop     rsi
0x180008d86  pop     rbx
0x180008d87  retn
0x180008d88  mov     rcx, [rax]
0x180008d8b  cmp     byte ptr [rcx+19h], 0
0x180008d8f  jnz     short loc_180008D58
0x180008d91  mov     rax, [rcx]
0x180008d94  mov     rbx, rcx
0x180008d97  mov     rcx, rax
0x180008d9a  cmp     byte ptr [rax+19h], 0
0x180008d9e  jz      short loc_180008D91
0x180008da0  lea     rdx, [rsp+48h+arg_0]
0x180008da5  mov     rcx, r14
0x180008da8  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,PDC_ENTRY *>>>>)
0x180008dad  jmp     loc_180008D23
```
