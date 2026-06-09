# WriteOutXMPSequence(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)

- ea: `0x18001405c`
- end: `0x1800141e6`
- name: `?WriteOutXMPSequence@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryWriter *, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012660`

## callees

- `0x1800089f0`
- `0x180008ea0`
- `0x18001405c`
- `0x180016a40`
- `0x180017408`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001416b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001416b`

## pseudocode

```c
__int64 __fastcall WriteOutXMPSequence(
        struct IWICMetadataQueryWriter *a1,
        const unsigned __int16 *a2,
        const struct tagPROPVARIANT *a3)
{
  int v6; // ebx
  __int64 i; // rdi
  BYTE *pData; // rcx
  __int64 v10; // [rsp+20h] [rbp-278h]
  PROPVARIANT pvar; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v12[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *))a1->lpVtbl->RemoveMetadataByName)(a1);
  if ( (int)(v6 + 0x80000000) < 0 || v6 == -2003292352 )
  {
    memset_0(v12, 0, 0x208u);
    if ( a3->vt == 31 )
    {
      v6 = StringCchPrintfW(v12, 0x104u, L"%s/{uint=0}", a2);
      if ( v6 >= 0 )
        return ((unsigned int (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, const struct tagPROPVARIANT *))a1->lpVtbl->SetMetadataByName)(
                 a1,
                 v12,
                 a3);
    }
    else if ( a3->vt == 4127 )
    {
      v6 = 0;
      for ( i = 0; (unsigned int)i < a3->lVal; i = (unsigned int)(i + 1) )
      {
        if ( v6 < 0 )
          break;
        LODWORD(v10) = i;
        v6 = StringCchPrintfW(v12, 0x104u, L"%s/{uint=%d}", a2, v10);
        if ( v6 >= 0 )
        {
          pData = a3->bstrblobVal.pData;
          memset(&pvar, 0, sizeof(pvar));
          pvar.vt = 31;
          v6 = PIXStrDup(*(const unsigned __int16 **)&pData[8 * i], &pvar.bstrVal);
          if ( v6 >= 0 )
            v6 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a1->lpVtbl->SetMetadataByName)(
                   a1,
                   v12,
                   &pvar);
          PropVariantClear(&pvar);
        }
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001405c  mov     [rsp+arg_18], rbx
0x180014061  push    rbp
0x180014062  push    rsi
0x180014063  push    rdi
0x180014064  push    r14
0x180014066  push    r15
0x180014068  sub     rsp, 270h
0x18001406f  mov     rax, cs:__security_cookie
0x180014076  xor     rax, rsp
0x180014079  mov     [rsp+298h+var_38], rax
0x180014081  mov     rax, [rcx]
0x180014084  mov     rsi, r8
0x180014087  mov     rbp, rdx
0x18001408a  mov     r14, rcx
0x18001408d  mov     rax, [rax+40h]
0x180014091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014096  mov     ebx, eax
0x180014098  mov     eax, 80000000h
0x18001409d  lea     ecx, [rbx+rax]
0x1800140a0  test    eax, ecx
0x1800140a2  jnz     short loc_1800140B0
0x1800140a4  cmp     ebx, 88982F40h
0x1800140aa  jnz     loc_1800141BC
0x1800140b0  xor     edx, edx; Val
0x1800140b2  lea     rcx, [rsp+298h+var_248]; void *
0x1800140b7  mov     r8d, 208h; Size
0x1800140bd  call    memset_0
0x1800140c2  mov     r15d, 1Fh
0x1800140c8  cmp     [rsi], r15w
0x1800140cc  jz      loc_180014184
0x1800140d2  mov     eax, 101Fh
0x1800140d7  cmp     [rsi], ax
0x1800140da  jz      short loc_1800140E6
0x1800140dc  mov     ebx, 8000FFFFh
0x1800140e1  jmp     loc_1800141BC
0x1800140e6  xor     ebx, ebx
0x1800140e8  xor     edi, edi
0x1800140ea  cmp     [rsi+8], ebx
0x1800140ed  jbe     loc_1800141BC
0x1800140f3  test    ebx, ebx
0x1800140f5  js      loc_1800141BC
0x1800140fb  mov     r9, rbp
0x1800140fe  mov     [rsp+298h+var_278], edi
0x180014102  lea     r8, aSUintD; "%s/{uint=%d}"
0x180014109  mov     edx, 104h; unsigned __int64
0x18001410e  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x180014113  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014118  mov     ebx, eax
0x18001411a  test    eax, eax
0x18001411c  js      short loc_180014177
0x18001411e  mov     rcx, [rsi+10h]
0x180014122  lea     rdx, [rsp+298h+pvar+8]; unsigned __int16 **
0x180014127  xorps   xmm0, xmm0
0x18001412a  xor     eax, eax
0x18001412c  movups  xmmword ptr [rsp+30h], xmm0
0x180014131  mov     qword ptr [rsp+298h+pvar+10h], rax
0x180014136  mov     word ptr [rsp+298h+pvar], r15w
0x18001413c  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x180014140  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x180014145  mov     ebx, eax
0x180014147  test    eax, eax
0x180014149  js      short loc_180014166
0x18001414b  mov     rax, [r14]
0x18001414e  lea     r8, [rsp+298h+pvar]
0x180014153  lea     rdx, [rsp+298h+var_248]
0x180014158  mov     rcx, r14
0x18001415b  mov     rax, [rax+38h]
0x18001415f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014164  mov     ebx, eax
0x180014166  lea     rcx, [rsp+298h+pvar]; pvar
0x18001416b  call    cs:__imp_PropVariantClear
0x180014172  nop     dword ptr [rax+rax+00h]
0x180014177  inc     edi
0x180014179  cmp     edi, [rsi+8]
0x18001417c  jb      loc_1800140F3
0x180014182  jmp     short loc_1800141BC
0x180014184  mov     r9, rbp
0x180014187  lea     r8, aSUint0; "%s/{uint=0}"
0x18001418e  mov     edx, 104h; unsigned __int64
0x180014193  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x180014198  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001419d  mov     ebx, eax
0x18001419f  test    eax, eax
0x1800141a1  js      short loc_1800141BC
0x1800141a3  mov     rax, [r14]
0x1800141a6  lea     rdx, [rsp+298h+var_248]
0x1800141ab  mov     r8, rsi
0x1800141ae  mov     rcx, r14
0x1800141b1  mov     rax, [rax+38h]
0x1800141b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141ba  mov     ebx, eax
0x1800141bc  mov     eax, ebx
0x1800141be  mov     rcx, [rsp+298h+var_38]
0x1800141c6  xor     rcx, rsp; StackCookie
0x1800141c9  call    __security_check_cookie
0x1800141ce  mov     rbx, [rsp+298h+arg_18]
0x1800141d6  add     rsp, 270h
0x1800141dd  pop     r15
0x1800141df  pop     r14
0x1800141e1  pop     rdi
0x1800141e2  pop     rsi
0x1800141e3  pop     rbp
0x1800141e4  retn
```
