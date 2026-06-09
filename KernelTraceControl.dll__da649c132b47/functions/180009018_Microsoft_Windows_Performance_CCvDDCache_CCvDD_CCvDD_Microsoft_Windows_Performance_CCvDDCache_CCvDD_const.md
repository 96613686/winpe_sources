# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x180009018`
- end: `0x1800091be`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z`
- size: `422`
- prototype: `Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *this, const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000f3b4`

## callees

- `0x18000139c`
- `0x1800056c8`
- `0x1800061c8`
- `0x180009018`
- `0x18000d62c`
- `0x18000d6e0`
- `0x180013934`
- `0x1800278f0`

## pseudocode

```c
Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-38h]

  *((_QWORD *)this + 4) = 7;
  v4 = 0;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 4) = 0;
  std::wstring::assign(this, a2, 0, -1, -2);
  *((_QWORD *)this + 9) = 7;
  *((_QWORD *)this + 8) = 0;
  *((_WORD *)this + 24) = 0;
  std::wstring::assign((char *)this + 40, (char *)a2 + 40, 0, -1, v7);
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  std::vector<unsigned char>::vector<unsigned char>((char *)this + 112, (char *)a2 + 112);
  *((_WORD *)this + 72) = *((_WORD *)a2 + 72);
  *((_WORD *)this + 73) = *((_WORD *)a2 + 73);
  *((_BYTE *)this + 148) = *((_BYTE *)a2 + 148);
  *((_DWORD *)this + 38) = *((_DWORD *)a2 + 38);
  *((_DWORD *)this + 39) = *((_DWORD *)a2 + 39);
  *((_DWORD *)this + 40) = *((_DWORD *)a2 + 40);
  if ( *((_DWORD *)this + 20) )
  {
    if ( !ATL::CAutoVectorPtr<_CVDD>::Allocate((_QWORD *)this + 11, *((unsigned int *)this + 20))
      || !ATL::CAutoVectorPtr<unsigned long>::Allocate((_QWORD *)this + 12, *((unsigned int *)this + 20))
      || !ATL::CAutoVectorPtr<unsigned __int64>::Allocate((_QWORD *)this + 13, *((unsigned int *)this + 20)) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    if ( *((_DWORD *)this + 20) )
    {
      do
      {
        v5 = *((_QWORD *)a2 + 12);
        if ( *(_DWORD *)(v5 + 4LL * v4) > 0x628u )
          ATL::AtlThrowImpl(-2147418113);
        memcpy_0(
          (void *)(1576LL * v4 + *((_QWORD *)this + 11)),
          (const void *)(1576LL * v4 + *((_QWORD *)a2 + 11)),
          *(unsigned int *)(v5 + 4LL * v4));
        *(_QWORD *)(*((_QWORD *)this + 13) + 8LL * v4) = *(_QWORD *)(*((_QWORD *)a2 + 13) + 8LL * v4);
        *(_DWORD *)(*((_QWORD *)this + 12) + 4LL * v4) = *(_DWORD *)(*((_QWORD *)a2 + 12) + 4LL * v4);
        ++v4;
      }
      while ( v4 < *((_DWORD *)this + 20) );
    }
  }
  return this;
}

```

## disassembly

```asm
0x180009018  mov     rax, rsp
0x18000901b  mov     [rax+8], rcx
0x18000901f  push    rsi
0x180009020  push    rdi
0x180009021  push    r12
0x180009023  push    r14
0x180009025  push    r15
0x180009027  sub     rsp, 30h
0x18000902b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180009033  mov     [rax+10h], rbx
0x180009037  mov     [rax+18h], rbp
0x18000903b  mov     rbp, rdx
0x18000903e  mov     rdi, rcx
0x180009041  mov     r14d, 7
0x180009047  mov     [rcx+20h], r14
0x18000904b  xor     ebx, ebx
0x18000904d  mov     [rcx+18h], rbx
0x180009051  mov     [rcx+8], bx
0x180009055  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009059  mov     r9, rsi
0x18000905c  xor     r8d, r8d
0x18000905f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180009064  nop
0x180009065  lea     rcx, [rdi+28h]
0x180009069  mov     [rcx+20h], r14
0x18000906d  mov     [rcx+18h], rbx
0x180009071  mov     [rcx+8], bx
0x180009075  lea     rdx, [rbp+28h]
0x180009079  mov     r9, rsi
0x18000907c  xor     r8d, r8d
0x18000907f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180009084  nop
0x180009085  mov     eax, [rbp+50h]
0x180009088  mov     [rdi+50h], eax
0x18000908b  lea     r12, [rdi+58h]
0x18000908f  mov     [r12], rbx
0x180009093  lea     r14, [rdi+60h]
0x180009097  mov     [r14], rbx
0x18000909a  lea     r15, [rdi+68h]
0x18000909e  mov     [r15], rbx
0x1800090a1  lea     rdx, [rbp+70h]
0x1800090a5  lea     rcx, [rdi+70h]
0x1800090a9  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x1800090ae  nop
0x1800090af  movzx   eax, word ptr [rbp+90h]
0x1800090b6  mov     [rdi+90h], ax
0x1800090bd  movzx   eax, word ptr [rbp+92h]
0x1800090c4  mov     [rdi+92h], ax
0x1800090cb  mov     al, [rbp+94h]
0x1800090d1  mov     [rdi+94h], al
0x1800090d7  mov     eax, [rbp+98h]
0x1800090dd  mov     [rdi+98h], eax
0x1800090e3  mov     eax, [rbp+9Ch]
0x1800090e9  mov     [rdi+9Ch], eax
0x1800090ef  mov     eax, [rbp+0A0h]
0x1800090f5  mov     [rdi+0A0h], eax
0x1800090fb  cmp     [rdi+50h], ebx
0x1800090fe  jz      loc_1800091A4
0x180009104  mov     edx, [rdi+50h]
0x180009107  mov     rcx, r12
0x18000910a  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18000910f  test    al, al
0x180009111  jz      loc_180009199
0x180009117  mov     edx, [rdi+50h]
0x18000911a  mov     rcx, r14
0x18000911d  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180009122  test    al, al
0x180009124  jz      short loc_180009199
0x180009126  mov     edx, [rdi+50h]
0x180009129  mov     rcx, r15
0x18000912c  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180009131  test    al, al
0x180009133  jz      short loc_180009199
0x180009135  cmp     [rdi+50h], ebx
0x180009138  jbe     short loc_1800091A4
0x18000913a  mov     rdx, [rbp+60h]
0x18000913e  mov     esi, ebx
0x180009140  cmp     dword ptr [rdx+rsi*4], 628h
0x180009147  ja      short loc_18000918E
0x180009149  mov     rcx, [rbp+58h]
0x18000914d  mov     r9, [r12]
0x180009151  imul    rax, rsi, 628h
0x180009158  mov     r8d, [rdx+rsi*4]; Size
0x18000915c  lea     rdx, [rax+rcx]; Src
0x180009160  lea     rcx, [rax+r9]; void *
0x180009164  call    memcpy_0
0x180009169  mov     rax, [rbp+68h]
0x18000916d  mov     rcx, [r15]
0x180009170  mov     rax, [rax+rsi*8]
0x180009174  mov     [rcx+rsi*8], rax
0x180009178  mov     rax, [rbp+60h]
0x18000917c  mov     rcx, [r14]
0x18000917f  mov     eax, [rax+rsi*4]
0x180009182  mov     [rcx+rsi*4], eax
0x180009185  inc     ebx
0x180009187  cmp     ebx, [rdi+50h]
0x18000918a  jb      short loc_18000913A
0x18000918c  jmp     short loc_1800091A4
0x18000918e  mov     ecx, 8000FFFFh; int
0x180009193  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009199  mov     ecx, 8007000Eh; int
0x18000919e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800091a4  mov     rax, rdi
0x1800091a7  mov     rbx, [rsp+58h+arg_8]
0x1800091ac  mov     rbp, [rsp+58h+arg_10]
0x1800091b1  add     rsp, 30h
0x1800091b5  pop     r15
0x1800091b7  pop     r14
0x1800091b9  pop     r12
0x1800091bb  pop     rdi
0x1800091bc  pop     rsi
0x1800091bd  retn
```
