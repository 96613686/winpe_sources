# ScriptHelpers::GetVectorFromScriptArray(tagVARIANT const &,std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>> &)

- ea: `0x18002e670`
- end: `0x18002e942`
- name: `?GetVectorFromScriptArray@ScriptHelpers@@YAJAEBUtagVARIANT@@AEAV?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004690`

## callees

- `0x180003858`
- `0x180003c38`
- `0x1800056ec`
- `0x18001e894`
- `0x18002d5a4`
- `0x18002e590`
- `0x18002e670`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002e6e4`
- `OLEAUT32!__imp_VariantInit` at `0x18002e7ab`
- `OLEAUT32!__imp_VariantInit` at `0x18002e6e4`
- `OLEAUT32!__imp_VariantInit` at `0x18002e7ab`
- `OLEAUT32!__imp_VariantClear` at `0x18002e69c`
- `OLEAUT32!__imp_VariantClear` at `0x18002e7f0`
- `OLEAUT32!__imp_VariantClear` at `0x18002e859`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8a8`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8c8`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8f4`
- `OLEAUT32!__imp_VariantClear` at `0x18002e69c`
- `OLEAUT32!__imp_VariantClear` at `0x18002e7f0`
- `OLEAUT32!__imp_VariantClear` at `0x18002e859`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8a8`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8c8`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8f4`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e7c7`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e7c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ScriptHelpers::GetVectorFromScriptArray(__int64 a1, __int64 a2)
{
  VARIANTARG *v4; // r14
  VARIANTARG *v5; // rbx
  __int64 v6; // rbx
  int PropertyByName; // edi
  unsigned __int64 ullVal; // r14
  __int64 v9; // rdi
  __int64 v10; // r12
  VARIANTARG *v11; // rdi
  HRESULT v12; // eax
  int v13; // r15d
  VARIANTARG pvarg; // [rsp+20h] [rbp-30h] BYREF
  VARIANTARG pvargSrc; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+90h] [rbp+40h] BYREF
  __int64 v18; // [rsp+98h] [rbp+48h] BYREF

  v4 = *(VARIANTARG **)(a2 + 8);
  v5 = *(VARIANTARG **)a2;
  if ( *(VARIANTARG **)a2 != v4 )
  {
    do
      VariantClear(v5++);
    while ( v5 != v4 );
    *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
  }
  if ( *(_WORD *)a1 != 9 )
    return 2147942487LL;
  v6 = *(_QWORD *)(a1 + 8);
  if ( !v6 )
    return 2147942487LL;
  v18 = *(_QWORD *)(a1 + 8);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  VariantInit(&pvarg);
  PropertyByName = ATL::CComPtr<IDispatch>::GetPropertyByName(&v18, L"length", &pvarg);
  if ( PropertyByName )
  {
    if ( PropertyByName >= 0 )
      PropertyByName = -2147467259;
    VariantClear(&pvarg);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return (unsigned int)PropertyByName;
  }
  else
  {
    ullVal = pvarg.ullVal;
    if ( pvarg.vt == 3 && pvarg.iVal >= 0 || pvarg.vt == 20 && pvarg.llVal >= 0 )
    {
      if ( pvarg.vt == 3 )
        ullVal = pvarg.iVal;
      v17 = ullVal;
      if ( ullVal > 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a2 + 16) - *(_QWORD *)a2) >> 3) )
      {
        if ( ullVal > 0xAAAAAAAAAAAAAAALL )
          std::vector<ATL::CComVariant>::_Xlength();
        std::vector<ATL::CComVariant>::_Reallocate<0>(a2, &v17);
      }
      v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v17 = v9;
      v10 = 0;
      if ( ullVal )
      {
        while ( 1 )
        {
          VariantInit(&pvargSrc);
          v11 = *(VARIANTARG **)(a2 + 8);
          if ( v11 == *(VARIANTARG **)(a2 + 16) )
          {
            std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(a2, *(_QWORD *)(a2 + 8), &pvargSrc);
          }
          else
          {
            v11->vt = 0;
            v12 = VariantCopy(v11, &pvargSrc);
            if ( v12 < 0 )
            {
              v11->vt = 10;
              v11->lVal = v12;
              ATL::AtlThrowImpl(v12);
            }
            *(_QWORD *)(a2 + 8) += 24LL;
          }
          VariantClear(&pvargSrc);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v17,
            L"%Iu",
            v10);
          v9 = v17;
          v13 = ATL::CComPtr<IDispatch>::GetPropertyByName(&v18, v17, *(_QWORD *)(a2 + 8) - 24LL);
          if ( v13 )
            break;
          if ( ++v10 >= ullVal )
            goto LABEL_23;
        }
        if ( v13 >= 0 )
          v13 = -2147467259;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
        VariantClear(&pvarg);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        return (unsigned int)v13;
      }
      else
      {
LABEL_23:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
        VariantClear(&pvarg);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        return 0;
      }
    }
    else
    {
      VariantClear(&pvarg);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      return 2147500037LL;
    }
  }
}

```

## disassembly

```asm
0x18002e670  mov     [rsp-38h+arg_10], rbx
0x18002e675  push    rbp
0x18002e676  push    rsi
0x18002e677  push    rdi
0x18002e678  push    r12
0x18002e67a  push    r13
0x18002e67c  push    r14
0x18002e67e  push    r15
0x18002e680  mov     rbp, rsp
0x18002e683  sub     rsp, 50h
0x18002e687  mov     rsi, rdx
0x18002e68a  mov     rdi, rcx
0x18002e68d  mov     r14, [rdx+8]
0x18002e691  mov     rbx, [rdx]
0x18002e694  cmp     rbx, r14
0x18002e697  jz      short loc_18002E6B2
0x18002e699  mov     rcx, rbx; pvarg
0x18002e69c  call    cs:__imp_VariantClear
0x18002e6a2  add     rbx, 18h
0x18002e6a6  cmp     rbx, r14
0x18002e6a9  jnz     short loc_18002E699
0x18002e6ab  mov     rax, [rsi]
0x18002e6ae  mov     [rsi+8], rax
0x18002e6b2  cmp     word ptr [rdi], 9
0x18002e6b6  jnz     loc_18002E90F
0x18002e6bc  mov     rbx, [rdi+8]
0x18002e6c0  xor     r13d, r13d
0x18002e6c3  test    rbx, rbx
0x18002e6c6  jz      loc_18002E90F
0x18002e6cc  mov     [rbp+arg_8], rbx
0x18002e6d0  mov     rax, [rbx]
0x18002e6d3  mov     rcx, rbx
0x18002e6d6  mov     rax, [rax+8]
0x18002e6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6df  nop
0x18002e6e0  lea     rcx, [rbp+pvarg]; pvarg
0x18002e6e4  call    cs:__imp_VariantInit
0x18002e6ea  nop
0x18002e6eb  lea     r8, [rbp+pvarg]
0x18002e6ef  lea     rdx, aLength; "length"
0x18002e6f6  lea     rcx, [rbp+arg_8]
0x18002e6fa  call    ?GetPropertyByName@?$CComPtr@UIDispatch@@@ATL@@QEAAJPEBGPEAUtagVARIANT@@@Z; ATL::CComPtr<IDispatch>::GetPropertyByName(ushort const *,tagVARIANT *)
0x18002e6ff  mov     edi, eax
0x18002e701  test    eax, eax
0x18002e703  jnz     loc_18002E8E6
0x18002e709  mov     r14, qword ptr [rbp+pvarg+8]
0x18002e70d  movzx   eax, word ptr [rbp+pvarg]
0x18002e711  cmp     ax, 3
0x18002e715  jnz     short loc_18002E71D
0x18002e717  test    r14w, r14w
0x18002e71b  jns     short loc_18002E730
0x18002e71d  cmp     ax, 14h
0x18002e721  jnz     loc_18002E8C4
0x18002e727  test    r14, r14
0x18002e72a  js      loc_18002E8C4
0x18002e730  cmp     ax, 3
0x18002e734  jnz     short loc_18002E73A
0x18002e736  movsx   r14, r14w
0x18002e73a  mov     [rbp+arg_0], r14
0x18002e73e  mov     rax, [rsi+10h]
0x18002e742  sub     rax, [rsi]
0x18002e745  sar     rax, 3
0x18002e749  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18002e753  imul    rax, rcx
0x18002e757  cmp     r14, rax
0x18002e75a  jbe     short loc_18002E77C
0x18002e75c  mov     rax, 0AAAAAAAAAAAAAAAh
0x18002e766  cmp     r14, rax
0x18002e769  ja      loc_18002E93C
0x18002e76f  lea     rdx, [rbp+arg_0]
0x18002e773  mov     rcx, rsi
0x18002e776  call    ??$_Reallocate@$0A@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAXAEA_K@Z; std::vector<ATL::CComVariant>::_Reallocate<0>(unsigned __int64 &)
0x18002e77b  nop
0x18002e77c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002e783  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002e78a  mov     rax, [rax+18h]
0x18002e78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e793  lea     rdi, [rax+18h]
0x18002e797  mov     [rbp+arg_0], rdi
0x18002e79b  mov     r12, r13
0x18002e79e  test    r14, r14
0x18002e7a1  jz      loc_18002E834
0x18002e7a7  lea     rcx, [rbp+pvargSrc]; pvarg
0x18002e7ab  call    cs:__imp_VariantInit
0x18002e7b1  nop
0x18002e7b2  mov     rdi, [rsi+8]
0x18002e7b6  cmp     rdi, [rsi+10h]
0x18002e7ba  jz      short loc_18002E7DC
0x18002e7bc  mov     [rdi], r13w
0x18002e7c0  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18002e7c4  mov     rcx, rdi; pvargDest
0x18002e7c7  call    cs:__imp_VariantCopy
0x18002e7cd  test    eax, eax
0x18002e7cf  js      loc_18002E92C
0x18002e7d5  add     qword ptr [rsi+8], 18h
0x18002e7da  jmp     short loc_18002E7EC
0x18002e7dc  lea     r8, [rbp+pvargSrc]
0x18002e7e0  mov     rdx, rdi
0x18002e7e3  mov     rcx, rsi
0x18002e7e6  call    ??$_Emplace_reallocate@VCComVariant@ATL@@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAPEAVCComVariant@ATL@@QEAV23@$$QEAV23@@Z; std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(ATL::CComVariant * const,ATL::CComVariant &&)
0x18002e7eb  nop
0x18002e7ec  lea     rcx, [rbp+pvargSrc]; pvarg
0x18002e7f0  call    cs:__imp_VariantClear
0x18002e7f6  mov     r8, r12
0x18002e7f9  lea     rdx, aIu; "%Iu"
0x18002e800  lea     rcx, [rbp+arg_0]
0x18002e804  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18002e809  mov     r8, [rsi+8]
0x18002e80d  sub     r8, 18h
0x18002e811  mov     rdi, [rbp+arg_0]
0x18002e815  mov     rdx, rdi
0x18002e818  lea     rcx, [rbp+arg_8]
0x18002e81c  call    ?GetPropertyByName@?$CComPtr@UIDispatch@@@ATL@@QEAAJPEBGPEAUtagVARIANT@@@Z; ATL::CComPtr<IDispatch>::GetPropertyByName(ushort const *,tagVARIANT *)
0x18002e821  mov     r15d, eax
0x18002e824  test    eax, eax
0x18002e826  jnz     short loc_18002E877
0x18002e828  inc     r12
0x18002e82b  cmp     r12, r14
0x18002e82e  jb      loc_18002E7A7
0x18002e834  lea     rdx, [rdi-18h]
0x18002e838  or      eax, 0FFFFFFFFh
0x18002e83b  lock xadd [rdx+10h], eax
0x18002e840  sub     eax, 1
0x18002e843  jg      short loc_18002E855
0x18002e845  mov     rcx, [rdx]
0x18002e848  mov     rax, [rcx]
0x18002e84b  mov     rax, [rax+8]
0x18002e84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e854  nop
0x18002e855  lea     rcx, [rbp+pvarg]; pvarg
0x18002e859  call    cs:__imp_VariantClear
0x18002e85f  nop
0x18002e860  mov     rax, [rbx]
0x18002e863  mov     rcx, rbx
0x18002e866  mov     rax, [rax+10h]
0x18002e86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e86f  nop
0x18002e870  xor     eax, eax
0x18002e872  jmp     loc_18002E914
0x18002e877  mov     eax, 80004005h
0x18002e87c  test    r15d, r15d
0x18002e87f  cmovns  r15d, eax
0x18002e883  lea     rdx, [rdi-18h]
0x18002e887  or      eax, 0FFFFFFFFh
0x18002e88a  lock xadd [rdx+10h], eax
0x18002e88f  sub     eax, 1
0x18002e892  jg      short loc_18002E8A4
0x18002e894  mov     rcx, [rdx]
0x18002e897  mov     rax, [rcx]
0x18002e89a  mov     rax, [rax+8]
0x18002e89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8a3  nop
0x18002e8a4  lea     rcx, [rbp+pvarg]; pvarg
0x18002e8a8  call    cs:__imp_VariantClear
0x18002e8ae  nop
0x18002e8af  mov     rcx, [rbx]
0x18002e8b2  mov     rax, [rcx+10h]
0x18002e8b6  mov     rcx, rbx
0x18002e8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8be  nop
0x18002e8bf  mov     eax, r15d
0x18002e8c2  jmp     short loc_18002E914
0x18002e8c4  lea     rcx, [rbp+pvarg]; pvarg
0x18002e8c8  call    cs:__imp_VariantClear
0x18002e8ce  nop
0x18002e8cf  mov     rax, [rbx]
0x18002e8d2  mov     rcx, rbx
0x18002e8d5  mov     rax, [rax+10h]
0x18002e8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8de  nop
0x18002e8df  mov     eax, 80004005h
0x18002e8e4  jmp     short loc_18002E914
0x18002e8e6  mov     eax, 80004005h
0x18002e8eb  test    edi, edi
0x18002e8ed  cmovns  edi, eax
0x18002e8f0  lea     rcx, [rbp+pvarg]; pvarg
0x18002e8f4  call    cs:__imp_VariantClear
0x18002e8fa  nop
0x18002e8fb  mov     rcx, [rbx]
0x18002e8fe  mov     rax, [rcx+10h]
0x18002e902  mov     rcx, rbx
0x18002e905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e90a  nop
0x18002e90b  mov     eax, edi
0x18002e90d  jmp     short loc_18002E914
0x18002e90f  mov     eax, 80070057h
0x18002e914  mov     rbx, [rsp+50h+arg_10]
0x18002e91c  add     rsp, 50h
0x18002e920  pop     r15
0x18002e922  pop     r14
0x18002e924  pop     r13
0x18002e926  pop     r12
0x18002e928  pop     rdi
0x18002e929  pop     rsi
0x18002e92a  pop     rbp
0x18002e92b  retn
0x18002e92c  mov     word ptr [rdi], 0Ah
0x18002e931  mov     [rdi+8], eax
0x18002e934  mov     ecx, eax; int
0x18002e936  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e93c  call    ?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ; std::vector<ATL::CComVariant>::_Xlength(void)
```
