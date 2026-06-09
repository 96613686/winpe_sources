# DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::Create(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint,DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>> * *)

- ea: `0x18001c4a0`
- end: `0x18001c537`
- name: `?Create@?$ClassInfo@VAccessibilityCplPage@@VCElementWithSite@@V?$StandardCreator@VAccessibilityCplPage@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@IPEAPEAV12@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c914`

## callees

- `0x18000314c`
- `0x18001c288`
- `0x18001c4a0`

## import_xrefs

- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18001c4d0`
- `DUI70!??0ClassInfoBase@DirectUI@@QEAA@XZ` at `0x18001c4d0`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18001c505`
- `DUI70!?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z` at `0x18001c505`

## string_xrefs

- `0x18001c4eb`: `AccessibilityCplPage`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::Create(
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
    *(_QWORD *)v7 = &DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::`vftable';
    v8 = DirectUI::ClassInfoBase::Initialize(v7, &_ImageBase, L"AccessibilityCplPage", 0, 0, 0);
    if ( v8 < 0 )
      DirectUI::HDelete<DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>>(v7);
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
0x18001c4a0  mov     [rsp+arg_0], rbx
0x18001c4a5  mov     [rsp+arg_8], rsi
0x18001c4aa  push    rdi
0x18001c4ab  sub     rsp, 30h
0x18001c4af  mov     rsi, [rsp+38h+arg_28]
0x18001c4b4  mov     ecx, 10h; this
0x18001c4b9  mov     qword ptr [rsi], 0
0x18001c4c0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001c4c5  mov     rbx, rax
0x18001c4c8  test    rax, rax
0x18001c4cb  jz      short loc_18001C520
0x18001c4cd  mov     rcx, rax
0x18001c4d0  call    cs:__imp_??0ClassInfoBase@DirectUI@@QEAA@XZ; DirectUI::ClassInfoBase::ClassInfoBase(void)
0x18001c4d6  lea     rax, ??_7?$ClassInfo@VAccessibilityCplPage@@VCElementWithSite@@V?$StandardCreator@VAccessibilityCplPage@@@DirectUI@@@DirectUI@@6B@; const DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>::`vftable'
0x18001c4dd  mov     [rsp+38h+var_10], 0
0x18001c4e5  xor     r9d, r9d
0x18001c4e8  mov     [rbx], rax
0x18001c4eb  lea     r8, aAccessibilityc_1; "AccessibilityCplPage"
0x18001c4f2  mov     [rsp+38h+var_18], 0
0x18001c4fb  lea     rdx, __ImageBase
0x18001c502  mov     rcx, rbx
0x18001c505  call    cs:__imp_?Initialize@ClassInfoBase@DirectUI@@QEAAJPEAUHINSTANCE__@@PEBG_NPEBQEBUPropertyInfo@2@I@Z; DirectUI::ClassInfoBase::Initialize(HINSTANCE__ *,ushort const *,bool,DirectUI::PropertyInfo const * const *,uint)
0x18001c50b  mov     edi, eax
0x18001c50d  test    eax, eax
0x18001c50f  js      short loc_18001C516
0x18001c511  mov     [rsi], rbx
0x18001c514  jmp     short loc_18001C525
0x18001c516  mov     rcx, rbx; this
0x18001c519  call    ??$HDelete@V?$ClassInfo@VAccessibilityCplPage@@VCElementWithSite@@V?$StandardCreator@VAccessibilityCplPage@@@DirectUI@@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VAccessibilityCplPage@@VCElementWithSite@@V?$StandardCreator@VAccessibilityCplPage@@@DirectUI@@@0@@Z; DirectUI::HDelete<DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>>>(DirectUI::ClassInfo<AccessibilityCplPage,CElementWithSite,DirectUI::StandardCreator<AccessibilityCplPage>> *)
0x18001c51e  jmp     short loc_18001C525
0x18001c520  mov     edi, 8007000Eh
0x18001c525  mov     rbx, [rsp+38h+arg_0]
0x18001c52a  mov     eax, edi
0x18001c52c  mov     rsi, [rsp+38h+arg_8]
0x18001c531  add     rsp, 30h
0x18001c535  pop     rdi
0x18001c536  retn
```
