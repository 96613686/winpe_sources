# CListViewPopup::_OnCreate(HWND__ *)

- ea: `0x1801adebc`
- end: `0x1801ae207`
- name: `?_OnCreate@CListViewPopup@@AEAA_JPEAUHWND__@@@Z`
- size: `843`
- prototype: `__int64 __fastcall(CListViewPopup *__hidden this, HWND hwnd)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800e3b0c`

## callees

- `0x1800218ac`
- `0x180036ab8`
- `0x180040924`
- `0x1800cce08`
- `0x18011a04c`
- `0x1801ad0cc`
- `0x1801adebc`
- `0x1801aed08`
- `0x180207e0c`
- `0x180210010`

## import_xrefs

- `SHELL32!__imp_SHCreateIconImageList` at `0x1801ae05e`
- `SHELL32!__imp_SHCreateIconImageList` at `0x1801ae05e`
- `USER32!SystemParametersInfoW` at `0x1801ae0db`
- `USER32!SystemParametersInfoW` at `0x1801ae0db`
- `USER32!GetWindowLongW` at `0x1801adfed`
- `USER32!GetWindowLongW` at `0x1801ae0ad`
- `USER32!GetWindowLongW` at `0x1801adfed`
- `USER32!GetWindowLongW` at `0x1801ae0ad`
- `UxTheme!OpenThemeData` at `0x1801adeec`
- `UxTheme!OpenThemeData` at `0x1801adf07`
- `UxTheme!OpenThemeData` at `0x1801adf30`
- `UxTheme!OpenThemeData` at `0x1801adf4b`
- `UxTheme!OpenThemeData` at `0x1801adeec`
- `UxTheme!OpenThemeData` at `0x1801adf07`
- `UxTheme!OpenThemeData` at `0x1801adf30`
- `UxTheme!OpenThemeData` at `0x1801adf4b`
- `UxTheme!GetThemePartSize` at `0x1801adf8a`
- `UxTheme!GetThemePartSize` at `0x1801adfc2`
- `UxTheme!GetThemePartSize` at `0x1801adf8a`
- `UxTheme!GetThemePartSize` at `0x1801adfc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CListViewPopup::_OnCreate(CListViewPopup *this, HWND hwnd)
{
  void *v3; // rcx
  void *v4; // rcx
  LONG WindowLongW; // eax
  int ListView; // edi
  __int64 (__fastcall ***v7)(_QWORD, GUID *, char *); // rcx
  unsigned int v8; // esi
  int prc; // [rsp+20h] [rbp-30h]
  int pvParam; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+44h] [rbp-Ch]
  int v13; // [rsp+4Ch] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v15; // [rsp+70h] [rbp+20h] BYREF
  __int64 (__fastcall ***v16)(_QWORD, GUID *, char *); // [rsp+78h] [rbp+28h] BYREF

  *((_DWORD *)this + 68) = 0;
  *((_QWORD *)this + 33) = hwnd;
  *((_QWORD *)this + 16) = OpenThemeData(hwnd, L"Menu");
  *((_QWORD *)this + 18) = OpenThemeData(*((HWND *)this + 33), L"Button");
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::GetImpl'::`2'::impl,
    0);
  *((_QWORD *)this + 17) = OpenThemeData(*((HWND *)this + 33), L"ItemsView::ListView");
  *((_QWORD *)this + 20) = OpenThemeData(*((HWND *)this + 33), L"ListViewPopup");
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
    GetThemePartSize(v3, 0, 10, 0, 0, TS_TRUE, (SIZE *)this + 22);
  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
    GetThemePartSize(v4, 0, 16, 0, 0, TS_TRUE, (SIZE *)this + 23);
  *((_QWORD *)this + 56) = 0;
  if ( !(unsigned int)CListViewPopup::_HasItemTheme(this) )
  {
    WindowLongW = GetWindowLongW(*((HWND *)this + 33), -20);
    *((_QWORD *)this + 56) = CreateCheckBoxImagelistForDPI(
                               *((_QWORD *)this + 32),
                               0,
                               (unsigned int)L"Button",
                               3,
                               (WindowLongW & 0x400000 | 0x800000u) >> 22);
  }
  v16 = 0;
  v15 = 0;
  SHLogicalToPhysicalDPIMetric(*((HWND *)this + 32), 49, &v15);
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v16);
  ListView = SHCreateIconImageList((unsigned int)v15, &GUID_46eb5926_582e_4017_9fdf_e8998daa0950, &v16);
  if ( ListView >= 0 )
  {
    v7 = v16;
    *((_QWORD *)this + 57) = v16;
    if ( v7 )
    {
      ListView = (**v7)(v7, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, (char *)this + 464);
      v16 = 0;
    }
    else
    {
      ListView = -2147418113;
    }
  }
  v8 = ((unsigned int)GetWindowLongW(*((HWND *)this + 33), -20) >> 9) & 0x2000;
  pvParam = 16;
  v12 = 0;
  v13 = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) && (v12 & 1) != 0 )
    *((_DWORD *)this + 70) = 1;
  if ( ListView >= 0 )
  {
    if ( (*((_BYTE *)this + 56) & 1) == 0
      || (ListView = wil::details::in1diag3::Log_Hr(
                       retaddr,
                       (void *)0x875,
                       (unsigned int)"shell\\explorerframe\\lvpopup.cpp",
                       (const char *)0x80070057LL,
                       prc),
          ListView >= 0) )
    {
      if ( !*((_QWORD *)this + 13)
        || (ListView = wil::details::in1diag3::Log_Hr(
                         retaddr,
                         (void *)0x87B,
                         (unsigned int)"shell\\explorerframe\\lvpopup.cpp",
                         (const char *)0x80070057LL,
                         prc),
            ListView >= 0) )
      {
        if ( (*((_BYTE *)this + 56) & 2) == 0
          || (ListView = wil::details::in1diag3::Log_Hr(
                           retaddr,
                           (void *)0x881,
                           (unsigned int)"shell\\explorerframe\\lvpopup.cpp",
                           (const char *)0x80070057LL,
                           prc),
              ListView >= 0) )
        {
          ListView = CListViewPopup::_CreateListView(this, v8, 3);
          if ( ListView >= 0 )
          {
            ListView = CListViewPopup::_CreateListView(this, v8, 5);
            if ( ListView >= 0 )
            {
              ListView = CListViewPopup::_CreateListView(this, v8, 6);
              if ( ListView >= 0 )
              {
                if ( *((_QWORD *)this + 55) )
                  CListViewPopup::_SetFocusToControl(this, 2);
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v16);
  return (__int64)ListView >> 31;
}

```

## disassembly

```asm
0x1801adebc  mov     [rsp-18h+arg_10], rbx
0x1801adec1  push    rbp
0x1801adec2  push    rsi
0x1801adec3  push    rdi
0x1801adec4  mov     rbp, rsp
0x1801adec7  sub     rsp, 50h
0x1801adecb  mov     rax, rdx
0x1801adece  mov     rbx, rcx
0x1801aded1  mov     dword ptr [rcx+110h], 0
0x1801adedb  mov     [rcx+108h], rdx
0x1801adee2  lea     rdx, aMenu_0; "Menu"
0x1801adee9  mov     rcx, rax; hwnd
0x1801adeec  call    cs:__imp_OpenThemeData
0x1801adef2  mov     [rbx+80h], rax
0x1801adef9  lea     rdx, aButton; "Button"
0x1801adf00  mov     rcx, [rbx+108h]; hwnd
0x1801adf07  call    cs:__imp_OpenThemeData
0x1801adf0d  mov     [rbx+90h], rax
0x1801adf14  xor     edx, edx
0x1801adf16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme> `wil::Feature<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::GetImpl(void)'::`2'::impl
0x1801adf1d  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerDarkTheme@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerDarkTheme>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1801adf22  lea     rdx, aItemsviewListv; "ItemsView::ListView"
0x1801adf29  mov     rcx, [rbx+108h]; hwnd
0x1801adf30  call    cs:__imp_OpenThemeData
0x1801adf36  mov     [rbx+88h], rax
0x1801adf3d  lea     rdx, aListviewpopup; "ListViewPopup"
0x1801adf44  mov     rcx, [rbx+108h]; hwnd
0x1801adf4b  call    cs:__imp_OpenThemeData
0x1801adf51  mov     [rbx+0A0h], rax
0x1801adf58  mov     rcx, [rbx+88h]; hTheme
0x1801adf5f  test    rcx, rcx
0x1801adf62  jz      short loc_1801ADF90
0x1801adf64  lea     rax, [rbx+0B0h]
0x1801adf6b  mov     [rsp+50h+psz], rax; psz
0x1801adf70  mov     [rsp+50h+eSize], 1; eSize
0x1801adf78  mov     [rsp+50h+prc], 0; prc
0x1801adf81  xor     r9d, r9d; iStateId
0x1801adf84  xor     edx, edx; hdc
0x1801adf86  lea     r8d, [r9+0Ah]; iPartId
0x1801adf8a  call    cs:__imp_GetThemePartSize
0x1801adf90  mov     rcx, [rbx+80h]; hTheme
0x1801adf97  test    rcx, rcx
0x1801adf9a  jz      short loc_1801ADFC8
0x1801adf9c  lea     rax, [rbx+0B8h]
0x1801adfa3  mov     [rsp+50h+psz], rax; psz
0x1801adfa8  mov     [rsp+50h+eSize], 1; eSize
0x1801adfb0  mov     [rsp+50h+prc], 0; prc
0x1801adfb9  xor     r9d, r9d; iStateId
0x1801adfbc  xor     edx, edx; hdc
0x1801adfbe  lea     r8d, [r9+10h]; iPartId
0x1801adfc2  call    cs:__imp_GetThemePartSize
0x1801adfc8  mov     qword ptr [rbx+1C0h], 0
0x1801adfd3  mov     rcx, rbx; this
0x1801adfd6  call    ?_HasItemTheme@CListViewPopup@@AEAAHXZ; CListViewPopup::_HasItemTheme(void)
0x1801adfdb  mov     esi, 0FFFFFFECh
0x1801adfe0  test    eax, eax
0x1801adfe2  jnz     short loc_1801AE023
0x1801adfe4  mov     edx, esi; nIndex
0x1801adfe6  mov     rcx, [rbx+108h]; hWnd
0x1801adfed  call    cs:__imp_GetWindowLongW
0x1801adff3  and     eax, 400000h
0x1801adff8  bts     eax, 17h
0x1801adffc  shr     eax, 16h
0x1801adfff  mov     dword ptr [rsp+50h+prc], eax; int
0x1801ae003  lea     r9d, [rsi+17h]
0x1801ae007  lea     r8, aButton; "Button"
0x1801ae00e  xor     edx, edx
0x1801ae010  mov     rcx, [rbx+100h]
0x1801ae017  call    CreateCheckBoxImagelistForDPI
0x1801ae01c  mov     [rbx+1C0h], rax
0x1801ae023  mov     [rbp+arg_8], 0
0x1801ae02b  mov     [rbp+arg_0], 0
0x1801ae032  lea     r8, [rbp+arg_0]; int *
0x1801ae036  mov     edx, 31h ; '1'; int
0x1801ae03b  mov     rcx, [rbx+100h]; HWND
0x1801ae042  call    ?SHLogicalToPhysicalDPIMetric@@YAXPEAUHWND__@@HPEAH@Z; SHLogicalToPhysicalDPIMetric(HWND__ *,int,int *)
0x1801ae047  lea     rcx, [rbp+arg_8]
0x1801ae04b  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x1801ae050  lea     r8, [rbp+arg_8]
0x1801ae054  lea     rdx, _GUID_46eb5926_582e_4017_9fdf_e8998daa0950
0x1801ae05b  mov     ecx, [rbp+arg_0]
0x1801ae05e  call    cs:__imp_SHCreateIconImageList
0x1801ae064  mov     edi, eax
0x1801ae066  test    eax, eax
0x1801ae068  js      short loc_1801AE0A4
0x1801ae06a  mov     rcx, [rbp+arg_8]
0x1801ae06e  mov     [rbx+1C8h], rcx
0x1801ae075  test    rcx, rcx
0x1801ae078  jz      short loc_1801AE09F
0x1801ae07a  mov     rax, [rcx]
0x1801ae07d  lea     r8, [rbx+1D0h]
0x1801ae084  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1
0x1801ae08b  mov     rax, [rax]
0x1801ae08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ae093  mov     edi, eax
0x1801ae095  mov     [rbp+arg_8], 0
0x1801ae09d  jmp     short loc_1801AE0A4
0x1801ae09f  mov     edi, 8000FFFFh
0x1801ae0a4  mov     edx, esi; nIndex
0x1801ae0a6  mov     rcx, [rbx+108h]; hWnd
0x1801ae0ad  call    cs:__imp_GetWindowLongW
0x1801ae0b3  mov     esi, eax
0x1801ae0b5  shr     esi, 9
0x1801ae0b8  and     esi, 2000h
0x1801ae0be  mov     [rbp+pvParam], 10h
0x1801ae0c5  xor     eax, eax
0x1801ae0c7  mov     [rbp+var_C], rax
0x1801ae0cb  mov     [rbp+var_4], eax
0x1801ae0ce  xor     r9d, r9d; fWinIni
0x1801ae0d1  lea     r8, [rbp+pvParam]; pvParam
0x1801ae0d5  lea     edx, [rax+10h]; uiParam
0x1801ae0d8  lea     ecx, [rax+42h]; uiAction
0x1801ae0db  call    cs:__imp_SystemParametersInfoW
0x1801ae0e1  test    eax, eax
0x1801ae0e3  jz      short loc_1801AE0F5
0x1801ae0e5  test    byte ptr [rbp+var_C], 1
0x1801ae0e9  jz      short loc_1801AE0F5
0x1801ae0eb  mov     dword ptr [rbx+118h], 1
0x1801ae0f5  test    edi, edi
0x1801ae0f7  js      loc_1801AE1E7
0x1801ae0fd  test    byte ptr [rbx+38h], 1
0x1801ae101  jz      short loc_1801AE128
0x1801ae103  mov     rcx, [rbp+18h]; this
0x1801ae107  mov     r9d, 80070057h; char *
0x1801ae10d  lea     r8, aShellExplorerf_2; "shell\\explorerframe\\lvpopup.cpp"
0x1801ae114  mov     edx, 875h; void *
0x1801ae119  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801ae11e  mov     edi, eax
0x1801ae120  test    eax, eax
0x1801ae122  js      loc_1801AE1E7
0x1801ae128  cmp     qword ptr [rbx+68h], 0
0x1801ae12d  jz      short loc_1801AE154
0x1801ae12f  mov     rcx, [rbp+18h]; this
0x1801ae133  mov     r9d, 80070057h; char *
0x1801ae139  lea     r8, aShellExplorerf_2; "shell\\explorerframe\\lvpopup.cpp"
0x1801ae140  mov     edx, 87Bh; void *
0x1801ae145  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801ae14a  mov     edi, eax
0x1801ae14c  test    eax, eax
0x1801ae14e  js      loc_1801AE1E7
0x1801ae154  test    byte ptr [rbx+38h], 2
0x1801ae158  jz      short loc_1801AE17B
0x1801ae15a  mov     rcx, [rbp+18h]; this
0x1801ae15e  mov     r9d, 80070057h; char *
0x1801ae164  lea     r8, aShellExplorerf_2; "shell\\explorerframe\\lvpopup.cpp"
0x1801ae16b  mov     edx, 881h; void *
0x1801ae170  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801ae175  mov     edi, eax
0x1801ae177  test    eax, eax
0x1801ae179  js      short loc_1801AE1E7
0x1801ae17b  mov     r8d, 3
0x1801ae181  mov     edx, esi
0x1801ae183  mov     rcx, rbx
0x1801ae186  call    ?_CreateListView@CListViewPopup@@AEAAJHW4LVPCONTROL@@@Z; CListViewPopup::_CreateListView(int,LVPCONTROL)
0x1801ae18b  mov     edi, eax
0x1801ae18d  test    eax, eax
0x1801ae18f  js      short loc_1801AE1E7
0x1801ae191  mov     r8d, 5
0x1801ae197  mov     edx, esi
0x1801ae199  mov     rcx, rbx
0x1801ae19c  call    ?_CreateListView@CListViewPopup@@AEAAJHW4LVPCONTROL@@@Z; CListViewPopup::_CreateListView(int,LVPCONTROL)
0x1801ae1a1  mov     edi, eax
0x1801ae1a3  test    eax, eax
0x1801ae1a5  js      short loc_1801AE1E7
0x1801ae1a7  mov     r8d, 6
0x1801ae1ad  mov     edx, esi
0x1801ae1af  mov     rcx, rbx
0x1801ae1b2  call    ?_CreateListView@CListViewPopup@@AEAAJHW4LVPCONTROL@@@Z; CListViewPopup::_CreateListView(int,LVPCONTROL)
0x1801ae1b7  mov     edi, eax
0x1801ae1b9  test    eax, eax
0x1801ae1bb  js      short loc_1801AE1E7
0x1801ae1bd  cmp     qword ptr [rbx+1B8h], 0
0x1801ae1c5  jz      short loc_1801AE1D6
0x1801ae1c7  xor     r8d, r8d
0x1801ae1ca  lea     edx, [r8+2]
0x1801ae1ce  mov     rcx, rbx
0x1801ae1d1  call    ?_SetFocusToControl@CListViewPopup@@AEAAXW4LVPCONTROL@@H@Z; CListViewPopup::_SetFocusToControl(LVPCONTROL,int)
0x1801ae1d6  mov     rcx, [rbx+30h]
0x1801ae1da  mov     rax, [rcx]
0x1801ae1dd  mov     rax, [rax+18h]
0x1801ae1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ae1e6  nop
0x1801ae1e7  lea     rcx, [rbp+arg_8]
0x1801ae1eb  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x1801ae1f0  movsxd  rax, edi
0x1801ae1f3  sar     rax, 1Fh
0x1801ae1f7  mov     rbx, [rsp+50h+arg_10]
0x1801ae1ff  add     rsp, 50h
0x1801ae203  pop     rdi
0x1801ae204  pop     rsi
0x1801ae205  pop     rbp
0x1801ae206  retn
```
