# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x1800282b4`
- end: `0x180028345`
- name: `??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a528`

## callees

- `0x180001bf8`
- `0x1800282b4`

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
        operator delete(v3);
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
0x1800282b4  mov     [rsp+arg_0], rbx
0x1800282b9  push    rdi
0x1800282ba  sub     rsp, 20h
0x1800282be  mov     rbx, [rcx]
0x1800282c1  test    rbx, rbx
0x1800282c4  jz      short loc_180028339
0x1800282c6  cmp     qword ptr [rbx+10h], 0
0x1800282cb  jz      short loc_180028339
0x1800282cd  mov     rcx, [rbx+8]
0x1800282d1  mov     rax, [rcx+8]
0x1800282d5  mov     qword ptr [rax], 0
0x1800282dc  mov     rcx, [rcx]; void *
0x1800282df  test    rcx, rcx
0x1800282e2  jz      short loc_1800282F9
0x1800282e4  mov     rdi, [rcx]
0x1800282e7  mov     edx, 18h; unsigned __int64
0x1800282ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800282f1  mov     rcx, rdi
0x1800282f4  test    rdi, rdi
0x1800282f7  jnz     short loc_1800282E4
0x1800282f9  mov     rax, [rbx+8]
0x1800282fd  xor     edx, edx
0x1800282ff  mov     [rax], rax
0x180028302  mov     rax, [rbx+8]
0x180028306  mov     [rax+8], rax
0x18002830a  mov     qword ptr [rbx+10h], 0
0x180028312  mov     rdi, [rbx+18h]
0x180028316  mov     rcx, [rbx+20h]
0x18002831a  sub     rcx, rdi
0x18002831d  add     rcx, 7
0x180028321  shr     rcx, 3
0x180028325  cmp     rdi, [rbx+20h]
0x180028329  cmova   rcx, rdx
0x18002832d  test    rcx, rcx
0x180028330  jz      short loc_180028339
0x180028332  mov     rax, [rbx+8]
0x180028336  rep stosq
0x180028339  mov     rbx, [rsp+28h+arg_0]
0x18002833e  add     rsp, 20h
0x180028342  pop     rdi
0x180028343  retn
```
