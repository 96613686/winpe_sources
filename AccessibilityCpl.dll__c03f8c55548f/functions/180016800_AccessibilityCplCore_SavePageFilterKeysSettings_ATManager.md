# AccessibilityCplCore::SavePageFilterKeysSettings(ATManager *)

- ea: `0x180016800`
- end: `0x180016b3e`
- name: `?SavePageFilterKeysSettings@AccessibilityCplCore@@AEAAJPEAVATManager@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct ATManager *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800134a0`
- `0x1800143a0`

## callees

- `0x180004f78`
- `0x1800055c0`
- `0x180014828`
- `0x180016800`
- `0x1800178c0`
- `0x180018260`
- `0x180018294`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `USER32!SendMessageW` at `0x18001695b`
- `USER32!SendMessageW` at `0x18001695b`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016904`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800169c6`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016904`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800169c6`
- `DUI70!StrToID` at `0x18001688f`
- `DUI70!StrToID` at `0x1800168c3`
- `DUI70!StrToID` at `0x1800168e3`
- `DUI70!StrToID` at `0x18001691d`
- `DUI70!StrToID` at `0x1800169fd`
- `DUI70!StrToID` at `0x180016a31`
- `DUI70!StrToID` at `0x18001688f`
- `DUI70!StrToID` at `0x1800168c3`
- `DUI70!StrToID` at `0x1800168e3`
- `DUI70!StrToID` at `0x18001691d`
- `DUI70!StrToID` at `0x1800169fd`
- `DUI70!StrToID` at `0x180016a31`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001689b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168cf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168ef`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016929`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016a09`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016a3d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001689b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168cf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168ef`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016929`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016a09`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016a3d`

## string_xrefs

- `0x180016a82`: `Control Panel\Accessibility\Keyboard Response`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SavePageFilterKeysSettings(AccessibilityCplCore *this, struct ATManager *a2)
{
  int v4; // edi
  const wchar_t **v5; // rbx
  unsigned int v6; // edx
  Accommodation *v7; // rcx
  DirectUI::Element *v8; // rdi
  unsigned __int16 v9; // ax
  struct DirectUI::Element *Descendent; // rax
  AccessibilityCplCore *v11; // rcx
  DirectUI::Element *v12; // rdi
  unsigned __int16 v13; // ax
  struct DirectUI::Element *v14; // rax
  DirectUI::Element *v15; // rdi
  DirectUI::Element *v16; // r14
  unsigned __int16 v17; // ax
  DirectUI::Element *v18; // rdi
  DirectUI::Element *v19; // rdi
  unsigned __int16 v20; // ax
  struct DirectUI::Element *v21; // rax
  HWND v22; // rax
  LRESULT v23; // rax
  LRESULT v24; // rax
  LRESULT v25; // rax
  LRESULT v26; // rax
  unsigned int v27; // eax
  DirectUI::Element *v28; // rdi
  unsigned __int16 v29; // ax
  struct DirectUI::Element *v30; // rax
  AccessibilityCplCore *v31; // rcx
  DirectUI::Element *v32; // rdi
  unsigned __int16 v33; // ax
  struct DirectUI::Element *v34; // rax
  AccessibilityCplCore *v35; // rcx
  HKEY v37[3]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v38[6]; // [rsp+48h] [rbp-28h] BYREF

  v4 = 0;
  v5 = (const wchar_t **)Accommodation::Open(L"filterkeys");
  if ( v5 )
  {
    v4 = AccessibilityCplCore::SaveWarnings(this);
    v7 = (Accommodation *)v5;
    if ( v4 < 0 )
    {
LABEL_33:
      Accommodation::`scalar deleting destructor'(v7, v6);
      return (unsigned int)v4;
    }
    memset(v38, 0, sizeof(v38));
    Accommodation::GetData(v5, v38);
    if ( !*((_DWORD *)this + 50) )
      Accommodation::GetData(v5, (_DWORD *)this + 51);
    v8 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v9 = StrToID(L"filterkeysShortcut");
    Descendent = DirectUI::Element::FindDescendent(v8, v9);
    if ( Descendent )
      AccessibilityCplCore::SetFlagBasedOnSelection(v11, Descendent, &v38[1], 4u);
    v12 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v13 = StrToID(L"bouncekeys");
    v14 = DirectUI::Element::FindDescendent(v12, v13);
    v15 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v16 = v14;
    v17 = StrToID(L"slowkeys");
    v18 = DirectUI::Element::FindDescendent(v15, v17);
    if ( !v16 || !DirectUI::Element::GetSelected(v16) )
    {
      if ( v18 && DirectUI::Element::GetSelected(v18) )
      {
        v38[3] = *((_DWORD *)this + 60);
        *(_QWORD *)&v38[4] = *((unsigned int *)this + 61);
        v38[2] = *((_DWORD *)this + 59);
      }
      goto LABEL_26;
    }
    v19 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v20 = StrToID(L"bouncekeysdelay");
    v21 = DirectUI::Element::FindDescendent(v19, v20);
    if ( !v21 )
    {
LABEL_26:
      v28 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v29 = StrToID(L"click");
      v30 = DirectUI::Element::FindDescendent(v28, v29);
      if ( v30 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v31, v30, &v38[1], 0x40u);
      v32 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v33 = StrToID(L"indicator");
      v34 = DirectUI::Element::FindDescendent(v32, v33);
      if ( v34 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v35, v34, &v38[1], 0x20u);
      memset(v37, 0, sizeof(v37));
      v4 = (unsigned int)StartList::Start(a2, v5, v38, 0, 0);
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)v37,
                            HKEY_CURRENT_USER,
                            L"Control Panel\\Accessibility\\Keyboard Response",
                            0x2001Fu) )
      {
        ATL::CRegKey::SetDWORDValue(v37, L"Last BounceKey Setting", *((_DWORD *)this + 62));
        ATL::CRegKey::SetDWORDValue(v37, L"Last Valid Delay", *((_DWORD *)this + 60));
        ATL::CRegKey::SetDWORDValue(v37, L"Last Valid Repeat", *((_DWORD *)this + 61));
        ATL::CRegKey::SetDWORDValue(v37, L"Last Valid Wait", *((_DWORD *)this + 59));
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v37);
      v7 = (Accommodation *)v5;
      goto LABEL_33;
    }
    v22 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v21 + 360LL))(v21);
    v23 = SendMessageW(v22, 0x147u, 0, 0);
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            if ( v26 != 1 )
            {
              v27 = v38[5];
LABEL_22:
              *((_DWORD *)this + 62) = v27;
              *(_QWORD *)&v38[3] = 0;
              v38[2] = 0;
              goto LABEL_26;
            }
            v27 = 2000;
          }
          else
          {
            v27 = 1500;
          }
        }
        else
        {
          v27 = 1000;
        }
      }
      else
      {
        v27 = 700;
      }
    }
    else
    {
      v27 = 500;
    }
    v38[5] = v27;
    goto LABEL_22;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016800  mov     [rsp-28h+arg_10], rbx
0x180016805  push    rbp
0x180016806  push    rsi
0x180016807  push    rdi
0x180016808  push    r14
0x18001680a  push    r15
0x18001680c  mov     rbp, rsp
0x18001680f  sub     rsp, 70h
0x180016813  mov     rax, cs:__security_cookie
0x18001681a  xor     rax, rsp
0x18001681d  mov     [rbp+var_10], rax
0x180016821  mov     rsi, rcx
0x180016824  mov     r15, rdx
0x180016827  lea     rcx, aFilterkeys; "filterkeys"
0x18001682e  xor     edi, edi
0x180016830  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180016835  mov     rbx, rax
0x180016838  test    rax, rax
0x18001683b  jz      loc_180016B1C
0x180016841  mov     rcx, rsi; this
0x180016844  call    ?SaveWarnings@AccessibilityCplCore@@AEAAJXZ; AccessibilityCplCore::SaveWarnings(void)
0x180016849  mov     edi, eax
0x18001684b  mov     rcx, rbx; this
0x18001684e  test    eax, eax
0x180016850  js      loc_180016B17
0x180016856  xorps   xmm0, xmm0
0x180016859  lea     rdx, [rbp+var_28]; void *
0x18001685d  xor     eax, eax
0x18001685f  movups  xmmword ptr [rbp+var_28], xmm0
0x180016863  mov     [rbp+var_18], rax
0x180016867  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x18001686c  cmp     dword ptr [rsi+0C8h], 0
0x180016873  jnz     short loc_180016884
0x180016875  lea     rdx, [rsi+0CCh]; void *
0x18001687c  mov     rcx, rbx; this
0x18001687f  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180016884  mov     rdi, [rsi+60h]
0x180016888  lea     rcx, aFilterkeysshor; "filterkeysShortcut"
0x18001688f  call    cs:__imp_StrToID
0x180016895  movzx   edx, ax
0x180016898  mov     rcx, rdi
0x18001689b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800168a1  test    rax, rax
0x1800168a4  jz      short loc_1800168B8
0x1800168a6  mov     r9d, 4; unsigned int
0x1800168ac  lea     r8, [rbp+var_28+4]; unsigned int *
0x1800168b0  mov     rdx, rax; struct DirectUI::Element *
0x1800168b3  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x1800168b8  mov     rdi, [rsi+60h]
0x1800168bc  lea     rcx, aBouncekeys; "bouncekeys"
0x1800168c3  call    cs:__imp_StrToID
0x1800168c9  movzx   edx, ax
0x1800168cc  mov     rcx, rdi
0x1800168cf  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800168d5  mov     rdi, [rsi+60h]
0x1800168d9  lea     rcx, aSlowkeys; "slowkeys"
0x1800168e0  mov     r14, rax
0x1800168e3  call    cs:__imp_StrToID
0x1800168e9  movzx   edx, ax
0x1800168ec  mov     rcx, rdi
0x1800168ef  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800168f5  mov     rdi, rax
0x1800168f8  test    r14, r14
0x1800168fb  jz      loc_1800169BE
0x180016901  mov     rcx, r14
0x180016904  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001690a  test    al, al
0x18001690c  jz      loc_1800169BE
0x180016912  mov     rdi, [rsi+60h]
0x180016916  lea     rcx, aBouncekeysdela; "bouncekeysdelay"
0x18001691d  call    cs:__imp_StrToID
0x180016923  movzx   edx, ax
0x180016926  mov     rcx, rdi
0x180016929  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001692f  mov     rdx, rax
0x180016932  test    rax, rax
0x180016935  jz      loc_1800169F2
0x18001693b  mov     rcx, [rax]
0x18001693e  mov     rax, [rcx+168h]
0x180016945  mov     rcx, rdx
0x180016948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001694d  mov     rcx, rax; hWnd
0x180016950  xor     r9d, r9d; lParam
0x180016953  xor     r8d, r8d; wParam
0x180016956  mov     edx, 147h; Msg
0x18001695b  call    cs:__imp_SendMessageW
0x180016961  test    rax, rax
0x180016964  jz      short loc_18001699F
0x180016966  sub     rax, 1
0x18001696a  jz      short loc_180016998
0x18001696c  sub     rax, 1
0x180016970  jz      short loc_180016991
0x180016972  sub     rax, 1
0x180016976  jz      short loc_18001698A
0x180016978  cmp     rax, 1
0x18001697c  jnz     short loc_180016985
0x18001697e  mov     eax, 7D0h
0x180016983  jmp     short loc_1800169A4
0x180016985  mov     eax, dword ptr [rbp+var_18+4]
0x180016988  jmp     short loc_1800169A7
0x18001698a  mov     eax, 5DCh
0x18001698f  jmp     short loc_1800169A4
0x180016991  mov     eax, 3E8h
0x180016996  jmp     short loc_1800169A4
0x180016998  mov     eax, 2BCh
0x18001699d  jmp     short loc_1800169A4
0x18001699f  mov     eax, 1F4h
0x1800169a4  mov     dword ptr [rbp+var_18+4], eax
0x1800169a7  mov     [rsi+0F8h], eax
0x1800169ad  mov     qword ptr [rbp+var_28+0Ch], 0
0x1800169b5  mov     [rbp+var_28+8], 0
0x1800169bc  jmp     short loc_1800169F2
0x1800169be  test    rdi, rdi
0x1800169c1  jz      short loc_1800169F2
0x1800169c3  mov     rcx, rdi
0x1800169c6  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800169cc  test    al, al
0x1800169ce  jz      short loc_1800169F2
0x1800169d0  mov     eax, [rsi+0F0h]
0x1800169d6  mov     [rbp+var_28+0Ch], eax
0x1800169d9  mov     eax, [rsi+0F4h]
0x1800169df  mov     dword ptr [rbp+var_18], eax
0x1800169e2  mov     eax, [rsi+0ECh]
0x1800169e8  mov     [rbp+var_28+8], eax
0x1800169eb  mov     dword ptr [rbp+var_18+4], 0
0x1800169f2  mov     rdi, [rsi+60h]
0x1800169f6  lea     rcx, aClick; "click"
0x1800169fd  call    cs:__imp_StrToID
0x180016a03  movzx   edx, ax
0x180016a06  mov     rcx, rdi
0x180016a09  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016a0f  test    rax, rax
0x180016a12  jz      short loc_180016A26
0x180016a14  mov     r9d, 40h ; '@'; unsigned int
0x180016a1a  lea     r8, [rbp+var_28+4]; unsigned int *
0x180016a1e  mov     rdx, rax; struct DirectUI::Element *
0x180016a21  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016a26  mov     rdi, [rsi+60h]
0x180016a2a  lea     rcx, aIndicator; "indicator"
0x180016a31  call    cs:__imp_StrToID
0x180016a37  movzx   edx, ax
0x180016a3a  mov     rcx, rdi
0x180016a3d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016a43  test    rax, rax
0x180016a46  jz      short loc_180016A5A
0x180016a48  mov     r9d, 20h ; ' '; unsigned int
0x180016a4e  lea     r8, [rbp+var_28+4]; unsigned int *
0x180016a52  mov     rdx, rax; struct DirectUI::Element *
0x180016a55  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016a5a  xor     r9d, r9d; int
0x180016a5d  mov     [rsp+70h+var_50], 0; int
0x180016a65  lea     r8, [rbp+var_28]; void *
0x180016a69  mov     rdx, rbx; struct Accommodation *
0x180016a6c  mov     rcx, r15; this
0x180016a6f  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180016a74  mov     r9d, 2001Fh; unsigned int
0x180016a7a  mov     [rbp+var_40], 0
0x180016a82  lea     r8, aControlPanelAc; "Control Panel\\Accessibility\\Keyboard "...
0x180016a89  mov     [rbp+var_38], 0
0x180016a91  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180016a98  mov     [rbp+var_30], 0
0x180016aa0  lea     rcx, [rbp+var_40]; this
0x180016aa4  mov     edi, eax
0x180016aa6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016aab  test    eax, eax
0x180016aad  jnz     short loc_180016B0B
0x180016aaf  mov     r8d, [rsi+0F8h]; unsigned int
0x180016ab6  lea     rdx, aLastBouncekeyS; "Last BounceKey Setting"
0x180016abd  lea     rcx, [rbp+var_40]; this
0x180016ac1  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180016ac6  mov     r8d, [rsi+0F0h]; unsigned int
0x180016acd  lea     rdx, aLastValidDelay; "Last Valid Delay"
0x180016ad4  lea     rcx, [rbp+var_40]; this
0x180016ad8  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180016add  mov     r8d, [rsi+0F4h]; unsigned int
0x180016ae4  lea     rdx, aLastValidRepea; "Last Valid Repeat"
0x180016aeb  lea     rcx, [rbp+var_40]; this
0x180016aef  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180016af4  mov     r8d, [rsi+0ECh]; unsigned int
0x180016afb  lea     rdx, aLastValidWait; "Last Valid Wait"
0x180016b02  lea     rcx, [rbp+var_40]; this
0x180016b06  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180016b0b  lea     rcx, [rbp+var_40]; this
0x180016b0f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016b14  mov     rcx, rbx; this
0x180016b17  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180016b1c  mov     eax, edi
0x180016b1e  mov     rcx, [rbp+var_10]
0x180016b22  xor     rcx, rsp; StackCookie
0x180016b25  call    __security_check_cookie
0x180016b2a  mov     rbx, [rsp+70h+arg_10]
0x180016b32  add     rsp, 70h
0x180016b36  pop     r15
0x180016b38  pop     r14
0x180016b3a  pop     rdi
0x180016b3b  pop     rsi
0x180016b3c  pop     rbp
0x180016b3d  retn
```
