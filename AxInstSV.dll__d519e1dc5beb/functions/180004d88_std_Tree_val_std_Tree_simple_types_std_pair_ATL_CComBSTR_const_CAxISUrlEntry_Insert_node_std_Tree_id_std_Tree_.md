# std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *>,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> * const)

- ea: `0x180004d88`
- end: `0x180004eb1`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027b4`
- `0x1800119a4`

## callees

- `0x180004d88`
- `0x180004eb8`
- `0x180004f2c`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Insert_node(
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
          std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(a1, *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL));
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
          std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(a1, v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(a1);
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
0x180004d88  push    rbx
0x180004d8a  sub     rsp, 20h
0x180004d8e  inc     qword ptr [rcx+8]
0x180004d92  mov     r9, r8
0x180004d95  mov     r11, [rcx]
0x180004d98  mov     rbx, rcx
0x180004d9b  mov     rax, [rdx]
0x180004d9e  mov     [r8+8], rax
0x180004da2  cmp     rax, r11
0x180004da5  jnz     short loc_180004DBC
0x180004da7  mov     [r11], r8
0x180004daa  mov     [r11+8], r8
0x180004dae  mov     [r11+10h], r8
0x180004db2  mov     byte ptr [r8+18h], 1
0x180004db7  jmp     loc_180004EA8
0x180004dbc  cmp     dword ptr [rdx+8], 0
0x180004dc0  jnz     short loc_180004DD2
0x180004dc2  mov     [rax+10h], r9
0x180004dc6  cmp     rax, [r11+10h]
0x180004dca  jnz     short loc_180004DDD
0x180004dcc  mov     [r11+10h], r9
0x180004dd0  jmp     short loc_180004DDD
0x180004dd2  mov     [rax], r9
0x180004dd5  cmp     rax, [r11]
0x180004dd8  jnz     short loc_180004DDD
0x180004dda  mov     [r11], r9
0x180004ddd  mov     rax, [r8+8]
0x180004de1  mov     r10, r9
0x180004de4  jmp     loc_180004E96
0x180004de9  mov     rdx, [r10+8]
0x180004ded  mov     rcx, [rdx+8]
0x180004df1  mov     rax, [rcx]
0x180004df4  cmp     rdx, rax
0x180004df7  jnz     short loc_180004E3A
0x180004df9  mov     rax, [rcx+10h]
0x180004dfd  cmp     byte ptr [rax+18h], 0
0x180004e01  jz      short loc_180004E40
0x180004e03  cmp     r10, [rdx+10h]
0x180004e07  jnz     short loc_180004E14
0x180004e09  mov     rcx, rbx
0x180004e0c  mov     r10, rdx
0x180004e0f  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180004e14  mov     rax, [r10+8]
0x180004e18  mov     byte ptr [rax+18h], 1
0x180004e1c  mov     rax, [r10+8]
0x180004e20  mov     rcx, [rax+8]
0x180004e24  mov     byte ptr [rcx+18h], 0
0x180004e28  mov     rcx, rbx
0x180004e2b  mov     rdx, [r10+8]
0x180004e2f  mov     rdx, [rdx+8]
0x180004e33  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@QEAAXPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(std::_Tree_node<CPolicyEntry *,void *> *)
0x180004e38  jmp     short loc_180004E92
0x180004e3a  cmp     byte ptr [rax+18h], 0
0x180004e3e  jnz     short loc_180004E5E
0x180004e40  mov     byte ptr [rdx+18h], 1
0x180004e44  mov     byte ptr [rax+18h], 1
0x180004e48  mov     rax, [r10+8]
0x180004e4c  mov     rcx, [rax+8]
0x180004e50  mov     byte ptr [rcx+18h], 0
0x180004e54  mov     rax, [r10+8]
0x180004e58  mov     r10, [rax+8]
0x180004e5c  jmp     short loc_180004E92
0x180004e5e  cmp     r10, [rdx]
0x180004e61  jnz     short loc_180004E6E
0x180004e63  mov     rcx, rbx
0x180004e66  mov     r10, rdx
0x180004e69  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@QEAAXPEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>::_Rrotate(std::_Tree_node<CPolicyEntry *,void *> *)
0x180004e6e  mov     rax, [r10+8]
0x180004e72  mov     byte ptr [rax+18h], 1
0x180004e76  mov     rax, [r10+8]
0x180004e7a  mov     rcx, [rax+8]
0x180004e7e  mov     byte ptr [rcx+18h], 0
0x180004e82  mov     rcx, rbx
0x180004e85  mov     rdx, [r10+8]
0x180004e89  mov     rdx, [rdx+8]
0x180004e8d  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Lrotate(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180004e92  mov     rax, [r10+8]
0x180004e96  cmp     byte ptr [rax+18h], 0
0x180004e9a  jz      loc_180004DE9
0x180004ea0  mov     rax, [r11+8]
0x180004ea4  mov     byte ptr [rax+18h], 1
0x180004ea8  mov     rax, r9
0x180004eab  add     rsp, 20h
0x180004eaf  pop     rbx
0x180004eb0  retn
```
