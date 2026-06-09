# WriteOutXMPIntegerSequence(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)

- ea: `0x1800133d8`
- end: `0x180013538`
- name: `?WriteOutXMPIntegerSequence@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `352`
- prototype: `int(struct IWICMetadataQueryWriter *, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012160`

## callees

- `0x1800089f0`
- `0x1800133d8`
- `0x180016a40`
- `0x180017408`
- `0x1800201e8`
- `0x1800209a4`
- `0x180020a9c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800134ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800134fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800134ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800134fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteOutXMPIntegerSequence(
        struct IWICMetadataQueryWriter *a1,
        const unsigned __int16 *a2,
        const struct tagPROPVARIANT *a3)
{
  int PropVariantElement; // ebx
  unsigned int PropVariantElementCount; // esi
  unsigned int i; // edi
  __int64 v10; // [rsp+20h] [rbp-E0h]
  PROPVARIANT pvar; // [rsp+30h] [rbp-D0h] BYREF
  PROPVARIANT v12; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v13[264]; // [rsp+60h] [rbp-A0h] BYREF

  PropVariantElement = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *))a1->lpVtbl->RemoveMetadataByName)(a1);
  if ( (int)(PropVariantElement + 0x80000000) < 0 || PropVariantElement == -2003292352 )
  {
    memset_0(v13, 0, 0x208u);
    PropVariantElementCount = GetPropVariantElementCount(a3);
    PropVariantElement = 0;
    for ( i = 0; i < PropVariantElementCount; ++i )
    {
      if ( PropVariantElement < 0 )
        break;
      LODWORD(v10) = i;
      PropVariantElement = StringCchPrintfW(v13, 0x104u, L"%s/{uint=%d}", a2, v10);
      if ( PropVariantElement >= 0 )
      {
        memset(&v12, 0, sizeof(v12));
        memset(&pvar, 0, sizeof(pvar));
        PropVariantElement = GetPropVariantElement(a3, i, &v12);
        if ( PropVariantElement >= 0 )
        {
          PropVariantElement = ConvertPropvarToNumericalString(&v12, &pvar);
          if ( PropVariantElement >= 0 )
            PropVariantElement = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a1->lpVtbl->SetMetadataByName)(
                                   a1,
                                   v13,
                                   &pvar);
        }
        PropVariantClear(&pvar);
        PropVariantClear(&v12);
      }
    }
  }
  return (unsigned int)PropVariantElement;
}

```

## disassembly

```asm
0x1800133d8  push    rbp
0x1800133da  push    rbx
0x1800133db  push    rsi
0x1800133dc  push    rdi
0x1800133dd  push    r12
0x1800133df  push    r14
0x1800133e1  push    r15
0x1800133e3  lea     rbp, [rsp-180h]
0x1800133eb  sub     rsp, 280h
0x1800133f2  mov     rax, cs:__security_cookie
0x1800133f9  xor     rax, rsp
0x1800133fc  mov     [rbp+1B0h+var_40], rax
0x180013403  mov     r15, r8
0x180013406  mov     r12, rdx
0x180013409  mov     r14, rcx
0x18001340c  mov     rax, [rcx]
0x18001340f  mov     rax, [rax+40h]
0x180013413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013418  mov     ebx, eax
0x18001341a  mov     eax, 80000000h
0x18001341f  lea     ecx, [rbx+rax]
0x180013422  test    eax, ecx
0x180013424  jnz     short loc_180013432
0x180013426  cmp     ebx, 88982F40h
0x18001342c  jnz     loc_180013514
0x180013432  xor     edx, edx; Val
0x180013434  mov     r8d, 208h; Size
0x18001343a  lea     rcx, [rsp+2B0h+var_250]; void *
0x18001343f  call    memset_0
0x180013444  mov     rcx, r15; struct tagPROPVARIANT *
0x180013447  call    ?GetPropVariantElementCount@@YAKPEBUtagPROPVARIANT@@@Z; GetPropVariantElementCount(tagPROPVARIANT const *)
0x18001344c  mov     esi, eax
0x18001344e  xor     ebx, ebx
0x180013450  xor     edi, edi
0x180013452  test    eax, eax
0x180013454  jz      loc_180013514
0x18001345a  test    ebx, ebx
0x18001345c  js      loc_180013514
0x180013462  mov     [rsp+2B0h+var_290], edi
0x180013466  mov     r9, r12
0x180013469  lea     r8, aSUintD; "%s/{uint=%d}"
0x180013470  mov     edx, 104h; unsigned __int64
0x180013475  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18001347a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001347f  mov     ebx, eax
0x180013481  test    eax, eax
0x180013483  js      loc_18001350A
0x180013489  xorps   xmm0, xmm0
0x18001348c  xor     eax, eax
0x18001348e  movups  xmmword ptr [rsp+2B0h+var_268], xmm0
0x180013493  mov     qword ptr [rsp+2B0h+var_268+10h], rax
0x180013498  movups  xmmword ptr [rsp+2B0h+pvar], xmm0
0x18001349d  mov     qword ptr [rsp+2B0h+pvar+10h], rax
0x1800134a2  lea     r8, [rsp+2B0h+var_268]; struct tagPROPVARIANT *
0x1800134a7  mov     edx, edi; unsigned int
0x1800134a9  mov     rcx, r15; struct tagPROPVARIANT *
0x1800134ac  call    ?GetPropVariantElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; GetPropVariantElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x1800134b1  mov     ebx, eax
0x1800134b3  test    eax, eax
0x1800134b5  js      short loc_1800134E7
0x1800134b7  lea     rdx, [rsp+2B0h+pvar]; struct tagPROPVARIANT *
0x1800134bc  lea     rcx, [rsp+2B0h+var_268]; struct tagPROPVARIANT *
0x1800134c1  call    ?ConvertPropvarToNumericalString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToNumericalString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800134c6  mov     ebx, eax
0x1800134c8  test    eax, eax
0x1800134ca  js      short loc_1800134E7
0x1800134cc  mov     rax, [r14]
0x1800134cf  lea     r8, [rsp+2B0h+pvar]
0x1800134d4  lea     rdx, [rsp+2B0h+var_250]
0x1800134d9  mov     rcx, r14
0x1800134dc  mov     rax, [rax+38h]
0x1800134e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134e5  mov     ebx, eax
0x1800134e7  lea     rcx, [rsp+2B0h+pvar]; pvar
0x1800134ec  call    cs:__imp_PropVariantClear
0x1800134f3  nop     dword ptr [rax+rax+00h]
0x1800134f8  nop
0x1800134f9  lea     rcx, [rsp+2B0h+var_268]; pvar
0x1800134fe  call    cs:__imp_PropVariantClear
0x180013505  nop     dword ptr [rax+rax+00h]
0x18001350a  inc     edi
0x18001350c  cmp     edi, esi
0x18001350e  jb      loc_18001345A
0x180013514  mov     eax, ebx
0x180013516  mov     rcx, [rbp+1B0h+var_40]
0x18001351d  xor     rcx, rsp; StackCookie
0x180013520  call    __security_check_cookie
0x180013525  add     rsp, 280h
0x18001352c  pop     r15
0x18001352e  pop     r14
0x180013530  pop     r12
0x180013532  pop     rdi
0x180013533  pop     rsi
0x180013534  pop     rbx
0x180013535  pop     rbp
0x180013536  retn
```
