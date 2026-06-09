# DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>> * *)

- ea: `0x180004f10`
- end: `0x180004fa7`
- name: `?Create@?$ClassInfo@VCElevatedCPLPage@@VElement@DirectUI@@V?$StandardCreator@VCElevatedCPLPage@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, int, DirectUI::ClassInfoBase **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000655c`

## callees

- `0x180004278`
- `0x180004f10`
- `0x180005b98`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180004f75`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180004f75`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180004f40`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180004f40`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, (HINSTANCE)&_ImageBase, L"ElevatedCPLPage", 0, 0, 0);
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
0x180004f10  mov     [rsp+arg_0], rbx
0x180004f15  mov     [rsp+arg_8], rsi
0x180004f1a  push    rdi
0x180004f1b  sub     rsp, 30h
0x180004f1f  mov     rsi, [rsp+38h+arg_28]
0x180004f24  mov     ecx, 10h; this
0x180004f29  mov     qword ptr [rsi], 0
0x180004f30  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180004f35  mov     rbx, rax
0x180004f38  test    rax, rax
0x180004f3b  jz      short loc_180004F90
0x180004f3d  mov     rcx, rax
0x180004f40  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180004f46  lea     rax, ??_7?$ClassInfo@VCElevatedCPLPage@@VElement@DirectUI@@V?$StandardCreator@VCElevatedCPLPage@@@3@@DirectUI@@6B@; const DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::`vftable'
0x180004f4d  mov     [rsp+38h+var_10], 0
0x180004f55  xor     r9d, r9d
0x180004f58  mov     [rbx], rax
0x180004f5b  lea     r8, aElevatedcplpag; "ElevatedCPLPage"
0x180004f62  mov     [rsp+38h+var_18], 0
0x180004f6b  lea     rdx, __ImageBase
0x180004f72  mov     rcx, rbx
0x180004f75  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180004f7b  mov     edi, eax
0x180004f7d  test    eax, eax
0x180004f7f  js      short loc_180004F86
0x180004f81  mov     [rsi], rbx
0x180004f84  jmp     short loc_180004F95
0x180004f86  mov     rcx, rbx; this
0x180004f89  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x180004f8e  jmp     short loc_180004F95
0x180004f90  mov     edi, 8007000Eh
0x180004f95  mov     rbx, [rsp+38h+arg_0]
0x180004f9a  mov     eax, edi
0x180004f9c  mov     rsi, [rsp+38h+arg_8]
0x180004fa1  add     rsp, 30h
0x180004fa5  pop     rdi
0x180004fa6  retn
```
