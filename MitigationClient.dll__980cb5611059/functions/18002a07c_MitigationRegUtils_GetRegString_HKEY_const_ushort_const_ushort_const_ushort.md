# MitigationRegUtils::GetRegString(HKEY__ * const &,ushort const *,ushort const *,ushort * *)

- ea: `0x18002a07c`
- end: `0x18002a13e`
- name: `?GetRegString@MitigationRegUtils@@CAJAEBQEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `194`
- prototype: `static int(HKEY *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029dbc`
- `0x180033994`
- `0x180033b48`

## callees

- `0x180019f10`
- `0x180024550`
- `0x18002a07c`
- `0x18002a144`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a0c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a0c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a102`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a102`

## pseudocode

```c
__int64 __fastcall MitigationRegUtils::GetRegString(
        HKEY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY hKey[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+8h] BYREF

  Type = 0;
  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  v8 = RegOpenKeyExW(*a1, a2, 0, 0x20019u, hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( RegQueryValueExW(hKey[0], a3, 0, &Type, 0, 0) )
      v9 = -2147024894;
    else
      v9 = MitigationRegUtils::GetRegStringWithTypeCheck(Type, hKey[0], a3, a4);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002a07c  push    rbx
0x18002a07e  push    rbp
0x18002a07f  push    rsi
0x18002a080  push    rdi
0x18002a081  sub     rsp, 48h
0x18002a085  mov     rbx, rdx
0x18002a088  mov     [rsp+68h+Type], 0
0x18002a090  mov     rdi, rcx
0x18002a093  mov     [rsp+68h+hKey], 0
0x18002a09c  xor     edx, edx
0x18002a09e  lea     rcx, [rsp+68h+hKey]
0x18002a0a3  mov     rbp, r9
0x18002a0a6  mov     rsi, r8
0x18002a0a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a0ae  mov     rcx, [rdi]; hKey
0x18002a0b1  lea     rax, [rsp+68h+hKey]
0x18002a0b6  mov     r9d, 20019h; samDesired
0x18002a0bc  mov     [rsp+68h+phkResult], rax; phkResult
0x18002a0c1  xor     r8d, r8d; ulOptions
0x18002a0c4  mov     rdx, rbx; lpSubKey
0x18002a0c7  call    cs:__imp_RegOpenKeyExW
0x18002a0cd  mov     ebx, eax
0x18002a0cf  test    eax, eax
0x18002a0d1  jle     short loc_18002A0DC
0x18002a0d3  movzx   ebx, ax
0x18002a0d6  or      ebx, 80070000h
0x18002a0dc  test    ebx, ebx
0x18002a0de  js      short loc_18002A129
0x18002a0e0  mov     rcx, [rsp+68h+hKey]; hKey
0x18002a0e5  lea     r9, [rsp+68h+Type]; lpType
0x18002a0ea  mov     [rsp+68h+lpcbData], 0; lpcbData
0x18002a0f3  xor     r8d, r8d; lpReserved
0x18002a0f6  mov     rdx, rsi; lpValueName
0x18002a0f9  mov     [rsp+68h+phkResult], 0; lpData
0x18002a102  call    cs:__imp_RegQueryValueExW
0x18002a108  test    eax, eax
0x18002a10a  jz      short loc_18002A113
0x18002a10c  mov     ebx, 80070002h
0x18002a111  jmp     short loc_18002A129
0x18002a113  mov     rdx, [rsp+68h+hKey]; HKEY
0x18002a118  mov     r9, rbp; unsigned __int16 **
0x18002a11b  mov     ecx, [rsp+68h+Type]; unsigned int
0x18002a11f  mov     r8, rsi; unsigned __int16 *
0x18002a122  call    ?GetRegStringWithTypeCheck@MitigationRegUtils@@CAJKPEAUHKEY__@@PEBGPEAPEAG@Z; MitigationRegUtils::GetRegStringWithTypeCheck(ulong,HKEY__ *,ushort const *,ushort * *)
0x18002a127  mov     ebx, eax
0x18002a129  lea     rcx, [rsp+68h+hKey]
0x18002a12e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a133  mov     eax, ebx
0x18002a135  add     rsp, 48h
0x18002a139  pop     rdi
0x18002a13a  pop     rsi
0x18002a13b  pop     rbp
0x18002a13c  pop     rbx
0x18002a13d  retn
```
