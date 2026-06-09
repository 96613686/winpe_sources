# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x180015e80`
- end: `0x180015f1d`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `157`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015ce8`
- `0x180028979`
- `0x180028baf`

## callees

- `0x180015e80`
- `0x1800268f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(
        __int64 a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  void *v4; // rcx
  _QWORD **v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  v2 = *(_QWORD **)(a1 + 16);
  v3 = (_QWORD *)*v2;
  if ( (_QWORD *)*v2 != v2 )
  {
    do
    {
      operator delete((void *)v3[2]);
      v3 = (_QWORD *)*v3;
    }
    while ( v3 != *(_QWORD **)(a1 + 16) );
  }
  v4 = *(void **)(a1 + 40);
  if ( v4 )
    operator delete(v4);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v5 = *(_QWORD ***)(a1 + 16);
  v6 = *v5;
  *v5 = v5;
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 24) = 0;
  if ( v6 != *(_QWORD **)(a1 + 16) )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      operator delete(v6);
      v6 = v7;
    }
    while ( v7 != *(_QWORD **)(a1 + 16) );
  }
  operator delete(*(void **)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180015e80  mov     [rsp+arg_0], rcx
0x180015e85  push    rdi
0x180015e86  sub     rsp, 30h
0x180015e8a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015e93  mov     [rsp+38h+arg_8], rbx
0x180015e98  mov     rdi, rcx
0x180015e9b  mov     rax, [rcx+10h]
0x180015e9f  mov     rbx, [rax]
0x180015ea2  cmp     rbx, rax
0x180015ea5  jz      short loc_180015EB9
0x180015ea7  mov     rcx, [rbx+10h]; Block
0x180015eab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015eb0  mov     rbx, [rbx]
0x180015eb3  cmp     rbx, [rdi+10h]
0x180015eb7  jnz     short loc_180015EA7
0x180015eb9  mov     rcx, [rdi+28h]; Block
0x180015ebd  test    rcx, rcx
0x180015ec0  jz      short loc_180015EC7
0x180015ec2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015ec7  and     qword ptr [rdi+28h], 0
0x180015ecc  and     qword ptr [rdi+30h], 0
0x180015ed1  and     qword ptr [rdi+38h], 0
0x180015ed6  mov     rax, [rdi+10h]
0x180015eda  mov     rcx, [rax]; Block
0x180015edd  mov     [rax], rax
0x180015ee0  mov     rax, [rdi+10h]
0x180015ee4  mov     [rax+8], rax
0x180015ee8  and     qword ptr [rdi+18h], 0
0x180015eed  cmp     rcx, [rdi+10h]
0x180015ef1  jz      short loc_180015F04
0x180015ef3  mov     rbx, [rcx]
0x180015ef6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015efb  mov     rcx, rbx
0x180015efe  cmp     rbx, [rdi+10h]
0x180015f02  jnz     short loc_180015EF3
0x180015f04  mov     rcx, [rdi+10h]; Block
0x180015f08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015f0d  and     qword ptr [rdi+10h], 0
0x180015f12  mov     rbx, [rsp+38h+arg_8]
0x180015f17  add     rsp, 30h
0x180015f1b  pop     rdi
0x180015f1c  retn
```
