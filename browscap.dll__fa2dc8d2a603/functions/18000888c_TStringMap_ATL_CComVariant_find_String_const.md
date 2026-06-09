# TStringMap<ATL::CComVariant>::find(String const &)

- ea: `0x18000888c`
- end: `0x18000893a`
- name: `?find@?$TStringMap@VCComVariant@ATL@@@@QEAAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@AEBVString@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800076e8`
- `0x1800081b0`
- `0x180008940`

## callees

- `0x180002498`
- `0x1800037f4`
- `0x180007284`
- `0x18000888c`
- `0x180009cf0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800088a2`
- `OLEAUT32!__imp_VariantInit` at `0x1800088a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800088d9`
- `OLEAUT32!__imp_VariantClear` at `0x18000890b`
- `OLEAUT32!__imp_VariantClear` at `0x1800088d9`
- `OLEAUT32!__imp_VariantClear` at `0x18000890b`
- `OLEAUT32!__imp_VariantCopy` at `0x1800088cb`
- `OLEAUT32!__imp_VariantCopy` at `0x1800088cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TStringMap<ATL::CComVariant>::find(__int64 a1, _BYTE *a2)
{
  __int64 v4; // rax
  HRESULT v5; // eax
  __int64 v6; // rax
  __int64 v7; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h] BYREF
  char v11; // [rsp+40h] [rbp-28h]
  VARIANTARG pvargDest; // [rsp+48h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  v4 = *(_QWORD *)a2;
  v10 = v4;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v11 = 1;
  pvargDest.vt = 0;
  v5 = VariantCopy(&pvargDest, &pvarg);
  if ( v5 < 0 )
  {
    pvargDest.vt = 10;
    pvargDest.lVal = v5;
    ATL::AtlThrowImpl(v5);
  }
  VariantClear(&pvarg);
  v6 = binary_find<std::pair<String,ATL::CComVariant>,StringPairCompare<ATL::CComVariant>>(a1, &v10);
  v7 = v6;
  if ( v6 == *(_QWORD *)(a1 + 16) || !String::operator==(a2, v6) )
    v7 = *(_QWORD *)(a1 + 16);
  VariantClear(&pvargDest);
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(&v10);
  return v7;
}

```

## disassembly

```asm
0x18000888c  push    rbp
0x18000888e  push    rbx
0x18000888f  push    rsi
0x180008890  push    rdi
0x180008891  mov     rbp, rsp
0x180008894  sub     rsp, 68h
0x180008898  mov     rsi, rdx
0x18000889b  mov     rdi, rcx
0x18000889e  lea     rcx, [rbp+pvarg]; pvarg
0x1800088a2  call    cs:__imp_VariantInit
0x1800088a8  nop
0x1800088a9  mov     rax, [rsi]
0x1800088ac  mov     [rbp+var_30], rax
0x1800088b0  test    rax, rax
0x1800088b3  jz      short loc_1800088B9
0x1800088b5  lock inc dword ptr [rax+8]
0x1800088b9  mov     [rbp+var_28], 1
0x1800088bd  xor     eax, eax
0x1800088bf  mov     word ptr [rbp+pvargDest], ax
0x1800088c3  lea     rdx, [rbp+pvarg]; pvargSrc
0x1800088c7  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800088cb  call    cs:__imp_VariantCopy
0x1800088d1  test    eax, eax
0x1800088d3  js      short loc_180008926
0x1800088d5  lea     rcx, [rbp+pvarg]; pvarg
0x1800088d9  call    cs:__imp_VariantClear
0x1800088df  lea     rdx, [rbp+var_30]
0x1800088e3  mov     rcx, rdi
0x1800088e6  call    ??$binary_find@U?$pair@VString@@VCComVariant@ATL@@@std@@U?$StringPairCompare@VCComVariant@ATL@@@@@@YAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@AEAV?$TVector@U?$pair@VString@@VCComVariant@ATL@@@std@@@@AEBU01@AEAU?$StringPairCompare@VCComVariant@ATL@@@@@Z; binary_find<std::pair<String,ATL::CComVariant>,StringPairCompare<ATL::CComVariant>>(TVector<std::pair<String,ATL::CComVariant>> &,std::pair<String,ATL::CComVariant> const &,StringPairCompare<ATL::CComVariant> &)
0x1800088eb  mov     rbx, rax
0x1800088ee  cmp     rax, [rdi+10h]
0x1800088f2  jz      short loc_180008903
0x1800088f4  mov     rdx, rax
0x1800088f7  mov     rcx, rsi
0x1800088fa  call    ??8String@@QEBA_NAEBV0@@Z; String::operator==(String const &)
0x1800088ff  test    al, al
0x180008901  jnz     short loc_180008907
0x180008903  mov     rbx, [rdi+10h]
0x180008907  lea     rcx, [rbp+pvargDest]; pvarg
0x18000890b  call    cs:__imp_VariantClear
0x180008911  lea     rcx, [rbp+var_30]
0x180008915  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x18000891a  mov     rax, rbx
0x18000891d  add     rsp, 68h
0x180008921  pop     rdi
0x180008922  pop     rsi
0x180008923  pop     rbx
0x180008924  pop     rbp
0x180008925  retn
0x180008926  mov     ecx, 0Ah
0x18000892b  mov     word ptr [rbp+pvargDest], cx
0x18000892f  mov     dword ptr [rbp+pvargDest+8], eax
0x180008932  mov     ecx, eax; int
0x180008934  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
