# CActiveXInstallBroker::RegisterDllFile2Helper(ushort *,ushort *,int,int)

- ea: `0x4044ae`
- end: `0x404800`
- name: `?RegisterDllFile2Helper@CActiveXInstallBroker@@AAEJPAG0HH@Z`
- size: `850`
- prototype: `int __thiscall(const unsigned __int16 **this, unsigned __int16 *, size_t cchDest, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x404460`
- `0x404806`

## callees

- `0x402dc4`
- `0x402df9`
- `0x402eb9`
- `0x402ed3`
- `0x403094`
- `0x4044ae`
- `0x408301`
- `0x40838e`
- `0x408480`
- `0x408a2f`
- `0x409dbc`
- `0x409e01`
- `0x409f13`
- `0x40cb60`
- `0x40d1d0`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x404778`
- `ADVAPI32!RegSetValueExW` at `0x404778`
- `ADVAPI32!RegCreateKeyExW` at `0x40463a`
- `ADVAPI32!RegCreateKeyExW` at `0x40463a`
- `ADVAPI32!RegCloseKey` at `0x4046bc`
- `ADVAPI32!RegCloseKey` at `0x4046bc`
- `ADVAPI32!RegQueryValueExW` at `0x40468e`
- `ADVAPI32!RegQueryValueExW` at `0x40468e`
- `ADVAPI32!RegOverridePredefKey` at `0x4046e4`
- `ADVAPI32!RegOverridePredefKey` at `0x4046f0`
- `ADVAPI32!RegOverridePredefKey` at `0x4046e4`
- `ADVAPI32!RegOverridePredefKey` at `0x4046f0`
- `KERNEL32!GetProcAddress` at `0x4047ae`
- `KERNEL32!GetProcAddress` at `0x4047ae`
- `KERNEL32!FreeLibrary` at `0x4046c7`
- `KERNEL32!FreeLibrary` at `0x4046c7`
- `KERNEL32!LoadLibraryExW` at `0x404791`
- `KERNEL32!LoadLibraryExW` at `0x404791`
- `KERNEL32!GetLastError` at `0x40479d`
- `KERNEL32!GetLastError` at `0x40479d`

## string_xrefs

- `0x40471c`: `rundll32.exe IEAdvpack.dll,RegisterOCX %s`
- `0x4047a8`: `DllRegisterServer`

## pseudocode

```c
int __thiscall CActiveXInstallBroker::RegisterDllFile2Helper(
        const unsigned __int16 **this,
        unsigned __int16 *a2,
        size_t cchDest,
        int a4,
        int a5)
{
  HMODULE v5; // edi
  int IsAuthorized; // esi
  int v8; // eax
  int v9; // ecx
  int LastError; // eax
  HMODULE Library; // eax
  HRESULT (__stdcall *DllRegisterServer)(); // esi
  int v14; // eax
  HMODULE v15; // [esp-4h] [ebp-848h]
  unsigned int v16; // [esp+0h] [ebp-844h]
  const unsigned __int16 *v17; // [esp+0h] [ebp-844h]
  const unsigned __int16 *v18; // [esp+4h] [ebp-840h]
  DWORD dwDisposition; // [esp+Ch] [ebp-838h] BYREF
  int v20; // [esp+10h] [ebp-834h]
  HKEY hKey; // [esp+14h] [ebp-830h] BYREF
  HKEY phkResult; // [esp+18h] [ebp-82Ch] BYREF
  HMODULE v23; // [esp+1Ch] [ebp-828h]
  wchar_t Data[520]; // [esp+20h] [ebp-824h] BYREF
  WCHAR ValueName[260]; // [esp+430h] [ebp-414h] BYREF
  WCHAR LibFileName[260]; // [esp+638h] [ebp-20Ch] BYREF

  v5 = 0;
  v20 = -2147467259;
  phkResult = 0;
  v23 = 0;
  if ( !CLock::Lock((CLock *)this) )
  {
    IsAuthorized = -2147024882;
    goto LABEL_30;
  }
  if ( (int)this[7] < 6 )
  {
    IsAuthorized = -2147019873;
    goto LABEL_30;
  }
  if ( !a2 || !cchDest )
    goto LABEL_49;
  v8 = wcscmp(a2, this[9]);
  if ( v8 )
    v8 = v8 < 0 ? -1 : 1;
  if ( v8 )
    goto LABEL_10;
  if ( StringCchCopyW(cchDest, v16, v18) < 0
    || (AxiAdjustSlashToBackslashW((__int16 *)LibFileName), AxiPreScanPathW(LibFileName) < 0)
    || VerifyFileHasExtensionW(v17) < 0 )
  {
LABEL_49:
    IsAuthorized = -2147024809;
    goto LABEL_30;
  }
  IsAuthorized = CActiveXInstallBroker::FileIsAuthorized((CActiveXInstallBroker *)this, LibFileName, v9);
  if ( IsAuthorized < 0 )
    goto LABEL_30;
  if ( !this[21] && !ContainingPathIsTamperProof(LibFileName) )
  {
LABEL_10:
    IsAuthorized = -2147024891;
    goto LABEL_30;
  }
  if ( a5 )
  {
    memset(ValueName, 0, sizeof(ValueName));
    hKey = 0;
    IsAuthorized = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
    if ( IsAuthorized )
      goto LABEL_30;
    LastError = RegCreateKeyExW(
                  hKey,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
                  0,
                  0,
                  0,
                  0x20006u,
                  0,
                  &phkResult,
                  &dwDisposition);
    if ( LastError )
      goto LABEL_20;
    while ( 1 )
    {
      v15 = v5;
      v5 = (HMODULE)((char *)v5 + 1);
      IsAuthorized = StringCchPrintfW(ValueName, 0x104u, (wchar_t *)L"ICDRegOCX%u", v15);
      if ( IsAuthorized < 0 )
        goto LABEL_29;
      if ( RegQueryValueExW(phkResult, ValueName, 0, 0, 0, &dwDisposition) )
        break;
      if ( !v5 )
        goto LABEL_28;
    }
    if ( !v5 )
    {
LABEL_28:
      IsAuthorized = -2147023883;
LABEL_29:
      v5 = v23;
      goto LABEL_30;
    }
    IsAuthorized = StringCchPrintfW(Data, 0x207u, (wchar_t *)L"rundll32.exe IEAdvpack.dll,RegisterOCX %s", LibFileName);
    if ( IsAuthorized < 0 )
      goto LABEL_29;
    v5 = 0;
    LastError = RegSetValueExW(phkResult, ValueName, 0, 1u, (const BYTE *)Data, 2 * wcslen(Data) + 2);
    if ( LastError )
    {
LABEL_20:
      IsAuthorized = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        IsAuthorized = LastError;
      goto LABEL_30;
    }
    goto LABEL_48;
  }
  Library = LoadLibraryExW(LibFileName, 0, 8u);
  v5 = Library;
  if ( !Library || (DllRegisterServer = GetProcAddress(Library, "DllRegisterServer")) == 0 )
  {
    LastError = GetLastError();
    goto LABEL_20;
  }
  if ( a4 )
  {
    v14 = EnableRedirectToHKCU();
    v20 = v14;
    if ( v14 )
    {
      IsAuthorized = v14;
      goto LABEL_30;
    }
  }
  IsAuthorized = ((int (__thiscall *)(HRESULT (__stdcall *)()))DllRegisterServer)(DllRegisterServer);
  if ( IsAuthorized >= 0 )
LABEL_48:
    this[7] = (const unsigned __int16 *)8;
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    FreeLibrary(v5);
  if ( a4 && !v20 )
  {
    RegOverridePredefKey(HKEY_CLASSES_ROOT, 0);
    RegOverridePredefKey(HKEY_LOCAL_MACHINE, 0);
    DestroyDetoursRedirectToHKCU();
  }
  CLock::Unlock((CLock *)this);
  return IsAuthorized;
}

```

## disassembly

```asm
0x4044ae  mov     edi, edi
0x4044b0  push    ebp
0x4044b1  mov     ebp, esp
0x4044b3  sub     esp, 838h
0x4044b9  mov     eax, ___security_cookie
0x4044be  xor     eax, ebp
0x4044c0  mov     [ebp+var_4], eax
0x4044c3  push    ebx
0x4044c4  push    esi; unsigned __int16 *
0x4044c5  mov     esi, [ebp+cchDest]
0x4044c8  xor     eax, eax
0x4044ca  push    edi; HKEY *
0x4044cb  mov     edi, eax
0x4044cd  mov     [ebp+var_834], 80004005h
0x4044d7  mov     ebx, ecx
0x4044d9  mov     [ebp+phkResult], eax
0x4044df  mov     [ebp+var_828], edi
0x4044e5  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x4044ea  test    eax, eax
0x4044ec  jnz     short loc_4044F8
0x4044ee  mov     esi, 8007000Eh
0x4044f3  jmp     loc_4046AD
0x4044f8  cmp     dword ptr [ebx+1Ch], 6
0x4044fc  jge     short loc_404508
0x4044fe  mov     esi, 8007139Fh
0x404503  jmp     loc_4046AD
0x404508  mov     eax, [ebp+arg_0]
0x40450b  test    eax, eax
0x40450d  jz      loc_4047F6
0x404513  test    esi, esi
0x404515  jz      loc_4047F6
0x40451b  mov     ecx, [ebx+24h]
0x40451e  mov     dx, [eax]
0x404521  cmp     dx, [ecx]
0x404524  jnz     short loc_404544
0x404526  test    dx, dx
0x404529  jz      short loc_404540
0x40452b  mov     dx, [eax+2]
0x40452f  cmp     dx, [ecx+2]
0x404533  jnz     short loc_404544
0x404535  add     eax, 4
0x404538  add     ecx, 4
0x40453b  test    dx, dx
0x40453e  jnz     short loc_40451E
0x404540  xor     eax, eax
0x404542  jmp     short loc_404549
0x404544  sbb     eax, eax
0x404546  or      eax, 1
0x404549  test    eax, eax
0x40454b  jz      short loc_404557
0x40454d  mov     esi, 80070005h
0x404552  jmp     loc_4046AD
0x404557  push    esi; cchDest
0x404558  mov     edx, 104h
0x40455d  lea     ecx, [ebp+LibFileName]
0x404563  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x404568  test    eax, eax
0x40456a  js      loc_4047F6
0x404570  lea     ecx, [ebp+LibFileName]
0x404576  call    ?AxiAdjustSlashToBackslashW@@YGXPAG@Z; AxiAdjustSlashToBackslashW(ushort *)
0x40457b  lea     ecx, [ebp+LibFileName]
0x404581  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x404586  test    eax, eax
0x404588  js      loc_4047F6
0x40458e  lea     ecx, [ebp+LibFileName]
0x404594  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x404599  test    eax, eax
0x40459b  js      loc_4047F6
0x4045a1  push    ecx; int
0x4045a2  lea     eax, [ebp+LibFileName]
0x4045a8  mov     ecx, ebx; this
0x4045aa  push    eax; unsigned __int16 *
0x4045ab  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x4045b0  mov     esi, eax
0x4045b2  test    esi, esi
0x4045b4  js      loc_4046AD
0x4045ba  xor     esi, esi
0x4045bc  cmp     [ebx+54h], esi
0x4045bf  jnz     short loc_4045D4
0x4045c1  lea     ecx, [ebp+LibFileName]
0x4045c7  call    ?ContainingPathIsTamperProof@@YGHPBG@Z; ContainingPathIsTamperProof(ushort const *)
0x4045cc  test    eax, eax
0x4045ce  jz      loc_40454D
0x4045d4  cmp     [ebp+arg_C], esi
0x4045d7  jz      loc_404787
0x4045dd  xor     eax, eax
0x4045df  push    206h; Size
0x4045e4  mov     [ebp+ValueName], ax
0x4045eb  lea     eax, [ebp+var_412]
0x4045f1  push    esi; Val
0x4045f2  push    eax; void *
0x4045f3  call    _memset
0x4045f8  add     esp, 0Ch
0x4045fb  mov     [ebp+hKey], esi
0x404601  lea     ecx, [ebp+hKey]
0x404607  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YGJPAPAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x40460c  mov     esi, eax
0x40460e  test    esi, esi
0x404610  jnz     loc_4046AD
0x404616  lea     eax, [ebp+dwDisposition]
0x40461c  push    eax; lpdwDisposition
0x40461d  lea     eax, [ebp+phkResult]
0x404623  push    eax; phkResult
0x404624  xor     eax, eax
0x404626  push    eax; lpSecurityAttributes
0x404627  push    20006h; samDesired
0x40462c  push    eax; dwOptions
0x40462d  push    eax; lpClass
0x40462e  push    eax; Reserved
0x40462f  push    offset aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x404634  push    [ebp+hKey]; hKey
0x40463a  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x404640  test    eax, eax
0x404642  jz      short loc_404654
0x404644  movzx   esi, ax
0x404647  or      esi, 80070000h
0x40464d  test    eax, eax
0x40464f  cmovle  esi, eax
0x404652  jmp     short loc_4046AD
0x404654  push    edi
0x404655  push    offset aIcdregocxU; "ICDRegOCX%u"
0x40465a  lea     eax, [ebp+ValueName]
0x404660  inc     edi
0x404661  push    104h; unsigned int
0x404666  push    eax; Buffer
0x404667  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x40466c  mov     esi, eax
0x40466e  add     esp, 10h
0x404671  test    esi, esi
0x404673  js      short loc_4046A7
0x404675  lea     eax, [ebp+dwDisposition]
0x40467b  push    eax; lpcbData
0x40467c  xor     eax, eax
0x40467e  push    eax; lpData
0x40467f  push    eax; lpType
0x404680  push    eax; lpReserved
0x404681  lea     eax, [ebp+ValueName]
0x404687  push    eax; lpValueName
0x404688  push    [ebp+phkResult]; hKey
0x40468e  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x404694  test    eax, eax
0x404696  jnz     short loc_40469E
0x404698  test    edi, edi
0x40469a  jnz     short loc_404654
0x40469c  jmp     short loc_4046A2
0x40469e  test    edi, edi
0x4046a0  jnz     short loc_404715
0x4046a2  mov     esi, 800703F5h
0x4046a7  mov     edi, [ebp+var_828]
0x4046ad  cmp     [ebp+phkResult], 0
0x4046b4  jz      short loc_4046C2
0x4046b6  push    [ebp+phkResult]; hKey
0x4046bc  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4046c2  test    edi, edi
0x4046c4  jz      short loc_4046CD
0x4046c6  push    edi; hLibModule
0x4046c7  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x4046cd  cmp     [ebp+arg_8], 0
0x4046d1  jz      short loc_4046FB
0x4046d3  cmp     [ebp+var_834], 0
0x4046da  jnz     short loc_4046FB
0x4046dc  xor     edi, edi
0x4046de  push    edi; hNewHKey
0x4046df  push    80000000h; hKey
0x4046e4  call    ds:__imp__RegOverridePredefKey@8; RegOverridePredefKey(x,x)
0x4046ea  push    edi; hNewHKey
0x4046eb  push    80000002h; hKey
0x4046f0  call    ds:__imp__RegOverridePredefKey@8; RegOverridePredefKey(x,x)
0x4046f6  call    ?DestroyDetoursRedirectToHKCU@@YGJXZ; DestroyDetoursRedirectToHKCU(void)
0x4046fb  mov     ecx, ebx; this
0x4046fd  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x404702  mov     ecx, [ebp+var_4]
0x404705  mov     eax, esi
0x404707  pop     edi
0x404708  pop     esi
0x404709  xor     ecx, ebp; StackCookie
0x40470b  pop     ebx
0x40470c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x404711  leave
0x404712  retn    10h
0x404715  lea     eax, [ebp+LibFileName]
0x40471b  push    eax
0x40471c  push    offset aRundll32ExeIea; "rundll32.exe IEAdvpack.dll,RegisterOCX "...
0x404721  lea     eax, [ebp+Data]
0x404727  push    207h; unsigned int
0x40472c  push    eax; Buffer
0x40472d  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x404732  mov     esi, eax
0x404734  add     esp, 10h
0x404737  test    esi, esi
0x404739  js      loc_4046A7
0x40473f  lea     ecx, [ebp+Data]
0x404745  xor     edi, edi
0x404747  lea     edx, [ecx+2]
0x40474a  mov     ax, [ecx]
0x40474d  add     ecx, 2
0x404750  cmp     ax, di
0x404753  jnz     short loc_40474A
0x404755  sub     ecx, edx
0x404757  sar     ecx, 1
0x404759  lea     eax, ds:2[ecx*2]
0x404760  push    eax; cbData
0x404761  lea     eax, [ebp+Data]
0x404767  push    eax; lpData
0x404768  push    1; dwType
0x40476a  push    edi; Reserved
0x40476b  lea     eax, [ebp+ValueName]
0x404771  push    eax; lpValueName
0x404772  push    [ebp+phkResult]; hKey
0x404778  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x40477e  test    eax, eax
0x404780  jz      short loc_4047EA
0x404782  jmp     loc_404644
0x404787  push    8; dwFlags
0x404789  push    esi; hFile
0x40478a  lea     eax, [ebp+LibFileName]
0x404790  push    eax; lpLibFileName
0x404791  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x404797  mov     edi, eax
0x404799  test    edi, edi
0x40479b  jnz     short loc_4047A8
0x40479d  call    ds:__imp__GetLastError@0; GetLastError()
0x4047a3  jmp     loc_404644
0x4047a8  push    offset aDllregisterser; "DllRegisterServer"
0x4047ad  push    edi; hModule
0x4047ae  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x4047b4  mov     esi, eax
0x4047b6  test    esi, esi
0x4047b8  jz      short loc_40479D
0x4047ba  cmp     [ebp+arg_8], 0
0x4047be  jz      short loc_4047D6
0x4047c0  call    _EnableRedirectToHKCU@0; EnableRedirectToHKCU()
0x4047c5  mov     [ebp+var_834], eax
0x4047cb  test    eax, eax
0x4047cd  jz      short loc_4047D6
0x4047cf  mov     esi, eax
0x4047d1  jmp     loc_4046AD
0x4047d6  mov     ecx, esi
0x4047d8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x4047de  call    esi
0x4047e0  mov     esi, eax
0x4047e2  test    esi, esi
0x4047e4  js      loc_4046AD
0x4047ea  mov     dword ptr [ebx+1Ch], 8
0x4047f1  jmp     loc_4046AD
0x4047f6  mov     esi, 80070057h
0x4047fb  jmp     loc_4046AD
```
