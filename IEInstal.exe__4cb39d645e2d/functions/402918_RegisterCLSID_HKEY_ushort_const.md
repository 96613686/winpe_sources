# RegisterCLSID(HKEY__ *,ushort const *)

- ea: `0x402918`
- end: `0x402ade`
- name: `?RegisterCLSID@@YGKPAUHKEY__@@PBG@Z`
- size: `454`
- prototype: `LSTATUS __fastcall(HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x409551`

## callees

- `0x402625`
- `0x402918`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x4029be`
- `ADVAPI32!RegSetValueExW` at `0x402a24`
- `ADVAPI32!RegSetValueExW` at `0x402ab9`
- `ADVAPI32!RegSetValueExW` at `0x4029be`
- `ADVAPI32!RegSetValueExW` at `0x402a24`
- `ADVAPI32!RegSetValueExW` at `0x402ab9`
- `ADVAPI32!RegCreateKeyExW` at `0x4029f1`
- `ADVAPI32!RegCreateKeyExW` at `0x4029f1`
- `ADVAPI32!RegCloseKey` at `0x402ac7`
- `ADVAPI32!RegCloseKey` at `0x402ac7`

## pseudocode

```c
LSTATUS __fastcall RegisterCLSID(HKEY a1, unsigned __int16 *a2)
{
  LSTATUS v4; // esi
  unsigned int v6; // [esp+0h] [ebp-454h]
  unsigned int v7; // [esp+0h] [ebp-454h]
  unsigned int v8; // [esp+0h] [ebp-454h]
  unsigned int v9; // [esp+0h] [ebp-454h]
  const unsigned __int16 *v10; // [esp+4h] [ebp-450h]
  const unsigned __int16 *v11; // [esp+4h] [ebp-450h]
  const unsigned __int16 *v12; // [esp+4h] [ebp-450h]
  const unsigned __int16 *v13; // [esp+4h] [ebp-450h]
  DWORD dwDisposition; // [esp+Ch] [ebp-448h] BYREF
  BYTE v15[4]; // [esp+10h] [ebp-444h] BYREF
  HKEY phkResult; // [esp+14h] [ebp-440h] BYREF
  BYTE v17[4]; // [esp+18h] [ebp-43Ch] BYREF
  BYTE v18[536]; // [esp+1Ch] [ebp-438h] BYREF
  BYTE Data[4]; // [esp+234h] [ebp-220h] BYREF
  _BYTE v20[536]; // [esp+238h] [ebp-21Ch] BYREF

  *(_DWORD *)Data = 64;
  memset(v20, 0, sizeof(v20));
  v4 = StringCchCatW(a2, v6, v10);
  if ( !v4 )
  {
    v4 = StringCchCatW(L",-1001", v7, v11);
    if ( !v4 )
    {
      v4 = RegSetValueExW(a1, L"LocalizedString", 0, 2u, Data, 2 * wcslen((const unsigned __int16 *)Data) + 2);
      if ( !v4 )
      {
        v4 = RegCreateKeyExW(a1, L"Elevation", 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
        if ( !v4 )
        {
          *(_DWORD *)v15 = 1;
          v4 = RegSetValueExW(phkResult, L"Enabled", 0, 4u, v15, 4u);
          if ( !v4 )
          {
            *(_DWORD *)v17 = 64;
            memset(v18, 0, sizeof(v18));
            v4 = StringCchCatW(a2, v8, v12);
            if ( !v4 )
            {
              v4 = StringCchCatW(L",-1002", v9, v13);
              if ( !v4 )
                v4 = RegSetValueExW(
                       phkResult,
                       L"IconReference",
                       0,
                       2u,
                       v17,
                       2 * wcslen((const unsigned __int16 *)v17) + 2);
            }
          }
          RegCloseKey(phkResult);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x402918  mov     edi, edi
0x40291a  push    ebp
0x40291b  mov     ebp, esp
0x40291d  sub     esp, 448h
0x402923  mov     eax, ___security_cookie
0x402928  xor     eax, ebp
0x40292a  mov     [ebp+var_4], eax
0x40292d  push    ebx
0x40292e  push    esi; unsigned __int16 *
0x40292f  push    edi; unsigned int
0x402930  push    218h; Size
0x402935  lea     eax, [ebp+var_21C]
0x40293b  mov     dword ptr [ebp+Data], 40h ; '@'
0x402945  push    0; Val
0x402947  push    eax; void *
0x402948  mov     ebx, edx
0x40294a  mov     edi, ecx
0x40294c  call    _memset
0x402951  add     esp, 0Ch
0x402954  lea     ecx, [ebp+Data]
0x40295a  mov     edx, 10Eh
0x40295f  push    ebx; unsigned __int16 *
0x402960  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x402965  mov     esi, eax
0x402967  test    esi, esi
0x402969  jnz     loc_402ACD
0x40296f  push    offset a1001; ",-1001"
0x402974  mov     edx, 10Eh
0x402979  lea     ecx, [ebp+Data]
0x40297f  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x402984  mov     esi, eax
0x402986  test    esi, esi
0x402988  jnz     loc_402ACD
0x40298e  lea     ecx, [ebp+Data]
0x402994  lea     edx, [ecx+2]
0x402997  mov     ax, [ecx]
0x40299a  add     ecx, 2
0x40299d  cmp     ax, si
0x4029a0  jnz     short loc_402997
0x4029a2  sub     ecx, edx
0x4029a4  sar     ecx, 1
0x4029a6  lea     eax, ds:2[ecx*2]
0x4029ad  push    eax; cbData
0x4029ae  lea     eax, [ebp+Data]
0x4029b4  push    eax; lpData
0x4029b5  push    2; dwType
0x4029b7  push    esi; Reserved
0x4029b8  push    offset aLocalizedstrin; "LocalizedString"
0x4029bd  push    edi; hKey
0x4029be  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x4029c4  mov     esi, eax
0x4029c6  test    esi, esi
0x4029c8  jnz     loc_402ACD
0x4029ce  lea     eax, [ebp+dwDisposition]
0x4029d4  push    eax; lpdwDisposition
0x4029d5  lea     eax, [ebp+phkResult]
0x4029db  push    eax; phkResult
0x4029dc  xor     eax, eax
0x4029de  push    eax; lpSecurityAttributes
0x4029df  push    0F003Fh; samDesired
0x4029e4  push    eax; dwOptions
0x4029e5  push    offset Class; "REG_SZ"
0x4029ea  push    eax; Reserved
0x4029eb  push    offset SubKey; "Elevation"
0x4029f0  push    edi; hKey
0x4029f1  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x4029f7  mov     esi, eax
0x4029f9  test    esi, esi
0x4029fb  jnz     loc_402ACD
0x402a01  push    4; cbData
0x402a03  lea     eax, [ebp+var_444]
0x402a09  mov     dword ptr [ebp+var_444], 1
0x402a13  push    eax; lpData
0x402a14  push    4; dwType
0x402a16  xor     edi, edi
0x402a18  push    edi; Reserved
0x402a19  push    offset aEnabled; "Enabled"
0x402a1e  push    [ebp+phkResult]; hKey
0x402a24  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x402a2a  mov     esi, eax
0x402a2c  test    esi, esi
0x402a2e  jnz     loc_402AC1
0x402a34  push    218h; Size
0x402a39  lea     eax, [ebp+var_438]
0x402a3f  mov     dword ptr [ebp+var_43C], 40h ; '@'
0x402a49  push    edi; Val
0x402a4a  push    eax; void *
0x402a4b  call    _memset
0x402a50  add     esp, 0Ch
0x402a53  lea     ecx, [ebp+var_43C]
0x402a59  push    ebx; unsigned __int16 *
0x402a5a  mov     ebx, 10Eh
0x402a5f  mov     edx, ebx
0x402a61  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x402a66  mov     esi, eax
0x402a68  test    esi, esi
0x402a6a  jnz     short loc_402AC1
0x402a6c  push    offset a1002; ",-1002"
0x402a71  mov     edx, ebx
0x402a73  lea     ecx, [ebp+var_43C]
0x402a79  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x402a7e  mov     esi, eax
0x402a80  test    esi, esi
0x402a82  jnz     short loc_402AC1
0x402a84  lea     ecx, [ebp+var_43C]
0x402a8a  lea     edx, [ecx+2]
0x402a8d  mov     ax, [ecx]
0x402a90  add     ecx, 2
0x402a93  cmp     ax, di
0x402a96  jnz     short loc_402A8D
0x402a98  sub     ecx, edx
0x402a9a  sar     ecx, 1
0x402a9c  lea     eax, ds:2[ecx*2]
0x402aa3  push    eax; cbData
0x402aa4  lea     eax, [ebp+var_43C]
0x402aaa  push    eax; lpData
0x402aab  push    2; dwType
0x402aad  push    edi; Reserved
0x402aae  push    offset aIconreference; "IconReference"
0x402ab3  push    [ebp+phkResult]; hKey
0x402ab9  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x402abf  mov     esi, eax
0x402ac1  push    [ebp+phkResult]; hKey
0x402ac7  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x402acd  mov     ecx, [ebp+var_4]
0x402ad0  mov     eax, esi
0x402ad2  pop     edi
0x402ad3  pop     esi
0x402ad4  xor     ecx, ebp; StackCookie
0x402ad6  pop     ebx
0x402ad7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x402adc  leave
0x402add  retn
```
