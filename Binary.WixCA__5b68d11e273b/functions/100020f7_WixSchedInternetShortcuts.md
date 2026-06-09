# WixSchedInternetShortcuts

- ea: `0x100020f7`
- end: `0x100025ae`
- name: `WixSchedInternetShortcuts`
- size: `1207`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x100020f7`
- `0x1000995c`
- `0x1000a538`
- `0x1000a952`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000dba2`
- `0x1000e2ae`
- `0x1000e355`
- `0x1000e78c`
- `0x1000e8e1`
- `0x1000e9ed`
- `0x1000eafc`
- `0x1000ed03`
- `0x1000ee5c`
- `0x1000f0b5`
- `0x1000f18d`
- `0x1000f1d7`
- `0x1000f269`

## import_xrefs

- `ole32!CoInitialize` at `0x10002171`
- `ole32!CoInitialize` at `0x10002171`
- `ole32!CoCreateInstance` at `0x100021a4`
- `ole32!CoCreateInstance` at `0x100021ce`
- `ole32!CoCreateInstance` at `0x10002187`
- `ole32!CoUninitialize` at `0x10002572`
- `ole32!CoUninitialize` at `0x10002572`

## string_xrefs

- `0x1000217d`: `failed to initialize COM`
- `0x100021aa`: `failed to create an instance of IUniformResourceLocatorW, skipping shortcut creation`
- `0x100021d4`: `failed to create an instance of IShellLinkW, skipping shortcut creation`
- `0x100021fd`: `failed to open view on WixInternetShortcut table`
- `0x10002473`: `failed to get shortcut component`
- `0x1000246c`: `failed to get shortcut directory`
- `0x100022e6`: `Skipping shortcut for null-action component '%ls'`
- `0x100022ff`: `Adding folder '%ls', component '%ls' to the CreateFolder table`
- `0x10002318`: `CreateFolder`
- `0x1000233a`: `Folder '%ls' already exists in the CreateFolder table; the above error is harmless`
- `0x10002439`: `Couldn't add temporary CreateFolder row`
- `0x10002432`: `failed to allocate string for shortcut directory`
- `0x10002424`: `failed to write shortcut path to custom action data`
- `0x1000241d`: `failed to write shortcut target to custom action data`
- `0x10002416`: `failed to write shortcut attributes to custom action data`
- `0x1000240f`: `failed to write icon file to custom action data`
- `0x100023fc`: `failed to write icon index to custom action data`
- `0x100024b5`: `WixRollbackInternetShortcuts`
- `0x100024c5`: `failed to set WixRollbackInternetShortcuts rollback custom action data`
- `0x100024cf`: `WixCreateInternetShortcuts`
- `0x100024df`: `failed to set WixCreateInternetShortcuts custom action data`

## pseudocode

```c
int __stdcall WixSchedInternetShortcuts(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // ebx
  HRESULT v3; // esi
  int v4; // eax
  int v5; // ebx
  bool v6; // zf
  int v7; // esi
  LPVOID ppv; // [esp+Ch] [ebp-44h] BYREF
  LPVOID v10; // [esp+10h] [ebp-40h] BYREF
  int v11; // [esp+14h] [ebp-3Ch] BYREF
  LPCWSTR v12; // [esp+18h] [ebp-38h] BYREF
  int v13; // [esp+1Ch] [ebp-34h] BYREF
  int v14; // [esp+20h] [ebp-30h] BYREF
  MSIHANDLE v15; // [esp+24h] [ebp-2Ch] BYREF
  MSIHANDLE v16; // [esp+28h] [ebp-28h] BYREF
  int iValue; // [esp+2Ch] [ebp-24h]
  LPCWSTR lpString; // [esp+30h] [ebp-20h] BYREF
  DWORD v19; // [esp+34h] [ebp-1Ch] BYREF
  DWORD pcchPathBuf; // [esp+38h] [ebp-18h] BYREF
  MSIHANDLE hAny; // [esp+3Ch] [ebp-14h] BYREF
  DWORD pcchValueBuf; // [esp+40h] [ebp-10h] BYREF
  LPCWSTR szComponent; // [esp+44h] [ebp-Ch] BYREF
  LPCWSTR szValue; // [esp+48h] [ebp-8h] BYREF
  MSIHANDLE hRecord; // [esp+4Ch] [ebp-4h] BYREF

  v1 = 0;
  iValue = 0;
  v2 = 0;
  hAny = 0;
  hRecord = 0;
  v16 = 0;
  v15 = 0;
  szValue = 0;
  szComponent = 0;
  pcchValueBuf = 0;
  v19 = 0;
  lpString = 0;
  pcchPathBuf = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  ppv = 0;
  v10 = 0;
  v3 = sub_1000D51F(hInstall, (int)"WixSchedInternetShortcuts");
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize WixSchedInternetShortcuts.");
    goto LABEL_67;
  }
  if ( sub_1000F18D(L"WixInternetShortcut") )
  {
    sub_1000D9AB(2, "WixInternetShortcut table doesn't exist, so there are no Internet shortcuts to process");
    goto LABEL_67;
  }
  v3 = CoInitialize(0);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize COM");
    goto LABEL_67;
  }
  v2 = 1;
  if ( CoCreateInstance(&stru_1002B4BC, 0, 0x17u, &stru_1002B4EC, &ppv) )
  {
    sub_1000D9AB(2, "failed to create an instance of IUniformResourceLocatorW, skipping shortcut creation");
LABEL_9:
    v3 = 0;
    goto LABEL_67;
  }
  if ( CoCreateInstance(&rclsid, 0, 0x17u, &riid, &v10) )
  {
    sub_1000D9AB(2, "failed to create an instance of IShellLinkW, skipping shortcut creation");
    goto LABEL_9;
  }
  if ( hAny )
    MsiCloseHandle(hAny);
  v3 = sub_1000ED03(off_10033004, &hAny);
  if ( v3 >= 0 )
  {
    while ( 1 )
    {
      if ( hRecord )
        MsiCloseHandle(hRecord);
      hRecord = 0;
      v4 = sub_1000E2AE(hAny, &hRecord);
      if ( v4 )
        break;
      v3 = sub_1000E9ED(hRecord, 1u, (DWORD)&szComponent);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut component");
        goto LABEL_67;
      }
      v3 = sub_1000E9ED(hRecord, 2u, (DWORD)&pcchValueBuf);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut directory");
        goto LABEL_67;
      }
      v3 = sub_1000E9ED(hRecord, 3u, (DWORD)&v19);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut filename");
        goto LABEL_67;
      }
      v3 = sub_1000E78C(hRecord, 4u, (DWORD)&lpString);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut target");
        goto LABEL_67;
      }
      v3 = sub_1000E8E1(hRecord, 5u, (int)&v13);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut attributes");
        goto LABEL_67;
      }
      v3 = sub_1000E78C(hRecord, 6u, (DWORD)&v12);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut icon file");
        goto LABEL_67;
      }
      v3 = sub_1000E8E1(hRecord, 7u, (int)&v11);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to get shortcut icon index");
        goto LABEL_67;
      }
      v5 = sub_1000E355(szComponent);
      if ( v5 )
      {
        v14 = 0;
        sub_1000D9AB(2, "Adding folder '%ls', component '%ls' to the CreateFolder table");
        v3 = sub_1000DBA2((int)&v16, (int)&v15, (int)L"CreateFolder", (int)&v14, 0, 2u);
        if ( v14 == 1 )
        {
          sub_1000D9AB(2, "Folder '%ls' already exists in the CreateFolder table; the above error is harmless");
          v3 = 0;
        }
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "Couldn't add temporary CreateFolder row");
          goto LABEL_42;
        }
        if ( v5 == 1 || (v6 = v5 == 3, v2 = 1, v6) )
        {
          v3 = sub_1000EAFC((LPCWSTR)pcchValueBuf, (DWORD)&pcchPathBuf);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to allocate string for shortcut directory");
            goto LABEL_42;
          }
          v3 = sub_1000A538(&pcchPathBuf, v19, 0);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to allocate string for shortcut filename");
            goto LABEL_42;
          }
          v3 = sub_1000F269((LPCWSTR)pcchPathBuf, (int)&szValue);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to write shortcut path to custom action data");
            goto LABEL_42;
          }
          v3 = sub_1000F269(lpString, (int)&szValue);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to write shortcut target to custom action data");
            goto LABEL_42;
          }
          v3 = sub_1000F1D7(v13, &szValue);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to write shortcut attributes to custom action data");
            goto LABEL_42;
          }
          v3 = sub_1000F269(v12, (int)&szValue);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to write icon file to custom action data");
            goto LABEL_42;
          }
          v3 = sub_1000F1D7(v11, &szValue);
          if ( v3 < 0 )
          {
            sub_1000DA66(v3, "failed to write icon index to custom action data");
LABEL_42:
            v2 = 1;
            goto LABEL_67;
          }
          iValue += 2000;
          v2 = 1;
        }
      }
      else
      {
        v2 = 1;
        sub_1000D9AB(1, "Skipping shortcut for null-action component '%ls'");
      }
    }
    v3 = v4 != -2147024637 ? v4 : 0;
    if ( v3 >= 0 )
    {
      if ( szValue && *szValue )
      {
        v3 = sub_1000EE5C(iValue, 1);
        if ( v3 >= 0 )
        {
          v3 = sub_1000F0B5(L"WixRollbackInternetShortcuts", szValue);
          if ( v3 >= 0 )
          {
            v3 = sub_1000F0B5(L"WixCreateInternetShortcuts", szValue);
            if ( v3 < 0 )
              sub_1000DA66(v3, "failed to set WixCreateInternetShortcuts custom action data");
          }
          else
          {
            sub_1000DA66(v3, "failed to set WixRollbackInternetShortcuts rollback custom action data");
          }
        }
        else
        {
          sub_1000DA66(v3, "failed to extend progress bar for InternetShortcuts");
        }
      }
    }
    else
    {
      sub_1000DA66(v3, "Failure occured while processing WixInternetShortcut table");
    }
  }
  else
  {
    sub_1000DA66(v3, "failed to open view on WixInternetShortcut table");
  }
LABEL_67:
  if ( v16 )
    MsiCloseHandle(v16);
  if ( v15 )
    MsiCloseHandle(v15);
  if ( szValue )
    sub_1000A952(szValue);
  if ( szComponent )
    sub_1000A952(szComponent);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v19 )
    sub_1000A952(v19);
  if ( lpString )
    sub_1000A952(lpString);
  if ( pcchPathBuf )
    sub_1000A952(pcchPathBuf);
  if ( v10 )
    (*(void (__stdcall **)(LPVOID))(*(_DWORD *)v10 + 8))(v10);
  if ( ppv )
    (*(void (__stdcall **)(LPVOID))(*(_DWORD *)ppv + 8))(ppv);
  if ( v2 )
    CoUninitialize();
  if ( v3 < 0 )
    v1 = 1603;
  v7 = sub_1000D4AE(v1);
  if ( hRecord )
    MsiCloseHandle(hRecord);
  if ( hAny )
    MsiCloseHandle(hAny);
  return v7;
}

```

## disassembly

```asm
0x100020f7  push    ebp
0x100020f8  mov     ebp, esp
0x100020fa  sub     esp, 44h
0x100020fd  push    ebx
0x100020fe  push    esi
0x100020ff  push    edi
0x10002100  xor     edi, edi
0x10002102  push    offset aWixschedintern_0; "WixSchedInternetShortcuts"
0x10002107  push    [ebp+hInstall]; hInstall
0x1000210a  mov     [ebp+iValue], edi
0x1000210d  mov     ebx, edi
0x1000210f  mov     [ebp+hAny], edi
0x10002112  mov     [ebp+hRecord], edi
0x10002115  mov     [ebp+var_28], edi
0x10002118  mov     [ebp+var_2C], edi
0x1000211b  mov     [ebp+szValue], edi
0x1000211e  mov     [ebp+szComponent], edi
0x10002121  mov     [ebp+pcchValueBuf], edi
0x10002124  mov     [ebp+var_1C], edi
0x10002127  mov     [ebp+lpString], edi
0x1000212a  mov     [ebp+pcchPathBuf], edi
0x1000212d  mov     [ebp+var_34], edi
0x10002130  mov     [ebp+var_38], edi
0x10002133  mov     [ebp+var_3C], edi
0x10002136  mov     [ebp+ppv], edi
0x10002139  mov     [ebp+var_40], edi
0x1000213c  call    sub_1000D51F
0x10002141  mov     esi, eax
0x10002143  test    esi, esi
0x10002145  jns     short loc_10002151
0x10002147  push    offset aFailedToInitia_6; "failed to initialize WixSchedInternetSh"...
0x1000214c  jmp     loc_100024E4
0x10002151  push    offset szTableName; "WixInternetShortcut"
0x10002156  call    sub_1000F18D
0x1000215b  test    eax, eax
0x1000215d  jz      short loc_10002170
0x1000215f  push    offset aWixinternetsho_0; "WixInternetShortcut table doesn't exist"...
0x10002164  push    2
0x10002166  call    sub_1000D9AB
0x1000216b  jmp     loc_100024EA
0x10002170  push    edi; pvReserved
0x10002171  call    ds:CoInitialize
0x10002177  mov     esi, eax
0x10002179  test    esi, esi
0x1000217b  jns     short loc_10002187
0x1000217d  push    offset aFailedToInitia_4; "failed to initialize COM"
0x10002182  jmp     loc_100024E4
0x10002187  mov     esi, ds:CoCreateInstance
0x1000218d  lea     eax, [ebp+ppv]
0x10002190  push    eax; ppv
0x10002191  push    offset stru_1002B4EC; riid
0x10002196  push    17h; dwClsContext
0x10002198  xor     ebx, ebx
0x1000219a  push    edi; pUnkOuter
0x1000219b  inc     ebx
0x1000219c  push    offset stru_1002B4BC; rclsid
0x100021a1  mov     [ebp+hInstall], ebx
0x100021a4  call    esi ; CoCreateInstance
0x100021a6  test    eax, eax
0x100021a8  jz      short loc_100021BD
0x100021aa  push    offset aFailedToCreate_3; "failed to create an instance of IUnifor"...
0x100021af  push    2
0x100021b1  call    sub_1000D9AB
0x100021b6  mov     esi, edi
0x100021b8  jmp     loc_100024EA
0x100021bd  lea     eax, [ebp+var_40]
0x100021c0  push    eax; ppv
0x100021c1  push    offset riid; riid
0x100021c6  push    17h; dwClsContext
0x100021c8  push    edi; pUnkOuter
0x100021c9  push    offset rclsid; rclsid
0x100021ce  call    esi ; CoCreateInstance
0x100021d0  test    eax, eax
0x100021d2  jz      short loc_100021DB
0x100021d4  push    offset aFailedToCreate_4; "failed to create an instance of IShellL"...
0x100021d9  jmp     short loc_100021AF
0x100021db  cmp     [ebp+hAny], edi
0x100021de  jz      short loc_100021E8
0x100021e0  push    [ebp+hAny]; hAny
0x100021e3  call    MsiCloseHandle
0x100021e8  lea     eax, [ebp+hAny]
0x100021eb  push    eax; phView
0x100021ec  push    off_10033004; szQuery
0x100021f2  call    sub_1000ED03
0x100021f7  mov     esi, eax
0x100021f9  test    esi, esi
0x100021fb  jns     short loc_10002207
0x100021fd  push    offset aFailedToOpenVi_0; "failed to open view on WixInternetShort"...
0x10002202  jmp     loc_100024E4
0x10002207  cmp     [ebp+hRecord], edi
0x1000220a  jz      short loc_10002214
0x1000220c  push    [ebp+hRecord]; hAny
0x1000220f  call    MsiCloseHandle
0x10002214  lea     eax, [ebp+hRecord]
0x10002217  mov     [ebp+hRecord], edi
0x1000221a  push    eax; phRecord
0x1000221b  push    [ebp+hAny]; hView
0x1000221e  call    sub_1000E2AE
0x10002223  test    eax, eax
0x10002225  jnz     loc_1000247A
0x1000222b  lea     eax, [ebp+szComponent]
0x1000222e  push    eax; pcchValueBuf
0x1000222f  push    ebx; iField
0x10002230  push    [ebp+hRecord]; hRecord
0x10002233  call    sub_1000E9ED
0x10002238  mov     esi, eax
0x1000223a  test    esi, esi
0x1000223c  js      loc_10002473
0x10002242  lea     eax, [ebp+pcchValueBuf]
0x10002245  push    eax; pcchValueBuf
0x10002246  push    2; iField
0x10002248  push    [ebp+hRecord]; hRecord
0x1000224b  call    sub_1000E9ED
0x10002250  mov     esi, eax
0x10002252  test    esi, esi
0x10002254  js      loc_1000246C
0x1000225a  lea     eax, [ebp+var_1C]
0x1000225d  push    eax; pcchValueBuf
0x1000225e  push    3; iField
0x10002260  push    [ebp+hRecord]; hRecord
0x10002263  call    sub_1000E9ED
0x10002268  mov     esi, eax
0x1000226a  test    esi, esi
0x1000226c  js      loc_10002465
0x10002272  lea     eax, [ebp+lpString]
0x10002275  push    eax; pcchResultBuf
0x10002276  push    4; iField
0x10002278  push    [ebp+hRecord]; hRecord
0x1000227b  call    sub_1000E78C
0x10002280  mov     esi, eax
0x10002282  test    esi, esi
0x10002284  js      loc_1000245E
0x1000228a  lea     eax, [ebp+var_34]
0x1000228d  push    eax; int
0x1000228e  push    5; iField
0x10002290  push    [ebp+hRecord]; hRecord
0x10002293  call    sub_1000E8E1
0x10002298  mov     esi, eax
0x1000229a  test    esi, esi
0x1000229c  js      loc_10002454
0x100022a2  lea     eax, [ebp+var_38]
0x100022a5  push    eax; pcchResultBuf
0x100022a6  push    6; iField
0x100022a8  push    [ebp+hRecord]; hRecord
0x100022ab  call    sub_1000E78C
0x100022b0  mov     esi, eax
0x100022b2  test    esi, esi
0x100022b4  js      loc_1000244A
0x100022ba  lea     eax, [ebp+var_3C]
0x100022bd  push    eax; int
0x100022be  push    7; iField
0x100022c0  push    [ebp+hRecord]; hRecord
0x100022c3  call    sub_1000E8E1
0x100022c8  mov     esi, eax
0x100022ca  test    esi, esi
0x100022cc  js      loc_10002440
0x100022d2  push    [ebp+szComponent]; szComponent
0x100022d5  call    sub_1000E355
0x100022da  push    [ebp+szComponent]
0x100022dd  mov     ebx, eax
0x100022df  test    ebx, ebx
0x100022e1  jnz     short loc_100022F9
0x100022e3  mov     ebx, [ebp+hInstall]
0x100022e6  push    offset aSkippingShortc; "Skipping shortcut for null-action compo"...
0x100022eb  push    ebx
0x100022ec  call    sub_1000D9AB
0x100022f1  add     esp, 0Ch
0x100022f4  jmp     loc_10002207
0x100022f9  push    [ebp+pcchValueBuf]
0x100022fc  mov     [ebp+var_30], edi
0x100022ff  push    offset aAddingFolderLs; "Adding folder '%ls', component '%ls' to"...
0x10002304  push    2
0x10002306  call    sub_1000D9AB
0x1000230b  push    [ebp+szComponent]
0x1000230e  lea     eax, [ebp+var_30]
0x10002311  push    [ebp+pcchValueBuf]
0x10002314  push    2; cParams
0x10002316  push    edi; int
0x10002317  push    eax; int
0x10002318  push    offset aCreatefolder; "CreateFolder"
0x1000231d  lea     eax, [ebp+var_2C]
0x10002320  push    eax; int
0x10002321  lea     eax, [ebp+var_28]
0x10002324  push    eax; int
0x10002325  call    sub_1000DBA2
0x1000232a  mov     esi, eax
0x1000232c  add     esp, 30h
0x1000232f  mov     eax, [ebp+hInstall]
0x10002332  cmp     [ebp+var_30], eax
0x10002335  jnz     short loc_1000234E
0x10002337  push    [ebp+pcchValueBuf]
0x1000233a  push    offset aFolderLsAlread; "Folder '%ls' already exists in the Crea"...
0x1000233f  push    2
0x10002341  call    sub_1000D9AB
0x10002346  mov     eax, [ebp+hInstall]
0x10002349  add     esp, 0Ch
0x1000234c  mov     esi, edi
0x1000234e  test    esi, esi
0x10002350  js      loc_10002439
0x10002356  cmp     ebx, eax
0x10002358  jz      short loc_10002366
0x1000235a  cmp     ebx, 3
0x1000235d  mov     ebx, [ebp+hInstall]
0x10002360  jnz     loc_10002207
0x10002366  lea     eax, [ebp+pcchPathBuf]
0x10002369  push    eax; pcchPathBuf
0x1000236a  push    [ebp+pcchValueBuf]; szFolder
0x1000236d  call    sub_1000EAFC
0x10002372  mov     esi, eax
0x10002374  test    esi, esi
0x10002376  js      loc_10002432
0x1000237c  push    edi
0x1000237d  push    [ebp+var_1C]
0x10002380  lea     eax, [ebp+pcchPathBuf]
0x10002383  push    eax
0x10002384  call    sub_1000A538
0x10002389  mov     esi, eax
0x1000238b  test    esi, esi
0x1000238d  js      loc_1000242B
0x10002393  lea     eax, [ebp+szValue]
0x10002396  push    eax; int
0x10002397  push    [ebp+pcchPathBuf]; lpString
0x1000239a  call    sub_1000F269
0x1000239f  mov     esi, eax
0x100023a1  test    esi, esi
0x100023a3  js      short loc_10002424
0x100023a5  lea     eax, [ebp+szValue]
0x100023a8  push    eax; int
0x100023a9  push    [ebp+lpString]; lpString
0x100023ac  call    sub_1000F269
0x100023b1  mov     esi, eax
0x100023b3  test    esi, esi
0x100023b5  js      short loc_1000241D
0x100023b7  lea     eax, [ebp+szValue]
0x100023ba  push    eax
0x100023bb  push    [ebp+var_34]
0x100023be  call    sub_1000F1D7
0x100023c3  mov     esi, eax
0x100023c5  test    esi, esi
0x100023c7  js      short loc_10002416
0x100023c9  lea     eax, [ebp+szValue]
0x100023cc  push    eax; int
0x100023cd  push    [ebp+var_38]; lpString
0x100023d0  call    sub_1000F269
0x100023d5  mov     esi, eax
0x100023d7  test    esi, esi
0x100023d9  js      short loc_1000240F
0x100023db  lea     eax, [ebp+szValue]
0x100023de  push    eax
0x100023df  push    [ebp+var_3C]
0x100023e2  call    sub_1000F1D7
0x100023e7  mov     esi, eax
0x100023e9  test    esi, esi
0x100023eb  js      short loc_100023FC
0x100023ed  add     [ebp+iValue], 7D0h
0x100023f4  mov     ebx, [ebp+hInstall]
0x100023f7  jmp     loc_10002207
0x100023fc  push    offset aFailedToWriteI_0; "failed to write icon index to custom ac"...
0x10002401  push    esi
0x10002402  call    sub_1000DA66
0x10002407  mov     ebx, [ebp+hInstall]
0x1000240a  jmp     loc_100024EA
0x1000240f  push    offset aFailedToWriteI_1; "failed to write icon file to custom act"...
0x10002414  jmp     short loc_10002401
0x10002416  push    offset aFailedToWriteS; "failed to write shortcut attributes to "...
0x1000241b  jmp     short loc_10002401
0x1000241d  push    offset aFailedToWriteS_0; "failed to write shortcut target to cust"...
0x10002422  jmp     short loc_10002401
0x10002424  push    offset aFailedToWriteS_1; "failed to write shortcut path to custom"...
0x10002429  jmp     short loc_10002401
0x1000242b  push    offset aFailedToAlloca; "failed to allocate string for shortcut "...
0x10002430  jmp     short loc_10002401
0x10002432  push    offset aFailedToAlloca_0; "failed to allocate string for shortcut "...
0x10002437  jmp     short loc_10002401
0x10002439  push    offset aCouldnTAddTemp; "Couldn't add temporary CreateFolder row"
0x1000243e  jmp     short loc_10002401
0x10002440  push    offset aFailedToGetSho; "failed to get shortcut icon index"
0x10002445  jmp     loc_100024E4
0x1000244a  push    offset aFailedToGetSho_0; "failed to get shortcut icon file"
0x1000244f  jmp     loc_100024E4
0x10002454  push    offset aFailedToGetSho_1; "failed to get shortcut attributes"
0x10002459  jmp     loc_100024E4
0x1000245e  push    offset aFailedToGetSho_2; "failed to get shortcut target"
0x10002463  jmp     short loc_100024E4
0x10002465  push    offset aFailedToGetSho_3; "failed to get shortcut filename"
0x1000246a  jmp     short loc_100024E4
0x1000246c  push    offset aFailedToGetSho_4; "failed to get shortcut directory"
0x10002471  jmp     short loc_100024E4
0x10002473  push    offset aFailedToGetSho_5; "failed to get shortcut component"
0x10002478  jmp     short loc_100024E4
0x1000247a  lea     esi, [eax+7FF8FEFDh]
0x10002480  neg     esi
0x10002482  sbb     esi, esi
0x10002484  and     esi, eax
0x10002486  jge     short loc_1000248F
0x10002488  push    offset aFailureOccured; "Failure occured while processing WixInt"...
0x1000248d  jmp     short loc_100024E4
0x1000248f  mov     eax, [ebp+szValue]
0x10002492  test    eax, eax
0x10002494  jz      short loc_100024EC
  ... truncated ...
```
