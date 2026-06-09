# std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)

- ea: `0x140006bfc`
- end: `0x140006c80`
- name: `?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004d90`
- `0x140004e40`
- `0x140004f50`

## callees

- `0x140006bfc`
- `0x140006c80`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
        _QWORD *a1,
        _QWORD *a2,
        unsigned __int8 *a3)
{
  __int64 v3; // r9
  __int64 v5; // r10
  unsigned __int64 i; // rdx
  __int64 v8; // rax
  unsigned __int64 j; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD v13[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = 0xCBF29CE484222325uLL;
  v5 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
  {
    v8 = a3[i];
    v5 = 0x100000001B3LL * (v8 ^ v5);
  }
  for ( j = 0; j < 8; ++j )
  {
    v10 = a3[j + 8];
    v3 = 0x100000001B3LL * (v10 ^ v3);
  }
  v11 = std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
          a1,
          v13,
          a3,
          v5 ^ v3)[1];
  if ( !v11 )
    v11 = a1[1];
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x140006bfc  mov     [rsp+arg_0], rbx
0x140006c01  push    rdi
0x140006c02  sub     rsp, 30h
0x140006c06  mov     r9, 0CBF29CE484222325h
0x140006c10  mov     rbx, rdx
0x140006c13  mov     r10, r9
0x140006c16  mov     rdi, rcx
0x140006c19  xor     edx, edx
0x140006c1b  mov     r11, 100000001B3h
0x140006c25  movzx   eax, byte ptr [r8+rdx]
0x140006c2a  inc     rdx
0x140006c2d  xor     r10, rax
0x140006c30  imul    r10, r11
0x140006c34  cmp     rdx, 8
0x140006c38  jb      short loc_140006C25
0x140006c3a  xor     ecx, ecx
0x140006c3c  movzx   eax, byte ptr [r8+rcx+8]
0x140006c42  inc     rcx
0x140006c45  xor     r9, rax
0x140006c48  imul    r9, r11
0x140006c4c  cmp     rcx, 8
0x140006c50  jb      short loc_140006C3C
0x140006c52  xor     r9, r10
0x140006c55  lea     rdx, [rsp+38h+var_18]
0x140006c5a  mov     rcx, rdi
0x140006c5d  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x140006c62  mov     rcx, [rax+8]
0x140006c66  test    rcx, rcx
0x140006c69  jnz     short loc_140006C6F
0x140006c6b  mov     rcx, [rdi+8]
0x140006c6f  mov     [rbx], rcx
0x140006c72  mov     rax, rbx
0x140006c75  mov     rbx, [rsp+38h+arg_0]
0x140006c7a  add     rsp, 30h
0x140006c7e  pop     rdi
0x140006c7f  retn
```
