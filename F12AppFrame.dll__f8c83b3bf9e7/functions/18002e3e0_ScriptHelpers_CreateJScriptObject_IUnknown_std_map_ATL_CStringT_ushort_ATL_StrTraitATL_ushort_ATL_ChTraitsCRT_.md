# ScriptHelpers::CreateJScriptObject(IUnknown *,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>> const &,ATL::CComVariant &)

- ea: `0x18002e3e0`
- end: `0x18002e4c2`
- name: `?CreateJScriptObject@ScriptHelpers@@YAJPEAUIUnknown@@AEBV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@AEAVCComVariant@ATL@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, VARIANTARG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007f08`

## callees

- `0x180003858`
- `0x180003880`
- `0x1800045b4`
- `0x18002e270`
- `0x18002e3e0`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002e3f9`
- `OLEAUT32!__imp_VariantInit` at `0x18002e3f9`
- `OLEAUT32!__imp_VariantClear` at `0x18002e479`
- `OLEAUT32!__imp_VariantClear` at `0x18002e4a1`
- `OLEAUT32!__imp_VariantClear` at `0x18002e479`
- `OLEAUT32!__imp_VariantClear` at `0x18002e4a1`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e493`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e493`

## pseudocode

```c
__int64 __fastcall ScriptHelpers::CreateJScriptObject(
        void (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        VARIANTARG *a3)
{
  int JScriptItem; // ebx
  HRESULT v8; // eax
  VARIANTARG pvarg; // [rsp+28h] [rbp-20h] BYREF
  wchar_t *v10; // [rsp+88h] [rbp+40h] BYREF

  VariantInit(&pvarg);
  v10 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &v10,
          (__int64)L"Object") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v10, L"Object", 6);
  JScriptItem = ScriptHelpers::CreateJScriptItem(a1, (__int64 *)&v10, a2, (__int64)&pvarg);
  if ( JScriptItem )
  {
    if ( JScriptItem >= 0 )
      JScriptItem = -2147467259;
    VariantClear(&pvarg);
    return (unsigned int)JScriptItem;
  }
  else
  {
    if ( a3 != &pvarg )
    {
      v8 = VariantCopy(a3, &pvarg);
      if ( v8 < 0 )
      {
        a3->vt = 10;
        a3->lVal = v8;
        ATL::AtlThrowImpl(v8);
      }
    }
    VariantClear(&pvarg);
    return 0;
  }
}

```

## disassembly

```asm
0x18002e3e0  push    rbp
0x18002e3e2  push    rbx
0x18002e3e3  push    rsi
0x18002e3e4  push    rdi
0x18002e3e5  mov     rbp, rsp
0x18002e3e8  sub     rsp, 48h
0x18002e3ec  mov     rdi, r8
0x18002e3ef  mov     rbx, rdx
0x18002e3f2  mov     rsi, rcx
0x18002e3f5  lea     rcx, [rbp+pvarg]; pvarg
0x18002e3f9  call    cs:__imp_VariantInit
0x18002e3ff  nop
0x18002e400  lea     rax, [rbp+arg_18]
0x18002e404  mov     [rbp+var_28], rax
0x18002e408  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002e40f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002e416  mov     rax, [rax+18h]
0x18002e41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e41f  add     rax, 18h
0x18002e423  mov     [rbp+arg_18], rax
0x18002e427  lea     rdx, aObject; "Object"
0x18002e42e  lea     rcx, [rbp+arg_18]
0x18002e432  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18002e437  test    al, al
0x18002e439  jnz     short loc_18002E452
0x18002e43b  mov     r8d, 6
0x18002e441  lea     rdx, aObject; "Object"
0x18002e448  lea     rcx, [rbp+arg_18]
0x18002e44c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002e451  nop
0x18002e452  lea     r9, [rbp+pvarg]
0x18002e456  mov     r8, rbx
0x18002e459  lea     rdx, [rbp+arg_18]
0x18002e45d  mov     rcx, rsi
0x18002e460  call    ?CreateJScriptItem@ScriptHelpers@@YAJPEAUIUnknown@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@AEAVCComVariant@4@@Z; ScriptHelpers::CreateJScriptItem(IUnknown *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant> const &,ATL::CComVariant &)
0x18002e465  mov     ebx, eax
0x18002e467  test    eax, eax
0x18002e469  jz      short loc_18002E483
0x18002e46b  mov     eax, 80004005h
0x18002e470  test    ebx, ebx
0x18002e472  cmovns  ebx, eax
0x18002e475  lea     rcx, [rbp+pvarg]; pvarg
0x18002e479  call    cs:__imp_VariantClear
0x18002e47f  mov     eax, ebx
0x18002e481  jmp     short loc_18002E4A9
0x18002e483  lea     rax, [rbp+pvarg]
0x18002e487  cmp     rdi, rax
0x18002e48a  jz      short loc_18002E49D
0x18002e48c  lea     rdx, [rbp+pvarg]; pvargSrc
0x18002e490  mov     rcx, rdi; pvargDest
0x18002e493  call    cs:__imp_VariantCopy
0x18002e499  test    eax, eax
0x18002e49b  js      short loc_18002E4B2
0x18002e49d  lea     rcx, [rbp+pvarg]; pvarg
0x18002e4a1  call    cs:__imp_VariantClear
0x18002e4a7  xor     eax, eax
0x18002e4a9  add     rsp, 48h
0x18002e4ad  pop     rdi
0x18002e4ae  pop     rsi
0x18002e4af  pop     rbx
0x18002e4b0  pop     rbp
0x18002e4b1  retn
0x18002e4b2  mov     word ptr [rdi], 0Ah
0x18002e4b7  mov     [rdi+8], eax
0x18002e4ba  mov     ecx, eax; int
0x18002e4bc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
