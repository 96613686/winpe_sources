# DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>> * *)

- ea: `0x18000ac30`
- end: `0x18000acc7`
- name: `?Create@?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, int, DirectUI::ClassInfoBase **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000add0`

## callees

- `0x180004278`
- `0x180005b98`
- `0x18000ac30`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000ac95`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000ac95`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000ac60`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000ac60`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::Create(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        DirectUI::ClassInfoBase **a6)
{
  DirectUI::ClassInfoBase *v6; // rax
  DirectUI::ClassInfoBase *v7; // rbx
  int v8; // edi

  *a6 = 0;
  v6 = (DirectUI::ClassInfoBase *)DirectUI::HAllocAndZero((DirectUI *)0x10, a2);
  v7 = v6;
  if ( v6 )
  {
    DirectUI::ClassInfoBase::ClassInfoBase(v6);
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, (HINSTANCE)&_ImageBase, L"CElementWithIUnknown", 0, 0, 0);
    if ( v8 < 0 )
      DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(v7);
    else
      *a6 = v7;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ac30  mov     [rsp+arg_0], rbx
0x18000ac35  mov     [rsp+arg_8], rsi
0x18000ac3a  push    rdi
0x18000ac3b  sub     rsp, 30h
0x18000ac3f  mov     rsi, [rsp+38h+arg_28]
0x18000ac44  mov     ecx, 10h; this
0x18000ac49  mov     qword ptr [rsi], 0
0x18000ac50  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000ac55  mov     rbx, rax
0x18000ac58  test    rax, rax
0x18000ac5b  jz      short loc_18000ACB0
0x18000ac5d  mov     rcx, rax
0x18000ac60  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x18000ac66  lea     rax, ??_7?$ClassInfo@VCElementWithIUnknown@@VElement@DirectUI@@V?$StandardCreator@VCElementWithIUnknown@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CElementWithIUnknown,DirectUI::Element,DirectUI::StandardCreator<CElementWithIUnknown>>::`vftable'
0x18000ac6d  mov     [rsp+38h+var_10], 0
0x18000ac75  xor     r9d, r9d
0x18000ac78  mov     [rbx], rax
0x18000ac7b  lea     r8, aCelementwithiu; "CElementWithIUnknown"
0x18000ac82  mov     [rsp+38h+var_18], 0
0x18000ac8b  lea     rdx, __ImageBase
0x18000ac92  mov     rcx, rbx
0x18000ac95  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18000ac9b  mov     edi, eax
0x18000ac9d  test    eax, eax
0x18000ac9f  js      short loc_18000ACA6
0x18000aca1  mov     [rsi], rbx
0x18000aca4  jmp     short loc_18000ACB5
0x18000aca6  mov     rcx, rbx; this
0x18000aca9  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x18000acae  jmp     short loc_18000ACB5
0x18000acb0  mov     edi, 8007000Eh
0x18000acb5  mov     rbx, [rsp+38h+arg_0]
0x18000acba  mov     eax, edi
0x18000acbc  mov     rsi, [rsp+38h+arg_8]
0x18000acc1  add     rsp, 30h
0x18000acc5  pop     rdi
0x18000acc6  retn
```
