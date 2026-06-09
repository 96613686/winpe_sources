# WriteOutXMPSequence(IWICMetadataQueryWriter *,ushort const *,tagPROPVARIANT const *)

- ea: `0x1800136c0`
- end: `0x180013843`
- name: `?WriteOutXMPSequence@@YAJPEAUIWICMetadataQueryWriter@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryWriter *, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011dd0`

## callees

- `0x1800076b0`
- `0x180007b20`
- `0x1800136c0`
- `0x180016020`
- `0x1800169b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800137cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800137cf`

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
0x1800136c0  mov     [rsp+arg_18], rbx
0x1800136c5  push    rbp
0x1800136c6  push    rsi
0x1800136c7  push    rdi
0x1800136c8  push    r14
0x1800136ca  push    r15
0x1800136cc  sub     rsp, 270h
0x1800136d3  mov     rax, cs:__security_cookie
0x1800136da  xor     rax, rsp
0x1800136dd  mov     [rsp+298h+var_38], rax
0x1800136e5  mov     rax, [rcx]
0x1800136e8  mov     rsi, r8
0x1800136eb  mov     rbp, rdx
0x1800136ee  mov     r14, rcx
0x1800136f1  mov     rax, [rax+40h]
0x1800136f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136fa  mov     ebx, eax
0x1800136fc  mov     eax, 80000000h
0x180013701  lea     ecx, [rbx+rax]
0x180013704  test    eax, ecx
0x180013706  jnz     short loc_180013714
0x180013708  cmp     ebx, 88982F40h
0x18001370e  jnz     loc_18001381A
0x180013714  xor     edx, edx; Val
0x180013716  lea     rcx, [rsp+298h+var_248]; void *
0x18001371b  mov     r8d, 208h; Size
0x180013721  call    memset_0
0x180013726  mov     r15d, 1Fh
0x18001372c  cmp     [rsi], r15w
0x180013730  jz      loc_1800137E2
0x180013736  mov     eax, 101Fh
0x18001373b  cmp     [rsi], ax
0x18001373e  jz      short loc_18001374A
0x180013740  mov     ebx, 8000FFFFh
0x180013745  jmp     loc_18001381A
0x18001374a  xor     ebx, ebx
0x18001374c  xor     edi, edi
0x18001374e  cmp     [rsi+8], ebx
0x180013751  jbe     loc_18001381A
0x180013757  test    ebx, ebx
0x180013759  js      loc_18001381A
0x18001375f  mov     r9, rbp
0x180013762  mov     [rsp+298h+var_278], edi
0x180013766  lea     r8, aSUintD; "%s/{uint=%d}"
0x18001376d  mov     edx, 104h; unsigned __int64
0x180013772  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x180013777  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001377c  mov     ebx, eax
0x18001377e  test    eax, eax
0x180013780  js      short loc_1800137D5
0x180013782  mov     rcx, [rsi+10h]
0x180013786  lea     rdx, [rsp+298h+pvar+8]; unsigned __int16 **
0x18001378b  xorps   xmm0, xmm0
0x18001378e  xor     eax, eax
0x180013790  movups  xmmword ptr [rsp+30h], xmm0
0x180013795  mov     qword ptr [rsp+298h+pvar+10h], rax
0x18001379a  mov     word ptr [rsp+298h+pvar], r15w
0x1800137a0  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x1800137a4  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x1800137a9  mov     ebx, eax
0x1800137ab  test    eax, eax
0x1800137ad  js      short loc_1800137CA
0x1800137af  mov     rax, [r14]
0x1800137b2  lea     r8, [rsp+298h+pvar]
0x1800137b7  lea     rdx, [rsp+298h+var_248]
0x1800137bc  mov     rcx, r14
0x1800137bf  mov     rax, [rax+38h]
0x1800137c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137c8  mov     ebx, eax
0x1800137ca  lea     rcx, [rsp+298h+pvar]; pvar
0x1800137cf  call    cs:__imp_PropVariantClear
0x1800137d5  inc     edi
0x1800137d7  cmp     edi, [rsi+8]
0x1800137da  jb      loc_180013757
0x1800137e0  jmp     short loc_18001381A
0x1800137e2  mov     r9, rbp
0x1800137e5  lea     r8, aSUint0; "%s/{uint=0}"
0x1800137ec  mov     edx, 104h; unsigned __int64
0x1800137f1  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x1800137f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800137fb  mov     ebx, eax
0x1800137fd  test    eax, eax
0x1800137ff  js      short loc_18001381A
0x180013801  mov     rax, [r14]
0x180013804  lea     rdx, [rsp+298h+var_248]
0x180013809  mov     r8, rsi
0x18001380c  mov     rcx, r14
0x18001380f  mov     rax, [rax+38h]
0x180013813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013818  mov     ebx, eax
0x18001381a  mov     eax, ebx
0x18001381c  mov     rcx, [rsp+298h+var_38]
0x180013824  xor     rcx, rsp; StackCookie
0x180013827  call    __security_check_cookie
0x18001382c  mov     rbx, [rsp+298h+arg_18]
0x180013834  add     rsp, 270h
0x18001383b  pop     r15
0x18001383d  pop     r14
0x18001383f  pop     rdi
0x180013840  pop     rsi
0x180013841  pop     rbp
0x180013842  retn
```
