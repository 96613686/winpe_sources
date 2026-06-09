# Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::GetStartInfo(tagVARIANT *)

- ea: `0x18000b2fc`
- end: `0x18000b515`
- name: `?GetStartInfo@CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAUtagVARIANT@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *this, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005fc0`
- `0x1800070d8`
- `0x18000b030`

## callees

- `0x180002604`
- `0x180007f94`
- `0x18000b2fc`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18000b490`
- `VCRUNTIME140!memcpy` at `0x18000b490`
- `OLEAUT32!__imp_VariantClear` at `0x18000b474`
- `OLEAUT32!__imp_VariantClear` at `0x18000b4a2`
- `OLEAUT32!__imp_VariantClear` at `0x18000b474`
- `OLEAUT32!__imp_VariantClear` at `0x18000b4a2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b37b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000b37b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000b4b9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000b4b9`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000b391`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000b391`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000b4ac`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000b4ac`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000b3f8`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000b3f8`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000b412`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000b412`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::GetStartInfo(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *this,
        struct tagVARIANT *a2)
{
  SAFEARRAY *v5; // rax
  HRESULT v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  SAFEARRAY *v10; // rbx
  HRESULT v11; // edx
  HRESULT Vartype; // r9d
  VARTYPE vt; // r8
  HRESULT v14; // esi
  SAFEARRAY *psa; // [rsp+20h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvt; // [rsp+30h] [rbp-20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  pvt.pRecInfo = 0;
  *(_OWORD *)&a2->vt = 0;
  a2->pRecInfo = pvt.pRecInfo;
  rgsabound = (SAFEARRAYBOUND)3LL;
  v5 = SafeArrayCreate(0x15u, 1u, &rgsabound);
  psa = v5;
  if ( !v5 )
  {
    v6 = -2147024882;
LABEL_24:
    _mm_lfence();
    ATL::AtlThrowImpl(v6);
  }
  v6 = SafeArrayLock(v5);
  if ( v6 < 0 )
    goto LABEL_24;
  v7 = *((_QWORD *)this + 117);
  *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 0) = v7;
  v8 = *((_QWORD *)this + 118);
  *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 1) = v8;
  v9 = *((_QWORD *)this + 119);
  *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 2) = v9;
  v10 = psa;
  if ( !psa )
  {
    pvt.vt = 10;
    pvt.lVal = -2147024809;
    ATL::AtlThrowImpl(-2147024809);
  }
  v11 = SafeArrayCopy(psa, (SAFEARRAY **)&rgsabound);
  if ( v11 < 0 )
  {
    pvt.vt = 10;
    pvt.lVal = v11;
LABEL_21:
    if ( v11 == -2147024882 )
      ATL::AtlThrowImpl(-2147024882);
    _mm_lfence();
    ATL::AtlThrowImpl(v11);
  }
  _mm_lfence();
  Vartype = SafeArrayGetVartype(v10, &pvt.vt);
  v11 = Vartype;
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v10->fFeatures & 0x440) == 0x440 )
  {
    vt = 9;
LABEL_12:
    pvt.vt = vt | 0x2000;
    pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
    goto LABEL_14;
  }
  if ( Vartype >= 0 )
    goto LABEL_12;
  pvt.vt = 10;
  pvt.lVal = Vartype;
LABEL_14:
  if ( Vartype < 0 )
    goto LABEL_21;
  v14 = VariantClear(a2);
  if ( v14 >= 0 )
  {
    _mm_lfence();
    memcpy(a2, &pvt, sizeof(struct tagVARIANT));
    pvt.vt = 0;
    v14 = 0;
  }
  VariantClear(&pvt);
  if ( SafeArrayUnlock(v10) >= 0 )
    SafeArrayDestroy(v10);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000b2fc  mov     [rsp-18h+arg_0], rbx
0x18000b301  mov     [rsp-18h+arg_10], rsi
0x18000b306  push    rbp
0x18000b307  push    rdi
0x18000b308  push    r14
0x18000b30a  mov     rbp, rsp
0x18000b30d  sub     rsp, 50h
0x18000b311  mov     rax, cs:__security_cookie
0x18000b318  xor     rax, rsp
0x18000b31b  mov     [rbp+var_8], rax
0x18000b31f  mov     rdi, rdx
0x18000b322  mov     rsi, rcx
0x18000b325  xor     r14d, r14d
0x18000b328  test    rdx, rdx
0x18000b32b  jnz     short loc_18000B353
0x18000b32d  mov     eax, 80004003h
0x18000b332  mov     rcx, [rbp+var_8]
0x18000b336  xor     rcx, rsp; StackCookie
0x18000b339  call    __security_check_cookie
0x18000b33e  lea     r11, [rsp+50h+var_s0]
0x18000b343  mov     rbx, [r11+20h]
0x18000b347  mov     rsi, [r11+30h]
0x18000b34b  mov     rsp, r11
0x18000b34e  pop     r14
0x18000b350  pop     rdi
0x18000b351  pop     rbp
0x18000b352  retn
0x18000b353  xorps   xmm0, xmm0
0x18000b356  xor     eax, eax
0x18000b358  mov     [rbp+var_10], rax
0x18000b35c  movups  xmmword ptr [rdx], xmm0
0x18000b35f  movsd   xmm0, [rbp+var_10]
0x18000b364  movsd   qword ptr [rdx+10h], xmm0
0x18000b369  mov     qword ptr [rbp+rgsabound.cElements], 3
0x18000b371  lea     ecx, [rax+15h]; vt
0x18000b374  lea     r8, [rbp+rgsabound]; rgsabound
0x18000b378  lea     edx, [rax+1]; cDims
0x18000b37b  call    cs:__imp_SafeArrayCreate
0x18000b381  mov     [rbp+psa], rax
0x18000b385  test    rax, rax
0x18000b388  jz      loc_18000B4E3
0x18000b38e  mov     rcx, rax; psa
0x18000b391  call    cs:__imp_SafeArrayLock
0x18000b397  test    eax, eax
0x18000b399  js      loc_18000B4E8
0x18000b39f  mov     rbx, [rsi+3A8h]
0x18000b3a6  xor     edx, edx
0x18000b3a8  lea     rcx, [rbp+psa]
0x18000b3ac  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000b3b1  mov     [rax], rbx
0x18000b3b4  mov     rbx, [rsi+3B0h]
0x18000b3bb  mov     edx, 1
0x18000b3c0  lea     rcx, [rbp+psa]
0x18000b3c4  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000b3c9  mov     [rax], rbx
0x18000b3cc  mov     rbx, [rsi+3B8h]
0x18000b3d3  mov     edx, 2
0x18000b3d8  lea     rcx, [rbp+psa]
0x18000b3dc  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000b3e1  mov     [rax], rbx
0x18000b3e4  mov     rbx, [rbp+psa]
0x18000b3e8  test    rbx, rbx
0x18000b3eb  jz      loc_18000B4FE
0x18000b3f1  lea     rdx, [rbp+rgsabound]; ppsaOut
0x18000b3f5  mov     rcx, rbx; psa
0x18000b3f8  call    cs:__imp_SafeArrayCopy
0x18000b3fe  mov     edx, eax
0x18000b400  test    eax, eax
0x18000b402  js      loc_18000B4C6
0x18000b408  lfence
0x18000b40b  lea     rdx, [rbp+pvt]; pvt
0x18000b40f  mov     rcx, rbx; psa
0x18000b412  call    cs:__imp_SafeArrayGetVartype
0x18000b418  mov     r9d, eax
0x18000b41b  mov     edx, eax
0x18000b41d  movzx   r8d, [rbp+pvt]
0x18000b422  test    eax, eax
0x18000b424  js      short loc_18000B446
0x18000b426  cmp     r8w, 0Dh
0x18000b42b  jnz     short loc_18000B446
0x18000b42d  movzx   ecx, word ptr [rbx+2]
0x18000b431  mov     eax, 440h
0x18000b436  and     cx, ax
0x18000b439  cmp     cx, ax
0x18000b43c  jnz     short loc_18000B446
0x18000b43e  mov     r8d, 9
0x18000b444  jmp     short loc_18000B44B
0x18000b446  test    r9d, r9d
0x18000b449  js      short loc_18000B460
0x18000b44b  or      r8w, 2000h
0x18000b451  mov     [rbp+pvt], r8w
0x18000b456  mov     rax, qword ptr [rbp+rgsabound.cElements]
0x18000b45a  mov     [rbp+var_18], rax
0x18000b45e  jmp     short loc_18000B46D
0x18000b460  mov     eax, 0Ah
0x18000b465  mov     [rbp+pvt], ax
0x18000b469  mov     dword ptr [rbp+var_18], r9d
0x18000b46d  test    edx, edx
0x18000b46f  js      short loc_18000B4D2
0x18000b471  mov     rcx, rdi; pvarg
0x18000b474  call    cs:__imp_VariantClear
0x18000b47a  mov     esi, eax
0x18000b47c  test    eax, eax
0x18000b47e  js      short loc_18000B49E
0x18000b480  lfence
0x18000b483  mov     r8d, 18h; Size
0x18000b489  lea     rdx, [rbp+pvt]; Src
0x18000b48d  mov     rcx, rdi; void *
0x18000b490  call    cs:__imp_memcpy
0x18000b496  mov     [rbp+pvt], r14w
0x18000b49b  mov     esi, r14d
0x18000b49e  lea     rcx, [rbp+pvt]; pvarg
0x18000b4a2  call    cs:__imp_VariantClear
0x18000b4a8  nop
0x18000b4a9  mov     rcx, rbx; psa
0x18000b4ac  call    cs:__imp_SafeArrayUnlock
0x18000b4b2  test    eax, eax
0x18000b4b4  js      short loc_18000B4BF
0x18000b4b6  mov     rcx, rbx; psa
0x18000b4b9  call    cs:__imp_SafeArrayDestroy
0x18000b4bf  mov     eax, esi
0x18000b4c1  jmp     loc_18000B332
0x18000b4c6  mov     eax, 0Ah
0x18000b4cb  mov     [rbp+pvt], ax
0x18000b4cf  mov     dword ptr [rbp+var_18], edx
0x18000b4d2  mov     eax, 8007000Eh
0x18000b4d7  cmp     edx, eax
0x18000b4d9  jnz     short loc_18000B4F3
0x18000b4db  mov     ecx, eax; int
0x18000b4dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b4e3  mov     eax, 8007000Eh
0x18000b4e8  lfence
0x18000b4eb  mov     ecx, eax; int
0x18000b4ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b4f3  lfence
0x18000b4f6  mov     ecx, edx; int
0x18000b4f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b4fe  mov     eax, 0Ah
0x18000b503  mov     [rbp+pvt], ax
0x18000b507  mov     ecx, 80070057h; int
0x18000b50c  mov     dword ptr [rbp+var_18], ecx
0x18000b50f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
