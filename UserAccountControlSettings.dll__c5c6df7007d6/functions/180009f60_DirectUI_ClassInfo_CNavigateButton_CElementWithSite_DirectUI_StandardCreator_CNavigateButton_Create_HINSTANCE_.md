# DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>> * *)

- ea: `0x180009f60`
- end: `0x180009ffa`
- name: `?Create@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `154`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, int, DirectUI::ClassInfoBase **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a6f4`

## callees

- `0x180004278`
- `0x180005b98`
- `0x180009f60`

## import_xrefs

- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180009fc8`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x180009fc8`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180009f90`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x180009f90`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(
           v7,
           (HINSTANCE)&_ImageBase,
           L"NavigateButton",
           0,
           (const struct DirectUI::PropertyInfo *const *)off_18000DB78,
           6u);
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
0x180009f60  mov     [rsp+arg_0], rbx
0x180009f65  mov     [rsp+arg_8], rsi
0x180009f6a  push    rdi
0x180009f6b  sub     rsp, 30h
0x180009f6f  mov     rsi, [rsp+38h+arg_28]
0x180009f74  mov     ecx, 10h; this
0x180009f79  mov     qword ptr [rsi], 0
0x180009f80  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180009f85  mov     rbx, rax
0x180009f88  test    rax, rax
0x180009f8b  jz      short loc_180009FE3
0x180009f8d  mov     rcx, rax
0x180009f90  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x180009f96  lea     rax, ??_7?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::`vftable'
0x180009f9d  mov     [rsp+38h+var_10], 6
0x180009fa5  mov     [rbx], rax
0x180009fa8  lea     r8, aNavigatebutton; "NavigateButton"
0x180009faf  lea     rax, off_18000DB78
0x180009fb6  xor     r9d, r9d
0x180009fb9  lea     rdx, __ImageBase
0x180009fc0  mov     [rsp+38h+var_18], rax
0x180009fc5  mov     rcx, rbx
0x180009fc8  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x180009fce  mov     edi, eax
0x180009fd0  test    eax, eax
0x180009fd2  js      short loc_180009FD9
0x180009fd4  mov     [rsi], rbx
0x180009fd7  jmp     short loc_180009FE8
0x180009fd9  mov     rcx, rbx; this
0x180009fdc  call    ??$HDelete@V?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCElementWithSite@@VCElementWithIUnknown@@V?$StandardCreator@VCElementWithSite@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>>>(DirectUI::ClassInfo<CElementWithSite,CElementWithIUnknown,DirectUI::StandardCreator<CElementWithSite>> *)
0x180009fe1  jmp     short loc_180009FE8
0x180009fe3  mov     edi, 8007000Eh
0x180009fe8  mov     rbx, [rsp+38h+arg_0]
0x180009fed  mov     eax, edi
0x180009fef  mov     rsi, [rsp+38h+arg_8]
0x180009ff4  add     rsp, 30h
0x180009ff8  pop     rdi
0x180009ff9  retn
```
