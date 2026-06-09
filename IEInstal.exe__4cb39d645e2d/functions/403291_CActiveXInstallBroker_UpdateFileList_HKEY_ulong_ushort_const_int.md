# CActiveXInstallBroker::UpdateFileList(HKEY__ *,ulong,ushort const * *,int *)

- ea: `0x403291`
- end: `0x403514`
- name: `?UpdateFileList@CActiveXInstallBroker@@AAEJPAUHKEY__@@KPAPBGPAH@Z`
- size: `643`
- prototype: `unsigned int __thiscall(CActiveXInstallBroker *this, HKEY hKey, unsigned int, const unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x404c02`

## callees

- `0x403291`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x4033dd`
- `ADVAPI32!RegDeleteValueW` at `0x4033dd`
- `ADVAPI32!RegSetValueExW` at `0x403437`
- `ADVAPI32!RegSetValueExW` at `0x4034ab`
- `ADVAPI32!RegSetValueExW` at `0x403437`
- `ADVAPI32!RegSetValueExW` at `0x4034ab`
- `ADVAPI32!RegCloseKey` at `0x4034bb`
- `ADVAPI32!RegCloseKey` at `0x4034e6`
- `ADVAPI32!RegCloseKey` at `0x4034fb`
- `ADVAPI32!RegCloseKey` at `0x4034bb`
- `ADVAPI32!RegCloseKey` at `0x4034e6`
- `ADVAPI32!RegCloseKey` at `0x4034fb`
- `ADVAPI32!RegEnumValueW` at `0x4033a8`
- `ADVAPI32!RegEnumValueW` at `0x4033a8`
- `ADVAPI32!RegCreateKeyW` at `0x4032fd`
- `ADVAPI32!RegCreateKeyW` at `0x40333b`
- `ADVAPI32!RegCreateKeyW` at `0x40347a`
- `ADVAPI32!RegCreateKeyW` at `0x4032fd`
- `ADVAPI32!RegCreateKeyW` at `0x40333b`
- `ADVAPI32!RegCreateKeyW` at `0x40347a`
- `ADVAPI32!RegOpenKeyExW` at `0x4032e1`
- `ADVAPI32!RegOpenKeyExW` at `0x40331f`
- `ADVAPI32!RegOpenKeyExW` at `0x4032e1`
- `ADVAPI32!RegOpenKeyExW` at `0x40331f`
- `KERNEL32!GetFileAttributesW` at `0x4033c3`
- `KERNEL32!GetFileAttributesW` at `0x4033c3`
- `msvcrt!wcsrchr` at `0x403452`
- `msvcrt!wcsrchr` at `0x403452`

## pseudocode

```c
unsigned int __thiscall CActiveXInstallBroker::UpdateFileList(
        CActiveXInstallBroker *this,
        HKEY hKey,
        unsigned int a3,
        const unsigned __int16 **a4,
        int *a5)
{
  const unsigned __int16 **v5; // ebx
  unsigned int v6; // edi
  LSTATUS KeyW; // eax
  int v8; // ebx
  LSTATUS i; // eax
  DWORD v10; // eax
  unsigned int j; // esi
  wchar_t *v12; // eax
  const WCHAR *v13; // eax
  DWORD Type; // [esp+10h] [ebp-220h] BYREF
  BYTE Data[4]; // [esp+14h] [ebp-21Ch] BYREF
  HKEY v17; // [esp+18h] [ebp-218h] BYREF
  DWORD cchValueName; // [esp+1Ch] [ebp-214h] BYREF
  HKEY phkResult; // [esp+20h] [ebp-210h] BYREF
  WCHAR ValueName[260]; // [esp+24h] [ebp-20Ch] BYREF

  v5 = a4;
  v6 = 0;
  *(_DWORD *)Data = a4;
  phkResult = 0;
  v17 = 0;
  if ( RegOpenKeyExW(hKey, L"Files", 0, 0x2001Fu, &phkResult)
    && a3
    && (KeyW = RegCreateKeyW(hKey, L"Files", &phkResult)) != 0
    || RegOpenKeyExW(hKey, L"FilesFlags", 0, 0xF003Fu, &v17)
    && a3
    && (KeyW = RegCreateKeyW(hKey, L"FilesFlags", &v17)) != 0 )
  {
LABEL_26:
    v6 = (unsigned __int16)KeyW | 0x80070000;
    if ( KeyW <= 0 )
      v6 = KeyW;
  }
  else
  {
    if ( phkResult )
    {
      Type = 1;
      memset(ValueName, 0, sizeof(ValueName));
      cchValueName = 260;
      v8 = 1;
      for ( i = RegEnumValueW(phkResult, 0, ValueName, &cchValueName, 0, &Type, 0, 0);
            !i;
            i = RegEnumValueW(phkResult, v10, ValueName, &cchValueName, 0, &Type, 0, 0) )
      {
        cchValueName = 260;
        if ( GetFileAttributesW(ValueName) == -1 )
        {
          v8 = 0;
          RegDeleteValueW(phkResult, ValueName);
        }
        v10 = v8++;
      }
      v5 = *(const unsigned __int16 ***)Data;
    }
    for ( j = 0; j < a3; ++j )
    {
      if ( v5[j] )
      {
        KeyW = RegSetValueExW(phkResult, v5[j], 0, 1u, (const BYTE *)&::Data, 1u);
        if ( KeyW )
          goto LABEL_26;
        if ( a5 )
        {
          v12 = _wcsrchr(v5[j], 0x5Cu);
          if ( v12 )
            v13 = v12 + 1;
          else
            v13 = v5[j];
          cchValueName = 0;
          KeyW = RegCreateKeyW(v17, v13, (PHKEY)&cchValueName);
          if ( KeyW )
            goto LABEL_26;
          *(_DWORD *)Data = a5[j];
          KeyW = RegSetValueExW((HKEY)cchValueName, L"RedirectToHKCU", 0, 4u, Data, 4u);
          if ( KeyW )
            goto LABEL_26;
          RegCloseKey((HKEY)cchValueName);
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v17 )
    RegCloseKey(v17);
  return v6;
}

```

## disassembly

```asm
0x403291  mov     edi, edi
0x403293  push    ebp
0x403294  mov     ebp, esp
0x403296  sub     esp, 224h
0x40329c  mov     eax, ___security_cookie
0x4032a1  xor     eax, ebp
0x4032a3  mov     [ebp+var_4], eax
0x4032a6  mov     eax, [ebp+arg_C]
0x4032a9  xor     ecx, ecx
0x4032ab  push    ebx
0x4032ac  mov     ebx, [ebp+arg_8]
0x4032af  push    esi
0x4032b0  mov     esi, [ebp+hKey]
0x4032b3  push    edi
0x4032b4  mov     [ebp+var_224], eax
0x4032ba  mov     edi, ecx
0x4032bc  lea     eax, [ebp+phkResult]
0x4032c2  mov     dword ptr [ebp+Data], ebx
0x4032c8  push    eax; phkResult
0x4032c9  push    2001Fh; samDesired
0x4032ce  push    ecx; ulOptions
0x4032cf  push    offset aFiles; "Files"
0x4032d4  push    esi; hKey
0x4032d5  mov     [ebp+phkResult], ecx
0x4032db  mov     [ebp+var_218], ecx
0x4032e1  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x4032e7  test    eax, eax
0x4032e9  jz      short loc_40330B
0x4032eb  cmp     [ebp+arg_4], edi
0x4032ee  jz      short loc_40330B
0x4032f0  lea     eax, [ebp+phkResult]
0x4032f6  push    eax; phkResult
0x4032f7  push    offset aFiles; "Files"
0x4032fc  push    esi; hKey
0x4032fd  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x403303  test    eax, eax
0x403305  jnz     loc_4034CD
0x40330b  lea     eax, [ebp+var_218]
0x403311  push    eax; phkResult
0x403312  push    0F003Fh; samDesired
0x403317  push    0; ulOptions
0x403319  push    offset aFilesflags; "FilesFlags"
0x40331e  push    esi; hKey
0x40331f  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x403325  test    eax, eax
0x403327  jz      short loc_403349
0x403329  cmp     [ebp+arg_4], edi
0x40332c  jz      short loc_403349
0x40332e  lea     eax, [ebp+var_218]
0x403334  push    eax; phkResult
0x403335  push    offset aFilesflags; "FilesFlags"
0x40333a  push    esi; hKey
0x40333b  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x403341  test    eax, eax
0x403343  jnz     loc_4034CD
0x403349  mov     esi, [ebp+phkResult]
0x40334f  test    esi, esi
0x403351  jz      loc_40340F
0x403357  xor     eax, eax
0x403359  mov     [ebp+Type], 1
0x403363  push    206h; Size
0x403368  push    eax; Val
0x403369  mov     [ebp+ValueName], ax
0x403370  lea     eax, [ebp+var_20A]
0x403376  push    eax; void *
0x403377  mov     [ebp+cchValueName], 104h
0x403381  call    _memset
0x403386  add     esp, 0Ch
0x403389  lea     eax, [ebp+Type]
0x40338f  xor     ebx, ebx
0x403391  inc     ebx
0x403392  xor     ecx, ecx
0x403394  push    ecx; lpcbData
0x403395  push    ecx; lpData
0x403396  push    eax; lpType
0x403397  push    ecx; lpReserved
0x403398  lea     eax, [ebp+cchValueName]
0x40339e  push    eax; lpcchValueName
0x40339f  lea     eax, [ebp+ValueName]
0x4033a5  push    eax; lpValueName
0x4033a6  push    ecx; dwIndex
0x4033a7  push    esi; hKey
0x4033a8  call    ds:__imp__RegEnumValueW@32; RegEnumValueW(x,x,x,x,x,x,x,x)
0x4033ae  test    eax, eax
0x4033b0  jnz     short loc_403409
0x4033b2  lea     eax, [ebp+ValueName]
0x4033b8  mov     [ebp+cchValueName], 104h
0x4033c2  push    eax; lpFileName
0x4033c3  call    ds:__imp__GetFileAttributesW@4; GetFileAttributesW(x)
0x4033c9  cmp     eax, 0FFFFFFFFh
0x4033cc  jnz     short loc_4033E3
0x4033ce  lea     eax, [ebp+ValueName]
0x4033d4  xor     ebx, ebx
0x4033d6  push    eax; lpValueName
0x4033d7  push    [ebp+phkResult]; hKey
0x4033dd  call    ds:__imp__RegDeleteValueW@8; RegDeleteValueW(x,x)
0x4033e3  mov     eax, ebx
0x4033e5  lea     ecx, [ebp+Type]
0x4033eb  inc     ebx
0x4033ec  xor     edx, edx
0x4033ee  push    edx
0x4033ef  push    edx
0x4033f0  push    ecx
0x4033f1  push    edx
0x4033f2  lea     ecx, [ebp+cchValueName]
0x4033f8  push    ecx
0x4033f9  lea     ecx, [ebp+ValueName]
0x4033ff  push    ecx
0x403400  push    eax
0x403401  push    [ebp+phkResult]
0x403407  jmp     short loc_4033A8
0x403409  mov     ebx, dword ptr [ebp+Data]
0x40340f  xor     esi, esi
0x403411  cmp     [ebp+arg_4], esi
0x403414  jbe     loc_4034DB
0x40341a  cmp     [ebx+esi*4], edi
0x40341d  jz      loc_4034C1
0x403423  push    1; cbData
0x403425  push    offset Data; lpData
0x40342a  push    1; dwType
0x40342c  push    0; Reserved
0x40342e  push    dword ptr [ebx+esi*4]; lpValueName
0x403431  push    [ebp+phkResult]; hKey
0x403437  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x40343d  test    eax, eax
0x40343f  jnz     loc_4034CD
0x403445  cmp     [ebp+var_224], edi
0x40344b  jz      short loc_4034C1
0x40344d  push    5Ch ; '\'; Ch
0x40344f  push    dword ptr [ebx+esi*4]; Str
0x403452  call    ds:__imp__wcsrchr
0x403458  pop     ecx
0x403459  pop     ecx
0x40345a  test    eax, eax
0x40345c  jz      short loc_403463
0x40345e  add     eax, 2
0x403461  jmp     short loc_403466
0x403463  mov     eax, [ebx+esi*4]
0x403466  lea     ecx, [ebp+cchValueName]
0x40346c  mov     [ebp+cchValueName], edi
0x403472  push    ecx; phkResult
0x403473  push    eax; lpSubKey
0x403474  push    [ebp+var_218]; hKey
0x40347a  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x403480  test    eax, eax
0x403482  jnz     short loc_4034CD
0x403484  mov     eax, [ebp+var_224]
0x40348a  push    4; cbData
0x40348c  mov     eax, [eax+esi*4]
0x40348f  mov     dword ptr [ebp+Data], eax
0x403495  lea     eax, [ebp+Data]
0x40349b  push    eax; lpData
0x40349c  push    4; dwType
0x40349e  push    0; Reserved
0x4034a0  push    offset aRedirecttohkcu; "RedirectToHKCU"
0x4034a5  push    [ebp+cchValueName]; hKey
0x4034ab  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x4034b1  test    eax, eax
0x4034b3  jnz     short loc_4034CD
0x4034b5  push    [ebp+cchValueName]; hKey
0x4034bb  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4034c1  inc     esi
0x4034c2  cmp     esi, [ebp+arg_4]
0x4034c5  jb      loc_40341A
0x4034cb  jmp     short loc_4034DB
0x4034cd  movzx   edi, ax
0x4034d0  or      edi, 80070000h
0x4034d6  test    eax, eax
0x4034d8  cmovle  edi, eax
0x4034db  mov     esi, [ebp+phkResult]
0x4034e1  test    esi, esi
0x4034e3  jz      short loc_4034EC
0x4034e5  push    esi; hKey
0x4034e6  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4034ec  cmp     [ebp+var_218], 0
0x4034f3  jz      short loc_403501
0x4034f5  push    [ebp+var_218]; hKey
0x4034fb  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x403501  mov     ecx, [ebp+var_4]
0x403504  mov     eax, edi
0x403506  pop     edi
0x403507  pop     esi
0x403508  xor     ecx, ebp; StackCookie
0x40350a  pop     ebx
0x40350b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x403510  leave
0x403511  retn    10h
```
