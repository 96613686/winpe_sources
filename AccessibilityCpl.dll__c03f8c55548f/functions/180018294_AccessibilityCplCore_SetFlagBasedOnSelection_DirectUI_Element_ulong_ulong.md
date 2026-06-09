# AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)

- ea: `0x180018294`
- end: `0x1800182cf`
- name: `?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z`
- size: `59`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *, unsigned int *, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180016494`
- `0x180016800`
- `0x180016b44`
- `0x180016d70`
- `0x180017114`
- `0x180017464`
- `0x1800178c0`

## callees

- `0x180018294`

## import_xrefs

- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800182ac`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800182ac`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetFlagBasedOnSelection(
        AccessibilityCplCore *this,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        int a4)
{
  bool Selected; // al
  int v7; // ecx

  if ( a2 )
  {
    Selected = DirectUI::Element::GetSelected(a2);
    v7 = *a3;
    if ( Selected )
      *a3 = a4 | v7;
    else
      *a3 = v7 & ~a4;
  }
}

```

## disassembly

```asm
0x180018294  test    rdx, rdx
0x180018297  jz      short locret_1800182CE
0x180018299  mov     [rsp+arg_0], rbx
0x18001829e  push    rdi
0x18001829f  sub     rsp, 20h
0x1800182a3  mov     rcx, rdx
0x1800182a6  mov     ebx, r9d
0x1800182a9  mov     rdi, r8
0x1800182ac  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800182b2  mov     ecx, [rdi]
0x1800182b4  test    al, al
0x1800182b6  jz      short loc_1800182BE
0x1800182b8  or      ecx, ebx
0x1800182ba  mov     [rdi], ecx
0x1800182bc  jmp     short loc_1800182C4
0x1800182be  not     ebx
0x1800182c0  and     ebx, ecx
0x1800182c2  mov     [rdi], ebx
0x1800182c4  mov     rbx, [rsp+28h+arg_0]
0x1800182c9  add     rsp, 20h
0x1800182cd  pop     rdi
0x1800182ce  retn
```
