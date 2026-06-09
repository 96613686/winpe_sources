# std::vector<std::shared_ptr<XgcSolidPath>,std::allocator<std::shared_ptr<XgcSolidPath>>>::_Emplace_reallocate<std::shared_ptr<XgcSolidPath> const &>(std::shared_ptr<XgcSolidPath> * const,std::shared_ptr<XgcSolidPath> const &)

- ea: `0x18002851c`
- end: `0x180028678`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@VXgcSolidPath@@@std@@@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VXgcSolidPath@@@1@QEAV21@AEBV21@@Z`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002a518`

## callees

- `0x18000d900`
- `0x18000da2c`
- `0x18000da60`
- `0x18000ddf8`
- `0x18000de24`
- `0x18000e8ec`
- `0x180011ee0`
- `0x18002851c`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<XgcSolidPath>>::_Emplace_reallocate<std::shared_ptr<XgcSolidPath> const &>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rsi
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 size_of; // rax
  __int64 v13; // rax
  _QWORD *v14; // r14
  __int64 v15; // rbp
  __int64 v16; // rax
  _QWORD *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 4;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<Gdiplus::Color>::_Xlength();
  v8 = a2 - *a1;
  v9 = v5 + 1;
  v10 = (a1[2] - *a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v11 + v10;
    if ( v11 + v10 < v9 )
      v3 = v9;
  }
  size_of = std::_Get_size_of_n<16>(v3);
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v23[0] = a1;
  v14 = (_QWORD *)(v13 + (v8 & 0xFFFFFFFFFFFFFFF0uLL));
  v23[2] = v3;
  v15 = v13;
  *v14 = 0;
  v14[1] = 0;
  v16 = a3[1];
  v25 = v14 + 2;
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  v17 = (_QWORD *)v15;
  *v14 = *a3;
  v14[1] = a3[1];
  v18 = a1[1];
  v19 = *a1;
  v24 = v14;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move<std::shared_ptr<IXpsOMVisual> *,std::allocator<std::shared_ptr<IXpsOMVisual>>>(
      v19,
      a2,
      v15);
    v18 = a1[1];
    v17 = v14 + 2;
    v19 = a2;
    v24 = (_QWORD *)v15;
  }
  std::_Uninitialized_move<std::shared_ptr<IXpsOMVisual> *,std::allocator<std::shared_ptr<IXpsOMVisual>>>(v19, v18, v17);
  v20 = *a1;
  v23[1] = 0;
  if ( v20 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<IWICColorTransform>>>(v20, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL, v21);
  }
  *a1 = v15;
  a1[1] = v15 + 16 * v9;
  a1[2] = v15 + 16 * v3;
  std::vector<std::shared_ptr<XgcSolidPath>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v14;
}

```

## disassembly

```asm
0x18002851c  push    rbx
0x18002851e  push    rbp
0x18002851f  push    rsi
0x180028520  push    rdi
0x180028521  push    r12
0x180028523  push    r13
0x180028525  push    r14
0x180028527  push    r15
0x180028529  sub     rsp, 58h
0x18002852d  mov     rsi, [rcx+8]
0x180028531  mov     rdi, 0FFFFFFFFFFFFFFFh
0x18002853b  sub     rsi, [rcx]
0x18002853e  mov     r12, r8
0x180028541  sar     rsi, 4
0x180028545  mov     r15, rdx
0x180028548  mov     rbx, rcx
0x18002854b  cmp     rsi, rdi
0x18002854e  jz      loc_180028672
0x180028554  mov     r14, rdx
0x180028557  mov     rax, rdi
0x18002855a  sub     r14, [rcx]
0x18002855d  mov     rcx, [rcx+10h]
0x180028561  inc     rsi
0x180028564  sub     rcx, [rbx]
0x180028567  sar     rcx, 4
0x18002856b  mov     rdx, rcx
0x18002856e  shr     rdx, 1
0x180028571  sub     rax, rdx
0x180028574  cmp     rcx, rax
0x180028577  ja      short loc_180028584
0x180028579  lea     rdi, [rdx+rcx]
0x18002857d  cmp     rdi, rsi
0x180028580  cmovb   rdi, rsi
0x180028584  mov     rcx, rdi
0x180028587  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18002858c  mov     rcx, rax
0x18002858f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180028594  and     r14, 0FFFFFFFFFFFFFFF0h
0x180028598  mov     [rsp+98h+var_78], rbx
0x18002859d  add     r14, rax
0x1800285a0  mov     [rsp+98h+var_68], rdi
0x1800285a5  mov     rbp, rax
0x1800285a8  mov     qword ptr [r14], 0
0x1800285af  lea     r13, [r14+10h]
0x1800285b3  mov     qword ptr [r14+8], 0
0x1800285bb  mov     rax, [r12+8]
0x1800285c0  mov     [rsp+98h+var_58], r13
0x1800285c5  test    rax, rax
0x1800285c8  jz      short loc_1800285CE
0x1800285ca  lock inc dword ptr [rax+8]
0x1800285ce  mov     rax, [r12]
0x1800285d2  mov     r8, rbp
0x1800285d5  mov     [r14], rax
0x1800285d8  mov     rax, [r12+8]
0x1800285dd  mov     [r14+8], rax
0x1800285e1  mov     rdx, [rbx+8]
0x1800285e5  mov     rcx, [rbx]
0x1800285e8  mov     [rsp+98h+var_60], r14
0x1800285ed  cmp     r15, rdx
0x1800285f0  jz      short loc_180028609
0x1800285f2  mov     rdx, r15
0x1800285f5  call    ??$_Uninitialized_move@PEAV?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@YAPEAV?$shared_ptr@UIXpsOMVisual@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<IXpsOMVisual> *,std::allocator<std::shared_ptr<IXpsOMVisual>>>(std::shared_ptr<IXpsOMVisual> * const,std::shared_ptr<IXpsOMVisual> * const,std::shared_ptr<IXpsOMVisual> *,std::allocator<std::shared_ptr<IXpsOMVisual>> &)
0x1800285fa  mov     rdx, [rbx+8]
0x1800285fe  mov     r8, r13
0x180028601  mov     rcx, r15
0x180028604  mov     [rsp+98h+var_60], rbp
0x180028609  call    ??$_Uninitialized_move@PEAV?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@YAPEAV?$shared_ptr@UIXpsOMVisual@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<IXpsOMVisual> *,std::allocator<std::shared_ptr<IXpsOMVisual>>>(std::shared_ptr<IXpsOMVisual> * const,std::shared_ptr<IXpsOMVisual> * const,std::shared_ptr<IXpsOMVisual> *,std::allocator<std::shared_ptr<IXpsOMVisual>> &)
0x18002860e  mov     rcx, [rbx]
0x180028611  mov     [rsp+98h+var_70], 0
0x18002861a  test    rcx, rcx
0x18002861d  jz      short loc_18002863B
0x18002861f  mov     rdx, [rbx+8]
0x180028623  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@UIWICColorTransform@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@UIWICColorTransform@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@UIWICColorTransform@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<IWICColorTransform>>>(std::shared_ptr<IWICColorTransform> *,std::shared_ptr<IWICColorTransform> * const,std::allocator<std::shared_ptr<IWICColorTransform>> &)
0x180028628  mov     rdx, [rbx+10h]
0x18002862c  sub     rdx, [rbx]
0x18002862f  mov     rcx, [rbx]
0x180028632  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180028636  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002863b  mov     [rbx], rbp
0x18002863e  lea     rcx, [rsp+98h+var_78]
0x180028643  shl     rsi, 4
0x180028647  shl     rdi, 4
0x18002864b  add     rsi, rbp
0x18002864e  add     rdi, rbp
0x180028651  mov     [rbx+8], rsi
0x180028655  mov     [rbx+10h], rdi
0x180028659  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<XgcSolidPath>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002865e  mov     rax, r14
0x180028661  add     rsp, 58h
0x180028665  pop     r15
0x180028667  pop     r14
0x180028669  pop     r13
0x18002866b  pop     r12
0x18002866d  pop     rdi
0x18002866e  pop     rsi
0x18002866f  pop     rbp
0x180028670  pop     rbx
0x180028671  retn
0x180028672  call    ?_Xlength@?$vector@VColor@Gdiplus@@V?$allocator@VColor@Gdiplus@@@std@@@std@@CAXXZ; std::vector<Gdiplus::Color>::_Xlength(void)
```
