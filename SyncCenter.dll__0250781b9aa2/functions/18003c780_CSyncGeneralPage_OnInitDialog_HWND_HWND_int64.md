# CSyncGeneralPage::OnInitDialog(HWND__ *,HWND__ *,__int64)

- ea: `0x18003c780`
- end: `0x18003cb41`
- name: `?OnInitDialog@CSyncGeneralPage@@MEAA_JPEAUHWND__@@0_J@Z`
- size: `961`
- prototype: `__int64 __fastcall(CSyncGeneralPage *__hidden this, HWND hDlg, HWND, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008584`
- `0x18003c780`
- `0x18003cccc`
- `0x18004be1c`
- `0x18004c098`
- `0x18004c214`
- `0x180052912`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c988`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c9a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c9a2`
- `USER32!GetDlgItem` at `0x18003c7b9`
- `USER32!GetDlgItem` at `0x18003c7cb`
- `USER32!GetDlgItem` at `0x18003c7dd`
- `USER32!GetDlgItem` at `0x18003cade`
- `USER32!GetDlgItem` at `0x18003c7b9`
- `USER32!GetDlgItem` at `0x18003c7cb`
- `USER32!GetDlgItem` at `0x18003c7dd`
- `USER32!GetDlgItem` at `0x18003cade`
- `USER32!SetDlgItemTextW` at `0x18003c802`
- `USER32!SetDlgItemTextW` at `0x18003c817`
- `USER32!SetDlgItemTextW` at `0x18003c830`
- `USER32!SetDlgItemTextW` at `0x18003c849`
- `USER32!SetDlgItemTextW` at `0x18003c85e`
- `USER32!SetDlgItemTextW` at `0x18003c97e`
- `USER32!SetDlgItemTextW` at `0x18003ca0a`
- `USER32!SetDlgItemTextW` at `0x18003ca81`
- `USER32!SetDlgItemTextW` at `0x18003cab3`
- `USER32!SetDlgItemTextW` at `0x18003c802`
- `USER32!SetDlgItemTextW` at `0x18003c817`
- `USER32!SetDlgItemTextW` at `0x18003c830`
- `USER32!SetDlgItemTextW` at `0x18003c849`
- `USER32!SetDlgItemTextW` at `0x18003c85e`
- `USER32!SetDlgItemTextW` at `0x18003c97e`
- `USER32!SetDlgItemTextW` at `0x18003ca0a`
- `USER32!SetDlgItemTextW` at `0x18003ca81`
- `USER32!SetDlgItemTextW` at `0x18003cab3`
- `USER32!EnableWindow` at `0x18003cb03`
- `USER32!EnableWindow` at `0x18003cb03`
- `USER32!ShowWindow` at `0x18003caf3`
- `USER32!ShowWindow` at `0x18003caf3`
- `PROPSYS!PSGetPropertyDescription` at `0x18003c89d`
- `PROPSYS!PSGetPropertyDescription` at `0x18003c89d`

## pseudocode

```c
__int64 __fastcall CSyncGeneralPage::OnInitDialog(CSyncGeneralPage *this, HWND hDlg, HWND a3)
{
  HWND DlgItem; // rax
  __int64 v6; // r15
  HWND v7; // r14
  int v8; // ebx
  __int64 v9; // rcx
  PROPVARIANT *v10; // r8
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // rcx
  HFONT v15; // rdx
  int v16; // edi
  HWND v17; // rbx
  CSyncBasePropertyPage *v18; // rcx
  unsigned int v20; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  LPCWSTR lpString; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+48h] [rbp-21h] BYREF
  void *ppv; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+68h] [rbp-1h]
  WCHAR String[8]; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v28; // [rsp+88h] [rbp+1Fh]

  CSyncBasePropertyPage::_CreateBoldFont((HWND *)this);
  *((_QWORD *)this + 3) = GetDlgItem(hDlg, 501);
  *((_QWORD *)this + 4) = GetDlgItem(hDlg, 524);
  DlgItem = GetDlgItem(hDlg, 525);
  v6 = *((_QWORD *)this + 7);
  v7 = (HWND)*((_QWORD *)this + 1);
  *((_QWORD *)this + 5) = DlgItem;
  SetDlgItemTextW(v7, 502, (LPCWSTR)(v6 + 284));
  SetDlgItemTextW(v7, 504, (LPCWSTR)(v6 + 540));
  SetDlgItemTextW(v7, 513, *(LPCWSTR *)(*((_QWORD *)this + 7) + 2728LL));
  SetDlgItemTextW(v7, 515, (LPCWSTR)(*((_QWORD *)this + 7) + 2744LL));
  SetDlgItemTextW(v7, 522, (LPCWSTR)(v6 + 848));
  if ( *((_BYTE *)this + 48) != 1 )
  {
    v11 = 506;
    v10 = (PROPVARIANT *)(*((_QWORD *)this + 7) + 1644LL);
    goto LABEL_15;
  }
  memcpy_0((void *)(v6 + 1368), (const void *)(v6 + 8), 0x550u);
  ppv = 0;
  if ( PSGetPropertyDescription(&PKEY_Sync_HandlerType, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, &ppv) < 0 )
    goto LABEL_12;
  v21 = 0;
  v8 = (*(__int64 (__fastcall **)(void *, GUID *, __int64 *))(*(_QWORD *)ppv + 160LL))(
         ppv,
         &GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6,
         &v21);
  if ( v8 >= 0 )
  {
    v20 = 0;
    v26 = 0;
    *(_OWORD *)pvar = 0;
    LOWORD(pvar[0]) = 19;
    LODWORD(pvar[1]) = *(_DWORD *)(v6 + 2156);
    v8 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *, unsigned int *))(*(_QWORD *)v21 + 48LL))(v21, pvar, &v20);
    if ( v8 >= 0 )
    {
      v23 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v21 + 32LL))(
             v21,
             v20,
             &GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2,
             &v23);
      if ( v8 >= 0 )
      {
        lpString = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v23 + 56LL))(v23, &lpString);
        if ( v8 >= 0 )
        {
          SetDlgItemTextW(v7, 510, lpString);
          CoTaskMemFree((LPVOID)lpString);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      PropVariantClear(pvar);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 < 0 )
  {
LABEL_12:
    if ( (int)StringCchPrintfW((unsigned __int16 *)pvar, 0x10u, L"%d", *(unsigned int *)(v6 + 2156)) >= 0 )
    {
      v10 = pvar;
      v11 = 510;
LABEL_15:
      SetDlgItemTextW(v7, v11, (LPCWSTR)v10);
    }
  }
  v12 = *((_QWORD *)this + 7);
  LOBYTE(v12) = *(_BYTE *)(v12 + 2872);
  CSyncBasePropertyPage::InitCheckbox(v9, *((_QWORD *)this + 4), v6 + 8, v12, 64);
  v13 = *((_QWORD *)this + 7);
  LOBYTE(v13) = *(_BYTE *)(v13 + 2873);
  CSyncBasePropertyPage::InitCheckbox(v14, *((_QWORD *)this + 5), v6 + 8, v13, 512);
  *(_OWORD *)String = 0;
  v28 = 0;
  StringCchPrintfW(String, 0x10u, L"%d", *(unsigned int *)(v6 + 816));
  SetDlgItemTextW(v7, 517, String);
  String[0] = 0;
  StringCchPrintfW(String, 0x10u, L"%d", *(unsigned int *)(v6 + 812));
  SetDlgItemTextW(v7, 519, String);
  v15 = (HFONT)*((_QWORD *)this + 2);
  if ( v15 )
    CSyncGeneralPage::_SetFontOnControls(this, v15);
  v16 = *(_DWORD *)(v6 + 800) & 0x400000;
  v17 = GetDlgItem(v7, 527);
  ShowWindow(v17, v16 != 0 ? 5 : 0);
  EnableWindow(v17, v16 != 0);
  CSyncBasePropertyPage::SetItemIcon(v18, *((HWND *)this + 3), **((struct IShellItem ***)this + 7));
  return 1;
}

```

## disassembly

```asm
0x18003c780  mov     [rsp-8+arg_10], rbx
0x18003c785  push    rbp
0x18003c786  push    rsi
0x18003c787  push    rdi
0x18003c788  push    r14
0x18003c78a  push    r15
0x18003c78c  lea     rbp, [rsp-37h]
0x18003c791  sub     rsp, 0A0h
0x18003c798  mov     rax, cs:__security_cookie
0x18003c79f  xor     rax, rsp
0x18003c7a2  mov     [rbp+57h+var_28], rax
0x18003c7a6  mov     rbx, rdx
0x18003c7a9  mov     rsi, rcx
0x18003c7ac  call    ?_CreateBoldFont@CSyncBasePropertyPage@@AEAAJXZ; CSyncBasePropertyPage::_CreateBoldFont(void)
0x18003c7b1  mov     edx, 1F5h; nIDDlgItem
0x18003c7b6  mov     rcx, rbx; hDlg
0x18003c7b9  call    cs:__imp_GetDlgItem
0x18003c7bf  mov     edx, 20Ch; nIDDlgItem
0x18003c7c4  mov     rcx, rbx; hDlg
0x18003c7c7  mov     [rsi+18h], rax
0x18003c7cb  call    cs:__imp_GetDlgItem
0x18003c7d1  mov     edx, 20Dh; nIDDlgItem
0x18003c7d6  mov     rcx, rbx; hDlg
0x18003c7d9  mov     [rsi+20h], rax
0x18003c7dd  call    cs:__imp_GetDlgItem
0x18003c7e3  mov     r15, [rsi+38h]
0x18003c7e7  mov     edx, 1F6h; nIDDlgItem
0x18003c7ec  mov     r14, [rsi+8]
0x18003c7f0  mov     rcx, r14; hDlg
0x18003c7f3  mov     [rsi+28h], rax
0x18003c7f7  lea     rdi, [r15+8]
0x18003c7fb  lea     r8, [rdi+114h]; lpString
0x18003c802  call    cs:__imp_SetDlgItemTextW
0x18003c808  lea     r8, [rdi+214h]; lpString
0x18003c80f  mov     edx, 1F8h; nIDDlgItem
0x18003c814  mov     rcx, r14; hDlg
0x18003c817  call    cs:__imp_SetDlgItemTextW
0x18003c81d  mov     r8, [rsi+38h]
0x18003c821  mov     edx, 201h; nIDDlgItem
0x18003c826  mov     rcx, r14; hDlg
0x18003c829  mov     r8, [r8+0AA8h]; lpString
0x18003c830  call    cs:__imp_SetDlgItemTextW
0x18003c836  mov     r8, [rsi+38h]
0x18003c83a  mov     edx, 203h; nIDDlgItem
0x18003c83f  add     r8, 0AB8h; lpString
0x18003c846  mov     rcx, r14; hDlg
0x18003c849  call    cs:__imp_SetDlgItemTextW
0x18003c84f  lea     r8, [rdi+348h]; lpString
0x18003c856  mov     edx, 20Ah; nIDDlgItem
0x18003c85b  mov     rcx, r14; hDlg
0x18003c85e  call    cs:__imp_SetDlgItemTextW
0x18003c864  cmp     byte ptr [rsi+30h], 1
0x18003c868  jnz     loc_18003C9F7
0x18003c86e  lea     rcx, [r15+558h]; void *
0x18003c875  mov     rdx, rdi; Src
0x18003c878  mov     r8d, 550h; Size
0x18003c87e  call    memcpy_0
0x18003c883  lea     r8, [rbp+57h+ppv]; ppv
0x18003c887  mov     [rbp+57h+ppv], 0
0x18003c88f  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x18003c896  lea     rcx, PKEY_Sync_HandlerType; propkey
0x18003c89d  call    cs:__imp_PSGetPropertyDescription
0x18003c8a3  test    eax, eax
0x18003c8a5  js      loc_18003C9CC
0x18003c8ab  mov     rcx, [rbp+57h+ppv]
0x18003c8af  lea     r8, [rbp+57h+var_88]
0x18003c8b3  mov     [rbp+57h+var_88], 0
0x18003c8bb  lea     rdx, _GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6
0x18003c8c2  mov     rax, [rcx]
0x18003c8c5  mov     rax, [rax+0A0h]
0x18003c8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8d1  mov     ebx, eax
0x18003c8d3  test    eax, eax
0x18003c8d5  js      loc_18003C9B8
0x18003c8db  mov     rcx, [rbp+57h+var_88]
0x18003c8df  lea     r8, [rbp+57h+var_90]
0x18003c8e3  xor     eax, eax
0x18003c8e5  mov     [rbp+57h+var_90], 0
0x18003c8ec  mov     [rbp+57h+var_58], rax
0x18003c8f0  lea     rdx, [rbp+57h+pvar]
0x18003c8f4  mov     eax, 13h
0x18003c8f9  xorps   xmm0, xmm0
0x18003c8fc  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003c900  mov     word ptr [rbp+57h+pvar], ax
0x18003c904  mov     eax, [r15+86Ch]
0x18003c90b  mov     dword ptr [rbp+57h+pvar+8], eax
0x18003c90e  mov     rax, [rcx]
0x18003c911  mov     rax, [rax+30h]
0x18003c915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c91a  mov     ebx, eax
0x18003c91c  test    eax, eax
0x18003c91e  js      loc_18003C9A8
0x18003c924  mov     rcx, [rbp+57h+var_88]
0x18003c928  lea     r9, [rbp+57h+var_78]
0x18003c92c  mov     edx, [rbp+57h+var_90]
0x18003c92f  lea     r8, _GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2
0x18003c936  mov     [rbp+57h+var_78], 0
0x18003c93e  mov     rax, [rcx]
0x18003c941  mov     rax, [rax+20h]
0x18003c945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c94a  mov     ebx, eax
0x18003c94c  test    eax, eax
0x18003c94e  js      short loc_18003C99E
0x18003c950  mov     rcx, [rbp+57h+var_78]
0x18003c954  lea     rdx, [rbp+57h+lpString]
0x18003c958  mov     [rbp+57h+lpString], 0
0x18003c960  mov     rax, [rcx]
0x18003c963  mov     rax, [rax+38h]
0x18003c967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c96c  mov     ebx, eax
0x18003c96e  test    eax, eax
0x18003c970  js      short loc_18003C98E
0x18003c972  mov     r8, [rbp+57h+lpString]; lpString
0x18003c976  mov     edx, 1FEh; nIDDlgItem
0x18003c97b  mov     rcx, r14; hDlg
0x18003c97e  call    cs:__imp_SetDlgItemTextW
0x18003c984  mov     rcx, [rbp+57h+lpString]; pv
0x18003c988  call    cs:__imp_CoTaskMemFree
0x18003c98e  mov     rcx, [rbp+57h+var_78]
0x18003c992  mov     rax, [rcx]
0x18003c995  mov     rax, [rax+10h]
0x18003c999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c99e  lea     rcx, [rbp+57h+pvar]; pvar
0x18003c9a2  call    cs:__imp_PropVariantClear
0x18003c9a8  mov     rcx, [rbp+57h+var_88]
0x18003c9ac  mov     rax, [rcx]
0x18003c9af  mov     rax, [rax+10h]
0x18003c9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9b8  mov     rcx, [rbp+57h+ppv]
0x18003c9bc  mov     rax, [rcx]
0x18003c9bf  mov     rax, [rax+10h]
0x18003c9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9c8  test    ebx, ebx
0x18003c9ca  jns     short loc_18003CA10
0x18003c9cc  mov     r9d, [r15+86Ch]
0x18003c9d3  lea     r8, aD; "%d"
0x18003c9da  mov     edx, 10h; unsigned __int64
0x18003c9df  lea     rcx, [rbp+57h+pvar]; unsigned __int16 *
0x18003c9e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c9e8  test    eax, eax
0x18003c9ea  js      short loc_18003CA10
0x18003c9ec  lea     r8, [rbp+57h+pvar]
0x18003c9f0  mov     edx, 1FEh
0x18003c9f5  jmp     short loc_18003CA07
0x18003c9f7  mov     r8, [rsi+38h]
0x18003c9fb  mov     edx, 1FAh; nIDDlgItem
0x18003ca00  add     r8, 66Ch; lpString
0x18003ca07  mov     rcx, r14; hDlg
0x18003ca0a  call    cs:__imp_SetDlgItemTextW
0x18003ca10  mov     r9, [rsi+38h]
0x18003ca14  mov     r8, rdi
0x18003ca17  mov     rdx, [rsi+20h]
0x18003ca1b  mov     [rsp+0C0h+var_A0], 40h ; '@'
0x18003ca23  mov     r9b, [r9+0B38h]
0x18003ca2a  call    ?InitCheckbox@CSyncBasePropertyPage@@IEAAXPEAUHWND__@@AEBUSYNCMGR_FOLDERITEMINFO@@_NW4SYNCMGR_CAPS_AND_POLICIES@@@Z; CSyncBasePropertyPage::InitCheckbox(HWND__ *,SYNCMGR_FOLDERITEMINFO const &,bool,SYNCMGR_CAPS_AND_POLICIES)
0x18003ca2f  mov     r9, [rsi+38h]
0x18003ca33  mov     r8, rdi
0x18003ca36  mov     rdx, [rsi+28h]
0x18003ca3a  mov     [rsp+0C0h+var_A0], 200h
0x18003ca42  mov     r9b, [r9+0B39h]
0x18003ca49  call    ?InitCheckbox@CSyncBasePropertyPage@@IEAAXPEAUHWND__@@AEBUSYNCMGR_FOLDERITEMINFO@@_NW4SYNCMGR_CAPS_AND_POLICIES@@@Z; CSyncBasePropertyPage::InitCheckbox(HWND__ *,SYNCMGR_FOLDERITEMINFO const &,bool,SYNCMGR_CAPS_AND_POLICIES)
0x18003ca4e  xorps   xmm0, xmm0
0x18003ca51  lea     r8, aD; "%d"
0x18003ca58  movups  xmmword ptr [rbp+57h+String], xmm0
0x18003ca5c  mov     edx, 10h; unsigned __int64
0x18003ca61  lea     rcx, [rbp+57h+String]; unsigned __int16 *
0x18003ca65  movups  [rbp+57h+var_38], xmm0
0x18003ca69  mov     r9d, [rdi+328h]
0x18003ca70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ca75  lea     r8, [rbp+57h+String]; lpString
0x18003ca79  mov     edx, 205h; nIDDlgItem
0x18003ca7e  mov     rcx, r14; hDlg
0x18003ca81  call    cs:__imp_SetDlgItemTextW
0x18003ca87  xor     eax, eax
0x18003ca89  lea     r8, aD; "%d"
0x18003ca90  mov     [rbp+57h+String], ax
0x18003ca94  lea     rcx, [rbp+57h+String]; unsigned __int16 *
0x18003ca98  mov     r9d, [rdi+324h]
0x18003ca9f  lea     edx, [rax+10h]; unsigned __int64
0x18003caa2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003caa7  lea     r8, [rbp+57h+String]; lpString
0x18003caab  mov     edx, 207h; nIDDlgItem
0x18003cab0  mov     rcx, r14; hDlg
0x18003cab3  call    cs:__imp_SetDlgItemTextW
0x18003cab9  mov     rdx, [rsi+10h]; HFONT
0x18003cabd  test    rdx, rdx
0x18003cac0  jz      short loc_18003CACA
0x18003cac2  mov     rcx, rsi; this
0x18003cac5  call    ?_SetFontOnControls@CSyncGeneralPage@@AEAAXPEAUHFONT__@@@Z; CSyncGeneralPage::_SetFontOnControls(HFONT__ *)
0x18003caca  mov     edi, [rdi+318h]
0x18003cad0  mov     edx, 20Fh; nIDDlgItem
0x18003cad5  mov     rcx, r14; hDlg
0x18003cad8  and     edi, 400000h
0x18003cade  call    cs:__imp_GetDlgItem
0x18003cae4  mov     ecx, edi
0x18003cae6  mov     rbx, rax
0x18003cae9  neg     ecx
0x18003caeb  mov     rcx, rax; hWnd
0x18003caee  sbb     edx, edx
0x18003caf0  and     edx, 5; nCmdShow
0x18003caf3  call    cs:__imp_ShowWindow
0x18003caf9  xor     edx, edx
0x18003cafb  mov     rcx, rbx; hWnd
0x18003cafe  test    edi, edi
0x18003cb00  setnz   dl; bEnable
0x18003cb03  call    cs:__imp_EnableWindow
0x18003cb09  mov     r8, [rsi+38h]
0x18003cb0d  mov     rdx, [rsi+18h]; HWND
0x18003cb11  mov     r8, [r8]; struct IShellItem *
0x18003cb14  call    ?SetItemIcon@CSyncBasePropertyPage@@IEAAXPEAUHWND__@@PEAUIShellItem@@@Z; CSyncBasePropertyPage::SetItemIcon(HWND__ *,IShellItem *)
0x18003cb19  mov     eax, 1
0x18003cb1e  mov     rcx, [rbp+57h+var_28]
0x18003cb22  xor     rcx, rsp; StackCookie
0x18003cb25  call    __security_check_cookie
0x18003cb2a  mov     rbx, [rsp+0C0h+arg_10]
0x18003cb32  add     rsp, 0A0h
0x18003cb39  pop     r15
0x18003cb3b  pop     r14
0x18003cb3d  pop     rdi
0x18003cb3e  pop     rsi
0x18003cb3f  pop     rbp
0x18003cb40  retn
```
