# DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> * *)

- ea: `0x18000acd0`
- end: `0x18000ad67`
- name: `?Create@?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, int, DirectUI::ClassInfoBase **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aef8`

## callees

- `0x180004278`
- `0x180005b98`
- `0x18000acd0`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000ad35`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18000ad35`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000ad00`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18000ad00`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, (HINSTANCE)&_ImageBase, L"CElementWithSite", 0, 0, 0);
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
0x18000acd0  mov     [rsp+arg_0], rbx
0x18000acd5  mov     [rsp+arg_8], rsi
0x18000acda  push    rdi
0x18000acdb  sub     rsp, 30h
0x18000acdf  mov     rsi, [rsp+38h+arg_28]
0x18000ace4  mov     ecx, 10h; this
0x18000ace9  mov     qword ptr [rsi], 0
0x18000acf0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000acf5  mov     rbx, rax
0x18000acf8  test    rax, rax
0x18000acfb  jz      short loc_18000AD50
0x18000acfd  mov     rcx, rax
0x18000ad00  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x18000ad06  lea     rax, ??_7?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>::`vftable'
0x18000ad0d  mov     [rsp+38h+var_10], 0
0x18000ad15  xor     r9d, r9d
0x18000ad18  mov     [rbx], rax
0x18000ad1b  lea     r8, aCelementwithsi; "CElementWithSite"
0x18000ad22  mov     [rsp+38h+var_18], 0
0x18000ad2b  lea     rdx, __ImageBase
0x18000ad32  mov     rcx, rbx
0x18000ad35  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18000ad3b  mov     edi, eax
0x18000ad3d  test    eax, eax
0x18000ad3f  js      short loc_18000AD46
0x18000ad41  mov     [rsi], rbx
0x18000ad44  jmp     short loc_18000AD55
0x18000ad46  mov     rcx, rbx; this
0x18000ad49  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x18000ad4e  jmp     short loc_18000AD55
0x18000ad50  mov     edi, 8007000Eh
0x18000ad55  mov     rbx, [rsp+38h+arg_0]
0x18000ad5a  mov     eax, edi
0x18000ad5c  mov     rsi, [rsp+38h+arg_8]
0x18000ad61  add     rsp, 30h
0x18000ad65  pop     rdi
0x18000ad66  retn
```
