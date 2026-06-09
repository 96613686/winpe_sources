# IERegGetDWORDWithPoliciesExW(ushort const *,ushort const *,ushort const *,ulong,int *,int *)

- ea: `0x409fc4`
- end: `0x40a136`
- name: `?IERegGetDWORDWithPoliciesExW@@YGKPBG00KPAH1@Z`
- size: `370`
- prototype: `unsigned int __stdcall(const unsigned __int16 *lpValueName, const unsigned __int16 *, const unsigned __int16 *, _DWORD *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x408235`

## callees

- `0x409fc4`
- `0x40a174`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x40a06b`
- `ADVAPI32!RegCloseKey` at `0x40a0c8`
- `ADVAPI32!RegCloseKey` at `0x40a06b`
- `ADVAPI32!RegCloseKey` at `0x40a0c8`
- `ADVAPI32!RegQueryValueExW` at `0x40a060`
- `ADVAPI32!RegQueryValueExW` at `0x40a0bd`
- `ADVAPI32!RegQueryValueExW` at `0x40a060`
- `ADVAPI32!RegQueryValueExW` at `0x40a0bd`
- `ADVAPI32!RegOpenKeyExW` at `0x40a03f`
- `ADVAPI32!RegOpenKeyExW` at `0x40a09e`
- `ADVAPI32!RegOpenKeyExW` at `0x40a03f`
- `ADVAPI32!RegOpenKeyExW` at `0x40a09e`
- `ADVAPI32!RegGetValueW` at `0x40a009`
- `ADVAPI32!RegGetValueW` at `0x40a0f4`
- `ADVAPI32!RegGetValueW` at `0x40a009`
- `ADVAPI32!RegGetValueW` at `0x40a0f4`
- `iertutil!__imp__IsPolicyKeyPresentW@12` at `0x409fe5`
- `iertutil!__imp__IsPolicyKeyPresentW@12` at `0x40a020`
- `iertutil!__imp__IsPolicyKeyPresentW@12` at `0x40a087`
- `iertutil!__imp__IsPolicyKeyPresentW@12` at `0x409fe5`
- `iertutil!__imp__IsPolicyKeyPresentW@12` at `0x40a020`
- `iertutil!__imp__IsPolicyKeyPresentW@12` at `0x40a087`

## string_xrefs

- `0x409ffa`: `Security_HKLM_Only`

## pseudocode

```c
unsigned int __stdcall IERegGetDWORDWithPoliciesExW(
        const unsigned __int16 *lpValueName,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        _DWORD *a4,
        int *a5,
        int *a6)
{
  int v6; // ebx
  LSTATUS v7; // esi
  const WCHAR *v8; // ecx
  LSTATUS ValueW; // eax
  void *v11; // [esp+0h] [ebp-20h]
  DWORD *v12; // [esp+4h] [ebp-1Ch]
  int pvData; // [esp+Ch] [ebp-14h] BYREF
  DWORD pcbData; // [esp+10h] [ebp-10h] BYREF
  HKEY phkResult; // [esp+14h] [ebp-Ch] BYREF
  BYTE Data[4]; // [esp+18h] [ebp-8h] BYREF
  DWORD cbData; // [esp+1Ch] [ebp-4h] BYREF

  pcbData = 4;
  v6 = 0;
  v7 = 1;
  if ( IsPolicyKeyPresentW(L"Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 2)
    && !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Internet Explorer\\Main",
          L"Security_HKLM_Only",
          0x18u,
          0,
          &pvData,
          &pcbData) )
  {
    v6 = pvData;
  }
  *(_DWORD *)Data = 0;
  if ( IsPolicyKeyPresentW(L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter", 0, 2) )
  {
    v7 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
           0,
           1u,
           &phkResult);
    if ( !v7 )
    {
      cbData = 4;
      v7 = RegQueryValueExW(phkResult, lpValueName, 0, 0, Data, &cbData);
      RegCloseKey(phkResult);
    }
  }
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_20;
    if ( !IsPolicyKeyPresentW(L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter", 1, 2)
      || RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
           0,
           1u,
           &phkResult) )
    {
LABEL_13:
      cbData = 4;
      if ( v6 )
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Internet Explorer\\Main\\AllowAxisCharacter",
                   lpValueName,
                   0x18u,
                   0,
                   Data,
                   &cbData);
      else
        ValueW = SHRegGetValueFromHKCUHKLM(v8, v8, (SRRF)Data, &cbData, v11, v12);
      if ( ValueW )
        *(_DWORD *)Data = 0;
      if ( a4 )
        *a4 = 0;
      return *(_DWORD *)Data;
    }
    cbData = 4;
    v7 = RegQueryValueExW(phkResult, lpValueName, 0, 0, Data, &cbData);
    RegCloseKey(phkResult);
  }
  if ( v7 )
    goto LABEL_13;
LABEL_20:
  if ( a4 )
    *a4 = 1;
  return *(_DWORD *)Data;
}

```

## disassembly

```asm
0x409fc4  mov     edi, edi
0x409fc6  push    ebp
0x409fc7  mov     ebp, esp
0x409fc9  sub     esp, 14h
0x409fcc  push    ebx
0x409fcd  push    esi; pcbData
0x409fce  push    edi; pvData
0x409fcf  push    2
0x409fd1  xor     edi, edi
0x409fd3  mov     [ebp+pcbData], 4
0x409fda  push    edi
0x409fdb  xor     esi, esi
0x409fdd  mov     ebx, edi
0x409fdf  push    offset aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Internet"...
0x409fe4  inc     esi
0x409fe5  call    ds:__imp__IsPolicyKeyPresentW@12; IsPolicyKeyPresentW(x,x,x)
0x409feb  test    eax, eax
0x409fed  jz      short loc_40A015
0x409fef  lea     eax, [ebp+pcbData]
0x409ff2  push    eax; pcbData
0x409ff3  lea     eax, [ebp+pvData]
0x409ff6  push    eax; pvData
0x409ff7  push    edi; pdwType
0x409ff8  push    18h; dwFlags
0x409ffa  push    offset Value; "Security_HKLM_Only"
0x409fff  push    offset aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Internet"...
0x40a004  push    80000002h; hkey
0x40a009  call    ds:__imp__RegGetValueW@28; RegGetValueW(x,x,x,x,x,x,x)
0x40a00f  test    eax, eax
0x40a011  cmovz   ebx, [ebp+pvData]
0x40a015  push    2
0x40a017  push    edi
0x40a018  push    offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x40a01d  mov     dword ptr [ebp+Data], edi
0x40a020  call    ds:__imp__IsPolicyKeyPresentW@12; IsPolicyKeyPresentW(x,x,x)
0x40a026  mov     edi, [ebp+lpValueName]
0x40a029  test    eax, eax
0x40a02b  jz      short loc_40A071
0x40a02d  lea     eax, [ebp+phkResult]
0x40a030  push    eax; phkResult
0x40a031  push    1; samDesired
0x40a033  push    0; ulOptions
0x40a035  push    offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x40a03a  push    80000002h; hKey
0x40a03f  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x40a045  mov     esi, eax
0x40a047  test    esi, esi
0x40a049  jnz     short loc_40A071
0x40a04b  lea     eax, [ebp+cbData]
0x40a04e  mov     [ebp+cbData], 4
0x40a055  push    eax; lpcbData
0x40a056  lea     eax, [ebp+Data]
0x40a059  push    eax; lpData
0x40a05a  push    esi; lpType
0x40a05b  push    esi; lpReserved
0x40a05c  push    edi; lpValueName
0x40a05d  push    [ebp+phkResult]; hKey
0x40a060  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x40a066  push    [ebp+phkResult]; hKey
0x40a069  mov     esi, eax
0x40a06b  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x40a071  test    ebx, ebx
0x40a073  jnz     short loc_40A0CE
0x40a075  test    esi, esi
0x40a077  jz      loc_40A11F
0x40a07d  push    2
0x40a07f  push    1
0x40a081  mov     esi, offset aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x40a086  push    esi
0x40a087  call    ds:__imp__IsPolicyKeyPresentW@12; IsPolicyKeyPresentW(x,x,x)
0x40a08d  test    eax, eax
0x40a08f  jz      short loc_40A0D2
0x40a091  lea     eax, [ebp+phkResult]
0x40a094  push    eax; phkResult
0x40a095  push    1; samDesired
0x40a097  push    ebx; ulOptions
0x40a098  push    esi; lpSubKey
0x40a099  push    80000001h; hKey
0x40a09e  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x40a0a4  test    eax, eax
0x40a0a6  jnz     short loc_40A0D2
0x40a0a8  lea     eax, [ebp+cbData]
0x40a0ab  mov     [ebp+cbData], 4
0x40a0b2  push    eax; lpcbData
0x40a0b3  lea     eax, [ebp+Data]
0x40a0b6  push    eax; lpData
0x40a0b7  push    ebx; lpType
0x40a0b8  push    ebx; lpReserved
0x40a0b9  push    edi; lpValueName
0x40a0ba  push    [ebp+phkResult]; hKey
0x40a0bd  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x40a0c3  push    [ebp+phkResult]; hKey
0x40a0c6  mov     esi, eax
0x40a0c8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x40a0ce  test    esi, esi
0x40a0d0  jz      short loc_40A11F
0x40a0d2  mov     [ebp+cbData], 4
0x40a0d9  lea     eax, [ebp+cbData]
0x40a0dc  push    eax; pdwType
0x40a0dd  lea     eax, [ebp+Data]
0x40a0e0  push    eax; srrfFlags
0x40a0e1  test    ebx, ebx
0x40a0e3  jz      short loc_40A0FC
0x40a0e5  push    0; pdwType
0x40a0e7  push    18h; dwFlags
0x40a0e9  push    edi; lpValue
0x40a0ea  push    offset aSoftwareMicros_3; "Software\\Microsoft\\Internet Explorer"...
0x40a0ef  push    80000002h; hkey
0x40a0f4  call    ds:__imp__RegGetValueW@28; RegGetValueW(x,x,x,x,x,x,x)
0x40a0fa  jmp     short loc_40A105
0x40a0fc  push    ecx; pwszValue
0x40a0fd  push    ecx; pwszKey
0x40a0fe  mov     edx, edi
0x40a100  call    _SHRegGetValueFromHKCUHKLM@24; SHRegGetValueFromHKCUHKLM(x,x,x,x,x,x)
0x40a105  test    eax, eax
0x40a107  jz      short loc_40A110
0x40a109  mov     dword ptr [ebp+Data], 0
0x40a110  mov     eax, [ebp+arg_C]
0x40a113  test    eax, eax
0x40a115  jz      short loc_40A12C
0x40a117  mov     dword ptr [eax], 0
0x40a11d  jmp     short loc_40A12C
0x40a11f  mov     eax, [ebp+arg_C]
0x40a122  test    eax, eax
0x40a124  jz      short loc_40A12C
0x40a126  mov     dword ptr [eax], 1
0x40a12c  mov     eax, dword ptr [ebp+Data]
0x40a12f  pop     edi
0x40a130  pop     esi
0x40a131  pop     ebx
0x40a132  leave
0x40a133  retn    10h
```
