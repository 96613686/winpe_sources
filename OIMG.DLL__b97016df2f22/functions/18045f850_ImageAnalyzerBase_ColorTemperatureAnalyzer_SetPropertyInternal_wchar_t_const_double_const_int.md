# ImageAnalyzerBase<ColorTemperatureAnalyzer>::SetPropertyInternal(wchar_t const *,double const *,int)

- ea: `0x18045f850`
- end: `0x18045fb21`
- name: `?SetPropertyInternal@?$ImageAnalyzerBase@VColorTemperatureAnalyzer@@@@IEAAXPEB_WPEBNH@Z`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18045ee30`

## callees

- `0x1801acb2c`
- `0x1801b1354`
- `0x18045f850`
- `0x1804c6944`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18045fa96`
- `OLEAUT32!__imp_VariantClear` at `0x18045fa96`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18045f8a0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18045f8a0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18045faac`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18045faac`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18045fa1a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18045fa1a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18045f8e9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18045f9f5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18045f8e9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18045f9f5`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18045f8bc`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18045f9c7`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18045f8bc`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18045f9c7`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18045f9a9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18045fa9f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18045f9a9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18045fa9f`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18045f942`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18045f942`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18045f9bc`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18045f9bc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18045f959`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18045f959`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall ImageAnalyzerBase<ColorTemperatureAnalyzer>::SetPropertyInternal(
        __int64 a1,
        SAFEARRAYBOUND a2,
        __int64 a3,
        LONG a4)
{
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rbx
  HRESULT v7; // edi
  int Count; // r13d
  HRESULT LBound; // eax
  ULONG cElements; // r14d
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  HRESULT v13; // eax
  __int64 v14; // r15
  LONG v15; // r14d
  HRESULT v16; // eax
  HRESULT UBound; // eax
  int result; // eax
  SAFEARRAYBOUND psaboundNew; // [rsp+20h] [rbp-20h] BYREF
  VARIANTARG pvt; // [rsp+28h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+88h] [rbp+48h] BYREF
  SAFEARRAY *v23; // [rsp+90h] [rbp+50h] BYREF
  LONG plLbound; // [rsp+98h] [rbp+58h] BYREF

  plLbound = a4;
  rgsabound = a2;
  v23 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    goto LABEL_40;
  }
  rgsabound = 0;
  v5 = SafeArrayCreate(5u, 1u, &rgsabound);
  v6 = v5;
  v23 = v5;
  if ( v5 )
    v7 = SafeArrayLock(v5);
  else
    v7 = -2147024882;
  if ( v7 < 0 )
    goto LABEL_40;
  Count = ATL::CComSafeArray<IUnknown *,13>::GetCount(&v23);
  rgsabound.cElements = 0;
  LBound = SafeArrayGetLBound(v6, 1u, (LONG *)&rgsabound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  psaboundNew.cElements = Count + 4;
  cElements = rgsabound.cElements;
  psaboundNew.lLbound = rgsabound.cElements;
  if ( !v6 )
    ATL::BaseAtlThrow(-2147467259);
  if ( (v6->fFeatures & 0x10) != 0 )
  {
    v7 = -2147467259;
  }
  else
  {
    v7 = SafeArrayUnlock(v6);
    if ( v7 >= 0 )
    {
      v7 = SafeArrayRedim(v6, &psaboundNew);
      v13 = SafeArrayLock(v6);
      if ( v7 >= 0 )
        v7 = v13;
    }
    if ( v7 >= 0 )
    {
      v14 = 0;
      v15 = Count + cElements;
      do
      {
        plLbound = 0;
        v16 = SafeArrayGetLBound(v6, 1u, &plLbound);
        if ( v16 < 0 )
          ATL::BaseAtlThrow(v16);
        if ( v15 < plLbound )
          goto LABEL_28;
        rgsabound.cElements = 0;
        UBound = SafeArrayGetUBound(v6, 1u, (LONG *)&rgsabound);
        if ( UBound < 0 )
          ATL::BaseAtlThrow(UBound);
        if ( v15 > (int)rgsabound.cElements )
        {
LABEL_28:
          v7 = -2147024809;
        }
        else
        {
          *((_QWORD *)v6->pvData + v15 - plLbound) = *(_QWORD *)(a3 + 8 * v14);
          v7 = 0;
        }
        if ( v7 < 0 )
          break;
        v14 = (unsigned int)(v14 + 1);
        ++v15;
      }
      while ( (unsigned int)v14 < 4 );
    }
  }
  if ( v7 < 0 )
LABEL_40:
    ATL::BaseAtlThrow(v7);
  rgsabound = 0;
  Vartype = SafeArrayCopy(v6, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_32;
  Vartype = SafeArrayGetVartype(v6, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v6->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_32:
    pvt.lVal = Vartype;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = vt | 0x2000;
    pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
  }
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  ImageAnalyzerBase<ColorTemperatureAnalyzer>::SetPropertyInternal(a1, L"_AutoNeutralPoint", &pvt);
  VariantClear(&pvt);
  result = SafeArrayUnlock(v6);
  if ( result >= 0 )
    return SafeArrayDestroy(v6);
  return result;
}

```

## disassembly

```asm
0x18045f850  mov     [rsp-38h+plLbound], r9d
0x18045f855  mov     qword ptr [rsp-38h+rgsabound.cElements], rdx
0x18045f85a  mov     [rsp-38h+arg_0], rcx
0x18045f85f  push    rbp
0x18045f860  push    rbx
0x18045f861  push    rdi
0x18045f862  push    r12
0x18045f864  push    r13
0x18045f866  push    r14
0x18045f868  push    r15
0x18045f86a  mov     rbp, rsp
0x18045f86d  sub     rsp, 40h
0x18045f871  mov     r12, r8
0x18045f874  mov     r14, rcx
0x18045f877  mov     [rbp+arg_10], 0
0x18045f87f  test    r8, r8
0x18045f882  jz      loc_18045FACB
0x18045f888  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18045f890  mov     ecx, 5; vt
0x18045f895  lea     r8, [rbp+rgsabound]; rgsabound
0x18045f899  lea     r15d, [rcx-4]
0x18045f89d  mov     edx, r15d; cDims
0x18045f8a0  call    cs:__imp_SafeArrayCreate
0x18045f8a6  mov     rbx, rax
0x18045f8a9  mov     [rbp+arg_10], rax
0x18045f8ad  test    rax, rax
0x18045f8b0  jnz     short loc_18045F8B9
0x18045f8b2  mov     edi, 8007000Eh
0x18045f8b7  jmp     short loc_18045F8C4
0x18045f8b9  mov     rcx, rbx; psa
0x18045f8bc  call    cs:__imp_SafeArrayLock
0x18045f8c2  mov     edi, eax
0x18045f8c4  test    edi, edi
0x18045f8c6  js      loc_18045FAD0
0x18045f8cc  lea     rcx, [rbp+arg_10]
0x18045f8d0  call    ?GetCount@?$CComSafeArray@PEAUIUnknown@@$0N@@ATL@@QEBAKI@Z; ATL::CComSafeArray<IUnknown *,13>::GetCount(uint)
0x18045f8d5  mov     r13d, eax
0x18045f8d8  mov     [rbp+rgsabound.cElements], 0
0x18045f8df  lea     r8, [rbp+rgsabound]; plLbound
0x18045f8e3  mov     edx, r15d; nDim
0x18045f8e6  mov     rcx, rbx; psa
0x18045f8e9  call    cs:__imp_SafeArrayGetLBound
0x18045f8ef  test    eax, eax
0x18045f8f1  js      loc_18045FAE3
0x18045f8f7  lea     eax, [r13+4]
0x18045f8fb  mov     [rbp+psaboundNew.cElements], eax
0x18045f8fe  mov     r14d, [rbp+rgsabound.cElements]
0x18045f902  mov     [rbp+psaboundNew.lLbound], r14d
0x18045f906  test    rbx, rbx
0x18045f909  jz      loc_18045FAEB
0x18045f90f  test    byte ptr [rbx+2], 10h
0x18045f913  jz      loc_18045F9A6
0x18045f919  mov     edi, 80004005h
0x18045f91e  mov     r14, [rbp+arg_0]
0x18045f922  test    edi, edi
0x18045f924  js      loc_18045FAD0
0x18045f92a  test    rbx, rbx
0x18045f92d  jz      loc_18045FB06
0x18045f933  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18045f93b  lea     rdx, [rbp+rgsabound]; ppsaOut
0x18045f93f  mov     rcx, rbx; psa
0x18045f942  call    cs:__imp_SafeArrayCopy
0x18045f948  mov     ecx, eax; int
0x18045f94a  test    eax, eax
0x18045f94c  js      loc_18045FA65
0x18045f952  lea     rdx, [rbp+pvt]; pvt
0x18045f956  mov     rcx, rbx; psa
0x18045f959  call    cs:__imp_SafeArrayGetVartype
0x18045f95f  mov     ecx, eax
0x18045f961  movzx   edx, [rbp+pvt]
0x18045f965  test    eax, eax
0x18045f967  js      short loc_18045F988
0x18045f969  cmp     dx, 0Dh
0x18045f96d  jnz     short loc_18045F988
0x18045f96f  movzx   eax, word ptr [rbx+2]
0x18045f973  mov     r8d, 440h
0x18045f979  and     ax, r8w
0x18045f97d  cmp     ax, r8w
0x18045f981  jnz     short loc_18045F988
0x18045f983  mov     edx, 9
0x18045f988  test    ecx, ecx
0x18045f98a  js      loc_18045FA65
0x18045f990  or      dx, 2000h
0x18045f995  mov     [rbp+pvt], dx
0x18045f999  mov     rax, qword ptr [rbp+rgsabound.cElements]
0x18045f99d  mov     [rbp+var_10], rax
0x18045f9a1  jmp     loc_18045FA71
0x18045f9a6  mov     rcx, rbx; psa
0x18045f9a9  call    cs:__imp_SafeArrayUnlock
0x18045f9af  mov     edi, eax
0x18045f9b1  test    eax, eax
0x18045f9b3  js      short loc_18045F9D2
0x18045f9b5  lea     rdx, [rbp+psaboundNew]; psaboundNew
0x18045f9b9  mov     rcx, rbx; psa
0x18045f9bc  call    cs:__imp_SafeArrayRedim
0x18045f9c2  mov     edi, eax
0x18045f9c4  mov     rcx, rbx; psa
0x18045f9c7  call    cs:__imp_SafeArrayLock
0x18045f9cd  test    edi, edi
0x18045f9cf  cmovns  edi, eax
0x18045f9d2  test    edi, edi
0x18045f9d4  js      loc_18045F91E
0x18045f9da  xor     r15d, r15d
0x18045f9dd  add     r14d, r13d
0x18045f9e0  lea     r13d, [r15+1]
0x18045f9e4  mov     [rbp+plLbound], 0
0x18045f9eb  lea     r8, [rbp+plLbound]; plLbound
0x18045f9ef  mov     edx, r13d; nDim
0x18045f9f2  mov     rcx, rbx; psa
0x18045f9f5  call    cs:__imp_SafeArrayGetLBound
0x18045f9fb  test    eax, eax
0x18045f9fd  js      loc_18045FAFE
0x18045fa03  cmp     r14d, [rbp+plLbound]
0x18045fa07  jl      short loc_18045FA47
0x18045fa09  mov     [rbp+rgsabound.cElements], 0
0x18045fa10  lea     r8, [rbp+rgsabound]; plUbound
0x18045fa14  mov     edx, r13d; nDim
0x18045fa17  mov     rcx, rbx; psa
0x18045fa1a  call    cs:__imp_SafeArrayGetUBound
0x18045fa20  test    eax, eax
0x18045fa22  js      loc_18045FAF6
0x18045fa28  cmp     r14d, [rbp+rgsabound.cElements]
0x18045fa2c  jg      short loc_18045FA47
0x18045fa2e  mov     eax, r14d
0x18045fa31  sub     eax, [rbp+plLbound]
0x18045fa34  movsxd  rdx, eax
0x18045fa37  mov     rcx, [rbx+10h]
0x18045fa3b  mov     rax, [r12+r15*8]
0x18045fa3f  mov     [rcx+rdx*8], rax
0x18045fa43  xor     edi, edi
0x18045fa45  jmp     short loc_18045FA4C
0x18045fa47  mov     edi, 80070057h
0x18045fa4c  test    edi, edi
0x18045fa4e  js      loc_18045F91E
0x18045fa54  add     r15d, r13d
0x18045fa57  add     r14d, r13d
0x18045fa5a  cmp     r15d, 4
0x18045fa5e  jb      short loc_18045F9E4
0x18045fa60  jmp     loc_18045F91E
0x18045fa65  mov     eax, 0Ah
0x18045fa6a  mov     dword ptr [rbp+var_10], ecx
0x18045fa6d  mov     [rbp+pvt], ax
0x18045fa71  test    ecx, ecx
0x18045fa73  jns     short loc_18045FA7F
0x18045fa75  cmp     ecx, 8007000Eh
0x18045fa7b  jz      short loc_18045FAD8
0x18045fa7d  jmp     short loc_18045FAC2
0x18045fa7f  lea     r8, [rbp+pvt]
0x18045fa83  lea     rdx, aAutoneutralpoi; "_AutoNeutralPoint"
0x18045fa8a  mov     rcx, r14
0x18045fa8d  call    ?SetPropertyInternal@?$ImageAnalyzerBase@VColorTemperatureAnalyzer@@@@IEAAXPEB_WAEBUtagVARIANT@@@Z; ImageAnalyzerBase<ColorTemperatureAnalyzer>::SetPropertyInternal(wchar_t const *,tagVARIANT const &)
0x18045fa92  lea     rcx, [rbp+pvt]; pvarg
0x18045fa96  call    cs:__imp_VariantClear
0x18045fa9c  mov     rcx, rbx; psa
0x18045fa9f  call    cs:__imp_SafeArrayUnlock
0x18045faa5  test    eax, eax
0x18045faa7  js      short loc_18045FAB2
0x18045faa9  mov     rcx, rbx; psa
0x18045faac  call    cs:__imp_SafeArrayDestroy
0x18045fab2  add     rsp, 40h
0x18045fab6  pop     r15
0x18045fab8  pop     r14
0x18045faba  pop     r13
0x18045fabc  pop     r12
0x18045fabe  pop     rdi
0x18045fabf  pop     rbx
0x18045fac0  pop     rbp
0x18045fac1  retn
0x18045fac2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045fac8  jmp     short $+2
0x18045faca  nop
0x18045facb  mov     edi, 80070057h
0x18045fad0  mov     ecx, edi; int
0x18045fad2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045fad8  mov     ecx, 8007000Eh; int
0x18045fadd  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045fae3  mov     ecx, eax; int
0x18045fae5  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045faeb  mov     ecx, 80004005h; int
0x18045faf0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045faf6  mov     ecx, eax; int
0x18045faf8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045fafe  mov     ecx, eax; int
0x18045fb00  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18045fb06  mov     eax, 0Ah
0x18045fb0b  mov     [rbp+pvt], ax
0x18045fb0f  mov     dword ptr [rbp+var_10], 80070057h
0x18045fb16  mov     ecx, 80070057h; int
0x18045fb1b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
