# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::find(_GUID const &)

- ea: `0x18000e1a4`
- end: `0x18000e238`
- name: `?find@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@AEBU_GUID@@@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aa6c`

## callees

- `0x18000ce94`
- `0x18000e1a4`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::find(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // r10
  _QWORD *i; // r9
  _QWORD *v10; // rcx
  __int64 v11; // rax
  _QWORD *result; // rax

  v6 = std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Hashval(
         (__int64)a1,
         (__int64)a3);
  v7 = a1[2];
  v8 = (_QWORD *)*a1;
  for ( i = *(_QWORD **)(v7 + 16 * v6); ; i = (_QWORD *)*i )
  {
    v10 = *(_QWORD **)(v7 + 16 * v6) == v8 ? (_QWORD *)*a1 : **(_QWORD ***)(v7 + 16 * v6 + 8);
    if ( i == v10 )
      break;
    if ( i[2] == *a3 && i[3] == a3[1] )
    {
      v11 = *a3 - i[2];
      if ( *a3 == i[2] )
        v11 = a3[1] - i[3];
      if ( !v11 )
        v8 = i;
      break;
    }
  }
  result = a2;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x18000e1a4  mov     [rsp+arg_0], rbx
0x18000e1a9  mov     [rsp+arg_8], rsi
0x18000e1ae  push    rdi
0x18000e1af  sub     rsp, 20h
0x18000e1b3  mov     rsi, rdx
0x18000e1b6  mov     rdi, r8
0x18000e1b9  mov     rdx, r8
0x18000e1bc  mov     rbx, rcx
0x18000e1bf  call    ?_Hashval@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEBA_KAEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Hashval(_GUID const &)
0x18000e1c4  mov     r8, [rbx+10h]
0x18000e1c8  mov     rdx, rax
0x18000e1cb  mov     r10, [rbx]
0x18000e1ce  add     rdx, rdx
0x18000e1d1  mov     r9, [r8+rdx*8]
0x18000e1d5  cmp     [r8+rdx*8], r10
0x18000e1d9  jnz     short loc_18000E1E0
0x18000e1db  mov     rcx, r10
0x18000e1de  jmp     short loc_18000E1E8
0x18000e1e0  mov     rcx, [r8+rdx*8+8]
0x18000e1e5  mov     rcx, [rcx]
0x18000e1e8  cmp     r9, rcx
0x18000e1eb  jz      short loc_18000E222
0x18000e1ed  mov     rax, [r9+10h]
0x18000e1f1  cmp     rax, [rdi]
0x18000e1f4  jnz     short loc_18000E200
0x18000e1f6  mov     rax, [r9+18h]
0x18000e1fa  cmp     rax, [rdi+8]
0x18000e1fe  jz      short loc_18000E205
0x18000e200  mov     r9, [r9]
0x18000e203  jmp     short loc_18000E1D5
0x18000e205  mov     rax, [rdi]
0x18000e208  sub     rax, [r9+10h]
0x18000e20c  jnz     short loc_18000E216
0x18000e20e  mov     rax, [rdi+8]
0x18000e212  sub     rax, [r9+18h]
0x18000e216  test    rax, rax
0x18000e219  setnz   al
0x18000e21c  test    al, al
0x18000e21e  cmovz   r10, r9
0x18000e222  mov     rbx, [rsp+28h+arg_0]
0x18000e227  mov     rax, rsi
0x18000e22a  mov     [rsi], r10
0x18000e22d  mov     rsi, [rsp+28h+arg_8]
0x18000e232  add     rsp, 20h
0x18000e236  pop     rdi
0x18000e237  retn
```
