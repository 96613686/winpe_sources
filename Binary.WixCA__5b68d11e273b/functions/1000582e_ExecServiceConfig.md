# ExecServiceConfig

- ea: `0x1000582e`
- end: `0x10005e60`
- name: `ExecServiceConfig`
- size: `1586`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1000530d`
- `0x1000566e`
- `0x1000570f`
- `0x1000582e`
- `0x1000a952`
- `0x1000ad15`
- `0x1000ae3a`
- `0x1000aeff`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e662`
- `0x1000ee5c`
- `0x1000ef44`
- `0x1000efcc`
- `0x1000f6f2`
- `0x1000f732`
- `0x1000f8bb`
- `0x1000fbcf`
- `0x1000fc44`
- `0x10010720`
- `0x10011390`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x10005cbf`
- `ADVAPI32!CloseServiceHandle` at `0x10005dba`
- `ADVAPI32!CloseServiceHandle` at `0x10005dc8`
- `ADVAPI32!CloseServiceHandle` at `0x10005cbf`
- `ADVAPI32!CloseServiceHandle` at `0x10005dba`
- `ADVAPI32!CloseServiceHandle` at `0x10005dc8`
- `ADVAPI32!OpenSCManagerW` at `0x100058ba`
- `ADVAPI32!OpenSCManagerW` at `0x100058ba`
- `ADVAPI32!QueryServiceConfig2W` at `0x10005acb`
- `ADVAPI32!QueryServiceConfig2W` at `0x10005b05`
- `ADVAPI32!QueryServiceConfig2W` at `0x10005acb`
- `ADVAPI32!QueryServiceConfig2W` at `0x10005b05`
- `KERNEL32!GetLastError` at `0x100058c7`
- `KERNEL32!GetLastError` at `0x10005adb`
- `KERNEL32!GetLastError` at `0x10005b0f`
- `KERNEL32!GetLastError` at `0x10005ce4`
- `KERNEL32!GetLastError` at `0x100058c7`
- `KERNEL32!GetLastError` at `0x10005ad5`
- `KERNEL32!GetLastError` at `0x10005b0f`
- `KERNEL32!LocalFree` at `0x10005dac`
- `KERNEL32!LocalFree` at `0x10005dac`
- `KERNEL32!FormatMessageW` at `0x100058f0`
- `KERNEL32!FormatMessageW` at `0x100058f0`

## string_xrefs

- `0x10005899`: `ExecServiceConfig`
- `0x1000596c`: `Failed to read encoding key from CustomActionData.`
- `0x1000598e`: `Failed to open rollback CustomAction script.`
- `0x10005a89`: `Configuring Service: %ls`
- `0x10005d84`: `Failed to get service: %ls`
- `0x10005d04`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\serviceconfig.cpp`
- `0x10005d23`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\serviceconfig.cpp`
- `0x10005d54`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\serviceconfig.cpp`
- `0x10005d0e`: `Failed to get current service config info.`
- `0x10005d5e`: `failed to allocate memory for service failure actions.`
- `0x10005d2d`: `failed to Query Service.`
- `0x10005d42`: `Failed to add service name to Rollback Log`
- `0x10005b83`: `failed to add data to Rollback CustomActionData`
- `0x10005d6f`: `Failed to configure service: %ls`

## pseudocode

```c
int __stdcall ExecServiceConfig(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // ebx
  signed int v3; // esi
  signed int LastError; // eax
  int v5; // eax
  _WORD *v6; // eax
  SC_HANDLE v7; // esi
  signed int v8; // eax
  bool v9; // sf
  int v10; // ecx
  int v11; // ecx
  const WCHAR *v12; // eax
  const WCHAR *v13; // eax
  SC_HANDLE v14; // ebx
  int v15; // eax
  signed int v16; // eax
  bool v17; // sf
  unsigned int v19; // [esp+Ch] [ebp-90h]
  int v20; // [esp+10h] [ebp-8Ch] BYREF
  int v21; // [esp+14h] [ebp-88h] BYREF
  int v22; // [esp+18h] [ebp-84h] BYREF
  int v23; // [esp+1Ch] [ebp-80h]
  int v24; // [esp+20h] [ebp-7Ch] BYREF
  int v25; // [esp+24h] [ebp-78h] BYREF
  int v26; // [esp+28h] [ebp-74h] BYREF
  int v27; // [esp+2Ch] [ebp-70h] BYREF
  int v28; // [esp+30h] [ebp-6Ch] BYREF
  SC_HANDLE hSCObject; // [esp+34h] [ebp-68h]
  WCHAR Buffer[2]; // [esp+38h] [ebp-64h] BYREF
  DWORD pcbBytesNeeded; // [esp+3Ch] [ebp-60h] BYREF
  DWORD pcchValueBuf; // [esp+40h] [ebp-5Ch] BYREF
  int v33; // [esp+44h] [ebp-58h] BYREF
  SC_HANDLE hService; // [esp+48h] [ebp-54h] BYREF
  LPCWSTR lpString; // [esp+4Ch] [ebp-50h] BYREF
  LPVOID lpMem; // [esp+50h] [ebp-4Ch] BYREF
  wchar_t SubStr[2]; // [esp+54h] [ebp-48h] BYREF
  WCHAR String[32]; // [esp+58h] [ebp-44h] BYREF

  v1 = 0;
  pcchValueBuf = 0;
  *(_DWORD *)SubStr = 0;
  v33 = 0;
  lpMem = 0;
  lpString = 0;
  v20 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v22 = 0;
  v21 = 0;
  *(_DWORD *)Buffer = 0;
  hSCObject = 0;
  hService = 0;
  v19 = 0;
  memset(String, 0, sizeof(String));
  pcbBytesNeeded = 0;
  v2 = 0;
  v3 = sub_1000D51F(hInstall, (int)"ExecServiceConfig");
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize");
    goto LABEL_78;
  }
  hSCObject = OpenSCManagerW(0, 0, 1u);
  if ( !hSCObject )
  {
    LastError = GetLastError();
    v3 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    FormatMessageW(0x1300u, 0, LastError, 0x400u, Buffer, 0, 0);
    if ( v3 < 0 )
    {
      sub_1000DA66(v3, "Failed to get handle to SCM. Error: %ls");
      goto LABEL_78;
    }
  }
  v3 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to get CustomActionData");
    goto LABEL_78;
  }
  sub_1000D9AB(0, "CustomActionData: %ls");
  *(_DWORD *)SubStr = pcchValueBuf;
  v5 = sub_1000EFCC((wchar_t)SubStr, (int)&v33);
  v3 = v5;
  if ( !v33 )
  {
    v3 = -2147418113;
    sub_1000DA66(-2147418113, "Failed due to unexpected CustomActionData passed.");
    goto LABEL_78;
  }
  if ( v5 < 0 )
  {
    sub_1000DA66(v5, "Failed to read encoding key from CustomActionData.");
    goto LABEL_78;
  }
  v3 = sub_1000F732(1, 1, 0, v33, 0, &lpMem);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "Failed to open rollback CustomAction script.");
    goto LABEL_78;
  }
  v6 = *(_WORD **)SubStr;
  if ( *(_DWORD *)SubStr )
  {
    while ( 1 )
    {
      v2 = 0;
      if ( !*v6 )
        goto LABEL_78;
      v3 = sub_1000EFCC((wchar_t)SubStr, (int)&lpString);
      if ( v3 < 0 )
        goto LABEL_77;
      v3 = sub_1000EF44((wchar_t)SubStr, (int)&v20);
      if ( v3 < 0
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v24), v3 < 0)
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v25), v3 < 0)
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v26), v3 < 0)
        || (v3 = sub_1000EF44((wchar_t)SubStr, (int)&v22), v3 < 0)
        || (v3 = sub_1000EF44((wchar_t)SubStr, (int)&v21), v3 < 0)
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v27), v3 < 0)
        || (v3 = sub_1000EFCC((wchar_t)SubStr, (int)&v28), v3 < 0) )
      {
LABEL_77:
        sub_1000DA66(v3, "failed to process CustomActionData");
        goto LABEL_78;
      }
      sub_1000D9AB(1, "Configuring Service: %ls");
      v3 = sub_1000570F(hSCObject, lpString, 0x13u, (int)&hService);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "Failed to get service: %ls");
        goto LABEL_78;
      }
      if ( !v20 )
      {
        v7 = hService;
        if ( !QueryServiceConfig2W(hService, 2u, 0, 0, &pcbBytesNeeded) && GetLastError() != 122 )
        {
          v16 = GetLastError();
          v3 = v16;
          v17 = v16 < 0;
          if ( v16 > 0 )
          {
            v3 = (unsigned __int16)v16 | 0x80070000;
            v17 = 1;
          }
          if ( !v17 )
            v3 = -2147467259;
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\serviceconfig.cpp", 307, v3);
          sub_1000DA66(v3, "Failed to get current service config info.");
          goto LABEL_67;
        }
        v2 = sub_1000AE3A(pcbBytesNeeded, 1);
        if ( !v2 )
        {
          v3 = -2147024882;
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\serviceconfig.cpp", 311, -2147024882);
          sub_1000DA66(-2147024882, "failed to allocate memory for service failure actions.");
          goto LABEL_78;
        }
        if ( !QueryServiceConfig2W(v7, 2u, (LPBYTE)v2, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          v8 = GetLastError();
          v3 = v8;
          v9 = v8 < 0;
          if ( v8 > 0 )
          {
            v3 = (unsigned __int16)v8 | 0x80070000;
            v9 = 1;
          }
          if ( v9 )
          {
            nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\serviceconfig.cpp", 315, v3);
            sub_1000DA66(v3, "failed to Query Service.");
            goto LABEL_78;
          }
        }
        v3 = sub_1000FC44((int)lpMem, lpString);
        if ( v3 < 0 )
        {
          sub_1000DA66(v3, "Failed to add service name to Rollback Log");
          goto LABEL_78;
        }
        if ( *(_DWORD *)(v2 + 12) >= 3u )
        {
          v10 = 0;
          v23 = 0;
          while ( 1 )
          {
            v3 = sub_1000566E(*(_DWORD *)(v10 + *(_DWORD *)(v2 + 16)), String, 32);
            if ( v3 < 0 )
              break;
            v11 = *(_DWORD *)(v2 + 16);
            if ( *(_DWORD *)(v23 + v11) == 1 )
              v19 = *(_DWORD *)(v23 + v11 + 4) / 0x3E8u;
            v3 = sub_1000FC44((int)lpMem, String);
            if ( v3 < 0 )
              goto LABEL_42;
            v10 = v23 + 8;
            v23 = v10;
            if ( v10 >= 24 )
              goto LABEL_49;
          }
          sub_1000DA66(v3, "failed to query SFA object");
          goto LABEL_78;
        }
        v3 = sub_1000FC44((int)lpMem, ::lpString);
        if ( v3 < 0 )
          goto LABEL_42;
        v3 = sub_1000FC44((int)lpMem, ::lpString);
        if ( v3 < 0 )
          goto LABEL_42;
        v3 = sub_1000FC44((int)lpMem, ::lpString);
        if ( v3 < 0 )
          goto LABEL_42;
LABEL_49:
        v3 = sub_1000FBCF(lpMem, *(_DWORD *)v2 / 0x15180u);
        if ( v3 < 0 || (v3 = sub_1000FBCF(lpMem, v19), v3 < 0) )
        {
          sub_1000DA66(v3, "failed to add data to CustomActionData");
          goto LABEL_78;
        }
        v12 = *(const WCHAR **)(v2 + 8);
        if ( !v12 )
        {
          v12 = &dword_100226F0;
          *(_DWORD *)(v2 + 8) = &dword_100226F0;
        }
        v3 = sub_1000FC44((int)lpMem, v12);
        if ( v3 < 0 )
          goto LABEL_42;
        v13 = *(const WCHAR **)(v2 + 4);
        if ( !v13 )
        {
          v13 = &dword_100226F0;
          *(_DWORD *)(v2 + 4) = &dword_100226F0;
        }
        v3 = sub_1000FC44((int)lpMem, v13);
        if ( v3 < 0 )
        {
LABEL_42:
          sub_1000DA66(v3, "failed to add data to Rollback CustomActionData");
          goto LABEL_78;
        }
        sub_1000F8BB(lpMem);
        sub_1000AEFF((LPVOID)v2);
      }
      v14 = hService;
      v15 = sub_1000530D(hSCObject, hService, lpString, v21, v24, v25, v26, v22, v28, v27);
      v3 = v15;
      if ( v15 < 0 )
        break;
      v3 = sub_1000EE5C(1000, 0);
      if ( v3 < 0 )
      {
        sub_1000DA66(v3, "failed to send progress message");
LABEL_67:
        v2 = 0;
        goto LABEL_78;
      }
      CloseServiceHandle(v14);
      v6 = *(_WORD **)SubStr;
      hService = 0;
      v22 = 0;
      v21 = 0;
      if ( !*(_DWORD *)SubStr )
        goto LABEL_75;
    }
    sub_1000DA66(v15, "Failed to configure service: %ls");
LABEL_75:
    v2 = 0;
  }
LABEL_78:
  sub_1000F6F2(lpMem, 0);
  if ( *(_DWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  if ( hService )
    CloseServiceHandle(hService);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  if ( v2 )
    sub_1000AEFF((LPVOID)v2);
  if ( v28 )
    sub_1000A952(v28);
  if ( v27 )
    sub_1000A952(v27);
  if ( v26 )
    sub_1000A952(v26);
  if ( v25 )
    sub_1000A952(v25);
  if ( v24 )
    sub_1000A952(v24);
  if ( lpString )
    sub_1000A952(lpString);
  if ( v33 )
    sub_1000A952(v33);
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x1000582e  push    ebp
0x1000582f  mov     ebp, esp
0x10005831  sub     esp, 90h
0x10005837  mov     eax, ___security_cookie
0x1000583c  xor     eax, ebp
0x1000583e  mov     [ebp+var_4], eax
0x10005841  push    ebx
0x10005842  push    esi
0x10005843  push    edi
0x10005844  xor     edi, edi
0x10005846  lea     eax, [ebp+String]
0x10005849  push    40h ; '@'; Size
0x1000584b  push    edi; Val
0x1000584c  push    eax; void *
0x1000584d  mov     [ebp+pcchValueBuf], edi
0x10005850  mov     dword ptr [ebp+SubStr], edi
0x10005853  mov     [ebp+var_58], edi
0x10005856  mov     [ebp+lpMem], edi
0x10005859  mov     [ebp+lpString], edi
0x1000585c  mov     [ebp+var_8C], edi
0x10005862  mov     [ebp+var_7C], edi
0x10005865  mov     [ebp+var_78], edi
0x10005868  mov     [ebp+var_74], edi
0x1000586b  mov     [ebp+var_70], edi
0x1000586e  mov     [ebp+var_6C], edi
0x10005871  mov     [ebp+var_84], edi
0x10005877  mov     [ebp+var_88], edi
0x1000587d  mov     dword ptr [ebp+Buffer], edi
0x10005880  mov     [ebp+hSCObject], edi
0x10005883  mov     [ebp+hService], edi
0x10005886  mov     [ebp+var_90], edi
0x1000588c  call    _memset
0x10005891  add     esp, 0Ch
0x10005894  mov     [ebp+pcbBytesNeeded], edi
0x10005897  mov     ebx, edi
0x10005899  push    offset aExecservicecon_0; "ExecServiceConfig"
0x1000589e  push    [ebp+hInstall]; hInstall
0x100058a1  call    sub_1000D51F
0x100058a6  mov     esi, eax
0x100058a8  test    esi, esi
0x100058aa  jns     short loc_100058B6
0x100058ac  push    offset aFailedToInitia_2; "failed to initialize"
0x100058b1  jmp     loc_10005D93
0x100058b6  push    1; dwDesiredAccess
0x100058b8  push    edi; lpDatabaseName
0x100058b9  push    edi; lpMachineName
0x100058ba  call    ds:OpenSCManagerW
0x100058c0  mov     [ebp+hSCObject], eax
0x100058c3  test    eax, eax
0x100058c5  jnz     short loc_10005910
0x100058c7  call    ds:GetLastError
0x100058cd  test    eax, eax
0x100058cf  jg      short loc_100058D5
0x100058d1  mov     esi, eax
0x100058d3  jmp     short loc_100058DE
0x100058d5  movzx   esi, ax
0x100058d8  or      esi, 80070000h
0x100058de  push    edi; Arguments
0x100058df  push    edi; nSize
0x100058e0  lea     ecx, [ebp+Buffer]
0x100058e3  push    ecx; lpBuffer
0x100058e4  push    400h; dwLanguageId
0x100058e9  push    eax; dwMessageId
0x100058ea  push    edi; lpSource
0x100058eb  push    1300h; dwFlags
0x100058f0  call    ds:FormatMessageW
0x100058f6  test    esi, esi
0x100058f8  jns     short loc_10005910
0x100058fa  push    dword ptr [ebp+Buffer]
0x100058fd  push    offset aFailedToGetHan_0; "Failed to get handle to SCM. Error: %ls"
0x10005902  push    esi
0x10005903  call    sub_1000DA66
0x10005908  add     esp, 0Ch
0x1000590b  jmp     loc_10005D9B
0x10005910  lea     eax, [ebp+pcchValueBuf]
0x10005913  push    eax; pcchValueBuf
0x10005914  push    offset aCustomactionda; "CustomActionData"
0x10005919  call    sub_1000E662
0x1000591e  mov     esi, eax
0x10005920  test    esi, esi
0x10005922  jns     short loc_1000592E
0x10005924  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x10005929  jmp     loc_10005D93
0x1000592e  push    [ebp+pcchValueBuf]
0x10005931  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10005936  push    edi
0x10005937  call    sub_1000D9AB
0x1000593c  mov     eax, [ebp+pcchValueBuf]
0x1000593f  add     esp, 0Ch
0x10005942  mov     dword ptr [ebp+SubStr], eax
0x10005945  lea     eax, [ebp+var_58]
0x10005948  push    eax; int
0x10005949  lea     eax, [ebp+SubStr]
0x1000594c  push    eax; SubStr
0x1000594d  call    sub_1000EFCC
0x10005952  mov     esi, eax
0x10005954  cmp     [ebp+var_58], ebx
0x10005957  jnz     short loc_10005968
0x10005959  mov     esi, 8000FFFFh
0x1000595e  push    offset aFailedDueToUne; "Failed due to unexpected CustomActionDa"...
0x10005963  jmp     loc_10005D93
0x10005968  test    esi, esi
0x1000596a  jns     short loc_10005976
0x1000596c  push    offset aFailedToReadEn; "Failed to read encoding key from Custom"...
0x10005971  jmp     loc_10005D93
0x10005976  lea     eax, [ebp+lpMem]
0x10005979  push    eax
0x1000597a  push    edi
0x1000597b  push    [ebp+var_58]
0x1000597e  push    edi
0x1000597f  push    1
0x10005981  push    1
0x10005983  call    sub_1000F732
0x10005988  mov     esi, eax
0x1000598a  test    esi, esi
0x1000598c  jns     short loc_10005998
0x1000598e  push    offset aFailedToOpenRo; "Failed to open rollback CustomAction sc"...
0x10005993  jmp     loc_10005D93
0x10005998  mov     eax, dword ptr [ebp+SubStr]
0x1000599b  test    eax, eax
0x1000599d  jz      loc_10005D9B
0x100059a3  mov     ebx, edi
0x100059a5  cmp     [eax], di
0x100059a8  jz      loc_10005D9B
0x100059ae  lea     eax, [ebp+lpString]
0x100059b1  push    eax; int
0x100059b2  lea     eax, [ebp+SubStr]
0x100059b5  push    eax; SubStr
0x100059b6  call    sub_1000EFCC
0x100059bb  mov     esi, eax
0x100059bd  test    esi, esi
0x100059bf  js      loc_10005D8E
0x100059c5  lea     eax, [ebp+var_8C]
0x100059cb  push    eax; int
0x100059cc  lea     eax, [ebp+SubStr]
0x100059cf  push    eax; SubStr
0x100059d0  call    sub_1000EF44
0x100059d5  mov     esi, eax
0x100059d7  test    esi, esi
0x100059d9  js      loc_10005D8E
0x100059df  lea     eax, [ebp+var_7C]
0x100059e2  push    eax; int
0x100059e3  lea     eax, [ebp+SubStr]
0x100059e6  push    eax; SubStr
0x100059e7  call    sub_1000EFCC
0x100059ec  mov     esi, eax
0x100059ee  test    esi, esi
0x100059f0  js      loc_10005D8E
0x100059f6  lea     eax, [ebp+var_78]
0x100059f9  push    eax; int
0x100059fa  lea     eax, [ebp+SubStr]
0x100059fd  push    eax; SubStr
0x100059fe  call    sub_1000EFCC
0x10005a03  mov     esi, eax
0x10005a05  test    esi, esi
0x10005a07  js      loc_10005D8E
0x10005a0d  lea     eax, [ebp+var_74]
0x10005a10  push    eax; int
0x10005a11  lea     eax, [ebp+SubStr]
0x10005a14  push    eax; SubStr
0x10005a15  call    sub_1000EFCC
0x10005a1a  mov     esi, eax
0x10005a1c  test    esi, esi
0x10005a1e  js      loc_10005D8E
0x10005a24  lea     eax, [ebp+var_84]
0x10005a2a  push    eax; int
0x10005a2b  lea     eax, [ebp+SubStr]
0x10005a2e  push    eax; SubStr
0x10005a2f  call    sub_1000EF44
0x10005a34  mov     esi, eax
0x10005a36  test    esi, esi
0x10005a38  js      loc_10005D8E
0x10005a3e  lea     eax, [ebp+var_88]
0x10005a44  push    eax; int
0x10005a45  lea     eax, [ebp+SubStr]
0x10005a48  push    eax; SubStr
0x10005a49  call    sub_1000EF44
0x10005a4e  mov     esi, eax
0x10005a50  test    esi, esi
0x10005a52  js      loc_10005D8E
0x10005a58  lea     eax, [ebp+var_70]
0x10005a5b  push    eax; int
0x10005a5c  lea     eax, [ebp+SubStr]
0x10005a5f  push    eax; SubStr
0x10005a60  call    sub_1000EFCC
0x10005a65  mov     esi, eax
0x10005a67  test    esi, esi
0x10005a69  js      loc_10005D8E
0x10005a6f  lea     eax, [ebp+var_6C]
0x10005a72  push    eax; int
0x10005a73  lea     eax, [ebp+SubStr]
0x10005a76  push    eax; SubStr
0x10005a77  call    sub_1000EFCC
0x10005a7c  mov     esi, eax
0x10005a7e  test    esi, esi
0x10005a80  js      loc_10005D8E
0x10005a86  push    [ebp+lpString]
0x10005a89  push    offset aConfiguringSer; "Configuring Service: %ls"
0x10005a8e  push    1
0x10005a90  call    sub_1000D9AB
0x10005a95  add     esp, 0Ch
0x10005a98  lea     eax, [ebp+hService]
0x10005a9b  push    eax; int
0x10005a9c  push    13h; dwDesiredAccess
0x10005a9e  push    [ebp+lpString]; lpServiceName
0x10005aa1  push    [ebp+hSCObject]; hSCManager
0x10005aa4  call    sub_1000570F
0x10005aa9  mov     esi, eax
0x10005aab  test    esi, esi
0x10005aad  js      loc_10005D81
0x10005ab3  cmp     [ebp+var_8C], ebx
0x10005ab9  jnz     loc_10005C74
0x10005abf  mov     esi, [ebp+hService]
0x10005ac2  lea     eax, [ebp+pcbBytesNeeded]
0x10005ac5  push    eax; pcbBytesNeeded
0x10005ac6  push    edi; cbBufSize
0x10005ac7  push    edi; lpBuffer
0x10005ac8  push    2; dwInfoLevel
0x10005aca  push    esi; hService
0x10005acb  call    ds:QueryServiceConfig2W
0x10005ad1  test    eax, eax
0x10005ad3  jnz     short loc_10005AE6
0x10005ad5  mov     ebx, ds:GetLastError
0x10005adb  call    ebx ; GetLastError
0x10005add  cmp     eax, 7Ah ; 'z'
0x10005ae0  jnz     loc_10005CE4
0x10005ae6  push    1; int
0x10005ae8  push    [ebp+pcbBytesNeeded]; dwBytes
0x10005aeb  call    sub_1000AE3A
0x10005af0  mov     ebx, eax
0x10005af2  test    ebx, ebx
0x10005af4  jz      loc_10005D49
0x10005afa  lea     eax, [ebp+pcbBytesNeeded]
0x10005afd  push    eax; pcbBytesNeeded
0x10005afe  push    [ebp+pcbBytesNeeded]; cbBufSize
0x10005b01  push    ebx; lpBuffer
0x10005b02  push    2; dwInfoLevel
0x10005b04  push    esi; hService
0x10005b05  call    ds:QueryServiceConfig2W
0x10005b0b  test    eax, eax
0x10005b0d  jnz     short loc_10005B2C
0x10005b0f  call    ds:GetLastError
0x10005b15  mov     esi, eax
0x10005b17  test    esi, esi
0x10005b19  jle     short loc_10005B26
0x10005b1b  movzx   esi, si
0x10005b1e  or      esi, 80070000h
0x10005b24  test    esi, esi
0x10005b26  js      loc_10005D1D
0x10005b2c  push    [ebp+lpString]; lpString
0x10005b2f  push    [ebp+lpMem]; int
0x10005b32  call    sub_1000FC44
0x10005b37  mov     esi, eax
0x10005b39  test    esi, esi
0x10005b3b  js      loc_10005D42
0x10005b41  cmp     dword ptr [ebx+0Ch], 3
0x10005b45  jnb     short loc_10005B8D
0x10005b47  push    lpString; lpString
0x10005b4d  push    [ebp+lpMem]; int
0x10005b50  call    sub_1000FC44
0x10005b55  mov     esi, eax
0x10005b57  test    esi, esi
0x10005b59  js      short loc_10005B83
0x10005b5b  push    lpString; lpString
0x10005b61  push    [ebp+lpMem]; int
0x10005b64  call    sub_1000FC44
0x10005b69  mov     esi, eax
0x10005b6b  test    esi, esi
0x10005b6d  js      short loc_10005B83
0x10005b6f  push    lpString; lpString
0x10005b75  push    [ebp+lpMem]; int
0x10005b78  call    sub_1000FC44
0x10005b7d  mov     esi, eax
0x10005b7f  test    esi, esi
0x10005b81  jns     short loc_10005BEC
0x10005b83  push    offset aFailedToAddDat_2; "failed to add data to Rollback CustomAc"...
0x10005b88  jmp     loc_10005D93
0x10005b8d  mov     ecx, edi
0x10005b8f  mov     [ebp+var_80], edi
0x10005b92  push    20h ; ' '
0x10005b94  lea     eax, [ebp+String]
0x10005b97  push    eax
0x10005b98  mov     eax, [ebx+10h]
0x10005b9b  push    dword ptr [ecx+eax]
0x10005b9e  call    sub_1000566E
0x10005ba3  mov     esi, eax
0x10005ba5  test    esi, esi
0x10005ba7  js      loc_10005D3B
0x10005bad  mov     ecx, [ebx+10h]
0x10005bb0  mov     eax, [ebp+var_80]
0x10005bb3  cmp     dword ptr [eax+ecx], 1
0x10005bb7  jnz     short loc_10005BCC
0x10005bb9  mov     eax, [eax+ecx+4]
0x10005bbd  xor     edx, edx
0x10005bbf  mov     ecx, 3E8h
0x10005bc4  div     ecx
0x10005bc6  mov     [ebp+var_90], eax
0x10005bcc  lea     eax, [ebp+String]
0x10005bcf  push    eax; lpString
0x10005bd0  push    [ebp+lpMem]; int
  ... truncated ...
```
