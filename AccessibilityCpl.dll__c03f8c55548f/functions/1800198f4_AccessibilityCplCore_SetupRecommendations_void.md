# AccessibilityCplCore::SetupRecommendations(void)

- ea: `0x1800198f4`
- end: `0x180019bdd`
- name: `?SetupRecommendations@AccessibilityCplCore@@AEAAXXZ`
- size: `745`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x18000539c`
- `0x180005a48`
- `0x1800071c4`
- `0x18000787c`
- `0x1800157dc`
- `0x180018688`
- `0x180018768`
- `0x1800187e0`
- `0x180018878`
- `0x180018954`
- `0x180018a28`
- `0x180018cf0`
- `0x180018d80`
- `0x180018ea0`
- `0x180018fe8`
- `0x180019194`
- `0x1800196c8`
- `0x1800198f4`
- `0x180019be4`
- `0x180019e68`
- `0x18001a13c`
- `0x18001a450`
- `0x18001a4c8`
- `0x18001bc60`
- `0x18001f484`
- `0x18001f9d8`

## import_xrefs

- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800199b5`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800199f6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019a7d`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019a89`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019a95`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019ac9`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800199b5`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800199f6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019a7d`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019a89`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019a95`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180019ac9`
- `DUI70!StrToID` at `0x180019996`
- `DUI70!StrToID` at `0x1800199d7`
- `DUI70!StrToID` at `0x180019a0f`
- `DUI70!StrToID` at `0x180019a2e`
- `DUI70!StrToID` at `0x180019a4d`
- `DUI70!StrToID` at `0x180019aaa`
- `DUI70!StrToID` at `0x180019996`
- `DUI70!StrToID` at `0x1800199d7`
- `DUI70!StrToID` at `0x180019a0f`
- `DUI70!StrToID` at `0x180019a2e`
- `DUI70!StrToID` at `0x180019a4d`
- `DUI70!StrToID` at `0x180019aaa`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800199a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800199e3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019a1b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019a3a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019a59`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019ab6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800199a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800199e3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019a1b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019a3a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019a59`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019ab6`

## string_xrefs

- `0x1800199d0`: `somerecommendations`
- `0x180019aa3`: `norecommendations`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupRecommendations(AccessibilityCplCore *this)
{
  __int64 *Matches; // r15
  DirectUI::Element **v3; // r14
  __int64 v4; // rcx
  _QWORD *Next; // rdi
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rax
  struct DirectUI::Element **v12; // rdi
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rax
  DirectUI::Element *v16; // rbx
  DirectUI::Element *v17; // r12
  unsigned __int16 v18; // ax
  struct DirectUI::Element *v19; // rax
  DirectUI::Element *v20; // rbx
  DirectUI::Element *v21; // r15
  unsigned __int16 v22; // ax
  struct DirectUI::Element *v23; // rax
  DirectUI::Element *v24; // rbx
  DirectUI::Element *v25; // rbx
  unsigned __int16 v26; // ax
  DirectUI::Element *v27; // rax
  int v28; // eax
  __int128 v29; // [rsp+20h] [rbp-39h] BYREF
  __int64 v30; // [rsp+30h] [rbp-29h]
  __int128 v31; // [rsp+38h] [rbp-21h]
  int v32; // [rsp+48h] [rbp-11h]
  _OWORD v33[3]; // [rsp+50h] [rbp-9h] BYREF
  int v34; // [rsp+80h] [rbp+27h]
  __int64 v35; // [rsp+88h] [rbp+2Fh]
  __int64 v36; // [rsp+C0h] [rbp+67h] BYREF

  v35 = 0;
  memset(v33, 0, sizeof(v33));
  v34 = 10;
  v32 = 10;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  Matches = (__int64 *)HciModel::FindMatches(v33, &v29);
  v3 = (DirectUI::Element **)((char *)this + 96);
  v4 = *Matches;
  v36 = v4;
  while ( v36 )
  {
    Next = (_QWORD *)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                       v4,
                       &v36);
    ATL::CSimpleStringT<unsigned short,0>::Append(Next, L"section", 7);
    v6 = *v3;
    v7 = StrToID(*Next);
    Descendent = DirectUI::Element::FindDescendent(v6, v7);
    if ( Descendent )
      DirectUI::Element::SetLayoutPos(Descendent, 1);
  }
  if ( Matches[2] )
  {
    v12 = (struct DirectUI::Element **)((char *)this + 96);
  }
  else
  {
    v9 = *v3;
    v10 = StrToID(L"somerecommendations");
    v11 = DirectUI::Element::FindDescendent(v9, v10);
    if ( v11 )
      DirectUI::Element::SetLayoutPos(v11, -3);
    v12 = (struct DirectUI::Element **)((char *)this + 96);
    v13 = *v3;
    v14 = StrToID(L"actionOK");
    v15 = DirectUI::Element::FindDescendent(v13, v14);
    v16 = *v3;
    v17 = v15;
    v18 = StrToID(L"actionCancel");
    v19 = DirectUI::Element::FindDescendent(v16, v18);
    v20 = *v3;
    v21 = v19;
    v22 = StrToID(L"actionApply");
    v23 = DirectUI::Element::FindDescendent(v20, v22);
    v24 = v23;
    if ( v17 && v21 )
    {
      if ( v23 )
      {
        DirectUI::Element::SetLayoutPos(v17, -3);
        DirectUI::Element::SetLayoutPos(v21, -3);
        DirectUI::Element::SetLayoutPos(v24, -3);
      }
    }
    else
    {
      v12 = (struct DirectUI::Element **)((char *)this + 96);
    }
    v25 = *v12;
    v26 = StrToID(L"norecommendations");
    v27 = DirectUI::Element::FindDescendent(v25, v26);
    if ( v27 )
      DirectUI::Element::SetLayoutPos(v27, 1);
  }
  AccessibilityCplCore::SetupCaretWidth(this);
  AccessibilityCplCore::SetupFocusRect(this);
  AccessibilityCplCore::SetupWindowTracking(this);
  AccessibilityCplCore::SetupWindowArranging(this);
  AccessibilityCplCore::SetupToggleKeys(this);
  AccessibilityCplCore::SetupKeyboardCues(this);
  AccessibilityCplCore::SetupSoundSentry(this);
  AccessibilityCplCore::SetupShowSounds(this);
  AccessibilityCplCore::SetupAnimations(this);
  AccessibilityCplCore::SetupOverlappedContent(this);
  AccessibilityCplCore::SetupAudioDescription(this);
  AccessibilityCplCore::SetupMessageDuration(this);
  AccessibilityCplCore::SetupFilterkeys(this);
  AccessibilityCplCore::SetupMousekeys(this);
  AccessibilityCplCore::SetupCursorScheme(this);
  AccessibilityCplCore::SetupHighContrast(this);
  v28 = AccessibilityCplCore::InitializeDataBinding(this, &v29);
  if ( v28 < 0 || (v28 = AccessibilityCplCore::SetupATs(this, *v12), v28 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_1ff7386e91a53ffb7aa4049a591e8623_Traceguids,
        (unsigned int)v28);
  }
  AccessibilityCplCore::DeleteShortCuts(this, *v12);
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v29);
  HciModel::~HciModel((HciModel *)v33);
}

```

## disassembly

```asm
0x1800198f4  mov     [rsp-8+arg_8], rbx
0x1800198f9  mov     [rsp-8+arg_10], rsi
0x1800198fe  push    rbp
0x1800198ff  push    rdi
0x180019900  push    r12
0x180019902  push    r14
0x180019904  push    r15
0x180019906  lea     rbp, [rsp-37h]
0x18001990b  sub     rsp, 90h
0x180019912  xorps   xmm0, xmm0
0x180019915  mov     [rbp+57h+var_28], 0
0x18001991d  xorps   xmm1, xmm1
0x180019920  movdqa  [rbp+57h+var_60], xmm0
0x180019925  mov     eax, 0Ah
0x18001992a  movdqa  [rbp+57h+var_50], xmm1
0x18001992f  mov     rsi, rcx
0x180019932  movdqa  [rbp+57h+var_40], xmm0
0x180019937  lea     rcx, [rbp+57h+var_60]
0x18001993b  mov     [rbp+57h+var_30], eax
0x18001993e  lea     rdx, [rbp+57h+var_90]
0x180019942  mov     [rbp+57h+var_68], eax
0x180019945  movdqu  [rbp+57h+var_90], xmm0
0x18001994a  mov     [rbp+57h+var_80], 0
0x180019952  movdqu  [rbp+57h+var_78], xmm1
0x180019957  call    ?FindMatches@HciModel@@QEAAAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV23@@Z; HciModel::FindMatches(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18001995c  mov     r15, rax
0x18001995f  lea     r14, [rsi+60h]
0x180019963  mov     rcx, [rax]
0x180019966  mov     [rbp+57h+arg_0], rcx
0x18001996a  test    rcx, rcx
0x18001996d  jz      short loc_1800199C2
0x18001996f  lea     rdx, [rbp+57h+arg_0]
0x180019973  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x180019978  mov     r8d, 7
0x18001997e  lea     rdx, aSection; "section"
0x180019985  mov     rcx, rax
0x180019988  mov     rdi, rax
0x18001998b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180019990  mov     rcx, [rdi]
0x180019993  mov     rbx, [r14]
0x180019996  call    cs:__imp_StrToID
0x18001999c  movzx   edx, ax
0x18001999f  mov     rcx, rbx
0x1800199a2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800199a8  test    rax, rax
0x1800199ab  jz      short loc_1800199BB
0x1800199ad  mov     edx, 1
0x1800199b2  mov     rcx, rax
0x1800199b5  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800199bb  cmp     [rbp+57h+arg_0], 0
0x1800199c0  jnz     short loc_18001996F
0x1800199c2  cmp     qword ptr [r15+10h], 0
0x1800199c7  jnz     loc_180019AD1
0x1800199cd  mov     rbx, [r14]
0x1800199d0  lea     rcx, aSomerecommenda; "somerecommendations"
0x1800199d7  call    cs:__imp_StrToID
0x1800199dd  movzx   edx, ax
0x1800199e0  mov     rcx, rbx
0x1800199e3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800199e9  test    rax, rax
0x1800199ec  jz      short loc_180019A02
0x1800199ee  mov     edx, 0FFFFFFFDh
0x1800199f3  mov     rcx, rax
0x1800199f6  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800199fc  lea     rdi, [rsi+60h]
0x180019a00  jmp     short loc_180019A05
0x180019a02  mov     rdi, r14
0x180019a05  mov     rbx, [r14]
0x180019a08  lea     rcx, aActionok; "actionOK"
0x180019a0f  call    cs:__imp_StrToID
0x180019a15  movzx   edx, ax
0x180019a18  mov     rcx, rbx
0x180019a1b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019a21  mov     rbx, [r14]
0x180019a24  lea     rcx, aActioncancel; "actionCancel"
0x180019a2b  mov     r12, rax
0x180019a2e  call    cs:__imp_StrToID
0x180019a34  movzx   edx, ax
0x180019a37  mov     rcx, rbx
0x180019a3a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019a40  mov     rbx, [r14]
0x180019a43  lea     rcx, aActionapply; "actionApply"
0x180019a4a  mov     r15, rax
0x180019a4d  call    cs:__imp_StrToID
0x180019a53  movzx   edx, ax
0x180019a56  mov     rcx, rbx
0x180019a59  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019a5f  mov     rbx, rax
0x180019a62  test    r12, r12
0x180019a65  jz      short loc_180019A9D
0x180019a67  test    r15, r15
0x180019a6a  jz      short loc_180019A9D
0x180019a6c  test    rax, rax
0x180019a6f  jz      short loc_180019AA0
0x180019a71  mov     r14d, 0FFFFFFFDh
0x180019a77  mov     rcx, r12
0x180019a7a  mov     edx, r14d
0x180019a7d  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180019a83  mov     edx, r14d
0x180019a86  mov     rcx, r15
0x180019a89  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180019a8f  mov     edx, r14d
0x180019a92  mov     rcx, rbx
0x180019a95  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180019a9b  jmp     short loc_180019AA0
0x180019a9d  mov     rdi, r14
0x180019aa0  mov     rbx, [rdi]
0x180019aa3  lea     rcx, aNorecommendati; "norecommendations"
0x180019aaa  call    cs:__imp_StrToID
0x180019ab0  movzx   edx, ax
0x180019ab3  mov     rcx, rbx
0x180019ab6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019abc  test    rax, rax
0x180019abf  jz      short loc_180019AD4
0x180019ac1  mov     edx, 1
0x180019ac6  mov     rcx, rax
0x180019ac9  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180019acf  jmp     short loc_180019AD4
0x180019ad1  mov     rdi, r14
0x180019ad4  mov     rcx, rsi; this
0x180019ad7  call    ?SetupCaretWidth@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupCaretWidth(void)
0x180019adc  mov     rcx, rsi; this
0x180019adf  call    ?SetupFocusRect@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupFocusRect(void)
0x180019ae4  mov     rcx, rsi; this
0x180019ae7  call    ?SetupWindowTracking@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupWindowTracking(void)
0x180019aec  mov     rcx, rsi; this
0x180019aef  call    ?SetupWindowArranging@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupWindowArranging(void)
0x180019af4  mov     rcx, rsi; this
0x180019af7  call    ?SetupToggleKeys@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupToggleKeys(void)
0x180019afc  mov     rcx, rsi; this
0x180019aff  call    ?SetupKeyboardCues@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupKeyboardCues(void)
0x180019b04  mov     rcx, rsi; this
0x180019b07  call    ?SetupSoundSentry@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupSoundSentry(void)
0x180019b0c  mov     rcx, rsi; this
0x180019b0f  call    ?SetupShowSounds@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupShowSounds(void)
0x180019b14  mov     rcx, rsi; this
0x180019b17  call    ?SetupAnimations@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupAnimations(void)
0x180019b1c  mov     rcx, rsi; this
0x180019b1f  call    ?SetupOverlappedContent@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupOverlappedContent(void)
0x180019b24  mov     rcx, rsi; this
0x180019b27  call    ?SetupAudioDescription@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupAudioDescription(void)
0x180019b2c  mov     rcx, rsi; this
0x180019b2f  call    ?SetupMessageDuration@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupMessageDuration(void)
0x180019b34  mov     rcx, rsi; this
0x180019b37  call    ?SetupFilterkeys@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupFilterkeys(void)
0x180019b3c  mov     rcx, rsi; this
0x180019b3f  call    ?SetupMousekeys@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupMousekeys(void)
0x180019b44  mov     rcx, rsi; this
0x180019b47  call    ?SetupCursorScheme@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupCursorScheme(void)
0x180019b4c  mov     rcx, rsi; this
0x180019b4f  call    ?SetupHighContrast@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupHighContrast(void)
0x180019b54  lea     rdx, [rbp+57h+var_90]
0x180019b58  mov     rcx, rsi
0x180019b5b  call    ?InitializeDataBinding@AccessibilityCplCore@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; AccessibilityCplCore::InitializeDataBinding(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x180019b60  test    eax, eax
0x180019b62  js      short loc_180019B73
0x180019b64  mov     rdx, [rdi]; struct DirectUI::Element *
0x180019b67  mov     rcx, rsi; this
0x180019b6a  call    ?SetupATs@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@@Z; AccessibilityCplCore::SetupATs(DirectUI::Element *)
0x180019b6f  test    eax, eax
0x180019b71  jns     short loc_180019BA4
0x180019b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b7a  lea     rdx, WPP_GLOBAL_Control
0x180019b81  cmp     rcx, rdx
0x180019b84  jz      short loc_180019BA4
0x180019b86  test    byte ptr [rcx+1Ch], 4
0x180019b8a  jz      short loc_180019BA4
0x180019b8c  mov     rcx, [rcx+10h]
0x180019b90  lea     r8, WPP_1ff7386e91a53ffb7aa4049a591e8623_Traceguids
0x180019b97  mov     edx, 0Ch
0x180019b9c  mov     r9d, eax
0x180019b9f  call    WPP_SF_d
0x180019ba4  mov     rdx, [rdi]; struct DirectUI::Element *
0x180019ba7  mov     rcx, rsi; this
0x180019baa  call    ?DeleteShortCuts@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@@Z; AccessibilityCplCore::DeleteShortCuts(DirectUI::Element *)
0x180019baf  lea     rcx, [rbp+57h+var_90]
0x180019bb3  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180019bb8  lea     rcx, [rbp+57h+var_60]; this
0x180019bbc  call    ??1HciModel@@QEAA@XZ; HciModel::~HciModel(void)
0x180019bc1  lea     r11, [rsp+0B0h+var_20]
0x180019bc9  mov     rbx, [r11+38h]
0x180019bcd  mov     rsi, [r11+40h]
0x180019bd1  mov     rsp, r11
0x180019bd4  pop     r15
0x180019bd6  pop     r14
0x180019bd8  pop     r12
0x180019bda  pop     rdi
0x180019bdb  pop     rbp
0x180019bdc  retn
```
