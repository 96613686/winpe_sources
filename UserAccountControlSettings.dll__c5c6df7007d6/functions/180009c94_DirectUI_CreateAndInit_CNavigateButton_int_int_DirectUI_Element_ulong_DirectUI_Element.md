# DirectUI::CreateAndInit<CNavigateButton,int>(int,DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180009c94`
- end: `0x180009d27`
- name: `??$CreateAndInit@VCNavigateButton@@H@DirectUI@@YAJHPEAVElement@0@PEAKPEAPEAV10@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64, struct DirectUI::Element *, unsigned int *, DirectUI::Element **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a090`

## callees

- `0x180005b98`
- `0x180009c94`

## import_xrefs

- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180009cf9`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x180009cf9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009d0f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180009d0f`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x180009cc2`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x180009cc2`

## pseudocode

```c
__int64 __fastcall DirectUI::CreateAndInit<CNavigateButton,int>(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  DirectUI::Element *v7; // rax
  DirectUI::Element *v8; // rbx
  int v9; // edi

  *a4 = 0;
  v7 = (DirectUI::Element *)DirectUI::HAllocAndZero((DirectUI *)0xE0, (unsigned __int64)a2);
  v8 = v7;
  if ( v7 )
  {
    DirectUI::Element::Element(v7);
    *(_QWORD *)v8 = &CNavigateButton::`vftable'{for `DirectUI::Element'};
    *((_QWORD *)v8 + 25) = &CElementWithSite::`vftable'{for `IUnknown'};
    *((_QWORD *)v8 + 26) = &CElementWithSite::`vftable';
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
0x180009c94  push    rbx
0x180009c96  push    rbp
0x180009c97  push    rsi
0x180009c98  push    rdi
0x180009c99  sub     rsp, 28h
0x180009c9d  mov     ecx, 0E0h; this
0x180009ca2  mov     qword ptr [r9], 0
0x180009ca9  mov     rsi, r9
0x180009cac  mov     rdi, r8
0x180009caf  mov     rbp, rdx
0x180009cb2  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180009cb7  mov     rbx, rax
0x180009cba  test    rax, rax
0x180009cbd  jz      short loc_180009D17
0x180009cbf  mov     rcx, rax
0x180009cc2  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x180009cc8  lea     rax, ??_7CNavigateButton@@6BElement@DirectUI@@@; const CNavigateButton::`vftable'{for `DirectUI::Element'}
0x180009ccf  mov     r9, rdi
0x180009cd2  mov     [rbx], rax
0x180009cd5  mov     r8, rbp
0x180009cd8  lea     rax, ??_7CElementWithSite@@6BIUnknown@@@; const CElementWithSite::`vftable'{for `IUnknown'}
0x180009cdf  xor     edx, edx
0x180009ce1  mov     [rbx+0C8h], rax
0x180009ce8  mov     rcx, rbx
0x180009ceb  lea     rax, ??_7CElementWithSite@@6B@; const CElementWithSite::`vftable'
0x180009cf2  mov     [rbx+0D0h], rax
0x180009cf9  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x180009cff  mov     edi, eax
0x180009d01  test    eax, eax
0x180009d03  js      short loc_180009D0A
0x180009d05  mov     [rsi], rbx
0x180009d08  jmp     short loc_180009D1C
0x180009d0a  xor     edx, edx
0x180009d0c  mov     rcx, rbx
0x180009d0f  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180009d15  jmp     short loc_180009D1C
0x180009d17  mov     edi, 8007000Eh
0x180009d1c  mov     eax, edi
0x180009d1e  add     rsp, 28h
0x180009d22  pop     rdi
0x180009d23  pop     rsi
0x180009d24  pop     rbp
0x180009d25  pop     rbx
0x180009d26  retn
```
