# std::vector<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>,std::allocator<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>>>::_Reallocate(unsigned __int64)

- ea: `0x18002450c`
- end: `0x1800245b7`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800227b4`

## callees

- `0x1800020d0`
- `0x180002278`
- `0x18001ecc0`
- `0x180022770`
- `0x18002450c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002458d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002458d`

## pseudocode

```c
char *__fastcall std::vector<std::unique_ptr<ProvPackageInfo>>::_Reallocate(_QWORD *a1, unsigned __int64 a2)
{
  char *v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rsi
  char *result; // rax
  void *v8; // [rsp+68h] [rbp+10h]

  v3 = 0;
  v8 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = 8 * a2, v3 = (char *)operator new(8 * a2), (v8 = v3) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  try
  {
    std::_Uninit_move<std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *,std::allocator<std::unique_ptr<ProvPackageInfo>>,std::unique_ptr<ProvPackageInfo>>(
      *a1,
      a1[1],
      v3);
  }
  catch ( ... )
  {
    operator delete(v8);
    throw;
  }
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( *a1 )
  {
    std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(v5, (ProvPackageInfo **)*a1, (ProvPackageInfo **)a1[1]);
    operator delete((void *)*a1);
  }
  a1[2] = &v3[v4];
  result = &v3[8 * v6];
  a1[1] = result;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18002450c  push    rbx
0x18002450e  push    rsi
0x18002450f  push    rdi
0x180024510  push    r14
0x180024512  sub     rsp, 38h
0x180024516  mov     rdi, rcx
0x180024519  xor     ebx, ebx
0x18002451b  mov     [rsp+58h+arg_8], rbx
0x180024520  test    rdx, rdx
0x180024523  jz      short loc_180024557
0x180024525  mov     rax, 1FFFFFFFFFFFFFFFh
0x18002452f  cmp     rdx, rax
0x180024532  ja      short loc_180024551
0x180024534  lea     r14, ds:0[rdx*8]
0x18002453c  mov     rcx, r14; Size
0x18002453f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024544  mov     rbx, rax
0x180024547  mov     [rsp+58h+arg_8], rax
0x18002454c  test    rax, rax
0x18002454f  jnz     short loc_18002455F
0x180024551  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180024557  lea     r14, ds:0[rdx*8]
0x18002455f  mov     r8, rbx
0x180024562  mov     rdx, [rdi+8]
0x180024566  mov     rcx, [rdi]
0x180024569  call    ??$_Uninit_move@PEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *,std::allocator<std::unique_ptr<ProvPackageInfo>>,std::unique_ptr<ProvPackageInfo>>(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackageInfo>>> &,std::unique_ptr<ProvPackageInfo> *,std::_Nonscalar_ptr_iterator_tag)
0x18002456e  nop
0x18002456f  mov     rdx, [rdi]
0x180024572  mov     r8, [rdi+8]
0x180024576  mov     rsi, r8
0x180024579  sub     rsi, rdx
0x18002457c  sar     rsi, 3
0x180024580  test    rdx, rdx
0x180024583  jz      short loc_180024599
0x180024585  call    ?_Destroy@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *)
0x18002458a  mov     rcx, [rdi]
0x18002458d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180024594  nop     dword ptr [rax+rax+00h]
0x180024599  lea     rax, [r14+rbx]
0x18002459d  mov     [rdi+10h], rax
0x1800245a1  lea     rax, [rbx+rsi*8]
0x1800245a5  mov     [rdi+8], rax
0x1800245a9  mov     [rdi], rbx
0x1800245ac  add     rsp, 38h
0x1800245b0  pop     r14
0x1800245b2  pop     rdi
0x1800245b3  pop     rsi
0x1800245b4  pop     rbx
0x1800245b5  retn
```
