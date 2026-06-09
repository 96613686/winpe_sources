# ExecXmlConfig

- ea: `0x10008ba5`
- end: `0x1000942a`
- name: `ExecXmlConfig`
- size: `2181`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x10008ba5`
- `0x1000a952`
- `0x1000b556`
- `0x1000b8d3`
- `0x1000c9b7`
- `0x1000cca3`
- `0x1000cd01`
- `0x1000ce26`
- `0x1000cf55`
- `0x1000d085`
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

- `KERNEL32!Sleep` at `0x10009256`
- `KERNEL32!Sleep` at `0x10009256`

## string_xrefs

- `0x10008c0f`: `failed to initialize xml utilities`
- `0x10009357`: `failed to read file name from custom action data`
- `0x1000927b`: `Custom action was told to act on a 64-bit component, but the custom action process is not running in WOW.`
- `0x1000926c`: `Custom action was told to act on a 64-bit component, but was unable to disable filesystem redirection through the Wow64 API.`
- `0x10008d16`: `Configuring Xml File: %ls`
- `0x10008e49`: `failed to load XML file: %ls`
- `0x100092f3`: `failed to set text to: %ls for element %ls.  Make sure that XPath points to an element.`
- `0x10009303`: `failed to find node: %ls in XML file: %ls`
- `0x100092bb`: `failed to create child element: %ls`
- `0x10009060`: `failed to remove attribute: %ls`
- `0x10009338`: `Failed to save changes to XML file: %ls`
- `0x10009342`: `Failed to save changes to XML file: %ls`
- `0x10009242`: `Unable to save changes to XML file: %ls, retry attempt: %x`
- `0x10008baf`: `ExecXmlConfig`
- `0x100092c5`: `failed to query verify path: %ls`
- `0x1000928f`: `failed to remove created child element`
- `0x10008f41`: `Failed to select path %ls for deleting.  Skipping...`
- `0x10008f58`: `No VerifyPath specified for delete element of ID: %ls`

## pseudocode

```c
int __stdcall ExecXmlConfig(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  int v3; // ebx
  _WORD *v4; // eax
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  const char *v15; // [esp-Ch] [ebp-68h]
  struct _FILETIME LastWriteTime; // [esp+8h] [ebp-54h] BYREF
  int v17; // [esp+10h] [ebp-4Ch]
  int v18; // [esp+14h] [ebp-48h] BYREF
  int v19; // [esp+18h] [ebp-44h]
  int v20; // [esp+1Ch] [ebp-40h] BYREF
  int v21; // [esp+20h] [ebp-3Ch]
  int v22; // [esp+24h] [ebp-38h] BYREF
  int v23; // [esp+28h] [ebp-34h] BYREF
  int v24; // [esp+2Ch] [ebp-30h] BYREF
  DWORD pcchValueBuf; // [esp+30h] [ebp-2Ch] BYREF
  int v26; // [esp+34h] [ebp-28h] BYREF
  int v27; // [esp+38h] [ebp-24h] BYREF
  int v28; // [esp+3Ch] [ebp-20h] BYREF
  OLECHAR *v29; // [esp+40h] [ebp-1Ch] BYREF
  OLECHAR *v30; // [esp+44h] [ebp-18h] BYREF
  int v31; // [esp+48h] [ebp-14h] BYREF
  OLECHAR *v32; // [esp+4Ch] [ebp-10h] BYREF
  OLECHAR *psz; // [esp+50h] [ebp-Ch] BYREF
  LPCWSTR lpFileName; // [esp+54h] [ebp-8h] BYREF
  wchar_t SubStr[2]; // [esp+58h] [ebp-4h] BYREF

  v1 = 0;
  v21 = 0;
  pcchValueBuf = 0;
  lpFileName = 0;
  v29 = 0;
  v30 = 0;
  psz = 0;
  v32 = 0;
  *(_DWORD *)SubStr = 0;
  v28 = 0;
  v27 = 0;
  v31 = 0;
  v22 = 0;
  v26 = 0;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v2 = sub_1000D51F(hInstall, (int)"ExecXmlConfig");
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize");
    goto LABEL_152;
  }
  v2 = sub_1000CCA3();
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to initialize xml utilities");
    goto LABEL_152;
  }
  v2 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to get CustomActionData");
    goto LABEL_152;
  }
  sub_1000D9AB(0, "CustomActionData: %ls");
  *(_DWORD *)SubStr = pcchValueBuf;
  v2 = sub_1000EF44((wchar_t)SubStr, (int)&hInstall);
  if ( v2 < 0 )
  {
    sub_1000DA66(v2, "failed to process CustomActionData");
    goto LABEL_152;
  }
  sub_10010583();
  v3 = sub_10010646();
  v17 = v3;
  if ( hInstall != 1 && hInstall != 2 )
  {
    v2 = -2147024809;
    sub_1000DA66(-2147024809, "invalid custom action data");
    goto LABEL_152;
  }
  v4 = *(_WORD **)SubStr;
  if ( *(_DWORD *)SubStr )
  {
LABEL_13:
    if ( !*v4 )
      goto LABEL_150;
    v2 = sub_1000EFCC((wchar_t)SubStr, (int)&lpFileName);
    if ( v2 < 0 )
    {
      sub_1000DA66(v2, "failed to read file name from custom action data");
      goto LABEL_150;
    }
    v19 = 0;
    if ( v27 )
    {
      (*(void (__stdcall **)(int))(*(_DWORD *)v27 + 8))(v27);
      v27 = 0;
    }
    if ( hInstall == 2 )
    {
      if ( !v3 )
      {
        v2 = -2147467263;
        sub_1000DA66(
          -2147467263,
          "Custom action was told to act on a 64-bit component, but the custom action process is not running in WOW.");
        goto LABEL_150;
      }
      v2 = sub_10010509();
      if ( v2 < 0 )
      {
        sub_1000DA66(
          v2,
          "Custom action was told to act on a 64-bit component, but was unable to disable filesystem redirection through the Wow64 API.");
        goto LABEL_150;
      }
      v21 = 1;
    }
    v5 = sub_1000CE26((OLECHAR *)lpFileName, 1, (int)&v27);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
    }
    else
    {
      v6 = v5;
      v2 = 0;
    }
    sub_1000D9AB(1, "Configuring Xml File: %ls");
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_106:
        v4 = *(_WORD **)SubStr;
        if ( !*(_DWORD *)SubStr || !**(_WORD **)SubStr )
          goto LABEL_109;
        if ( v28 > 0 )
        {
          while ( 1 )
          {
            v2 = sub_1000EFCC((wchar_t)SubStr, (int)&psz);
            if ( v2 < 0 )
              break;
            v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v32);
            if ( v2 < 0 )
              break;
            if ( --v28 <= 0 )
              goto LABEL_106;
          }
LABEL_133:
          sub_1000DA66(v2, "failed to process CustomActionData");
          goto LABEL_150;
        }
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&hInstall);
        if ( v2 < 0 )
          goto LABEL_133;
        if ( hInstall == 1 || hInstall == 2 )
        {
          v4 = *(_WORD **)SubStr;
LABEL_109:
          if ( v6 )
            goto LABEL_124;
          if ( v19 )
          {
            v2 = sub_1000B556(lpFileName, 0, 0, &LastWriteTime);
            if ( v2 < 0 )
            {
              v15 = "failed to get modified time of file : %ls";
              goto LABEL_139;
            }
          }
          v9 = 0;
          while ( 1 )
          {
LABEL_113:
            v10 = sub_1000D085(v27, (OLECHAR *)lpFileName);
            v2 = v10;
            if ( v10 >= 0 )
              goto LABEL_129;
            v11 = sub_1000E13E(25543, v10, (INSTALLMESSAGE)16777218, 1);
            if ( !v11 )
              break;
            v12 = v11 - 3;
            if ( !v12 )
              goto LABEL_146;
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 != 1 )
              {
LABEL_146:
                v15 = "Failed to save changes to XML file: %ls";
                goto LABEL_139;
              }
              v2 = 0;
LABEL_119:
              if ( !v19 || (v2 = sub_1000B8D3(lpFileName, 0, 0, &LastWriteTime), v2 >= 0) )
              {
                if ( v21 )
                {
                  v21 = 0;
                  sub_10010671();
                }
                v4 = *(_WORD **)SubStr;
LABEL_124:
                if ( v4 )
                {
                  v3 = v17;
                  goto LABEL_13;
                }
LABEL_150:
                if ( v21 )
                  sub_10010671();
                goto LABEL_152;
              }
              v15 = "failed to set modified time of file : %ls";
LABEL_139:
              sub_1000DA66(v2, v15);
              goto LABEL_150;
            }
          }
          if ( v2 == -2147024864 )
          {
            if ( v9 >= 30 )
            {
              sub_1000DA66(-2147024864, "Failed to save changes to XML file: %ls");
              goto LABEL_150;
            }
            ++v9;
            sub_1000D9AB(1, "Unable to save changes to XML file: %ls, retry attempt: %x");
            Sleep(0x3E8u);
            goto LABEL_113;
          }
LABEL_129:
          if ( v2 != 1 )
            goto LABEL_119;
          goto LABEL_113;
        }
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&v18);
        if ( v2 < 0 )
          goto LABEL_133;
        if ( v18 == 1 )
          v19 = 1;
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v29);
        if ( v2 < 0 )
          goto LABEL_133;
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v30);
        if ( v2 < 0 )
          goto LABEL_133;
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&psz);
        if ( v2 < 0 )
          goto LABEL_133;
        v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v32);
        if ( v2 < 0 )
          goto LABEL_133;
        v2 = sub_1000EF44((wchar_t)SubStr, (int)&v28);
        if ( v2 < 0 )
          goto LABEL_133;
        if ( v6 >= 0 )
          break;
        if ( hInstall == 6 || hInstall == 3 || hInstall == 4 )
        {
          sub_1000DA66(v6, "failed to load XML file: %ls");
          v2 = v6;
          sub_1000E13E(25541, v6, INSTALLMESSAGE_ERROR, 1);
          goto LABEL_150;
        }
      }
      if ( v31 )
      {
        (*(void (__stdcall **)(int))(*(_DWORD *)v31 + 8))(v31);
        v31 = 0;
      }
      v2 = sub_1000D171(v27, v29, (int)&v31);
      if ( v2 != 1 )
        goto LABEL_55;
      if ( hInstall == 6 || hInstall == 3 || hInstall == 4 )
      {
        v2 = -2147020584;
LABEL_55:
        if ( v2 < 0 )
        {
          sub_1000DA66(v2, "failed to find node: %ls in XML file: %ls");
          sub_1000E13E(25542, v2, INSTALLMESSAGE_ERROR, 2);
          goto LABEL_150;
        }
        switch ( hInstall )
        {
          case 3u:
            if ( psz && *psz )
            {
              v2 = sub_1000D1F7(v31, psz, v32);
              if ( v2 < 0 )
              {
LABEL_104:
                sub_1000DA66(v2, "failed to set attribute: %ls to value %ls");
                goto LABEL_150;
              }
            }
            else
            {
              v2 = sub_1000D326(v31, v32);
              if ( v2 < 0 )
              {
                sub_1000DA66(
                  v2,
                  "failed to set text to: %ls for element %ls.  Make sure that XPath points to an element.");
                goto LABEL_150;
              }
            }
            break;
          case 4u:
            if ( !v30 || !*v30 )
              goto LABEL_94;
            v8 = sub_1000D171(v31, v30, (int)&v22);
            v2 = v8;
            if ( v8 )
            {
              if ( v8 < 0 )
              {
LABEL_138:
                v15 = "failed to query verify path: %ls";
                goto LABEL_139;
              }
LABEL_94:
              v2 = sub_1000CD01(v32, 1, (int)&v23);
              if ( v2 < 0 )
              {
                sub_1000DA66(v2, "Failed to load value as document.");
                goto LABEL_150;
              }
              v2 = (*(int (__stdcall **)(int, int *))(*(_DWORD *)v23 + 180))(v23, &v24);
              if ( v2 < 0 )
              {
                sub_1000DA66(v2, "Failed to get document element.");
                goto LABEL_150;
              }
              v2 = (*(int (__stdcall **)(int, int, _DWORD))(*(_DWORD *)v31 + 84))(v31, v24, 0);
              if ( v2 < 0 )
              {
                sub_1000DA66(v2, "Failed to append document element on to parent element.");
                goto LABEL_150;
              }
              if ( v24 )
              {
                (*(void (__stdcall **)(int))(*(_DWORD *)v24 + 8))(v24);
                v24 = 0;
              }
              if ( v23 )
              {
                (*(void (__stdcall **)(int))(*(_DWORD *)v23 + 8))(v23);
                v23 = 0;
              }
            }
            break;
          case 5u:
            if ( psz && *psz )
            {
              v2 = sub_1000CF55(v31, psz);
              if ( v2 < 0 )
              {
                v15 = "failed to remove attribute: %ls";
                goto LABEL_139;
              }
            }
            else
            {
              v2 = sub_1000D326(v31, (OLECHAR *)&dword_100226F0);
              if ( v2 < 0 )
              {
                sub_1000DA66(v2, "failed to clear text value");
                goto LABEL_150;
              }
            }
            break;
          case 6u:
            if ( !v30 || !*v30 )
              goto LABEL_73;
            v7 = sub_1000D171(v31, v30, (int)&v22);
            v2 = v7;
            if ( v7 )
            {
              if ( v7 < 0 )
                goto LABEL_138;
LABEL_73:
              v2 = sub_1000C9B7(v31, psz, (int)&v26);
              if ( v2 < 0 )
              {
                v15 = "failed to create child element: %ls";
                goto LABEL_139;
              }
              if ( v32 )
              {
                if ( *v32 )
                {
                  v2 = sub_1000D326(v26, v32);
                  if ( v2 < 0 )
                  {
                    sub_1000DA66(v2, "failed to set text to: %ls for node: %ls");
                    goto LABEL_150;
                  }
                }
              }
              if ( v28 > 0 )
              {
                do
                {
                  v2 = sub_1000EFCC((wchar_t)SubStr, (int)&psz);
                  if ( v2 < 0 )
                    goto LABEL_133;
                  v2 = sub_1000EFCC((wchar_t)SubStr, (int)&v32);
                  if ( v2 < 0 )
                    goto LABEL_133;
                  v2 = sub_1000D1F7(v26, psz, v32);
                  if ( v2 < 0 )
                    goto LABEL_104;
                }
                while ( --v28 > 0 );
              }
              if ( v26 )
              {
                (*(void (__stdcall **)(int))(*(_DWORD *)v26 + 8))(v26);
                v26 = 0;
              }
            }
            break;
          case 7u:
            if ( v30 && *v30 )
            {
              if ( sub_1000D171(v31, v30, (int)&v22) )
              {
                sub_1000D9AB(1, "Failed to select path %ls for deleting.  Skipping...");
                goto LABEL_53;
              }
              v2 = (*(int (__stdcall **)(int, int, int *))(*(_DWORD *)v31 + 80))(v31, v22, &v20);
              if ( v2 < 0 )
              {
                sub_1000DA66(v2, "failed to remove created child element");
                goto LABEL_150;
              }
              if ( v20 )
              {
                (*(void (__stdcall **)(int))(*(_DWORD *)v20 + 8))(v20);
                v20 = 0;
              }
            }
            else
            {
              sub_1000D9AB(1, "No VerifyPath specified for delete element of ID: %ls");
            }
            break;
          default:
            v2 = -2147418113;
            sub_1000DA66(-2147418113, "Invalid modification specified in custom action data");
            goto LABEL_150;
        }
      }
      else
      {
LABEL_53:
        v2 = 0;
      }
    }
  }
LABEL_152:
  sub_10010563();
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( lpFileName )
    sub_1000A952(lpFileName);
  if ( v29 )
    sub_1000A952(v29);
  if ( v30 )
    sub_1000A952(v30);
  if ( psz )
    sub_1000A952(psz);
  if ( v32 )
    sub_1000A952(v32);
  if ( v24 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v24 + 8))(v24);
  if ( v23 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v23 + 8))(v23);
  if ( v31 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v31 + 8))(v31);
  if ( v27 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v27 + 8))(v27);
  if ( v26 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v26 + 8))(v26);
  if ( v20 )
    (*(void (__stdcall **)(int))(*(_DWORD *)v20 + 8))(v20);
  sub_1000D47E();
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10008ba5  push    ebp
0x10008ba6  mov     ebp, esp
0x10008ba8  sub     esp, 54h
0x10008bab  push    esi
0x10008bac  push    edi
0x10008bad  xor     edi, edi
0x10008baf  push    offset aExecxmlconfig_0; "ExecXmlConfig"
0x10008bb4  push    [ebp+hInstall]; hInstall
0x10008bb7  mov     [ebp+var_3C], edi
0x10008bba  mov     [ebp+pcchValueBuf], edi
0x10008bbd  mov     [ebp+lpFileName], edi
0x10008bc0  mov     [ebp+var_1C], edi
0x10008bc3  mov     [ebp+var_18], edi
0x10008bc6  mov     [ebp+psz], edi
0x10008bc9  mov     [ebp+var_10], edi
0x10008bcc  mov     dword ptr [ebp+SubStr], edi
0x10008bcf  mov     [ebp+var_20], edi
0x10008bd2  mov     [ebp+var_24], edi
0x10008bd5  mov     [ebp+var_14], edi
0x10008bd8  mov     [ebp+var_38], edi
0x10008bdb  mov     [ebp+var_28], edi
0x10008bde  mov     [ebp+var_40], edi
0x10008be1  mov     [ebp+var_34], edi
0x10008be4  mov     [ebp+var_30], edi
0x10008be7  call    sub_1000D51F
0x10008bec  mov     esi, eax
0x10008bee  test    esi, esi
0x10008bf0  jns     short loc_10008C04
0x10008bf2  push    offset aFailedToInitia_2; "failed to initialize"
0x10008bf7  push    esi
0x10008bf8  call    sub_1000DA66
0x10008bfd  pop     ecx
0x10008bfe  pop     ecx
0x10008bff  jmp     loc_1000936F
0x10008c04  call    sub_1000CCA3
0x10008c09  mov     esi, eax
0x10008c0b  test    esi, esi
0x10008c0d  jns     short loc_10008C16
0x10008c0f  push    offset aFailedToInitia_10; "failed to initialize xml utilities"
0x10008c14  jmp     short loc_10008BF7
0x10008c16  lea     eax, [ebp+pcchValueBuf]
0x10008c19  push    eax; pcchValueBuf
0x10008c1a  push    offset aCustomactionda; "CustomActionData"
0x10008c1f  call    sub_1000E662
0x10008c24  mov     esi, eax
0x10008c26  test    esi, esi
0x10008c28  jns     short loc_10008C31
0x10008c2a  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10008c2f  jmp     short loc_10008BF7
0x10008c31  push    [ebp+pcchValueBuf]
0x10008c34  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10008c39  push    edi
0x10008c3a  call    sub_1000D9AB
0x10008c3f  mov     eax, [ebp+pcchValueBuf]
0x10008c42  add     esp, 0Ch
0x10008c45  mov     dword ptr [ebp+SubStr], eax
0x10008c48  lea     eax, [ebp+hInstall]
0x10008c4b  push    eax; int
0x10008c4c  lea     eax, [ebp+SubStr]
0x10008c4f  push    eax; SubStr
0x10008c50  call    sub_1000EF44
0x10008c55  mov     esi, eax
0x10008c57  test    esi, esi
0x10008c59  jns     short loc_10008C62
0x10008c5b  push    offset aFailedToProces; "failed to process CustomActionData"
0x10008c60  jmp     short loc_10008BF7
0x10008c62  push    ebx
0x10008c63  call    sub_10010583
0x10008c68  call    sub_10010646
0x10008c6d  cmp     [ebp+hInstall], 1
0x10008c71  mov     ebx, eax
0x10008c73  mov     [ebp+var_4C], ebx
0x10008c76  jz      short loc_10008C95
0x10008c78  cmp     [ebp+hInstall], 2
0x10008c7c  jz      short loc_10008C95
0x10008c7e  mov     esi, 80070057h
0x10008c83  push    offset aInvalidCustomA; "invalid custom action data"
0x10008c88  push    esi
0x10008c89  call    sub_1000DA66
0x10008c8e  pop     ecx
0x10008c8f  pop     ecx
0x10008c90  jmp     loc_1000936E
0x10008c95  mov     eax, dword ptr [ebp+SubStr]
0x10008c98  test    eax, eax
0x10008c9a  jz      loc_1000936E
0x10008ca0  cmp     [eax], di
0x10008ca3  jz      loc_10009364
0x10008ca9  lea     eax, [ebp+lpFileName]
0x10008cac  push    eax; int
0x10008cad  lea     eax, [ebp+SubStr]
0x10008cb0  push    eax; SubStr
0x10008cb1  call    sub_1000EFCC
0x10008cb6  mov     esi, eax
0x10008cb8  test    esi, esi
0x10008cba  js      loc_10009357
0x10008cc0  mov     ecx, [ebp+var_24]
0x10008cc3  mov     [ebp+var_44], edi
0x10008cc6  test    ecx, ecx
0x10008cc8  jz      short loc_10008CD3
0x10008cca  mov     eax, [ecx]
0x10008ccc  push    ecx
0x10008ccd  call    dword ptr [eax+8]
0x10008cd0  mov     [ebp+var_24], edi
0x10008cd3  cmp     [ebp+hInstall], 2
0x10008cd7  jnz     short loc_10008CF7
0x10008cd9  test    ebx, ebx
0x10008cdb  jz      loc_10009276
0x10008ce1  call    sub_10010509
0x10008ce6  mov     esi, eax
0x10008ce8  test    esi, esi
0x10008cea  js      loc_1000926C
0x10008cf0  mov     [ebp+var_3C], 1
0x10008cf7  lea     eax, [ebp+var_24]
0x10008cfa  push    eax; int
0x10008cfb  push    1; char
0x10008cfd  push    [ebp+lpFileName]; psz
0x10008d00  call    sub_1000CE26
0x10008d05  mov     esi, eax
0x10008d07  test    esi, esi
0x10008d09  jns     short loc_10008D11
0x10008d0b  mov     ebx, esi
0x10008d0d  mov     esi, edi
0x10008d0f  jmp     short loc_10008D13
0x10008d11  mov     ebx, edi
0x10008d13  push    [ebp+lpFileName]
0x10008d16  push    offset aConfiguringXml; "Configuring Xml File: %ls"
0x10008d1b  jmp     loc_10008F5D
0x10008d20  cmp     [eax], di
0x10008d23  jz      loc_1000917D
0x10008d29  cmp     [ebp+var_20], edi
0x10008d2c  jle     short loc_10008D6C
0x10008d2e  lea     eax, [ebp+psz]
0x10008d31  push    eax; int
0x10008d32  lea     eax, [ebp+SubStr]
0x10008d35  push    eax; SubStr
0x10008d36  call    sub_1000EFCC
0x10008d3b  mov     esi, eax
0x10008d3d  test    esi, esi
0x10008d3f  js      loc_10009285
0x10008d45  lea     eax, [ebp+var_10]
0x10008d48  push    eax; int
0x10008d49  lea     eax, [ebp+SubStr]
0x10008d4c  push    eax; SubStr
0x10008d4d  call    sub_1000EFCC
0x10008d52  mov     esi, eax
0x10008d54  test    esi, esi
0x10008d56  js      loc_10009285
0x10008d5c  mov     eax, [ebp+var_20]
0x10008d5f  dec     eax
0x10008d60  mov     [ebp+var_20], eax
0x10008d63  test    eax, eax
0x10008d65  jg      short loc_10008D2E
0x10008d67  jmp     loc_1000916D
0x10008d6c  lea     eax, [ebp+hInstall]
0x10008d6f  push    eax; int
0x10008d70  lea     eax, [ebp+SubStr]
0x10008d73  push    eax; SubStr
0x10008d74  call    sub_1000EF44
0x10008d79  mov     esi, eax
0x10008d7b  test    esi, esi
0x10008d7d  js      loc_10009285
0x10008d83  cmp     [ebp+hInstall], 1
0x10008d87  jz      loc_1000917A
0x10008d8d  cmp     [ebp+hInstall], 2
0x10008d91  jz      loc_1000917A
0x10008d97  lea     eax, [ebp+var_48]
0x10008d9a  push    eax; int
0x10008d9b  lea     eax, [ebp+SubStr]
0x10008d9e  push    eax; SubStr
0x10008d9f  call    sub_1000EF44
0x10008da4  mov     esi, eax
0x10008da6  test    esi, esi
0x10008da8  js      loc_10009285
0x10008dae  xor     eax, eax
0x10008db0  inc     eax
0x10008db1  cmp     [ebp+var_48], eax
0x10008db4  jnz     short loc_10008DB9
0x10008db6  mov     [ebp+var_44], eax
0x10008db9  lea     eax, [ebp+var_1C]
0x10008dbc  push    eax; int
0x10008dbd  lea     eax, [ebp+SubStr]
0x10008dc0  push    eax; SubStr
0x10008dc1  call    sub_1000EFCC
0x10008dc6  mov     esi, eax
0x10008dc8  test    esi, esi
0x10008dca  js      loc_10009285
0x10008dd0  lea     eax, [ebp+var_18]
0x10008dd3  push    eax; int
0x10008dd4  lea     eax, [ebp+SubStr]
0x10008dd7  push    eax; SubStr
0x10008dd8  call    sub_1000EFCC
0x10008ddd  mov     esi, eax
0x10008ddf  test    esi, esi
0x10008de1  js      loc_10009285
0x10008de7  lea     eax, [ebp+psz]
0x10008dea  push    eax; int
0x10008deb  lea     eax, [ebp+SubStr]
0x10008dee  push    eax; SubStr
0x10008def  call    sub_1000EFCC
0x10008df4  mov     esi, eax
0x10008df6  test    esi, esi
0x10008df8  js      loc_10009285
0x10008dfe  lea     eax, [ebp+var_10]
0x10008e01  push    eax; int
0x10008e02  lea     eax, [ebp+SubStr]
0x10008e05  push    eax; SubStr
0x10008e06  call    sub_1000EFCC
0x10008e0b  mov     esi, eax
0x10008e0d  test    esi, esi
0x10008e0f  js      loc_10009285
0x10008e15  lea     eax, [ebp+var_20]
0x10008e18  push    eax; int
0x10008e19  lea     eax, [ebp+SubStr]
0x10008e1c  push    eax; SubStr
0x10008e1d  call    sub_1000EF44
0x10008e22  mov     esi, eax
0x10008e24  test    esi, esi
0x10008e26  js      loc_10009285
0x10008e2c  test    ebx, ebx
0x10008e2e  jns     short loc_10008E73
0x10008e30  cmp     [ebp+hInstall], 6
0x10008e34  jz      short loc_10008E46
0x10008e36  cmp     [ebp+hInstall], 3
0x10008e3a  jz      short loc_10008E46
0x10008e3c  cmp     [ebp+hInstall], 4
0x10008e40  jnz     loc_1000916D
0x10008e46  push    [ebp+lpFileName]
0x10008e49  push    offset aFailedToLoadXm; "failed to load XML file: %ls"
0x10008e4e  push    ebx
0x10008e4f  call    sub_1000DA66
0x10008e54  push    [ebp+lpFileName]
0x10008e57  mov     esi, ebx
0x10008e59  push    1; int
0x10008e5b  push    1000000h; eMessageType
0x10008e60  push    ebx; int
0x10008e61  push    63C5h; iValue
0x10008e66  call    sub_1000E13E
0x10008e6b  add     esp, 20h
0x10008e6e  jmp     loc_10009364
0x10008e73  mov     ecx, [ebp+var_14]
0x10008e76  test    ecx, ecx
0x10008e78  jz      short loc_10008E83
0x10008e7a  mov     eax, [ecx]
0x10008e7c  push    ecx
0x10008e7d  call    dword ptr [eax+8]
0x10008e80  mov     [ebp+var_14], edi
0x10008e83  lea     eax, [ebp+var_14]
0x10008e86  push    eax; int
0x10008e87  push    [ebp+var_1C]; psz
0x10008e8a  push    [ebp+var_24]; int
0x10008e8d  call    sub_1000D171
0x10008e92  mov     esi, eax
0x10008e94  mov     eax, [ebp+hInstall]
0x10008e97  cmp     esi, 1
0x10008e9a  jnz     short loc_10008EB7
0x10008e9c  cmp     eax, 6
0x10008e9f  jz      short loc_10008EB2
0x10008ea1  cmp     eax, 3
0x10008ea4  jz      short loc_10008EB2
0x10008ea6  cmp     eax, 4
0x10008ea9  jz      short loc_10008EB2
0x10008eab  mov     esi, edi
0x10008ead  jmp     loc_1000916D
0x10008eb2  mov     esi, 800710D8h
0x10008eb7  test    esi, esi
0x10008eb9  js      loc_100092FD
0x10008ebf  sub     eax, 3
0x10008ec2  jz      loc_10009121
0x10008ec8  sub     eax, 1
0x10008ecb  jz      loc_1000908B
0x10008ed1  sub     eax, 1
0x10008ed4  jz      loc_1000903E
0x10008eda  sub     eax, 1
0x10008edd  jz      loc_10008F6C
0x10008ee3  sub     eax, 1
0x10008ee6  jnz     loc_10009299
0x10008eec  mov     eax, [ebp+var_18]
0x10008eef  test    eax, eax
0x10008ef1  jz      short loc_10008F55
0x10008ef3  xor     ecx, ecx
0x10008ef5  cmp     cx, [eax]
0x10008ef8  jz      short loc_10008F55
0x10008efa  lea     ecx, [ebp+var_38]
0x10008efd  push    ecx; int
0x10008efe  push    eax; psz
0x10008eff  push    [ebp+var_14]; int
0x10008f02  call    sub_1000D171
0x10008f07  test    eax, eax
0x10008f09  jnz     short loc_10008F3E
0x10008f0b  mov     eax, [ebp+var_14]
0x10008f0e  lea     edx, [ebp+var_40]
0x10008f11  push    edx
0x10008f12  push    [ebp+var_38]
0x10008f15  mov     ecx, [eax]
0x10008f17  push    eax
0x10008f18  call    dword ptr [ecx+50h]
0x10008f1b  mov     esi, eax
0x10008f1d  test    esi, esi
0x10008f1f  js      loc_1000928F
0x10008f25  mov     ecx, [ebp+var_40]
  ... truncated ...
```
