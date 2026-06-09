# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180027130`
- end: `0x1800271c0`
- name: `??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029350`

## callees

- `0x180001bc8`
- `0x180027130`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  _QWORD **v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = (_QWORD **)v1[1];
    *v2[1] = 0;
    v3 = *v2;
    if ( v3 )
    {
      do
      {
        v4 = (_QWORD *)*v3;
        operator delete(v3, 0x18u);
        v3 = v4;
      }
      while ( v4 );
    }
    *(_QWORD *)v1[1] = v1[1];
    *(_QWORD *)(v1[1] + 8) = v1[1];
    v1[2] = 0;
    v5 = (void *)v1[3];
    v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
    if ( (unsigned __int64)v5 > v1[4] )
      v6 = 0;
    if ( v6 )
      memset64(v5, v1[1], v6);
  }
}

```

## disassembly

```asm
0x180027130  mov     [rsp+arg_0], rbx
0x180027135  push    rdi
0x180027136  sub     rsp, 20h
0x18002713a  mov     rbx, [rcx]
0x18002713d  test    rbx, rbx
0x180027140  jz      short loc_1800271B5
0x180027142  cmp     qword ptr [rbx+10h], 0
0x180027147  jz      short loc_1800271B5
0x180027149  mov     rcx, [rbx+8]
0x18002714d  mov     rax, [rcx+8]
0x180027151  mov     qword ptr [rax], 0
0x180027158  mov     rcx, [rcx]; void *
0x18002715b  test    rcx, rcx
0x18002715e  jz      short loc_180027175
0x180027160  mov     rdi, [rcx]
0x180027163  mov     edx, 18h; unsigned __int64
0x180027168  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002716d  mov     rcx, rdi
0x180027170  test    rdi, rdi
0x180027173  jnz     short loc_180027160
0x180027175  mov     rax, [rbx+8]
0x180027179  xor     edx, edx
0x18002717b  mov     [rax], rax
0x18002717e  mov     rax, [rbx+8]
0x180027182  mov     [rax+8], rax
0x180027186  mov     qword ptr [rbx+10h], 0
0x18002718e  mov     rdi, [rbx+18h]
0x180027192  mov     rcx, [rbx+20h]
0x180027196  sub     rcx, rdi
0x180027199  add     rcx, 7
0x18002719d  shr     rcx, 3
0x1800271a1  cmp     rdi, [rbx+20h]
0x1800271a5  cmova   rcx, rdx
0x1800271a9  test    rcx, rcx
0x1800271ac  jz      short loc_1800271B5
0x1800271ae  mov     rax, [rbx+8]
0x1800271b2  rep stosq
0x1800271b5  mov     rbx, [rsp+28h+arg_0]
0x1800271ba  add     rsp, 20h
0x1800271be  pop     rdi
0x1800271bf  retn
```
