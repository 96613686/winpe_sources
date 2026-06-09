# CActiveXInstallBroker::UpdateSharedDlls(char const *)

- ea: `0x40351a`
- end: `0x4035e2`
- name: `?UpdateSharedDlls@CActiveXInstallBroker@@AAEJPBD@Z`
- size: `200`
- prototype: `unsigned int __thiscall(CActiveXInstallBroker *this, const char *lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x405304`

## callees

- `0x40351a`
- `0x409dbc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x4035d3`
- `ADVAPI32!RegCloseKey` at `0x4035d3`
- `ADVAPI32!RegCreateKeyW` at `0x403573`
- `ADVAPI32!RegCreateKeyW` at `0x403573`
- `ADVAPI32!RegOpenKeyExW` at `0x40355d`
- `ADVAPI32!RegOpenKeyExW` at `0x40355d`
- `ADVAPI32!RegSetValueExA` at `0x4035b3`
- `ADVAPI32!RegSetValueExA` at `0x4035b3`
- `ADVAPI32!RegQueryValueExA` at `0x403590`
- `ADVAPI32!RegQueryValueExA` at `0x403590`

## string_xrefs

- `0x403555`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`
- `0x40356b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`

## pseudocode

```c
unsigned int __thiscall CActiveXInstallBroker::UpdateSharedDlls(CActiveXInstallBroker *this, const char *lpValueName)
{
  unsigned int RegistrationRootKeyFromIntegrityLevel; // esi
  LSTATUS v3; // eax
  int v4; // eax
  DWORD Type; // [esp+Ch] [ebp-14h] BYREF
  DWORD cbData; // [esp+10h] [ebp-10h] BYREF
  HKEY hKey; // [esp+14h] [ebp-Ch] BYREF
  BYTE Data[4]; // [esp+18h] [ebp-8h] BYREF
  HKEY phkResult; // [esp+1Ch] [ebp-4h] BYREF

  hKey = 0;
  phkResult = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  RegistrationRootKeyFromIntegrityLevel = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
  if ( !RegistrationRootKeyFromIntegrityLevel )
  {
    if ( RegOpenKeyExW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls", 0, 0x2001Fu, &phkResult)
      && (v3 = RegCreateKeyW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls", &phkResult)) != 0
      || (RegQueryValueExA(phkResult, lpValueName, 0, &Type, Data, &cbData) ? (v4 = 1) : (v4 = *(_DWORD *)Data + 1),
          *(_DWORD *)Data = v4,
          (v3 = RegSetValueExA(phkResult, lpValueName, 0, 4u, Data, 4u)) != 0) )
    {
      RegistrationRootKeyFromIntegrityLevel = (unsigned __int16)v3 | 0x80070000;
      if ( v3 <= 0 )
        RegistrationRootKeyFromIntegrityLevel = v3;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return RegistrationRootKeyFromIntegrityLevel;
}

```

## disassembly

```asm
0x40351a  mov     edi, edi
0x40351c  push    ebp
0x40351d  mov     ebp, esp
0x40351f  sub     esp, 14h
0x403522  push    ebx
0x403523  push    esi
0x403524  push    edi; HKEY *
0x403525  xor     edi, edi
0x403527  lea     ecx, [ebp+hKey]
0x40352a  push    4
0x40352c  pop     ebx
0x40352d  mov     [ebp+hKey], edi
0x403530  mov     [ebp+phkResult], edi
0x403533  mov     [ebp+Type], edi
0x403536  mov     dword ptr [ebp+Data], edi
0x403539  mov     [ebp+cbData], ebx
0x40353c  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YGJPAPAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x403541  mov     esi, eax
0x403543  test    esi, esi
0x403545  jnz     loc_4035CB
0x40354b  lea     eax, [ebp+phkResult]
0x40354e  push    eax; phkResult
0x40354f  push    2001Fh; samDesired
0x403554  push    edi; ulOptions
0x403555  push    offset aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x40355a  push    [ebp+hKey]; hKey
0x40355d  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x403563  test    eax, eax
0x403565  jz      short loc_40357D
0x403567  lea     eax, [ebp+phkResult]
0x40356a  push    eax; phkResult
0x40356b  push    offset aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x403570  push    [ebp+hKey]; hKey
0x403573  call    ds:__imp__RegCreateKeyW@12; RegCreateKeyW(x,x,x)
0x403579  test    eax, eax
0x40357b  jnz     short loc_4035BD
0x40357d  lea     eax, [ebp+cbData]
0x403580  push    eax; lpcbData
0x403581  lea     eax, [ebp+Data]
0x403584  push    eax; lpData
0x403585  lea     eax, [ebp+Type]
0x403588  push    eax; lpType
0x403589  push    edi; lpReserved
0x40358a  push    [ebp+lpValueName]; lpValueName
0x40358d  push    [ebp+phkResult]; hKey
0x403590  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x403596  test    eax, eax
0x403598  jnz     short loc_4035A0
0x40359a  mov     eax, dword ptr [ebp+Data]
0x40359d  inc     eax
0x40359e  jmp     short loc_4035A3
0x4035a0  xor     eax, eax
0x4035a2  inc     eax
0x4035a3  push    ebx; cbData
0x4035a4  mov     dword ptr [ebp+Data], eax
0x4035a7  lea     eax, [ebp+Data]
0x4035aa  push    eax; lpData
0x4035ab  push    ebx; dwType
0x4035ac  push    edi; Reserved
0x4035ad  push    [ebp+lpValueName]; lpValueName
0x4035b0  push    [ebp+phkResult]; hKey
0x4035b3  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x4035b9  test    eax, eax
0x4035bb  jz      short loc_4035CB
0x4035bd  movzx   esi, ax
0x4035c0  or      esi, 80070000h
0x4035c6  test    eax, eax
0x4035c8  cmovle  esi, eax
0x4035cb  cmp     [ebp+phkResult], edi
0x4035ce  jz      short loc_4035D9
0x4035d0  push    [ebp+phkResult]; hKey
0x4035d3  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4035d9  pop     edi
0x4035da  mov     eax, esi
0x4035dc  pop     esi
0x4035dd  pop     ebx
0x4035de  leave
0x4035df  retn    4
```
