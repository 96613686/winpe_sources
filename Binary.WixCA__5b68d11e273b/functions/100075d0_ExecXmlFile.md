# ExecXmlFile

- ea: `0x100075d0`
- end: `0x10007d8c`
- name: `ExecXmlFile`
- size: `1980`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x100075d0`
- `0x1000a952`
- `0x1000ad15`
- `0x1000b556`
- `0x1000b8d3`
- `0x1000c9b7`
- `0x1000cca3`
- `0x1000ce26`
- `0x1000cf55`
- `0x1000cfc6`
- `0x1000d085`
- `0x1000d0eb`
- `0x1000d171`
- `0x1000d1f7`
- `0x1000d326`
- `0x1000d47e`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e13e`
- `0x1000e662`
- `0x1000ef44`
- `0x1000efcc`
- `0x10010509`
- `0x10010563`
- `0x10010583`
- `0x10010646`
- `0x10010671`

## import_xrefs

- `OLEAUT32!SysAllocString` at `0x1000760a`
- `OLEAUT32!SysAllocString` at `0x10007652`
- `OLEAUT32!SysAllocString` at `0x100075da`
- `OLEAUT32!SysFreeString` at `0x10007d20`
- `OLEAUT32!SysFreeString` at `0x10007d20`
- `OLEAUT32!VariantInit` at `0x10007640`
- `OLEAUT32!VariantInit` at `0x10007640`
- `OLEAUT32!VariantClear` at `0x10007d2a`
- `OLEAUT32!VariantClear` at `0x10007d2a`
- `KERNEL32!Sleep` at `0x10007bf5`
- `KERNEL32!Sleep` at `0x10007bf5`

## string_xrefs

- `0x1000761e`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\xmlfile.cpp`
- `0x10007649`: `XPath`
- `0x10007668`: `ExecXmlFile`
- `0x1000768e`: `failed to initialize xml utilities`
- `0x10007cb4`: `failed to read file name from custom action data`
- `0x10007c15`: `Custom action was told to act on a 64-bit component, but the custom action process is not running in WOW.`
- `0x10007c0b`: `Custom action was told to act on a 64-bit component, but was unable to disable filesystem redirection through the Wow64 API.`
- `0x100077a9`: `Configuring Xml File: %ls`
- `0x10007c31`: `failed in querying IXMLDOMDocument2 interface`
- `0x10007c3b`: `Error: current MSXML version does not support xpath query.`
- `0x100078d4`: `failed to load XML file: %ls`
- `0x10007941`: `failed to find any nodes: %ls in XML file: %ls`
- `0x10007a4a`: `failed to set text to: %ls for element %ls.  Make sure that XPath points to an element.`
- `0x10007c81`: `failed to find node: %ls in XML file: %ls`
- `0x10007c55`: `failed to create child element: %ls`
- `0x10007ac6`: `failed to remove attribute: %ls`
- `0x10007c68`: `failed to delete child node: %ls`
- `0x10007c98`: `Failed to save changes to XML file: %ls`
- `0x10007ca2`: `Failed to save changes to XML file: %ls`
- `0x10007be1`: `Unable to save changes to XML file: %ls, retry attempt: %x`

## pseudocode

```c
int __stdcall ExecXmlFile(MSIHANDLE hInstall)
{
  int v1; // ebx
  int v2; // esi
  int v3; // edi
  _WORD *i; // eax
  int v5; // eax
  int v6; // edi
  int v7; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13; // [esp-8h] [ebp-74h]
  const char *v14; // [esp-8h] [ebp-74h]
  const char *v15; // [esp-4h] [ebp-70h]
  const char *v16; // [esp-4h] [ebp-70h]
  VARIANTARG pvarg; // [esp+Ch] [ebp-60h] BYREF
  struct _FILETIME LastWriteTime; // [esp+1Ch] [ebp-50h] BYREF
  int v19; // [esp+24h] [ebp-48h]
  int v20; // [esp+28h] [ebp-44h] BYREF
  int v21; // [esp+2Ch] [ebp-40h] BYREF
  BSTR bstrString; // [esp+30h] [ebp-3Ch]
  int v23; // [esp+34h] [ebp-38h] BYREF
  int v24; // [esp+38h] [ebp-34h]
  int v25; // [esp+3Ch] [ebp-30h] BYREF
  int v26; // [esp+40h] [ebp-2Ch]
  int v27; // [esp+44h] [ebp-28h] BYREF
  DWORD pcchValueBuf; // [esp+48h] [ebp-24h] BYREF
  int v29; // [esp+4Ch] [ebp-20h] BYREF
  OLECHAR *v30; // [esp+50h] [ebp-1Ch] BYREF
  int v31; // [esp+54h] [ebp-18h] BYREF
  OLECHAR *v32; // [esp+58h] [ebp-14h] BYREF
  OLECHAR *psz; // [esp+5Ch] [ebp-10h] BYREF
  wchar_t SubStr[2]; // [esp+60h] [ebp-Ch] BYREF
  int v35; // [esp+64h] [ebp-8h] BYREF
  LPCWSTR lpFileName; // [esp+68h] [ebp-4h] BYREF
  signed int hInstalla; // [esp+74h] [ebp+8h]

  v1 = 0;
  v26 = 0;
  pcchValueBuf = 0;
  lpFileName = 0;
  v30 = 0;
  psz = 0;
  v32 = 0;
  *(_DWORD *)SubStr = 0;
  v29 = 0;
  v35 = 0;
  v27 = 0;
  v25 = 0;
  v23 = 0;
  bstrString = SysAllocString(L"SelectionLanguage");
  if ( !bstrString )
  {
    v13 = 506;
LABEL_3:
    v2 = -2147024882;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\xmlfile.cpp", v13, -2147024882);
    sub_1000DA66(-2147024882, "failed SysAllocString");
    goto LABEL_140;
  }
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.lVal = (LONG)SysAllocString(L"XPath");
  if ( !pvarg.lVal )
  {
    v13 = 511;
    goto LABEL_3;
  }
  v2 = sub_1000D51F(hInstall, (int)"ExecXmlFile");
  if ( v2 < 0 )
  {
    v15 = "failed to initialize";
LABEL_8:
    sub_1000DA66(v2, v15);
    goto LABEL_140;
  }
  v2 = sub_1000CCA3();
  if ( v2 < 0 )
  {
    v15 = "failed to initialize xml utilities";
    goto LABEL_8;
  }
  v2 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v2 < 0 )
  {
    v15 = "failed to get CustomActionData";
    goto LABEL_8;
  }
  sub_1000D9AB(0, "CustomActionData: %ls");
  *(_DWORD *)SubStr = pcchValueBuf;
  v2 = sub_1000EF44((wchar_t)SubStr, (int)&v31);
  if ( v2 < 0 )
  {
    v15 = "failed to process CustomActionData";
    goto LABEL_8;
  }
  sub_10010583();
  v3 = sub_10010646();
  v19 = v3;
  if ( v31 != 1 && v31 != 2 )
  {
    v2 = -2147024809;
    v15 = "invalid custom action data";
    goto LABEL_8;
  }
  i = *(_WORD **)SubStr;
  if ( !*(_DWORD *)SubStr )
    goto LABEL_140;
  while ( 2 )
  {
    if ( !*i )
      goto LABEL_138;
    v2 = sub_1000EF44((wchar_t)SubStr, (int)&v21);
    if ( v2 < 0 )
    {
LABEL_137:
      sub_1000DA66(v2, "failed to process CustomActionData");
      goto LABEL_138;
    }
    v2 = sub_1000EFCC((wchar_t)SubStr, (int)&lpFileName);
    if ( v2 < 0 )
    {
      sub_1000DA66(v2, "failed to read file name from custom action data");
      goto LABEL_138;
    }
    v24 = 0;
    if ( v29 )
    {
      (*(void (__stdcall **)(int))(*(_DWORD *)v29 + 8))(v29);
      v29 = 0;
    }
    if ( v31 == 2 )
    {
      if ( !v3 )
      {
        v16 = "Custom action was told to act on a 64-bit component, but the custom action process is not running in WOW.";
        goto LABEL_122;
      }
      v2 = sub_10010509();
      if ( v2 < 0 )
      {
        sub_1000DA66(
          v2,
          "Custom action was told to act on a 64-bit component, but was unable to disable filesystem redirection through the Wow64 API.");
        goto LABEL_138;
      }
      v26 = 1;
    }
    v5 = sub_1000CE26((OLECHAR *)lpFileName, 1, (int)&v29);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      hInstalla = 0;
    }
    else
    {
      v6 = v5;
      v2 = 0;
      hInstalla = v5;
    }
    sub_1000D9AB(1, "Configuring Xml File: %ls");
    if ( v21 == 1 )
    {
      if ( dword_1003390C )
      {
        if ( v6 >= 0 )
        {
          v2 = (**(int (__stdcall ***)(int, int *, int *))v29)(v29, dword_100223C0, &v23);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "failed in querying IXMLDOMDocument2 interface");
            goto LABEL_138;
          }
          v2 = (*(int (__stdcall **)(int, BSTR, _DWORD, ULONG, LONG, LONG))(*(_DWORD *)v23 + 320))(
                 v23,
                 bstrString,
                 *(_DWORD *)&pvarg.vt,
                 pvarg.decVal.Hi32,
                 pvarg.lVal,
                 pvarg.cyVal.Hi);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "failed in setting SelectionLanguage");
            goto LABEL_138;
          }
        }
        goto LABEL_36;
      }
      v16 = "Error: current MSXML version does not support xpath query.";
LABEL_122:
      v2 = -2147467263;
      sub_1000DA66(-2147467263, v16);
      goto LABEL_138;
    }
LABEL_36:
    for ( i = *(_WORD **)SubStr; *(_DWORD *)SubStr; i = *(_WORD **)SubStr )
    {
      if ( !*i )
        break;
      v2 = sub_1000EF44((wchar_t)SubStr, (int)&v31);
      if ( v2 < 0 )
        goto LABEL_137;
      if ( v31 == 1 || v31 == 2 )
      {
        i = *(_WORD **)SubStr;
        break;
      }
      v2 = sub_1000EF44((wchar_t)SubStr, (int)&v20);
      if ( v2 < 0 )
        goto LABEL_137;
      if ( v20 == 1 )
        v24 = 1;
      v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v30);
      if ( v2 < 0 )
        goto LABEL_137;
      v2 = sub_1000EFCC((wchar_t)SubStr, (int)&psz);
      if ( v2 < 0 )
        goto LABEL_137;
      v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v32);
      if ( v2 < 0 )
        goto LABEL_137;
      if ( hInstalla >= 0 )
      {
        if ( v35 )
        {
          (*(void (__stdcall **)(int))(*(_DWORD *)v35 + 8))(v35);
          v35 = 0;
        }
        if ( v31 == 7 )
        {
          v2 = sub_1000D0EB(v29, v30, (int)&v25);
          if ( v2 == 1 )
            v2 = -2147020584;
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "failed to find any nodes: %ls in XML file: %ls");
LABEL_59:
            sub_1000E13E(25532, v2, INSTALLMESSAGE_ERROR, 2);
            goto LABEL_138;
          }
          while ( 1 )
          {
            (*(void (__stdcall **)(int, int *))(*(_DWORD *)v25 + 36))(v25, &v35);
            if ( !v35 )
              break;
            if ( psz && *psz )
            {
              v2 = sub_1000D1F7(v35, psz, v32);
              if ( v2 < 0 )
                goto LABEL_63;
            }
            else
            {
              v2 = sub_1000D326(v35, v32);
              if ( v2 < 0 )
                goto LABEL_78;
            }
            if ( v35 )
            {
              (*(void (__stdcall **)(int))(*(_DWORD *)v35 + 8))(v35);
              v35 = 0;
            }
          }
        }
        else
        {
          v2 = sub_1000D171(v29, v30, (int)&v35);
          if ( v2 == 1 )
            v2 = -2147020584;
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "failed to find node: %ls in XML file: %ls");
            goto LABEL_59;
          }
          switch ( v31 )
          {
            case 3:
              if ( psz && *psz )
              {
                v2 = sub_1000D1F7(v35, psz, v32);
                if ( v2 < 0 )
                {
LABEL_63:
                  sub_1000DA66(v2, "failed to set attribute: %ls to value %ls");
                  goto LABEL_138;
                }
              }
              else
              {
                v2 = sub_1000D326(v35, v32);
                if ( v2 < 0 )
                {
LABEL_78:
                  sub_1000DA66(
                    v2,
                    "failed to set text to: %ls for element %ls.  Make sure that XPath points to an element.");
                  goto LABEL_138;
                }
              }
              break;
            case 5:
              v2 = sub_1000C9B7(v35, psz, (int)&v27);
              if ( v2 < 0 )
              {
                v14 = "failed to create child element: %ls";
                goto LABEL_128;
              }
              if ( v32 )
              {
                if ( *v32 )
                {
                  v2 = sub_1000D326(v27, v32);
                  if ( v2 < 0 )
                  {
                    sub_1000DA66(v2, "failed to set text to: %ls for node: %ls");
                    goto LABEL_138;
                  }
                }
              }
              if ( v27 )
              {
                (*(void (__stdcall **)(int))(*(_DWORD *)v27 + 8))(v27);
                v27 = 0;
              }
              break;
            case 4:
              if ( psz && *psz )
              {
                v2 = sub_1000CF55(v35, psz);
                if ( v2 < 0 )
                {
                  v14 = "failed to remove attribute: %ls";
                  goto LABEL_128;
                }
              }
              else
              {
                v2 = sub_1000D326(v35, (OLECHAR *)&dword_100226F0);
                if ( v2 < 0 )
                {
                  sub_1000DA66(v2, "failed to clear text value");
                  goto LABEL_138;
                }
              }
              break;
            case 6:
              v2 = sub_1000CFC6(v35, psz);
              if ( v2 < 0 )
              {
                v14 = "failed to delete child node: %ls";
                goto LABEL_128;
              }
              break;
            default:
              v2 = -2147418113;
              sub_1000DA66(-2147418113, "Invalid modification specified in custom action data");
              goto LABEL_138;
          }
        }
      }
      else if ( v31 == 5 || v31 == 3 || v31 == 7 )
      {
        sub_1000DA66(hInstalla, "failed to load XML file: %ls");
        v2 = hInstalla;
        sub_1000E13E(25531, hInstalla, INSTALLMESSAGE_ERROR, 1);
        goto LABEL_138;
      }
    }
    if ( hInstalla )
      goto LABEL_113;
    if ( v24 )
    {
      v2 = sub_1000B556(lpFileName, 0, 0, &LastWriteTime);
      if ( v2 < 0 )
      {
        v14 = "failed to get modified time of file : %ls";
        goto LABEL_128;
      }
    }
    v7 = 0;
    do
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v8 = sub_1000D085(v29, (OLECHAR *)lpFileName);
          v2 = v8;
          if ( v8 < 0 )
            break;
LABEL_118:
          if ( v2 != 1 )
            goto LABEL_108;
        }
        v9 = sub_1000E13E(25543, v8, (INSTALLMESSAGE)16777218, 1);
        if ( v9 )
          break;
        if ( v2 != -2147024864 )
          goto LABEL_118;
        if ( v7 >= 30 )
        {
          sub_1000DA66(-2147024864, "Failed to save changes to XML file: %ls");
          goto LABEL_138;
        }
        ++v7;
        sub_1000D9AB(1, "Unable to save changes to XML file: %ls, retry attempt: %x");
        Sleep(0x3E8u);
      }
      v10 = v9 - 3;
      if ( !v10 )
        goto LABEL_133;
      v11 = v10 - 1;
    }
    while ( !v11 );
    if ( v11 != 1 )
    {
LABEL_133:
      v14 = "Failed to save changes to XML file: %ls";
      goto LABEL_128;
    }
    v2 = 0;
LABEL_108:
    if ( !v24 || (v2 = sub_1000B8D3(lpFileName, 0, 0, &LastWriteTime), v2 >= 0) )
    {
      if ( v26 )
      {
        v26 = 0;
        sub_10010671();
      }
      i = *(_WORD **)SubStr;
LABEL_113:
      if ( !i )
        goto LABEL_138;
      v3 = v19;
      continue;
    }
    break;
  }
  v14 = "failed to set modified time of file : %ls";
LABEL_128:
  sub_1000DA66(v2, v14);
LABEL_138:
  if ( v26 )
    sub_10010671();
LABEL_140:
  sub_10010563();
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( lpFileName )
    sub_1000A952(lpFileName);
  if ( v30 )
    sub_1000A952(v30);
  if ( psz )
    sub_1000A952(psz);
  if ( v32 )
    sub_1000A952(v32);
  if ( bstrString )
    SysFreeString(bstrString);
  VariantClear(&pvarg);
  if ( v23 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v23 + 8))(v23);
  if ( v35 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v35 + 8))(v35);
  if ( v29 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v29 + 8))(v29);
  if ( v27 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v27 + 8))(v27);
  if ( v25 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v25 + 8))(v25);
  sub_1000D47E();
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x100075d0  push    ebp
0x100075d1  mov     ebp, esp
0x100075d3  sub     esp, 60h
0x100075d6  push    ebx
0x100075d7  xor     ebx, ebx
0x100075d9  push    esi
0x100075da  mov     esi, ds:SysAllocString
0x100075e0  push    edi
0x100075e1  push    offset psz; "SelectionLanguage"
0x100075e6  mov     [ebp+var_2C], ebx
0x100075e9  mov     [ebp+pcchValueBuf], ebx
0x100075ec  mov     [ebp+lpFileName], ebx
0x100075ef  mov     [ebp+var_1C], ebx
0x100075f2  mov     [ebp+psz], ebx
0x100075f5  mov     [ebp+var_14], ebx
0x100075f8  mov     dword ptr [ebp+SubStr], ebx
0x100075fb  mov     [ebp+var_20], ebx
0x100075fe  mov     [ebp+var_8], ebx
0x10007601  mov     [ebp+var_28], ebx
0x10007604  mov     [ebp+var_30], ebx
0x10007607  mov     [ebp+var_38], ebx
0x1000760a  call    esi ; SysAllocString
0x1000760c  mov     [ebp+bstrString], eax
0x1000760f  test    eax, eax
0x10007611  jnz     short loc_1000763C
0x10007613  mov     edi, 8007000Eh
0x10007618  push    edi
0x10007619  push    1FAh
0x1000761e  push    offset aDAWork1SSrcExt_5; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10007623  mov     esi, edi
0x10007625  call    nullsub_1
0x1000762a  push    offset aFailedSysalloc; "failed SysAllocString"
0x1000762f  push    edi
0x10007630  call    sub_1000DA66
0x10007635  pop     ecx
0x10007636  pop     ecx
0x10007637  jmp     loc_10007CD2
0x1000763c  lea     eax, [ebp+pvarg]
0x1000763f  push    eax; pvarg
0x10007640  call    ds:VariantInit
0x10007646  push    8
0x10007648  pop     eax
0x10007649  push    offset aXpath; "XPath"
0x1000764e  mov     word ptr [ebp+pvarg], ax
0x10007652  call    esi ; SysAllocString
0x10007654  mov     dword ptr [ebp+pvarg+8], eax
0x10007657  test    eax, eax
0x10007659  jnz     short loc_10007668
0x1000765b  mov     edi, 8007000Eh
0x10007660  push    edi
0x10007661  push    1FFh
0x10007666  jmp     short loc_1000761E
0x10007668  push    offset aExecxmlfile_0; "ExecXmlFile"
0x1000766d  push    [ebp+hInstall]; hInstall
0x10007670  call    sub_1000D51F
0x10007675  mov     esi, eax
0x10007677  test    esi, esi
0x10007679  jns     short loc_10007683
0x1000767b  push    offset aFailedToInitia_2; "failed to initialize"
0x10007680  push    esi
0x10007681  jmp     short loc_10007630
0x10007683  call    sub_1000CCA3
0x10007688  mov     esi, eax
0x1000768a  test    esi, esi
0x1000768c  jns     short loc_10007695
0x1000768e  push    offset aFailedToInitia_10; "failed to initialize xml utilities"
0x10007693  jmp     short loc_10007680
0x10007695  lea     eax, [ebp+pcchValueBuf]
0x10007698  push    eax; pcchValueBuf
0x10007699  push    offset aCustomactionda; "CustomActionData"
0x1000769e  call    sub_1000E662
0x100076a3  mov     esi, eax
0x100076a5  test    esi, esi
0x100076a7  jns     short loc_100076B0
0x100076a9  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x100076ae  jmp     short loc_10007680
0x100076b0  push    [ebp+pcchValueBuf]
0x100076b3  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x100076b8  push    ebx
0x100076b9  call    sub_1000D9AB
0x100076be  mov     eax, [ebp+pcchValueBuf]
0x100076c1  add     esp, 0Ch
0x100076c4  mov     dword ptr [ebp+SubStr], eax
0x100076c7  lea     eax, [ebp+var_18]
0x100076ca  push    eax; int
0x100076cb  lea     eax, [ebp+SubStr]
0x100076ce  push    eax; SubStr
0x100076cf  call    sub_1000EF44
0x100076d4  mov     esi, eax
0x100076d6  test    esi, esi
0x100076d8  jns     short loc_100076E1
0x100076da  push    offset aFailedToProces; "failed to process CustomActionData"
0x100076df  jmp     short loc_10007680
0x100076e1  call    sub_10010583
0x100076e6  call    sub_10010646
0x100076eb  cmp     [ebp+var_18], 1
0x100076ef  mov     edi, eax
0x100076f1  mov     [ebp+var_48], edi
0x100076f4  jz      short loc_1000770B
0x100076f6  cmp     [ebp+var_18], 2
0x100076fa  jz      short loc_1000770B
0x100076fc  mov     esi, 80070057h
0x10007701  push    offset aInvalidCustomA; "invalid custom action data"
0x10007706  jmp     loc_10007680
0x1000770b  mov     eax, dword ptr [ebp+SubStr]
0x1000770e  test    eax, eax
0x10007710  jz      loc_10007CD2
0x10007716  cmp     [eax], bx
0x10007719  jz      loc_10007CC8
0x1000771f  lea     eax, [ebp+var_40]
0x10007722  push    eax; int
0x10007723  lea     eax, [ebp+SubStr]
0x10007726  push    eax; SubStr
0x10007727  call    sub_1000EF44
0x1000772c  mov     esi, eax
0x1000772e  test    esi, esi
0x10007730  js      loc_10007CBB
0x10007736  lea     eax, [ebp+lpFileName]
0x10007739  push    eax; int
0x1000773a  lea     eax, [ebp+SubStr]
0x1000773d  push    eax; SubStr
0x1000773e  call    sub_1000EFCC
0x10007743  mov     esi, eax
0x10007745  test    esi, esi
0x10007747  js      loc_10007CB4
0x1000774d  mov     ecx, [ebp+var_20]
0x10007750  mov     [ebp+var_34], ebx
0x10007753  test    ecx, ecx
0x10007755  jz      short loc_10007760
0x10007757  mov     eax, [ecx]
0x10007759  push    ecx
0x1000775a  call    dword ptr [eax+8]
0x1000775d  mov     [ebp+var_20], ebx
0x10007760  cmp     [ebp+var_18], 2
0x10007764  jnz     short loc_10007784
0x10007766  test    edi, edi
0x10007768  jz      loc_10007C15
0x1000776e  call    sub_10010509
0x10007773  mov     esi, eax
0x10007775  test    esi, esi
0x10007777  js      loc_10007C0B
0x1000777d  mov     [ebp+var_2C], 1
0x10007784  lea     eax, [ebp+var_20]
0x10007787  push    eax; int
0x10007788  push    1; char
0x1000778a  push    [ebp+lpFileName]; psz
0x1000778d  call    sub_1000CE26
0x10007792  mov     esi, eax
0x10007794  test    esi, esi
0x10007796  jns     short loc_100077A1
0x10007798  mov     edi, esi
0x1000779a  mov     esi, ebx
0x1000779c  mov     [ebp+hInstall], edi
0x1000779f  jmp     short loc_100077A6
0x100077a1  mov     edi, ebx
0x100077a3  mov     [ebp+hInstall], ebx
0x100077a6  push    [ebp+lpFileName]
0x100077a9  push    offset aConfiguringXml; "Configuring Xml File: %ls"
0x100077ae  push    1
0x100077b0  call    sub_1000D9AB
0x100077b5  add     esp, 0Ch
0x100077b8  cmp     [ebp+var_40], 1
0x100077bc  jnz     short loc_1000780E
0x100077be  cmp     dword_1003390C, ebx
0x100077c4  jz      loc_10007C3B
0x100077ca  test    edi, edi
0x100077cc  js      short loc_1000780E
0x100077ce  mov     eax, [ebp+var_20]
0x100077d1  lea     edx, [ebp+var_38]
0x100077d4  push    edx
0x100077d5  push    offset dword_100223C0
0x100077da  push    eax
0x100077db  mov     ecx, [eax]
0x100077dd  call    dword ptr [ecx]
0x100077df  mov     esi, eax
0x100077e1  test    esi, esi
0x100077e3  js      loc_10007C31
0x100077e9  mov     eax, [ebp+var_38]
0x100077ec  lea     esi, [ebp+pvarg]
0x100077ef  sub     esp, 10h
0x100077f2  mov     edi, esp
0x100077f4  mov     ecx, [eax]
0x100077f6  push    [ebp+bstrString]
0x100077f9  movsd
0x100077fa  push    eax
0x100077fb  movsd
0x100077fc  movsd
0x100077fd  movsd
0x100077fe  call    dword ptr [ecx+140h]
0x10007804  mov     esi, eax
0x10007806  test    esi, esi
0x10007808  js      loc_10007C27
0x1000780e  mov     eax, dword ptr [ebp+SubStr]
0x10007811  test    eax, eax
0x10007813  jz      loc_10007B1B
0x10007819  mov     edi, [ebp+hInstall]
0x1000781c  cmp     [eax], bx
0x1000781f  jz      loc_10007B1B
0x10007825  lea     eax, [ebp+var_18]
0x10007828  push    eax; int
0x10007829  lea     eax, [ebp+SubStr]
0x1000782c  push    eax; SubStr
0x1000782d  call    sub_1000EF44
0x10007832  mov     esi, eax
0x10007834  test    esi, esi
0x10007836  js      loc_10007CBB
0x1000783c  cmp     [ebp+var_18], 1
0x10007840  jz      loc_10007B18
0x10007846  cmp     [ebp+var_18], 2
0x1000784a  jz      loc_10007B18
0x10007850  lea     eax, [ebp+var_44]
0x10007853  push    eax; int
0x10007854  lea     eax, [ebp+SubStr]
0x10007857  push    eax; SubStr
0x10007858  call    sub_1000EF44
0x1000785d  mov     esi, eax
0x1000785f  test    esi, esi
0x10007861  js      loc_10007CBB
0x10007867  xor     eax, eax
0x10007869  inc     eax
0x1000786a  cmp     [ebp+var_44], eax
0x1000786d  jnz     short loc_10007872
0x1000786f  mov     [ebp+var_34], eax
0x10007872  lea     eax, [ebp+var_1C]
0x10007875  push    eax; int
0x10007876  lea     eax, [ebp+SubStr]
0x10007879  push    eax; SubStr
0x1000787a  call    sub_1000EFCC
0x1000787f  mov     esi, eax
0x10007881  test    esi, esi
0x10007883  js      loc_10007CBB
0x10007889  lea     eax, [ebp+psz]
0x1000788c  push    eax; int
0x1000788d  lea     eax, [ebp+SubStr]
0x10007890  push    eax; SubStr
0x10007891  call    sub_1000EFCC
0x10007896  mov     esi, eax
0x10007898  test    esi, esi
0x1000789a  js      loc_10007CBB
0x100078a0  lea     eax, [ebp+var_14]
0x100078a3  push    eax; int
0x100078a4  lea     eax, [ebp+SubStr]
0x100078a7  push    eax; SubStr
0x100078a8  call    sub_1000EFCC
0x100078ad  mov     esi, eax
0x100078af  test    esi, esi
0x100078b1  js      loc_10007CBB
0x100078b7  test    edi, edi
0x100078b9  jns     short loc_100078FE
0x100078bb  cmp     [ebp+var_18], 5
0x100078bf  jz      short loc_100078D1
0x100078c1  cmp     [ebp+var_18], 3
0x100078c5  jz      short loc_100078D1
0x100078c7  cmp     [ebp+var_18], 7
0x100078cb  jnz     loc_10007B0B
0x100078d1  push    [ebp+lpFileName]
0x100078d4  push    offset aFailedToLoadXm; "failed to load XML file: %ls"
0x100078d9  push    edi
0x100078da  call    sub_1000DA66
0x100078df  push    [ebp+lpFileName]
0x100078e2  mov     esi, edi
0x100078e4  push    1; int
0x100078e6  push    1000000h; eMessageType
0x100078eb  push    edi; int
0x100078ec  push    63BBh; iValue
0x100078f1  call    sub_1000E13E
0x100078f6  add     esp, 20h
0x100078f9  jmp     loc_10007CC8
0x100078fe  mov     ecx, [ebp+var_8]
0x10007901  test    ecx, ecx
0x10007903  jz      short loc_1000790E
0x10007905  mov     eax, [ecx]
0x10007907  push    ecx
0x10007908  call    dword ptr [eax+8]
0x1000790b  mov     [ebp+var_8], ebx
0x1000790e  cmp     [ebp+var_18], 7
0x10007912  jnz     loc_100079DD
0x10007918  lea     eax, [ebp+var_30]
0x1000791b  push    eax; int
0x1000791c  push    [ebp+var_1C]; psz
0x1000791f  push    [ebp+var_20]; int
0x10007922  call    sub_1000D0EB
0x10007927  mov     esi, eax
0x10007929  cmp     esi, 1
0x1000792c  jnz     short loc_10007933
0x1000792e  mov     esi, 800710D8h
0x10007933  test    esi, esi
0x10007935  jns     loc_100079C4
0x1000793b  push    [ebp+lpFileName]
0x1000793e  push    [ebp+var_1C]
0x10007941  push    offset aFailedToFindAn; "failed to find any nodes: %ls in XML fi"...
0x10007946  push    esi
0x10007947  call    sub_1000DA66
0x1000794c  push    [ebp+lpFileName]
0x1000794f  push    [ebp+var_1C]
0x10007952  push    2; int
0x10007954  push    1000000h; eMessageType
0x10007959  push    esi; int
0x1000795a  push    63BCh; iValue
0x1000795f  call    sub_1000E13E
  ... truncated ...
```
