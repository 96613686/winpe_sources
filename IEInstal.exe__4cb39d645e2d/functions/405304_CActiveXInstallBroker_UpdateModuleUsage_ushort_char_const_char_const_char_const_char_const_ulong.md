# CActiveXInstallBroker::UpdateModuleUsage(ushort *,char const *,char const *,char const *,char const *,ulong)

- ea: `0x405304`
- end: `0x405622`
- name: `?UpdateModuleUsage@CActiveXInstallBroker@@QAGJPAGPBD111K@Z`
- size: `798`
- prototype: `int __userpurge@<eax>(_WORD *@<edx>, CLock *@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, const char *, const char *, const char *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x406000`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x40351a`
- `0x405304`
- `0x409dbc`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x40551b`
- `ADVAPI32!RegCloseKey` at `0x405530`
- `ADVAPI32!RegCloseKey` at `0x40551b`
- `ADVAPI32!RegCloseKey` at `0x405530`
- `ADVAPI32!RegCreateKeyW` at `0x40545e`
- `ADVAPI32!RegCreateKeyW` at `0x40545e`
- `ADVAPI32!RegOpenKeyExW` at `0x405442`
- `ADVAPI32!RegOpenKeyExW` at `0x405442`
- `ADVAPI32!RegOpenKeyExA` at `0x405486`
- `ADVAPI32!RegOpenKeyExA` at `0x405486`
- `ADVAPI32!RegSetValueExA` at `0x40558c`
- `ADVAPI32!RegSetValueExA` at `0x405601`
- `ADVAPI32!RegSetValueExA` at `0x40558c`
- `ADVAPI32!RegSetValueExA` at `0x405601`
- `ADVAPI32!RegQueryValueExA` at `0x4054d3`
- `ADVAPI32!RegQueryValueExA` at `0x4055be`
- `ADVAPI32!RegQueryValueExA` at `0x4054d3`
- `ADVAPI32!RegQueryValueExA` at `0x4055be`
- `ADVAPI32!RegCreateKeyA` at `0x4054a3`
- `ADVAPI32!RegCreateKeyA` at `0x4054a3`
- `KERNEL32!lstrcmpiA` at `0x4054ef`
- `KERNEL32!lstrcmpiA` at `0x4054ef`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::UpdateModuleUsage@<eax>(
        _WORD *a1@<edx>,
        CLock *a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        const char *a5,
        const char *a6,
        const char *a7,
        const char *a8,
        unsigned int a9)
{
  unsigned int v10; // ebx
  int v11; // edi
  CActiveXInstallBroker *v12; // ecx
  int RegistrationRootKeyFromIntegrityLevel; // esi
  _WORD *v14; // eax
  bool v15; // cf
  int v16; // eax
  LSTATUS v17; // eax
  const CHAR *v18; // ebx
  int v20; // eax
  LPCSTR v21; // eax
  const BYTE *v22; // edx
  DWORD v23; // [esp-4h] [ebp-140h]
  DWORD Type; // [esp+14h] [ebp-128h] BYREF
  CLock *v25; // [esp+18h] [ebp-124h]
  LPCSTR lpString2; // [esp+1Ch] [ebp-120h]
  DWORD cbData; // [esp+20h] [ebp-11Ch] BYREF
  LPCSTR lpSubKey; // [esp+24h] [ebp-118h]
  HKEY hKey; // [esp+28h] [ebp-114h] BYREF
  HKEY phkResult; // [esp+2Ch] [ebp-110h] BYREF
  HKEY v31; // [esp+30h] [ebp-10Ch] BYREF
  BYTE Data[260]; // [esp+34h] [ebp-108h] BYREF

  lpSubKey = (LPCSTR)this;
  hKey = 0;
  phkResult = 0;
  v31 = 0;
  Type = 0;
  memset(Data, 0, sizeof(Data));
  v25 = a2;
  lpString2 = a5;
  cbData = 260;
  v10 = strlen(a5);
  v11 = 1;
  if ( !CLock::Lock(v25) )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024882;
    goto LABEL_25;
  }
  if ( *((int *)v25 + 7) < 7 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147019873;
    goto LABEL_25;
  }
  if ( !a1 || !lpSubKey )
    goto LABEL_24;
  v14 = (_WORD *)*((_DWORD *)v25 + 9);
  while ( 1 )
  {
    LOWORD(v12) = *a1;
    v15 = *a1 < *v14;
    if ( *a1 != *v14 )
      break;
    if ( !(_WORD)v12 )
      goto LABEL_12;
    LOWORD(v12) = a1[1];
    v15 = (unsigned __int16)v12 < v14[1];
    if ( (_WORD)v12 != v14[1] )
      break;
    a1 += 2;
    v14 += 2;
    if ( !(_WORD)v12 )
    {
LABEL_12:
      v16 = 0;
      goto LABEL_14;
    }
  }
  v16 = v15 ? -1 : 1;
LABEL_14:
  if ( v16 )
  {
    RegistrationRootKeyFromIntegrityLevel = -2147024891;
    goto LABEL_25;
  }
  RegistrationRootKeyFromIntegrityLevel = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
  if ( RegistrationRootKeyFromIntegrityLevel )
    goto LABEL_25;
  if ( RegOpenKeyExW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ModuleUsage", 0, 0x2001Fu, &phkResult) )
  {
    v17 = RegCreateKeyW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ModuleUsage", &phkResult);
    if ( v17 )
      goto LABEL_42;
  }
  if ( RegOpenKeyExA(phkResult, lpSubKey, 0, 0x2001Fu, &v31) )
  {
    v17 = RegCreateKeyA(phkResult, lpSubKey, &v31);
    if ( v17 )
      goto LABEL_42;
  }
  if ( RegQueryValueExA(v31, ".Owner", 0, &Type, Data, &cbData) )
  {
    v20 = 14;
    if ( ((unsigned __int8)a7 & 1) != 0 )
      v20 = v10;
    v18 = lpString2;
    v23 = v20;
    v21 = "Unknown Owner";
    if ( ((unsigned __int8)a7 & 1) != 0 )
      v21 = lpString2;
    v17 = RegSetValueExA(v31, ".Owner", 0, 1u, (const BYTE *)v21, v23);
    if ( !v17 )
      goto LABEL_37;
LABEL_42:
    RegistrationRootKeyFromIntegrityLevel = (unsigned __int16)v17 | 0x80070000;
    if ( v17 <= 0 )
      RegistrationRootKeyFromIntegrityLevel = v17;
    goto LABEL_25;
  }
  v18 = lpString2;
  if ( lstrcmpiA((LPCSTR)Data, lpString2) && ((unsigned __int8)a7 & 1) != 0 )
  {
LABEL_24:
    RegistrationRootKeyFromIntegrityLevel = -2147024809;
    goto LABEL_25;
  }
LABEL_37:
  cbData = 260;
  if ( !RegQueryValueExA(v31, v18, 0, &Type, Data, &cbData) )
  {
    v11 = 0;
    goto LABEL_25;
  }
  v22 = (const BYTE *)&Args;
  if ( a6 )
    v22 = (const BYTE *)a6;
  v17 = RegSetValueExA(v31, lpString2, 0, 1u, v22, strlen((const char *)v22) + 1);
  if ( v17 )
    goto LABEL_42;
LABEL_25:
  if ( v31 )
    RegCloseKey(v31);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v11 )
    RegistrationRootKeyFromIntegrityLevel = CActiveXInstallBroker::UpdateSharedDlls(v12, (const char *)a4);
  CLock::Unlock(v25);
  return RegistrationRootKeyFromIntegrityLevel;
}

```

## disassembly

```asm
0x405304  mov     edi, edi
0x405306  push    ebp
0x405307  mov     ebp, esp
0x405309  sub     esp, 130h
0x40530f  mov     eax, ___security_cookie
0x405314  xor     eax, ebp
0x405316  mov     [ebp+var_4], eax
0x405319  mov     eax, [ebp+this]
0x40531c  push    ebx
0x40531d  mov     ebx, [ebp+arg_8]
0x405320  mov     [ebp+lpSubKey], eax
0x405326  mov     eax, [ebp+arg_4]
0x405329  push    esi
0x40532a  mov     [ebp+var_130], eax
0x405330  mov     esi, edx
0x405332  mov     eax, [ebp+arg_C]
0x405335  push    edi; HKEY *
0x405336  mov     [ebp+lpData], eax
0x40533c  xor     eax, eax
0x40533e  push    103h; Size
0x405343  push    eax; Val
0x405344  mov     [ebp+hKey], eax
0x40534a  mov     [ebp+phkResult], eax
0x405350  mov     [ebp+var_10C], eax
0x405356  mov     [ebp+Type], eax
0x40535c  mov     [ebp+Data], al
0x405362  lea     eax, [ebp+var_107]
0x405368  push    eax; void *
0x405369  mov     [ebp+var_124], ecx
0x40536f  mov     [ebp+lpString2], ebx
0x405375  call    _memset
0x40537a  add     esp, 0Ch
0x40537d  mov     [ebp+cbData], 104h
0x405387  lea     ecx, [ebx+1]
0x40538a  mov     al, [ebx]
0x40538c  inc     ebx
0x40538d  test    al, al
0x40538f  jnz     short loc_40538A
0x405391  sub     ebx, ecx
0x405393  xor     edi, edi
0x405395  mov     ecx, [ebp+var_124]; this
0x40539b  inc     edi
0x40539c  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x4053a1  test    eax, eax
0x4053a3  jnz     short loc_4053AF
0x4053a5  mov     esi, 8007000Eh
0x4053aa  jmp     loc_40550C
0x4053af  mov     eax, [ebp+var_124]
0x4053b5  cmp     dword ptr [eax+1Ch], 7
0x4053b9  jge     short loc_4053C5
0x4053bb  mov     esi, 8007139Fh
0x4053c0  jmp     loc_40550C
0x4053c5  test    esi, esi
0x4053c7  jz      loc_405507
0x4053cd  cmp     [ebp+lpSubKey], 0
0x4053d4  jz      loc_405507
0x4053da  mov     eax, [eax+24h]
0x4053dd  mov     cx, [esi]
0x4053e0  cmp     cx, [eax]
0x4053e3  jnz     short loc_405403
0x4053e5  test    cx, cx
0x4053e8  jz      short loc_4053FF
0x4053ea  mov     cx, [esi+2]
0x4053ee  cmp     cx, [eax+2]
0x4053f2  jnz     short loc_405403
0x4053f4  add     esi, 4
0x4053f7  add     eax, 4
0x4053fa  test    cx, cx
0x4053fd  jnz     short loc_4053DD
0x4053ff  xor     eax, eax
0x405401  jmp     short loc_405407
0x405403  sbb     eax, eax
0x405405  or      eax, edi
0x405407  test    eax, eax
0x405409  jz      short loc_405415
0x40540b  mov     esi, 80070005h
0x405410  jmp     loc_40550C
0x405415  lea     ecx, [ebp+hKey]
0x40541b  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YGJPAPAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x405420  mov     esi, eax
0x405422  test    esi, esi
0x405424  jnz     loc_40550C
0x40542a  lea     eax, [ebp+phkResult]
0x405430  push    eax; phkResult
0x405431  push    2001Fh; samDesired
0x405436  push    esi; ulOptions
0x405437  push    offset aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x40543c  push    [ebp+hKey]; hKey
0x405442  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x405448  test    eax, eax
0x40544a  jz      short loc_40546C
0x40544c  lea     eax, [ebp+phkResult]
0x405452  push    eax; phkResult
0x405453  push    offset aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x405458  push    [ebp+hKey]; hKey
0x40545e  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x405464  test    eax, eax
0x405466  jnz     loc_40560F
0x40546c  lea     eax, [ebp+var_10C]
0x405472  push    eax; phkResult
0x405473  push    2001Fh; samDesired
0x405478  push    0; ulOptions
0x40547a  push    [ebp+lpSubKey]; lpSubKey
0x405480  push    [ebp+phkResult]; hKey
0x405486  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x40548c  test    eax, eax
0x40548e  jz      short loc_4054B1
0x405490  lea     eax, [ebp+var_10C]
0x405496  push    eax; phkResult
0x405497  push    [ebp+lpSubKey]; lpSubKey
0x40549d  push    [ebp+phkResult]; hKey
0x4054a3  call    ds:__imp__RegCreateKeyA@12; RegCreateKeyA(x,x,x)
0x4054a9  test    eax, eax
0x4054ab  jnz     loc_40560F
0x4054b1  lea     eax, [ebp+cbData]
0x4054b7  push    eax; lpcbData
0x4054b8  lea     eax, [ebp+Data]
0x4054be  push    eax; lpData
0x4054bf  lea     eax, [ebp+Type]
0x4054c5  push    eax; lpType
0x4054c6  push    0; lpReserved
0x4054c8  push    offset aOwner; ".Owner"
0x4054cd  push    [ebp+var_10C]; hKey
0x4054d3  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x4054d9  test    eax, eax
0x4054db  jnz     loc_405565
0x4054e1  mov     ebx, [ebp+lpString2]
0x4054e7  lea     eax, [ebp+Data]
0x4054ed  push    ebx; lpString2
0x4054ee  push    eax; lpString1
0x4054ef  call    ds:__imp__lstrcmpiA@8; lstrcmpiA(x,x)
0x4054f5  test    eax, eax
0x4054f7  jz      loc_405596
0x4054fd  test    byte ptr [ebp+arg_10], 1
0x405501  jz      loc_405596
0x405507  mov     esi, 80070057h
0x40550c  cmp     [ebp+var_10C], 0
0x405513  jz      short loc_405521
0x405515  push    [ebp+var_10C]; hKey
0x40551b  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x405521  cmp     [ebp+phkResult], 0
0x405528  jz      short loc_405536
0x40552a  push    [ebp+phkResult]; hKey
0x405530  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x405536  test    edi, edi
0x405538  jz      short loc_405547
0x40553a  push    [ebp+var_130]; char *
0x405540  call    ?UpdateSharedDlls@CActiveXInstallBroker@@AAEJPBD@Z; CActiveXInstallBroker::UpdateSharedDlls(char const *)
0x405545  mov     esi, eax
0x405547  mov     ecx, [ebp+var_124]; this
0x40554d  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x405552  mov     ecx, [ebp+var_4]
0x405555  mov     eax, esi
0x405557  pop     edi
0x405558  pop     esi
0x405559  xor     ecx, ebp; StackCookie
0x40555b  pop     ebx
0x40555c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x405561  leave
0x405562  retn    14h
0x405565  test    [ebp+arg_10], edi
0x405568  push    0Eh
0x40556a  pop     eax
0x40556b  cmovnz  eax, ebx
0x40556e  mov     ebx, [ebp+lpString2]
0x405574  push    eax; cbData
0x405575  mov     eax, offset aUnknownOwner; "Unknown Owner"
0x40557a  cmovnz  eax, ebx
0x40557d  push    eax; lpData
0x40557e  push    edi; dwType
0x40557f  push    0; Reserved
0x405581  push    offset aOwner; ".Owner"
0x405586  push    [ebp+var_10C]; hKey
0x40558c  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x405592  test    eax, eax
0x405594  jnz     short loc_40560F
0x405596  lea     eax, [ebp+cbData]
0x40559c  mov     [ebp+cbData], 104h
0x4055a6  push    eax; lpcbData
0x4055a7  lea     eax, [ebp+Data]
0x4055ad  push    eax; lpData
0x4055ae  lea     eax, [ebp+Type]
0x4055b4  push    eax; lpType
0x4055b5  push    0; lpReserved
0x4055b7  push    ebx; lpValueName
0x4055b8  push    [ebp+var_10C]; hKey
0x4055be  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x4055c4  test    eax, eax
0x4055c6  jnz     short loc_4055CF
0x4055c8  xor     edi, edi
0x4055ca  jmp     loc_40550C
0x4055cf  mov     eax, [ebp+lpData]
0x4055d5  mov     edx, offset Args
0x4055da  test    eax, eax
0x4055dc  cmovnz  edx, eax
0x4055df  mov     ecx, edx
0x4055e1  lea     ebx, [ecx+1]
0x4055e4  mov     al, [ecx]
0x4055e6  inc     ecx
0x4055e7  test    al, al
0x4055e9  jnz     short loc_4055E4
0x4055eb  sub     ecx, ebx
0x4055ed  lea     eax, [ecx+1]
0x4055f0  push    eax; cbData
0x4055f1  push    edx; lpData
0x4055f2  push    edi; dwType
0x4055f3  push    0; Reserved
0x4055f5  push    [ebp+lpString2]; lpValueName
0x4055fb  push    [ebp+var_10C]; hKey
0x405601  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x405607  test    eax, eax
0x405609  jz      loc_40550C
0x40560f  movzx   esi, ax
0x405612  or      esi, 80070000h
0x405618  test    eax, eax
0x40561a  cmovle  esi, eax
0x40561d  jmp     loc_40550C
```
