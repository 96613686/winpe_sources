# CServerObject_ComRegistration::Load_LocalServer32(ushort const *)

- ea: `0x140013334`
- end: `0x140013424`
- name: `?Load_LocalServer32@CServerObject_ComRegistration@@AEAAJPEBG@Z`
- size: `240`
- prototype: `__int64 __fastcall(CServerObject_ComRegistration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014f2c`

## callees

- `0x140013334`
- `0x140014860`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013412`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013412`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400133ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400133ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001341c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001341c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400133b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400133b9`

## pseudocode

```c
__int64 __fastcall CServerObject_ComRegistration::Load_LocalServer32(
        CServerObject_ComRegistration *this,
        const unsigned __int16 *a2)
{
  int v3; // edi
  int v4; // r9d
  const WCHAR *v6; // rdx
  HKEY v7; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  lpSubKey = 0;
  v3 = WmiHelper::ConcatenateStrings(2u, (BSTR *)&lpSubKey, a2, L"LocalServer32");
  if ( v3 >= 0 )
  {
    v4 = 512;
    if ( *((_DWORD *)this + 404) != 32 )
      v4 = 256;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, v4 | 0x20019, &hKey) )
    {
      v6 = CServerObject_ComRegistration::s_Strings_Reg_Null;
      v7 = hKey;
      *((_DWORD *)this + 5) = 1;
      Type = 1;
      *((_QWORD *)this + 1) = 2;
      cbData = 520;
      RegQueryValueExW(v7, v6, 0, &Type, (LPBYTE)this + 576, &cbData);
      RegCloseKey(hKey);
    }
    SysFreeString((BSTR)lpSubKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140013334  mov     [rsp-8+arg_0], rbx
0x140013339  mov     [rsp-8+arg_8], rdi
0x14001333e  push    rbp
0x14001333f  mov     rbp, rsp
0x140013342  sub     rsp, 40h
0x140013346  mov     rbx, rcx
0x140013349  mov     [rbp+lpSubKey], 0
0x140013351  mov     r8, rdx
0x140013354  lea     r9, aLocalserver32; "LocalServer32"
0x14001335b  lea     rdx, [rbp+lpSubKey]
0x14001335f  mov     ecx, 2
0x140013364  call    ?ConcatenateStrings@WmiHelper@@SA?AW4WmiStatusCode@@KPEAPEAGZZ; WmiHelper::ConcatenateStrings(ulong,ushort * *,...)
0x140013369  mov     edi, eax
0x14001336b  test    eax, eax
0x14001336d  js      short loc_1400133BF
0x14001336f  cmp     dword ptr [rbx+650h], 20h ; ' '
0x140013376  mov     eax, 100h
0x14001337b  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14001337f  mov     r9d, 200h
0x140013385  cmovnz  r9d, eax
0x140013389  mov     [rbp+hKey], 0
0x140013391  lea     rax, [rbp+hKey]
0x140013395  or      r9d, 20019h; samDesired
0x14001339c  xor     r8d, r8d; ulOptions
0x14001339f  mov     [rsp+40h+phkResult], rax; phkResult
0x1400133a4  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1400133ab  call    cs:__imp_RegOpenKeyExW
0x1400133b1  test    eax, eax
0x1400133b3  jz      short loc_1400133D1
0x1400133b5  mov     rcx, [rbp+lpSubKey]; bstrString
0x1400133b9  call    cs:__imp_SysFreeString
0x1400133bf  mov     rbx, [rsp+40h+arg_0]
0x1400133c4  mov     eax, edi
0x1400133c6  mov     rdi, [rsp+40h+arg_8]
0x1400133cb  add     rsp, 40h
0x1400133cf  pop     rbp
0x1400133d0  retn
0x1400133d1  mov     rdx, cs:?s_Strings_Reg_Null@CServerObject_ComRegistration@@1PEBGEB; lpValueName
0x1400133d8  lea     rcx, [rbp+cbData]
0x1400133dc  mov     eax, 1
0x1400133e1  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x1400133e6  mov     rcx, [rbp+hKey]; hKey
0x1400133ea  lea     r9, [rbp+Type]; lpType
0x1400133ee  mov     [rbx+14h], eax
0x1400133f1  xor     r8d, r8d; lpReserved
0x1400133f4  mov     [rbp+Type], eax
0x1400133f7  lea     rax, [rbx+240h]
0x1400133fe  mov     [rsp+40h+phkResult], rax; lpData
0x140013403  mov     qword ptr [rbx+8], 2
0x14001340b  mov     [rbp+cbData], 208h
0x140013412  call    cs:__imp_RegQueryValueExW
0x140013418  mov     rcx, [rbp+hKey]; hKey
0x14001341c  call    cs:__imp_RegCloseKey
0x140013422  jmp     short loc_1400133B5
```
