# WICRawUtilities::GetMetadataDoubleMatrixProperty(IWICMetadataQueryReader *,int,wchar_t const *,int,int,ATL::CComVariant *)

- ea: `0x180508108`
- end: `0x180508431`
- name: `?GetMetadataDoubleMatrixProperty@WICRawUtilities@@YA_NPEAUIWICMetadataQueryReader@@HPEB_WHHPEAVCComVariant@ATL@@@Z`
- size: `809`
- prototype: `bool __usercall@<al>(WICRawUtilities *__hidden this@<rcx>, struct IWICMetadataQueryReader *@<rdx>, int@<r8d>, const wchar_t *@<r9>, int, int, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18050952c`

## callees

- `0x1801e8c64`
- `0x1804c6944`
- `0x1804fbdb0`
- `0x180508108`
- `0x18056bd00`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1805081d9`
- `OLEAUT32!__imp_VariantInit` at `0x1805081d9`
- `OLEAUT32!__imp_VariantClear` at `0x180508287`
- `OLEAUT32!__imp_VariantClear` at `0x180508354`
- `OLEAUT32!__imp_VariantClear` at `0x1805083a3`
- `OLEAUT32!__imp_VariantClear` at `0x180508287`
- `OLEAUT32!__imp_VariantClear` at `0x180508354`
- `OLEAUT32!__imp_VariantClear` at `0x1805083a3`
- `OLEAUT32!__imp_VariantCopy` at `0x180508341`
- `OLEAUT32!__imp_VariantCopy` at `0x180508341`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180508170`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180508170`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18050836a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1805083be`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18050836a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1805083be`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180508252`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180508252`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180508225`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180508225`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18050818d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18050818d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18050835d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1805083b1`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18050835d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1805083b1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1805082a9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1805082a9`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1805082c2`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1805082c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall WICRawUtilities::GetMetadataDoubleMatrixProperty(
        WICRawUtilities *this,
        struct IWICMetadataQueryReader *a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        VARIANTARG *pvargDest)
{
  unsigned int v6; // r15d
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rbx
  HRESULT v10; // eax
  LONG v11; // edi
  int v12; // eax
  const wchar_t *v13; // r9
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT v16; // eax
  HRESULT Vartype; // ecx
  VARTYPE v18; // dx
  HRESULT v19; // eax
  __int16 v21[4]; // [rsp+28h] [rbp-E0h]
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-D0h] BYREF
  LONG plLbound; // [rsp+40h] [rbp-C8h] BYREF
  VARTYPE pvt[4]; // [rsp+48h] [rbp-C0h] BYREF
  SAFEARRAYBOUND v25; // [rsp+50h] [rbp-B8h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-98h]
  SAFEARRAY *v28; // [rsp+78h] [rbp-90h]
  wchar_t Buffer[1000]; // [rsp+88h] [rbp-80h] BYREF

  v6 = (unsigned int)a2;
  if ( !this || !pvargDest )
    ATL::BaseAtlThrow(-2147467261);
  rgsabound = (SAFEARRAYBOUND)3LL;
  v8 = SafeArrayCreate(5u, 1u, &rgsabound);
  v9 = v8;
  v28 = v8;
  if ( v8 )
    v10 = SafeArrayLock(v8);
  else
    v10 = -2147024882;
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  v11 = 0;
  while ( 1 )
  {
    *(_DWORD *)v21 = v11;
    v12 = StringCchPrintfW(Buffer, 0x3E8u, L"%s%d", L"WhiteBalance", *(_QWORD *)v21);
    if ( v12 < 0 )
      ATL::BaseAtlThrow(v12);
    *(_OWORD *)&pvarg.decVal.Lo32 = 0;
    v27 = 0;
    VariantInit((VARIANTARG *)&pvarg.decVal.8);
    if ( !WICRawUtilities::GetMetadataProperty(
            this,
            (struct IWICMetadataQueryReader *)v6,
            (int)Buffer,
            v13,
            5,
            (VARIANTARG *)&pvarg.decVal.8,
            *(struct ATL::CComVariant **)&rgsabound) )
      break;
    if ( !v9 )
      ATL::BaseAtlThrow(-2147467259);
    plLbound = 0;
    LBound = SafeArrayGetLBound(v9, 1u, &plLbound);
    if ( LBound < 0 )
      ATL::BaseAtlThrow(LBound);
    if ( v11 < plLbound )
      goto LABEL_44;
    rgsabound.cElements = 0;
    UBound = SafeArrayGetUBound(v9, 1u, (LONG *)&rgsabound);
    if ( UBound < 0 )
      ATL::BaseAtlThrow(UBound);
    if ( v11 > (int)rgsabound.cElements )
LABEL_44:
      ATL::BaseAtlThrow(-2147024809);
    *((_QWORD *)v9->pvData + v11 - plLbound) = pvarg.pRecInfo;
    VariantClear((VARIANTARG *)&pvarg.decVal.8);
    if ( ++v11 >= 3 )
    {
      rgsabound = 0;
      v16 = SafeArrayCopy(v9, (SAFEARRAY **)&rgsabound);
      Vartype = v16;
      if ( v16 < 0 )
      {
        v25.cElements = v16;
      }
      else
      {
        Vartype = SafeArrayGetVartype(v9, pvt);
        v18 = pvt[0];
        if ( Vartype >= 0 && pvt[0] == 13 && (v9->fFeatures & 0x440) == 0x440 )
          v18 = 9;
        if ( Vartype >= 0 )
        {
          pvt[0] = v18 | 0x2000;
          v25 = rgsabound;
LABEL_26:
          if ( Vartype < 0 )
          {
            if ( Vartype != -2147024882 )
              ATL::BaseAtlThrow(Vartype);
            ATL::BaseAtlThrow(-2147024882);
          }
          if ( pvargDest != (VARIANTARG *)pvt )
          {
            v19 = VariantCopy(pvargDest, (const VARIANTARG *)pvt);
            if ( v19 < 0 )
            {
              pvargDest->vt = 10;
              pvargDest->lVal = v19;
              ATL::BaseAtlThrow(v19);
            }
          }
          VariantClear((VARIANTARG *)pvt);
          if ( SafeArrayUnlock(v9) >= 0 )
            SafeArrayDestroy(v9);
          return 1;
        }
        v25.cElements = Vartype;
      }
      pvt[0] = 10;
      goto LABEL_26;
    }
  }
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v9 && SafeArrayUnlock(v9) >= 0 )
    SafeArrayDestroy(v9);
  return 0;
}

```

## disassembly

```asm
0x180508108  mov     rax, rsp
0x18050810b  mov     [rax+10h], rbx
0x18050810f  mov     [rax+18h], rsi
0x180508113  mov     [rax+20h], rdi
0x180508117  push    rbp
0x180508118  push    r14
0x18050811a  push    r15
0x18050811c  lea     rbp, [rax-778h]
0x180508123  sub     rsp, 860h
0x18050812a  mov     rax, cs:__security_cookie
0x180508131  xor     rax, rsp
0x180508134  mov     [rbp+770h+var_20], rax
0x18050813b  mov     r15d, edx
0x18050813e  mov     r14, rcx
0x180508141  mov     rsi, [rbp+770h+pvargDest]
0x180508148  test    rcx, rcx
0x18050814b  jz      loc_1805083DB
0x180508151  test    rsi, rsi
0x180508154  jz      loc_1805083DB
0x18050815a  mov     qword ptr [rsp+870h+rgsabound.cElements], 3; struct ATL::CComVariant *
0x180508163  mov     ecx, 5; vt
0x180508168  lea     r8, [rsp+870h+rgsabound]; rgsabound
0x18050816d  lea     edx, [rcx-4]; cDims
0x180508170  call    cs:__imp_SafeArrayCreate
0x180508176  mov     rbx, rax
0x180508179  mov     [rsp+870h+var_800], rax
0x18050817e  test    rax, rax
0x180508181  jnz     short loc_18050818A
0x180508183  mov     eax, 8007000Eh
0x180508188  jmp     short loc_180508193
0x18050818a  mov     rcx, rbx; psa
0x18050818d  call    cs:__imp_SafeArrayLock
0x180508193  test    eax, eax
0x180508195  js      loc_1805083E6
0x18050819b  xor     edi, edi
0x18050819d  mov     dword ptr [rsp+870h+var_850], edi
0x1805081a1  lea     r9, aWhitebalance_0; "WhiteBalance"
0x1805081a8  lea     r8, aSD; "%s%d"
0x1805081af  mov     edx, 3E8h; unsigned __int64
0x1805081b4  lea     rcx, [rbp+770h+Buffer]; Buffer
0x1805081b8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1805081bd  test    eax, eax
0x1805081bf  js      loc_1805083C8
0x1805081c5  xorps   xmm0, xmm0
0x1805081c8  xor     eax, eax
0x1805081ca  movups  xmmword ptr [rsp+870h+pvarg+8], xmm0
0x1805081cf  mov     [rsp+870h+var_808], rax
0x1805081d4  lea     rcx, [rsp+870h+pvarg+8]; pvarg
0x1805081d9  call    cs:__imp_VariantInit
0x1805081df  lea     rax, [rsp+870h+pvarg+8]
0x1805081e4  mov     [rsp+870h+var_848], rax; pvargDest
0x1805081e9  mov     [rsp+870h+var_850], 5; __int16
0x1805081f0  lea     r8, [rbp+770h+Buffer]; int
0x1805081f4  mov     edx, r15d; struct IWICMetadataQueryReader *
0x1805081f7  mov     rcx, r14; this
0x1805081fa  call    ?GetMetadataProperty@WICRawUtilities@@YA_NPEAUIWICMetadataQueryReader@@HPEB_WHGPEAVCComVariant@ATL@@@Z; WICRawUtilities::GetMetadataProperty(IWICMetadataQueryReader *,int,wchar_t const *,int,ushort,ATL::CComVariant *)
0x1805081ff  test    al, al
0x180508201  jz      loc_18050839E
0x180508207  test    rbx, rbx
0x18050820a  jz      loc_180508426
0x180508210  mov     [rsp+870h+plLbound], 0
0x180508218  lea     r8, [rsp+870h+plLbound]; plLbound
0x18050821d  mov     edx, 1; nDim
0x180508222  mov     rcx, rbx; psa
0x180508225  call    cs:__imp_SafeArrayGetLBound
0x18050822b  test    eax, eax
0x18050822d  js      loc_18050841E
0x180508233  cmp     edi, [rsp+870h+plLbound]
0x180508237  jl      loc_180508413
0x18050823d  mov     [rsp+870h+rgsabound.cElements], 0
0x180508245  lea     r8, [rsp+870h+rgsabound]; plUbound
0x18050824a  mov     edx, 1; nDim
0x18050824f  mov     rcx, rbx; psa
0x180508252  call    cs:__imp_SafeArrayGetUBound
0x180508258  test    eax, eax
0x18050825a  js      loc_18050840B
0x180508260  cmp     edi, [rsp+870h+rgsabound.cElements]
0x180508264  jg      loc_180508413
0x18050826a  mov     eax, edi
0x18050826c  sub     eax, [rsp+870h+plLbound]
0x180508270  movsxd  rcx, eax
0x180508273  mov     rax, [rbx+10h]
0x180508277  movsd   xmm0, qword ptr [rsp+870h+pvarg+10h]
0x18050827d  movsd   qword ptr [rax+rcx*8], xmm0
0x180508282  lea     rcx, [rsp+870h+pvarg+8]; pvarg
0x180508287  call    cs:__imp_VariantClear
0x18050828d  inc     edi
0x18050828f  cmp     edi, 3
0x180508292  jl      loc_18050819D
0x180508298  mov     qword ptr [rsp+870h+rgsabound.cElements], 0
0x1805082a1  lea     rdx, [rsp+870h+rgsabound]; ppsaOut
0x1805082a6  mov     rcx, rbx; psa
0x1805082a9  call    cs:__imp_SafeArrayCopy
0x1805082af  mov     ecx, eax
0x1805082b1  mov     edi, 0Ah
0x1805082b6  test    eax, eax
0x1805082b8  js      short loc_180508310
0x1805082ba  lea     rdx, [rsp+870h+pvt]; pvt
0x1805082bf  mov     rcx, rbx; psa
0x1805082c2  call    cs:__imp_SafeArrayGetVartype
0x1805082c8  mov     ecx, eax
0x1805082ca  movzx   edx, [rsp+870h+pvt]
0x1805082cf  test    eax, eax
0x1805082d1  js      short loc_1805082F0
0x1805082d3  cmp     dx, 0Dh
0x1805082d7  jnz     short loc_1805082F0
0x1805082d9  movzx   eax, word ptr [rbx+2]
0x1805082dd  mov     r8d, 440h
0x1805082e3  and     ax, r8w
0x1805082e7  cmp     ax, r8w
0x1805082eb  jnz     short loc_1805082F0
0x1805082ed  lea     edx, [rdi-1]
0x1805082f0  test    ecx, ecx
0x1805082f2  js      short loc_18050830A
0x1805082f4  or      dx, 2000h
0x1805082f9  mov     [rsp+870h+pvt], dx
0x1805082fe  mov     rax, qword ptr [rsp+870h+rgsabound.cElements]
0x180508303  mov     [rsp+870h+var_828], rax
0x180508308  jmp     short loc_180508319
0x18050830a  mov     dword ptr [rsp+870h+var_828], ecx
0x18050830e  jmp     short loc_180508314
0x180508310  mov     dword ptr [rsp+870h+var_828], eax
0x180508314  mov     [rsp+870h+pvt], di
0x180508319  test    ecx, ecx
0x18050831b  jns     short loc_18050832F
0x18050831d  mov     eax, 8007000Eh
0x180508322  cmp     ecx, eax
0x180508324  jz      loc_1805083D0
0x18050832a  jmp     loc_1805083F1
0x18050832f  lea     rax, [rsp+870h+pvt]
0x180508334  cmp     rsi, rax
0x180508337  jz      short loc_18050834F
0x180508339  lea     rdx, [rsp+870h+pvt]; pvargSrc
0x18050833e  mov     rcx, rsi; pvargDest
0x180508341  call    cs:__imp_VariantCopy
0x180508347  test    eax, eax
0x180508349  js      loc_1805083FA
0x18050834f  lea     rcx, [rsp+870h+pvt]; pvarg
0x180508354  call    cs:__imp_VariantClear
0x18050835a  mov     rcx, rbx; psa
0x18050835d  call    cs:__imp_SafeArrayUnlock
0x180508363  test    eax, eax
0x180508365  js      short loc_180508370
0x180508367  mov     rcx, rbx; psa
0x18050836a  call    cs:__imp_SafeArrayDestroy
0x180508370  mov     al, 1
0x180508372  mov     rcx, [rbp+770h+var_20]
0x180508379  xor     rcx, rsp; StackCookie
0x18050837c  call    __security_check_cookie
0x180508381  lea     r11, [rsp+870h+var_10]
0x180508389  mov     rbx, [r11+28h]
0x18050838d  mov     rsi, [r11+30h]
0x180508391  mov     rdi, [r11+38h]
0x180508395  mov     rsp, r11
0x180508398  pop     r15
0x18050839a  pop     r14
0x18050839c  pop     rbp
0x18050839d  retn
0x18050839e  lea     rcx, [rsp+870h+pvarg+8]; pvarg
0x1805083a3  call    cs:__imp_VariantClear
0x1805083a9  test    rbx, rbx
0x1805083ac  jz      short loc_1805083C4
0x1805083ae  mov     rcx, rbx; psa
0x1805083b1  call    cs:__imp_SafeArrayUnlock
0x1805083b7  test    eax, eax
0x1805083b9  js      short loc_1805083C4
0x1805083bb  mov     rcx, rbx; psa
0x1805083be  call    cs:__imp_SafeArrayDestroy
0x1805083c4  xor     al, al
0x1805083c6  jmp     short loc_180508372
0x1805083c8  mov     ecx, eax; int
0x1805083ca  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1805083d0  mov     ecx, eax; int
0x1805083d2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1805083d8  jmp     short $+2
0x1805083da  nop
0x1805083db  mov     ecx, 80004003h; int
0x1805083e0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1805083e6  mov     ecx, eax; int
0x1805083e8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1805083ee  jmp     short $+2
0x1805083f0  nop
0x1805083f1  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1805083f7  jmp     short $+2
0x1805083f9  nop
0x1805083fa  mov     [rsi], di
0x1805083fd  mov     [rsi+8], eax
0x180508400  mov     ecx, eax; int
0x180508402  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508408  jmp     short $+2
0x18050840a  nop
0x18050840b  mov     ecx, eax; int
0x18050840d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508413  mov     ecx, 80070057h; int
0x180508418  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18050841e  mov     ecx, eax; int
0x180508420  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508426  mov     ecx, 80004005h; int
0x18050842b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
