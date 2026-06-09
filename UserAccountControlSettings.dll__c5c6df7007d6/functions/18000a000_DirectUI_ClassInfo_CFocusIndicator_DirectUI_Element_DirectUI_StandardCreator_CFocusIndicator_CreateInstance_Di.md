# DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000a000`
- end: `0x18000a07f`
- name: `?CreateInstance@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `127`
- prototype: `__int64 __fastcall(__int64, struct DirectUI::Element *, unsigned int *, DirectUI::Element **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005b98`
- `0x18000a000`

## import_xrefs

- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18000a05d`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18000a05d`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18000a049`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18000a049`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a067`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a067`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x18000a02e`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x18000a02e`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  DirectUI::Element *v7; // rax
  DirectUI::Element *v8; // rbx
  int v9; // edi

  *a4 = 0;
  v7 = (DirectUI::Element *)DirectUI::HAllocAndZero((DirectUI *)0xC8, (unsigned __int64)a2);
  v8 = v7;
  if ( v7 )
  {
    DirectUI::Element::Element(v7);
    *(_QWORD *)v8 = &CFocusIndicator::`vftable';
    v9 = DirectUI::Element::Initialize(v8, 0, a2, a3);
    if ( v9 < 0 )
    {
      DirectUI::Element::Destroy(v8, 0);
    }
    else
    {
      *a4 = v8;
      return (unsigned int)DirectUI::Element::SetActive(v8, 0);
    }
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
0x18000a000  push    rbx
0x18000a002  push    rbp
0x18000a003  push    rsi
0x18000a004  push    rdi
0x18000a005  sub     rsp, 28h
0x18000a009  mov     ecx, 0C8h; this
0x18000a00e  mov     qword ptr [r9], 0
0x18000a015  mov     rsi, r9
0x18000a018  mov     rdi, r8
0x18000a01b  mov     rbp, rdx
0x18000a01e  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000a023  mov     rbx, rax
0x18000a026  test    rax, rax
0x18000a029  jz      short loc_18000A06F
0x18000a02b  mov     rcx, rax
0x18000a02e  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x18000a034  lea     rax, ??_7CFocusIndicator@@6B@; const CFocusIndicator::`vftable'
0x18000a03b  mov     r9, rdi
0x18000a03e  mov     r8, rbp
0x18000a041  mov     [rbx], rax
0x18000a044  xor     edx, edx
0x18000a046  mov     rcx, rbx
0x18000a049  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18000a04f  xor     edx, edx
0x18000a051  mov     rcx, rbx
0x18000a054  mov     edi, eax
0x18000a056  test    eax, eax
0x18000a058  js      short loc_18000A067
0x18000a05a  mov     [rsi], rbx
0x18000a05d  call    cs:__imp_?SetActive@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetActive(int)
0x18000a063  mov     edi, eax
0x18000a065  jmp     short loc_18000A074
0x18000a067  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000a06d  jmp     short loc_18000A074
0x18000a06f  mov     edi, 8007000Eh
0x18000a074  mov     eax, edi
0x18000a076  add     rsp, 28h
0x18000a07a  pop     rdi
0x18000a07b  pop     rsi
0x18000a07c  pop     rbp
0x18000a07d  pop     rbx
0x18000a07e  retn
```
