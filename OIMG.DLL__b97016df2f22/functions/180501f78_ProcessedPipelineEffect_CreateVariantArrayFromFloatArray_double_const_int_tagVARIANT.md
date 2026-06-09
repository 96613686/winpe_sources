# ProcessedPipelineEffect::CreateVariantArrayFromFloatArray(double const *,int,tagVARIANT *)

- ea: `0x180501f78`
- end: `0x18050219f`
- name: `?CreateVariantArrayFromFloatArray@ProcessedPipelineEffect@@CAXPEBNHPEAUtagVARIANT@@@Z`
- size: `551`
- prototype: `static void(const double *, int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1805021a0`

## callees

- `0x1804c6944`
- `0x180501f78`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180502109`
- `OLEAUT32!__imp_VariantClear` at `0x180502109`
- `OLEAUT32!__imp_VariantCopy` at `0x1805020ff`
- `OLEAUT32!__imp_VariantCopy` at `0x1805020ff`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180501fb5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180501fb5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18050211f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18050211f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050203a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050203a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180502010`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180502010`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180501fd1`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180501fd1`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180502112`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180502112`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180502084`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180502084`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180502097`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180502097`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProcessedPipelineEffect::CreateVariantArrayFromFloatArray(
        const double *a1,
        signed int a2,
        struct tagVARIANT *a3)
{
  __int64 v4; // rsi
  SAFEARRAY *v6; // rax
  SAFEARRAY *v7; // rbx
  HRESULT v8; // eax
  LONG v9; // edi
  __int64 v10; // r14
  __int64 v11; // rsi
  double v12; // xmm6_8
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  VARIANTARG pvt; // [rsp+28h] [rbp-28h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+38h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+98h] [rbp+48h] BYREF

  v4 = a2;
  rgsabound.cElements = a2;
  rgsabound.lLbound = 0;
  v6 = SafeArrayCreate(5u, 1u, &rgsabound);
  v7 = v6;
  if ( v6 )
    v8 = SafeArrayLock(v6);
  else
    v8 = -2147024882;
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  v9 = 0;
  v10 = v4;
  if ( (int)v4 > 0 )
  {
    v11 = 0;
    do
    {
      v12 = a1[v11];
      if ( !v7 )
        ATL::BaseAtlThrow(-2147467259);
      plLbound = 0;
      LBound = SafeArrayGetLBound(v7, 1u, &plLbound);
      if ( LBound < 0 )
        ATL::BaseAtlThrow(LBound);
      if ( v9 < plLbound )
        goto LABEL_32;
      rgsabound.cElements = 0;
      UBound = SafeArrayGetUBound(v7, 1u, (LONG *)&rgsabound);
      if ( UBound < 0 )
        ATL::BaseAtlThrow(UBound);
      if ( v9 > (int)rgsabound.cElements )
LABEL_32:
        ATL::BaseAtlThrow(-2147024809);
      *((double *)v7->pvData + v9 - plLbound) = v12;
      ++v9;
      ++v11;
    }
    while ( v11 < v10 );
  }
  if ( !v7 )
  {
    pvt.vt = 10;
    pvt.lVal = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  rgsabound = 0;
  Vartype = SafeArrayCopy(v7, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_21;
  Vartype = SafeArrayGetVartype(v7, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v7->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_21:
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
  VariantCopy(a3, &pvt);
  VariantClear(&pvt);
  if ( SafeArrayUnlock(v7) >= 0 )
    SafeArrayDestroy(v7);
}

```

## disassembly

```asm
0x180501f78  mov     [rsp-28h+arg_0], rbx
0x180501f7d  mov     [rsp-28h+arg_10], rsi
0x180501f82  push    rbp
0x180501f83  push    rdi
0x180501f84  push    r12
0x180501f86  push    r14
0x180501f88  push    r15
0x180501f8a  mov     rbp, rsp
0x180501f8d  sub     rsp, 50h
0x180501f91  movaps  [rsp+50h+var_10], xmm6
0x180501f96  mov     r12, r8
0x180501f99  movsxd  rsi, edx
0x180501f9c  mov     r15, rcx
0x180501f9f  mov     [rbp+rgsabound.cElements], esi
0x180501fa2  mov     [rbp+rgsabound.lLbound], 0
0x180501fa9  mov     ecx, 5; vt
0x180501fae  lea     r8, [rbp+rgsabound]; rgsabound
0x180501fb2  lea     edx, [rcx-4]; cDims
0x180501fb5  call    cs:__imp_SafeArrayCreate
0x180501fbb  mov     rbx, rax
0x180501fbe  mov     [rbp+var_30], rax
0x180501fc2  test    rax, rax
0x180501fc5  jnz     short loc_180501FCE
0x180501fc7  mov     eax, 8007000Eh
0x180501fcc  jmp     short loc_180501FD7
0x180501fce  mov     rcx, rbx; psa
0x180501fd1  call    cs:__imp_SafeArrayLock
0x180501fd7  test    eax, eax
0x180501fd9  js      loc_180502157
0x180501fdf  xor     edi, edi
0x180501fe1  mov     r14, rsi
0x180501fe4  test    esi, esi
0x180501fe6  jle     loc_18050206C
0x180501fec  xor     esi, esi
0x180501fee  movsd   xmm6, qword ptr [r15+rsi*8]
0x180501ff4  test    rbx, rbx
0x180501ff7  jz      loc_180502194
0x180501ffd  mov     [rbp+plLbound], 0
0x180502004  lea     r8, [rbp+plLbound]; plLbound
0x180502008  mov     edx, 1; nDim
0x18050200d  mov     rcx, rbx; psa
0x180502010  call    cs:__imp_SafeArrayGetLBound
0x180502016  test    eax, eax
0x180502018  js      loc_18050218C
0x18050201e  cmp     edi, [rbp+plLbound]
0x180502021  jl      loc_180502181
0x180502027  mov     [rbp+rgsabound.cElements], 0
0x18050202e  lea     r8, [rbp+rgsabound]; plUbound
0x180502032  mov     edx, 1; nDim
0x180502037  mov     rcx, rbx; psa
0x18050203a  call    cs:__imp_SafeArrayGetUBound
0x180502040  test    eax, eax
0x180502042  js      loc_180502179
0x180502048  cmp     edi, [rbp+rgsabound.cElements]
0x18050204b  jg      loc_180502181
0x180502051  mov     eax, edi
0x180502053  sub     eax, [rbp+plLbound]
0x180502056  movsxd  rcx, eax
0x180502059  mov     rax, [rbx+10h]
0x18050205d  movsd   qword ptr [rax+rcx*8], xmm6
0x180502062  inc     edi
0x180502064  inc     rsi
0x180502067  cmp     rsi, r14
0x18050206a  jl      short loc_180501FEE
0x18050206c  test    rbx, rbx
0x18050206f  jz      loc_180502162
0x180502075  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18050207d  lea     rdx, [rbp+rgsabound]; ppsaOut
0x180502081  mov     rcx, rbx; psa
0x180502084  call    cs:__imp_SafeArrayCopy
0x18050208a  mov     ecx, eax; int
0x18050208c  test    eax, eax
0x18050208e  js      short loc_1805020DD
0x180502090  lea     rdx, [rbp+pvt]; pvt
0x180502094  mov     rcx, rbx; psa
0x180502097  call    cs:__imp_SafeArrayGetVartype
0x18050209d  mov     ecx, eax
0x18050209f  movzx   edx, [rbp+pvt]
0x1805020a3  test    eax, eax
0x1805020a5  js      short loc_1805020C6
0x1805020a7  cmp     dx, 0Dh
0x1805020ab  jnz     short loc_1805020C6
0x1805020ad  movzx   eax, word ptr [rbx+2]
0x1805020b1  mov     r8d, 440h
0x1805020b7  and     ax, r8w
0x1805020bb  cmp     ax, r8w
0x1805020bf  jnz     short loc_1805020C6
0x1805020c1  mov     edx, 9
0x1805020c6  test    ecx, ecx
0x1805020c8  js      short loc_1805020DD
0x1805020ca  or      dx, 2000h
0x1805020cf  mov     [rbp+pvt], dx
0x1805020d3  mov     rax, qword ptr [rbp+rgsabound.cElements]
0x1805020d7  mov     [rbp+var_20], rax
0x1805020db  jmp     short loc_1805020E9
0x1805020dd  mov     eax, 0Ah
0x1805020e2  mov     dword ptr [rbp+var_20], ecx
0x1805020e5  mov     [rbp+pvt], ax
0x1805020e9  test    ecx, ecx
0x1805020eb  jns     short loc_1805020F8
0x1805020ed  mov     eax, 8007000Eh
0x1805020f2  cmp     ecx, eax
0x1805020f4  jz      short loc_18050214C
0x1805020f6  jmp     short loc_180502143
0x1805020f8  lea     rdx, [rbp+pvt]; pvargSrc
0x1805020fc  mov     rcx, r12; pvargDest
0x1805020ff  call    cs:__imp_VariantCopy
0x180502105  lea     rcx, [rbp+pvt]; pvarg
0x180502109  call    cs:__imp_VariantClear
0x18050210f  mov     rcx, rbx; psa
0x180502112  call    cs:__imp_SafeArrayUnlock
0x180502118  test    eax, eax
0x18050211a  js      short loc_180502125
0x18050211c  mov     rcx, rbx; psa
0x18050211f  call    cs:__imp_SafeArrayDestroy
0x180502125  lea     r11, [rsp+50h+var_s0]
0x18050212a  mov     rbx, [r11+30h]
0x18050212e  mov     rsi, [r11+40h]
0x180502132  movaps  xmm6, [rsp+50h+var_10]
0x180502137  mov     rsp, r11
0x18050213a  pop     r15
0x18050213c  pop     r14
0x18050213e  pop     r12
0x180502140  pop     rdi
0x180502141  pop     rbp
0x180502142  retn
0x180502143  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180502149  jmp     short $+2
0x18050214b  nop
0x18050214c  mov     ecx, eax; int
0x18050214e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180502154  jmp     short $+2
0x180502156  nop
0x180502157  mov     ecx, eax; int
0x180502159  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18050215f  jmp     short $+2
0x180502161  nop
0x180502162  mov     eax, 0Ah
0x180502167  mov     [rbp+pvt], ax
0x18050216b  mov     ecx, 80070057h; int
0x180502170  mov     dword ptr [rbp+var_20], ecx
0x180502173  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180502179  mov     ecx, eax; int
0x18050217b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180502181  mov     ecx, 80070057h; int
0x180502186  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18050218c  mov     ecx, eax; int
0x18050218e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180502194  mov     ecx, 80004005h; int
0x180502199  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
