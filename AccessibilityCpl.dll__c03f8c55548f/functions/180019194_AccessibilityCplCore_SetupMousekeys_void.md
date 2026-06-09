# AccessibilityCplCore::SetupMousekeys(void)

- ea: `0x180019194`
- end: `0x1800193c0`
- name: `?SetupMousekeys@AccessibilityCplCore@@AEAAXXZ`
- size: `556`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`
- `0x1800198f4`

## callees

- `0x180004f78`
- `0x180019194`
- `0x18001a340`
- `0x180020d64`
- `0x180020edc`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `USER32!SendMessageW` at `0x18001927a`
- `USER32!SendMessageW` at `0x1800192d8`
- `USER32!SendMessageW` at `0x18001927a`
- `USER32!SendMessageW` at `0x1800192d8`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001920f`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001930c`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180019368`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001939c`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001920f`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001930c`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180019368`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001939c`
- `DUI70!StrToID` at `0x1800191f3`
- `DUI70!StrToID` at `0x180019228`
- `DUI70!StrToID` at `0x18001928b`
- `DUI70!StrToID` at `0x1800192f0`
- `DUI70!StrToID` at `0x18001931d`
- `DUI70!StrToID` at `0x18001933d`
- `DUI70!StrToID` at `0x180019380`
- `DUI70!StrToID` at `0x1800191f3`
- `DUI70!StrToID` at `0x180019228`
- `DUI70!StrToID` at `0x18001928b`
- `DUI70!StrToID` at `0x1800192f0`
- `DUI70!StrToID` at `0x18001931d`
- `DUI70!StrToID` at `0x18001933d`
- `DUI70!StrToID` at `0x180019380`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800191ff`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019234`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019297`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800192fc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019329`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019349`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001938c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800191ff`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019234`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019297`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800192fc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019329`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019349`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001938c`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupMousekeys(AccessibilityCplCore *this)
{
  const wchar_t **v2; // rax
  Accommodation *v3; // rbx
  DirectUI::Element *v4; // rdi
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v7; // rdi
  unsigned __int16 v8; // ax
  struct DirectUI::Element *v9; // rax
  unsigned int v10; // edi
  HWND v11; // rax
  DirectUI::Element *v12; // rdi
  unsigned __int16 v13; // ax
  struct DirectUI::Element *v14; // rax
  unsigned int v15; // edi
  HWND v16; // rax
  DirectUI::Element *v17; // rdi
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // rax
  DirectUI::Element *v20; // rdi
  unsigned __int16 v21; // ax
  struct DirectUI::Element *v22; // rax
  DirectUI::Element *v23; // rdi
  DirectUI::Element *v24; // rbp
  unsigned __int16 v25; // ax
  struct DirectUI::Element *v26; // rax
  DirectUI::Element *v27; // rcx
  DirectUI::Element *v28; // rdi
  unsigned __int16 v29; // ax
  DirectUI::Element *v30; // rax
  _DWORD v31[8]; // [rsp+20h] [rbp-58h] BYREF

  v2 = (const wchar_t **)Accommodation::Open(L"mousekeys");
  v3 = (Accommodation *)v2;
  if ( v2 )
  {
    memset(v31, 0, 28);
    Accommodation::GetData(v2, v31);
    if ( (v31[1] & 4) != 0 )
    {
      v4 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v5 = StrToID(L"mousekeysshortcut");
      Descendent = DirectUI::Element::FindDescendent(v4, v5);
      if ( Descendent )
        DirectUI::Element::SetSelected(Descendent, 1);
    }
    AccessibilityCplCore::SetupWarnings(this);
    v7 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v8 = StrToID(L"maxspeed");
    v9 = DirectUI::Element::FindDescendent(v7, v8);
    if ( v9 )
    {
      v10 = (v31[2] - 10) / 0x1Du;
      v11 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v9 + 360LL))(v9);
      SendMessageW(v11, 0x405u, 1u, v10);
    }
    v12 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v13 = StrToID(L"timetomaxspeed");
    v14 = DirectUI::Element::FindDescendent(v12, v13);
    if ( v14 )
    {
      v15 = 10 - v31[3] / 0x1F4u;
      v16 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v14 + 360LL))(v14);
      SendMessageW(v16, 0x405u, 1u, v15);
    }
    if ( (v31[1] & 0x40) != 0 )
    {
      v17 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v18 = StrToID(L"changespeed");
      v19 = DirectUI::Element::FindDescendent(v17, v18);
      if ( v19 )
        DirectUI::Element::SetSelected(v19, 1);
    }
    v20 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v21 = StrToID(L"numlockon");
    v22 = DirectUI::Element::FindDescendent(v20, v21);
    v23 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v24 = v22;
    v25 = StrToID(L"numlockoff");
    v26 = DirectUI::Element::FindDescendent(v23, v25);
    if ( v24 && v26 )
    {
      v27 = v26;
      if ( SLOBYTE(v31[1]) >= 0 )
        v27 = v24;
      DirectUI::Element::SetSelected(v27, 1);
    }
    if ( (v31[1] & 0x20) != 0 )
    {
      v28 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v29 = StrToID(L"showstatus");
      v30 = DirectUI::Element::FindDescendent(v28, v29);
      if ( v30 )
        DirectUI::Element::SetSelected(v30, 1);
    }
    Accommodation::`scalar deleting destructor'(v3);
  }
}

```

## disassembly

```asm
0x180019194  push    rbx
0x180019196  push    rbp
0x180019197  push    rsi
0x180019198  push    rdi
0x180019199  sub     rsp, 58h
0x18001919d  mov     rax, cs:__security_cookie
0x1800191a4  xor     rax, rsp
0x1800191a7  mov     [rsp+78h+var_38], rax
0x1800191ac  mov     rsi, rcx
0x1800191af  lea     rcx, aMousekeys; "mousekeys"
0x1800191b6  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800191bb  mov     rbx, rax
0x1800191be  test    rax, rax
0x1800191c1  jz      loc_1800193AA
0x1800191c7  xorps   xmm0, xmm0
0x1800191ca  lea     rdx, [rsp+78h+var_58]; void *
0x1800191cf  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x1800191d4  mov     rcx, rax; this
0x1800191d7  movups  xmmword ptr [rsp+78h+var_58+0Ch], xmm0
0x1800191dc  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x1800191e1  test    [rsp+78h+var_58+4], 4
0x1800191e6  jz      short loc_180019215
0x1800191e8  mov     rdi, [rsi+60h]
0x1800191ec  lea     rcx, aMousekeysshort; "mousekeysshortcut"
0x1800191f3  call    cs:__imp_StrToID
0x1800191f9  movzx   edx, ax
0x1800191fc  mov     rcx, rdi
0x1800191ff  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019205  test    rax, rax
0x180019208  jz      short loc_180019215
0x18001920a  mov     dl, 1
0x18001920c  mov     rcx, rax
0x18001920f  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180019215  mov     rcx, rsi; this
0x180019218  call    ?SetupWarnings@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupWarnings(void)
0x18001921d  mov     rdi, [rsi+60h]
0x180019221  lea     rcx, aMaxspeed; "maxspeed"
0x180019228  call    cs:__imp_StrToID
0x18001922e  movzx   edx, ax
0x180019231  mov     rcx, rdi
0x180019234  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001923a  mov     r8, rax
0x18001923d  mov     ebp, 405h
0x180019242  test    rax, rax
0x180019245  jz      short loc_180019280
0x180019247  mov     ecx, dword ptr [rsp+78h+var_58+8]
0x18001924b  mov     eax, 8D3DCB09h
0x180019250  add     ecx, 0FFFFFFF6h
0x180019253  mul     ecx
0x180019255  mov     rcx, [r8]
0x180019258  shr     edx, 4
0x18001925b  mov     edi, edx
0x18001925d  mov     rax, [rcx+168h]
0x180019264  mov     rcx, r8
0x180019267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001926c  mov     rcx, rax; hWnd
0x18001926f  mov     r9d, edi; lParam
0x180019272  mov     r8d, 1; wParam
0x180019278  mov     edx, ebp; Msg
0x18001927a  call    cs:__imp_SendMessageW
0x180019280  mov     rdi, [rsi+60h]
0x180019284  lea     rcx, aTimetomaxspeed; "timetomaxspeed"
0x18001928b  call    cs:__imp_StrToID
0x180019291  movzx   edx, ax
0x180019294  mov     rcx, rdi
0x180019297  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001929d  mov     r8, rax
0x1800192a0  test    rax, rax
0x1800192a3  jz      short loc_1800192DE
0x1800192a5  mov     rcx, [r8]
0x1800192a8  mov     eax, 10624DD3h
0x1800192ad  mul     dword ptr [rsp+78h+var_58+0Ch]
0x1800192b1  mov     rax, [rcx+168h]
0x1800192b8  mov     edi, 0Ah
0x1800192bd  shr     edx, 5
0x1800192c0  mov     rcx, r8
0x1800192c3  sub     edi, edx
0x1800192c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192ca  mov     rcx, rax; hWnd
0x1800192cd  mov     r9d, edi; lParam
0x1800192d0  mov     r8d, 1; wParam
0x1800192d6  mov     edx, ebp; Msg
0x1800192d8  call    cs:__imp_SendMessageW
0x1800192de  test    [rsp+78h+var_58+4], 40h
0x1800192e3  jz      short loc_180019312
0x1800192e5  mov     rdi, [rsi+60h]
0x1800192e9  lea     rcx, aChangespeed; "changespeed"
0x1800192f0  call    cs:__imp_StrToID
0x1800192f6  movzx   edx, ax
0x1800192f9  mov     rcx, rdi
0x1800192fc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019302  test    rax, rax
0x180019305  jz      short loc_180019312
0x180019307  mov     dl, 1
0x180019309  mov     rcx, rax
0x18001930c  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180019312  mov     rdi, [rsi+60h]
0x180019316  lea     rcx, aNumlockon; "numlockon"
0x18001931d  call    cs:__imp_StrToID
0x180019323  movzx   edx, ax
0x180019326  mov     rcx, rdi
0x180019329  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001932f  mov     rdi, [rsi+60h]
0x180019333  lea     rcx, aNumlockoff; "numlockoff"
0x18001933a  mov     rbp, rax
0x18001933d  call    cs:__imp_StrToID
0x180019343  movzx   edx, ax
0x180019346  mov     rcx, rdi
0x180019349  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001934f  test    rbp, rbp
0x180019352  jz      short loc_18001936E
0x180019354  test    rax, rax
0x180019357  jz      short loc_18001936E
0x180019359  test    [rsp+78h+var_58+4], 80h
0x18001935e  mov     dl, 1
0x180019360  mov     rcx, rax
0x180019363  jnz     short loc_180019368
0x180019365  mov     rcx, rbp
0x180019368  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001936e  test    [rsp+78h+var_58+4], 20h
0x180019373  jz      short loc_1800193A2
0x180019375  mov     rdi, [rsi+60h]
0x180019379  lea     rcx, aShowstatus; "showstatus"
0x180019380  call    cs:__imp_StrToID
0x180019386  movzx   edx, ax
0x180019389  mov     rcx, rdi
0x18001938c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019392  test    rax, rax
0x180019395  jz      short loc_1800193A2
0x180019397  mov     dl, 1
0x180019399  mov     rcx, rax
0x18001939c  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x1800193a2  mov     rcx, rbx; this
0x1800193a5  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x1800193aa  mov     rcx, [rsp+78h+var_38]
0x1800193af  xor     rcx, rsp; StackCookie
0x1800193b2  call    __security_check_cookie
0x1800193b7  add     rsp, 58h
0x1800193bb  pop     rdi
0x1800193bc  pop     rsi
0x1800193bd  pop     rbp
0x1800193be  pop     rbx
0x1800193bf  retn
```
