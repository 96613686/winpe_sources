# AccessibilityCplCore::SavekeyboardCues(void)

- ea: `0x180017eb8`
- end: `0x180017ff5`
- name: `?SavekeyboardCues@AccessibilityCplCore@@AEAAJXZ`
- size: `317`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180017eb8`
- `0x18001af04`
- `0x180020edc`
- `0x1800241b0`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180017efb`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180017efb`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017f0c`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017f48`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017f9d`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017f0c`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017f48`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017f9d`
- `DUI70!StrToID` at `0x180017eda`
- `DUI70!StrToID` at `0x180017eda`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017ee6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017ee6`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SavekeyboardCues(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned int v3; // esi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rbp
  const wchar_t **v7; // rbx
  Start *v8; // rdi
  bool Selected; // al
  UINT *v10; // r8
  const wchar_t **v11; // rdi
  Start *v12; // rsi
  bool v13; // al
  UINT *v14; // r8
  int v16; // [rsp+50h] [rbp+8h] BYREF
  int v17; // [rsp+58h] [rbp+10h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = 0;
  v4 = StrToID(L"keyboardpref");
  Descendent = DirectUI::Element::FindDescendent(v1, v4);
  v6 = Descendent;
  if ( Descendent && DirectUI::Element::GetVisible(Descendent) )
  {
    DirectUI::Element::GetSelected(v6);
    AccessibilityCplCore::VisitBOOLSetting(this);
    v7 = (const wchar_t **)Accommodation::Open(L"keyboardpref");
    if ( v7 )
    {
      v8 = (Start *)*((_QWORD *)this + 11);
      v17 = 1;
      v16 = 0;
      Selected = DirectUI::Element::GetSelected(v6);
      v10 = (UINT *)&v16;
      if ( Selected )
        v10 = (UINT *)&v17;
      v3 = (unsigned int)StartList::Start(v8, v7, v10, 0, 0);
    }
    v11 = (const wchar_t **)Accommodation::Open(L"keyboardcues");
    if ( v11 )
    {
      v12 = (Start *)*((_QWORD *)this + 11);
      v17 = 1;
      v16 = 0;
      v13 = DirectUI::Element::GetSelected(v6);
      v14 = (UINT *)&v16;
      if ( v13 )
        v14 = (UINT *)&v17;
      v3 = (unsigned int)StartList::Start(v12, v11, v14, 0, 0);
      Accommodation::`scalar deleting destructor'((Accommodation *)v11);
    }
    if ( v7 )
      Accommodation::`scalar deleting destructor'((Accommodation *)v7);
  }
  return v3;
}

```

## disassembly

```asm
0x180017eb8  mov     [rsp+arg_10], rbx
0x180017ebd  mov     [rsp+arg_18], rbp
0x180017ec2  push    rsi
0x180017ec3  push    rdi
0x180017ec4  push    r14
0x180017ec6  sub     rsp, 30h
0x180017eca  mov     rbx, [rcx+60h]
0x180017ece  mov     r14, rcx
0x180017ed1  lea     rcx, aKeyboardpref; "keyboardpref"
0x180017ed8  xor     esi, esi
0x180017eda  call    cs:__imp_StrToID
0x180017ee0  movzx   edx, ax
0x180017ee3  mov     rcx, rbx
0x180017ee6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017eec  mov     rbp, rax
0x180017eef  test    rax, rax
0x180017ef2  jz      loc_180017FE0
0x180017ef8  mov     rcx, rax
0x180017efb  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180017f01  test    al, al
0x180017f03  jz      loc_180017FE0
0x180017f09  mov     rcx, rbp
0x180017f0c  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180017f12  movzx   r8d, al; int
0x180017f16  lea     edx, [rsi+14h]; unsigned int
0x180017f19  mov     rcx, r14; this
0x180017f1c  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x180017f21  lea     rcx, aKeyboardpref; "keyboardpref"
0x180017f28  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017f2d  mov     rbx, rax
0x180017f30  test    rax, rax
0x180017f33  jz      short loc_180017F72
0x180017f35  mov     rdi, [r14+58h]
0x180017f39  mov     rcx, rbp
0x180017f3c  mov     [rsp+48h+arg_8], 1
0x180017f44  mov     [rsp+48h+arg_0], esi
0x180017f48  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180017f4e  lea     rcx, [rsp+48h+arg_8]
0x180017f53  mov     [rsp+48h+var_28], esi; int
0x180017f57  test    al, al
0x180017f59  lea     r8, [rsp+48h+arg_0]
0x180017f5e  mov     rdx, rbx; struct Accommodation *
0x180017f61  cmovnz  r8, rcx; void *
0x180017f65  xor     r9d, r9d; int
0x180017f68  mov     rcx, rdi; this
0x180017f6b  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017f70  mov     esi, eax
0x180017f72  lea     rcx, aKeyboardcues; "keyboardcues"
0x180017f79  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017f7e  mov     rdi, rax
0x180017f81  test    rax, rax
0x180017f84  jz      short loc_180017FD3
0x180017f86  mov     rsi, [r14+58h]
0x180017f8a  mov     rcx, rbp
0x180017f8d  mov     [rsp+48h+arg_8], 1
0x180017f95  mov     [rsp+48h+arg_0], 0
0x180017f9d  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180017fa3  lea     rcx, [rsp+48h+arg_8]
0x180017fa8  mov     [rsp+48h+var_28], 0; int
0x180017fb0  test    al, al
0x180017fb2  lea     r8, [rsp+48h+arg_0]
0x180017fb7  mov     rdx, rdi; struct Accommodation *
0x180017fba  cmovnz  r8, rcx; void *
0x180017fbe  xor     r9d, r9d; int
0x180017fc1  mov     rcx, rsi; this
0x180017fc4  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017fc9  mov     rcx, rdi; this
0x180017fcc  mov     esi, eax
0x180017fce  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017fd3  test    rbx, rbx
0x180017fd6  jz      short loc_180017FE0
0x180017fd8  mov     rcx, rbx; this
0x180017fdb  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017fe0  mov     rbx, [rsp+48h+arg_10]
0x180017fe5  mov     eax, esi
0x180017fe7  mov     rbp, [rsp+48h+arg_18]
0x180017fec  add     rsp, 30h
0x180017ff0  pop     r14
0x180017ff2  pop     rdi
0x180017ff3  pop     rsi
0x180017ff4  retn
```
