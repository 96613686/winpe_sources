# AccessibilityCplCore::SaveFocusRect(void)

- ea: `0x18001636c`
- end: `0x18001648c`
- name: `?SaveFocusRect@AccessibilityCplCore@@AEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x18001636c`
- `0x18001af04`
- `0x180020edc`
- `0x1800241b0`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800163af`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800163af`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800163f4`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001640a`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800163f4`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001640a`
- `DUI70!StrToID` at `0x18001638e`
- `DUI70!StrToID` at `0x18001638e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001639a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001639a`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveFocusRect(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned int v3; // esi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rbp
  Accommodation *v7; // rdi
  struct Accommodation *v8; // rax
  const wchar_t **v9; // rbx
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = 0;
  v4 = StrToID(L"focusrect");
  Descendent = DirectUI::Element::FindDescendent(v1, v4);
  v6 = Descendent;
  if ( Descendent && DirectUI::Element::GetVisible(Descendent) )
  {
    v7 = Accommodation::Open(L"focusborderheight");
    v8 = Accommodation::Open(L"focusborderwidth");
    v9 = (const wchar_t **)v8;
    if ( v7 )
    {
      if ( !v8 )
      {
LABEL_9:
        Accommodation::`scalar deleting destructor'(v7);
        return v3;
      }
      v12 = 0;
      v11 = 0;
      v12 = DirectUI::Element::GetSelected(v6) + 1;
      v11 = v12;
      DirectUI::Element::GetSelected(v6);
      AccessibilityCplCore::VisitBOOLSetting(this);
      v3 = (unsigned int)StartList::Start(*((Start **)this + 11), (const wchar_t **)v7, (UINT *)&v11, 0, 0);
      if ( (v3 & 0x80000000) == 0 )
        v3 = (unsigned int)StartList::Start(*((Start **)this + 11), v9, (UINT *)&v12, 0, 0);
    }
    else if ( !v8 )
    {
      return v3;
    }
    Accommodation::`scalar deleting destructor'((Accommodation *)v9);
    if ( v7 )
      goto LABEL_9;
  }
  return v3;
}

```

## disassembly

```asm
0x18001636c  mov     [rsp+arg_10], rbx
0x180016371  mov     [rsp+arg_18], rbp
0x180016376  push    rsi
0x180016377  push    rdi
0x180016378  push    r14
0x18001637a  sub     rsp, 30h
0x18001637e  mov     rbx, [rcx+60h]
0x180016382  mov     r14, rcx
0x180016385  lea     rcx, aFocusrect; "focusrect"
0x18001638c  xor     esi, esi
0x18001638e  call    cs:__imp_StrToID
0x180016394  movzx   edx, ax
0x180016397  mov     rcx, rbx
0x18001639a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800163a0  mov     rbp, rax
0x1800163a3  test    rax, rax
0x1800163a6  jz      loc_180016477
0x1800163ac  mov     rcx, rax
0x1800163af  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800163b5  test    al, al
0x1800163b7  jz      loc_180016477
0x1800163bd  lea     rcx, aFocusborderhei; "focusborderheight"
0x1800163c4  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800163c9  lea     rcx, aFocusborderwid; "focusborderwidth"
0x1800163d0  mov     rdi, rax
0x1800163d3  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800163d8  mov     rbx, rax
0x1800163db  test    rdi, rdi
0x1800163de  jz      short loc_18001645D
0x1800163e0  test    rax, rax
0x1800163e3  jz      loc_18001646F
0x1800163e9  mov     rcx, rbp
0x1800163ec  mov     [rsp+48h+arg_8], esi
0x1800163f0  mov     [rsp+48h+arg_0], esi
0x1800163f4  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800163fa  movzx   eax, al
0x1800163fd  mov     rcx, rbp
0x180016400  inc     eax
0x180016402  mov     [rsp+48h+arg_8], eax
0x180016406  mov     [rsp+48h+arg_0], eax
0x18001640a  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180016410  movzx   r8d, al; int
0x180016414  lea     edx, [rsi+10h]; unsigned int
0x180016417  mov     rcx, r14; this
0x18001641a  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x18001641f  mov     rcx, [r14+58h]; this
0x180016423  lea     r8, [rsp+48h+arg_0]; void *
0x180016428  xor     r9d, r9d; int
0x18001642b  mov     [rsp+48h+var_28], esi; int
0x18001642f  mov     rdx, rdi; struct Accommodation *
0x180016432  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180016437  mov     esi, eax
0x180016439  test    eax, eax
0x18001643b  js      short loc_180016462
0x18001643d  mov     rcx, [r14+58h]; this
0x180016441  lea     r8, [rsp+48h+arg_8]; void *
0x180016446  xor     r9d, r9d; int
0x180016449  mov     [rsp+48h+var_28], 0; int
0x180016451  mov     rdx, rbx; struct Accommodation *
0x180016454  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180016459  mov     esi, eax
0x18001645b  jmp     short loc_180016462
0x18001645d  test    rbx, rbx
0x180016460  jz      short loc_180016477
0x180016462  mov     rcx, rbx; this
0x180016465  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x18001646a  test    rdi, rdi
0x18001646d  jz      short loc_180016477
0x18001646f  mov     rcx, rdi; this
0x180016472  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180016477  mov     rbx, [rsp+48h+arg_10]
0x18001647c  mov     eax, esi
0x18001647e  mov     rbp, [rsp+48h+arg_18]
0x180016483  add     rsp, 30h
0x180016487  pop     r14
0x180016489  pop     rdi
0x18001648a  pop     rsi
0x18001648b  retn
```
