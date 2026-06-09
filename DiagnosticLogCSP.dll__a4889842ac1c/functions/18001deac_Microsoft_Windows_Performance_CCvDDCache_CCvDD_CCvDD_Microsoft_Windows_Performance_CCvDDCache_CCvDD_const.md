# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x18001deac`
- end: `0x18001e0ce`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z`
- size: `546`
- prototype: `Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *this, const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180026a08`

## callees

- `0x180001b84`
- `0x180002cf5`
- `0x180002d01`
- `0x18000bb3c`
- `0x18000fde8`
- `0x180010db8`
- `0x18001543c`
- `0x18001562c`
- `0x18001deac`
- `0x18001ecf8`
- `0x1800220cc`
- `0x180026964`

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
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF

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
0x18001deac  mov     [rsp+arg_10], rbx
0x18001deb1  mov     [rsp+arg_18], rbp
0x18001deb6  mov     [rsp+arg_0], rcx
0x18001debb  push    rsi
0x18001debc  push    rdi
0x18001debd  push    r12
0x18001debf  push    r14
0x18001dec1  push    r15
0x18001dec3  sub     rsp, 20h
0x18001dec7  mov     rbp, rdx
0x18001deca  mov     rsi, rcx
0x18001decd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ded2  nop
0x18001ded3  lea     rdx, [rbp+20h]
0x18001ded7  lea     rcx, [rsi+20h]
0x18001dedb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dee0  nop
0x18001dee1  mov     eax, [rbp+40h]
0x18001dee4  mov     [rsi+40h], eax
0x18001dee7  lea     r12, [rsi+48h]
0x18001deeb  mov     qword ptr [r12], 0
0x18001def3  lea     r14, [rsi+50h]
0x18001def7  mov     qword ptr [r14], 0
0x18001defe  lea     r15, [rsi+58h]
0x18001df02  mov     qword ptr [r15], 0
0x18001df09  mov     qword ptr [rsi+60h], 0
0x18001df11  mov     qword ptr [rsi+68h], 0
0x18001df19  mov     qword ptr [rsi+70h], 0
0x18001df21  mov     rbx, [rbp+68h]
0x18001df25  sub     rbx, [rbp+60h]
0x18001df29  jz      loc_18001DFC5
0x18001df2f  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001df39  cmp     rbx, rax
0x18001df3c  ja      loc_18001E0C2
0x18001df42  cmp     rbx, 1000h
0x18001df49  jb      short loc_18001DF78
0x18001df4b  lea     rcx, [rbx+27h]; Size
0x18001df4f  cmp     rcx, rbx
0x18001df52  jbe     loc_18001E0C8
0x18001df58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001df5d  mov     rcx, rax
0x18001df60  test    rax, rax
0x18001df63  jnz     short loc_18001DF6A
0x18001df65  lea     ecx, [rax+5]
0x18001df68  int     29h; Win8: RtlFailFast(ecx)
0x18001df6a  add     rax, 27h ; '''
0x18001df6e  and     rax, 0FFFFFFFFFFFFFFE0h
0x18001df72  mov     [rax-8], rcx
0x18001df76  jmp     short loc_18001DF80
0x18001df78  mov     rcx, rbx; Size
0x18001df7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001df80  mov     [rsi+60h], rax
0x18001df84  mov     [rsi+68h], rax
0x18001df88  add     rax, rbx
0x18001df8b  mov     [rsi+70h], rax
0x18001df8f  mov     rdi, [rsi+60h]
0x18001df93  mov     rdx, [rbp+60h]; Src
0x18001df97  mov     rbx, [rbp+68h]
0x18001df9b  sub     rbx, rdx
0x18001df9e  mov     r8, rbx; Size
0x18001dfa1  mov     rcx, rdi; void *
0x18001dfa4  call    memmove_0
0x18001dfa9  lea     rax, [rbx+rdi]
0x18001dfad  mov     [rsi+68h], rax
0x18001dfb1  mov     [rsp+48h+arg_8], 0
0x18001dfba  lea     rcx, [rsp+48h+arg_8]
0x18001dfbf  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18001dfc4  nop
0x18001dfc5  movzx   eax, word ptr [rbp+78h]
0x18001dfc9  mov     [rsi+78h], ax
0x18001dfcd  movzx   eax, word ptr [rbp+7Ah]
0x18001dfd1  mov     [rsi+7Ah], ax
0x18001dfd5  mov     al, [rbp+7Ch]
0x18001dfd8  mov     [rsi+7Ch], al
0x18001dfdb  mov     eax, [rbp+80h]
0x18001dfe1  mov     [rsi+80h], eax
0x18001dfe7  mov     eax, [rbp+84h]
0x18001dfed  mov     [rsi+84h], eax
0x18001dff3  mov     eax, [rbp+88h]
0x18001dff9  mov     [rsi+88h], eax
0x18001dfff  cmp     dword ptr [rsi+40h], 0
0x18001e003  jz      loc_18001E092
0x18001e009  mov     edx, [rsi+40h]
0x18001e00c  mov     rcx, r12
0x18001e00f  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001e014  test    al, al
0x18001e016  jz      loc_18001E0B7
0x18001e01c  mov     edx, [rsi+40h]
0x18001e01f  mov     rcx, r14
0x18001e022  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001e027  test    al, al
0x18001e029  jz      loc_18001E0B7
0x18001e02f  mov     edx, [rsi+40h]
0x18001e032  mov     rcx, r15
0x18001e035  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001e03a  test    al, al
0x18001e03c  jz      short loc_18001E0B7
0x18001e03e  xor     edi, edi
0x18001e040  cmp     [rsi+40h], edi
0x18001e043  jbe     short loc_18001E092
0x18001e045  mov     ebx, edi
0x18001e047  mov     rax, [rbp+50h]
0x18001e04b  cmp     dword ptr [rax+rdi*4], 628h
0x18001e052  ja      short loc_18001E0AC
0x18001e054  imul    rcx, rbx, 628h
0x18001e05b  mov     r8d, [rax+rdi*4]; Size
0x18001e05f  mov     rdx, [rbp+48h]
0x18001e063  add     rdx, rcx; Src
0x18001e066  add     rcx, [r12]; void *
0x18001e06a  call    memcpy_0
0x18001e06f  mov     rax, [rbp+58h]
0x18001e073  mov     rcx, [r15]
0x18001e076  mov     rax, [rax+rdi*8]
0x18001e07a  mov     [rcx+rdi*8], rax
0x18001e07e  mov     rax, [rbp+50h]
0x18001e082  mov     rcx, [r14]
0x18001e085  mov     eax, [rax+rdi*4]
0x18001e088  mov     [rcx+rdi*4], eax
0x18001e08b  inc     edi
0x18001e08d  cmp     edi, [rsi+40h]
0x18001e090  jb      short loc_18001E045
0x18001e092  mov     rax, rsi
0x18001e095  mov     rbx, [rsp+48h+arg_10]
0x18001e09a  mov     rbp, [rsp+48h+arg_18]
0x18001e09f  add     rsp, 20h
0x18001e0a3  pop     r15
0x18001e0a5  pop     r14
0x18001e0a7  pop     r12
0x18001e0a9  pop     rdi
0x18001e0aa  pop     rsi
0x18001e0ab  retn
0x18001e0ac  mov     ecx, 8000FFFFh; int
0x18001e0b1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e0b7  mov     ecx, 8007000Eh; int
0x18001e0bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e0c2  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18001e0c8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
