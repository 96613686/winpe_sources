# AccessibilityCplCore::SaveWarnings(void)

- ea: `0x1800178c0`
- end: `0x180017cb9`
- name: `?SaveWarnings@AccessibilityCplCore@@AEAAJXZ`
- size: `1017`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016494`
- `0x180016800`
- `0x180016b44`
- `0x180017114`

## callees

- `0x180004f78`
- `0x1800055c0`
- `0x180014828`
- `0x1800178c0`
- `0x180018260`
- `0x180018294`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179cc`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001798d`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800179ae`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001798d`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800179ae`
- `DUI70!StrToID` at `0x1800178f5`
- `DUI70!StrToID` at `0x180017919`
- `DUI70!StrToID` at `0x1800178f5`
- `DUI70!StrToID` at `0x180017919`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017901`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017925`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017901`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180017925`

## string_xrefs

- `0x180017950`: `Control Panel\Accessibility`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveWarnings(AccessibilityCplCore *this)
{
  DirectUI::Element *v1; // rbx
  unsigned __int16 v3; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v5; // rbx
  DirectUI::Element *v6; // rdi
  unsigned __int16 v7; // ax
  struct DirectUI::Element *v8; // rax
  DirectUI::Element *v9; // rbx
  signed int LastError; // eax
  unsigned int v11; // ebx
  bool Selected; // al
  bool v13; // al
  signed int v14; // eax
  int v16; // r12d
  const wchar_t **v17; // r15
  const wchar_t **v18; // rbx
  const wchar_t **v19; // rsi
  Accommodation *v20; // r14
  struct Accommodation *v21; // rax
  unsigned int v22; // edx
  const wchar_t **v23; // rdi
  struct DirectUI::Element *v24; // r12
  AccessibilityCplCore *v25; // rcx
  AccessibilityCplCore *v26; // rcx
  AccessibilityCplCore *v27; // rcx
  AccessibilityCplCore *v28; // rcx
  AccessibilityCplCore *v29; // rcx
  struct DirectUI::Element *v30; // r12
  AccessibilityCplCore *v31; // rcx
  AccessibilityCplCore *v32; // rcx
  AccessibilityCplCore *v33; // rcx
  AccessibilityCplCore *v34; // rcx
  AccessibilityCplCore *v35; // rcx
  Start *v36; // rcx
  unsigned int v37[2]; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v38[2]; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-69h]
  unsigned int v40[4]; // [rsp+48h] [rbp-61h] BYREF
  HKEY v41[3]; // [rsp+58h] [rbp-51h] BYREF
  struct DirectUI::Element *v42; // [rsp+70h] [rbp-39h]
  struct DirectUI::Element *v43; // [rsp+78h] [rbp-31h]
  unsigned int v44[4]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v45; // [rsp+90h] [rbp-19h]
  UINT v46[8]; // [rsp+98h] [rbp-11h] BYREF

  v1 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v3 = StrToID(L"warningmessage");
  Descendent = DirectUI::Element::FindDescendent(v1, v3);
  v5 = (DirectUI::Element *)*((_QWORD *)this + 12);
  v6 = Descendent;
  v42 = Descendent;
  v7 = StrToID(L"warningsound");
  v8 = DirectUI::Element::FindDescendent(v5, v7);
  v43 = v8;
  v9 = v8;
  if ( !v6 || !v8 )
    return 2147500037LL;
  memset(v41, 0, sizeof(v41));
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v41,
                       HKEY_CURRENT_USER,
                       L"Control Panel\\Accessibility",
                       0x2001Fu) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
    ATL::CRegKey::Close((ATL::CRegKey *)v41);
    return v11;
  }
  Selected = DirectUI::Element::GetSelected(v9);
  if ( ATL::CRegKey::SetDWORDValue(v41, L"Sound on Activation", Selected)
    || (v13 = DirectUI::Element::GetSelected(v6), ATL::CRegKey::SetDWORDValue(v41, L"Warning Sounds", v13)) )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v11 = v14;
    goto LABEL_11;
  }
  v16 = 0;
  v17 = (const wchar_t **)Accommodation::Open(L"filterkeys");
  v18 = (const wchar_t **)Accommodation::Open(L"mousekeys");
  v19 = (const wchar_t **)Accommodation::Open(L"stickykeys");
  v20 = Accommodation::Open(L"togglekeys");
  v21 = Accommodation::Open(L"highcontrast");
  v23 = (const wchar_t **)v21;
  if ( v17 && v18 && v19 && v20 )
  {
    if ( !v21 )
    {
LABEL_26:
      Accommodation::`scalar deleting destructor'(v20, v22);
      goto LABEL_27;
    }
    v45 = 0;
    *(_QWORD *)v37 = 0;
    memset(v46, 0, 28);
    *(_QWORD *)v38 = 0;
    *(_OWORD *)v44 = 0;
    *(_OWORD *)v40 = 0;
    Accommodation::GetData(v17, v44);
    Accommodation::GetData(v23, v40);
    Accommodation::GetData(v18, v46);
    Accommodation::GetData(v19, v37);
    Accommodation::GetData((const wchar_t **)v20, v38);
    v24 = v42;
    v39 = v40[1];
    AccessibilityCplCore::SetFlagBasedOnSelection(v25, v42, &v44[1], 8u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v26, v24, &v46[1], 8u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v27, v24, &v37[1], 8u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v28, v24, &v38[1], 8u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v29, v24, &v40[1], 8u);
    v30 = v43;
    AccessibilityCplCore::SetFlagBasedOnSelection(v31, v43, &v44[1], 0x10u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v32, v30, &v46[1], 0x10u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v33, v30, &v37[1], 0x10u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v34, v30, &v38[1], 0x10u);
    AccessibilityCplCore::SetFlagBasedOnSelection(v35, v30, &v40[1], 0x10u);
    v16 = (unsigned int)StartList::Start(*((Start **)this + 11), v17, v44, 0, 0);
    if ( v16 >= 0 )
    {
      v16 = (unsigned int)StartList::Start(*((Start **)this + 11), v18, v46, 0, 0);
      if ( v16 >= 0 )
      {
        v16 = (unsigned int)StartList::Start(*((Start **)this + 11), v19, v37, 0, 0);
        if ( v16 >= 0 )
        {
          v16 = (unsigned int)StartList::Start(*((Start **)this + 11), (const wchar_t **)v20, v38, 0, 0);
          if ( v16 >= 0 && v39 != v40[1] )
          {
            v36 = (Start *)*((_QWORD *)this + 11);
            v40[1] |= 0x1000u;
            StartList::Start(v36, v23, v40, 0, 0);
          }
        }
      }
    }
  }
  else if ( !v21 )
  {
    goto LABEL_25;
  }
  Accommodation::`scalar deleting destructor'((Accommodation *)v23, v22);
LABEL_25:
  if ( v20 )
    goto LABEL_26;
LABEL_27:
  if ( v19 )
    Accommodation::`scalar deleting destructor'((Accommodation *)v19, v22);
  if ( v18 )
    Accommodation::`scalar deleting destructor'((Accommodation *)v18, v22);
  if ( v17 )
    Accommodation::`scalar deleting destructor'((Accommodation *)v17, v22);
  ATL::CRegKey::Close((ATL::CRegKey *)v41);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800178c0  push    rbp
0x1800178c2  push    rbx
0x1800178c3  push    rsi
0x1800178c4  push    rdi
0x1800178c5  push    r12
0x1800178c7  push    r13
0x1800178c9  push    r14
0x1800178cb  push    r15
0x1800178cd  lea     rbp, [rsp-1Fh]
0x1800178d2  sub     rsp, 0C8h
0x1800178d9  mov     rax, cs:__security_cookie
0x1800178e0  xor     rax, rsp
0x1800178e3  mov     [rbp+57h+var_48], rax
0x1800178e7  mov     rbx, [rcx+60h]
0x1800178eb  mov     r13, rcx
0x1800178ee  lea     rcx, aWarningmessage; "warningmessage"
0x1800178f5  call    cs:__imp_StrToID
0x1800178fb  movzx   edx, ax
0x1800178fe  mov     rcx, rbx
0x180017901  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017907  mov     rbx, [r13+60h]
0x18001790b  lea     rcx, aWarningsound; "warningsound"
0x180017912  mov     rdi, rax
0x180017915  mov     [rbp+57h+var_90], rax
0x180017919  call    cs:__imp_StrToID
0x18001791f  movzx   edx, ax
0x180017922  mov     rcx, rbx
0x180017925  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001792b  xor     esi, esi
0x18001792d  mov     [rbp+57h+var_88], rax
0x180017931  mov     rbx, rax
0x180017934  test    rdi, rdi
0x180017937  jz      loc_180017C94
0x18001793d  test    rax, rax
0x180017940  jz      loc_180017C94
0x180017946  mov     r9d, 2001Fh; unsigned int
0x18001794c  mov     [rbp+57h+var_A8], rsi
0x180017950  lea     r8, aControlPanelAc_1; "Control Panel\\Accessibility"
0x180017957  mov     [rbp+57h+var_A0], rsi
0x18001795b  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180017962  mov     [rbp+57h+var_98], rsi
0x180017966  lea     rcx, [rbp+57h+var_A8]; this
0x18001796a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001796f  test    eax, eax
0x180017971  jz      short loc_18001798A
0x180017973  call    cs:__imp_GetLastError
0x180017979  mov     ebx, eax
0x18001797b  test    eax, eax
0x18001797d  jle     short loc_1800179E0
0x18001797f  movzx   ebx, ax
0x180017982  or      ebx, 80070000h
0x180017988  jmp     short loc_1800179E0
0x18001798a  mov     rcx, rbx
0x18001798d  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180017993  movzx   r8d, al; unsigned int
0x180017997  lea     rdx, aSoundOnActivat; "Sound on Activation"
0x18001799e  lea     rcx, [rbp+57h+var_A8]; this
0x1800179a2  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800179a7  test    eax, eax
0x1800179a9  jnz     short loc_1800179CC
0x1800179ab  mov     rcx, rdi
0x1800179ae  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800179b4  movzx   r8d, al; unsigned int
0x1800179b8  lea     rdx, aWarningSounds; "Warning Sounds"
0x1800179bf  lea     rcx, [rbp+57h+var_A8]; this
0x1800179c3  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800179c8  test    eax, eax
0x1800179ca  jz      short loc_1800179F0
0x1800179cc  call    cs:__imp_GetLastError
0x1800179d2  test    eax, eax
0x1800179d4  jle     short loc_1800179DE
0x1800179d6  movzx   eax, ax
0x1800179d9  or      eax, 80070000h
0x1800179de  mov     ebx, eax
0x1800179e0  lea     rcx, [rbp+57h+var_A8]; this
0x1800179e4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800179e9  mov     eax, ebx
0x1800179eb  jmp     loc_180017C99
0x1800179f0  lea     rcx, aFilterkeys; "filterkeys"
0x1800179f7  mov     r12d, esi
0x1800179fa  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800179ff  lea     rcx, aMousekeys; "mousekeys"
0x180017a06  mov     r15, rax
0x180017a09  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017a0e  lea     rcx, aStickykeys; "stickykeys"
0x180017a15  mov     rbx, rax
0x180017a18  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017a1d  lea     rcx, aTogglekeys; "togglekeys"
0x180017a24  mov     rsi, rax
0x180017a27  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017a2c  lea     rcx, aHighcontrast; "highcontrast"
0x180017a33  mov     r14, rax
0x180017a36  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017a3b  mov     rdi, rax
0x180017a3e  test    r15, r15
0x180017a41  jz      loc_180017C45
0x180017a47  test    rbx, rbx
0x180017a4a  jz      loc_180017C45
0x180017a50  test    rsi, rsi
0x180017a53  jz      loc_180017C45
0x180017a59  test    r14, r14
0x180017a5c  jz      loc_180017C45
0x180017a62  test    rax, rax
0x180017a65  jz      loc_180017C57
0x180017a6b  xor     eax, eax
0x180017a6d  lea     rdx, [rbp+57h+var_80]; void *
0x180017a71  xorps   xmm1, xmm1
0x180017a74  mov     [rbp+57h+var_70], rax
0x180017a78  xorps   xmm0, xmm0
0x180017a7b  mov     qword ptr [rbp+57h+var_D0], rax
0x180017a7f  movups  xmmword ptr [rbp+57h+var_68], xmm1
0x180017a83  mov     rcx, r15; this
0x180017a86  mov     qword ptr [rbp+57h+var_C8], rax
0x180017a8a  movups  xmmword ptr [rbp+57h+var_68+0Ch], xmm1
0x180017a8e  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180017a92  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180017a96  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017a9b  lea     rdx, [rbp+57h+var_B8]; void *
0x180017a9f  mov     rcx, rdi; this
0x180017aa2  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017aa7  lea     rdx, [rbp+57h+var_68]; void *
0x180017aab  mov     rcx, rbx; this
0x180017aae  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017ab3  lea     rdx, [rbp+57h+var_D0]; void *
0x180017ab7  mov     rcx, rsi; this
0x180017aba  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017abf  lea     rdx, [rbp+57h+var_C8]; void *
0x180017ac3  mov     rcx, r14; this
0x180017ac6  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180017acb  mov     eax, [rbp+57h+var_B8+4]
0x180017ace  lea     r8, [rbp+57h+var_80+4]; unsigned int *
0x180017ad2  mov     r12, [rbp+57h+var_90]
0x180017ad6  mov     r9d, 8; unsigned int
0x180017adc  mov     rdx, r12; struct DirectUI::Element *
0x180017adf  mov     [rbp+57h+var_C0], eax
0x180017ae2  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017ae7  mov     r9d, 8; unsigned int
0x180017aed  lea     r8, [rbp+57h+var_68+4]; unsigned int *
0x180017af1  mov     rdx, r12; struct DirectUI::Element *
0x180017af4  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017af9  mov     r9d, 8; unsigned int
0x180017aff  lea     r8, [rbp+57h+var_D0+4]; unsigned int *
0x180017b03  mov     rdx, r12; struct DirectUI::Element *
0x180017b06  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b0b  mov     r9d, 8; unsigned int
0x180017b11  lea     r8, [rbp+57h+var_C8+4]; unsigned int *
0x180017b15  mov     rdx, r12; struct DirectUI::Element *
0x180017b18  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b1d  mov     r9d, 8; unsigned int
0x180017b23  lea     r8, [rbp+57h+var_B8+4]; unsigned int *
0x180017b27  mov     rdx, r12; struct DirectUI::Element *
0x180017b2a  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b2f  mov     r12, [rbp+57h+var_88]
0x180017b33  lea     r8, [rbp+57h+var_80+4]; unsigned int *
0x180017b37  mov     rdx, r12; struct DirectUI::Element *
0x180017b3a  mov     r9d, 10h; unsigned int
0x180017b40  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b45  mov     r9d, 10h; unsigned int
0x180017b4b  lea     r8, [rbp+57h+var_68+4]; unsigned int *
0x180017b4f  mov     rdx, r12; struct DirectUI::Element *
0x180017b52  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b57  mov     r9d, 10h; unsigned int
0x180017b5d  lea     r8, [rbp+57h+var_D0+4]; unsigned int *
0x180017b61  mov     rdx, r12; struct DirectUI::Element *
0x180017b64  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b69  mov     r9d, 10h; unsigned int
0x180017b6f  lea     r8, [rbp+57h+var_C8+4]; unsigned int *
0x180017b73  mov     rdx, r12; struct DirectUI::Element *
0x180017b76  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b7b  mov     r9d, 10h; unsigned int
0x180017b81  lea     r8, [rbp+57h+var_B8+4]; unsigned int *
0x180017b85  mov     rdx, r12; struct DirectUI::Element *
0x180017b88  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180017b8d  mov     rcx, [r13+58h]; this
0x180017b91  lea     r8, [rbp+57h+var_80]; void *
0x180017b95  xor     r9d, r9d; int
0x180017b98  mov     [rsp+100h+var_E0], 0; int
0x180017ba0  mov     rdx, r15; struct Accommodation *
0x180017ba3  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017ba8  mov     r12d, eax
0x180017bab  test    eax, eax
0x180017bad  js      loc_180017C4A
0x180017bb3  mov     rcx, [r13+58h]; this
0x180017bb7  lea     r8, [rbp+57h+var_68]; void *
0x180017bbb  xor     r9d, r9d; int
0x180017bbe  mov     [rsp+100h+var_E0], 0; int
0x180017bc6  mov     rdx, rbx; struct Accommodation *
0x180017bc9  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017bce  mov     r12d, eax
0x180017bd1  test    eax, eax
0x180017bd3  js      short loc_180017C4A
0x180017bd5  mov     rcx, [r13+58h]; this
0x180017bd9  lea     r8, [rbp+57h+var_D0]; void *
0x180017bdd  xor     r9d, r9d; int
0x180017be0  mov     [rsp+100h+var_E0], 0; int
0x180017be8  mov     rdx, rsi; struct Accommodation *
0x180017beb  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017bf0  mov     r12d, eax
0x180017bf3  test    eax, eax
0x180017bf5  js      short loc_180017C4A
0x180017bf7  mov     rcx, [r13+58h]; this
0x180017bfb  lea     r8, [rbp+57h+var_C8]; void *
0x180017bff  xor     r9d, r9d; int
0x180017c02  mov     [rsp+100h+var_E0], 0; int
0x180017c0a  mov     rdx, r14; struct Accommodation *
0x180017c0d  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017c12  mov     r12d, eax
0x180017c15  test    eax, eax
0x180017c17  js      short loc_180017C4A
0x180017c19  mov     eax, [rbp+57h+var_B8+4]
0x180017c1c  cmp     [rbp+57h+var_C0], eax
0x180017c1f  jz      short loc_180017C4A
0x180017c21  mov     rcx, [r13+58h]; this
0x180017c25  lea     r8, [rbp+57h+var_B8]; void *
0x180017c29  bts     eax, 0Ch
0x180017c2d  mov     [rsp+100h+var_E0], 0; int
0x180017c35  xor     r9d, r9d; int
0x180017c38  mov     [rbp+57h+var_B8+4], eax
0x180017c3b  mov     rdx, rdi; struct Accommodation *
0x180017c3e  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017c43  jmp     short loc_180017C4A
0x180017c45  test    rdi, rdi
0x180017c48  jz      short loc_180017C52
0x180017c4a  mov     rcx, rdi; this
0x180017c4d  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017c52  test    r14, r14
0x180017c55  jz      short loc_180017C5F
0x180017c57  mov     rcx, r14; this
0x180017c5a  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017c5f  test    rsi, rsi
0x180017c62  jz      short loc_180017C6C
0x180017c64  mov     rcx, rsi; this
0x180017c67  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017c6c  test    rbx, rbx
0x180017c6f  jz      short loc_180017C79
0x180017c71  mov     rcx, rbx; this
0x180017c74  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017c79  test    r15, r15
0x180017c7c  jz      short loc_180017C86
0x180017c7e  mov     rcx, r15; this
0x180017c81  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017c86  lea     rcx, [rbp+57h+var_A8]; this
0x180017c8a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017c8f  mov     eax, r12d
0x180017c92  jmp     short loc_180017C99
0x180017c94  mov     eax, 80004005h
0x180017c99  mov     rcx, [rbp+57h+var_48]
0x180017c9d  xor     rcx, rsp; StackCookie
0x180017ca0  call    __security_check_cookie
0x180017ca5  add     rsp, 0C8h
0x180017cac  pop     r15
0x180017cae  pop     r14
0x180017cb0  pop     r13
0x180017cb2  pop     r12
0x180017cb4  pop     rdi
0x180017cb5  pop     rsi
0x180017cb6  pop     rbx
0x180017cb7  pop     rbp
0x180017cb8  retn
```
