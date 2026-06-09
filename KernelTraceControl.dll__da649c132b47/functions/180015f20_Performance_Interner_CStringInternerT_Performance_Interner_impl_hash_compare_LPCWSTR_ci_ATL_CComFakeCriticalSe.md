# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x180015f20`
- end: `0x180016041`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `289`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800149c4`

## callees

- `0x180013ac8`
- `0x180015f20`
- `0x1800160b8`
- `0x1800268fc`
- `0x1800278f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015f9a`
- `msvcrt!_wcsicmp` at `0x180015fbb`
- `msvcrt!_wcsicmp` at `0x180015f9a`
- `msvcrt!_wcsicmp` at `0x180015fbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wchar_t *__fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(
        _QWORD *a1,
        const wchar_t *a2)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rsi
  __int64 v7; // rax
  __int64 *v8; // rbx
  __int64 v9; // rbx
  unsigned __int64 v10; // rbx
  _BYTE v11[24]; // [rsp+38h] [rbp-30h] BYREF
  wchar_t *v12; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v5 = a1[8];
  v6 = v5 & Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, a2);
  if ( a1[9] <= v6 )
    v6 += -1LL - (v5 >> 1);
  v7 = a1[5];
  v8 = *(__int64 **)(v7 + 8 * v6);
  while ( v8 != *(__int64 **)(v7 + 8 * v6 + 8) )
  {
    if ( _wcsicmp((const wchar_t *)v8[2], a2) >= 0 )
    {
      if ( _wcsicmp(a2, (const wchar_t *)v8[2]) >= 0 )
        goto LABEL_12;
      break;
    }
    v8 = (__int64 *)*v8;
    v7 = a1[5];
  }
  v8 = (__int64 *)a1[2];
LABEL_12:
  if ( v8 != (__int64 *)a1[2] )
    return (wchar_t *)v8[2];
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  v12 = (wchar_t *)operator new[](saturated_mul(v10, 2u));
  memcpy_0(v12, a2, 2 * v10);
  try
  {
    stdext::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::insert(
      (unsigned __int64)a1,
      (__int64)v11,
      (const wchar_t **)&v12);
  }
  catch ( ... )
  {
    operator delete(v12);
    throw;
  }
  return v12;
}

```

## disassembly

```asm
0x180015f20  mov     rax, rsp
0x180015f23  push    r12
0x180015f25  push    r14
0x180015f27  push    r15
0x180015f29  sub     rsp, 50h
0x180015f2d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180015f35  mov     [rax+8], rbx
0x180015f39  mov     [rax+18h], rsi
0x180015f3d  mov     [rax+20h], rdi
0x180015f41  mov     r14, rdx
0x180015f44  mov     rdi, rcx
0x180015f47  xor     r12d, r12d
0x180015f4a  test    rdx, rdx
0x180015f4d  jnz     short loc_180015F56
0x180015f4f  xor     eax, eax
0x180015f51  jmp     loc_180016026
0x180015f56  lea     rax, [rcx+50h]
0x180015f5a  mov     [rsp+68h+var_40], rax
0x180015f5f  mov     [rsp+68h+var_38], 1
0x180015f64  mov     rbx, [rcx+40h]
0x180015f68  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180015f6d  mov     rsi, rax
0x180015f70  and     rsi, rbx
0x180015f73  or      r15, 0FFFFFFFFFFFFFFFFh
0x180015f77  cmp     [rdi+48h], rsi
0x180015f7b  ja      short loc_180015F89
0x180015f7d  shr     rbx, 1
0x180015f80  mov     rcx, r15
0x180015f83  sub     rcx, rbx
0x180015f86  add     rsi, rcx
0x180015f89  mov     rax, [rdi+28h]
0x180015f8d  mov     rbx, [rax+rsi*8]
0x180015f91  jmp     short loc_180015FAB
0x180015f93  mov     rdx, r14; String2
0x180015f96  mov     rcx, [rbx+10h]; String1
0x180015f9a  call    cs:__imp__wcsicmp
0x180015fa0  test    eax, eax
0x180015fa2  jns     short loc_180015FB4
0x180015fa4  mov     rbx, [rbx]
0x180015fa7  mov     rax, [rdi+28h]
0x180015fab  cmp     rbx, [rax+rsi*8+8]
0x180015fb0  jnz     short loc_180015F93
0x180015fb2  jmp     short loc_180015FC5
0x180015fb4  mov     rdx, [rbx+10h]; String2
0x180015fb8  mov     rcx, r14; String1
0x180015fbb  call    cs:__imp__wcsicmp
0x180015fc1  test    eax, eax
0x180015fc3  jns     short loc_180015FC9
0x180015fc5  mov     rbx, [rdi+10h]
0x180015fc9  cmp     rbx, [rdi+10h]
0x180015fcd  jz      short loc_180015FD5
0x180015fcf  mov     rax, [rbx+10h]
0x180015fd3  jmp     short loc_180016026
0x180015fd5  mov     rbx, r15
0x180015fd8  inc     rbx
0x180015fdb  cmp     [r14+rbx*2], r12w
0x180015fe0  jnz     short loc_180015FD8
0x180015fe2  inc     rbx
0x180015fe5  mov     eax, 2
0x180015fea  mul     rbx
0x180015fed  cmovo   rax, r15
0x180015ff1  mov     rcx, rax; unsigned __int64
0x180015ff4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180015ff9  mov     [rsp+68h+arg_8], rax
0x180015ffe  lea     r8, [rbx+rbx]; Size
0x180016002  mov     rdx, r14; Src
0x180016005  mov     rcx, rax; void *
0x180016008  call    memcpy_0
0x18001600d  nop
0x18001600e  lea     r8, [rsp+68h+arg_8]
0x180016013  lea     rdx, [rsp+68h+var_30]
0x180016018  mov     rcx, rdi
0x18001601b  call    ?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@stdext@@QEAA?AU?$pair@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@_N@std@@AEBQEBG@Z; stdext::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)
0x180016020  nop
0x180016021  mov     rax, [rsp+68h+arg_8]
0x180016026  lea     r11, [rsp+68h+var_18]
0x18001602b  mov     rbx, [r11+20h]
0x18001602f  mov     rsi, [r11+30h]
0x180016033  mov     rdi, [r11+38h]
0x180016037  mov     rsp, r11
0x18001603a  pop     r15
0x18001603c  pop     r14
0x18001603e  pop     r12
0x180016040  retn
```
