# AccessibilityCplCore::SaveWindowTracking(void)

- ea: `0x180017d78`
- end: `0x180017eb2`
- name: `?SaveWindowTracking@AccessibilityCplCore@@AEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180017d78`
- `0x18001af04`
- `0x180020edc`
- `0x1800241b0`

## import_xrefs

- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180017db5`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180017db5`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017dc6`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180017dc6`
- `DUI70!StrToID` at `0x180017d94`
- `DUI70!StrToID` at `0x180017d94`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017da0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017da0`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveWindowTracking(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  int v3; // esi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rbx
  const wchar_t **v7; // rax
  Accommodation *v8; // rbx
  const wchar_t **v9; // rax
  Accommodation *v10; // rdi
  const wchar_t **v11; // rax
  Accommodation *v12; // rdi
  Start *v13; // rcx
  BOOL Selected; // [rsp+50h] [rbp+8h] BYREF
  UINT v16; // [rsp+58h] [rbp+10h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = 0;
  v4 = StrToID(L"windowtracking");
  Descendent = DirectUI::Element::FindDescendent(v1, v4);
  v6 = Descendent;
  if ( Descendent && DirectUI::Element::GetVisible(Descendent) )
  {
    Selected = DirectUI::Element::GetSelected(v6);
    AccessibilityCplCore::VisitBOOLSetting(this);
    v7 = (const wchar_t **)Accommodation::Open(L"windowtracking");
    v8 = (Accommodation *)v7;
    if ( v7 )
    {
      v3 = (unsigned int)StartList::Start(*((Start **)this + 11), v7, (UINT *)&Selected, 0, 0);
      if ( v3 < 0 )
        goto LABEL_10;
    }
    v9 = (const wchar_t **)Accommodation::Open(L"windowtrackingzorder");
    v10 = (Accommodation *)v9;
    if ( !v9
      || (v3 = (unsigned int)StartList::Start(*((Start **)this + 11), v9, (UINT *)&Selected, 0, 0),
          Accommodation::`scalar deleting destructor'(v10),
          v3 >= 0) )
    {
      v11 = (const wchar_t **)Accommodation::Open(L"windowtrackingtimeout");
      v12 = (Accommodation *)v11;
      if ( v11 )
      {
        v13 = (Start *)*((_QWORD *)this + 11);
        v16 = 500;
        v3 = (unsigned int)StartList::Start(v13, v11, &v16, 0, 0);
        Accommodation::`scalar deleting destructor'(v12);
      }
    }
    if ( v8 )
LABEL_10:
      Accommodation::`scalar deleting destructor'(v8);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017d78  mov     [rsp+arg_10], rbx
0x180017d7d  push    rbp
0x180017d7e  push    rsi
0x180017d7f  push    rdi
0x180017d80  sub     rsp, 30h
0x180017d84  mov     rbx, [rcx+60h]
0x180017d88  mov     rbp, rcx
0x180017d8b  lea     rcx, aWindowtracking; "windowtracking"
0x180017d92  xor     esi, esi
0x180017d94  call    cs:__imp_StrToID
0x180017d9a  movzx   edx, ax
0x180017d9d  mov     rcx, rbx
0x180017da0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017da6  mov     rbx, rax
0x180017da9  test    rax, rax
0x180017dac  jz      loc_180017EA3
0x180017db2  mov     rcx, rax
0x180017db5  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180017dbb  test    al, al
0x180017dbd  jz      loc_180017EA3
0x180017dc3  mov     rcx, rbx
0x180017dc6  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180017dcc  movzx   r8d, al; int
0x180017dd0  lea     edx, [rsi+13h]; unsigned int
0x180017dd3  mov     rcx, rbp; this
0x180017dd6  mov     [rsp+48h+arg_0], r8d
0x180017ddb  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x180017de0  lea     rcx, aWindowtracking; "windowtracking"
0x180017de7  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017dec  mov     rbx, rax
0x180017def  test    rax, rax
0x180017df2  jz      short loc_180017E16
0x180017df4  mov     rcx, [rbp+58h]; this
0x180017df8  lea     r8, [rsp+48h+arg_0]; void *
0x180017dfd  xor     r9d, r9d; int
0x180017e00  mov     [rsp+48h+var_28], esi; int
0x180017e04  mov     rdx, rax; struct Accommodation *
0x180017e07  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017e0c  mov     esi, eax
0x180017e0e  test    eax, eax
0x180017e10  js      loc_180017E9B
0x180017e16  lea     rcx, aWindowtracking_0; "windowtrackingzorder"
0x180017e1d  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017e22  mov     rdi, rax
0x180017e25  test    rax, rax
0x180017e28  jz      short loc_180017E54
0x180017e2a  mov     rcx, [rbp+58h]; this
0x180017e2e  lea     r8, [rsp+48h+arg_0]; void *
0x180017e33  xor     r9d, r9d; int
0x180017e36  mov     [rsp+48h+var_28], 0; int
0x180017e3e  mov     rdx, rax; struct Accommodation *
0x180017e41  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017e46  mov     rcx, rdi; this
0x180017e49  mov     esi, eax
0x180017e4b  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017e50  test    esi, esi
0x180017e52  js      short loc_180017E96
0x180017e54  lea     rcx, aWindowtracking_1; "windowtrackingtimeout"
0x180017e5b  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017e60  mov     rdi, rax
0x180017e63  test    rax, rax
0x180017e66  jz      short loc_180017E96
0x180017e68  mov     rcx, [rbp+58h]; this
0x180017e6c  lea     r8, [rsp+48h+arg_8]; void *
0x180017e71  xor     r9d, r9d; int
0x180017e74  mov     [rsp+48h+arg_8], 1F4h
0x180017e7c  mov     rdx, rax; struct Accommodation *
0x180017e7f  mov     [rsp+48h+var_28], 0; int
0x180017e87  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017e8c  mov     rcx, rdi; this
0x180017e8f  mov     esi, eax
0x180017e91  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017e96  test    rbx, rbx
0x180017e99  jz      short loc_180017EA3
0x180017e9b  mov     rcx, rbx; this
0x180017e9e  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017ea3  mov     rbx, [rsp+48h+arg_10]
0x180017ea8  mov     eax, esi
0x180017eaa  add     rsp, 30h
0x180017eae  pop     rdi
0x180017eaf  pop     rsi
0x180017eb0  pop     rbp
0x180017eb1  retn
```
