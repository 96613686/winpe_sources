# ATL::CComCreator<ATL::CComObjectCached<CBrowserFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003c50`
- end: `0x180003d76`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCBrowserFactory@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003c50`
- `0x180004480`
- `0x1800099f8`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180003d5f`
- `msvcrt!free` at `0x180003d5f`
- `KERNEL32!DeleteCriticalSection` at `0x180003d56`
- `KERNEL32!DeleteCriticalSection` at `0x180003d56`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<CBrowserFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x50u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<CBrowserFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      free(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003c50  mov     [rsp+arg_10], r8
0x180003c55  mov     [rsp+arg_8], rdx
0x180003c5a  mov     [rsp+arg_0], rcx
0x180003c5f  push    rbx
0x180003c60  push    rsi
0x180003c61  push    r12
0x180003c63  push    r13
0x180003c65  push    r14
0x180003c67  push    r15
0x180003c69  sub     rsp, 38h
0x180003c6d  mov     r15, r8
0x180003c70  mov     r12, rdx
0x180003c73  mov     r14, rcx
0x180003c76  test    r8, r8
0x180003c79  jnz     short loc_180003C85
0x180003c7b  mov     eax, 80004003h
0x180003c80  jmp     loc_180003D67
0x180003c85  mov     qword ptr [r8], 0
0x180003c8c  mov     esi, 8007000Eh
0x180003c91  mov     [rsp+68h+arg_18], esi
0x180003c98  mov     [rsp+68h+var_48], 0
0x180003ca1  mov     ecx, 50h ; 'P'; unsigned __int64
0x180003ca6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003cab  mov     rbx, rax
0x180003cae  test    rbx, rbx
0x180003cb1  jz      short loc_180003CD8
0x180003cb3  mov     dword ptr [rax+8], 0
0x180003cba  xorps   xmm0, xmm0
0x180003cbd  xor     eax, eax
0x180003cbf  movups  xmmword ptr [rbx+10h], xmm0
0x180003cc3  movups  xmmword ptr [rbx+20h], xmm0
0x180003cc7  mov     [rbx+30h], rax
0x180003ccb  mov     [rbx+38h], al
0x180003cce  lea     rax, ??_7?$CComObjectCached@VCBrowserFactory@@@ATL@@6B@; const ATL::CComObjectCached<CBrowserFactory>::`vftable'
0x180003cd5  mov     [rbx], rax
0x180003cd8  mov     [rsp+68h+var_48], rbx
0x180003cdd  jmp     short loc_180003CFD
0x180003cdf  mov     r15, [rsp+68h+arg_10]
0x180003ce7  mov     r12, [rsp+68h+arg_8]
0x180003cec  mov     r14, [rsp+68h+arg_0]
0x180003cf1  mov     esi, [rsp+68h+arg_18]
0x180003cf8  mov     rbx, [rsp+68h+var_48]
0x180003cfd  test    rbx, rbx
0x180003d00  jz      short loc_180003D65
0x180003d02  mov     [rbx+40h], r14
0x180003d06  lea     rcx, [rbx+10h]; this
0x180003d0a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003d0f  mov     esi, eax
0x180003d11  lea     r14, [rbx+38h]
0x180003d15  test    eax, eax
0x180003d17  js      short loc_180003D37
0x180003d19  mov     byte ptr [r14], 1
0x180003d1d  mov     rax, [rbx]
0x180003d20  mov     r8, r15
0x180003d23  mov     rdx, r12
0x180003d26  mov     rcx, rbx
0x180003d29  mov     rax, [rax]
0x180003d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d31  mov     esi, eax
0x180003d33  test    eax, eax
0x180003d35  jz      short loc_180003D65
0x180003d37  mov     dword ptr [rbx+8], 0C0000001h
0x180003d3e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003d45  mov     [rbx], rax
0x180003d48  cmp     byte ptr [r14], 0
0x180003d4c  jz      short loc_180003D5C
0x180003d4e  mov     byte ptr [r14], 0
0x180003d52  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003d56  call    cs:__imp_DeleteCriticalSection
0x180003d5c  mov     rcx, rbx; Block
0x180003d5f  call    cs:__imp_free
0x180003d65  mov     eax, esi
0x180003d67  add     rsp, 38h
0x180003d6b  pop     r15
0x180003d6d  pop     r14
0x180003d6f  pop     r13
0x180003d71  pop     r12
0x180003d73  pop     rsi
0x180003d74  pop     rbx
0x180003d75  retn
```
