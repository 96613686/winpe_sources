# HubPage::SetUpScanning(void)

- ea: `0x18001d6dc`
- end: `0x18001d971`
- name: `?SetUpScanning@HubPage@@AEAAJXZ`
- size: `661`
- prototype: `__int64 __fastcall(HubPage *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cf40`
- `0x18001d62c`

## callees

- `0x1800055c0`
- `0x1800057d4`
- `0x180014b34`
- `0x180018260`
- `0x18001d070`
- `0x18001d6dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d73b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d73b`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001d925`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001d925`
- `USER32!SetTimer` at `0x18001d94c`
- `USER32!SetTimer` at `0x18001d94c`
- `USER32!KillTimer` at `0x18001d7c1`
- `USER32!KillTimer` at `0x18001d7c1`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d791`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d851`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d791`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d851`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d79c`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d846`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d79c`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001d846`
- `DUI70!StrToID` at `0x18001d767`
- `DUI70!StrToID` at `0x18001d865`
- `DUI70!StrToID` at `0x18001d88c`
- `DUI70!StrToID` at `0x18001d8b3`
- `DUI70!StrToID` at `0x18001d8da`
- `DUI70!StrToID` at `0x18001d767`
- `DUI70!StrToID` at `0x18001d865`
- `DUI70!StrToID` at `0x18001d88c`
- `DUI70!StrToID` at `0x18001d8b3`
- `DUI70!StrToID` at `0x18001d8da`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d773`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d871`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d898`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d8bf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d8e6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d773`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d871`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d898`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d8bf`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d8e6`

## string_xrefs

- `0x18001d6f7`: `Software\Microsoft\Ease of Access`
- `0x18001d8cc`: `highcontrastlink`

## pseudocode

```c
__int64 __fastcall HubPage::SetUpScanning(HubPage *this, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rbx
  HubPage *v10; // rcx
  unsigned int v11; // eax
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rbx
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rbx
  unsigned __int16 v17; // ax
  struct DirectUI::Element *v18; // rax
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  HWND v21; // rax
  HKEY v23; // [rsp+30h] [rbp-30h]
  _QWORD v24[4]; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v25; // [rsp+78h] [rbp+18h] BYREF
  unsigned int v26; // [rsp+80h] [rbp+20h] BYREF

  memset(v24, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Create(
                       (ATL::CRegKey *)v24,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Ease of Access",
                       a4,
                       0,
                       0x2001Fu,
                       v23,
                       0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = (DirectUI::Element *)*((_QWORD *)this + 32);
    v8 = StrToID(L"selfscan");
    Descendent = DirectUI::Element::FindDescendent(v7, v8);
    if ( HubPage::IsSimpleProfileConfiguredToRun(v10, L"osk") )
    {
      DirectUI::Element::SetSelected(Descendent, 0);
      DirectUI::Element::SetEnabled(Descendent, 0);
      ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v24, L"selfscan", 0);
      KillTimer(*((HWND *)this + 41), 0x123u);
    }
    else
    {
      v26 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"selfscan", &v26) != 0;
      v25 = 0;
      if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"selfvoice", &v25) )
      {
        v11 = 1;
        v25 = 1;
      }
      else
      {
        v11 = v25;
      }
      *((_DWORD *)this + 94) = v11 != 0 ? 20000 : 3000;
      if ( v26 )
      {
        if ( Descendent )
        {
          DirectUI::Element::SetEnabled(Descendent, 1);
          DirectUI::Element::SetSelected(Descendent, 1);
        }
        v12 = (DirectUI::Element *)*((_QWORD *)this + 32);
        v13 = StrToID(L"magnifierpane");
        *((_QWORD *)this + 43) = DirectUI::Element::FindDescendent(v12, v13);
        v14 = (DirectUI::Element *)*((_QWORD *)this + 32);
        v15 = StrToID(L"Narrator");
        *((_QWORD *)this + 44) = DirectUI::Element::FindDescendent(v14, v15);
        v16 = (DirectUI::Element *)*((_QWORD *)this + 32);
        v17 = StrToID(L"osk");
        v18 = DirectUI::Element::FindDescendent(v16, v17);
        v19 = (DirectUI::Element *)*((_QWORD *)this + 32);
        *((_QWORD *)this + 45) = v18;
        v20 = StrToID(L"highcontrastlink");
        *((_QWORD *)this + 46) = DirectUI::Element::FindDescendent(v19, v20);
        v21 = (HWND)*((_QWORD *)this + 41);
        *((_QWORD *)this + 42) = 0;
        if ( !v21 )
        {
          v21 = (HWND)SHCreateWorkerWindowW(HubPage::s_TimerProc, *((_QWORD *)this + 1), 0, 0, 0, this);
          *((_QWORD *)this + 41) = v21;
        }
        SetTimer(v21, 0x123u, *((_DWORD *)this + *((unsigned int *)this + 84) + 94), 0);
      }
    }
    v6 = 0;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v24);
  return v6;
}

```

## disassembly

```asm
0x18001d6dc  mov     rax, rsp
0x18001d6df  mov     [rax+8], rbx
0x18001d6e3  mov     [rax+20h], rdi
0x18001d6e7  push    rbp
0x18001d6e8  mov     rbp, rsp
0x18001d6eb  sub     rsp, 60h
0x18001d6ef  mov     qword ptr [rax-30h], 0
0x18001d6f7  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x18001d6fe  mov     rdi, rcx
0x18001d701  mov     dword ptr [rax-40h], 2001Fh
0x18001d708  lea     rcx, [rbp+var_20]; this
0x18001d70c  mov     dword ptr [rax-48h], 0
0x18001d713  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001d71a  mov     [rbp+var_20], 0
0x18001d722  mov     [rbp+var_18], 0
0x18001d72a  mov     [rbp+var_10], 0
0x18001d732  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001d737  test    eax, eax
0x18001d739  jz      short loc_18001D759
0x18001d73b  call    cs:__imp_GetLastError
0x18001d741  mov     ebx, eax
0x18001d743  test    eax, eax
0x18001d745  jle     loc_18001D954
0x18001d74b  movzx   ebx, ax
0x18001d74e  or      ebx, 80070000h
0x18001d754  jmp     loc_18001D954
0x18001d759  mov     rbx, [rdi+100h]
0x18001d760  lea     rcx, aSelfscan; "selfscan"
0x18001d767  call    cs:__imp_StrToID
0x18001d76d  movzx   edx, ax
0x18001d770  mov     rcx, rbx
0x18001d773  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d779  lea     rdx, aOsk; "osk"
0x18001d780  mov     rbx, rax
0x18001d783  call    ?IsSimpleProfileConfiguredToRun@HubPage@@AEAAHPEAG@Z; HubPage::IsSimpleProfileConfiguredToRun(ushort *)
0x18001d788  test    eax, eax
0x18001d78a  jz      short loc_18001D7CC
0x18001d78c  xor     edx, edx
0x18001d78e  mov     rcx, rbx
0x18001d791  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001d797  xor     edx, edx
0x18001d799  mov     rcx, rbx
0x18001d79c  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18001d7a2  xor     r8d, r8d; unsigned int
0x18001d7a5  lea     rdx, aSelfscan; "selfscan"
0x18001d7ac  lea     rcx, [rbp+var_20]; this
0x18001d7b0  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001d7b5  mov     rcx, [rdi+148h]; hWnd
0x18001d7bc  mov     edx, 123h; uIDEvent
0x18001d7c1  call    cs:__imp_KillTimer
0x18001d7c7  jmp     loc_18001D952
0x18001d7cc  lea     r8, [rbp+arg_10]; unsigned int *
0x18001d7d0  mov     [rbp+arg_10], 0
0x18001d7d7  lea     rdx, aSelfscan; "selfscan"
0x18001d7de  lea     rcx, [rbp+var_20]; this
0x18001d7e2  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001d7e7  test    eax, eax
0x18001d7e9  jz      short loc_18001D7F2
0x18001d7eb  mov     [rbp+arg_10], 1
0x18001d7f2  lea     r8, [rbp+arg_8]; unsigned int *
0x18001d7f6  mov     [rbp+arg_8], 0
0x18001d7fd  lea     rdx, aSelfvoice; "selfvoice"
0x18001d804  lea     rcx, [rbp+var_20]; this
0x18001d808  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001d80d  test    eax, eax
0x18001d80f  jz      short loc_18001D81B
0x18001d811  mov     eax, 1
0x18001d816  mov     [rbp+arg_8], eax
0x18001d819  jmp     short loc_18001D81E
0x18001d81b  mov     eax, [rbp+arg_8]
0x18001d81e  neg     eax
0x18001d820  sbb     eax, eax
0x18001d822  and     eax, 4268h
0x18001d827  add     eax, 0BB8h
0x18001d82c  mov     [rdi+178h], eax
0x18001d832  cmp     [rbp+arg_10], 0
0x18001d836  jz      loc_18001D952
0x18001d83c  test    rbx, rbx
0x18001d83f  jz      short loc_18001D857
0x18001d841  mov     dl, 1
0x18001d843  mov     rcx, rbx
0x18001d846  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18001d84c  mov     dl, 1
0x18001d84e  mov     rcx, rbx
0x18001d851  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001d857  mov     rbx, [rdi+100h]
0x18001d85e  lea     rcx, aMagnifierpane; "magnifierpane"
0x18001d865  call    cs:__imp_StrToID
0x18001d86b  movzx   edx, ax
0x18001d86e  mov     rcx, rbx
0x18001d871  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d877  mov     [rdi+158h], rax
0x18001d87e  lea     rcx, aNarrator_0; "Narrator"
0x18001d885  mov     rbx, [rdi+100h]
0x18001d88c  call    cs:__imp_StrToID
0x18001d892  movzx   edx, ax
0x18001d895  mov     rcx, rbx
0x18001d898  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d89e  mov     [rdi+160h], rax
0x18001d8a5  lea     rcx, aOsk; "osk"
0x18001d8ac  mov     rbx, [rdi+100h]
0x18001d8b3  call    cs:__imp_StrToID
0x18001d8b9  movzx   edx, ax
0x18001d8bc  mov     rcx, rbx
0x18001d8bf  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d8c5  mov     rbx, [rdi+100h]
0x18001d8cc  lea     rcx, aHighcontrastli; "highcontrastlink"
0x18001d8d3  mov     [rdi+168h], rax
0x18001d8da  call    cs:__imp_StrToID
0x18001d8e0  movzx   edx, ax
0x18001d8e3  mov     rcx, rbx
0x18001d8e6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d8ec  mov     [rdi+170h], rax
0x18001d8f3  mov     rax, [rdi+148h]
0x18001d8fa  mov     qword ptr [rdi+150h], 0
0x18001d905  test    rax, rax
0x18001d908  jnz     short loc_18001D932
0x18001d90a  mov     rdx, [rdi+8]
0x18001d90e  lea     rcx, ?s_TimerProc@HubPage@@CA_JPEAUHWND__@@I_K_J@Z; HubPage::s_TimerProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001d915  mov     [rsp+60h+var_38], rdi
0x18001d91a  xor     r9d, r9d
0x18001d91d  xor     r8d, r8d
0x18001d920  mov     [rsp+60h+var_40], rax
0x18001d925  call    cs:__imp_SHCreateWorkerWindowW
0x18001d92b  mov     [rdi+148h], rax
0x18001d932  mov     r8d, [rdi+150h]
0x18001d939  xor     r9d, r9d; lpTimerFunc
0x18001d93c  mov     edx, 123h; nIDEvent
0x18001d941  mov     rcx, rax; hWnd
0x18001d944  mov     r8d, [rdi+r8*4+178h]; uElapse
0x18001d94c  call    cs:__imp_SetTimer
0x18001d952  xor     ebx, ebx
0x18001d954  lea     rcx, [rbp+var_20]; this
0x18001d958  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001d95d  lea     r11, [rsp+60h+var_s0]
0x18001d962  mov     eax, ebx
0x18001d964  mov     rbx, [r11+10h]
0x18001d968  mov     rdi, [r11+28h]
0x18001d96c  mov     rsp, r11
0x18001d96f  pop     rbp
0x18001d970  retn
```
