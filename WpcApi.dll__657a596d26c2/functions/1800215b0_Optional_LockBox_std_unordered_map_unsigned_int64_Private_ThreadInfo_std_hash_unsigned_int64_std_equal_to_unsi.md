# Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>,4294967295>>::Reset(void)

- ea: `0x1800215b0`
- end: `0x180021626`
- name: `?Reset@?$Optional@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180021114`
- `0x180021540`
- `0x180021c30`

## callees

- `0x1800036e4`
- `0x1800211b0`
- `0x1800215b0`

## pseudocode

```c
void __fastcall Optional<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::Reset(
        __int64 a1)
{
  __int64 v1; // rdi
  _QWORD **v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v1 = *(_QWORD *)(a1 + 88);
  if ( v1 )
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>((char **)(v1 + 40));
    v3 = *(_QWORD ***)(v1 + 24);
    *v3[1] = 0;
    v4 = *v3;
    if ( *v3 )
    {
      do
      {
        v5 = (_QWORD *)*v4;
        operator delete(v4);
        v4 = v5;
      }
      while ( v5 );
    }
    operator delete(*(void **)(v1 + 24));
    *(_QWORD *)(a1 + 88) = 0;
  }
}

```

## disassembly

```asm
0x1800215b0  mov     [rsp+arg_0], rbx
0x1800215b5  mov     [rsp+arg_8], rsi
0x1800215ba  push    rdi
0x1800215bb  sub     rsp, 20h
0x1800215bf  mov     rdi, [rcx+58h]
0x1800215c3  mov     rsi, rcx
0x1800215c6  test    rdi, rdi
0x1800215c9  jz      short loc_180021616
0x1800215cb  lea     rcx, [rdi+28h]
0x1800215cf  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>(void)
0x1800215d4  mov     rdx, [rdi+18h]
0x1800215d8  mov     rax, [rdx+8]
0x1800215dc  mov     qword ptr [rax], 0
0x1800215e3  mov     rcx, [rdx]; Block
0x1800215e6  test    rcx, rcx
0x1800215e9  jz      short loc_180021600
0x1800215eb  mov     rbx, [rcx]
0x1800215ee  mov     edx, 20h ; ' '
0x1800215f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800215f8  mov     rcx, rbx
0x1800215fb  test    rbx, rbx
0x1800215fe  jnz     short loc_1800215EB
0x180021600  mov     rcx, [rdi+18h]; Block
0x180021604  mov     edx, 20h ; ' '
0x180021609  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002160e  mov     qword ptr [rsi+58h], 0
0x180021616  mov     rbx, [rsp+28h+arg_0]
0x18002161b  mov     rsi, [rsp+28h+arg_8]
0x180021620  add     rsp, 20h
0x180021624  pop     rdi
0x180021625  retn
```
