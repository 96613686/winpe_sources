# ProcessorManager::GetProcessorLoadHistory(tagSAFEARRAY * *)

- ea: `0x140022720`
- end: `0x1400229c2`
- name: `?GetProcessorLoadHistory@ProcessorManager@@UEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `674`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140022720`
- `0x1400229c8`
- `0x140023850`
- `0x14006af38`
- `0x140132940`
- `0x140135935`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1400228b5`
- `OLEAUT32!__imp_VariantClear` at `0x1400228b5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400227d4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022845`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1400227d4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140022845`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022879`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400228f6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140022879`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400228f6`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14002279e`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022816`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x14002279e`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140022816`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14002289a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14002289a`

## string_xrefs

- `0x140022940`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022955`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140022994`: `onecore\vm\common\vml\VmAutomation.h`
- `0x1400229b0`: `onecore\vm\common\vml\VmAutomation.h`
- `0x14002296a`: `onecore\vm\common\vml\VmVariant.h`
- `0x14002297f`: `onecore\vm\common\vml\VmVariant.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ProcessorManager::GetProcessorLoadHistory(ProcessorManager *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v4; // r15
  HRESULT v5; // eax
  VARIANTARG *v6; // rdi
  __int64 i; // rbx
  __int64 v8; // r14
  SAFEARRAY *v9; // rax
  SAFEARRAY *v10; // rsi
  HRESULT v11; // eax
  HRESULT Vartype; // eax
  HRESULT v13; // eax
  SAFEARRAY *psa; // [rsp+20h] [rbp-60h]
  void *v15; // [rsp+28h] [rbp-58h] BYREF
  SAFEARRAY *v16; // [rsp+30h] [rbp-50h]
  SAFEARRAY *v17; // [rsp+38h] [rbp-48h]
  VARTYPE pvt; // [rsp+40h] [rbp-40h] BYREF
  __int128 v19; // [rsp+48h] [rbp-38h] BYREF
  __int64 v20; // [rsp+58h] [rbp-28h]
  void *ppvData[2]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  VpStatistics::GetProcessorLoadHistory(*((_QWORD *)this + 93), &v19);
  Vector = SafeArrayCreateVectorEx(
             0xCu,
             0,
             -1431655765 * (unsigned int)((__int64)(*((_QWORD *)&v19 + 1) - v19) >> 3),
             0);
  v4 = Vector;
  if ( !Vector )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      (int)psa);
  v16 = Vector;
  ppvData[0] = Vector;
  ppvData[1] = 0;
  v5 = SafeArrayAccessData(Vector, &ppvData[1]);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B2,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)(unsigned int)v5,
      (int)psa);
  v6 = (VARIANTARG *)ppvData[1];
  for ( i = v19; i != *((_QWORD *)&v19 + 1); i += 24 )
  {
    v8 = (__int64)(*(_QWORD *)(i + 8) - *(_QWORD *)i) >> 2;
    v9 = SafeArrayCreateVectorEx(0x13u, 0, v8, 0);
    v10 = v9;
    v17 = v9;
    if ( !v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)0x8007000ELL,
        (int)psa);
    psa = v9;
    v15 = 0;
    v11 = SafeArrayAccessData(v9, &v15);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7B2,
        (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
        (const char *)(unsigned int)v11,
        (int)psa);
    memcpy_0(v15, *(const void **)i, 4LL * (unsigned int)v8);
    SafeArrayUnaccessData(psa);
    v17 = 0;
    pvt = 0;
    Vartype = SafeArrayGetVartype(v10, &pvt);
    if ( Vartype < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6ED,
        (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
        (const char *)(unsigned int)Vartype,
        (int)psa);
    v13 = VariantClear(v6);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x723,
        (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
        (const char *)(unsigned int)v13,
        (int)psa);
    v6->vt = pvt | 0x2000;
    v6->llVal = (LONGLONG)v10;
    ++v6;
  }
  *a2 = v4;
  if ( ppvData[0] )
    SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
  std::vector<std::vector<unsigned long>>::_Tidy(&v19);
}

```

## disassembly

```asm
0x140022720  mov     [rsp-28h+arg_10], rbx
0x140022725  mov     [rsp-28h+arg_18], rsi
0x14002272a  push    rbp
0x14002272b  push    rdi
0x14002272c  push    r12
0x14002272e  push    r14
0x140022730  push    r15
0x140022732  mov     rbp, rsp
0x140022735  sub     rsp, 80h
0x14002273c  mov     rax, cs:__security_cookie
0x140022743  xor     rax, rsp
0x140022746  mov     [rbp+var_10], rax
0x14002274a  mov     r12, rdx
0x14002274d  mov     qword ptr [rdx], 0
0x140022754  mov     [rbp+var_50], 0
0x14002275c  xor     eax, eax
0x14002275e  xorps   xmm1, xmm1
0x140022761  movdqu  [rbp+var_38], xmm1
0x140022766  mov     [rbp+var_28], rax
0x14002276a  lea     rdx, [rbp+var_38]
0x14002276e  mov     rcx, [rcx+2E8h]
0x140022775  call    ?GetProcessorLoadHistory@VpStatistics@@UEBAXAEAV?$vector@V?$vector@KV?$allocator@K@std@@@std@@V?$allocator@V?$vector@KV?$allocator@K@std@@@std@@@2@@std@@@Z; VpStatistics::GetProcessorLoadHistory(std::vector<std::vector<ulong>> &)
0x14002277a  mov     r8, qword ptr [rbp+var_38+8]
0x14002277e  sub     r8, qword ptr [rbp+var_38]
0x140022782  sar     r8, 3
0x140022786  mov     rax, 0AAAAAAAAAAAAAAABh
0x140022790  imul    r8, rax; cElements
0x140022794  mov     ecx, 0Ch; vt
0x140022799  xor     r9d, r9d; pvExtra
0x14002279c  xor     edx, edx; lLbound
0x14002279e  call    cs:__imp_SafeArrayCreateVectorEx
0x1400227a5  nop     dword ptr [rax+rax+00h]
0x1400227aa  mov     r15, rax
0x1400227ad  test    rax, rax
0x1400227b0  jz      loc_140022936
0x1400227b6  mov     [rbp+var_50], rax
0x1400227ba  xorps   xmm0, xmm0
0x1400227bd  movups  xmmword ptr [rbp+ppvData], xmm0
0x1400227c1  mov     [rbp+ppvData], rax
0x1400227c5  mov     [rbp+ppvData+8], 0
0x1400227cd  lea     rdx, [rbp+ppvData+8]; ppvData
0x1400227d1  mov     rcx, rax; psa
0x1400227d4  call    cs:__imp_SafeArrayAccessData
0x1400227db  nop     dword ptr [rax+rax+00h]
0x1400227e0  mov     rcx, [rbp+28h]; this
0x1400227e4  test    eax, eax
0x1400227e6  js      loc_140022952
0x1400227ec  mov     rdi, [rbp+ppvData+8]
0x1400227f0  mov     rbx, qword ptr [rbp+var_38]
0x1400227f4  cmp     rbx, qword ptr [rbp+var_38+8]
0x1400227f8  jz      loc_1400228E9
0x1400227fe  mov     r14, [rbx+8]
0x140022802  sub     r14, [rbx]
0x140022805  sar     r14, 2
0x140022809  mov     ecx, 13h; vt
0x14002280e  xor     r9d, r9d; pvExtra
0x140022811  mov     r8d, r14d; cElements
0x140022814  xor     edx, edx; lLbound
0x140022816  call    cs:__imp_SafeArrayCreateVectorEx
0x14002281d  nop     dword ptr [rax+rax+00h]
0x140022822  mov     rsi, rax
0x140022825  mov     [rbp+var_48], rax
0x140022829  test    rax, rax
0x14002282c  jz      loc_1400229A6
0x140022832  mov     [rbp+psa], rax
0x140022836  mov     [rbp+var_58], 0
0x14002283e  lea     rdx, [rbp+var_58]; ppvData
0x140022842  mov     rcx, rax; psa
0x140022845  call    cs:__imp_SafeArrayAccessData
0x14002284c  nop     dword ptr [rax+rax+00h]
0x140022851  mov     rcx, [rbp+28h]; this
0x140022855  test    eax, eax
0x140022857  js      loc_140022991
0x14002285d  mov     r8d, r14d
0x140022860  shl     r8, 2; Size
0x140022864  mov     rdx, [rbx]; Src
0x140022867  mov     rcx, [rbp+var_58]; void *
0x14002286b  call    memcpy_0
0x140022870  mov     rcx, [rbp+psa]; psa
0x140022874  test    rcx, rcx
0x140022877  jz      short loc_140022885
0x140022879  call    cs:__imp_SafeArrayUnaccessData
0x140022880  nop     dword ptr [rax+rax+00h]
0x140022885  mov     [rbp+var_48], 0
0x14002288d  xor     eax, eax
0x14002288f  mov     [rbp+pvt], ax
0x140022893  lea     rdx, [rbp+pvt]; pvt
0x140022897  mov     rcx, rsi; psa
0x14002289a  call    cs:__imp_SafeArrayGetVartype
0x1400228a1  nop     dword ptr [rax+rax+00h]
0x1400228a6  mov     rcx, [rbp+28h]; this
0x1400228aa  test    eax, eax
0x1400228ac  js      loc_14002297C
0x1400228b2  mov     rcx, rdi; pvarg
0x1400228b5  call    cs:__imp_VariantClear
0x1400228bc  nop     dword ptr [rax+rax+00h]
0x1400228c1  mov     rcx, [rbp+28h]; this
0x1400228c5  test    eax, eax
0x1400228c7  js      loc_140022967
0x1400228cd  movzx   eax, [rbp+pvt]
0x1400228d1  or      ax, 2000h
0x1400228d5  mov     [rdi], ax
0x1400228d8  mov     [rdi+8], rsi
0x1400228dc  add     rbx, 18h
0x1400228e0  add     rdi, 18h
0x1400228e4  jmp     loc_1400227F4
0x1400228e9  mov     [r12], r15
0x1400228ed  mov     rcx, [rbp+ppvData]; psa
0x1400228f1  test    rcx, rcx
0x1400228f4  jz      short loc_140022903
0x1400228f6  call    cs:__imp_SafeArrayUnaccessData
0x1400228fd  nop     dword ptr [rax+rax+00h]
0x140022902  nop
0x140022903  lea     rcx, [rbp+var_38]
0x140022907  call    ?_Tidy@?$vector@V?$vector@KV?$allocator@K@std@@@std@@V?$allocator@V?$vector@KV?$allocator@K@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<ulong>>::_Tidy(void)
0x14002290c  nop
0x14002290d  mov     rcx, [rbp+var_10]
0x140022911  xor     rcx, rsp; StackCookie
0x140022914  call    __security_check_cookie
0x140022919  lea     r11, [rsp+80h+var_s0]
0x140022921  mov     rbx, [r11+40h]
0x140022925  mov     rsi, [r11+48h]
0x140022929  mov     rsp, r11
0x14002292c  pop     r15
0x14002292e  pop     r14
0x140022930  pop     r12
0x140022932  pop     rdi
0x140022933  pop     rbp
0x140022934  retn
0x140022936  mov     rcx, [rbp+28h]; this
0x14002293a  mov     r9d, 8007000Eh; char *
0x140022940  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140022947  mov     edx, 250h; void *
0x14002294c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022952  mov     r9d, eax; char *
0x140022955  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14002295c  mov     edx, 7B2h; void *
0x140022961  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022967  mov     r9d, eax; char *
0x14002296a  lea     r8, aOnecoreVmCommo_42; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140022971  mov     edx, 723h; void *
0x140022976  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14002297c  mov     r9d, eax; char *
0x14002297f  lea     r8, aOnecoreVmCommo_42; "onecore\\vm\\common\\vml\\VmVariant.h"
0x140022986  mov     edx, 6EDh; void *
0x14002298b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140022991  mov     r9d, eax; char *
0x140022994  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x14002299b  mov     edx, 7B2h; void *
0x1400229a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400229a6  mov     rcx, [rbp+28h]; this
0x1400229aa  mov     r9d, 8007000Eh; char *
0x1400229b0  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x1400229b7  mov     edx, 1D9h; void *
0x1400229bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
