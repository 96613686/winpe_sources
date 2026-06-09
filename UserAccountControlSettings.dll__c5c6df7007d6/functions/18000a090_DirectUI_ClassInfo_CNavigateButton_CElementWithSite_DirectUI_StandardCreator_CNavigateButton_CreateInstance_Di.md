# DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000a090`
- end: `0x18000a0c3`
- name: `?CreateInstance@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `51`
- prototype: `__int64 __fastcall(__int64, struct DirectUI::Element *, unsigned int *, DirectUI::Element **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009c94`
- `0x18000a090`

## import_xrefs

- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18000a0b0`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18000a0b0`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Element **a4)
{
  int v5; // ebx

  v5 = DirectUI::CreateAndInit<CNavigateButton,int>(a1, a2, a3, a4);
  if ( v5 >= 0 )
    DirectUI::Element::SetActive(*a4, 1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a090  mov     [rsp+arg_0], rbx
0x18000a095  push    rdi
0x18000a096  sub     rsp, 20h
0x18000a09a  mov     rdi, r9
0x18000a09d  call    ??$CreateAndInit@VCNavigateButton@@H@DirectUI@@YAJHPEAVElement@0@PEAKPEAPEAV10@@Z; DirectUI::CreateAndInit<CNavigateButton,int>(int,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000a0a2  mov     ebx, eax
0x18000a0a4  test    eax, eax
0x18000a0a6  js      short loc_18000A0B6
0x18000a0a8  mov     rcx, [rdi]
0x18000a0ab  mov     edx, 1
0x18000a0b0  call    cs:__imp_?SetActive@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetActive(int)
0x18000a0b6  mov     eax, ebx
0x18000a0b8  mov     rbx, [rsp+28h+arg_0]
0x18000a0bd  add     rsp, 20h
0x18000a0c1  pop     rdi
0x18000a0c2  retn
```
