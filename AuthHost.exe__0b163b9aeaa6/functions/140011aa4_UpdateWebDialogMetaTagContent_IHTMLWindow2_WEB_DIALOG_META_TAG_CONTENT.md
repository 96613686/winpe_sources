# UpdateWebDialogMetaTagContent(IHTMLWindow2 *,_WEB_DIALOG_META_TAG_CONTENT *)

- ea: `0x140011aa4`
- end: `0x1400124ee`
- name: `?UpdateWebDialogMetaTagContent@@YAXPEAUIHTMLWindow2@@PEAU_WEB_DIALOG_META_TAG_CONTENT@@@Z`
- size: `2634`
- prototype: `void __fastcall(struct IHTMLWindow2 *, struct _WEB_DIALOG_META_TAG_CONTENT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a4b0`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x140003a8c`
- `0x14000429c`
- `0x1400096a8`
- `0x14000c3dc`
- `0x14000c45c`
- `0x14000cca0`
- `0x14000d8d8`
- `0x140011784`
- `0x140011810`
- `0x140011aa4`
- `0x1400127b0`
- `0x1400128d4`
- `0x140012a2c`
- `0x140012af8`
- `0x140012f22`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140011f0f`
- `msvcrt!_wcsicmp` at `0x140012005`
- `msvcrt!_wcsicmp` at `0x1400120b0`
- `msvcrt!_wcsicmp` at `0x1400121ae`
- `msvcrt!_wcsicmp` at `0x14001220d`
- `msvcrt!_wcsicmp` at `0x140012396`
- `msvcrt!_wcsicmp` at `0x140011f0f`
- `msvcrt!_wcsicmp` at `0x140012005`
- `msvcrt!_wcsicmp` at `0x1400120b0`
- `msvcrt!_wcsicmp` at `0x1400121ae`
- `msvcrt!_wcsicmp` at `0x14001220d`
- `msvcrt!_wcsicmp` at `0x140012396`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140011f36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140011f36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011f1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011f1b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x140011fbf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x140011fbf`
- `OLEAUT32!__imp_SysAllocString` at `0x14001202a`
- `OLEAUT32!__imp_SysAllocString` at `0x14001202a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14001204a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14001204a`
- `OLEAUT32!__imp_SysFreeString` at `0x140011ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x140011ecf`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f93`
- `OLEAUT32!__imp_SysFreeString` at `0x1400122d6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001232c`
- `OLEAUT32!__imp_SysFreeString` at `0x140012473`
- `OLEAUT32!__imp_SysFreeString` at `0x14001247e`
- `OLEAUT32!__imp_SysFreeString` at `0x140011ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x140011ecf`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f93`
- `OLEAUT32!__imp_SysFreeString` at `0x1400122d6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001232c`
- `OLEAUT32!__imp_SysFreeString` at `0x140012473`
- `OLEAUT32!__imp_SysFreeString` at `0x14001247e`
- `OLEAUT32!__imp_VariantClear` at `0x140011ec3`
- `OLEAUT32!__imp_VariantClear` at `0x140011f87`
- `OLEAUT32!__imp_VariantClear` at `0x1400122ca`
- `OLEAUT32!__imp_VariantClear` at `0x140011ec3`
- `OLEAUT32!__imp_VariantClear` at `0x140011f87`
- `OLEAUT32!__imp_VariantClear` at `0x1400122ca`
- `MSHTML!GetColorValueFromString` at `0x140012136`
- `MSHTML!GetColorValueFromString` at `0x140012136`

## string_xrefs

- `0x140011ba8`: `metaTagElementName.CopyFromString`
- `0x140011bf2`: `CleanUri`
- `0x140011cdc`: `metaTagContentAttributeName.CopyFromString`

## pseudocode

```c
void __fastcall UpdateWebDialogMetaTagContent(struct IHTMLWindow2 *a1, struct _WEB_DIALOG_META_TAG_CONTENT *a2)
{
  struct _WEB_DIALOG_META_TAG_CONTENT *v2; // rsi
  int v4; // eax
  char v5; // bl
  __int64 v6; // r15
  const wchar_t *v7; // rdi
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  OLECHAR *v16; // rcx
  int v17; // eax
  int v18; // r14d
  __int64 v19; // xmm6_8
  __int64 v20; // xmm7_8
  int v21; // edx
  int v22; // r8d
  const wchar_t *v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, _QWORD); // rdi
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rdi
  WCHAR *bstrVal; // rbx
  HMODULE ModuleHandleW; // rax
  BSTR v30; // rax
  __int64 v31; // rdx
  PVOID v32; // rcx
  const wchar_t *v33; // r8
  __int64 *v34; // rdx
  HRESULT ColorValueFromString; // eax
  __int64 v36; // r9
  PVOID v37; // rcx
  int v38; // eax
  int v39; // edx
  __int64 v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rcx
  wchar_t **p_String2; // rax
  __int64 v43; // rcx
  BSTR String1; // [rsp+38h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+48h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B8h] BYREF
  BSTR v48; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A8h] BYREF
  COLORREF pColor[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-90h] BYREF
  __int64 v53; // [rsp+80h] [rbp-88h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-80h] BYREF
  BSTR v55; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-70h] BYREF
  struct _WEB_DIALOG_META_TAG_CONTENT *v57; // [rsp+B0h] [rbp-58h]
  __int128 v58; // [rsp+B8h] [rbp-50h]
  __int64 v59; // [rsp+C8h] [rbp-40h]
  __int128 v60; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-20h]
  __int128 v62; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v63; // [rsp+108h] [rbp+0h]
  wchar_t *String2; // [rsp+118h] [rbp+10h] BYREF
  OLECHAR *v65; // [rsp+120h] [rbp+18h]
  COLORREF v66; // [rsp+128h] [rbp+20h]
  const wchar_t *v67; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int16 *v68; // [rsp+138h] [rbp+30h] BYREF
  int v69; // [rsp+140h] [rbp+38h]
  unsigned int v70; // [rsp+144h] [rbp+3Ch]
  _QWORD v71[32]; // [rsp+148h] [rbp+40h] BYREF
  WCHAR Buffer[264]; // [rsp+248h] [rbp+140h] BYREF

  v2 = a2;
  v57 = a2;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v55 = 0;
  v48 = 0;
  memset_0(&String2, 0, 0x130u);
  v66 = -1;
  v4 = ((__int64 (__fastcall *)(struct IHTMLWindow2 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))a1->lpVtbl->get_document)(
         a1,
         &v54);
  v5 = v4;
  v6 = 2;
  if ( v4 < 0 )
  {
    v7 = L"get_document";
LABEL_23:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        23,
        (unsigned int)&WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
        (_DWORD)v7,
        v5);
    }
    goto LABEL_123;
  }
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v54;
  v9 = **v54;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  v10 = v9(v8, &GUID_3050f485_98b5_11cf_bb82_00aa00bdce0b, &v53);
  v5 = v10;
  if ( v10 < 0 )
  {
    v7 = L"get_document3";
    goto LABEL_23;
  }
  v11 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
          &v55,
          L"meta");
  v5 = v11;
  if ( v11 < 0 )
  {
    v7 = L"metaTagElementName.CopyFromString";
    goto LABEL_23;
  }
  v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), BSTR *))(*v54)[40])(v54, &v48);
  v5 = v12;
  if ( v12 < 0 )
  {
    v7 = L"get_URL";
    goto LABEL_23;
  }
  v13 = CLoginForm::CleanUri(v48, &v68);
  v5 = v13;
  if ( v13 < 0 )
  {
    v7 = L"CleanUri";
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids, v48);
  }
  GetUrlDomain(v48, &String2);
  v14 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v53 + 376LL))(v53, v55, &v51);
  v5 = v14;
  if ( v14 < 0 )
  {
    v7 = L"getElementsByTagName";
    goto LABEL_23;
  }
  if ( !v51 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids);
    }
    goto LABEL_123;
  }
  LODWORD(v46) = 0;
  v58 = 0;
  v59 = 0;
  v61 = 0;
  bstrString = 0;
  LOWORD(v58) = 3;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 72LL))(v51, &v46);
  v5 = v15;
  if ( v15 < 0 )
  {
    v7 = L"get_metaTagCount";
    v16 = 0;
LABEL_22:
    SysFreeString(v16);
    goto LABEL_23;
  }
  v17 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
          &bstrString,
          L"content");
  v5 = v17;
  if ( v17 < 0 )
  {
    v7 = L"metaTagContentAttributeName.CopyFromString";
    v16 = bstrString;
    goto LABEL_22;
  }
  v18 = 0;
  if ( (int)v46 <= 0 )
    goto LABEL_118;
  v19 = v59;
  v20 = v61;
  do
  {
    v45 = 0;
    v47 = 0;
    v49 = 0;
    String1 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    pvarg.vt = 0;
    DWORD2(v58) = v18;
    v62 = 0;
    v63 = v20;
    v60 = v58;
    v61 = v19;
    v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD)))(*(_QWORD *)v51 + 88LL))(
            v51,
            &v60,
            &v62,
            &v45);
    if ( v21 < 0 )
    {
      v23 = L"item";
LABEL_39:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_dSd(*((_QWORD *)WPP_GLOBAL_Control + 7), v21, v22, v18, (__int64)v23, v21);
      }
      goto LABEL_114;
    }
    v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
    v25 = **v45;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v21 = v25(v24, &GUID_3050f203_98b5_11cf_bb82_00aa00bdce0b, &v47);
    if ( v21 < 0 )
    {
      v23 = L"get_metaTag";
      goto LABEL_39;
    }
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    v27 = **v47;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v21 = v27(v26, &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b, &v49);
    if ( v21 < 0 )
    {
      v23 = L"get_metaTagAsElement";
      goto LABEL_39;
    }
    v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), BSTR *))(*v47)[12])(
            v47,
            &String1);
    if ( v21 < 0 )
    {
      v23 = L"get_name";
      goto LABEL_39;
    }
    v21 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *))(*(_QWORD *)v49 + 64LL))(
            v49,
            bstrString,
            0,
            &pvarg);
    if ( v21 < 0 )
    {
      v23 = L"get_content";
      goto LABEL_39;
    }
    bstrVal = (WCHAR *)&szColor;
    if ( pvarg.vt == 8 && pvarg.llVal )
    {
      if ( _wcsicmp(pvarg.bstrVal, L"{3357C6C4-F2BD-4F41-8095-C8883B855ADD}") )
      {
        bstrVal = pvarg.bstrVal;
      }
      else
      {
        ModuleHandleW = GetModuleHandleW(0);
        LoadStringW(ModuleHandleW, 0x3E9u, Buffer, 260);
        bstrVal = Buffer;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)String1, (__int64)bstrVal);
    }
    if ( String1 )
    {
      if ( StrTrimW(bstrVal, L" ")
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids, bstrVal);
      }
      if ( _wcsicmp(String1, L"mswebdialog-title") )
      {
        if ( _wcsicmp(String1, L"mswebdialog-header-color") )
        {
          if ( _wcsicmp(String1, L"mswebdialog-logo") )
          {
            if ( _wcsicmp(String1, L"mswebdialog-newwindowurl") )
              goto LABEL_114;
            v39 = *bstrVal - 42;
            if ( *bstrVal == 42 )
              v39 = bstrVal[1];
            if ( v39 )
            {
              if ( v70 < 0x20 && (int)ResolveMetaTagUrl(v48, bstrVal, &v71[v70]) >= 0 )
              {
                if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
                  McTemplateU0z_EventWriteTransfer(v40, MetaTagNewWindowUrlEvent, v71[v70]);
                ++v70;
              }
            }
            else
            {
              v69 = 1;
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids);
              }
              if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
              {
                v33 = L"*";
                v34 = MetaTagNewWindowUrlEvent;
                goto LABEL_108;
              }
            }
          }
          else if ( !v67 && *bstrVal )
          {
            v38 = ResolveMetaTagUrl(v48, bstrVal, &v67);
            v33 = L"???";
            if ( v38 >= 0 )
              v33 = v67;
            if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
            {
              v34 = MetaTagLogoEvent;
              goto LABEL_108;
            }
          }
        }
        else
        {
          if ( v66 != -1 )
            goto LABEL_114;
          pColor[0] = -1;
          if ( *bstrVal )
          {
            ColorValueFromString = GetColorValueFromString(bstrVal, 0, 0, pColor);
            if ( ColorValueFromString >= 0 )
            {
              v36 = pColor[0] & 0xFFFFFF;
              v66 = pColor[0] & 0xFFFFFF;
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids, v36);
                v36 = v66;
              }
              if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
                McTemplateU0zd_EventWriteTransfer(v37, MetaTagHeaderColorEvent, bstrVal, v36);
              goto LABEL_114;
            }
          }
          else
          {
            LOBYTE(ColorValueFromString) = 13;
          }
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              20,
              (unsigned int)&WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
              (_DWORD)bstrVal,
              ColorValueFromString);
          }
          if ( (Microsoft_Windows_WebAuthEnableBits & 4) != 0 )
          {
            v33 = bstrVal;
            v34 = MetaTagHeaderColorWarningEvent;
            goto LABEL_108;
          }
        }
      }
      else if ( !v65 )
      {
        if ( *bstrVal )
        {
          v31 = -1;
          do
            ++v31;
          while ( bstrVal[v31] );
          if ( (unsigned int)v31 > 0x400 )
            LODWORD(v31) = 1024;
          v30 = SysAllocStringLen(bstrVal, v31);
        }
        else
        {
          v30 = SysAllocString(L" ");
        }
        v65 = v30;
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids, v30);
          v30 = v65;
        }
        if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
        {
          v33 = v30;
          v34 = MetaTagTitleEvent;
LABEL_108:
          McTemplateU0z_EventWriteTransfer(v32, v34, v33);
        }
      }
    }
LABEL_114:
    VariantClear(&pvarg);
    SysFreeString(String1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
    if ( v45 )
    {
      v45 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v41)[2])(v41);
    }
    ++v18;
  }
  while ( v18 < (int)v46 );
  v2 = v57;
  v6 = 2;
LABEL_118:
  SysFreeString(bstrString);
LABEL_123:
  if ( (unsigned int)HasWebDialogHeaderMetaTag((struct _WEB_DIALOG_META_TAG_CONTENT *)&String2) || v69 || v70 )
  {
    ClearWebDialogMetaTagContent(v2);
    p_String2 = &String2;
    do
    {
      *(_OWORD *)v2 = *(_OWORD *)p_String2;
      *((_OWORD *)v2 + 1) = *((_OWORD *)p_String2 + 1);
      *((_OWORD *)v2 + 2) = *((_OWORD *)p_String2 + 2);
      *((_OWORD *)v2 + 3) = *((_OWORD *)p_String2 + 3);
      *((_OWORD *)v2 + 4) = *((_OWORD *)p_String2 + 4);
      *((_OWORD *)v2 + 5) = *((_OWORD *)p_String2 + 5);
      *((_OWORD *)v2 + 6) = *((_OWORD *)p_String2 + 6);
      *((_OWORD *)v2 + 7) = *((_OWORD *)p_String2 + 7);
      v2 = (struct _WEB_DIALOG_META_TAG_CONTENT *)((char *)v2 + 128);
      p_String2 += 16;
      --v6;
    }
    while ( v6 );
    *(_OWORD *)v2 = *(_OWORD *)p_String2;
    *((_OWORD *)v2 + 1) = *((_OWORD *)p_String2 + 1);
    *((_OWORD *)v2 + 2) = *((_OWORD *)p_String2 + 2);
  }
  else if ( *(_QWORD *)v2 && String2 && !_wcsicmp(*(const wchar_t **)v2, String2) )
  {
    ClearWebDialogMetaTagContent((struct _WEB_DIALOG_META_TAG_CONTENT *)&String2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids, *(_QWORD *)v2);
    }
  }
  else
  {
    ClearWebDialogMetaTagContent(v2);
    ClearWebDialogMetaTagContent((struct _WEB_DIALOG_META_TAG_CONTENT *)&String2);
  }
  SysFreeString(v48);
  SysFreeString(v55);
  v43 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
}

```

## disassembly

```asm
0x140011aa4  mov     rax, rsp
0x140011aa7  mov     [rax+18h], rbx
0x140011aab  push    rbp
0x140011aac  push    rsi
0x140011aad  push    rdi
0x140011aae  push    r12
0x140011ab0  push    r13
0x140011ab2  push    r14
0x140011ab4  push    r15
0x140011ab6  lea     rbp, [rax-3C8h]
0x140011abd  sub     rsp, 490h
0x140011ac4  movaps  xmmword ptr [rax-48h], xmm6
0x140011ac8  movaps  xmmword ptr [rax-58h], xmm7
0x140011acc  movaps  xmmword ptr [rax-68h], xmm8
0x140011ad1  mov     rax, cs:__security_cookie
0x140011ad8  xor     rax, rsp
0x140011adb  mov     [rbp+3C0h+var_70], rax
0x140011ae2  mov     rsi, rdx
0x140011ae5  mov     [rbp+3C0h+var_418], rdx
0x140011ae9  mov     rbx, rcx
0x140011aec  xor     r12d, r12d
0x140011aef  mov     [rbp+3C0h+var_440], r12
0x140011af3  mov     [rsp+4C0h+var_448], r12
0x140011af8  mov     [rsp+4C0h+var_458], r12
0x140011afd  mov     [rbp+3C0h+var_438], r12
0x140011b01  mov     [rsp+4C0h+var_470], r12
0x140011b06  xor     edx, edx; Val
0x140011b08  mov     r8d, 130h; Size
0x140011b0e  lea     rcx, [rbp+3C0h+String2]; void *
0x140011b12  call    memset_0
0x140011b17  mov     [rbp+3C0h+var_3A0], 0FFFFFFFFh
0x140011b1e  mov     rax, [rbx]
0x140011b21  lea     rdx, [rbp+3C0h+var_440]
0x140011b25  mov     rcx, rbx
0x140011b28  mov     rax, [rax+1A0h]
0x140011b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b34  mov     ebx, eax
0x140011b36  lea     r15d, [r12+2]
0x140011b3b  lea     r14, WPP_GLOBAL_Control
0x140011b42  mov     r13b, 4
0x140011b45  test    eax, eax
0x140011b47  jns     short loc_140011B55
0x140011b49  lea     rdi, aGetDocument; "get_document"
0x140011b50  jmp     loc_140011CEE
0x140011b55  mov     rbx, [rbp+3C0h+var_440]
0x140011b59  mov     rax, [rbx]
0x140011b5c  mov     rdi, [rax]
0x140011b5f  lea     rcx, [rsp+4C0h+var_448]
0x140011b64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011b69  lea     r8, [rsp+4C0h+var_448]
0x140011b6e  lea     rdx, _GUID_3050f485_98b5_11cf_bb82_00aa00bdce0b
0x140011b75  mov     rcx, rbx
0x140011b78  mov     rax, rdi
0x140011b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b80  mov     ebx, eax
0x140011b82  test    eax, eax
0x140011b84  jns     short loc_140011B92
0x140011b86  lea     rdi, aGetDocument3; "get_document3"
0x140011b8d  jmp     loc_140011CEE
0x140011b92  lea     rdx, aMeta; "meta"
0x140011b99  lea     rcx, [rbp+3C0h+var_438]
0x140011b9d  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x140011ba2  mov     ebx, eax
0x140011ba4  test    eax, eax
0x140011ba6  jns     short loc_140011BB4
0x140011ba8  lea     rdi, aMetatagelement; "metaTagElementName.CopyFromString"
0x140011baf  jmp     loc_140011CEE
0x140011bb4  mov     rcx, [rbp+3C0h+var_440]
0x140011bb8  mov     rax, [rcx]
0x140011bbb  lea     rdx, [rsp+4C0h+var_470]
0x140011bc0  mov     rax, [rax+140h]
0x140011bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bcc  mov     ebx, eax
0x140011bce  test    eax, eax
0x140011bd0  jns     short loc_140011BDE
0x140011bd2  lea     rdi, aGetUrl; "get_URL"
0x140011bd9  jmp     loc_140011CEE
0x140011bde  lea     rdx, [rbp+3C0h+var_390]; unsigned __int16 **
0x140011be2  mov     rcx, [rsp+4C0h+var_470]; unsigned __int16 *
0x140011be7  call    ?CleanUri@CLoginForm@@SAJPEBGPEAPEAG@Z; CLoginForm::CleanUri(ushort const *,ushort * *)
0x140011bec  mov     ebx, eax
0x140011bee  test    eax, eax
0x140011bf0  jns     short loc_140011BFE
0x140011bf2  lea     rdi, aCleanuri; "CleanUri"
0x140011bf9  jmp     loc_140011CEE
0x140011bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c05  cmp     rcx, r14
0x140011c08  jz      short loc_140011C30
0x140011c0a  test    [rcx+44h], r13b
0x140011c0e  jz      short loc_140011C30
0x140011c10  cmp     byte ptr [rcx+41h], 5
0x140011c14  jb      short loc_140011C30
0x140011c16  mov     edx, 0Eh
0x140011c1b  mov     r9, [rsp+4C0h+var_470]
0x140011c20  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x140011c27  mov     rcx, [rcx+38h]
0x140011c2b  call    WPP_SF_S
0x140011c30  lea     rdx, [rbp+3C0h+String2]
0x140011c34  mov     rcx, [rsp+4C0h+var_470]
0x140011c39  call    _GetUrlDomain
0x140011c3e  mov     rcx, [rsp+4C0h+var_448]
0x140011c43  mov     rax, [rcx]
0x140011c46  lea     r8, [rsp+4C0h+var_458]
0x140011c4b  mov     rdx, [rbp+3C0h+var_438]
0x140011c4f  mov     rax, [rax+178h]
0x140011c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c5b  mov     ebx, eax
0x140011c5d  test    eax, eax
0x140011c5f  jns     short loc_140011C6D
0x140011c61  lea     rdi, aGetelementsbyt; "getElementsByTagName"
0x140011c68  jmp     loc_140011CEE
0x140011c6d  mov     rcx, [rsp+4C0h+var_458]
0x140011c72  test    rcx, rcx
0x140011c75  jz      loc_14001233B
0x140011c7b  mov     dword ptr [rsp+4C0h+var_480], r12d
0x140011c80  xorps   xmm0, xmm0
0x140011c83  xor     eax, eax
0x140011c85  movups  [rbp+3C0h+var_410], xmm0
0x140011c89  mov     [rbp+3C0h+var_400], rax
0x140011c8d  xorps   xmm8, xmm8
0x140011c91  mov     [rbp+3C0h+var_3E0], rax
0x140011c95  mov     [rsp+4C0h+bstrString], r12
0x140011c9a  mov     eax, 3
0x140011c9f  mov     word ptr [rbp+3C0h+var_410], ax
0x140011ca3  mov     rax, [rcx]
0x140011ca6  lea     rdx, [rsp+4C0h+var_480]
0x140011cab  mov     rax, [rax+48h]
0x140011caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cb4  mov     ebx, eax
0x140011cb6  test    eax, eax
0x140011cb8  jns     short loc_140011CC5
0x140011cba  lea     rdi, aGetMetatagcoun; "get_metaTagCount"
0x140011cc1  xor     ecx, ecx
0x140011cc3  jmp     short loc_140011CE8
0x140011cc5  lea     rdx, aContent; "content"
0x140011ccc  lea     rcx, [rsp+4C0h+bstrString]
0x140011cd1  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x140011cd6  mov     ebx, eax
0x140011cd8  test    eax, eax
0x140011cda  jns     short loc_140011D33
0x140011cdc  lea     rdi, aMetatagcontent; "metaTagContentAttributeName.CopyFromStr"...
0x140011ce3  mov     rcx, [rsp+4C0h+bstrString]; bstrString
0x140011ce8  call    cs:__imp_SysFreeString
0x140011cee  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cf5  cmp     rcx, r14
0x140011cf8  jz      loc_140012368
0x140011cfe  test    [rcx+44h], r13b
0x140011d02  jz      loc_140012368
0x140011d08  cmp     [rcx+41h], r15b
0x140011d0c  jb      loc_140012368
0x140011d12  mov     edx, 17h
0x140011d17  mov     dword ptr [rsp+4C0h+var_4A0], ebx
0x140011d1b  mov     r9, rdi
0x140011d1e  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x140011d25  mov     rcx, [rcx+38h]
0x140011d29  call    WPP_SF_Sd
0x140011d2e  jmp     loc_140012368
0x140011d33  mov     r14d, r12d
0x140011d36  cmp     dword ptr [rsp+4C0h+var_480], r12d
0x140011d3b  jle     loc_140012327
0x140011d41  mov     r15d, 400h
0x140011d47  movsd   xmm6, [rbp+3C0h+var_400]
0x140011d4c  movsd   xmm7, [rbp+3C0h+var_3E0]
0x140011d51  lea     rsi, WPP_GLOBAL_Control
0x140011d58  mov     [rsp+4C0h+var_488], r12
0x140011d5d  mov     [rsp+4C0h+var_478], r12
0x140011d62  mov     [rsp+4C0h+var_468], r12
0x140011d67  mov     [rsp+4C0h+String1], r12
0x140011d6c  xorps   xmm0, xmm0
0x140011d6f  xor     eax, eax
0x140011d71  movups  xmmword ptr [rbp+3C0h+pvarg], xmm0
0x140011d75  mov     qword ptr [rbp+3C0h+pvarg+10h], rax
0x140011d79  mov     word ptr [rbp+3C0h+pvarg], r12w
0x140011d7e  mov     dword ptr [rbp+3C0h+var_410+8], r14d
0x140011d82  mov     rcx, [rsp+4C0h+var_458]
0x140011d87  movaps  [rbp+3C0h+var_3D0], xmm8
0x140011d8c  movsd   [rbp+3C0h+var_3C0], xmm7
0x140011d91  movups  xmm0, [rbp+3C0h+var_410]
0x140011d95  movaps  [rbp+3C0h+var_3F0], xmm0
0x140011d99  movsd   [rbp+3C0h+var_3E0], xmm6
0x140011d9e  mov     rax, [rcx]
0x140011da1  lea     r9, [rsp+4C0h+var_488]
0x140011da6  lea     r8, [rbp+3C0h+var_3D0]
0x140011daa  lea     rdx, [rbp+3C0h+var_3F0]
0x140011dae  mov     rax, [rax+58h]
0x140011db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011db7  mov     edx, eax
0x140011db9  test    eax, eax
0x140011dbb  jns     short loc_140011DC9
0x140011dbd  lea     rcx, aItem; "item"
0x140011dc4  jmp     loc_140011E91
0x140011dc9  mov     rbx, [rsp+4C0h+var_488]
0x140011dce  mov     rax, [rbx]
0x140011dd1  mov     rdi, [rax]
0x140011dd4  lea     rcx, [rsp+4C0h+var_478]
0x140011dd9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011dde  lea     r8, [rsp+4C0h+var_478]
0x140011de3  lea     rdx, _GUID_3050f203_98b5_11cf_bb82_00aa00bdce0b
0x140011dea  mov     rcx, rbx
0x140011ded  mov     rax, rdi
0x140011df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011df5  mov     edx, eax
0x140011df7  test    eax, eax
0x140011df9  jns     short loc_140011E07
0x140011dfb  lea     rcx, aGetMetatag; "get_metaTag"
0x140011e02  jmp     loc_140011E91
0x140011e07  mov     rbx, [rsp+4C0h+var_478]
0x140011e0c  mov     rax, [rbx]
0x140011e0f  mov     rdi, [rax]
0x140011e12  lea     rcx, [rsp+4C0h+var_468]
0x140011e17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011e1c  lea     r8, [rsp+4C0h+var_468]
0x140011e21  lea     rdx, _GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b
0x140011e28  mov     rcx, rbx
0x140011e2b  mov     rax, rdi
0x140011e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e33  mov     edx, eax
0x140011e35  test    eax, eax
0x140011e37  jns     short loc_140011E42
0x140011e39  lea     rcx, aGetMetatagasel; "get_metaTagAsElement"
0x140011e40  jmp     short loc_140011E91
0x140011e42  mov     rcx, [rsp+4C0h+var_478]
0x140011e47  mov     rax, [rcx]
0x140011e4a  lea     rdx, [rsp+4C0h+String1]
0x140011e4f  mov     rax, [rax+60h]
0x140011e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e58  mov     edx, eax
0x140011e5a  test    eax, eax
0x140011e5c  jns     short loc_140011E67
0x140011e5e  lea     rcx, aGetName; "get_name"
0x140011e65  jmp     short loc_140011E91
0x140011e67  mov     rcx, [rsp+4C0h+var_468]
0x140011e6c  mov     rax, [rcx]
0x140011e6f  lea     r9, [rbp+3C0h+pvarg]
0x140011e73  xor     r8d, r8d
0x140011e76  mov     rdx, [rsp+4C0h+bstrString]
0x140011e7b  mov     rax, [rax+40h]
0x140011e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e84  mov     edx, eax
0x140011e86  test    eax, eax
0x140011e88  jns     short loc_140011EF1
0x140011e8a  lea     rcx, aGetContent; "get_content"
0x140011e91  mov     rax, cs:WPP_GLOBAL_Control
0x140011e98  cmp     rax, rsi
0x140011e9b  jz      short loc_140011EBF
0x140011e9d  test    [rax+44h], r13b
0x140011ea1  jz      short loc_140011EBF
0x140011ea3  cmp     byte ptr [rax+41h], 5
0x140011ea7  jb      short loc_140011EBF
0x140011ea9  mov     dword ptr [rsp+4C0h+var_498], edx
0x140011ead  mov     [rsp+4C0h+var_4A0], rcx
0x140011eb2  mov     r9d, r14d
0x140011eb5  mov     rcx, [rax+38h]
0x140011eb9  call    WPP_SF_dSd
0x140011ebe  nop
0x140011ebf  lea     rcx, [rbp+3C0h+pvarg]; pvarg
0x140011ec3  call    cs:__imp_VariantClear
0x140011ec9  nop
0x140011eca  mov     rcx, [rsp+4C0h+String1]; bstrString
0x140011ecf  call    cs:__imp_SysFreeString
0x140011ed5  nop
0x140011ed6  lea     rcx, [rsp+4C0h+var_468]
0x140011edb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011ee0  nop
0x140011ee1  lea     rcx, [rsp+4C0h+var_478]
0x140011ee6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140011eeb  nop
0x140011eec  jmp     loc_1400122F3
0x140011ef1  lea     rbx, szColor
0x140011ef8  cmp     word ptr [rbp+3C0h+pvarg], 8
0x140011efd  jnz     short loc_140011F49
0x140011eff  mov     rcx, qword ptr [rbp+3C0h+pvarg+8]; String1
0x140011f03  test    rcx, rcx
0x140011f06  jz      short loc_140011F49
0x140011f08  lea     rdx, a3357c6c4F2bd4f; "{3357C6C4-F2BD-4F41-8095-C8883B855ADD}"
0x140011f0f  call    cs:__imp__wcsicmp
0x140011f15  test    eax, eax
0x140011f17  jnz     short loc_140011F45
0x140011f19  xor     ecx, ecx; lpModuleName
0x140011f1b  call    cs:__imp_GetModuleHandleW
0x140011f21  mov     rcx, rax; hInstance
0x140011f24  mov     r9d, 104h; cchBufferMax
0x140011f2a  lea     r8, [rbp+3C0h+Buffer]; lpBuffer
0x140011f31  mov     edx, 3E9h; uID
0x140011f36  call    cs:__imp_LoadStringW
0x140011f3c  lea     rbx, [rbp+3C0h+Buffer]
0x140011f43  jmp     short loc_140011F49
0x140011f45  mov     rbx, qword ptr [rbp+3C0h+pvarg+8]
0x140011f49  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f50  cmp     rcx, rsi
0x140011f53  jz      short loc_140011F7C
0x140011f55  test    [rcx+44h], r13b
0x140011f59  jz      short loc_140011F7C
0x140011f5b  cmp     byte ptr [rcx+41h], 5
0x140011f5f  jb      short loc_140011F7C
0x140011f61  mov     [rsp+4C0h+var_498], rbx; __int64
0x140011f66  mov     rax, [rsp+4C0h+String1]
0x140011f6b  mov     [rsp+4C0h+var_4A0], rax; __int64
0x140011f70  mov     r9d, r14d
0x140011f73  mov     rcx, [rcx+38h]; LoggerHandle
  ... truncated ...
```
