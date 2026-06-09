# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *>,std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const)

- ea: `0x180010464`
- end: `0x18001058d`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f1b8`
- `0x180014368`
- `0x180014470`
- `0x180014538`

## callees

- `0x180010464`
- `0x1800105a4`
- `0x180010638`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(
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
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Lrotate(
            a1,
            v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Rrotate(a1);
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
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Rrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Lrotate(
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
0x180010464  push    rbx
0x180010466  sub     rsp, 20h
0x18001046a  inc     qword ptr [rcx+8]
0x18001046e  mov     r9, r8
0x180010471  mov     r11, [rcx]
0x180010474  mov     rbx, rcx
0x180010477  mov     rax, [rdx]
0x18001047a  mov     [r8+8], rax
0x18001047e  cmp     rax, r11
0x180010481  jnz     short loc_180010498
0x180010483  mov     [r11], r8
0x180010486  mov     [r11+8], r8
0x18001048a  mov     [r11+10h], r8
0x18001048e  mov     byte ptr [r8+18h], 1
0x180010493  jmp     loc_180010584
0x180010498  cmp     dword ptr [rdx+8], 0
0x18001049c  jnz     short loc_1800104AE
0x18001049e  mov     [rax+10h], r9
0x1800104a2  cmp     rax, [r11+10h]
0x1800104a6  jnz     short loc_1800104B9
0x1800104a8  mov     [r11+10h], r9
0x1800104ac  jmp     short loc_1800104B9
0x1800104ae  mov     [rax], r9
0x1800104b1  cmp     rax, [r11]
0x1800104b4  jnz     short loc_1800104B9
0x1800104b6  mov     [r11], r9
0x1800104b9  mov     rax, [r8+8]
0x1800104bd  mov     r10, r9
0x1800104c0  jmp     loc_180010572
0x1800104c5  mov     rdx, [r10+8]
0x1800104c9  mov     rcx, [rdx+8]
0x1800104cd  mov     rax, [rcx]
0x1800104d0  cmp     rdx, rax
0x1800104d3  jnz     short loc_180010516
0x1800104d5  mov     rax, [rcx+10h]
0x1800104d9  cmp     byte ptr [rax+18h], 0
0x1800104dd  jz      short loc_18001051C
0x1800104df  cmp     r10, [rdx+10h]
0x1800104e3  jnz     short loc_1800104F0
0x1800104e5  mov     rcx, rbx
0x1800104e8  mov     r10, rdx
0x1800104eb  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Lrotate(std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *> *)
0x1800104f0  mov     rax, [r10+8]
0x1800104f4  mov     byte ptr [rax+18h], 1
0x1800104f8  mov     rax, [r10+8]
0x1800104fc  mov     rcx, [rax+8]
0x180010500  mov     byte ptr [rcx+18h], 0
0x180010504  mov     rcx, rbx
0x180010507  mov     rdx, [r10+8]
0x18001050b  mov     rdx, [rdx+8]
0x18001050f  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Rrotate(std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *> *)
0x180010514  jmp     short loc_18001056E
0x180010516  cmp     byte ptr [rax+18h], 0
0x18001051a  jnz     short loc_18001053A
0x18001051c  mov     byte ptr [rdx+18h], 1
0x180010520  mov     byte ptr [rax+18h], 1
0x180010524  mov     rax, [r10+8]
0x180010528  mov     rcx, [rax+8]
0x18001052c  mov     byte ptr [rcx+18h], 0
0x180010530  mov     rax, [r10+8]
0x180010534  mov     r10, [rax+8]
0x180010538  jmp     short loc_18001056E
0x18001053a  cmp     r10, [rdx]
0x18001053d  jnz     short loc_18001054A
0x18001053f  mov     rcx, rbx
0x180010542  mov     r10, rdx
0x180010545  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Rrotate(std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *> *)
0x18001054a  mov     rax, [r10+8]
0x18001054e  mov     byte ptr [rax+18h], 1
0x180010552  mov     rax, [r10+8]
0x180010556  mov     rcx, [rax+8]
0x18001055a  mov     byte ptr [rcx+18h], 0
0x18001055e  mov     rcx, rbx
0x180010561  mov     rdx, [r10+8]
0x180010565  mov     rdx, [rdx+8]
0x180010569  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Lrotate(std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *> *)
0x18001056e  mov     rax, [r10+8]
0x180010572  cmp     byte ptr [rax+18h], 0
0x180010576  jz      loc_1800104C5
0x18001057c  mov     rax, [r11+8]
0x180010580  mov     byte ptr [rax+18h], 1
0x180010584  mov     rax, r9
0x180010587  add     rsp, 20h
0x18001058b  pop     rbx
0x18001058c  retn
```
