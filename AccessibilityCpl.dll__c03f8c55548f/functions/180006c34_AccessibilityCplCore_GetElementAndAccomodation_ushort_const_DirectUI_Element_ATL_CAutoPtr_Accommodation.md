# AccessibilityCplCore::GetElementAndAccomodation(ushort const *,DirectUI::Element * &,ATL::CAutoPtr<Accommodation> &)

- ea: `0x180006c34`
- end: `0x180006c98`
- name: `?GetElementAndAccomodation@AccessibilityCplCore@@AEAAHPEBGAEAPEAVElement@DirectUI@@AEAV?$CAutoPtr@VAccommodation@@@ATL@@@Z`
- size: `100`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018768`
- `0x1800187e0`
- `0x180018ea0`
- `0x180018fe8`
- `0x1800196c8`
- `0x180019be4`
- `0x180019e68`
- `0x18001a450`
- `0x18001a4c8`

## callees

- `0x180006c34`
- `0x180020edc`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180006c6b`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180006c6b`
- `DUI70!StrToID` at `0x180006c4e`
- `DUI70!StrToID` at `0x180006c4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180006c5a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180006c5a`

## pseudocode

```c
_BOOL8 __fastcall AccessibilityCplCore::GetElementAndAccomodation(
        __int64 a1,
        const unsigned __int16 *a2,
        DirectUI::Element **a3,
        struct Accommodation **a4)
{
  DirectUI::Element *v4; // rbx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rax
  struct Accommodation *v10; // rax

  v4 = *(DirectUI::Element **)(a1 + 96);
  v8 = StrToID(a2);
  Descendent = DirectUI::Element::FindDescendent(v4, v8);
  *a3 = Descendent;
  if ( !Descendent || !DirectUI::Element::GetVisible(Descendent) )
    return 0;
  v10 = Accommodation::Open(a2);
  *a4 = v10;
  return v10 != 0;
}

```

## disassembly

```asm
0x180006c34  push    rbx
0x180006c36  push    rsi
0x180006c37  push    rdi
0x180006c38  push    r14
0x180006c3a  sub     rsp, 28h
0x180006c3e  mov     rbx, [rcx+60h]
0x180006c42  mov     r14, r9
0x180006c45  mov     rcx, rdx
0x180006c48  mov     rdi, r8
0x180006c4b  mov     rsi, rdx
0x180006c4e  call    cs:__imp_StrToID
0x180006c54  movzx   edx, ax
0x180006c57  mov     rcx, rbx
0x180006c5a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180006c60  mov     [rdi], rax
0x180006c63  test    rax, rax
0x180006c66  jz      short loc_180006C8C
0x180006c68  mov     rcx, rax
0x180006c6b  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180006c71  test    al, al
0x180006c73  jz      short loc_180006C8C
0x180006c75  mov     rcx, rsi; unsigned __int16 *
0x180006c78  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180006c7d  xor     ecx, ecx
0x180006c7f  mov     [r14], rax
0x180006c82  test    rax, rax
0x180006c85  setnz   cl
0x180006c88  mov     eax, ecx
0x180006c8a  jmp     short loc_180006C8E
0x180006c8c  xor     eax, eax
0x180006c8e  add     rsp, 28h
0x180006c92  pop     r14
0x180006c94  pop     rdi
0x180006c95  pop     rsi
0x180006c96  pop     rbx
0x180006c97  retn
```
