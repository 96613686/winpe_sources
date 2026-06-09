# AccessibilityCplCore::SavePageStickyKeysSettings(void)

- ea: `0x180017114`
- end: `0x1800172a9`
- name: `?SavePageStickyKeysSettings@AccessibilityCplCore@@AEAAJXZ`
- size: `405`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180017114`
- `0x1800178c0`
- `0x180018294`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`

## import_xrefs

- `DUI70!StrToID` at `0x180017173`
- `DUI70!StrToID` at `0x1800171a8`
- `DUI70!StrToID` at `0x1800171dd`
- `DUI70!StrToID` at `0x180017212`
- `DUI70!StrToID` at `0x180017247`
- `DUI70!StrToID` at `0x180017173`
- `DUI70!StrToID` at `0x1800171a8`
- `DUI70!StrToID` at `0x1800171dd`
- `DUI70!StrToID` at `0x180017212`
- `DUI70!StrToID` at `0x180017247`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001717f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800171b4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800171e9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001721e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017253`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001717f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800171b4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800171e9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001721e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017253`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SavePageStickyKeysSettings(Start **this)
{
  int v2; // edi
  const wchar_t **v3; // rbx
  Accommodation *v4; // rcx
  DirectUI::Element *v5; // rdi
  unsigned __int16 v6; // ax
  struct DirectUI::Element *Descendent; // rax
  AccessibilityCplCore *v8; // rcx
  DirectUI::Element *v9; // rdi
  unsigned __int16 v10; // ax
  struct DirectUI::Element *v11; // rax
  AccessibilityCplCore *v12; // rcx
  DirectUI::Element *v13; // rdi
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rax
  AccessibilityCplCore *v16; // rcx
  DirectUI::Element *v17; // rdi
  unsigned __int16 v18; // ax
  struct DirectUI::Element *v19; // rax
  AccessibilityCplCore *v20; // rcx
  DirectUI::Element *v21; // rdi
  unsigned __int16 v22; // ax
  struct DirectUI::Element *v23; // rax
  AccessibilityCplCore *v24; // rcx
  __int64 v26; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (const wchar_t **)Accommodation::Open(L"stickykeys");
  if ( v3 )
  {
    v2 = AccessibilityCplCore::SaveWarnings((AccessibilityCplCore *)this);
    v4 = (Accommodation *)v3;
    if ( v2 >= 0 )
    {
      v26 = 0;
      Accommodation::GetData(v3, &v26);
      v5 = this[12];
      v6 = StrToID(L"stickykeysshortcut");
      Descendent = DirectUI::Element::FindDescendent(v5, v6);
      if ( Descendent )
        AccessibilityCplCore::SetFlagBasedOnSelection(v8, Descendent, (unsigned int *)&v26 + 1, 4u);
      v9 = this[12];
      v10 = StrToID(L"lockmodifier");
      v11 = DirectUI::Element::FindDescendent(v9, v10);
      if ( v11 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v12, v11, (unsigned int *)&v26 + 1, 0x80u);
      v13 = this[12];
      v14 = StrToID(L"turnoff");
      v15 = DirectUI::Element::FindDescendent(v13, v14);
      if ( v15 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v16, v15, (unsigned int *)&v26 + 1, 0x100u);
      v17 = this[12];
      v18 = StrToID(L"playsound");
      v19 = DirectUI::Element::FindDescendent(v17, v18);
      if ( v19 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v20, v19, (unsigned int *)&v26 + 1, 0x40u);
      v21 = this[12];
      v22 = StrToID(L"showstatus");
      v23 = DirectUI::Element::FindDescendent(v21, v22);
      if ( v23 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v24, v23, (unsigned int *)&v26 + 1, 0x20u);
      v2 = (unsigned int)StartList::Start(this[11], v3, (UINT *)&v26, 0, 0);
      v4 = (Accommodation *)v3;
    }
    Accommodation::`scalar deleting destructor'(v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180017114  mov     [rsp+arg_0], rbx
0x180017119  mov     [rsp+arg_10], rsi
0x18001711e  push    rdi
0x18001711f  sub     rsp, 30h
0x180017123  mov     rsi, rcx
0x180017126  xor     edi, edi
0x180017128  lea     rcx, aStickykeys; "stickykeys"
0x18001712f  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017134  mov     rbx, rax
0x180017137  test    rax, rax
0x18001713a  jz      loc_180017297
0x180017140  mov     rcx, rsi; this
0x180017143  call    ?SaveWarnings@AccessibilityCplCore@@AEAAJXZ; AccessibilityCplCore::SaveWarnings(void)
0x180017148  mov     edi, eax
0x18001714a  mov     rcx, rbx; this
0x18001714d  test    eax, eax
0x18001714f  js      loc_180017292
0x180017155  lea     rdx, [rsp+38h+arg_8]; void *
0x18001715a  mov     qword ptr [rsp+38h+arg_8], 0
0x180017163  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017168  mov     rdi, [rsi+60h]
0x18001716c  lea     rcx, aStickykeysshor; "stickykeysshortcut"
0x180017173  call    cs:__imp_StrToID
0x180017179  movzx   edx, ax
0x18001717c  mov     rcx, rdi
0x18001717f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017185  test    rax, rax
0x180017188  jz      short loc_18001719D
0x18001718a  mov     r9d, 4; unsigned int
0x180017190  lea     r8, [rsp+38h+arg_C]; unsigned int *
0x180017195  mov     rdx, rax; struct DirectUI::Element *
0x180017198  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x18001719d  mov     rdi, [rsi+60h]
0x1800171a1  lea     rcx, aLockmodifier; "lockmodifier"
0x1800171a8  call    cs:__imp_StrToID
0x1800171ae  movzx   edx, ax
0x1800171b1  mov     rcx, rdi
0x1800171b4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800171ba  test    rax, rax
0x1800171bd  jz      short loc_1800171D2
0x1800171bf  mov     r9d, 80h; unsigned int
0x1800171c5  lea     r8, [rsp+38h+arg_C]; unsigned int *
0x1800171ca  mov     rdx, rax; struct DirectUI::Element *
0x1800171cd  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x1800171d2  mov     rdi, [rsi+60h]
0x1800171d6  lea     rcx, aTurnoff; "turnoff"
0x1800171dd  call    cs:__imp_StrToID
0x1800171e3  movzx   edx, ax
0x1800171e6  mov     rcx, rdi
0x1800171e9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800171ef  test    rax, rax
0x1800171f2  jz      short loc_180017207
0x1800171f4  mov     r9d, 100h; unsigned int
0x1800171fa  lea     r8, [rsp+38h+arg_C]; unsigned int *
0x1800171ff  mov     rdx, rax; struct DirectUI::Element *
0x180017202  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017207  mov     rdi, [rsi+60h]
0x18001720b  lea     rcx, aPlaysound; "playsound"
0x180017212  call    cs:__imp_StrToID
0x180017218  movzx   edx, ax
0x18001721b  mov     rcx, rdi
0x18001721e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017224  test    rax, rax
0x180017227  jz      short loc_18001723C
0x180017229  mov     r9d, 40h ; '@'; unsigned int
0x18001722f  lea     r8, [rsp+38h+arg_C]; unsigned int *
0x180017234  mov     rdx, rax; struct DirectUI::Element *
0x180017237  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x18001723c  mov     rdi, [rsi+60h]
0x180017240  lea     rcx, aShowstatus; "showstatus"
0x180017247  call    cs:__imp_StrToID
0x18001724d  movzx   edx, ax
0x180017250  mov     rcx, rdi
0x180017253  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017259  test    rax, rax
0x18001725c  jz      short loc_180017271
0x18001725e  mov     r9d, 20h ; ' '; unsigned int
0x180017264  lea     r8, [rsp+38h+arg_C]; unsigned int *
0x180017269  mov     rdx, rax; struct DirectUI::Element *
0x18001726c  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017271  mov     rcx, [rsi+58h]; this
0x180017275  lea     r8, [rsp+38h+arg_8]; void *
0x18001727a  xor     r9d, r9d; int
0x18001727d  mov     [rsp+38h+var_18], 0; int
0x180017285  mov     rdx, rbx; struct Accommodation *
0x180017288  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x18001728d  mov     edi, eax
0x18001728f  mov     rcx, rbx; this
0x180017292  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017297  mov     rbx, [rsp+38h+arg_0]
0x18001729c  mov     eax, edi
0x18001729e  mov     rsi, [rsp+38h+arg_10]
0x1800172a3  add     rsp, 30h
0x1800172a7  pop     rdi
0x1800172a8  retn
```
