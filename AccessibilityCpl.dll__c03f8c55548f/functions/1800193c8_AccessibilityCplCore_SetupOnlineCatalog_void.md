# AccessibilityCplCore::SetupOnlineCatalog(void)

- ea: `0x1800193c8`
- end: `0x180019569`
- name: `?SetupOnlineCatalog@AccessibilityCplCore@@AEAAXXZ`
- size: `417`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180007a70`

## callees

- `0x1800043d4`
- `0x180012a88`
- `0x180015780`
- `0x1800193c8`

## import_xrefs

- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180019411`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001943a`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180019463`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001948c`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800194b2`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800194d8`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800194fe`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180019411`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001943a`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x180019463`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001948c`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800194b2`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800194d8`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800194fe`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180019537`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180019537`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x18001954a`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x18001954a`
- `DUI70!StrToID` at `0x1800193e5`
- `DUI70!StrToID` at `0x180019421`
- `DUI70!StrToID` at `0x18001944a`
- `DUI70!StrToID` at `0x180019473`
- `DUI70!StrToID` at `0x18001949c`
- `DUI70!StrToID` at `0x1800194c2`
- `DUI70!StrToID` at `0x1800194e8`
- `DUI70!StrToID` at `0x18001950e`
- `DUI70!StrToID` at `0x1800193e5`
- `DUI70!StrToID` at `0x180019421`
- `DUI70!StrToID` at `0x18001944a`
- `DUI70!StrToID` at `0x180019473`
- `DUI70!StrToID` at `0x18001949c`
- `DUI70!StrToID` at `0x1800194c2`
- `DUI70!StrToID` at `0x1800194e8`
- `DUI70!StrToID` at `0x18001950e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800193f1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800193f1`

## string_xrefs

- `0x180019504`: `pageEasierToReadAndWrite`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupOnlineCatalog(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rsi
  unsigned __int16 ID; // bx
  __int64 v6; // rdx
  unsigned __int16 v7; // bx
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // bx
  unsigned __int16 v10; // bx
  unsigned __int16 v11; // bx
  unsigned __int16 v12; // bx
  __int16 v13; // ax
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // [rsp+30h] [rbp+8h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = StrToID(L"onlinecatalog");
  Descendent = DirectUI::Element::FindDescendent(v1, v3);
  if ( Descendent )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v15);
    ID = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
    if ( ID == (unsigned __int16)StrToID(L"pageEasierToSee") )
    {
      v6 = 20;
    }
    else
    {
      v7 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
      if ( v7 == (unsigned __int16)StrToID(L"pageNoVisuals") )
      {
        v6 = 21;
      }
      else
      {
        v8 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
        if ( v8 == (unsigned __int16)StrToID(L"pageNoMouseOrKeyboard") )
        {
          v6 = 22;
        }
        else
        {
          v9 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
          if ( v9 == (unsigned __int16)StrToID(L"pageEasierToClick") )
          {
            v6 = 23;
          }
          else
          {
            v10 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
            if ( v10 == (unsigned __int16)StrToID(L"pageKeyboardEasierToUse") )
            {
              v6 = 24;
            }
            else
            {
              v11 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
              if ( v11 == (unsigned __int16)StrToID(L"pageEasierWithSounds") )
              {
                v6 = 25;
              }
              else
              {
                v12 = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
                v13 = StrToID(L"pageEasierToReadAndWrite");
                v6 = 3;
                if ( v12 == v13 )
                  v6 = 26;
              }
            }
          }
        }
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      &v15,
      v6);
    v14 = v15;
    DirectUI::Element::SetContentString(Descendent, v15);
    DirectUI::CCBase::SetNotifyHandler(
      Descendent,
      (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))AccessibilityCplCore::CCSysLinkNotifyHandler,
      0);
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
  }
}

```

## disassembly

```asm
0x1800193c8  mov     [rsp+arg_8], rbx
0x1800193cd  mov     [rsp+arg_10], rsi
0x1800193d2  push    rdi
0x1800193d3  sub     rsp, 20h
0x1800193d7  mov     rbx, [rcx+60h]
0x1800193db  mov     rdi, rcx
0x1800193de  lea     rcx, aOnlinecatalog; "onlinecatalog"
0x1800193e5  call    cs:__imp_StrToID
0x1800193eb  movzx   edx, ax
0x1800193ee  mov     rcx, rbx
0x1800193f1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800193f7  mov     rsi, rax
0x1800193fa  test    rax, rax
0x1800193fd  jz      loc_180019559
0x180019403  lea     rcx, [rsp+28h+arg_0]
0x180019408  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001940d  mov     rcx, [rdi+60h]
0x180019411  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180019417  lea     rcx, aPageeasiertose; "pageEasierToSee"
0x18001941e  movzx   ebx, ax
0x180019421  call    cs:__imp_StrToID
0x180019427  cmp     bx, ax
0x18001942a  jnz     short loc_180019436
0x18001942c  mov     edx, 14h
0x180019431  jmp     loc_180019522
0x180019436  mov     rcx, [rdi+60h]
0x18001943a  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180019440  lea     rcx, aPagenovisuals; "pageNoVisuals"
0x180019447  movzx   ebx, ax
0x18001944a  call    cs:__imp_StrToID
0x180019450  cmp     bx, ax
0x180019453  jnz     short loc_18001945F
0x180019455  mov     edx, 15h
0x18001945a  jmp     loc_180019522
0x18001945f  mov     rcx, [rdi+60h]
0x180019463  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180019469  lea     rcx, aPagenomouseork; "pageNoMouseOrKeyboard"
0x180019470  movzx   ebx, ax
0x180019473  call    cs:__imp_StrToID
0x180019479  cmp     bx, ax
0x18001947c  jnz     short loc_180019488
0x18001947e  mov     edx, 16h
0x180019483  jmp     loc_180019522
0x180019488  mov     rcx, [rdi+60h]
0x18001948c  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180019492  lea     rcx, aPageeasiertocl; "pageEasierToClick"
0x180019499  movzx   ebx, ax
0x18001949c  call    cs:__imp_StrToID
0x1800194a2  cmp     bx, ax
0x1800194a5  jnz     short loc_1800194AE
0x1800194a7  mov     edx, 17h
0x1800194ac  jmp     short loc_180019522
0x1800194ae  mov     rcx, [rdi+60h]
0x1800194b2  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800194b8  lea     rcx, aPagekeyboardea; "pageKeyboardEasierToUse"
0x1800194bf  movzx   ebx, ax
0x1800194c2  call    cs:__imp_StrToID
0x1800194c8  cmp     bx, ax
0x1800194cb  jnz     short loc_1800194D4
0x1800194cd  mov     edx, 18h
0x1800194d2  jmp     short loc_180019522
0x1800194d4  mov     rcx, [rdi+60h]
0x1800194d8  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800194de  lea     rcx, aPageeasierwith; "pageEasierWithSounds"
0x1800194e5  movzx   ebx, ax
0x1800194e8  call    cs:__imp_StrToID
0x1800194ee  cmp     bx, ax
0x1800194f1  jnz     short loc_1800194FA
0x1800194f3  mov     edx, 19h
0x1800194f8  jmp     short loc_180019522
0x1800194fa  mov     rcx, [rdi+60h]
0x1800194fe  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180019504  lea     rcx, aPageeasiertore; "pageEasierToReadAndWrite"
0x18001950b  movzx   ebx, ax
0x18001950e  call    cs:__imp_StrToID
0x180019514  mov     edx, 3
0x180019519  cmp     bx, ax
0x18001951c  lea     ecx, [rdx+17h]
0x18001951f  cmovz   edx, ecx
0x180019522  lea     rcx, [rsp+28h+arg_0]
0x180019527  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18001952c  mov     rbx, [rsp+28h+arg_0]
0x180019531  mov     rcx, rsi
0x180019534  mov     rdx, rbx
0x180019537  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18001953d  xor     r8d, r8d
0x180019540  lea     rdx, ?CCSysLinkNotifyHandler@AccessibilityCplCore@@CAHI_K_JPEA_JPEAX@Z; AccessibilityCplCore::CCSysLinkNotifyHandler(uint,unsigned __int64,__int64,__int64 *,void *)
0x180019547  mov     rcx, rsi
0x18001954a  call    cs:__imp_?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z; DirectUI::CCBase::SetNotifyHandler(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *)
0x180019550  lea     rcx, [rbx-18h]; this
0x180019554  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019559  mov     rbx, [rsp+28h+arg_8]
0x18001955e  mov     rsi, [rsp+28h+arg_10]
0x180019563  add     rsp, 20h
0x180019567  pop     rdi
0x180019568  retn
```
