# std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(std::_Tree_id<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *>,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * const)

- ea: `0x18000d27c`
- end: `0x18000d3a5`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c40`
- `0x18000dca4`
- `0x18000f09c`
- `0x18000f1ec`
- `0x18000f33c`
- `0x18000f4b8`
- `0x18001a094`
- `0x18001a1a4`

## callees

- `0x18000d27c`
- `0x18000d3ac`
- `0x18000d3fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  _QWORD *v4; // r11
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 i; // r10
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax

  ++*(_QWORD *)(a1 + 8);
  v3 = a3;
  v4 = *(_QWORD **)a1;
  v6 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v6 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v6 = a3;
      if ( v6 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v6[2] = a3;
      if ( v6 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v7 = *(_QWORD *)(a3 + 8);
    for ( i = a3; ; v7 = *(_QWORD *)(i + 8) )
    {
      if ( *(_BYTE *)(v7 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return v3;
      }
      v9 = *(_QWORD *)(i + 8);
      v10 = *(__int64 **)(v9 + 8);
      v11 = *v10;
      if ( v9 == *v10 )
      {
        v11 = v10[2];
        if ( !*(_BYTE *)(v11 + 24) )
          goto LABEL_15;
        if ( i == *(_QWORD *)(v9 + 16) )
          std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>::_Lrotate(a1, v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Rrotate(a1);
      }
      else
      {
        if ( !*(_BYTE *)(v11 + 24) )
        {
LABEL_15:
          *(_BYTE *)(v9 + 24) = 1;
          *(_BYTE *)(v11 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
          i = *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL);
          continue;
        }
        if ( i == *(_QWORD *)v9 )
          std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Rrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>::_Lrotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL));
      }
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return v3;
}

```

## disassembly

```asm
0x18000d27c  push    rbx
0x18000d27e  sub     rsp, 20h
0x18000d282  inc     qword ptr [rcx+8]
0x18000d286  mov     r9, r8
0x18000d289  mov     r11, [rcx]
0x18000d28c  mov     rbx, rcx
0x18000d28f  mov     rax, [rdx]
0x18000d292  mov     [r8+8], rax
0x18000d296  cmp     rax, r11
0x18000d299  jnz     short loc_18000D2B0
0x18000d29b  mov     [r11], r8
0x18000d29e  mov     [r11+8], r8
0x18000d2a2  mov     [r11+10h], r8
0x18000d2a6  mov     byte ptr [r8+18h], 1
0x18000d2ab  jmp     loc_18000D39C
0x18000d2b0  cmp     dword ptr [rdx+8], 0
0x18000d2b4  jnz     short loc_18000D2C6
0x18000d2b6  mov     [rax+10h], r9
0x18000d2ba  cmp     rax, [r11+10h]
0x18000d2be  jnz     short loc_18000D2D1
0x18000d2c0  mov     [r11+10h], r9
0x18000d2c4  jmp     short loc_18000D2D1
0x18000d2c6  mov     [rax], r9
0x18000d2c9  cmp     rax, [r11]
0x18000d2cc  jnz     short loc_18000D2D1
0x18000d2ce  mov     [r11], r9
0x18000d2d1  mov     rax, [r8+8]
0x18000d2d5  mov     r10, r9
0x18000d2d8  jmp     loc_18000D38A
0x18000d2dd  mov     rdx, [r10+8]
0x18000d2e1  mov     rcx, [rdx+8]
0x18000d2e5  mov     rax, [rcx]
0x18000d2e8  cmp     rdx, rax
0x18000d2eb  jnz     short loc_18000D32E
0x18000d2ed  mov     rax, [rcx+10h]
0x18000d2f1  cmp     byte ptr [rax+18h], 0
0x18000d2f5  jz      short loc_18000D334
0x18000d2f7  cmp     r10, [rdx+10h]
0x18000d2fb  jnz     short loc_18000D308
0x18000d2fd  mov     rcx, rbx
0x18000d300  mov     r10, rdx
0x18000d303  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAAXPEAU?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>::_Lrotate(std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *> *)
0x18000d308  mov     rax, [r10+8]
0x18000d30c  mov     byte ptr [rax+18h], 1
0x18000d310  mov     rax, [r10+8]
0x18000d314  mov     rcx, [rax+8]
0x18000d318  mov     byte ptr [rcx+18h], 0
0x18000d31c  mov     rcx, rbx
0x18000d31f  mov     rdx, [r10+8]
0x18000d323  mov     rdx, [rdx+8]
0x18000d327  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXPEAU?$_Tree_node@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Rrotate(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *> *)
0x18000d32c  jmp     short loc_18000D386
0x18000d32e  cmp     byte ptr [rax+18h], 0
0x18000d332  jnz     short loc_18000D352
0x18000d334  mov     byte ptr [rdx+18h], 1
0x18000d338  mov     byte ptr [rax+18h], 1
0x18000d33c  mov     rax, [r10+8]
0x18000d340  mov     rcx, [rax+8]
0x18000d344  mov     byte ptr [rcx+18h], 0
0x18000d348  mov     rax, [r10+8]
0x18000d34c  mov     r10, [rax+8]
0x18000d350  jmp     short loc_18000D386
0x18000d352  cmp     r10, [rdx]
0x18000d355  jnz     short loc_18000D362
0x18000d357  mov     rcx, rbx
0x18000d35a  mov     r10, rdx
0x18000d35d  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXPEAU?$_Tree_node@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Rrotate(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *> *)
0x18000d362  mov     rax, [r10+8]
0x18000d366  mov     byte ptr [rax+18h], 1
0x18000d36a  mov     rax, [r10+8]
0x18000d36e  mov     rcx, [rax+8]
0x18000d372  mov     byte ptr [rcx+18h], 0
0x18000d376  mov     rcx, rbx
0x18000d379  mov     rdx, [r10+8]
0x18000d37d  mov     rdx, [rdx+8]
0x18000d381  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@VSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAAXPEAU?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyView>>::_Lrotate(std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *> *)
0x18000d386  mov     rax, [r10+8]
0x18000d38a  cmp     byte ptr [rax+18h], 0
0x18000d38e  jz      loc_18000D2DD
0x18000d394  mov     rax, [r11+8]
0x18000d398  mov     byte ptr [rax+18h], 1
0x18000d39c  mov     rax, r9
0x18000d39f  add     rsp, 20h
0x18000d3a3  pop     rbx
0x18000d3a4  retn
```
