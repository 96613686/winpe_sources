# TStringMap<ATL::CComVariant>::operator[](String const &)

- ea: `0x180007570`
- end: `0x1800076e0`
- name: `??A?$TStringMap@VCComVariant@ATL@@@@QEAAAEAVCComVariant@ATL@@AEBVString@@@Z`
- size: `368`
- prototype: `char *__fastcall(_QWORD *, _BYTE *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800076e8`
- `0x180007968`

## callees

- `0x180002498`
- `0x1800037f4`
- `0x180007284`
- `0x180007570`
- `0x180008ac4`
- `0x180009cf0`
- `0x18000b602`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180007586`
- `OLEAUT32!__imp_VariantInit` at `0x180007586`
- `OLEAUT32!__imp_VariantClear` at `0x1800075c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800076a0`
- `OLEAUT32!__imp_VariantClear` at `0x1800075c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800076a0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800075af`
- `OLEAUT32!__imp_VariantCopy` at `0x18000768d`
- `OLEAUT32!__imp_VariantCopy` at `0x1800075af`
- `OLEAUT32!__imp_VariantCopy` at `0x18000768d`

## pseudocode

```c
char *__fastcall TStringMap<ATL::CComVariant>::operator[](_QWORD *a1, _BYTE *a2)
{
  __int64 v4; // rax
  HRESULT v5; // eax
  __int64 v6; // rax
  char *v7; // rbx
  __int64 v8; // rcx
  char *v9; // rcx
  __int64 v10; // rax
  HRESULT v11; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  char v15; // [rsp+40h] [rbp-28h]
  VARIANTARG pvargDest; // [rsp+48h] [rbp-20h] BYREF
  char *v17; // [rsp+98h] [rbp+30h] BYREF

  VariantInit(&pvarg);
  v4 = *(_QWORD *)a2;
  v14 = v4;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v15 = 1;
  pvargDest.vt = 0;
  v5 = VariantCopy(&pvargDest, &pvarg);
  if ( v5 < 0 )
  {
    pvargDest.vt = 10;
    pvargDest.lVal = v5;
    ATL::AtlThrowImpl(v5);
  }
  VariantClear(&pvarg);
  v6 = binary_find<std::pair<String,ATL::CComVariant>,StringPairCompare<ATL::CComVariant>>(a1, &v14);
  v7 = (char *)v6;
  if ( v6 == a1[2] || !String::operator==(a2, v6) )
  {
    v17 = v7;
    v8 = a1[2] - a1[1];
    if ( ((__int64)((unsigned __int128)(v8 * (__int128)0x6666666666666667LL) >> 64) >> 4)
       + ((unsigned __int64)((unsigned __int128)(v8 * (__int128)0x6666666666666667LL) >> 64) >> 63)
       + 1 >= *a1 )
    {
      TVector<std::pair<String,ATL::CComVariant>>::growSpace(a1, &v17);
      v7 = v17;
    }
    v9 = (char *)a1[2];
    if ( v7 != v9 )
      memmove_0(v7 + 40, v7, 40 * ((v9 - v7) / 40));
    v17 = v7;
    v10 = v14;
    *(_QWORD *)v7 = v14;
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v7[8] = 1;
    *((_WORD *)v7 + 8) = 0;
    v11 = VariantCopy((VARIANTARG *)(v7 + 16), &pvargDest);
    if ( v11 < 0 )
    {
      *((_WORD *)v7 + 8) = 10;
      *((_DWORD *)v7 + 6) = v11;
      ATL::AtlThrowImpl(v11);
    }
    a1[2] += 40LL;
  }
  VariantClear(&pvargDest);
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(&v14);
  return v7 + 16;
}

```

## disassembly

```asm
0x180007570  push    rbp
0x180007572  push    rbx
0x180007573  push    rsi
0x180007574  push    rdi
0x180007575  mov     rbp, rsp
0x180007578  sub     rsp, 68h
0x18000757c  mov     rsi, rdx
0x18000757f  mov     rdi, rcx
0x180007582  lea     rcx, [rbp+pvarg]; pvarg
0x180007586  call    cs:__imp_VariantInit
0x18000758c  nop
0x18000758d  mov     rax, [rsi]
0x180007590  mov     [rbp+var_30], rax
0x180007594  test    rax, rax
0x180007597  jz      short loc_18000759D
0x180007599  lock inc dword ptr [rax+8]
0x18000759d  mov     [rbp+var_28], 1
0x1800075a1  xor     eax, eax
0x1800075a3  mov     word ptr [rbp+pvargDest], ax
0x1800075a7  lea     rdx, [rbp+pvarg]; pvargSrc
0x1800075ab  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800075af  call    cs:__imp_VariantCopy
0x1800075b5  test    eax, eax
0x1800075b7  js      loc_1800076CC
0x1800075bd  lea     rcx, [rbp+pvarg]; pvarg
0x1800075c1  call    cs:__imp_VariantClear
0x1800075c7  lea     rdx, [rbp+var_30]
0x1800075cb  mov     rcx, rdi
0x1800075ce  call    ??$binary_find@U?$pair@VString@@VCComVariant@ATL@@@std@@U?$StringPairCompare@VCComVariant@ATL@@@@@@YAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@AEAV?$TVector@U?$pair@VString@@VCComVariant@ATL@@@std@@@@AEBU01@AEAU?$StringPairCompare@VCComVariant@ATL@@@@@Z; binary_find<std::pair<String,ATL::CComVariant>,StringPairCompare<ATL::CComVariant>>(TVector<std::pair<String,ATL::CComVariant>> &,std::pair<String,ATL::CComVariant> const &,StringPairCompare<ATL::CComVariant> &)
0x1800075d3  mov     rbx, rax
0x1800075d6  cmp     rax, [rdi+10h]
0x1800075da  jz      short loc_1800075EF
0x1800075dc  mov     rdx, rax
0x1800075df  mov     rcx, rsi
0x1800075e2  call    ??8String@@QEBA_NAEBV0@@Z; String::operator==(String const &)
0x1800075e7  test    al, al
0x1800075e9  jnz     loc_18000769C
0x1800075ef  mov     [rbp+arg_8], rbx
0x1800075f3  mov     rcx, [rdi+10h]
0x1800075f7  sub     rcx, [rdi+8]
0x1800075fb  mov     rsi, 6666666666666667h
0x180007605  mov     rax, rsi
0x180007608  imul    rcx
0x18000760b  sar     rdx, 4
0x18000760f  mov     rax, rdx
0x180007612  shr     rax, 3Fh
0x180007616  inc     rax
0x180007619  add     rax, rdx
0x18000761c  cmp     rax, [rdi]
0x18000761f  jb      short loc_180007631
0x180007621  lea     rdx, [rbp+arg_8]
0x180007625  mov     rcx, rdi
0x180007628  call    ?growSpace@?$TVector@U?$pair@VString@@VCComVariant@ATL@@@std@@@@AEAAXAEAPEAU?$pair@VString@@VCComVariant@ATL@@@std@@_K@Z; TVector<std::pair<String,ATL::CComVariant>>::growSpace(std::pair<String,ATL::CComVariant> * &,unsigned __int64)
0x18000762d  mov     rbx, [rbp+arg_8]
0x180007631  mov     rcx, [rdi+10h]
0x180007635  cmp     rbx, rcx
0x180007638  jz      short loc_180007665
0x18000763a  sub     rcx, rbx
0x18000763d  mov     rax, rsi
0x180007640  imul    rcx
0x180007643  sar     rdx, 4
0x180007647  mov     rax, rdx
0x18000764a  shr     rax, 3Fh
0x18000764e  add     rdx, rax
0x180007651  lea     r8, [rdx+rdx*4]
0x180007655  shl     r8, 3; Size
0x180007659  lea     rcx, [rbx+28h]; void *
0x18000765d  mov     rdx, rbx; Src
0x180007660  call    memmove_0
0x180007665  mov     [rbp+arg_8], rbx
0x180007669  mov     rax, [rbp+var_30]
0x18000766d  mov     [rbx], rax
0x180007670  test    rax, rax
0x180007673  jz      short loc_180007679
0x180007675  lock inc dword ptr [rax+8]
0x180007679  mov     byte ptr [rbx+8], 1
0x18000767d  lea     rsi, [rbx+10h]
0x180007681  xor     eax, eax
0x180007683  mov     [rsi], ax
0x180007686  lea     rdx, [rbp+pvargDest]; pvargSrc
0x18000768a  mov     rcx, rsi; pvargDest
0x18000768d  call    cs:__imp_VariantCopy
0x180007693  test    eax, eax
0x180007695  js      short loc_1800076BC
0x180007697  add     qword ptr [rdi+10h], 28h ; '('
0x18000769c  lea     rcx, [rbp+pvargDest]; pvarg
0x1800076a0  call    cs:__imp_VariantClear
0x1800076a6  lea     rcx, [rbp+var_30]
0x1800076aa  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x1800076af  lea     rax, [rbx+10h]
0x1800076b3  add     rsp, 68h
0x1800076b7  pop     rdi
0x1800076b8  pop     rsi
0x1800076b9  pop     rbx
0x1800076ba  pop     rbp
0x1800076bb  retn
0x1800076bc  mov     word ptr [rsi], 0Ah
0x1800076c1  mov     [rsi+8], eax
0x1800076c4  mov     ecx, eax; int
0x1800076c6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800076cc  mov     ecx, 0Ah
0x1800076d1  mov     word ptr [rbp+pvargDest], cx
0x1800076d5  mov     dword ptr [rbp+pvargDest+8], eax
0x1800076d8  mov     ecx, eax; int
0x1800076da  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
