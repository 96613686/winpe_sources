# std::unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>::~unordered_map<unsigned __int64,Private::ThreadInfo *,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>(void)

- ea: `0x180021278`
- end: `0x1800212d2`
- name: `??1?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002a6f0`
- `0x18002a72e`

## callees

- `0x1800036e4`
- `0x1800211b0`
- `0x180021278`

## pseudocode

```c
void __fastcall std::unordered_map<unsigned __int64,Private::ThreadInfo *>::~unordered_map<unsigned __int64,Private::ThreadInfo *>(
        __int64 a1)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>((char **)(a1 + 24));
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
0x180021278  mov     [rsp+arg_0], rbx
0x18002127d  push    rdi
0x18002127e  sub     rsp, 20h
0x180021282  mov     rdi, rcx
0x180021285  add     rcx, 18h
0x180021289  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>(void)
0x18002128e  mov     rdx, [rdi+8]
0x180021292  mov     rax, [rdx+8]
0x180021296  mov     qword ptr [rax], 0
0x18002129d  mov     rcx, [rdx]; Block
0x1800212a0  test    rcx, rcx
0x1800212a3  jz      short loc_1800212BA
0x1800212a5  mov     rbx, [rcx]
0x1800212a8  mov     edx, 20h ; ' '
0x1800212ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800212b2  mov     rcx, rbx
0x1800212b5  test    rbx, rbx
0x1800212b8  jnz     short loc_1800212A5
0x1800212ba  mov     rcx, [rdi+8]; Block
0x1800212be  mov     edx, 20h ; ' '
0x1800212c3  mov     rbx, [rsp+28h+arg_0]
0x1800212c8  add     rsp, 20h
0x1800212cc  pop     rdi
0x1800212cd  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
