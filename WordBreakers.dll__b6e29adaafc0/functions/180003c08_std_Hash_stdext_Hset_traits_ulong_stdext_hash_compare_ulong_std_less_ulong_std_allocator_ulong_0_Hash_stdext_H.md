# std::_Hash<stdext::_Hset_traits<ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<ulong>,0>>::~_Hash<stdext::_Hset_traits<ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<ulong>,0>>(void)

- ea: `0x180003c08`
- end: `0x180003c76`
- name: `??1?$_Hash@V?$_Hset_traits@KV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@K@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000bdd0`

## callees

- `0x180003c08`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003c20`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c54`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c20`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c54`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003c6f`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<stdext::_Hset_traits<unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<unsigned long>,0>>(
        __int64 a1)
{
  void *v2; // rcx
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v2 = *(void **)(a1 + 16);
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
  }
  v3 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  v4 = *(_QWORD **)a1;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v3 != v4 )
  {
    do
    {
      v5 = (_QWORD *)*v3;
      operator delete(v3);
      v4 = *(_QWORD **)a1;
      v3 = v5;
    }
    while ( v5 != *(_QWORD **)a1 );
  }
  operator delete(v4);
}

```

## disassembly

```asm
0x180003c08  mov     [rsp+arg_0], rbx
0x180003c0d  push    rdi
0x180003c0e  sub     rsp, 20h
0x180003c12  mov     rdi, rcx
0x180003c15  xor     ebx, ebx
0x180003c17  mov     rcx, [rcx+10h]
0x180003c1b  test    rcx, rcx
0x180003c1e  jz      short loc_180003C32
0x180003c20  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003c26  mov     [rdi+10h], rbx
0x180003c2a  mov     [rdi+18h], rbx
0x180003c2e  mov     [rdi+20h], rbx
0x180003c32  mov     rax, [rdi]
0x180003c35  mov     rdx, [rax]
0x180003c38  mov     [rax], rax
0x180003c3b  mov     rax, [rdi]
0x180003c3e  mov     [rax+8], rax
0x180003c42  mov     rcx, [rdi]
0x180003c45  mov     [rdi+8], rbx
0x180003c49  cmp     rdx, rcx
0x180003c4c  jz      short loc_180003C65
0x180003c4e  mov     rbx, [rdx]
0x180003c51  mov     rcx, rdx
0x180003c54  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003c5a  mov     rcx, [rdi]
0x180003c5d  mov     rdx, rbx
0x180003c60  cmp     rbx, rcx
0x180003c63  jnz     short loc_180003C4E
0x180003c65  mov     rbx, [rsp+28h+arg_0]
0x180003c6a  add     rsp, 20h
0x180003c6e  pop     rdi
0x180003c6f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
