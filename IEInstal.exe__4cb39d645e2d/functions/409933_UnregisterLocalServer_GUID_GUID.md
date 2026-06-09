# UnregisterLocalServer(_GUID,_GUID)

- ea: `0x409933`
- end: `0x409a21`
- name: `?UnregisterLocalServer@@YGJU_GUID@@U1@@Z`
- size: `238`
- prototype: `unsigned int __stdcall(GUID, GUID)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x409212`

## callees

- `0x409933`
- `0x40cb60`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x4099a1`
- `ADVAPI32!RegCloseKey` at `0x4099e2`
- `ADVAPI32!RegCloseKey` at `0x4099a1`
- `ADVAPI32!RegCloseKey` at `0x4099e2`
- `ADVAPI32!RegOpenKeyExW` at `0x409973`
- `ADVAPI32!RegOpenKeyExW` at `0x4099b4`
- `ADVAPI32!RegOpenKeyExW` at `0x409973`
- `ADVAPI32!RegOpenKeyExW` at `0x4099b4`
- `ADVAPI32!RegDeleteKeyW` at `0x409996`
- `ADVAPI32!RegDeleteKeyW` at `0x4099d7`
- `ADVAPI32!RegDeleteKeyW` at `0x409996`
- `ADVAPI32!RegDeleteKeyW` at `0x4099d7`
- `ole32!StringFromGUID2` at `0x409989`
- `ole32!StringFromGUID2` at `0x4099ca`
- `ole32!StringFromGUID2` at `0x409989`
- `ole32!StringFromGUID2` at `0x4099ca`

## string_xrefs

- `0x40996d`: `CLSID`

## pseudocode

```c
unsigned int __stdcall UnregisterLocalServer(GUID a1, GUID a2)
{
  LSTATUS v2; // edi
  LSTATUS v3; // esi
  unsigned int result; // eax
  HKEY hKey; // [esp+Ch] [ebp-7Ch] BYREF
  HKEY phkResult; // [esp+10h] [ebp-78h] BYREF
  GUID v7; // [esp+14h] [ebp-74h] BYREF
  GUID rguid; // [esp+24h] [ebp-64h] BYREF
  OLECHAR sz[40]; // [esp+34h] [ebp-54h] BYREF

  rguid = a1;
  v7 = a2;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &phkResult);
  if ( !v2 )
  {
    StringFromGUID2(&rguid, sz, 39);
    v2 = RegDeleteKeyW(phkResult, sz);
    RegCloseKey(phkResult);
  }
  v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, 0xF003Fu, &hKey);
  if ( v3 || (StringFromGUID2(&v7, sz, 39), v3 = RegDeleteKeyW(hKey, sz), RegCloseKey(hKey), v3) )
  {
    result = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      return v3;
  }
  else if ( v2 )
  {
    result = (unsigned __int16)v2 | 0x80070000;
    if ( v2 <= 0 )
      return v2;
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x409933  mov     edi, edi
0x409935  push    ebp
0x409936  mov     ebp, esp
0x409938  sub     esp, 7Ch
0x40993b  mov     eax, ___security_cookie
0x409940  xor     eax, ebp
0x409942  mov     [ebp+var_4], eax
0x409945  push    ebx
0x409946  push    esi
0x409947  push    edi
0x409948  lea     esi, [ebp+arg_0]
0x40994b  mov     ebx, 80000000h
0x409950  lea     edi, [ebp+rguid]
0x409953  movsd
0x409954  lea     eax, [ebp+phkResult]
0x409957  push    eax; phkResult
0x409958  movsd
0x409959  movsd
0x40995a  movsd
0x40995b  lea     esi, [ebp+arg_10]
0x40995e  lea     edi, [ebp+var_74]
0x409961  movsd
0x409962  movsd
0x409963  movsd
0x409964  movsd
0x409965  mov     esi, 0F003Fh
0x40996a  push    esi; samDesired
0x40996b  push    0; ulOptions
0x40996d  push    offset aClsid_0; "CLSID"
0x409972  push    ebx; hKey
0x409973  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x409979  mov     edi, eax
0x40997b  test    edi, edi
0x40997d  jnz     short loc_4099A7
0x40997f  push    27h ; '''; cchMax
0x409981  lea     eax, [ebp+sz]
0x409984  push    eax; lpsz
0x409985  lea     eax, [ebp+rguid]
0x409988  push    eax; rguid
0x409989  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x40998f  lea     eax, [ebp+sz]
0x409992  push    eax; lpSubKey
0x409993  push    [ebp+phkResult]; hKey
0x409996  call    ds:__imp__RegDeleteKeyW@8; RegDeleteKeyW(x,x)
0x40999c  push    [ebp+phkResult]; hKey
0x40999f  mov     edi, eax
0x4099a1  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4099a7  lea     eax, [ebp+hKey]
0x4099aa  push    eax; phkResult
0x4099ab  push    esi; samDesired
0x4099ac  push    0; ulOptions
0x4099ae  push    offset aAppid; "AppID"
0x4099b3  push    ebx; hKey
0x4099b4  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x4099ba  mov     esi, eax
0x4099bc  test    esi, esi
0x4099be  jnz     short loc_409A03
0x4099c0  push    27h ; '''; cchMax
0x4099c2  lea     eax, [ebp+sz]
0x4099c5  push    eax; lpsz
0x4099c6  lea     eax, [ebp+var_74]
0x4099c9  push    eax; rguid
0x4099ca  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x4099d0  lea     eax, [ebp+sz]
0x4099d3  push    eax; lpSubKey
0x4099d4  push    [ebp+hKey]; hKey
0x4099d7  call    ds:__imp__RegDeleteKeyW@8; RegDeleteKeyW(x,x)
0x4099dd  push    [ebp+hKey]; hKey
0x4099e0  mov     esi, eax
0x4099e2  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4099e8  test    esi, esi
0x4099ea  jnz     short loc_409A03
0x4099ec  test    edi, edi
0x4099ee  jnz     short loc_4099F4
0x4099f0  xor     eax, eax
0x4099f2  jmp     short loc_409A10
0x4099f4  movzx   eax, di
0x4099f7  or      eax, 80070000h
0x4099fc  test    edi, edi
0x4099fe  cmovle  eax, edi
0x409a01  jmp     short loc_409A10
0x409a03  movzx   eax, si
0x409a06  or      eax, 80070000h
0x409a0b  test    esi, esi
0x409a0d  cmovle  eax, esi
0x409a10  mov     ecx, [ebp+var_4]
0x409a13  pop     edi
0x409a14  pop     esi
0x409a15  xor     ecx, ebp; StackCookie
0x409a17  pop     ebx
0x409a18  call    @__security_check_cookie@4; __security_check_cookie(x)
0x409a1d  leave
0x409a1e  retn    20h ; ' '
```
