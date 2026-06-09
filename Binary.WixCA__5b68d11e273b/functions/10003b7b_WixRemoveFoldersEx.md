# WixRemoveFoldersEx

- ea: `0x10003b7b`
- end: `0x10003e3c`
- name: `WixRemoveFoldersEx`
- size: `705`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x10003447`
- `0x1000380d`
- `0x10003b7b`
- `0x1000995c`
- `0x1000a952`
- `0x1000c382`
- `0x1000c3df`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e2ae`
- `0x1000e662`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000ed03`
- `0x1000f18d`

## string_xrefs

- `0x10003b85`: `WixRemoveFoldersEx`
- `0x10003bb9`: `Failed to initialize WixRemoveFoldersEx.`
- `0x10003bc3`: `WixRemoveFolderEx`
- `0x10003bd1`: `WixRemoveFolderEx table doesn't exist, so there are no folders to remove.`
- `0x10003c04`: `Failed to open view on WixRemoveFolderEx table`
- `0x10003d8a`: `Failed to get remove folder identity.`
- `0x10003d83`: `Failed to get remove folder component.`
- `0x10003d7c`: `Failed to get remove folder property.`
- `0x10003d75`: `Failed to get remove folder mode`
- `0x10003d65`: `Failed to resolve remove folder property: %S for row: %S`
- `0x10003d46`: `Failed to expand path: %S for row: %S`
- `0x10003d30`: `Failed to backslash-terminate path: %S`
- `0x10003ce7`: `Recursing path: %S for row: %S.`
- `0x10003d26`: `Failed while navigating path: %S for row: %S`
- `0x10003d9f`: `Failure occured while processing WixRemoveFolderEx table`

## pseudocode

```c
int __stdcall WixRemoveFoldersEx(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // esi
  int v3; // eax
  int v4; // eax
  int v5; // esi
  int v7; // [esp+8h] [ebp-2Ch] BYREF
  int v8; // [esp+Ch] [ebp-28h] BYREF
  MSIHANDLE v9; // [esp+10h] [ebp-24h] BYREF
  MSIHANDLE v10; // [esp+14h] [ebp-20h] BYREF
  DWORD v11; // [esp+18h] [ebp-1Ch] BYREF
  MSIHANDLE hAny; // [esp+1Ch] [ebp-18h] BYREF
  LPCWSTR szName; // [esp+20h] [ebp-14h] BYREF
  LPCWSTR lpSrc; // [esp+24h] [ebp-10h] BYREF
  LPCWSTR lpFileName; // [esp+28h] [ebp-Ch] BYREF
  DWORD pcchValueBuf; // [esp+2Ch] [ebp-8h] BYREF
  MSIHANDLE hRecord; // [esp+30h] [ebp-4h] BYREF

  v1 = 0;
  hAny = 0;
  hRecord = 0;
  pcchValueBuf = 0;
  v11 = 0;
  szName = 0;
  lpSrc = 0;
  lpFileName = 0;
  v8 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixRemoveFoldersEx");
  if ( v2 >= 0 )
  {
    if ( sub_1000F18D(L"WixRemoveFolderEx") )
    {
      sub_1000D9AB(2, "WixRemoveFolderEx table doesn't exist, so there are no folders to remove.");
    }
    else
    {
      v2 = sub_1000ED03(off_1003300C, &hAny);
      if ( v2 >= 0 )
      {
        while ( 1 )
        {
          if ( hRecord )
            MsiCloseHandle(hRecord);
          hRecord = 0;
          v3 = sub_1000E2AE(hAny, &hRecord);
          if ( v3 )
            break;
          v2 = sub_1000E9ED(hRecord, 1u, (DWORD)&pcchValueBuf);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed to get remove folder identity.");
            goto LABEL_30;
          }
          v2 = sub_1000E9ED(hRecord, 2u, (DWORD)&v11);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed to get remove folder component.");
            goto LABEL_30;
          }
          v2 = sub_1000E9ED(hRecord, 3u, (DWORD)&szName);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed to get remove folder property.");
            goto LABEL_30;
          }
          v2 = sub_1000E8E1(hRecord, 4u, (int)&v8);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed to get remove folder mode");
            goto LABEL_30;
          }
          v2 = sub_1000E662(szName, (DWORD)&lpSrc);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed to resolve remove folder property: %S for row: %S");
            goto LABEL_30;
          }
          if ( (int)sub_10003447(lpSrc, 1, &hInstall) >= 0 )
          {
            v2 = -2147024809;
            sub_1000DA66(-2147024809, "Missing folder property: %S for row: %S");
            goto LABEL_30;
          }
          v2 = sub_1000C3DF((int)&lpFileName, lpSrc, (LPWSTR)1);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed to expand path: %S for row: %S");
            goto LABEL_30;
          }
          v4 = sub_1000C382(&lpFileName);
          v2 = v4;
          if ( v4 < 0 )
          {
            sub_1000DA66(v4, "Failed to backslash-terminate path: %S");
            goto LABEL_30;
          }
          sub_1000D9AB(2, "Recursing path: %S for row: %S.");
          v2 = sub_1000380D(lpFileName, pcchValueBuf, v11, (int)szName, v8, (int)&v7, (int)&v9, (int)&v10);
          if ( v2 < 0 )
          {
            sub_1000DA66(v2, "Failed while navigating path: %S for row: %S");
            goto LABEL_30;
          }
        }
        v2 = v3 != -2147024637 ? v3 : 0;
        if ( v2 < 0 )
          sub_1000DA66(v2, "Failure occured while processing WixRemoveFolderEx table");
      }
      else
      {
        sub_1000DA66(v2, "Failed to open view on WixRemoveFolderEx table");
      }
    }
  }
  else
  {
    sub_1000DA66(v2, "Failed to initialize WixRemoveFoldersEx.");
  }
LABEL_30:
  if ( v10 )
    MsiCloseHandle(v10);
  if ( v9 )
    MsiCloseHandle(v9);
  if ( lpFileName )
    sub_1000A952(lpFileName);
  if ( lpSrc )
    sub_1000A952(lpSrc);
  if ( szName )
    sub_1000A952(szName);
  if ( v11 )
    sub_1000A952(v11);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v2 < 0 )
    v1 = 1603;
  v5 = sub_1000D4AE(v1);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v5;
}

```

## disassembly

```asm
0x10003b7b  push    ebp
0x10003b7c  mov     ebp, esp
0x10003b7e  sub     esp, 2Ch
0x10003b81  push    esi
0x10003b82  push    edi
0x10003b83  xor     edi, edi
0x10003b85  push    offset aWixremovefolde_0; "WixRemoveFoldersEx"
0x10003b8a  push    [ebp+hInstall]; hInstall
0x10003b8d  mov     [ebp+hAny], edi
0x10003b90  mov     [ebp+hRecord], edi
0x10003b93  mov     [ebp+pcchValueBuf], edi
0x10003b96  mov     [ebp+var_1C], edi
0x10003b99  mov     [ebp+szName], edi
0x10003b9c  mov     [ebp+lpSrc], edi
0x10003b9f  mov     [ebp+lpFileName], edi
0x10003ba2  mov     [ebp+var_28], edi
0x10003ba5  mov     [ebp+var_2C], edi
0x10003ba8  mov     [ebp+var_24], edi
0x10003bab  mov     [ebp+var_20], edi
0x10003bae  call    sub_1000D51F
0x10003bb3  mov     esi, eax
0x10003bb5  test    esi, esi
0x10003bb7  jns     short loc_10003BC3
0x10003bb9  push    offset aFailedToInitia_8; "Failed to initialize WixRemoveFoldersEx"...
0x10003bbe  jmp     loc_10003DA4
0x10003bc3  push    offset aWixremovefolde_1; "WixRemoveFolderEx"
0x10003bc8  call    sub_1000F18D
0x10003bcd  test    eax, eax
0x10003bcf  jz      short loc_10003BE2
0x10003bd1  push    offset aWixremovefolde_2; "WixRemoveFolderEx table doesn't exist, "...
0x10003bd6  push    2
0x10003bd8  call    sub_1000D9AB
0x10003bdd  jmp     loc_10003DAA
0x10003be2  cmp     [ebp+hAny], edi
0x10003be5  jz      short loc_10003BEF
0x10003be7  push    [ebp+hAny]; hAny
0x10003bea  call    MsiCloseHandle
0x10003bef  lea     eax, [ebp+hAny]
0x10003bf2  push    eax; phView
0x10003bf3  push    off_1003300C; szQuery
0x10003bf9  call    sub_1000ED03
0x10003bfe  mov     esi, eax
0x10003c00  test    esi, esi
0x10003c02  jns     short loc_10003C0E
0x10003c04  push    offset aFailedToOpenVi_1; "Failed to open view on WixRemoveFolderE"...
0x10003c09  jmp     loc_10003DA4
0x10003c0e  cmp     [ebp+hRecord], edi
0x10003c11  jz      short loc_10003C1B
0x10003c13  push    [ebp+hRecord]; hAny
0x10003c16  call    MsiCloseHandle
0x10003c1b  lea     eax, [ebp+hRecord]
0x10003c1e  mov     [ebp+hRecord], edi
0x10003c21  push    eax; phRecord
0x10003c22  push    [ebp+hAny]; hView
0x10003c25  call    sub_1000E2AE
0x10003c2a  test    eax, eax
0x10003c2c  jnz     loc_10003D91
0x10003c32  lea     eax, [ebp+pcchValueBuf]
0x10003c35  push    eax; pcchValueBuf
0x10003c36  push    1; iField
0x10003c38  push    [ebp+hRecord]; hRecord
0x10003c3b  call    sub_1000E9ED
0x10003c40  mov     esi, eax
0x10003c42  test    esi, esi
0x10003c44  js      loc_10003D8A
0x10003c4a  lea     eax, [ebp+var_1C]
0x10003c4d  push    eax; pcchValueBuf
0x10003c4e  push    2; iField
0x10003c50  push    [ebp+hRecord]; hRecord
0x10003c53  call    sub_1000E9ED
0x10003c58  mov     esi, eax
0x10003c5a  test    esi, esi
0x10003c5c  js      loc_10003D83
0x10003c62  lea     eax, [ebp+szName]
0x10003c65  push    eax; pcchValueBuf
0x10003c66  push    3; iField
0x10003c68  push    [ebp+hRecord]; hRecord
0x10003c6b  call    sub_1000E9ED
0x10003c70  mov     esi, eax
0x10003c72  test    esi, esi
0x10003c74  js      loc_10003D7C
0x10003c7a  lea     eax, [ebp+var_28]
0x10003c7d  push    eax; int
0x10003c7e  push    4; iField
0x10003c80  push    [ebp+hRecord]; hRecord
0x10003c83  call    sub_1000E8E1
0x10003c88  mov     esi, eax
0x10003c8a  test    esi, esi
0x10003c8c  js      loc_10003D75
0x10003c92  lea     eax, [ebp+lpSrc]
0x10003c95  push    eax; pcchValueBuf
0x10003c96  push    [ebp+szName]; szName
0x10003c99  call    sub_1000E662
0x10003c9e  mov     esi, eax
0x10003ca0  test    esi, esi
0x10003ca2  js      loc_10003D5F
0x10003ca8  lea     eax, [ebp+hInstall]
0x10003cab  push    eax
0x10003cac  push    1
0x10003cae  push    [ebp+lpSrc]
0x10003cb1  call    sub_10003447
0x10003cb6  test    eax, eax
0x10003cb8  jns     loc_10003D4D
0x10003cbe  push    1; FilePart
0x10003cc0  push    [ebp+lpSrc]; lpSrc
0x10003cc3  lea     eax, [ebp+lpFileName]
0x10003cc6  push    eax; int
0x10003cc7  call    sub_1000C3DF
0x10003ccc  mov     esi, eax
0x10003cce  test    esi, esi
0x10003cd0  js      short loc_10003D40
0x10003cd2  lea     eax, [ebp+lpFileName]
0x10003cd5  push    eax
0x10003cd6  call    sub_1000C382
0x10003cdb  mov     esi, eax
0x10003cdd  test    esi, esi
0x10003cdf  js      short loc_10003D2D
0x10003ce1  push    [ebp+pcchValueBuf]
0x10003ce4  push    [ebp+lpFileName]
0x10003ce7  push    offset aRecursingPathS; "Recursing path: %S for row: %S."
0x10003cec  push    2
0x10003cee  call    sub_1000D9AB
0x10003cf3  add     esp, 10h
0x10003cf6  lea     eax, [ebp+var_20]
0x10003cf9  push    eax; int
0x10003cfa  lea     eax, [ebp+var_24]
0x10003cfd  push    eax; int
0x10003cfe  lea     eax, [ebp+var_2C]
0x10003d01  push    eax; int
0x10003d02  push    [ebp+var_28]; int
0x10003d05  push    [ebp+szName]; int
0x10003d08  push    [ebp+var_1C]; int
0x10003d0b  push    [ebp+pcchValueBuf]; int
0x10003d0e  push    [ebp+lpFileName]; lpFileName
0x10003d11  call    sub_1000380D
0x10003d16  mov     esi, eax
0x10003d18  test    esi, esi
0x10003d1a  jns     loc_10003C0E
0x10003d20  push    [ebp+pcchValueBuf]
0x10003d23  push    [ebp+lpSrc]
0x10003d26  push    offset aFailedWhileNav; "Failed while navigating path: %S for ro"...
0x10003d2b  jmp     short loc_10003D6A
0x10003d2d  push    [ebp+lpFileName]
0x10003d30  push    offset aFailedToBacksl; "Failed to backslash-terminate path: %S"
0x10003d35  push    esi
0x10003d36  call    sub_1000DA66
0x10003d3b  add     esp, 0Ch
0x10003d3e  jmp     short loc_10003DAC
0x10003d40  push    [ebp+pcchValueBuf]
0x10003d43  push    [ebp+lpSrc]
0x10003d46  push    offset aFailedToExpand; "Failed to expand path: %S for row: %S"
0x10003d4b  jmp     short loc_10003D6A
0x10003d4d  push    [ebp+pcchValueBuf]
0x10003d50  mov     esi, 80070057h
0x10003d55  push    [ebp+szName]
0x10003d58  push    offset aMissingFolderP; "Missing folder property: %S for row: %S"
0x10003d5d  jmp     short loc_10003D6A
0x10003d5f  push    [ebp+pcchValueBuf]
0x10003d62  push    [ebp+szName]
0x10003d65  push    offset aFailedToResolv; "Failed to resolve remove folder propert"...
0x10003d6a  push    esi
0x10003d6b  call    sub_1000DA66
0x10003d70  add     esp, 10h
0x10003d73  jmp     short loc_10003DAC
0x10003d75  push    offset aFailedToGetRem; "Failed to get remove folder mode"
0x10003d7a  jmp     short loc_10003DA4
0x10003d7c  push    offset aFailedToGetRem_0; "Failed to get remove folder property."
0x10003d81  jmp     short loc_10003DA4
0x10003d83  push    offset aFailedToGetRem_1; "Failed to get remove folder component."
0x10003d88  jmp     short loc_10003DA4
0x10003d8a  push    offset aFailedToGetRem_2; "Failed to get remove folder identity."
0x10003d8f  jmp     short loc_10003DA4
0x10003d91  lea     esi, [eax+7FF8FEFDh]
0x10003d97  neg     esi
0x10003d99  sbb     esi, esi
0x10003d9b  and     esi, eax
0x10003d9d  jge     short loc_10003DAC
0x10003d9f  push    offset aFailureOccured_0; "Failure occured while processing WixRem"...
0x10003da4  push    esi
0x10003da5  call    sub_1000DA66
0x10003daa  pop     ecx
0x10003dab  pop     ecx
0x10003dac  cmp     [ebp+var_20], edi
0x10003daf  jz      short loc_10003DB9
0x10003db1  push    [ebp+var_20]; hAny
0x10003db4  call    MsiCloseHandle
0x10003db9  cmp     [ebp+var_24], edi
0x10003dbc  jz      short loc_10003DC6
0x10003dbe  push    [ebp+var_24]; hAny
0x10003dc1  call    MsiCloseHandle
0x10003dc6  cmp     [ebp+lpFileName], edi
0x10003dc9  jz      short loc_10003DD3
0x10003dcb  push    [ebp+lpFileName]
0x10003dce  call    sub_1000A952
0x10003dd3  cmp     [ebp+lpSrc], edi
0x10003dd6  jz      short loc_10003DE0
0x10003dd8  push    [ebp+lpSrc]
0x10003ddb  call    sub_1000A952
0x10003de0  cmp     [ebp+szName], edi
0x10003de3  jz      short loc_10003DED
0x10003de5  push    [ebp+szName]
0x10003de8  call    sub_1000A952
0x10003ded  cmp     [ebp+var_1C], edi
0x10003df0  jz      short loc_10003DFA
0x10003df2  push    [ebp+var_1C]
0x10003df5  call    sub_1000A952
0x10003dfa  cmp     [ebp+pcchValueBuf], edi
0x10003dfd  jz      short loc_10003E07
0x10003dff  push    [ebp+pcchValueBuf]
0x10003e02  call    sub_1000A952
0x10003e07  test    esi, esi
0x10003e09  jns     short loc_10003E10
0x10003e0b  mov     edi, 643h
0x10003e10  push    edi
0x10003e11  call    sub_1000D4AE
0x10003e16  cmp     [ebp+hRecord], 0
0x10003e1a  mov     esi, eax
0x10003e1c  jz      short loc_10003E26
0x10003e1e  push    [ebp+hRecord]; hAny
0x10003e21  call    MsiCloseHandle
0x10003e26  cmp     [ebp+hAny], 0
0x10003e2a  jz      short loc_10003E34
0x10003e2c  push    [ebp+hAny]; hAny
0x10003e2f  call    MsiCloseHandle
0x10003e34  pop     edi
0x10003e35  mov     eax, esi
0x10003e37  pop     esi
0x10003e38  leave
0x10003e39  retn    4
```
