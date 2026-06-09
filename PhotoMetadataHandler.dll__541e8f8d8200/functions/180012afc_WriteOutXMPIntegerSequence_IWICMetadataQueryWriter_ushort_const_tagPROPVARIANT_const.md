# WriteOutXMPIntegerSequence(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)

- ea: `0x180012afc`
- end: `0x180012c4b`
- name: `?WriteOutXMPIntegerSequence@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `335`
- prototype: `int(struct IWICMetadataQueryWriter *, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011940`

## callees

- `0x1800076b0`
- `0x180012afc`
- `0x180016020`
- `0x1800169b8`
- `0x18001f2c0`
- `0x18001fa18`
- `0x18001fafc`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c0c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c18`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c0c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c18`

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
0x180012afc  push    rbp
0x180012afe  push    rbx
0x180012aff  push    rsi
0x180012b00  push    rdi
0x180012b01  push    r12
0x180012b03  push    r14
0x180012b05  push    r15
0x180012b07  lea     rbp, [rsp-180h]
0x180012b0f  sub     rsp, 280h
0x180012b16  mov     rax, cs:__security_cookie
0x180012b1d  xor     rax, rsp
0x180012b20  mov     [rbp+1B0h+var_40], rax
0x180012b27  mov     r15, r8
0x180012b2a  mov     r12, rdx
0x180012b2d  mov     r14, rcx
0x180012b30  mov     rax, [rcx]
0x180012b33  mov     rax, [rax+40h]
0x180012b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b3c  mov     ebx, eax
0x180012b3e  mov     eax, 80000000h
0x180012b43  lea     ecx, [rbx+rax]
0x180012b46  test    eax, ecx
0x180012b48  jnz     short loc_180012B56
0x180012b4a  cmp     ebx, 88982F40h
0x180012b50  jnz     loc_180012C28
0x180012b56  xor     edx, edx; Val
0x180012b58  mov     r8d, 208h; Size
0x180012b5e  lea     rcx, [rsp+2B0h+var_250]; void *
0x180012b63  call    memset_0
0x180012b68  mov     rcx, r15; struct tagPROPVARIANT *
0x180012b6b  call    ?GetPropVariantElementCount@@YAKPEBUtagPROPVARIANT@@@Z; GetPropVariantElementCount(tagPROPVARIANT const *)
0x180012b70  mov     esi, eax
0x180012b72  xor     ebx, ebx
0x180012b74  xor     edi, edi
0x180012b76  test    eax, eax
0x180012b78  jz      loc_180012C28
0x180012b7e  test    ebx, ebx
0x180012b80  js      loc_180012C28
0x180012b86  mov     [rsp+2B0h+var_290], edi
0x180012b8a  mov     r9, r12
0x180012b8d  lea     r8, aSUintD; "%s/{uint=%d}"
0x180012b94  mov     edx, 104h; unsigned __int64
0x180012b99  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180012b9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012ba3  mov     ebx, eax
0x180012ba5  test    eax, eax
0x180012ba7  js      short loc_180012C1E
0x180012ba9  xorps   xmm0, xmm0
0x180012bac  xor     eax, eax
0x180012bae  movups  xmmword ptr [rsp+2B0h+var_268], xmm0
0x180012bb3  mov     qword ptr [rsp+2B0h+var_268+10h], rax
0x180012bb8  movups  xmmword ptr [rsp+2B0h+pvar], xmm0
0x180012bbd  mov     qword ptr [rsp+2B0h+pvar+10h], rax
0x180012bc2  lea     r8, [rsp+2B0h+var_268]; struct tagPROPVARIANT *
0x180012bc7  mov     edx, edi; unsigned int
0x180012bc9  mov     rcx, r15; struct tagPROPVARIANT *
0x180012bcc  call    ?GetPropVariantElement@@YAJPEBUtagPROPVARIANT@@KPEAU1@@Z; GetPropVariantElement(tagPROPVARIANT const *,ulong,tagPROPVARIANT *)
0x180012bd1  mov     ebx, eax
0x180012bd3  test    eax, eax
0x180012bd5  js      short loc_180012C07
0x180012bd7  lea     rdx, [rsp+2B0h+pvar]; struct tagPROPVARIANT *
0x180012bdc  lea     rcx, [rsp+2B0h+var_268]; struct tagPROPVARIANT *
0x180012be1  call    ?ConvertPropvarToNumericalString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToNumericalString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012be6  mov     ebx, eax
0x180012be8  test    eax, eax
0x180012bea  js      short loc_180012C07
0x180012bec  mov     rax, [r14]
0x180012bef  lea     r8, [rsp+2B0h+pvar]
0x180012bf4  lea     rdx, [rsp+2B0h+var_250]
0x180012bf9  mov     rcx, r14
0x180012bfc  mov     rax, [rax+38h]
0x180012c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c05  mov     ebx, eax
0x180012c07  lea     rcx, [rsp+2B0h+pvar]; pvar
0x180012c0c  call    cs:__imp_PropVariantClear
0x180012c12  nop
0x180012c13  lea     rcx, [rsp+2B0h+var_268]; pvar
0x180012c18  call    cs:__imp_PropVariantClear
0x180012c1e  inc     edi
0x180012c20  cmp     edi, esi
0x180012c22  jb      loc_180012B7E
0x180012c28  mov     eax, ebx
0x180012c2a  mov     rcx, [rbp+1B0h+var_40]
0x180012c31  xor     rcx, rsp; StackCookie
0x180012c34  call    __security_check_cookie
0x180012c39  add     rsp, 280h
0x180012c40  pop     r15
0x180012c42  pop     r14
0x180012c44  pop     r12
0x180012c46  pop     rdi
0x180012c47  pop     rsi
0x180012c48  pop     rbx
0x180012c49  pop     rbp
0x180012c4a  retn
```
