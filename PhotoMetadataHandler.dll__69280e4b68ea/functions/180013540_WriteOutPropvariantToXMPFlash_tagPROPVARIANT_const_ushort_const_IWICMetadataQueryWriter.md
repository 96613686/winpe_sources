# WriteOutPropvariantToXMPFlash(tagPROPVARIANT const *,ushort const *,IWICMetadataQueryWriter *)

- ea: `0x180013540`
- end: `0x180013955`
- name: `?WriteOutPropvariantToXMPFlash@@YAJPEBUtagPROPVARIANT@@PEBGPEAUIWICMetadataQueryWriter@@@Z`
- size: `1045`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const unsigned __int16 *, struct IWICMetadataQueryWriter *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012160`

## callees

- `0x1800089f0`
- `0x180013540`
- `0x180016a40`
- `0x180017408`
- `0x18002019c`
- `0x1800201e8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001364d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001365f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800136f9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001370b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800137a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800137b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013858`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001386a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001390a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001391c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001364d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001365f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800136f9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001370b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800137a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800137b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013858`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001386a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001390a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001391c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteOutPropvariantToXMPFlash(
        const struct tagPROPVARIANT *a1,
        const unsigned __int16 *a2,
        struct IWICMetadataQueryWriter *a3)
{
  int v5; // ebx
  unsigned int bVal; // edi
  PROPVARIANT v8; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v10[264]; // [rsp+50h] [rbp-B0h] BYREF

  switch ( a1->vt )
  {
    case 0x11u:
      bVal = a1->bVal;
      break;
    case 0x12u:
      bVal = a1->uiVal;
      break;
    case 0x13u:
      bVal = a1->ulVal;
      break;
    default:
      return (unsigned int)-2003292271;
  }
  memset_0(v10, 0, 0x208u);
  v5 = StringCchPrintfW(v10, 0x104u, L"%s/exif:Fired", a2);
  if ( v5 >= 0 )
  {
    memset(&v8, 0, sizeof(v8));
    v8.vt = 11;
    if ( (bVal & 1) != 0 )
      v8.iVal = -1;
    else
      v8.iVal = 0;
    memset(&pvar, 0, sizeof(pvar));
    v5 = ConvertPropvarToBooleanString(&v8, &pvar);
    if ( v5 >= 0 )
      v5 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a3->lpVtbl->SetMetadataByName)(
             a3,
             v10,
             &pvar);
    PropVariantClear(&pvar);
    PropVariantClear(&v8);
    if ( v5 >= 0 )
    {
      v5 = StringCchPrintfW(v10, 0x104u, L"%s/exif:Return", a2, *(_OWORD *)&v8.vt, v8.bstrblobVal.pData);
      if ( v5 >= 0 )
      {
        memset(&v8, 0, sizeof(v8));
        v8.vt = 17;
        v8.cVal = (bVal >> 1) & 3;
        memset(&pvar, 0, sizeof(pvar));
        v5 = ConvertPropvarToNumericalString(&v8, &pvar);
        if ( v5 >= 0 )
          v5 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a3->lpVtbl->SetMetadataByName)(
                 a3,
                 v10,
                 &pvar);
        PropVariantClear(&pvar);
        PropVariantClear(&v8);
        if ( v5 >= 0 )
        {
          v5 = StringCchPrintfW(v10, 0x104u, L"%s/exif:Mode", a2);
          if ( v5 >= 0 )
          {
            memset(&v8, 0, sizeof(v8));
            v8.vt = 17;
            v8.cVal = (bVal >> 3) & 3;
            memset(&pvar, 0, sizeof(pvar));
            v5 = ConvertPropvarToNumericalString(&v8, &pvar);
            if ( v5 >= 0 )
              v5 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a3->lpVtbl->SetMetadataByName)(
                     a3,
                     v10,
                     &pvar);
            PropVariantClear(&pvar);
            PropVariantClear(&v8);
            if ( v5 >= 0 )
            {
              v5 = StringCchPrintfW(v10, 0x104u, L"%s/exif:Function", a2);
              if ( v5 >= 0 )
              {
                memset(&v8, 0, sizeof(v8));
                v8.vt = 11;
                if ( (bVal & 0x20) != 0 )
                  v8.iVal = -1;
                else
                  v8.iVal = 0;
                memset(&pvar, 0, sizeof(pvar));
                v5 = ConvertPropvarToBooleanString(&v8, &pvar);
                if ( v5 >= 0 )
                  v5 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a3->lpVtbl->SetMetadataByName)(
                         a3,
                         v10,
                         &pvar);
                PropVariantClear(&pvar);
                PropVariantClear(&v8);
                if ( v5 >= 0 )
                {
                  v5 = StringCchPrintfW(v10, 0x104u, L"%s/exif:RedEyeMode", a2, *(_OWORD *)&v8.vt, v8.bstrblobVal.pData);
                  if ( v5 >= 0 )
                  {
                    memset(&v8, 0, sizeof(v8));
                    v8.vt = 11;
                    if ( (bVal & 0x40) != 0 )
                      v8.iVal = -1;
                    else
                      v8.iVal = 0;
                    memset(&pvar, 0, sizeof(pvar));
                    v5 = ConvertPropvarToBooleanString(&v8, &pvar);
                    if ( v5 >= 0 )
                      v5 = ((__int64 (__fastcall *)(struct IWICMetadataQueryWriter *, unsigned __int16 *, PROPVARIANT *))a3->lpVtbl->SetMetadataByName)(
                             a3,
                             v10,
                             &pvar);
                    PropVariantClear(&pvar);
                    PropVariantClear(&v8);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013540  mov     [rsp-8+arg_18], rbx
0x180013545  push    rbp
0x180013546  push    rsi
0x180013547  push    rdi
0x180013548  push    r12
0x18001354a  push    r13
0x18001354c  push    r14
0x18001354e  push    r15
0x180013550  lea     rbp, [rsp-170h]
0x180013558  sub     rsp, 270h
0x18001355f  mov     rax, cs:__security_cookie
0x180013566  xor     rax, rsp
0x180013569  mov     [rbp+1A0h+var_40], rax
0x180013570  mov     rsi, r8
0x180013573  mov     r14, rdx
0x180013576  movzx   edx, word ptr [rcx]
0x180013579  sub     edx, 11h
0x18001357c  jz      short loc_18001359D
0x18001357e  sub     edx, 1
0x180013581  jz      short loc_180013597
0x180013583  cmp     edx, 1
0x180013586  jz      short loc_180013592
0x180013588  mov     ebx, 88982F91h
0x18001358d  jmp     loc_180013928
0x180013592  mov     edi, [rcx+8]
0x180013595  jmp     short loc_1800135A1
0x180013597  movzx   edi, word ptr [rcx+8]
0x18001359b  jmp     short loc_1800135A1
0x18001359d  movzx   edi, byte ptr [rcx+8]
0x1800135a1  xor     edx, edx; Val
0x1800135a3  mov     r8d, 208h; Size
0x1800135a9  lea     rcx, [rsp+2A0h+var_250]; void *
0x1800135ae  call    memset_0
0x1800135b3  mov     r9, r14
0x1800135b6  lea     r8, aSExifFired; "%s/exif:Fired"
0x1800135bd  mov     r15d, 104h
0x1800135c3  mov     edx, r15d; unsigned __int64
0x1800135c6  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x1800135cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800135d0  mov     ebx, eax
0x1800135d2  test    eax, eax
0x1800135d4  js      loc_180013928
0x1800135da  xorps   xmm0, xmm0
0x1800135dd  xor     ecx, ecx
0x1800135df  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x1800135e4  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x1800135e9  lea     r13d, [rcx+0Bh]
0x1800135ed  mov     word ptr [rsp+2A0h+var_280], r13w
0x1800135f3  or      r12d, 0FFFFFFFFh
0x1800135f7  test    dil, 1
0x1800135fb  jz      short loc_180013605
0x1800135fd  mov     word ptr [rsp+2A0h+var_280+8], r12w
0x180013603  jmp     short loc_18001360C
0x180013605  xor     eax, eax
0x180013607  mov     word ptr [rsp+2A0h+var_280+8], ax
0x18001360c  xor     eax, eax
0x18001360e  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x180013613  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180013618  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x18001361d  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x180013622  call    ?ConvertPropvarToBooleanString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToBooleanString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180013627  mov     ebx, eax
0x180013629  test    eax, eax
0x18001362b  js      short loc_180013648
0x18001362d  mov     rax, [rsi]
0x180013630  lea     r8, [rsp+2A0h+pvar]
0x180013635  lea     rdx, [rsp+2A0h+var_250]
0x18001363a  mov     rcx, rsi
0x18001363d  mov     rax, [rax+38h]
0x180013641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013646  mov     ebx, eax
0x180013648  lea     rcx, [rsp+2A0h+pvar]; pvar
0x18001364d  call    cs:__imp_PropVariantClear
0x180013654  nop     dword ptr [rax+rax+00h]
0x180013659  nop
0x18001365a  lea     rcx, [rsp+2A0h+var_280]; pvar
0x18001365f  call    cs:__imp_PropVariantClear
0x180013666  nop     dword ptr [rax+rax+00h]
0x18001366b  test    ebx, ebx
0x18001366d  js      loc_180013928
0x180013673  mov     r9, r14
0x180013676  lea     r8, aSExifReturn; "%s/exif:Return"
0x18001367d  mov     rdx, r15; unsigned __int64
0x180013680  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180013685  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001368a  mov     ebx, eax
0x18001368c  test    eax, eax
0x18001368e  js      loc_180013928
0x180013694  mov     eax, edi
0x180013696  shr     eax, 1
0x180013698  and     eax, 3
0x18001369b  xorps   xmm0, xmm0
0x18001369e  xor     ecx, ecx
0x1800136a0  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x1800136a5  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x1800136aa  mov     ecx, 11h
0x1800136af  mov     word ptr [rsp+2A0h+var_280], cx
0x1800136b4  mov     byte ptr [rsp+2A0h+var_280+8], al
0x1800136b8  xor     eax, eax
0x1800136ba  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x1800136bf  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x1800136c4  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x1800136c9  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x1800136ce  call    ?ConvertPropvarToNumericalString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToNumericalString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800136d3  mov     ebx, eax
0x1800136d5  test    eax, eax
0x1800136d7  js      short loc_1800136F4
0x1800136d9  mov     rax, [rsi]
0x1800136dc  lea     r8, [rsp+2A0h+pvar]
0x1800136e1  lea     rdx, [rsp+2A0h+var_250]
0x1800136e6  mov     rcx, rsi
0x1800136e9  mov     rax, [rax+38h]
0x1800136ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136f2  mov     ebx, eax
0x1800136f4  lea     rcx, [rsp+2A0h+pvar]; pvar
0x1800136f9  call    cs:__imp_PropVariantClear
0x180013700  nop     dword ptr [rax+rax+00h]
0x180013705  nop
0x180013706  lea     rcx, [rsp+2A0h+var_280]; pvar
0x18001370b  call    cs:__imp_PropVariantClear
0x180013712  nop     dword ptr [rax+rax+00h]
0x180013717  test    ebx, ebx
0x180013719  js      loc_180013928
0x18001371f  mov     r9, r14
0x180013722  lea     r8, aSExifMode; "%s/exif:Mode"
0x180013729  mov     rdx, r15; unsigned __int64
0x18001372c  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180013731  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013736  mov     ebx, eax
0x180013738  test    eax, eax
0x18001373a  js      loc_180013928
0x180013740  mov     eax, edi
0x180013742  shr     eax, 3
0x180013745  and     eax, 3
0x180013748  xorps   xmm0, xmm0
0x18001374b  xor     ecx, ecx
0x18001374d  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x180013752  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x180013757  mov     ecx, 11h
0x18001375c  mov     word ptr [rsp+2A0h+var_280], cx
0x180013761  mov     byte ptr [rsp+2A0h+var_280+8], al
0x180013765  xor     eax, eax
0x180013767  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x18001376c  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180013771  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180013776  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x18001377b  call    ?ConvertPropvarToNumericalString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToNumericalString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180013780  mov     ebx, eax
0x180013782  test    eax, eax
0x180013784  js      short loc_1800137A1
0x180013786  mov     rax, [rsi]
0x180013789  lea     r8, [rsp+2A0h+pvar]
0x18001378e  lea     rdx, [rsp+2A0h+var_250]
0x180013793  mov     rcx, rsi
0x180013796  mov     rax, [rax+38h]
0x18001379a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001379f  mov     ebx, eax
0x1800137a1  lea     rcx, [rsp+2A0h+pvar]; pvar
0x1800137a6  call    cs:__imp_PropVariantClear
0x1800137ad  nop     dword ptr [rax+rax+00h]
0x1800137b2  nop
0x1800137b3  lea     rcx, [rsp+2A0h+var_280]; pvar
0x1800137b8  call    cs:__imp_PropVariantClear
0x1800137bf  nop     dword ptr [rax+rax+00h]
0x1800137c4  test    ebx, ebx
0x1800137c6  js      loc_180013928
0x1800137cc  mov     r9, r14
0x1800137cf  lea     r8, aSExifFunction; "%s/exif:Function"
0x1800137d6  mov     rdx, r15; unsigned __int64
0x1800137d9  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x1800137de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800137e3  mov     ebx, eax
0x1800137e5  test    eax, eax
0x1800137e7  js      loc_180013928
0x1800137ed  xorps   xmm0, xmm0
0x1800137f0  xor     ecx, ecx
0x1800137f2  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x1800137f7  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x1800137fc  mov     word ptr [rsp+2A0h+var_280], r13w
0x180013802  bt      edi, 5
0x180013806  jnb     short loc_180013810
0x180013808  mov     word ptr [rsp+2A0h+var_280+8], r12w
0x18001380e  jmp     short loc_180013817
0x180013810  xor     eax, eax
0x180013812  mov     word ptr [rsp+2A0h+var_280+8], ax
0x180013817  xor     eax, eax
0x180013819  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x18001381e  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180013823  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180013828  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x18001382d  call    ?ConvertPropvarToBooleanString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToBooleanString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180013832  mov     ebx, eax
0x180013834  test    eax, eax
0x180013836  js      short loc_180013853
0x180013838  mov     rax, [rsi]
0x18001383b  lea     r8, [rsp+2A0h+pvar]
0x180013840  lea     rdx, [rsp+2A0h+var_250]
0x180013845  mov     rcx, rsi
0x180013848  mov     rax, [rax+38h]
0x18001384c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013851  mov     ebx, eax
0x180013853  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180013858  call    cs:__imp_PropVariantClear
0x18001385f  nop     dword ptr [rax+rax+00h]
0x180013864  nop
0x180013865  lea     rcx, [rsp+2A0h+var_280]; pvar
0x18001386a  call    cs:__imp_PropVariantClear
0x180013871  nop     dword ptr [rax+rax+00h]
0x180013876  test    ebx, ebx
0x180013878  js      loc_180013928
0x18001387e  mov     r9, r14
0x180013881  lea     r8, aSExifRedeyemod; "%s/exif:RedEyeMode"
0x180013888  mov     rdx, r15; unsigned __int64
0x18001388b  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180013890  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013895  mov     ebx, eax
0x180013897  test    eax, eax
0x180013899  js      loc_180013928
0x18001389f  xorps   xmm0, xmm0
0x1800138a2  xor     eax, eax
0x1800138a4  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x1800138a9  mov     qword ptr [rsp+2A0h+var_280+10h], rax
0x1800138ae  mov     word ptr [rsp+2A0h+var_280], r13w
0x1800138b4  bt      edi, 6
0x1800138b8  jnb     short loc_1800138C2
0x1800138ba  mov     word ptr [rsp+2A0h+var_280+8], r12w
0x1800138c0  jmp     short loc_1800138C9
0x1800138c2  xor     eax, eax
0x1800138c4  mov     word ptr [rsp+2A0h+var_280+8], ax
0x1800138c9  xor     eax, eax
0x1800138cb  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x1800138d0  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x1800138d5  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x1800138da  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x1800138df  call    ?ConvertPropvarToBooleanString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToBooleanString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800138e4  mov     ebx, eax
0x1800138e6  test    eax, eax
0x1800138e8  js      short loc_180013905
0x1800138ea  mov     rax, [rsi]
0x1800138ed  lea     r8, [rsp+2A0h+pvar]
0x1800138f2  lea     rdx, [rsp+2A0h+var_250]
0x1800138f7  mov     rcx, rsi
0x1800138fa  mov     rax, [rax+38h]
0x1800138fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013903  mov     ebx, eax
0x180013905  lea     rcx, [rsp+2A0h+pvar]; pvar
0x18001390a  call    cs:__imp_PropVariantClear
0x180013911  nop     dword ptr [rax+rax+00h]
0x180013916  nop
0x180013917  lea     rcx, [rsp+2A0h+var_280]; pvar
0x18001391c  call    cs:__imp_PropVariantClear
0x180013923  nop     dword ptr [rax+rax+00h]
0x180013928  mov     eax, ebx
0x18001392a  mov     rcx, [rbp+1A0h+var_40]
0x180013931  xor     rcx, rsp; StackCookie
0x180013934  call    __security_check_cookie
0x180013939  mov     rbx, [rsp+2A0h+arg_18]
0x180013941  add     rsp, 270h
0x180013948  pop     r15
0x18001394a  pop     r14
0x18001394c  pop     r13
0x18001394e  pop     r12
0x180013950  pop     rdi
0x180013951  pop     rsi
0x180013952  pop     rbp
0x180013953  retn
```
