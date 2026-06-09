# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x18000d294`
- end: `0x18000d4b5`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z`
- size: `545`
- prototype: `Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *this, const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015c0c`

## callees

- `0x1800018a0`
- `0x1800027b1`
- `0x1800027bd`
- `0x180003bb8`
- `0x18000439c`
- `0x18000458c`
- `0x18000be50`
- `0x18000d074`
- `0x18000d294`
- `0x18000e0d8`
- `0x1800114bc`
- `0x180015b68`

## pseudocode

```c
Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a2)
{
  size_t v4; // rbx
  void *v5; // rax
  void *v6; // rcx
  _QWORD *v7; // rax
  char *v8; // rdi
  const void *v9; // rdx
  size_t v10; // rbx
  __int64 i; // rdi
  __int64 v12; // rax
  Microsoft::Windows::Performance::CCvDDCache::CCvDD *v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = this;
  std::wstring::wstring((__int64)this, (__int64)a2);
  std::wstring::wstring((__int64)this + 32, (__int64)a2 + 32);
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 16);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  v4 = *((_QWORD *)a2 + 13) - *((_QWORD *)a2 + 12);
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<unsigned int>::_Xlength();
    if ( v4 < 0x1000 )
    {
      v7 = operator new(v4);
    }
    else
    {
      if ( v4 + 39 < v4 )
        __scrt_throw_std_bad_array_new_length();
      v5 = operator new(v4 + 39);
      v6 = v5;
      if ( !v5 )
        __fastfail(5u);
      v7 = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v7 - 1) = v6;
    }
    *((_QWORD *)this + 12) = v7;
    *((_QWORD *)this + 13) = v7;
    *((_QWORD *)this + 14) = (char *)v7 + v4;
    v8 = (char *)*((_QWORD *)this + 12);
    v9 = (const void *)*((_QWORD *)a2 + 12);
    v10 = *((_QWORD *)a2 + 13) - (_QWORD)v9;
    memmove_0(v8, v9, v10);
    *((_QWORD *)this + 13) = &v8[v10];
    v14 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v14);
  }
  *((_WORD *)this + 60) = *((_WORD *)a2 + 60);
  *((_WORD *)this + 61) = *((_WORD *)a2 + 61);
  *((_BYTE *)this + 124) = *((_BYTE *)a2 + 124);
  *((_DWORD *)this + 32) = *((_DWORD *)a2 + 32);
  *((_DWORD *)this + 33) = *((_DWORD *)a2 + 33);
  *((_DWORD *)this + 34) = *((_DWORD *)a2 + 34);
  if ( *((_DWORD *)this + 16) )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate((char *)this + 72, *((unsigned int *)this + 16))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate((char *)this + 80, *((unsigned int *)this + 16))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(
                             (char *)this + 88,
                             *((unsigned int *)this + 16)) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 16); i = (unsigned int)(i + 1) )
    {
      v12 = *((_QWORD *)a2 + 10);
      if ( *(_DWORD *)(v12 + 4 * i) > 0x628u )
        ATL::AtlThrowImpl(-2147418113);
      memcpy_0(
        (void *)(*((_QWORD *)this + 9) + 1576LL * (unsigned int)i),
        (const void *)(1576LL * (unsigned int)i + *((_QWORD *)a2 + 9)),
        *(unsigned int *)(v12 + 4 * i));
      *(_QWORD *)(*((_QWORD *)this + 11) + 8 * i) = *(_QWORD *)(*((_QWORD *)a2 + 11) + 8 * i);
      *(_DWORD *)(*((_QWORD *)this + 10) + 4 * i) = *(_DWORD *)(*((_QWORD *)a2 + 10) + 4 * i);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000d294  mov     [rsp+arg_8], rbx
0x18000d299  mov     [rsp+arg_10], rbp
0x18000d29e  mov     [rsp+arg_0], rcx
0x18000d2a3  push    rsi
0x18000d2a4  push    rdi
0x18000d2a5  push    r12
0x18000d2a7  push    r14
0x18000d2a9  push    r15
0x18000d2ab  sub     rsp, 20h
0x18000d2af  mov     rbp, rdx
0x18000d2b2  mov     rsi, rcx
0x18000d2b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d2ba  nop
0x18000d2bb  lea     rdx, [rbp+20h]
0x18000d2bf  lea     rcx, [rsi+20h]
0x18000d2c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d2c8  nop
0x18000d2c9  mov     eax, [rbp+40h]
0x18000d2cc  mov     [rsi+40h], eax
0x18000d2cf  lea     r12, [rsi+48h]
0x18000d2d3  mov     qword ptr [r12], 0
0x18000d2db  lea     r14, [rsi+50h]
0x18000d2df  mov     qword ptr [r14], 0
0x18000d2e6  lea     r15, [rsi+58h]
0x18000d2ea  mov     qword ptr [r15], 0
0x18000d2f1  mov     qword ptr [rsi+60h], 0
0x18000d2f9  mov     qword ptr [rsi+68h], 0
0x18000d301  mov     qword ptr [rsi+70h], 0
0x18000d309  mov     rbx, [rbp+68h]
0x18000d30d  sub     rbx, [rbp+60h]
0x18000d311  jz      loc_18000D3AC
0x18000d317  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000d321  cmp     rbx, rax
0x18000d324  ja      loc_18000D4A9
0x18000d32a  cmp     rbx, 1000h
0x18000d331  jb      short loc_18000D360
0x18000d333  lea     rcx, [rbx+27h]; Size
0x18000d337  cmp     rcx, rbx
0x18000d33a  jbe     loc_18000D4AF
0x18000d340  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d345  mov     rcx, rax
0x18000d348  test    rax, rax
0x18000d34b  jnz     short loc_18000D352
0x18000d34d  lea     ecx, [rax+5]
0x18000d350  int     29h; Win8: RtlFailFast(ecx)
0x18000d352  add     rax, 27h ; '''
0x18000d356  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000d35a  mov     [rax-8], rcx
0x18000d35e  jmp     short loc_18000D368
0x18000d360  mov     rcx, rbx; Size
0x18000d363  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d368  mov     [rsi+60h], rax
0x18000d36c  mov     [rsi+68h], rax
0x18000d370  add     rax, rbx
0x18000d373  mov     [rsi+70h], rax
0x18000d377  mov     rdi, [rsi+60h]
0x18000d37b  mov     rdx, [rbp+60h]; Src
0x18000d37f  mov     rbx, [rbp+68h]
0x18000d383  sub     rbx, rdx
0x18000d386  mov     r8, rbx; Size
0x18000d389  mov     rcx, rdi; void *
0x18000d38c  call    memmove_0
0x18000d391  lea     rax, [rbx+rdi]
0x18000d395  mov     [rsi+68h], rax
0x18000d399  mov     [rsp+48h+arg_0], 0
0x18000d3a2  lea     rcx, [rsp+48h+arg_0]
0x18000d3a7  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18000d3ac  movzx   eax, word ptr [rbp+78h]
0x18000d3b0  mov     [rsi+78h], ax
0x18000d3b4  movzx   eax, word ptr [rbp+7Ah]
0x18000d3b8  mov     [rsi+7Ah], ax
0x18000d3bc  mov     al, [rbp+7Ch]
0x18000d3bf  mov     [rsi+7Ch], al
0x18000d3c2  mov     eax, [rbp+80h]
0x18000d3c8  mov     [rsi+80h], eax
0x18000d3ce  mov     eax, [rbp+84h]
0x18000d3d4  mov     [rsi+84h], eax
0x18000d3da  mov     eax, [rbp+88h]
0x18000d3e0  mov     [rsi+88h], eax
0x18000d3e6  cmp     dword ptr [rsi+40h], 0
0x18000d3ea  jz      loc_18000D479
0x18000d3f0  mov     edx, [rsi+40h]
0x18000d3f3  mov     rcx, r12
0x18000d3f6  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18000d3fb  test    al, al
0x18000d3fd  jz      loc_18000D49E
0x18000d403  mov     edx, [rsi+40h]
0x18000d406  mov     rcx, r14
0x18000d409  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18000d40e  test    al, al
0x18000d410  jz      loc_18000D49E
0x18000d416  mov     edx, [rsi+40h]
0x18000d419  mov     rcx, r15
0x18000d41c  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18000d421  test    al, al
0x18000d423  jz      short loc_18000D49E
0x18000d425  xor     edi, edi
0x18000d427  cmp     [rsi+40h], edi
0x18000d42a  jbe     short loc_18000D479
0x18000d42c  mov     ebx, edi
0x18000d42e  mov     rax, [rbp+50h]
0x18000d432  cmp     dword ptr [rax+rdi*4], 628h
0x18000d439  ja      short loc_18000D493
0x18000d43b  imul    rcx, rbx, 628h
0x18000d442  mov     r8d, [rax+rdi*4]; Size
0x18000d446  mov     rdx, [rbp+48h]
0x18000d44a  add     rdx, rcx; Src
0x18000d44d  add     rcx, [r12]; void *
0x18000d451  call    memcpy_0
0x18000d456  mov     rax, [rbp+58h]
0x18000d45a  mov     rcx, [r15]
0x18000d45d  mov     rax, [rax+rdi*8]
0x18000d461  mov     [rcx+rdi*8], rax
0x18000d465  mov     rax, [rbp+50h]
0x18000d469  mov     rcx, [r14]
0x18000d46c  mov     eax, [rax+rdi*4]
0x18000d46f  mov     [rcx+rdi*4], eax
0x18000d472  inc     edi
0x18000d474  cmp     edi, [rsi+40h]
0x18000d477  jb      short loc_18000D42C
0x18000d479  mov     rax, rsi
0x18000d47c  mov     rbx, [rsp+48h+arg_8]
0x18000d481  mov     rbp, [rsp+48h+arg_10]
0x18000d486  add     rsp, 20h
0x18000d48a  pop     r15
0x18000d48c  pop     r14
0x18000d48e  pop     r12
0x18000d490  pop     rdi
0x18000d491  pop     rsi
0x18000d492  retn
0x18000d493  mov     ecx, 8000FFFFh; int
0x18000d498  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d49e  mov     ecx, 8007000Eh; int
0x18000d4a3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d4a9  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18000d4af  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
