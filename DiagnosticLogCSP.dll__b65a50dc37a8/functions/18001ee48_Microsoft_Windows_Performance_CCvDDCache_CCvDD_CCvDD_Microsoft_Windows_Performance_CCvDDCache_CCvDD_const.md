# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x18001ee48`
- end: `0x18001f06b`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z`
- size: `547`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this, const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180027b70`

## callees

- `0x180001bb4`
- `0x180002d25`
- `0x180002d31`
- `0x18000c07c`
- `0x1800105f8`
- `0x180011648`
- `0x180015f9c`
- `0x18001618c`
- `0x18001ee48`
- `0x18001fcec`
- `0x180023010`
- `0x180027b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  std::wstring::wstring(this, a2);
  std::wstring::wstring((char *)this + 32, (char *)a2 + 32);
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
0x18001ee48  mov     [rsp+arg_10], rbx
0x18001ee4d  mov     [rsp+arg_18], rbp
0x18001ee52  mov     [rsp+arg_0], rcx
0x18001ee57  push    rsi
0x18001ee58  push    rdi
0x18001ee59  push    r12
0x18001ee5b  push    r14
0x18001ee5d  push    r15
0x18001ee5f  sub     rsp, 20h
0x18001ee63  mov     rbp, rdx
0x18001ee66  mov     rsi, rcx
0x18001ee69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ee6e  nop
0x18001ee6f  lea     rdx, [rbp+20h]
0x18001ee73  lea     rcx, [rsi+20h]
0x18001ee77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ee7c  nop
0x18001ee7d  mov     eax, [rbp+40h]
0x18001ee80  mov     [rsi+40h], eax
0x18001ee83  lea     r12, [rsi+48h]
0x18001ee87  mov     qword ptr [r12], 0
0x18001ee8f  lea     r14, [rsi+50h]
0x18001ee93  mov     qword ptr [r14], 0
0x18001ee9a  lea     r15, [rsi+58h]
0x18001ee9e  mov     qword ptr [r15], 0
0x18001eea5  mov     qword ptr [rsi+60h], 0
0x18001eead  mov     qword ptr [rsi+68h], 0
0x18001eeb5  mov     qword ptr [rsi+70h], 0
0x18001eebd  mov     rbx, [rbp+68h]
0x18001eec1  sub     rbx, [rbp+60h]
0x18001eec5  jz      loc_18001EF61
0x18001eecb  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001eed5  cmp     rbx, rax
0x18001eed8  ja      loc_18001F05F
0x18001eede  cmp     rbx, 1000h
0x18001eee5  jb      short loc_18001EF14
0x18001eee7  lea     rcx, [rbx+27h]; Size
0x18001eeeb  cmp     rcx, rbx
0x18001eeee  jbe     loc_18001F065
0x18001eef4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eef9  mov     rcx, rax
0x18001eefc  test    rax, rax
0x18001eeff  jnz     short loc_18001EF06
0x18001ef01  lea     ecx, [rax+5]
0x18001ef04  int     29h; Win8: RtlFailFast(ecx)
0x18001ef06  add     rax, 27h ; '''
0x18001ef0a  and     rax, 0FFFFFFFFFFFFFFE0h
0x18001ef0e  mov     [rax-8], rcx
0x18001ef12  jmp     short loc_18001EF1C
0x18001ef14  mov     rcx, rbx; Size
0x18001ef17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ef1c  mov     [rsi+60h], rax
0x18001ef20  mov     [rsi+68h], rax
0x18001ef24  add     rax, rbx
0x18001ef27  mov     [rsi+70h], rax
0x18001ef2b  mov     rdi, [rsi+60h]
0x18001ef2f  mov     rdx, [rbp+60h]; Src
0x18001ef33  mov     rbx, [rbp+68h]
0x18001ef37  sub     rbx, rdx
0x18001ef3a  mov     r8, rbx; Size
0x18001ef3d  mov     rcx, rdi; void *
0x18001ef40  call    memmove_0
0x18001ef45  lea     rax, [rbx+rdi]
0x18001ef49  mov     [rsi+68h], rax
0x18001ef4d  mov     [rsp+48h+arg_8], 0
0x18001ef56  lea     rcx, [rsp+48h+arg_8]
0x18001ef5b  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18001ef60  nop
0x18001ef61  movzx   eax, word ptr [rbp+78h]
0x18001ef65  mov     [rsi+78h], ax
0x18001ef69  movzx   eax, word ptr [rbp+7Ah]
0x18001ef6d  mov     [rsi+7Ah], ax
0x18001ef71  mov     al, [rbp+7Ch]
0x18001ef74  mov     [rsi+7Ch], al
0x18001ef77  mov     eax, [rbp+80h]
0x18001ef7d  mov     [rsi+80h], eax
0x18001ef83  mov     eax, [rbp+84h]
0x18001ef89  mov     [rsi+84h], eax
0x18001ef8f  mov     eax, [rbp+88h]
0x18001ef95  mov     [rsi+88h], eax
0x18001ef9b  cmp     dword ptr [rsi+40h], 0
0x18001ef9f  jz      loc_18001F02E
0x18001efa5  mov     edx, [rsi+40h]
0x18001efa8  mov     rcx, r12
0x18001efab  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001efb0  test    al, al
0x18001efb2  jz      loc_18001F054
0x18001efb8  mov     edx, [rsi+40h]
0x18001efbb  mov     rcx, r14
0x18001efbe  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001efc3  test    al, al
0x18001efc5  jz      loc_18001F054
0x18001efcb  mov     edx, [rsi+40h]
0x18001efce  mov     rcx, r15
0x18001efd1  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001efd6  test    al, al
0x18001efd8  jz      short loc_18001F054
0x18001efda  xor     edi, edi
0x18001efdc  cmp     [rsi+40h], edi
0x18001efdf  jbe     short loc_18001F02E
0x18001efe1  mov     ebx, edi
0x18001efe3  mov     rax, [rbp+50h]
0x18001efe7  cmp     dword ptr [rax+rdi*4], 628h
0x18001efee  ja      short loc_18001F049
0x18001eff0  imul    rcx, rbx, 628h
0x18001eff7  mov     r8d, [rax+rdi*4]; Size
0x18001effb  mov     rdx, [rbp+48h]
0x18001efff  add     rdx, rcx; Src
0x18001f002  add     rcx, [r12]; void *
0x18001f006  call    memcpy_0
0x18001f00b  mov     rax, [rbp+58h]
0x18001f00f  mov     rcx, [r15]
0x18001f012  mov     rax, [rax+rdi*8]
0x18001f016  mov     [rcx+rdi*8], rax
0x18001f01a  mov     rax, [rbp+50h]
0x18001f01e  mov     rcx, [r14]
0x18001f021  mov     eax, [rax+rdi*4]
0x18001f024  mov     [rcx+rdi*4], eax
0x18001f027  inc     edi
0x18001f029  cmp     edi, [rsi+40h]
0x18001f02c  jb      short loc_18001EFE1
0x18001f02e  mov     rax, rsi
0x18001f031  mov     rbx, [rsp+48h+arg_10]
0x18001f036  mov     rbp, [rsp+48h+arg_18]
0x18001f03b  add     rsp, 20h
0x18001f03f  pop     r15
0x18001f041  pop     r14
0x18001f043  pop     r12
0x18001f045  pop     rdi
0x18001f046  pop     rsi
0x18001f047  retn
0x18001f049  mov     ecx, 8000FFFFh; int
0x18001f04e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f054  mov     ecx, 8007000Eh; int
0x18001f059  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f05f  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18001f065  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
