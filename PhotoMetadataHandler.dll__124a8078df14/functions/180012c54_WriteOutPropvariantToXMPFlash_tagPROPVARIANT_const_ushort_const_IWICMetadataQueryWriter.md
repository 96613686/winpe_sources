# WriteOutPropvariantToXMPFlash(tagPROPVARIANT const *,ushort const *,IWICMetadataQueryWriter *)

- ea: `0x180012c54`
- end: `0x180013028`
- name: `?WriteOutPropvariantToXMPFlash@@YAJPEBUtagPROPVARIANT@@PEBGPEAUIWICMetadataQueryWriter@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const unsigned __int16 *, struct IWICMetadataQueryWriter *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011940`

## callees

- `0x1800076b0`
- `0x180012c54`
- `0x180016020`
- `0x1800169b8`
- `0x18001f274`
- `0x18001f2c0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012d61`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012d6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e0d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ea2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012eae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012f48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012f54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012fea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ff6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012d61`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012d6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012e0d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ea2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012eae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012f48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012f54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012fea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ff6`

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
0x180012c54  mov     [rsp-8+arg_18], rbx
0x180012c59  push    rbp
0x180012c5a  push    rsi
0x180012c5b  push    rdi
0x180012c5c  push    r12
0x180012c5e  push    r13
0x180012c60  push    r14
0x180012c62  push    r15
0x180012c64  lea     rbp, [rsp-170h]
0x180012c6c  sub     rsp, 270h
0x180012c73  mov     rax, cs:__security_cookie
0x180012c7a  xor     rax, rsp
0x180012c7d  mov     [rbp+1A0h+var_40], rax
0x180012c84  mov     rsi, r8
0x180012c87  mov     r14, rdx
0x180012c8a  movzx   edx, word ptr [rcx]
0x180012c8d  sub     edx, 11h
0x180012c90  jz      short loc_180012CB1
0x180012c92  sub     edx, 1
0x180012c95  jz      short loc_180012CAB
0x180012c97  cmp     edx, 1
0x180012c9a  jz      short loc_180012CA6
0x180012c9c  mov     ebx, 88982F91h
0x180012ca1  jmp     loc_180012FFC
0x180012ca6  mov     edi, [rcx+8]
0x180012ca9  jmp     short loc_180012CB5
0x180012cab  movzx   edi, word ptr [rcx+8]
0x180012caf  jmp     short loc_180012CB5
0x180012cb1  movzx   edi, byte ptr [rcx+8]
0x180012cb5  xor     edx, edx; Val
0x180012cb7  mov     r8d, 208h; Size
0x180012cbd  lea     rcx, [rsp+2A0h+var_250]; void *
0x180012cc2  call    memset_0
0x180012cc7  mov     r9, r14
0x180012cca  lea     r8, aSExifFired; "%s/exif:Fired"
0x180012cd1  mov     r15d, 104h
0x180012cd7  mov     edx, r15d; unsigned __int64
0x180012cda  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180012cdf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012ce4  mov     ebx, eax
0x180012ce6  test    eax, eax
0x180012ce8  js      loc_180012FFC
0x180012cee  xorps   xmm0, xmm0
0x180012cf1  xor     ecx, ecx
0x180012cf3  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x180012cf8  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x180012cfd  lea     r13d, [rcx+0Bh]
0x180012d01  mov     word ptr [rsp+2A0h+var_280], r13w
0x180012d07  or      r12d, 0FFFFFFFFh
0x180012d0b  test    dil, 1
0x180012d0f  jz      short loc_180012D19
0x180012d11  mov     word ptr [rsp+2A0h+var_280+8], r12w
0x180012d17  jmp     short loc_180012D20
0x180012d19  xor     eax, eax
0x180012d1b  mov     word ptr [rsp+2A0h+var_280+8], ax
0x180012d20  xor     eax, eax
0x180012d22  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x180012d27  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180012d2c  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180012d31  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x180012d36  call    ?ConvertPropvarToBooleanString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToBooleanString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012d3b  mov     ebx, eax
0x180012d3d  test    eax, eax
0x180012d3f  js      short loc_180012D5C
0x180012d41  mov     rax, [rsi]
0x180012d44  lea     r8, [rsp+2A0h+pvar]
0x180012d49  lea     rdx, [rsp+2A0h+var_250]
0x180012d4e  mov     rcx, rsi
0x180012d51  mov     rax, [rax+38h]
0x180012d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d5a  mov     ebx, eax
0x180012d5c  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180012d61  call    cs:__imp_PropVariantClear
0x180012d67  nop
0x180012d68  lea     rcx, [rsp+2A0h+var_280]; pvar
0x180012d6d  call    cs:__imp_PropVariantClear
0x180012d73  test    ebx, ebx
0x180012d75  js      loc_180012FFC
0x180012d7b  mov     r9, r14
0x180012d7e  lea     r8, aSExifReturn; "%s/exif:Return"
0x180012d85  mov     rdx, r15; unsigned __int64
0x180012d88  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180012d8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012d92  mov     ebx, eax
0x180012d94  test    eax, eax
0x180012d96  js      loc_180012FFC
0x180012d9c  mov     eax, edi
0x180012d9e  shr     eax, 1
0x180012da0  and     eax, 3
0x180012da3  xorps   xmm0, xmm0
0x180012da6  xor     ecx, ecx
0x180012da8  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x180012dad  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x180012db2  mov     ecx, 11h
0x180012db7  mov     word ptr [rsp+2A0h+var_280], cx
0x180012dbc  mov     byte ptr [rsp+2A0h+var_280+8], al
0x180012dc0  xor     eax, eax
0x180012dc2  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x180012dc7  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180012dcc  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180012dd1  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x180012dd6  call    ?ConvertPropvarToNumericalString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToNumericalString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012ddb  mov     ebx, eax
0x180012ddd  test    eax, eax
0x180012ddf  js      short loc_180012DFC
0x180012de1  mov     rax, [rsi]
0x180012de4  lea     r8, [rsp+2A0h+pvar]
0x180012de9  lea     rdx, [rsp+2A0h+var_250]
0x180012dee  mov     rcx, rsi
0x180012df1  mov     rax, [rax+38h]
0x180012df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dfa  mov     ebx, eax
0x180012dfc  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180012e01  call    cs:__imp_PropVariantClear
0x180012e07  nop
0x180012e08  lea     rcx, [rsp+2A0h+var_280]; pvar
0x180012e0d  call    cs:__imp_PropVariantClear
0x180012e13  test    ebx, ebx
0x180012e15  js      loc_180012FFC
0x180012e1b  mov     r9, r14
0x180012e1e  lea     r8, aSExifMode; "%s/exif:Mode"
0x180012e25  mov     rdx, r15; unsigned __int64
0x180012e28  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180012e2d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012e32  mov     ebx, eax
0x180012e34  test    eax, eax
0x180012e36  js      loc_180012FFC
0x180012e3c  mov     eax, edi
0x180012e3e  shr     eax, 3
0x180012e41  and     eax, 3
0x180012e44  xorps   xmm0, xmm0
0x180012e47  xor     ecx, ecx
0x180012e49  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x180012e4e  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x180012e53  mov     ecx, 11h
0x180012e58  mov     word ptr [rsp+2A0h+var_280], cx
0x180012e5d  mov     byte ptr [rsp+2A0h+var_280+8], al
0x180012e61  xor     eax, eax
0x180012e63  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x180012e68  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180012e6d  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180012e72  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x180012e77  call    ?ConvertPropvarToNumericalString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToNumericalString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012e7c  mov     ebx, eax
0x180012e7e  test    eax, eax
0x180012e80  js      short loc_180012E9D
0x180012e82  mov     rax, [rsi]
0x180012e85  lea     r8, [rsp+2A0h+pvar]
0x180012e8a  lea     rdx, [rsp+2A0h+var_250]
0x180012e8f  mov     rcx, rsi
0x180012e92  mov     rax, [rax+38h]
0x180012e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e9b  mov     ebx, eax
0x180012e9d  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180012ea2  call    cs:__imp_PropVariantClear
0x180012ea8  nop
0x180012ea9  lea     rcx, [rsp+2A0h+var_280]; pvar
0x180012eae  call    cs:__imp_PropVariantClear
0x180012eb4  test    ebx, ebx
0x180012eb6  js      loc_180012FFC
0x180012ebc  mov     r9, r14
0x180012ebf  lea     r8, aSExifFunction; "%s/exif:Function"
0x180012ec6  mov     rdx, r15; unsigned __int64
0x180012ec9  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180012ece  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012ed3  mov     ebx, eax
0x180012ed5  test    eax, eax
0x180012ed7  js      loc_180012FFC
0x180012edd  xorps   xmm0, xmm0
0x180012ee0  xor     ecx, ecx
0x180012ee2  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x180012ee7  mov     qword ptr [rsp+2A0h+var_280+10h], rcx
0x180012eec  mov     word ptr [rsp+2A0h+var_280], r13w
0x180012ef2  bt      edi, 5
0x180012ef6  jnb     short loc_180012F00
0x180012ef8  mov     word ptr [rsp+2A0h+var_280+8], r12w
0x180012efe  jmp     short loc_180012F07
0x180012f00  xor     eax, eax
0x180012f02  mov     word ptr [rsp+2A0h+var_280+8], ax
0x180012f07  xor     eax, eax
0x180012f09  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x180012f0e  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180012f13  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180012f18  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x180012f1d  call    ?ConvertPropvarToBooleanString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToBooleanString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012f22  mov     ebx, eax
0x180012f24  test    eax, eax
0x180012f26  js      short loc_180012F43
0x180012f28  mov     rax, [rsi]
0x180012f2b  lea     r8, [rsp+2A0h+pvar]
0x180012f30  lea     rdx, [rsp+2A0h+var_250]
0x180012f35  mov     rcx, rsi
0x180012f38  mov     rax, [rax+38h]
0x180012f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f41  mov     ebx, eax
0x180012f43  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180012f48  call    cs:__imp_PropVariantClear
0x180012f4e  nop
0x180012f4f  lea     rcx, [rsp+2A0h+var_280]; pvar
0x180012f54  call    cs:__imp_PropVariantClear
0x180012f5a  test    ebx, ebx
0x180012f5c  js      loc_180012FFC
0x180012f62  mov     r9, r14
0x180012f65  lea     r8, aSExifRedeyemod; "%s/exif:RedEyeMode"
0x180012f6c  mov     rdx, r15; unsigned __int64
0x180012f6f  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180012f74  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012f79  mov     ebx, eax
0x180012f7b  test    eax, eax
0x180012f7d  js      short loc_180012FFC
0x180012f7f  xorps   xmm0, xmm0
0x180012f82  xor     eax, eax
0x180012f84  movups  xmmword ptr [rsp+2A0h+var_280], xmm0
0x180012f89  mov     qword ptr [rsp+2A0h+var_280+10h], rax
0x180012f8e  mov     word ptr [rsp+2A0h+var_280], r13w
0x180012f94  bt      edi, 6
0x180012f98  jnb     short loc_180012FA2
0x180012f9a  mov     word ptr [rsp+2A0h+var_280+8], r12w
0x180012fa0  jmp     short loc_180012FA9
0x180012fa2  xor     eax, eax
0x180012fa4  mov     word ptr [rsp+2A0h+var_280+8], ax
0x180012fa9  xor     eax, eax
0x180012fab  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x180012fb0  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x180012fb5  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x180012fba  lea     rcx, [rsp+2A0h+var_280]; struct tagPROPVARIANT *
0x180012fbf  call    ?ConvertPropvarToBooleanString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertPropvarToBooleanString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012fc4  mov     ebx, eax
0x180012fc6  test    eax, eax
0x180012fc8  js      short loc_180012FE5
0x180012fca  mov     rax, [rsi]
0x180012fcd  lea     r8, [rsp+2A0h+pvar]
0x180012fd2  lea     rdx, [rsp+2A0h+var_250]
0x180012fd7  mov     rcx, rsi
0x180012fda  mov     rax, [rax+38h]
0x180012fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fe3  mov     ebx, eax
0x180012fe5  lea     rcx, [rsp+2A0h+pvar]; pvar
0x180012fea  call    cs:__imp_PropVariantClear
0x180012ff0  nop
0x180012ff1  lea     rcx, [rsp+2A0h+var_280]; pvar
0x180012ff6  call    cs:__imp_PropVariantClear
0x180012ffc  mov     eax, ebx
0x180012ffe  mov     rcx, [rbp+1A0h+var_40]
0x180013005  xor     rcx, rsp; StackCookie
0x180013008  call    __security_check_cookie
0x18001300d  mov     rbx, [rsp+2A0h+arg_18]
0x180013015  add     rsp, 270h
0x18001301c  pop     r15
0x18001301e  pop     r14
0x180013020  pop     r13
0x180013022  pop     r12
0x180013024  pop     rdi
0x180013025  pop     rsi
0x180013026  pop     rbp
0x180013027  retn
```
