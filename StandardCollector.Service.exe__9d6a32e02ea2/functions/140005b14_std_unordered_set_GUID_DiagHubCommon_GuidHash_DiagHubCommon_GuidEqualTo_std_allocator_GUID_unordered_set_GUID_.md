# std::unordered_set<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo,std::allocator<_GUID>>::~unordered_set<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo,std::allocator<_GUID>>(void)

- ea: `0x140005b14`
- end: `0x140005b6e`
- name: `??1?$unordered_set@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140014f32`

## callees

- `0x140001fac`
- `0x140005b14`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::unordered_set<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo,std::allocator<_GUID>>::~unordered_set<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo,std::allocator<_GUID>>(
        __int64 a1)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(a1 + 24);
  v2 = *(_QWORD ***)(a1 + 8);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*(void **)(a1 + 8));
}

```

## disassembly

```asm
0x140005b14  mov     [rsp+arg_8], rbx
0x140005b19  push    rdi
0x140005b1a  sub     rsp, 20h
0x140005b1e  mov     rdi, rcx
0x140005b21  add     rcx, 18h
0x140005b25  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x140005b2a  mov     rdx, [rdi+8]
0x140005b2e  mov     rax, [rdx+8]
0x140005b32  mov     qword ptr [rax], 0
0x140005b39  mov     rcx, [rdx]; Block
0x140005b3c  test    rcx, rcx
0x140005b3f  jz      short loc_140005B56
0x140005b41  mov     rbx, [rcx]
0x140005b44  mov     edx, 20h ; ' '
0x140005b49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005b4e  mov     rcx, rbx
0x140005b51  test    rbx, rbx
0x140005b54  jnz     short loc_140005B41
0x140005b56  mov     rcx, [rdi+8]; Block
0x140005b5a  mov     edx, 20h ; ' '
0x140005b5f  mov     rbx, [rsp+28h+arg_8]
0x140005b64  add     rsp, 20h
0x140005b68  pop     rdi
0x140005b69  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
