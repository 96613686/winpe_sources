# CActiveXInstallBroker::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)

- ea: `0x404c02`
- end: `0x4052fe`
- name: `?UpdateDistributionUnit2@CActiveXInstallBroker@@QAGJPAGPBG1KPAK1H11J111KPAPBGPAHK3K33@Z`
- size: `1788`
- prototype: `int __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, const WCHAR *this, BYTE *lpData, const unsigned __int16 *Data, BYTE *, DWORD, LPDWORD lpReserved, const unsigned __int16 *, const WCHAR *, const unsigned __int16 *, BYTE *, BYTE *, BYTE *, const unsigned __int16 *, unsigned __int16 **, int *, const unsigned __int16 **, int *, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x405f20`
- `0x405f90`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x4031fd`
- `0x403291`
- `0x404c02`
- `0x409dbc`
- `0x40cb60`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x404f5d`
- `ADVAPI32!RegDeleteValueW` at `0x404fd7`
- `ADVAPI32!RegDeleteValueW` at `0x404f5d`
- `ADVAPI32!RegDeleteValueW` at `0x404fd7`
- `ADVAPI32!RegSetValueExW` at `0x404de2`
- `ADVAPI32!RegSetValueExW` at `0x404e05`
- `ADVAPI32!RegSetValueExW` at `0x404e28`
- `ADVAPI32!RegSetValueExW` at `0x404e4f`
- `ADVAPI32!RegSetValueExW` at `0x404ed1`
- `ADVAPI32!RegSetValueExW` at `0x405013`
- `ADVAPI32!RegSetValueExW` at `0x40505b`
- `ADVAPI32!RegSetValueExW` at `0x405114`
- `ADVAPI32!RegSetValueExW` at `0x405155`
- `ADVAPI32!RegSetValueExW` at `0x4051a2`
- `ADVAPI32!RegSetValueExW` at `0x4051e5`
- `ADVAPI32!RegSetValueExW` at `0x404de2`
- `ADVAPI32!RegSetValueExW` at `0x404e05`
- `ADVAPI32!RegSetValueExW` at `0x404e28`
- `ADVAPI32!RegSetValueExW` at `0x404e4f`
- `ADVAPI32!RegSetValueExW` at `0x404ed1`
- `ADVAPI32!RegSetValueExW` at `0x405013`
- `ADVAPI32!RegSetValueExW` at `0x40505b`
- `ADVAPI32!RegSetValueExW` at `0x405114`
- `ADVAPI32!RegSetValueExW` at `0x405155`
- `ADVAPI32!RegSetValueExW` at `0x4051a2`
- `ADVAPI32!RegSetValueExW` at `0x4051e5`
- `ADVAPI32!RegCloseKey` at `0x405286`
- `ADVAPI32!RegCloseKey` at `0x40529b`
- `ADVAPI32!RegCloseKey` at `0x4052b0`
- `ADVAPI32!RegCloseKey` at `0x4052c5`
- `ADVAPI32!RegCloseKey` at `0x4052da`
- `ADVAPI32!RegCloseKey` at `0x405286`
- `ADVAPI32!RegCloseKey` at `0x40529b`
- `ADVAPI32!RegCloseKey` at `0x4052b0`
- `ADVAPI32!RegCloseKey` at `0x4052c5`
- `ADVAPI32!RegCloseKey` at `0x4052da`
- `ADVAPI32!RegQueryValueExW` at `0x404f1b`
- `ADVAPI32!RegQueryValueExW` at `0x404f95`
- `ADVAPI32!RegQueryValueExW` at `0x404f1b`
- `ADVAPI32!RegQueryValueExW` at `0x404f95`
- `ADVAPI32!RegCreateKeyW` at `0x404d6c`
- `ADVAPI32!RegCreateKeyW` at `0x404da7`
- `ADVAPI32!RegCreateKeyW` at `0x404e8e`
- `ADVAPI32!RegCreateKeyW` at `0x40509b`
- `ADVAPI32!RegCreateKeyW` at `0x4050f2`
- `ADVAPI32!RegCreateKeyW` at `0x405220`
- `ADVAPI32!RegCreateKeyW` at `0x404d6c`
- `ADVAPI32!RegCreateKeyW` at `0x404da7`
- `ADVAPI32!RegCreateKeyW` at `0x404e8e`
- `ADVAPI32!RegCreateKeyW` at `0x40509b`
- `ADVAPI32!RegCreateKeyW` at `0x4050f2`
- `ADVAPI32!RegCreateKeyW` at `0x405220`
- `ADVAPI32!RegOpenKeyExW` at `0x404d50`
- `ADVAPI32!RegOpenKeyExW` at `0x404d8f`
- `ADVAPI32!RegOpenKeyExW` at `0x404e76`
- `ADVAPI32!RegOpenKeyExW` at `0x405083`
- `ADVAPI32!RegOpenKeyExW` at `0x4050d6`
- `ADVAPI32!RegOpenKeyExW` at `0x405208`
- `ADVAPI32!RegOpenKeyExW` at `0x404d50`
- `ADVAPI32!RegOpenKeyExW` at `0x404d8f`
- `ADVAPI32!RegOpenKeyExW` at `0x404e76`
- `ADVAPI32!RegOpenKeyExW` at `0x405083`
- `ADVAPI32!RegOpenKeyExW` at `0x4050d6`
- `ADVAPI32!RegOpenKeyExW` at `0x405208`
- `ADVAPI32!RegDeleteKeyW` at `0x4050b4`
- `ADVAPI32!RegDeleteKeyW` at `0x4050b4`
- `KERNEL32!lstrcmpiW` at `0x404f37`
- `KERNEL32!lstrcmpiW` at `0x404fb1`
- `KERNEL32!lstrcmpiW` at `0x404f37`
- `KERNEL32!lstrcmpiW` at `0x404fb1`
- `KERNEL32!DeleteFileW` at `0x404f48`
- `KERNEL32!DeleteFileW` at `0x404fc2`
- `KERNEL32!DeleteFileW` at `0x404f48`
- `KERNEL32!DeleteFileW` at `0x404fc2`

## string_xrefs

- `0x404dfa`: `SystemComponent`
- `0x404e1d`: `Installer`
- `0x40506f`: `InstalledVersion`
- `0x404e15`: `MSICD`
- `0x405109`: `Precache`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::UpdateDistributionUnit2@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        const WCHAR *this,
        BYTE *lpData,
        const unsigned __int16 *Data,
        BYTE *a6,
        DWORD a7,
        LPDWORD lpReserved,
        const unsigned __int16 *a9,
        const WCHAR *a10,
        const unsigned __int16 *a11,
        BYTE *a12,
        BYTE *a13,
        BYTE *a14,
        const unsigned __int16 *a15,
        unsigned __int16 **a16,
        int *a17,
        const unsigned __int16 **a18,
        int *a19,
        unsigned int a20,
        const unsigned __int16 **a21,
        unsigned int a22,
        const unsigned __int16 **a23,
        const unsigned __int16 **a24)
{
  int RegistrationRootKeyFromIntegrityLevel; // esi
  int v26; // eax
  LSTATUS v27; // eax
  unsigned int *v28; // edi
  const WCHAR *v29; // ecx
  __int16 v30; // ax
  const WCHAR *v31; // ecx
  __int16 v32; // ax
  char *v33; // ecx
  __int16 v34; // ax
  CActiveXInstallBroker *v35; // ecx
  CActiveXInstallBroker *v36; // ecx
  unsigned __int16 **v38; // [esp+Ch] [ebp-254h]
  unsigned __int16 **v39; // [esp+10h] [ebp-250h]
  int *v40; // [esp+14h] [ebp-24Ch]
  BYTE *v41; // [esp+18h] [ebp-248h]
  BYTE *v42; // [esp+1Ch] [ebp-244h]
  BYTE *v43; // [esp+20h] [ebp-240h]
  BYTE *v44; // [esp+24h] [ebp-23Ch]
  const WCHAR *lpString1; // [esp+2Ch] [ebp-234h]
  const WCHAR *v47; // [esp+30h] [ebp-230h]
  DWORD Type; // [esp+34h] [ebp-22Ch] BYREF
  int v49; // [esp+38h] [ebp-228h]
  HKEY phkResult; // [esp+3Ch] [ebp-224h] BYREF
  HKEY v51; // [esp+40h] [ebp-220h] BYREF
  HKEY hKey; // [esp+44h] [ebp-21Ch] BYREF
  HKEY v53; // [esp+48h] [ebp-218h] BYREF
  HKEY v54; // [esp+4Ch] [ebp-214h] BYREF
  HKEY v55; // [esp+50h] [ebp-210h] BYREF
  WCHAR v56[259]; // [esp+54h] [ebp-20Ch] BYREF
  __int16 v57; // [esp+25Ah] [ebp-6h]

  v44 = a6;
  Type = a7;
  lpString1 = a9;
  v47 = a10;
  v43 = a12;
  v42 = a13;
  v41 = a14;
  v39 = a16;
  v40 = a17;
  v38 = (unsigned __int16 **)a19;
  v49 = 0;
  hKey = 0;
  phkResult = 0;
  v55 = 0;
  v54 = 0;
  v51 = 0;
  v53 = 0;
  if ( !CLock::Lock((CLock *)a2) )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024882;
    goto LABEL_67;
  }
  if ( *(int *)(a2 + 28) < 7 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147019873;
    goto LABEL_67;
  }
  if ( !a1 || !this )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024809;
    goto LABEL_67;
  }
  v26 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
  if ( v26 )
    v26 = v26 < 0 ? -1 : 1;
  if ( v26 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024891;
    goto LABEL_67;
  }
  RegistrationRootKeyFromIntegrityLevel = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
  if ( !RegistrationRootKeyFromIntegrityLevel )
  {
    if ( RegOpenKeyExW(hKey, L"Software\\Microsoft\\Code Store Database\\Distribution Units", 0, 0x2001Fu, &phkResult) )
    {
      v27 = RegCreateKeyW(hKey, L"Software\\Microsoft\\Code Store Database\\Distribution Units", &phkResult);
      if ( v27 )
        goto LABEL_63;
    }
    if ( RegOpenKeyExW(phkResult, this, 0, 0x2001Fu, &v55) )
    {
      v27 = RegCreateKeyW(phkResult, this, &v55);
      if ( v27 )
        goto LABEL_63;
    }
    if ( lpData )
    {
      v27 = RegSetValueExW(v55, 0, 0, 1u, lpData, 2 * wcslen((const unsigned __int16 *)lpData) + 2);
      if ( v27 )
        goto LABEL_63;
    }
    v27 = RegSetValueExW(v55, L"SystemComponent", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v27 )
      goto LABEL_63;
    v27 = RegSetValueExW(v55, L"Installer", 0, 1u, L"MSICD", 0xCu);
    if ( v27 )
      goto LABEL_63;
    if ( v44 )
    {
      v27 = RegSetValueExW(v55, L"Expire", 0, 4u, v44, 4u);
      if ( v27 )
        goto LABEL_63;
    }
    if ( RegOpenKeyExW(v55, L"DownloadInformation", 0, 0x2001Fu, &v54) )
    {
      v27 = RegCreateKeyW(v55, L"DownloadInformation", &v54);
      if ( v27 )
        goto LABEL_63;
    }
    if ( Type )
    {
      v27 = RegSetValueExW(v54, L"CODEBASE", 0, 1u, (const BYTE *)Type, 2 * wcslen((const unsigned __int16 *)Type) + 2);
      if ( v27 )
        goto LABEL_63;
    }
    v28 = lpReserved;
    if ( lpReserved )
    {
      if ( !RegOpenKeyExW(v55, L"AvailableVersion", 0, 0x2001Fu, &v53)
        || (v27 = RegCreateKeyW(v55, L"AvailableVersion", &v53)) == 0 )
      {
        v27 = RegSetValueExW(v53, L"Precache", 0, 4u, (const BYTE *)&a11, 4u);
        if ( !v27 )
          goto LABEL_51;
      }
      goto LABEL_63;
    }
    hKey = (HKEY)259;
    v57 = 0;
    if ( !RegQueryValueExW(v54, L"INF", 0, &Type, (LPBYTE)v56, (LPDWORD)&hKey)
      && (!lpString1 || lstrcmpiW(lpString1, v56)) )
    {
      DeleteFileW(v56);
      if ( !lpString1 )
        RegDeleteValueW(v54, L"INF");
    }
    hKey = (HKEY)259;
    v57 = 0;
    if ( RegQueryValueExW(v54, L"OSD", 0, &Type, (LPBYTE)v56, (LPDWORD)&hKey) )
    {
      if ( !v47 )
      {
LABEL_41:
        if ( !lpString1 )
          goto LABEL_80;
        v31 = lpString1;
        do
          v32 = *v31++;
        while ( v32 != (_WORD)v49 );
        v27 = RegSetValueExW(v54, L"INF", 0, 1u, (const BYTE *)lpString1, 2 * (v31 - (lpString1 + 1)) + 2);
        if ( !v27 )
        {
LABEL_80:
          if ( !RegOpenKeyExW(v55, L"InstalledVersion", 0, 0x2001Fu, &v53)
            || (v27 = RegCreateKeyW(v55, L"InstalledVersion", &v53)) == 0 )
          {
            RegDeleteKeyW(v55, L"AvailableVersion");
LABEL_51:
            v33 = (char *)v43;
            do
            {
              v34 = *(_WORD *)v33;
              v33 += 2;
            }
            while ( v34 != (_WORD)v49 );
            v27 = RegSetValueExW(v53, 0, 0, 1u, v43, 2 * ((v33 - (char *)(v43 + 2)) >> 1) + 2);
            if ( !v27 )
            {
              if ( v28 )
                goto LABEL_67;
              if ( (!v42
                 || (v27 = RegSetValueExW(
                             v53,
                             L"LastModified",
                             0,
                             1u,
                             v42,
                             2 * wcslen((const unsigned __int16 *)v42) + 2)) == 0)
                && (!v41
                 || (v27 = RegSetValueExW(v53, L"Etag", 0, 1u, v41, 2 * wcslen((const unsigned __int16 *)v41) + 2)) == 0)
                && (!RegOpenKeyExW(v55, L"Contains", 0, 0x2001Fu, &v51)
                 || (v27 = RegCreateKeyW(v55, L"Contains", &v51)) == 0) )
              {
                RegistrationRootKeyFromIntegrityLevel = CActiveXInstallBroker::UpdateFileList(
                                                          v35,
                                                          v51,
                                                          (unsigned int)a15,
                                                          (const unsigned __int16 **)v39,
                                                          v40);
                if ( RegistrationRootKeyFromIntegrityLevel >= 0 )
                  RegistrationRootKeyFromIntegrityLevel = CActiveXInstallBroker::UpdateDependencyList(
                                                            v36,
                                                            v51,
                                                            (unsigned int)a18,
                                                            (const unsigned __int16 **)v38);
                goto LABEL_67;
              }
            }
          }
        }
LABEL_63:
        RegistrationRootKeyFromIntegrityLevel = (unsigned __int16)v27 | 0x80070000;
        if ( v27 <= 0 )
          RegistrationRootKeyFromIntegrityLevel = v27;
        goto LABEL_67;
      }
    }
    else if ( !v47 || lstrcmpiW(v47, v56) )
    {
      DeleteFileW(v56);
      if ( !v47 )
      {
        RegDeleteValueW(v54, L"OSD");
        goto LABEL_41;
      }
    }
    v29 = v47;
    do
      v30 = *v29++;
    while ( v30 != (_WORD)v49 );
    v27 = RegSetValueExW(v54, L"OSD", 0, 1u, (const BYTE *)v47, 2 * (v29 - (v47 + 1)) + 2);
    if ( v27 )
      goto LABEL_63;
    goto LABEL_41;
  }
LABEL_67:
  if ( v51 )
    RegCloseKey(v51);
  if ( v54 )
    RegCloseKey(v54);
  if ( v53 )
    RegCloseKey(v53);
  if ( v55 )
    RegCloseKey(v55);
  if ( phkResult )
    RegCloseKey(phkResult);
  CLock::Unlock((CLock *)a2);
  return RegistrationRootKeyFromIntegrityLevel;
}

```

## disassembly

```asm
0x404c02  mov     edi, edi
0x404c04  push    ebp
0x404c05  mov     ebp, esp
0x404c07  sub     esp, 254h
0x404c0d  mov     eax, ___security_cookie
0x404c12  xor     eax, ebp
0x404c14  mov     [ebp+var_4], eax
0x404c17  push    ebx
0x404c18  push    esi
0x404c19  push    edi; HKEY *
0x404c1a  mov     esi, edx
0x404c1c  mov     [ebp+var_238], ecx
0x404c22  mov     eax, [ebp+arg_C]
0x404c25  mov     [ebp+var_23C], eax
0x404c2b  mov     eax, [ebp+arg_10]
0x404c2e  mov     [ebp+Type], eax
0x404c34  mov     eax, [ebp+arg_18]
0x404c37  mov     [ebp+lpString1], eax
0x404c3d  mov     eax, [ebp+arg_1C]
0x404c40  mov     [ebp+var_230], eax
0x404c46  mov     eax, [ebp+arg_24]
0x404c49  mov     [ebp+var_240], eax
0x404c4f  mov     eax, [ebp+arg_28]
0x404c52  mov     [ebp+var_244], eax
0x404c58  mov     eax, [ebp+arg_2C]
0x404c5b  mov     [ebp+var_248], eax
0x404c61  mov     eax, [ebp+arg_34]
0x404c64  mov     [ebp+var_250], eax
0x404c6a  mov     eax, [ebp+arg_38]
0x404c6d  mov     ebx, [ebp+lpData]
0x404c70  mov     [ebp+var_24C], eax
0x404c76  mov     eax, [ebp+arg_40]
0x404c79  mov     [ebp+var_254], eax
0x404c7f  xor     eax, eax
0x404c81  mov     edi, [ebp+lpSubKey]
0x404c84  mov     [ebp+var_228], eax
0x404c8a  mov     [ebp+hKey], eax
0x404c90  mov     [ebp+phkResult], eax
0x404c96  mov     [ebp+var_210], eax
0x404c9c  mov     [ebp+var_214], eax
0x404ca2  mov     [ebp+var_220], eax
0x404ca8  mov     [ebp+var_218], eax
0x404cae  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x404cb3  test    eax, eax
0x404cb5  jnz     short loc_404CC1
0x404cb7  mov     esi, 8007000Eh
0x404cbc  jmp     loc_405277
0x404cc1  mov     eax, [ebp+var_238]
0x404cc7  cmp     dword ptr [eax+1Ch], 7
0x404ccb  jge     short loc_404CD7
0x404ccd  mov     esi, 8007139Fh
0x404cd2  jmp     loc_405277
0x404cd7  test    esi, esi
0x404cd9  jz      loc_405272
0x404cdf  test    edi, edi
0x404ce1  jz      loc_405272
0x404ce7  mov     eax, [eax+24h]
0x404cea  mov     cx, [esi]
0x404ced  cmp     cx, [eax]
0x404cf0  jnz     short loc_404D10
0x404cf2  test    cx, cx
0x404cf5  jz      short loc_404D0C
0x404cf7  mov     cx, [esi+2]
0x404cfb  cmp     cx, [eax+2]
0x404cff  jnz     short loc_404D10
0x404d01  add     esi, 4
0x404d04  add     eax, 4
0x404d07  test    cx, cx
0x404d0a  jnz     short loc_404CEA
0x404d0c  xor     eax, eax
0x404d0e  jmp     short loc_404D15
0x404d10  sbb     eax, eax
0x404d12  or      eax, 1
0x404d15  test    eax, eax
0x404d17  jz      short loc_404D23
0x404d19  mov     esi, 80070005h
0x404d1e  jmp     loc_405277
0x404d23  lea     ecx, [ebp+hKey]
0x404d29  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YGJPAPAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x404d2e  mov     esi, eax
0x404d30  test    esi, esi
0x404d32  jnz     loc_405277
0x404d38  lea     eax, [ebp+phkResult]
0x404d3e  push    eax; phkResult
0x404d3f  push    2001Fh; samDesired
0x404d44  push    esi; ulOptions
0x404d45  push    offset aSoftwareMicros_2; "Software\\Microsoft\\Code Store Databas"...
0x404d4a  push    [ebp+hKey]; hKey
0x404d50  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x404d56  test    eax, eax
0x404d58  jz      short loc_404D7A
0x404d5a  lea     eax, [ebp+phkResult]
0x404d60  push    eax; phkResult
0x404d61  push    offset aSoftwareMicros_2; "Software\\Microsoft\\Code Store Databas"...
0x404d66  push    [ebp+hKey]; hKey
0x404d6c  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x404d72  test    eax, eax
0x404d74  jnz     loc_405262
0x404d7a  lea     eax, [ebp+var_210]
0x404d80  push    eax; phkResult
0x404d81  push    2001Fh; samDesired
0x404d86  push    0; ulOptions
0x404d88  push    edi; lpSubKey
0x404d89  push    [ebp+phkResult]; hKey
0x404d8f  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x404d95  test    eax, eax
0x404d97  jz      short loc_404DB5
0x404d99  lea     eax, [ebp+var_210]
0x404d9f  push    eax; phkResult
0x404da0  push    edi; lpSubKey
0x404da1  push    [ebp+phkResult]; hKey
0x404da7  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x404dad  test    eax, eax
0x404daf  jnz     loc_405262
0x404db5  xor     edi, edi
0x404db7  test    ebx, ebx
0x404db9  jz      short loc_404DF0
0x404dbb  mov     ecx, ebx
0x404dbd  lea     edx, [ecx+2]
0x404dc0  mov     ax, [ecx]
0x404dc3  add     ecx, 2
0x404dc6  cmp     ax, di
0x404dc9  jnz     short loc_404DC0
0x404dcb  sub     ecx, edx
0x404dcd  sar     ecx, 1
0x404dcf  lea     eax, ds:2[ecx*2]
0x404dd6  push    eax; cbData
0x404dd7  push    ebx; lpData
0x404dd8  push    1; dwType
0x404dda  push    edi; Reserved
0x404ddb  push    edi; lpValueName
0x404ddc  push    [ebp+var_210]; hKey
0x404de2  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x404de8  test    eax, eax
0x404dea  jnz     loc_405262
0x404df0  push    4
0x404df2  pop     ebx
0x404df3  push    ebx; cbData
0x404df4  lea     eax, [ebp+Data]
0x404df7  push    eax; lpData
0x404df8  push    ebx; dwType
0x404df9  push    edi; Reserved
0x404dfa  push    offset aSystemcomponen; "SystemComponent"
0x404dff  push    [ebp+var_210]; hKey
0x404e05  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x404e0b  test    eax, eax
0x404e0d  jnz     loc_405262
0x404e13  push    0Ch; cbData
0x404e15  push    offset aMsicd; "MSICD"
0x404e1a  push    1; dwType
0x404e1c  push    edi; Reserved
0x404e1d  push    offset aInstaller; "Installer"
0x404e22  push    [ebp+var_210]; hKey
0x404e28  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x404e2e  test    eax, eax
0x404e30  jnz     loc_405262
0x404e36  mov     eax, [ebp+var_23C]
0x404e3c  test    eax, eax
0x404e3e  jz      short loc_404E5D
0x404e40  push    ebx; cbData
0x404e41  push    eax; lpData
0x404e42  push    ebx; dwType
0x404e43  push    edi; Reserved
0x404e44  push    offset aExpire; "Expire"
0x404e49  push    [ebp+var_210]; hKey
0x404e4f  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x404e55  test    eax, eax
0x404e57  jnz     loc_405262
0x404e5d  lea     eax, [ebp+var_214]
0x404e63  mov     ebx, offset aDownloadinform; "DownloadInformation"
0x404e68  push    eax; phkResult
0x404e69  push    2001Fh; samDesired
0x404e6e  push    edi; ulOptions
0x404e6f  push    ebx; lpSubKey
0x404e70  push    [ebp+var_210]; hKey
0x404e76  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x404e7c  test    eax, eax
0x404e7e  jz      short loc_404E9C
0x404e80  lea     eax, [ebp+var_214]
0x404e86  push    eax; phkResult
0x404e87  push    ebx; lpSubKey
0x404e88  push    [ebp+var_210]; hKey
0x404e8e  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x404e94  test    eax, eax
0x404e96  jnz     loc_405262
0x404e9c  mov     ebx, [ebp+Type]
0x404ea2  test    ebx, ebx
0x404ea4  jz      short loc_404EDF
0x404ea6  mov     ecx, ebx
0x404ea8  lea     edx, [ecx+2]
0x404eab  mov     ax, [ecx]
0x404eae  add     ecx, 2
0x404eb1  cmp     ax, di
0x404eb4  jnz     short loc_404EAB
0x404eb6  sub     ecx, edx
0x404eb8  sar     ecx, 1
0x404eba  lea     eax, ds:2[ecx*2]
0x404ec1  push    eax; cbData
0x404ec2  push    ebx; lpData
0x404ec3  push    1; dwType
0x404ec5  push    edi; Reserved
0x404ec6  push    offset aCodebase; "CODEBASE"
0x404ecb  push    [ebp+var_214]; hKey
0x404ed1  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x404ed7  test    eax, eax
0x404ed9  jnz     loc_405262
0x404edf  mov     edi, [ebp+lpReserved]
0x404ee2  test    edi, edi
0x404ee4  jnz     loc_4050BC
0x404eea  xor     eax, eax
0x404eec  mov     [ebp+hKey], 103h
0x404ef6  mov     [ebp+var_6], ax
0x404efa  lea     eax, [ebp+hKey]
0x404f00  push    eax; lpcbData
0x404f01  lea     eax, [ebp+var_20C]
0x404f07  push    eax; lpData
0x404f08  lea     eax, [ebp+Type]
0x404f0e  push    eax; lpType
0x404f0f  push    edi; lpReserved
0x404f10  push    offset aInf; "INF"
0x404f15  push    [ebp+var_214]; hKey
0x404f1b  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x404f21  test    eax, eax
0x404f23  jnz     short loc_404F63
0x404f25  mov     ebx, [ebp+lpString1]
0x404f2b  test    ebx, ebx
0x404f2d  jz      short loc_404F41
0x404f2f  lea     eax, [ebp+var_20C]
0x404f35  push    eax; lpString2
0x404f36  push    ebx; lpString1
0x404f37  call    ds:__imp__lstrcmpiW@8; lstrcmpiW(x,x)
0x404f3d  test    eax, eax
0x404f3f  jz      short loc_404F63
0x404f41  lea     eax, [ebp+var_20C]
0x404f47  push    eax; lpFileName
0x404f48  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x404f4e  test    ebx, ebx
0x404f50  jnz     short loc_404F63
0x404f52  push    offset aInf; "INF"
0x404f57  push    [ebp+var_214]; hKey
0x404f5d  call    ds:__imp__RegDeleteValueW@8; RegDeleteValueW(x,x)
0x404f63  xor     eax, eax
0x404f65  mov     [ebp+hKey], 103h
0x404f6f  mov     [ebp+var_6], ax
0x404f73  lea     eax, [ebp+hKey]
0x404f79  push    eax; lpcbData
0x404f7a  lea     eax, [ebp+var_20C]
0x404f80  push    eax; lpData
0x404f81  lea     eax, [ebp+Type]
0x404f87  push    eax; lpType
0x404f88  push    0; lpReserved
0x404f8a  push    offset aOsd; "OSD"
0x404f8f  push    [ebp+var_214]; hKey
0x404f95  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x404f9b  mov     ebx, [ebp+var_230]
0x404fa1  test    eax, eax
0x404fa3  jnz     short loc_404FDF
0x404fa5  test    ebx, ebx
0x404fa7  jz      short loc_404FBB
0x404fa9  lea     eax, [ebp+var_20C]
0x404faf  push    eax; lpString2
0x404fb0  push    ebx; lpString1
0x404fb1  call    ds:__imp__lstrcmpiW@8; lstrcmpiW(x,x)
0x404fb7  test    eax, eax
0x404fb9  jz      short loc_404FE3
0x404fbb  lea     eax, [ebp+var_20C]
0x404fc1  push    eax; lpFileName
0x404fc2  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x404fc8  test    ebx, ebx
0x404fca  jnz     short loc_404FE3
0x404fcc  push    offset aOsd; "OSD"
0x404fd1  push    [ebp+var_214]; hKey
0x404fd7  call    ds:__imp__RegDeleteValueW@8; RegDeleteValueW(x,x)
0x404fdd  jmp     short loc_405021
0x404fdf  test    ebx, ebx
0x404fe1  jz      short loc_405021
0x404fe3  mov     ecx, ebx
0x404fe5  lea     edx, [ecx+2]
0x404fe8  mov     ax, [ecx]
0x404feb  add     ecx, 2
0x404fee  cmp     ax, word ptr [ebp+var_228]
0x404ff5  jnz     short loc_404FE8
0x404ff7  sub     ecx, edx
0x404ff9  sar     ecx, 1
0x404ffb  lea     eax, ds:2[ecx*2]
0x405002  push    eax; cbData
0x405003  push    ebx; lpData
0x405004  push    1; dwType
0x405006  push    0; Reserved
0x405008  push    offset aOsd; "OSD"
0x40500d  push    [ebp+var_214]; hKey
0x405013  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x405019  test    eax, eax
0x40501b  jnz     loc_405262
0x405021  mov     ebx, [ebp+lpString1]
0x405027  test    ebx, ebx
0x405029  jz      short loc_405069
0x40502b  mov     ecx, ebx
0x40502d  lea     edx, [ecx+2]
0x405030  mov     ax, [ecx]
  ... truncated ...
```
