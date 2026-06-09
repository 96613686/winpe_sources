# DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>> * *)

- ea: `0x180009ec0`
- end: `0x180009f5a`
- name: `?Create@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `154`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, int, DirectUI::ClassInfoBase **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5c4`

## callees

- `0x180004278`
- `0x180005b98`
- `0x180009ec0`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180009f28`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180009f28`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180009ef0`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180009ef0`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(
           v7,
           (HINSTANCE)&_ImageBase,
           L"FocusIndicator",
           0,
           (const struct DirectUI::PropertyInfo *const *)off_18000DB70,
           1u);
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
0x180009ec0  mov     [rsp+arg_0], rbx
0x180009ec5  mov     [rsp+arg_8], rsi
0x180009eca  push    rdi
0x180009ecb  sub     rsp, 30h
0x180009ecf  mov     rsi, [rsp+38h+arg_28]
0x180009ed4  mov     ecx, 10h; this
0x180009ed9  mov     qword ptr [rsi], 0
0x180009ee0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180009ee5  mov     rbx, rax
0x180009ee8  test    rax, rax
0x180009eeb  jz      short loc_180009F43
0x180009eed  mov     rcx, rax
0x180009ef0  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180009ef6  lea     rax, ??_7?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::`vftable'
0x180009efd  mov     [rsp+38h+var_10], 1
0x180009f05  mov     [rbx], rax
0x180009f08  lea     r8, aFocusindicator; "FocusIndicator"
0x180009f0f  lea     rax, off_18000DB70
0x180009f16  xor     r9d, r9d
0x180009f19  lea     rdx, __ImageBase
0x180009f20  mov     [rsp+38h+var_18], rax
0x180009f25  mov     rcx, rbx
0x180009f28  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180009f2e  mov     edi, eax
0x180009f30  test    eax, eax
0x180009f32  js      short loc_180009F39
0x180009f34  mov     [rsi], rbx
0x180009f37  jmp     short loc_180009F48
0x180009f39  mov     rcx, rbx; this
0x180009f3c  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x180009f41  jmp     short loc_180009F48
0x180009f43  mov     edi, 8007000Eh
0x180009f48  mov     rbx, [rsp+38h+arg_0]
0x180009f4d  mov     eax, edi
0x180009f4f  mov     rsi, [rsp+38h+arg_8]
0x180009f54  add     rsp, 30h
0x180009f58  pop     rdi
0x180009f59  retn
```
