# CEventGeneralPage::OnInitDialog(HWND__ *,HWND__ *,__int64)

- ea: `0x18003d5d0`
- end: `0x18003d8a4`
- name: `?OnInitDialog@CEventGeneralPage@@MEAA_JPEAUHWND__@@0_J@Z`
- size: `724`
- prototype: `__int64 __fastcall(CEventGeneralPage *__hidden this, HWND hDlg, HWND, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008584`
- `0x18003d5d0`
- `0x18003d978`
- `0x18004c098`
- `0x18004c214`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d79b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d79b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d7b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d7b7`
- `USER32!GetDlgItem` at `0x18003d60f`
- `USER32!GetDlgItem` at `0x18003d60f`
- `USER32!SetDlgItemTextW` at `0x18003d630`
- `USER32!SetDlgItemTextW` at `0x18003d645`
- `USER32!SetDlgItemTextW` at `0x18003d65a`
- `USER32!SetDlgItemTextW` at `0x18003d66f`
- `USER32!SetDlgItemTextW` at `0x18003d688`
- `USER32!SetDlgItemTextW` at `0x18003d790`
- `USER32!SetDlgItemTextW` at `0x18003d815`
- `USER32!SetDlgItemTextW` at `0x18003d852`
- `USER32!SetDlgItemTextW` at `0x18003d630`
- `USER32!SetDlgItemTextW` at `0x18003d645`
- `USER32!SetDlgItemTextW` at `0x18003d65a`
- `USER32!SetDlgItemTextW` at `0x18003d66f`
- `USER32!SetDlgItemTextW` at `0x18003d688`
- `USER32!SetDlgItemTextW` at `0x18003d790`
- `USER32!SetDlgItemTextW` at `0x18003d815`
- `USER32!SetDlgItemTextW` at `0x18003d852`
- `PROPSYS!PSGetPropertyDescription` at `0x18003d6a9`
- `PROPSYS!PSGetPropertyDescription` at `0x18003d6a9`

## string_xrefs

- `0x18003d828`: `<a id="openlink">%s</a>`

## pseudocode

```c
__int64 __fastcall CEventGeneralPage::OnInitDialog(CEventGeneralPage *this, HWND hDlg, HWND a3)
{
  HWND DlgItem; // rax
  __int64 v6; // r14
  HWND v7; // rsi
  int v8; // ebx
  __int64 v9; // rax
  CSyncBasePropertyPage *v10; // rcx
  HFONT v11; // rdx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpString; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h]
  WCHAR String[264]; // [rsp+80h] [rbp-80h] BYREF

  CSyncBasePropertyPage::_CreateBoldFont((HWND *)this);
  DlgItem = GetDlgItem(hDlg, 541);
  v6 = *((_QWORD *)this + 3);
  v7 = (HWND)*((_QWORD *)this + 1);
  *((_QWORD *)this + 4) = DlgItem;
  SetDlgItemTextW(v7, 542, (LPCWSTR)(v6 + 292));
  SetDlgItemTextW(v7, 544, (LPCWSTR)(v6 + 2364));
  SetDlgItemTextW(v7, 546, (LPCWSTR)(v6 + 2620));
  SetDlgItemTextW(v7, 550, (LPCWSTR)(v6 + 548));
  SetDlgItemTextW(v7, 553, (LPCWSTR)(*((_QWORD *)this + 3) + 2888LL));
  ppv = 0;
  if ( PSGetPropertyDescription(&PKEY_Sync_EventLevel, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, &ppv) < 0 )
    goto LABEL_11;
  v14 = 0;
  v8 = (*(__int64 (__fastcall **)(void *, GUID *, __int64 *))(*(_QWORD *)ppv + 160LL))(
         ppv,
         &GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6,
         &v14);
  if ( v8 >= 0 )
  {
    v19 = 0;
    v9 = *((_QWORD *)this + 3);
    *(_OWORD *)pvar = 0;
    LODWORD(pvar[1]) = *(_DWORD *)(v9 + 2884);
    LOWORD(pvar[0]) = 19;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *, unsigned int *))(*(_QWORD *)v14 + 48LL))(v14, pvar, &v13);
    if ( v8 >= 0 )
    {
      v16 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v14 + 32LL))(
             v14,
             v13,
             &GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2,
             &v16);
      if ( v8 >= 0 )
      {
        lpString = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v16 + 56LL))(v16, &lpString);
        if ( v8 >= 0 )
        {
          SetDlgItemTextW(v7, 548, lpString);
          CoTaskMemFree((LPVOID)lpString);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      PropVariantClear(pvar);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 < 0 )
  {
LABEL_11:
    if ( (int)StringCchPrintfW(
                (unsigned __int16 *)pvar,
                0x10u,
                L"%d",
                *(unsigned int *)(*((_QWORD *)this + 3) + 2884LL)) >= 0 )
      SetDlgItemTextW(v7, 548, (LPCWSTR)pvar);
  }
  if ( *(_WORD *)(v6 + 1068) )
  {
    if ( (int)StringCchPrintfW(String, 0x104u, L"<a id=\"openlink\">%s</a>") < 0 )
      String[0] = 0;
    SetDlgItemTextW(v7, 555, String);
  }
  v11 = (HFONT)*((_QWORD *)this + 2);
  if ( v11 )
    CEventGeneralPage::_SetFontOnControls(this, v11);
  CSyncBasePropertyPage::SetItemIcon(v10, *((HWND *)this + 4), **((struct IShellItem ***)this + 3));
  return 1;
}

```

## disassembly

```asm
0x18003d5d0  mov     [rsp-8+arg_10], rbx
0x18003d5d5  push    rbp
0x18003d5d6  push    rsi
0x18003d5d7  push    rdi
0x18003d5d8  push    r14
0x18003d5da  push    r15
0x18003d5dc  lea     rbp, [rsp-1A0h]
0x18003d5e4  sub     rsp, 2A0h
0x18003d5eb  mov     rax, cs:__security_cookie
0x18003d5f2  xor     rax, rsp
0x18003d5f5  mov     [rbp+1C0h+var_30], rax
0x18003d5fc  mov     rbx, rdx
0x18003d5ff  mov     rdi, rcx
0x18003d602  call    ?_CreateBoldFont@CSyncBasePropertyPage@@AEAAJXZ; CSyncBasePropertyPage::_CreateBoldFont(void)
0x18003d607  mov     edx, 21Dh; nIDDlgItem
0x18003d60c  mov     rcx, rbx; hDlg
0x18003d60f  call    cs:__imp_GetDlgItem
0x18003d615  mov     r14, [rdi+18h]
0x18003d619  mov     edx, 21Eh; nIDDlgItem
0x18003d61e  mov     rsi, [rdi+8]
0x18003d622  mov     rcx, rsi; hDlg
0x18003d625  mov     [rdi+20h], rax
0x18003d629  lea     r8, [r14+124h]; lpString
0x18003d630  call    cs:__imp_SetDlgItemTextW
0x18003d636  lea     r8, [r14+93Ch]; lpString
0x18003d63d  mov     edx, 220h; nIDDlgItem
0x18003d642  mov     rcx, rsi; hDlg
0x18003d645  call    cs:__imp_SetDlgItemTextW
0x18003d64b  lea     r8, [r14+0A3Ch]; lpString
0x18003d652  mov     edx, 222h; nIDDlgItem
0x18003d657  mov     rcx, rsi; hDlg
0x18003d65a  call    cs:__imp_SetDlgItemTextW
0x18003d660  lea     r8, [r14+224h]; lpString
0x18003d667  mov     edx, 226h; nIDDlgItem
0x18003d66c  mov     rcx, rsi; hDlg
0x18003d66f  call    cs:__imp_SetDlgItemTextW
0x18003d675  mov     r8, [rdi+18h]
0x18003d679  mov     edx, 229h; nIDDlgItem
0x18003d67e  add     r8, 0B48h; lpString
0x18003d685  mov     rcx, rsi; hDlg
0x18003d688  call    cs:__imp_SetDlgItemTextW
0x18003d68e  xor     r15d, r15d
0x18003d691  lea     r8, [rsp+2C0h+ppv]; ppv
0x18003d696  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x18003d69d  mov     [rsp+2C0h+ppv], r15
0x18003d6a2  lea     rcx, PKEY_Sync_EventLevel; propkey
0x18003d6a9  call    cs:__imp_PSGetPropertyDescription
0x18003d6af  test    eax, eax
0x18003d6b1  js      loc_18003D7E3
0x18003d6b7  mov     rcx, [rsp+2C0h+ppv]
0x18003d6bc  lea     r8, [rsp+2C0h+var_288]
0x18003d6c1  mov     [rsp+2C0h+var_288], r15
0x18003d6c6  lea     rdx, _GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6
0x18003d6cd  mov     rax, [rcx]
0x18003d6d0  mov     rax, [rax+0A0h]
0x18003d6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6dc  mov     ebx, eax
0x18003d6de  test    eax, eax
0x18003d6e0  js      loc_18003D7CE
0x18003d6e6  xor     eax, eax
0x18003d6e8  lea     r8, [rsp+2C0h+var_290]
0x18003d6ed  mov     [rsp+2C0h+var_258], rax
0x18003d6f2  lea     rdx, [rsp+2C0h+pvar]
0x18003d6f7  mov     rax, [rdi+18h]
0x18003d6fb  xorps   xmm0, xmm0
0x18003d6fe  movups  xmmword ptr [rsp+2C0h+pvar], xmm0
0x18003d703  mov     ecx, [rax+0B44h]
0x18003d709  lea     eax, [r15+13h]
0x18003d70d  mov     dword ptr [rsp+2C0h+pvar+8], ecx
0x18003d711  mov     rcx, [rsp+2C0h+var_288]
0x18003d716  mov     word ptr [rsp+2C0h+pvar], ax
0x18003d71b  mov     [rsp+2C0h+var_290], r15d
0x18003d720  mov     rax, [rcx]
0x18003d723  mov     rax, [rax+30h]
0x18003d727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d72c  mov     ebx, eax
0x18003d72e  test    eax, eax
0x18003d730  js      loc_18003D7BD
0x18003d736  mov     rcx, [rsp+2C0h+var_288]
0x18003d73b  lea     r9, [rsp+2C0h+var_278]
0x18003d740  mov     edx, [rsp+2C0h+var_290]
0x18003d744  lea     r8, _GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2
0x18003d74b  mov     [rsp+2C0h+var_278], r15
0x18003d750  mov     rax, [rcx]
0x18003d753  mov     rax, [rax+20h]
0x18003d757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d75c  mov     ebx, eax
0x18003d75e  test    eax, eax
0x18003d760  js      short loc_18003D7B2
0x18003d762  mov     rcx, [rsp+2C0h+var_278]
0x18003d767  lea     rdx, [rsp+2C0h+lpString]
0x18003d76c  mov     [rsp+2C0h+lpString], r15
0x18003d771  mov     rax, [rcx]
0x18003d774  mov     rax, [rax+38h]
0x18003d778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d77d  mov     ebx, eax
0x18003d77f  test    eax, eax
0x18003d781  js      short loc_18003D7A1
0x18003d783  mov     r8, [rsp+2C0h+lpString]; lpString
0x18003d788  mov     edx, 224h; nIDDlgItem
0x18003d78d  mov     rcx, rsi; hDlg
0x18003d790  call    cs:__imp_SetDlgItemTextW
0x18003d796  mov     rcx, [rsp+2C0h+lpString]; pv
0x18003d79b  call    cs:__imp_CoTaskMemFree
0x18003d7a1  mov     rcx, [rsp+2C0h+var_278]
0x18003d7a6  mov     rax, [rcx]
0x18003d7a9  mov     rax, [rax+10h]
0x18003d7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7b2  lea     rcx, [rsp+2C0h+pvar]; pvar
0x18003d7b7  call    cs:__imp_PropVariantClear
0x18003d7bd  mov     rcx, [rsp+2C0h+var_288]
0x18003d7c2  mov     rax, [rcx]
0x18003d7c5  mov     rax, [rax+10h]
0x18003d7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7ce  mov     rcx, [rsp+2C0h+ppv]
0x18003d7d3  mov     rax, [rcx]
0x18003d7d6  mov     rax, [rax+10h]
0x18003d7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7df  test    ebx, ebx
0x18003d7e1  jns     short loc_18003D81B
0x18003d7e3  mov     r9, [rdi+18h]
0x18003d7e7  lea     r8, aD; "%d"
0x18003d7ee  mov     edx, 10h; unsigned __int64
0x18003d7f3  lea     rcx, [rsp+2C0h+pvar]; unsigned __int16 *
0x18003d7f8  mov     r9d, [r9+0B44h]
0x18003d7ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d804  test    eax, eax
0x18003d806  js      short loc_18003D81B
0x18003d808  lea     r8, [rsp+2C0h+pvar]; lpString
0x18003d80d  mov     edx, 224h; nIDDlgItem
0x18003d812  mov     rcx, rsi; hDlg
0x18003d815  call    cs:__imp_SetDlgItemTextW
0x18003d81b  lea     r9, [r14+42Ch]
0x18003d822  cmp     [r9], r15w
0x18003d826  jz      short loc_18003D858
0x18003d828  lea     r8, aAIdOpenlinkSA; "<a id=\"openlink\">%s</a>"
0x18003d82f  mov     edx, 104h; unsigned __int64
0x18003d834  lea     rcx, [rbp+1C0h+String]; unsigned __int16 *
0x18003d838  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d83d  test    eax, eax
0x18003d83f  jns     short loc_18003D846
0x18003d841  mov     [rbp+1C0h+String], r15w
0x18003d846  lea     r8, [rbp+1C0h+String]; lpString
0x18003d84a  mov     edx, 22Bh; nIDDlgItem
0x18003d84f  mov     rcx, rsi; hDlg
0x18003d852  call    cs:__imp_SetDlgItemTextW
0x18003d858  mov     rdx, [rdi+10h]; HFONT
0x18003d85c  test    rdx, rdx
0x18003d85f  jz      short loc_18003D869
0x18003d861  mov     rcx, rdi; this
0x18003d864  call    ?_SetFontOnControls@CEventGeneralPage@@AEAAXPEAUHFONT__@@@Z; CEventGeneralPage::_SetFontOnControls(HFONT__ *)
0x18003d869  mov     r8, [rdi+18h]
0x18003d86d  mov     rdx, [rdi+20h]; HWND
0x18003d871  mov     r8, [r8]; struct IShellItem *
0x18003d874  call    ?SetItemIcon@CSyncBasePropertyPage@@IEAAXPEAUHWND__@@PEAUIShellItem@@@Z; CSyncBasePropertyPage::SetItemIcon(HWND__ *,IShellItem *)
0x18003d879  mov     eax, 1
0x18003d87e  mov     rcx, [rbp+1C0h+var_30]
0x18003d885  xor     rcx, rsp; StackCookie
0x18003d888  call    __security_check_cookie
0x18003d88d  mov     rbx, [rsp+2C0h+arg_10]
0x18003d895  add     rsp, 2A0h
0x18003d89c  pop     r15
0x18003d89e  pop     r14
0x18003d8a0  pop     rdi
0x18003d8a1  pop     rsi
0x18003d8a2  pop     rbp
0x18003d8a3  retn
```
