# AccessibilityCplCore::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)

- ea: `0x1800143a0`
- end: `0x180014573`
- name: `?OnKeyFocusMoved@AccessibilityCplCore@@UEAAXPEAVElement@DirectUI@@0@Z`
- size: `467`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004f78`
- `0x1800143a0`
- `0x1800156e0`
- `0x180016800`
- `0x180016ee4`
- `0x180020edc`
- `0x1800241b0`
- `0x180024fd4`
- `0x180025068`
- `0x18002e010`

## import_xrefs

- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800143cf`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800143e0`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800144ba`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800143cf`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800143e0`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800144ba`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001455f`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001455f`
- `DUI70!StrToID` at `0x1800143f5`
- `DUI70!StrToID` at `0x18001445f`
- `DUI70!StrToID` at `0x1800144ca`
- `DUI70!StrToID` at `0x1800144e9`
- `DUI70!StrToID` at `0x180014543`
- `DUI70!StrToID` at `0x1800143f5`
- `DUI70!StrToID` at `0x18001445f`
- `DUI70!StrToID` at `0x1800144ca`
- `DUI70!StrToID` at `0x1800144e9`
- `DUI70!StrToID` at `0x180014543`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001454f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001454f`
- `DUI70!?GetClassInfoPtr@CCTrackBar@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180014518`
- `DUI70!?GetClassInfoPtr@CCTrackBar@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180014518`

## pseudocode

```c
void __fastcall AccessibilityCplCore::OnKeyFocusMoved(
        AccessibilityCplCore *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3)
{
  unsigned __int16 ID; // bx
  unsigned __int16 v6; // bp
  const wchar_t **v7; // rbx
  const wchar_t **v8; // rax
  Accommodation *v9; // rbx
  unsigned __int16 v10; // bp
  __int64 ClassInfoPtr; // rbx
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  DirectUI::Element *Descendent; // rax
  _BYTE v15[392]; // [rsp+30h] [rbp-188h] BYREF

  if ( *((_QWORD *)this + 11) )
  {
    ID = 0;
    v6 = 0;
    if ( a2 )
      ID = DirectUI::Element::GetID(a2);
    if ( a3 )
      v6 = DirectUI::Element::GetID(a3);
    if ( ID )
    {
      if ( ID == (unsigned __int16)StrToID(L"filterkeystest") )
      {
        if ( *((_DWORD *)this + 50) )
        {
          v7 = (const wchar_t **)Accommodation::Open(L"filterkeys");
          if ( v7 )
          {
            AccessibilityCplCore::RefreshATManager(this);
            StartList::Start(*((Start **)this + 11), v7, (UINT *)this + 51, 0, 0);
            *((_DWORD *)this + 50) = 0;
            Accommodation::`scalar deleting destructor'((Accommodation *)v7);
          }
        }
      }
    }
    if ( v6 && v6 == (unsigned __int16)StrToID(L"filterkeystest") )
    {
      ATManager::ATManager((ATManager *)v15, 0);
      v8 = (const wchar_t **)Accommodation::Open(L"filterkeys");
      v9 = (Accommodation *)v8;
      if ( v8 )
      {
        if ( *((_QWORD *)this + 12) )
        {
          *((_DWORD *)this + 50) = 1;
          StartList::Start((Start *)v15, v8, 0, 0, 0);
          v10 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
          if ( v10 == (unsigned __int16)StrToID(L"pageFilterKeysSettings") )
            AccessibilityCplCore::SavePageFilterKeysSettings(this, (struct ATManager *)v15);
          if ( v10 == (unsigned __int16)StrToID(L"pageRepeatRateSlowKeysSettings") )
            AccessibilityCplCore::SavePageRepeatRateSlowKeysSettings(this, (struct ATManager *)v15);
        }
        Accommodation::`scalar deleting destructor'(v9);
      }
      ATManager::~ATManager((ATManager *)v15);
    }
    if ( a3 )
    {
      ClassInfoPtr = DirectUI::CCTrackBar::GetClassInfoPtr();
      if ( (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)a3 + 280LL))(a3) == ClassInfoPtr )
      {
        v12 = (DirectUI::Element *)*((_QWORD *)this + 12);
        v13 = StrToID(L"actionApply");
        Descendent = DirectUI::Element::FindDescendent(v12, v13);
        if ( Descendent )
          DirectUI::Element::SetEnabled(Descendent, 1);
      }
    }
  }
}

```

## disassembly

```asm
0x1800143a0  push    rbx
0x1800143a2  push    rbp
0x1800143a3  push    rsi
0x1800143a4  push    rdi
0x1800143a5  push    r14
0x1800143a7  sub     rsp, 190h
0x1800143ae  xor     r14d, r14d
0x1800143b1  mov     rsi, r8
0x1800143b4  mov     rdi, rcx
0x1800143b7  cmp     [rcx+58h], r14
0x1800143bb  jz      loc_180014565
0x1800143c1  mov     ebx, r14d
0x1800143c4  mov     ebp, r14d
0x1800143c7  test    rdx, rdx
0x1800143ca  jz      short loc_1800143D8
0x1800143cc  mov     rcx, rdx
0x1800143cf  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800143d5  movzx   ebx, ax
0x1800143d8  test    rsi, rsi
0x1800143db  jz      short loc_1800143E9
0x1800143dd  mov     rcx, rsi
0x1800143e0  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800143e6  movzx   ebp, ax
0x1800143e9  test    bx, bx
0x1800143ec  jz      short loc_18001444F
0x1800143ee  lea     rcx, aFilterkeystest; "filterkeystest"
0x1800143f5  call    cs:__imp_StrToID
0x1800143fb  cmp     bx, ax
0x1800143fe  jnz     short loc_18001444F
0x180014400  cmp     [rdi+0C8h], r14d
0x180014407  jz      short loc_18001444F
0x180014409  lea     rcx, aFilterkeys; "filterkeys"
0x180014410  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180014415  mov     rbx, rax
0x180014418  test    rax, rax
0x18001441b  jz      short loc_18001444F
0x18001441d  mov     rcx, rdi; this
0x180014420  call    ?RefreshATManager@AccessibilityCplCore@@AEAAJXZ; AccessibilityCplCore::RefreshATManager(void)
0x180014425  mov     rcx, [rdi+58h]; this
0x180014429  lea     r8, [rdi+0CCh]; void *
0x180014430  xor     r9d, r9d; int
0x180014433  mov     [rsp+1B8h+var_198], r14d; int
0x180014438  mov     rdx, rbx; struct Accommodation *
0x18001443b  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180014440  mov     rcx, rbx; this
0x180014443  mov     [rdi+0C8h], r14d
0x18001444a  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x18001444f  test    bp, bp
0x180014452  jz      loc_180014513
0x180014458  lea     rcx, aFilterkeystest; "filterkeystest"
0x18001445f  call    cs:__imp_StrToID
0x180014465  cmp     bp, ax
0x180014468  jnz     loc_180014513
0x18001446e  xor     edx, edx; int
0x180014470  lea     rcx, [rsp+1B8h+var_188]; this
0x180014475  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x18001447a  lea     rcx, aFilterkeys; "filterkeys"
0x180014481  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180014486  mov     rbx, rax
0x180014489  test    rax, rax
0x18001448c  jz      short loc_180014509
0x18001448e  cmp     [rdi+60h], r14
0x180014492  jz      short loc_180014501
0x180014494  xor     r9d, r9d; int
0x180014497  mov     dword ptr [rdi+0C8h], 1
0x1800144a1  xor     r8d, r8d; void *
0x1800144a4  mov     [rsp+1B8h+var_198], r14d; int
0x1800144a9  mov     rdx, rax; struct Accommodation *
0x1800144ac  lea     rcx, [rsp+1B8h+var_188]; this
0x1800144b1  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x1800144b6  mov     rcx, [rdi+60h]
0x1800144ba  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800144c0  lea     rcx, aPagefilterkeys; "pageFilterKeysSettings"
0x1800144c7  movzx   ebp, ax
0x1800144ca  call    cs:__imp_StrToID
0x1800144d0  cmp     bp, ax
0x1800144d3  jnz     short loc_1800144E2
0x1800144d5  lea     rdx, [rsp+1B8h+var_188]; struct ATManager *
0x1800144da  mov     rcx, rdi; this
0x1800144dd  call    ?SavePageFilterKeysSettings@AccessibilityCplCore@@AEAAJPEAVATManager@@@Z; AccessibilityCplCore::SavePageFilterKeysSettings(ATManager *)
0x1800144e2  lea     rcx, aPagerepeatrate; "pageRepeatRateSlowKeysSettings"
0x1800144e9  call    cs:__imp_StrToID
0x1800144ef  cmp     bp, ax
0x1800144f2  jnz     short loc_180014501
0x1800144f4  lea     rdx, [rsp+1B8h+var_188]; struct ATManager *
0x1800144f9  mov     rcx, rdi; this
0x1800144fc  call    ?SavePageRepeatRateSlowKeysSettings@AccessibilityCplCore@@AEAAJPEAVATManager@@@Z; AccessibilityCplCore::SavePageRepeatRateSlowKeysSettings(ATManager *)
0x180014501  mov     rcx, rbx; this
0x180014504  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180014509  lea     rcx, [rsp+1B8h+var_188]; this
0x18001450e  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x180014513  test    rsi, rsi
0x180014516  jz      short loc_180014565
0x180014518  call    cs:__imp_?GetClassInfoPtr@CCTrackBar@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::CCTrackBar::GetClassInfoPtr(void)
0x18001451e  mov     rcx, [rsi]
0x180014521  mov     rbx, rax
0x180014524  mov     rax, [rcx+118h]
0x18001452b  mov     rcx, rsi
0x18001452e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014533  cmp     rax, rbx
0x180014536  jnz     short loc_180014565
0x180014538  mov     rbx, [rdi+60h]
0x18001453c  lea     rcx, aActionapply; "actionApply"
0x180014543  call    cs:__imp_StrToID
0x180014549  movzx   edx, ax
0x18001454c  mov     rcx, rbx
0x18001454f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180014555  test    rax, rax
0x180014558  jz      short loc_180014565
0x18001455a  mov     dl, 1
0x18001455c  mov     rcx, rax
0x18001455f  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180014565  add     rsp, 190h
0x18001456c  pop     r14
0x18001456e  pop     rdi
0x18001456f  pop     rsi
0x180014570  pop     rbp
0x180014571  pop     rbx
0x180014572  retn
```
