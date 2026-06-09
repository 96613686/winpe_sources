# StructuredQuery1::Interval::CreateInstance(tagINTERVAL_LIMIT_KIND,tagPROPVARIANT *,tagINTERVAL_LIMIT_KIND,tagPROPVARIANT *,_GUID const &,void * *)

- ea: `0x1800115d4`
- end: `0x1800116d9`
- name: `?CreateInstance@Interval@StructuredQuery1@@SAJW4tagINTERVAL_LIMIT_KIND@@PEAUtagPROPVARIANT@@01AEBU_GUID@@PEAPEAX@Z`
- size: `261`
- prototype: `static int(enum tagINTERVAL_LIMIT_KIND, struct tagPROPVARIANT *, enum tagINTERVAL_LIMIT_KIND, struct tagPROPVARIANT *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006790`
- `0x18000f7cc`
- `0x180046eb8`

## callees

- `0x1800115d4`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001166a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001167d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001166a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001167d`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Interval::CreateInstance(
        enum tagINTERVAL_LIMIT_KIND a1,
        const PROPVARIANT *a2,
        enum tagINTERVAL_LIMIT_KIND a3,
        const PROPVARIANT *a4,
        const struct _GUID *a5,
        void **a6)
{
  HRESULT v10; // edi
  char *v11; // rax
  PROPVARIANT *v12; // rbx

  a5 = 0;
  v10 = -2147024882;
  v11 = (char *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = (PROPVARIANT *)v11;
  if ( v11 )
  {
    *((_DWORD *)v11 + 4) = a1;
    *(_QWORD *)v11 = &StructuredQuery1::Interval::`vftable'{for `IInterval'};
    *((_QWORD *)v11 + 1) = &StructuredQuery1::Interval::`vftable'{for `IPersistStream'};
    *((_DWORD *)v11 + 12) = a3;
    *((_DWORD *)v11 + 20) = 1;
    _InterlockedIncrement(&dword_1800B134C);
    *(_OWORD *)(v11 + 24) = 0;
    *((_QWORD *)v11 + 5) = 0;
    *(_OWORD *)(v11 + 56) = 0;
    *((_QWORD *)v11 + 9) = 0;
    v10 = PropVariantCopy((PROPVARIANT *)v11 + 3, a2);
    if ( v10 >= 0 )
    {
      v10 = PropVariantCopy(v12 + 7, a4);
      if ( v10 >= 0 )
        v10 = (*(__int64 (__fastcall **)(PROPVARIANT *, GUID *, const struct _GUID **))*v12)(
                v12,
                &GUID_00000000_0000_0000_c000_000000000046,
                &a5);
    }
    (*((void (__fastcall **)(PROPVARIANT *))*v12 + 2))(v12);
  }
  *a6 = (void *)a5;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800115d4  mov     rax, rsp
0x1800115d7  push    rbx
0x1800115d8  push    rbp
0x1800115d9  push    rsi
0x1800115da  push    rdi
0x1800115db  push    r14
0x1800115dd  push    r15
0x1800115df  sub     rsp, 38h
0x1800115e3  mov     rbp, rdx
0x1800115e6  mov     qword ptr [rax+28h], 0
0x1800115ee  mov     r15d, ecx
0x1800115f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800115f8  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800115fd  mov     rsi, r9
0x180011600  mov     r14d, r8d
0x180011603  mov     edi, 8007000Eh
0x180011608  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001160d  mov     [rsp+68h+var_48], rax
0x180011612  mov     rbx, rax
0x180011615  test    rax, rax
0x180011618  jz      loc_1800116B7
0x18001161e  lea     rax, ??_7Interval@StructuredQuery1@@6BIInterval@@@; const StructuredQuery1::Interval::`vftable'{for `IInterval'}
0x180011625  mov     [rbx+10h], r15d
0x180011629  mov     [rbx], rax
0x18001162c  lea     rax, ??_7Interval@StructuredQuery1@@6BIPersistStream@@@; const StructuredQuery1::Interval::`vftable'{for `IPersistStream'}
0x180011633  mov     [rbx+8], rax
0x180011637  mov     [rbx+30h], r14d
0x18001163b  mov     dword ptr [rbx+50h], 1
0x180011642  lock inc cs:dword_1800B134C
0x180011649  xor     eax, eax
0x18001164b  xorps   xmm0, xmm0
0x18001164e  movups  xmmword ptr [rbx+18h], xmm0
0x180011652  mov     [rbx+28h], rax
0x180011656  movups  xmmword ptr [rbx+38h], xmm0
0x18001165a  mov     [rbx+48h], rax
0x18001165e  test    rbx, rbx
0x180011661  jz      short loc_1800116B7
0x180011663  lea     rcx, [rbx+18h]; pvarDest
0x180011667  mov     rdx, rbp; pvarSrc
0x18001166a  call    cs:__imp_PropVariantCopy
0x180011670  mov     edi, eax
0x180011672  test    eax, eax
0x180011674  js      short loc_1800116A8
0x180011676  lea     rcx, [rbx+38h]; pvarDest
0x18001167a  mov     rdx, rsi; pvarSrc
0x18001167d  call    cs:__imp_PropVariantCopy
0x180011683  mov     edi, eax
0x180011685  test    eax, eax
0x180011687  js      short loc_1800116A8
0x180011689  mov     rax, [rbx]
0x18001168c  lea     r8, [rsp+68h+arg_20]
0x180011694  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001169b  mov     rcx, rbx
0x18001169e  mov     rax, [rax]
0x1800116a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a6  mov     edi, eax
0x1800116a8  mov     rax, [rbx]
0x1800116ab  mov     rcx, rbx
0x1800116ae  mov     rax, [rax+10h]
0x1800116b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116b7  mov     rax, [rsp+68h+arg_20]
0x1800116bf  mov     rcx, [rsp+68h+arg_28]
0x1800116c7  mov     [rcx], rax
0x1800116ca  mov     eax, edi
0x1800116cc  add     rsp, 38h
0x1800116d0  pop     r15
0x1800116d2  pop     r14
0x1800116d4  pop     rdi
0x1800116d5  pop     rsi
0x1800116d6  pop     rbp
0x1800116d7  pop     rbx
0x1800116d8  retn
```
