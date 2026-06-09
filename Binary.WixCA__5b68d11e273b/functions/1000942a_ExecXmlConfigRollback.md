# ExecXmlConfigRollback

- ea: `0x1000942a`
- end: `0x10009693`
- name: `ExecXmlConfigRollback`
- size: `617`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1000942a`
- `0x1000a952`
- `0x1000ad15`
- `0x1000aeff`
- `0x1000b556`
- `0x1000b8d3`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000d9ab`
- `0x1000da66`
- `0x1000e662`
- `0x1000ef44`
- `0x1000ef8f`
- `0x1000efcc`
- `0x10010509`
- `0x10010563`
- `0x10010583`
- `0x10010646`
- `0x10010671`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1000960d`
- `KERNEL32!CloseHandle` at `0x1000965b`
- `KERNEL32!CloseHandle` at `0x1000960d`
- `KERNEL32!CloseHandle` at `0x1000965b`
- `KERNEL32!GetLastError` at `0x1000958b`
- `KERNEL32!GetLastError` at `0x100095d9`
- `KERNEL32!GetLastError` at `0x1000958b`
- `KERNEL32!GetLastError` at `0x100095d9`
- `KERNEL32!CreateFileW` at `0x1000957e`
- `KERNEL32!CreateFileW` at `0x1000957e`
- `KERNEL32!WriteFile` at `0x100095cf`
- `KERNEL32!WriteFile` at `0x100095cf`

## string_xrefs

- `0x100094d1`: `failed to read file name from custom action data`
- `0x100094b7`: `failed to read component bitness from custom action data`
- `0x100094ef`: `failed to read file contents from custom action data`
- `0x10009545`: `Custom action was told to rollback a 64-bit component, but was unable to Disable Filesystem Redirection through the Wow64 API.`
- `0x100095bc`: `failed to open file: %ls`
- `0x10009605`: `failed to write to file: %ls`
- `0x100095af`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\xmlconfig.cpp`
- `0x100095f8`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\xmlconfig.cpp`
- `0x10009438`: `ExecXmlConfigRollback`
- `0x10009530`: `Custom action was told to rollback a 64-bit component, but the Wow64 API is unavailable.`

## pseudocode

```c
int __stdcall ExecXmlConfigRollback(MSIHANDLE hInstall)
{
  int v1; // edi
  int FileW; // ebx
  signed int v3; // esi
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  bool v7; // sf
  struct _FILETIME LastWriteTime; // [esp+Ch] [ebp-24h] BYREF
  DWORD NumberOfBytesWritten; // [esp+14h] [ebp-1Ch] BYREF
  MSIHANDLE v11; // [esp+18h] [ebp-18h]
  DWORD nNumberOfBytesToWrite; // [esp+1Ch] [ebp-14h] BYREF
  LPCVOID lpBuffer; // [esp+20h] [ebp-10h] BYREF
  wchar_t SubStr[2]; // [esp+24h] [ebp-Ch] BYREF
  DWORD pcchValueBuf; // [esp+28h] [ebp-8h] BYREF
  LPCWSTR lpFileName; // [esp+2Ch] [ebp-4h] BYREF

  v1 = 0;
  FileW = -1;
  v11 = 0;
  pcchValueBuf = 0;
  *(_DWORD *)SubStr = 0;
  lpFileName = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  v3 = sub_1000D51F(hInstall, (int)"ExecXmlConfigRollback");
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize");
    goto LABEL_35;
  }
  v3 = sub_1000E662(L"CustomActionData", (DWORD)&pcchValueBuf);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to get CustomActionData");
    goto LABEL_35;
  }
  sub_1000D9AB(0, "CustomActionData: %ls");
  *(_DWORD *)SubStr = pcchValueBuf;
  v3 = sub_1000EF44((wchar_t)SubStr, (int)&hInstall);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to read component bitness from custom action data");
    goto LABEL_35;
  }
  v3 = sub_1000EFCC((wchar_t)SubStr, (int)&lpFileName);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to read file name from custom action data");
    goto LABEL_35;
  }
  v3 = sub_1000EF8F((wchar_t)SubStr, (int)&lpBuffer, (int)&nNumberOfBytesToWrite);
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to read file contents from custom action data");
    goto LABEL_35;
  }
  v11 = hInstall;
  if ( !hInstall )
    goto LABEL_20;
  v3 = sub_10010583();
  if ( v3 == 1 )
    v3 = -2147319761;
  if ( v3 < 0 )
  {
    sub_1000DA66(v3, "failed to initialize Wow64 API");
    goto LABEL_35;
  }
  if ( !sub_10010646() )
  {
    v3 = -2147467263;
    sub_1000DA66(
      -2147467263,
      "Custom action was told to rollback a 64-bit component, but the Wow64 API is unavailable.");
    goto LABEL_35;
  }
  v3 = sub_10010509();
  if ( v3 < 0 )
  {
    sub_1000DA66(
      v3,
      "Custom action was told to rollback a 64-bit component, but was unable to Disable Filesystem Redirection through the Wow64 API.");
  }
  else
  {
LABEL_20:
    v3 = sub_1000B556(lpFileName, 0, 0, &LastWriteTime);
    if ( v3 >= 0 )
    {
      FileW = (int)CreateFileW(lpFileName, 0x40000000u, 0, 0, 5u, 0, 0);
      if ( FileW == -1 )
      {
        LastError = GetLastError();
        v3 = LastError;
        v5 = LastError < 0;
        if ( LastError > 0 )
        {
          v3 = (unsigned __int16)LastError | 0x80070000;
          v5 = 1;
        }
        if ( !v5 )
          v3 = -2147467259;
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\xmlconfig.cpp", 1076, v3);
        sub_1000DA66(v3, "failed to open file: %ls");
      }
      else
      {
        if ( WriteFile((HANDLE)FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
          goto LABEL_33;
        v6 = GetLastError();
        v3 = v6;
        v7 = v6 < 0;
        if ( v6 > 0 )
        {
          v3 = (unsigned __int16)v6 | 0x80070000;
          v7 = 1;
        }
        if ( !v7 )
        {
LABEL_33:
          CloseHandle((HANDLE)FileW);
          FileW = -1;
          v3 = sub_1000B8D3(lpFileName, 0, 0, &LastWriteTime);
          if ( v3 < 0 )
            sub_1000DA66(v3, "Failed to set modified date of file %ls.");
        }
        else
        {
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\xmlconfig.cpp", 1081, v3);
          sub_1000DA66(v3, "failed to write to file: %ls");
        }
      }
    }
    else
    {
      sub_1000DA66(v3, "Failed to get modified date of file %ls.");
    }
  }
LABEL_35:
  if ( pcchValueBuf )
    sub_1000A952(pcchValueBuf);
  if ( lpFileName )
    sub_1000A952(lpFileName);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v11 )
  {
    sub_10010671();
    sub_10010563();
  }
  if ( lpBuffer )
    sub_1000AEFF((LPVOID)lpBuffer);
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x1000942a  push    ebp
0x1000942b  mov     ebp, esp
0x1000942d  sub     esp, 24h
0x10009430  push    ebx
0x10009431  push    esi
0x10009432  push    edi
0x10009433  xor     edi, edi
0x10009435  or      ebx, 0FFFFFFFFh
0x10009438  push    offset aExecxmlconfigr_1; "ExecXmlConfigRollback"
0x1000943d  push    [ebp+hInstall]; hInstall
0x10009440  mov     [ebp+var_18], edi
0x10009443  mov     [ebp+pcchValueBuf], edi
0x10009446  mov     dword ptr [ebp+SubStr], edi
0x10009449  mov     [ebp+lpFileName], edi
0x1000944c  mov     [ebp+lpBuffer], edi
0x1000944f  mov     [ebp+nNumberOfBytesToWrite], edi
0x10009452  mov     [ebp+NumberOfBytesWritten], edi
0x10009455  call    sub_1000D51F
0x1000945a  mov     esi, eax
0x1000945c  test    esi, esi
0x1000945e  jns     short loc_10009472
0x10009460  push    offset aFailedToInitia_2; "failed to initialize"
0x10009465  push    esi
0x10009466  call    sub_1000DA66
0x1000946b  pop     ecx
0x1000946c  pop     ecx
0x1000946d  jmp     loc_1000963B
0x10009472  lea     eax, [ebp+pcchValueBuf]
0x10009475  push    eax; pcchValueBuf
0x10009476  push    offset aCustomactionda; "CustomActionData"
0x1000947b  call    sub_1000E662
0x10009480  mov     esi, eax
0x10009482  test    esi, esi
0x10009484  jns     short loc_1000948D
0x10009486  push    offset aFailedToGetCus; "failed to get CustomActionData"
0x1000948b  jmp     short loc_10009465
0x1000948d  push    [ebp+pcchValueBuf]
0x10009490  push    offset aCustomactionda_0; "CustomActionData: %ls"
0x10009495  push    edi
0x10009496  call    sub_1000D9AB
0x1000949b  mov     eax, [ebp+pcchValueBuf]
0x1000949e  add     esp, 0Ch
0x100094a1  mov     dword ptr [ebp+SubStr], eax
0x100094a4  lea     eax, [ebp+hInstall]
0x100094a7  push    eax; int
0x100094a8  lea     eax, [ebp+SubStr]
0x100094ab  push    eax; SubStr
0x100094ac  call    sub_1000EF44
0x100094b1  mov     esi, eax
0x100094b3  test    esi, esi
0x100094b5  jns     short loc_100094BE
0x100094b7  push    offset aFailedToReadCo; "failed to read component bitness from c"...
0x100094bc  jmp     short loc_10009465
0x100094be  lea     eax, [ebp+lpFileName]
0x100094c1  push    eax; int
0x100094c2  lea     eax, [ebp+SubStr]
0x100094c5  push    eax; SubStr
0x100094c6  call    sub_1000EFCC
0x100094cb  mov     esi, eax
0x100094cd  test    esi, esi
0x100094cf  jns     short loc_100094D8
0x100094d1  push    offset aFailedToReadFi_0; "failed to read file name from custom ac"...
0x100094d6  jmp     short loc_10009465
0x100094d8  lea     eax, [ebp+nNumberOfBytesToWrite]
0x100094db  push    eax; int
0x100094dc  lea     eax, [ebp+lpBuffer]
0x100094df  push    eax; int
0x100094e0  lea     eax, [ebp+SubStr]
0x100094e3  push    eax; SubStr
0x100094e4  call    sub_1000EF8F
0x100094e9  mov     esi, eax
0x100094eb  test    esi, esi
0x100094ed  jns     short loc_100094F9
0x100094ef  push    offset aFailedToReadFi_1; "failed to read file contents from custo"...
0x100094f4  jmp     loc_10009465
0x100094f9  mov     eax, [ebp+hInstall]
0x100094fc  mov     [ebp+var_18], eax
0x100094ff  test    eax, eax
0x10009501  jz      short loc_1000954F
0x10009503  call    sub_10010583
0x10009508  mov     esi, eax
0x1000950a  cmp     esi, 1
0x1000950d  jnz     short loc_10009514
0x1000950f  mov     esi, 8002802Fh
0x10009514  test    esi, esi
0x10009516  jns     short loc_10009522
0x10009518  push    offset aFailedToInitia_11; "failed to initialize Wow64 API"
0x1000951d  jmp     loc_10009465
0x10009522  call    sub_10010646
0x10009527  test    eax, eax
0x10009529  jnz     short loc_1000953A
0x1000952b  mov     esi, 80004001h
0x10009530  push    offset aCustomActionWa_3; "Custom action was told to rollback a 64"...
0x10009535  jmp     loc_10009465
0x1000953a  call    sub_10010509
0x1000953f  mov     esi, eax
0x10009541  test    esi, esi
0x10009543  jns     short loc_1000954F
0x10009545  push    offset aCustomActionWa_2; "Custom action was told to rollback a 64"...
0x1000954a  jmp     loc_10009465
0x1000954f  lea     eax, [ebp+LastWriteTime]
0x10009552  push    eax; lpLastWriteTime
0x10009553  push    edi; lpLastAccessTime
0x10009554  push    edi; lpCreationTime
0x10009555  push    [ebp+lpFileName]; lpFileName
0x10009558  call    sub_1000B556
0x1000955d  mov     esi, eax
0x1000955f  test    esi, esi
0x10009561  jns     short loc_10009570
0x10009563  push    [ebp+lpFileName]
0x10009566  push    offset aFailedToGetMod_0; "Failed to get modified date of file %ls"...
0x1000956b  jmp     loc_10009632
0x10009570  push    edi; hTemplateFile
0x10009571  push    edi; dwFlagsAndAttributes
0x10009572  push    5; dwCreationDisposition
0x10009574  push    edi; lpSecurityAttributes
0x10009575  push    edi; dwShareMode
0x10009576  push    40000000h; dwDesiredAccess
0x1000957b  push    [ebp+lpFileName]; lpFileName
0x1000957e  call    ds:CreateFileW
0x10009584  mov     ebx, eax
0x10009586  cmp     ebx, 0FFFFFFFFh
0x10009589  jnz     short loc_100095C3
0x1000958b  call    ds:GetLastError
0x10009591  mov     esi, eax
0x10009593  test    esi, esi
0x10009595  jle     short loc_100095A2
0x10009597  movzx   esi, si
0x1000959a  or      esi, 80070000h
0x100095a0  test    esi, esi
0x100095a2  js      short loc_100095A9
0x100095a4  mov     esi, 80004005h
0x100095a9  push    esi
0x100095aa  push    434h
0x100095af  push    offset aDAWork1SSrcExt_6; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x100095b4  call    nullsub_1
0x100095b9  push    [ebp+lpFileName]
0x100095bc  push    offset aFailedToOpenFi; "failed to open file: %ls"
0x100095c1  jmp     short loc_10009632
0x100095c3  push    edi; lpOverlapped
0x100095c4  lea     eax, [ebp+NumberOfBytesWritten]
0x100095c7  push    eax; lpNumberOfBytesWritten
0x100095c8  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x100095cb  push    [ebp+lpBuffer]; lpBuffer
0x100095ce  push    ebx; hFile
0x100095cf  call    ds:WriteFile
0x100095d5  test    eax, eax
0x100095d7  jnz     short loc_1000960C
0x100095d9  call    ds:GetLastError
0x100095df  mov     esi, eax
0x100095e1  test    esi, esi
0x100095e3  jle     short loc_100095F0
0x100095e5  movzx   esi, si
0x100095e8  or      esi, 80070000h
0x100095ee  test    esi, esi
0x100095f0  jns     short loc_1000960C
0x100095f2  push    esi
0x100095f3  push    439h
0x100095f8  push    offset aDAWork1SSrcExt_6; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x100095fd  call    nullsub_1
0x10009602  push    [ebp+lpFileName]
0x10009605  push    offset aFailedToWriteT; "failed to write to file: %ls"
0x1000960a  jmp     short loc_10009632
0x1000960c  push    ebx; hObject
0x1000960d  call    ds:CloseHandle
0x10009613  lea     eax, [ebp+LastWriteTime]
0x10009616  or      ebx, 0FFFFFFFFh
0x10009619  push    eax; lpLastWriteTime
0x1000961a  push    edi; lpLastAccessTime
0x1000961b  push    edi; lpCreationTime
0x1000961c  push    [ebp+lpFileName]; lpFileName
0x1000961f  call    sub_1000B8D3
0x10009624  mov     esi, eax
0x10009626  test    esi, esi
0x10009628  jns     short loc_1000963B
0x1000962a  push    [ebp+lpFileName]
0x1000962d  push    offset aFailedToSetMod_0; "Failed to set modified date of file %ls"...
0x10009632  push    esi
0x10009633  call    sub_1000DA66
0x10009638  add     esp, 0Ch
0x1000963b  cmp     [ebp+pcchValueBuf], edi
0x1000963e  jz      short loc_10009648
0x10009640  push    [ebp+pcchValueBuf]
0x10009643  call    sub_1000A952
0x10009648  cmp     [ebp+lpFileName], edi
0x1000964b  jz      short loc_10009655
0x1000964d  push    [ebp+lpFileName]
0x10009650  call    sub_1000A952
0x10009655  cmp     ebx, 0FFFFFFFFh
0x10009658  jz      short loc_10009661
0x1000965a  push    ebx; hObject
0x1000965b  call    ds:CloseHandle
0x10009661  cmp     [ebp+var_18], edi
0x10009664  jz      short loc_10009670
0x10009666  call    sub_10010671
0x1000966b  call    sub_10010563
0x10009670  cmp     [ebp+lpBuffer], edi
0x10009673  jz      short loc_1000967D
0x10009675  push    [ebp+lpBuffer]; lpMem
0x10009678  call    sub_1000AEFF
0x1000967d  test    esi, esi
0x1000967f  jns     short loc_10009686
0x10009681  mov     edi, 643h
0x10009686  push    edi
0x10009687  call    sub_1000D4AE
0x1000968c  pop     edi
0x1000968d  pop     esi
0x1000968e  pop     ebx
0x1000968f  leave
0x10009690  retn    4
```
