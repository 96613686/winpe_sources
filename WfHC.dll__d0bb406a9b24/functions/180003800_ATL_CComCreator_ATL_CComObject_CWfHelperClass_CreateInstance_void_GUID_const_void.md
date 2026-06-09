# ATL::CComCreator<ATL::CComObject<CWfHelperClass>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003800`
- end: `0x1800039e9`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWfHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800037d0`

## callees

- `0x180001250`
- `0x180003800`
- `0x180004370`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWfHelperClass>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  char *v7; // rax
  char *v8; // rbx
  __int64 v9; // rcx
  _BYTE *v10; // rax
  signed __int32 i; // eax
  int v12; // eax
  int v13; // ecx
  signed __int32 j; // eax
  char *v17; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0xC8u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 16) = 0;
      *(_OWORD *)(v7 + 72) = 0;
      *(_OWORD *)(v7 + 88) = 0;
      *((_QWORD *)v7 + 13) = 0;
      v7[112] = 0;
      *(_QWORD *)v7 = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'};
      *((_QWORD *)v7 + 1) = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'};
      *(_QWORD *)(v7 + 20) = 0;
      *((_QWORD *)v7 + 4) = 0;
      *((_DWORD *)v7 + 4) = 0;
      *((_QWORD *)v7 + 7) = &CNetDiagHelperExImpl::`vftable';
      *((_QWORD *)v7 + 15) = 0;
      *((_QWORD *)v7 + 18) = 0;
      *((_QWORD *)v7 + 19) = 0;
      *((_QWORD *)v7 + 20) = 0;
      *((_QWORD *)v7 + 21) = 0;
      *((_QWORD *)v7 + 22) = 0;
      *((_DWORD *)v7 + 46) = 0;
      *((_QWORD *)v7 + 24) = 0;
      v9 = 16;
      v10 = v7 + 128;
      do
      {
        *v10++ = 0;
        --v9;
      }
      while ( v9 );
      *(_QWORD *)v8 = &ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelper'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelperInfo'};
      *((_QWORD *)v8 + 7) = &ATL::CComObject<CWfHelperClass>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v8 = 0;
    }
    v17 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v17;
  }
  if ( v8 )
  {
    for ( i = *((_DWORD *)v8 + 16); i != 0x7FFFFFFF; i = *((_DWORD *)v8 + 16) )
    {
      if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v8 + 16, i + 1, i) )
        break;
    }
    v12 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 72));
    if ( v12 >= 0 )
      v8[112] = 1;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v6 = 0;
    if ( v13 < 0 )
      v6 = v13;
    for ( j = *((_DWORD *)v8 + 16); j != 0x7FFFFFFF; j = *((_DWORD *)v8 + 16) )
    {
      if ( j == _InterlockedCompareExchange((volatile signed __int32 *)v8 + 16, j - 1, j) )
        break;
    }
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003800  mov     [rsp+arg_10], r8
0x180003805  mov     [rsp+arg_8], rdx
0x18000380a  mov     [rsp+arg_0], rcx
0x18000380f  push    rbx
0x180003810  push    rsi
0x180003811  push    rdi
0x180003812  push    r14
0x180003814  push    r15
0x180003816  sub     rsp, 20h
0x18000381a  mov     r14, r8
0x18000381d  mov     r15, rdx
0x180003820  test    r8, r8
0x180003823  jnz     short loc_180003836
0x180003825  mov     eax, 80004003h
0x18000382a  add     rsp, 20h
0x18000382e  pop     r15
0x180003830  pop     r14
0x180003832  pop     rdi
0x180003833  pop     rsi
0x180003834  pop     rbx
0x180003835  retn
0x180003836  xor     edi, edi
0x180003838  mov     [r8], rdi
0x18000383b  mov     esi, 8007000Eh
0x180003840  mov     dword ptr [rsp+48h+arg_0], esi
0x180003844  mov     [rsp+48h+arg_18], rdi
0x180003849  mov     ecx, 0C8h; Size
0x18000384e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003853  mov     rbx, rax
0x180003856  test    rax, rax
0x180003859  jz      loc_180003923
0x18000385f  mov     [rax+40h], edi
0x180003862  xorps   xmm0, xmm0
0x180003865  xor     eax, eax
0x180003867  movups  xmmword ptr [rbx+48h], xmm0
0x18000386b  movups  xmmword ptr [rbx+58h], xmm0
0x18000386f  mov     [rbx+68h], rax
0x180003873  mov     [rbx+70h], al
0x180003876  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x18000387d  mov     [rbx], rax
0x180003880  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x180003887  mov     [rbx+8], rax
0x18000388b  mov     [rbx+14h], rdi
0x18000388f  mov     [rbx+20h], rdi
0x180003893  mov     [rbx+10h], edi
0x180003896  lea     rax, ??_7CNetDiagHelperExImpl@@6B@; const CNetDiagHelperExImpl::`vftable'
0x18000389d  mov     [rbx+38h], rax
0x1800038a1  mov     [rbx+78h], rdi
0x1800038a5  mov     [rbx+90h], rdi
0x1800038ac  mov     [rbx+98h], rdi
0x1800038b3  mov     [rbx+0A0h], rdi
0x1800038ba  mov     [rbx+0A8h], rdi
0x1800038c1  mov     [rbx+0B0h], rdi
0x1800038c8  mov     [rbx+0B8h], edi
0x1800038ce  mov     [rbx+0C0h], rdi
0x1800038d5  mov     ecx, 10h
0x1800038da  lea     rax, [rbx+80h]
0x1800038e1  mov     byte ptr [rax], 0
0x1800038e4  lea     rax, [rax+1]
0x1800038e8  sub     rcx, 1
0x1800038ec  jnz     short loc_1800038E1
0x1800038ee  lea     rax, ??_7?$CComObject@VCWfHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelper'}
0x1800038f5  mov     [rbx], rax
0x1800038f8  lea     rax, ??_7?$CComObject@VCWfHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x1800038ff  mov     [rbx+8], rax
0x180003903  lea     rax, ??_7?$CComObject@VCWfHelperClass@@@ATL@@6B@; const ATL::CComObject<CWfHelperClass>::`vftable'
0x18000390a  mov     [rbx+38h], rax
0x18000390e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003915  mov     rax, [rcx]
0x180003918  mov     rax, [rax+8]
0x18000391c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003921  jmp     short loc_180003926
0x180003923  mov     rbx, rdi
0x180003926  mov     [rsp+48h+arg_18], rbx
0x18000392b  jmp     short loc_180003942
0x18000392d  xor     edi, edi
0x18000392f  mov     r14, [rsp+48h+arg_10]
0x180003934  mov     r15, [rsp+48h+arg_8]
0x180003939  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000393d  mov     rbx, [rsp+48h+arg_18]
0x180003942  test    rbx, rbx
0x180003945  jz      loc_1800039DB
0x18000394b  mov     eax, [rbx+40h]
0x18000394e  cmp     eax, 7FFFFFFFh
0x180003953  jz      short loc_180003969
0x180003955  lea     ecx, [rax+1]
0x180003958  lock cmpxchg [rbx+40h], ecx
0x18000395d  jz      short loc_180003969
0x18000395f  mov     eax, [rbx+40h]
0x180003962  cmp     eax, 7FFFFFFFh
0x180003967  jnz     short loc_180003955
0x180003969  lea     rcx, [rbx+48h]; this
0x18000396d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003972  test    eax, eax
0x180003974  js      short loc_18000397A
0x180003976  mov     byte ptr [rbx+70h], 1
0x18000397a  mov     ecx, edi
0x18000397c  test    eax, eax
0x18000397e  cmovs   ecx, eax
0x180003981  mov     esi, edi
0x180003983  test    ecx, ecx
0x180003985  cmovs   esi, ecx
0x180003988  mov     eax, [rbx+40h]
0x18000398b  cmp     eax, 7FFFFFFFh
0x180003990  jz      short loc_1800039A6
0x180003992  lea     ecx, [rax-1]
0x180003995  lock cmpxchg [rbx+40h], ecx
0x18000399a  jz      short loc_1800039A6
0x18000399c  mov     eax, [rbx+40h]
0x18000399f  cmp     eax, 7FFFFFFFh
0x1800039a4  jnz     short loc_180003992
0x1800039a6  test    esi, esi
0x1800039a8  jnz     short loc_1800039C4
0x1800039aa  mov     rax, [rbx]
0x1800039ad  mov     r8, r14
0x1800039b0  mov     rdx, r15
0x1800039b3  mov     rcx, rbx
0x1800039b6  mov     rax, [rax]
0x1800039b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039be  mov     esi, eax
0x1800039c0  test    eax, eax
0x1800039c2  jz      short loc_1800039DB
0x1800039c4  mov     rcx, [rbx]
0x1800039c7  mov     rax, [rcx+0A8h]
0x1800039ce  mov     edx, 1
0x1800039d3  mov     rcx, rbx
0x1800039d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039db  mov     eax, esi
0x1800039dd  add     rsp, 20h
0x1800039e1  pop     r15
0x1800039e3  pop     r14
0x1800039e5  pop     rdi
0x1800039e6  pop     rsi
0x1800039e7  pop     rbx
0x1800039e8  retn
```
