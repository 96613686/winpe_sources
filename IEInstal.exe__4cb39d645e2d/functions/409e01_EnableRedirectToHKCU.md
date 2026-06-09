# EnableRedirectToHKCU()

- ea: `0x409e01`
- end: `0x409e97`
- name: `_EnableRedirectToHKCU@0`
- size: `150`
- prototype: `unsigned int __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x4044ae`

## callees

- `0x409e01`
- `0x409e9d`
- `0x409f13`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x409e6e`
- `ADVAPI32!RegCloseKey` at `0x409e77`
- `ADVAPI32!RegCloseKey` at `0x409e6e`
- `ADVAPI32!RegCloseKey` at `0x409e77`
- `ADVAPI32!RegOpenKeyExW` at `0x409e44`
- `ADVAPI32!RegOpenKeyExW` at `0x409e44`
- `ADVAPI32!RegOpenCurrentUser` at `0x409e14`
- `ADVAPI32!RegOpenCurrentUser` at `0x409e14`
- `ADVAPI32!RegOverridePredefKey` at `0x409e28`
- `ADVAPI32!RegOverridePredefKey` at `0x409e58`
- `ADVAPI32!RegOverridePredefKey` at `0x409e28`
- `ADVAPI32!RegOverridePredefKey` at `0x409e58`

## pseudocode

```c
unsigned int __stdcall EnableRedirectToHKCU()
{
  LSTATUS inited; // esi
  unsigned int result; // eax
  HKEY phkResult; // [esp+8h] [ebp-8h] BYREF
  HKEY hNewHKey; // [esp+Ch] [ebp-4h] BYREF

  inited = RegOpenCurrentUser(0xF003Fu, &phkResult);
  if ( inited )
    goto LABEL_8;
  inited = RegOverridePredefKey(HKEY_LOCAL_MACHINE, phkResult);
  if ( !inited )
  {
    inited = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Classes", 0, 0xF003Fu, &hNewHKey);
    if ( !inited )
    {
      inited = RegOverridePredefKey(HKEY_CLASSES_ROOT, hNewHKey);
      if ( !inited )
        inited = InitDetoursRedirectToHKCU();
      RegCloseKey(hNewHKey);
    }
  }
  RegCloseKey(phkResult);
  if ( inited )
LABEL_8:
    DestroyDetoursRedirectToHKCU();
  result = (unsigned __int16)inited | 0x80070000;
  if ( inited <= 0 )
    return inited;
  return result;
}

```

## disassembly

```asm
0x409e01  mov     edi, edi
0x409e03  push    ebp
0x409e04  mov     ebp, esp
0x409e06  push    ecx
0x409e07  push    ecx
0x409e08  push    esi
0x409e09  push    edi
0x409e0a  lea     eax, [ebp+phkResult]
0x409e0d  mov     edi, 0F003Fh
0x409e12  push    eax; phkResult
0x409e13  push    edi; samDesired
0x409e14  call    ds:__imp__RegOpenCurrentUser@8; RegOpenCurrentUser(x,x)
0x409e1a  mov     esi, eax
0x409e1c  test    esi, esi
0x409e1e  jnz     short loc_409E81
0x409e20  push    [ebp+phkResult]; hNewHKey
0x409e23  push    80000002h; hKey
0x409e28  call    ds:__imp__RegOverridePredefKey@8; RegOverridePredefKey(x,x)
0x409e2e  mov     esi, eax
0x409e30  test    esi, esi
0x409e32  jnz     short loc_409E74
0x409e34  lea     eax, [ebp+hNewHKey]
0x409e37  push    eax; phkResult
0x409e38  push    edi; samDesired
0x409e39  push    esi; ulOptions
0x409e3a  push    offset aSoftwareClasse; "Software\\Classes"
0x409e3f  push    80000001h; hKey
0x409e44  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x409e4a  mov     esi, eax
0x409e4c  test    esi, esi
0x409e4e  jnz     short loc_409E74
0x409e50  push    [ebp+hNewHKey]; hNewHKey
0x409e53  push    80000000h; hKey
0x409e58  call    ds:__imp__RegOverridePredefKey@8; RegOverridePredefKey(x,x)
0x409e5e  mov     esi, eax
0x409e60  test    esi, esi
0x409e62  jnz     short loc_409E6B
0x409e64  call    ?InitDetoursRedirectToHKCU@@YGJXZ; InitDetoursRedirectToHKCU(void)
0x409e69  mov     esi, eax
0x409e6b  push    [ebp+hNewHKey]; hKey
0x409e6e  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x409e74  push    [ebp+phkResult]; hKey
0x409e77  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x409e7d  test    esi, esi
0x409e7f  jz      short loc_409E86
0x409e81  call    ?DestroyDetoursRedirectToHKCU@@YGJXZ; DestroyDetoursRedirectToHKCU(void)
0x409e86  movzx   eax, si
0x409e89  or      eax, 80070000h
0x409e8e  test    esi, esi
0x409e90  pop     edi
0x409e91  cmovle  eax, esi
0x409e94  pop     esi
0x409e95  leave
0x409e96  retn
```
