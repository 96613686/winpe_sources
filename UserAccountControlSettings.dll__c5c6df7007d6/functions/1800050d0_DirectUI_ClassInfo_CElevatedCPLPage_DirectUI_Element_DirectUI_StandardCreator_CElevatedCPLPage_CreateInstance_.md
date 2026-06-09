# DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800050d0`
- end: `0x180005147`
- name: `?CreateInstance@?$ClassInfo@VCElevatedCPLPage@@VElement@DirectUI@@V?$StandardCreator@VCElevatedCPLPage@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `119`
- prototype: `__int64 __fastcall(__int64, struct DirectUI::Element *, unsigned int *, DirectUI::Element **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800050d0`
- `0x180005b98`

## import_xrefs

- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180005119`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180005119`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000512f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000512f`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x1800050fe`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x1800050fe`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  DirectUI::Element *v7; // rax
  DirectUI::Element *v8; // rbx
  int v9; // edi

  *a4 = 0;
  v7 = (DirectUI::Element *)DirectUI::HAllocAndZero((DirectUI *)0xD0, (unsigned __int64)a2);
  v8 = v7;
  if ( v7 )
  {
    DirectUI::Element::Element(v7);
    *(_QWORD *)v8 = &CElevatedCPLPage::`vftable';
    v9 = DirectUI::Element::Initialize(v8, 0, a2, a3);
    if ( v9 < 0 )
      DirectUI::Element::Destroy(v8, 0);
    else
      *a4 = v8;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800050d0  push    rbx
0x1800050d2  push    rbp
0x1800050d3  push    rsi
0x1800050d4  push    rdi
0x1800050d5  sub     rsp, 28h
0x1800050d9  mov     ecx, 0D0h; this
0x1800050de  mov     qword ptr [r9], 0
0x1800050e5  mov     rsi, r9
0x1800050e8  mov     rdi, r8
0x1800050eb  mov     rbp, rdx
0x1800050ee  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800050f3  mov     rbx, rax
0x1800050f6  test    rax, rax
0x1800050f9  jz      short loc_180005137
0x1800050fb  mov     rcx, rax
0x1800050fe  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x180005104  lea     rax, ??_7CElevatedCPLPage@@6B@; const CElevatedCPLPage::`vftable'
0x18000510b  mov     r9, rdi
0x18000510e  mov     r8, rbp
0x180005111  mov     [rbx], rax
0x180005114  xor     edx, edx
0x180005116  mov     rcx, rbx
0x180005119  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18000511f  mov     edi, eax
0x180005121  test    eax, eax
0x180005123  js      short loc_18000512A
0x180005125  mov     [rsi], rbx
0x180005128  jmp     short loc_18000513C
0x18000512a  xor     edx, edx
0x18000512c  mov     rcx, rbx
0x18000512f  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180005135  jmp     short loc_18000513C
0x180005137  mov     edi, 8007000Eh
0x18000513c  mov     eax, edi
0x18000513e  add     rsp, 28h
0x180005142  pop     rdi
0x180005143  pop     rsi
0x180005144  pop     rbp
0x180005145  pop     rbx
0x180005146  retn
```
