# AccessibilityCplCore::SavePageMouseKeysSettings(void)

- ea: `0x180016b44`
- end: `0x180016d67`
- name: `?SavePageMouseKeysSettings@AccessibilityCplCore@@AEAAJXZ`
- size: `547`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800134a0`

## callees

- `0x180004f78`
- `0x180016b44`
- `0x1800178c0`
- `0x180018294`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `USER32!SendMessageW` at `0x180016c24`
- `USER32!SendMessageW` at `0x180016c78`
- `USER32!SendMessageW` at `0x180016c24`
- `USER32!SendMessageW` at `0x180016c78`
- `DUI70!StrToID` at `0x180016bb0`
- `DUI70!StrToID` at `0x180016be5`
- `DUI70!StrToID` at `0x180016c3e`
- `DUI70!StrToID` at `0x180016c95`
- `DUI70!StrToID` at `0x180016cca`
- `DUI70!StrToID` at `0x180016cff`
- `DUI70!StrToID` at `0x180016bb0`
- `DUI70!StrToID` at `0x180016be5`
- `DUI70!StrToID` at `0x180016c3e`
- `DUI70!StrToID` at `0x180016c95`
- `DUI70!StrToID` at `0x180016cca`
- `DUI70!StrToID` at `0x180016cff`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016bbc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016bf1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016c4a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016ca1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016cd6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016d0b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016bbc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016bf1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016c4a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016ca1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016cd6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016d0b`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SavePageMouseKeysSettings(Start **this)
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
  HWND v12; // rax
  DirectUI::Element *v13; // rdi
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rax
  HWND v16; // rax
  DirectUI::Element *v17; // rdi
  unsigned __int16 v18; // ax
  struct DirectUI::Element *v19; // rax
  AccessibilityCplCore *v20; // rcx
  DirectUI::Element *v21; // rdi
  unsigned __int16 v22; // ax
  struct DirectUI::Element *v23; // rax
  AccessibilityCplCore *v24; // rcx
  DirectUI::Element *v25; // rdi
  unsigned __int16 v26; // ax
  struct DirectUI::Element *v27; // rax
  AccessibilityCplCore *v28; // rcx
  UINT v30[8]; // [rsp+30h] [rbp-58h] BYREF

  v2 = 0;
  v3 = (const wchar_t **)Accommodation::Open(L"mousekeys");
  if ( v3 )
  {
    v2 = AccessibilityCplCore::SaveWarnings((AccessibilityCplCore *)this);
    v4 = (Accommodation *)v3;
    if ( v2 >= 0 )
    {
      memset(v30, 0, 28);
      Accommodation::GetData(v3, v30);
      v5 = this[12];
      v6 = StrToID(L"mousekeysshortcut");
      Descendent = DirectUI::Element::FindDescendent(v5, v6);
      if ( Descendent )
        AccessibilityCplCore::SetFlagBasedOnSelection(v8, Descendent, &v30[1], 4u);
      v9 = this[12];
      v10 = StrToID(L"maxspeed");
      v11 = DirectUI::Element::FindDescendent(v9, v10);
      if ( v11 )
      {
        v12 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v11 + 360LL))(v11);
        v30[2] = 29 * SendMessageW(v12, 0x400u, 0, 0) + 10;
      }
      v13 = this[12];
      v14 = StrToID(L"timetomaxspeed");
      v15 = DirectUI::Element::FindDescendent(v13, v14);
      if ( v15 )
      {
        v16 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v15 + 360LL))(v15);
        v30[3] = 500 * (10 - SendMessageW(v16, 0x400u, 0, 0));
      }
      v17 = this[12];
      v18 = StrToID(L"changespeed");
      v19 = DirectUI::Element::FindDescendent(v17, v18);
      if ( v19 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v20, v19, &v30[1], 0x40u);
      v21 = this[12];
      v22 = StrToID(L"numLockoff");
      v23 = DirectUI::Element::FindDescendent(v21, v22);
      if ( v23 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v24, v23, &v30[1], 0x80u);
      v25 = this[12];
      v26 = StrToID(L"showstatus");
      v27 = DirectUI::Element::FindDescendent(v25, v26);
      if ( v27 )
        AccessibilityCplCore::SetFlagBasedOnSelection(v28, v27, &v30[1], 0x20u);
      v2 = (unsigned int)StartList::Start(this[11], v3, v30, 0, 0);
      v4 = (Accommodation *)v3;
    }
    Accommodation::`scalar deleting destructor'(v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180016b44  push    rbx
0x180016b46  push    rbp
0x180016b47  push    rsi
0x180016b48  push    rdi
0x180016b49  sub     rsp, 68h
0x180016b4d  mov     rax, cs:__security_cookie
0x180016b54  xor     rax, rsp
0x180016b57  mov     [rsp+88h+var_38], rax
0x180016b5c  mov     rsi, rcx
0x180016b5f  xor     edi, edi
0x180016b61  lea     rcx, aMousekeys; "mousekeys"
0x180016b68  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180016b6d  mov     rbx, rax
0x180016b70  test    rax, rax
0x180016b73  jz      loc_180016D4F
0x180016b79  mov     rcx, rsi; this
0x180016b7c  call    ?SaveWarnings@AccessibilityCplCore@@AEAAJXZ; AccessibilityCplCore::SaveWarnings(void)
0x180016b81  mov     edi, eax
0x180016b83  mov     rcx, rbx; this
0x180016b86  test    eax, eax
0x180016b88  js      loc_180016D4A
0x180016b8e  xorps   xmm0, xmm0
0x180016b91  lea     rdx, [rsp+88h+var_58]; void *
0x180016b96  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x180016b9b  movups  xmmword ptr [rsp+88h+var_58+0Ch], xmm0
0x180016ba0  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180016ba5  mov     rdi, [rsi+60h]
0x180016ba9  lea     rcx, aMousekeysshort; "mousekeysshortcut"
0x180016bb0  call    cs:__imp_StrToID
0x180016bb6  movzx   edx, ax
0x180016bb9  mov     rcx, rdi
0x180016bbc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016bc2  test    rax, rax
0x180016bc5  jz      short loc_180016BDA
0x180016bc7  mov     r9d, 4; unsigned int
0x180016bcd  lea     r8, [rsp+88h+var_58+4]; unsigned int *
0x180016bd2  mov     rdx, rax; struct DirectUI::Element *
0x180016bd5  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016bda  mov     rdi, [rsi+60h]
0x180016bde  lea     rcx, aMaxspeed; "maxspeed"
0x180016be5  call    cs:__imp_StrToID
0x180016beb  movzx   edx, ax
0x180016bee  mov     rcx, rdi
0x180016bf1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016bf7  mov     rdx, rax
0x180016bfa  mov     ebp, 0Ah
0x180016bff  test    rax, rax
0x180016c02  jz      short loc_180016C33
0x180016c04  mov     rcx, [rax]
0x180016c07  mov     rax, [rcx+168h]
0x180016c0e  mov     rcx, rdx
0x180016c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c16  mov     rcx, rax; hWnd
0x180016c19  xor     r9d, r9d; lParam
0x180016c1c  xor     r8d, r8d; wParam
0x180016c1f  mov     edx, 400h; Msg
0x180016c24  call    cs:__imp_SendMessageW
0x180016c2a  imul    ecx, eax, 1Dh
0x180016c2d  add     ecx, ebp
0x180016c2f  mov     [rsp+88h+var_58+8], ecx
0x180016c33  mov     rdi, [rsi+60h]
0x180016c37  lea     rcx, aTimetomaxspeed; "timetomaxspeed"
0x180016c3e  call    cs:__imp_StrToID
0x180016c44  movzx   edx, ax
0x180016c47  mov     rcx, rdi
0x180016c4a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016c50  mov     r8, rax
0x180016c53  test    rax, rax
0x180016c56  jz      short loc_180016C8A
0x180016c58  mov     rcx, [rax]
0x180016c5b  mov     rax, [rcx+168h]
0x180016c62  mov     rcx, r8
0x180016c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c6a  mov     rcx, rax; hWnd
0x180016c6d  xor     r9d, r9d; lParam
0x180016c70  xor     r8d, r8d; wParam
0x180016c73  mov     edx, 400h; Msg
0x180016c78  call    cs:__imp_SendMessageW
0x180016c7e  sub     ebp, eax
0x180016c80  imul    eax, ebp, 1F4h
0x180016c86  mov     [rsp+88h+var_58+0Ch], eax
0x180016c8a  mov     rdi, [rsi+60h]
0x180016c8e  lea     rcx, aChangespeed; "changespeed"
0x180016c95  call    cs:__imp_StrToID
0x180016c9b  movzx   edx, ax
0x180016c9e  mov     rcx, rdi
0x180016ca1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016ca7  test    rax, rax
0x180016caa  jz      short loc_180016CBF
0x180016cac  mov     r9d, 40h ; '@'; unsigned int
0x180016cb2  lea     r8, [rsp+88h+var_58+4]; unsigned int *
0x180016cb7  mov     rdx, rax; struct DirectUI::Element *
0x180016cba  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016cbf  mov     rdi, [rsi+60h]
0x180016cc3  lea     rcx, aNumlockoff_0; "numLockoff"
0x180016cca  call    cs:__imp_StrToID
0x180016cd0  movzx   edx, ax
0x180016cd3  mov     rcx, rdi
0x180016cd6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016cdc  test    rax, rax
0x180016cdf  jz      short loc_180016CF4
0x180016ce1  mov     r9d, 80h; unsigned int
0x180016ce7  lea     r8, [rsp+88h+var_58+4]; unsigned int *
0x180016cec  mov     rdx, rax; struct DirectUI::Element *
0x180016cef  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016cf4  mov     rdi, [rsi+60h]
0x180016cf8  lea     rcx, aShowstatus; "showstatus"
0x180016cff  call    cs:__imp_StrToID
0x180016d05  movzx   edx, ax
0x180016d08  mov     rcx, rdi
0x180016d0b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016d11  test    rax, rax
0x180016d14  jz      short loc_180016D29
0x180016d16  mov     r9d, 20h ; ' '; unsigned int
0x180016d1c  lea     r8, [rsp+88h+var_58+4]; unsigned int *
0x180016d21  mov     rdx, rax; struct DirectUI::Element *
0x180016d24  call    ?SetFlagBasedOnSelection@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@PEAKK@Z; AccessibilityCplCore::SetFlagBasedOnSelection(DirectUI::Element *,ulong *,ulong)
0x180016d29  mov     rcx, [rsi+58h]; this
0x180016d2d  lea     r8, [rsp+88h+var_58]; void *
0x180016d32  xor     r9d, r9d; int
0x180016d35  mov     [rsp+88h+var_68], 0; int
0x180016d3d  mov     rdx, rbx; struct Accommodation *
0x180016d40  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180016d45  mov     edi, eax
0x180016d47  mov     rcx, rbx; this
0x180016d4a  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180016d4f  mov     eax, edi
0x180016d51  mov     rcx, [rsp+88h+var_38]
0x180016d56  xor     rcx, rsp; StackCookie
0x180016d59  call    __security_check_cookie
0x180016d5e  add     rsp, 68h
0x180016d62  pop     rdi
0x180016d63  pop     rsi
0x180016d64  pop     rbp
0x180016d65  pop     rbx
0x180016d66  retn
```
