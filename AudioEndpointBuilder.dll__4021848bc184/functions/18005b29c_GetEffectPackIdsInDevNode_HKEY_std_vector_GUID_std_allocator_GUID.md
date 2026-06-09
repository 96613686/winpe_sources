# GetEffectPackIdsInDevNode(HKEY__ *,std::vector<_GUID,std::allocator<_GUID>> &)

- ea: `0x18005b29c`
- end: `0x18005b3a7`
- name: `?GetEffectPackIdsInDevNode@@YAXPEAUHKEY__@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@Z`
- size: `267`
- prototype: `LSTATUS __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b434`

## callees

- `0x18001deb0`
- `0x18003e920`
- `0x18005b0cc`
- `0x18005b29c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b37d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b37d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b2f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b2f3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b33c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b33c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005b358`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005b358`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
LSTATUS __fastcall GetEffectPackIdsInDevNode(HKEY hKey, __int64 a2)
{
  LSTATUS result; // eax
  DWORD i; // ebx
  const char *v6; // r9
  HKEY hKeya; // [rsp+40h] [rbp-438h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-430h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-428h] BYREF
  WCHAR Name[512]; // [rsp+60h] [rbp-418h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+0h]

  hKeya = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKeya,
    0);
  result = RegOpenKeyExW(hKey, L"EffectPackRegistration\\", 0, 0x20019u, &hKeya);
  if ( !result )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 512;
      result = RegEnumKeyExW(hKeya, i, Name, &cchName, 0, 0, 0, 0);
      if ( result )
        break;
      pclsid = 0;
      if ( CLSIDFromString(Name, &pclsid) >= 0 )
      {
        try
        {
          std::vector<_GUID>::emplace_back<_GUID &>(a2, &pclsid);
        }
        catch ( ... )
        {
          return wil::details::in1diag3::Log_CaughtException(
                   retaddr,
                   (void *)0x6C,
                   (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\globalapo.cpp",
                   v6);
        }
      }
    }
  }
  if ( hKeya )
    return RegCloseKey(hKeya);
  return result;
}

```

## disassembly

```asm
0x18005b29c  mov     [rsp+arg_10], rbx
0x18005b2a1  push    rdi
0x18005b2a2  sub     rsp, 470h
0x18005b2a9  mov     rax, cs:__security_cookie
0x18005b2b0  xor     rax, rsp
0x18005b2b3  mov     [rsp+478h+var_18], rax
0x18005b2bb  mov     rdi, rdx
0x18005b2be  mov     rbx, rcx
0x18005b2c1  mov     [rsp+478h+hKey], 0
0x18005b2ca  xor     edx, edx
0x18005b2cc  lea     rcx, [rsp+478h+hKey]
0x18005b2d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005b2d6  lea     rax, [rsp+478h+hKey]
0x18005b2db  mov     [rsp+478h+phkResult], rax; phkResult
0x18005b2e0  mov     r9d, 20019h; samDesired
0x18005b2e6  xor     r8d, r8d; ulOptions
0x18005b2e9  lea     rdx, aEffectpackregi; "EffectPackRegistration\\"
0x18005b2f0  mov     rcx, rbx; hKey
0x18005b2f3  call    cs:__imp_RegOpenKeyExW
0x18005b2f9  test    eax, eax
0x18005b2fb  jnz     short loc_18005B373
0x18005b2fd  xor     ebx, ebx
0x18005b2ff  mov     [rsp+478h+cchName], 200h
0x18005b307  mov     [rsp+478h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18005b310  mov     [rsp+478h+lpcchClass], 0; lpcchClass
0x18005b319  mov     [rsp+478h+lpClass], 0; lpClass
0x18005b322  mov     [rsp+478h+phkResult], 0; lpReserved
0x18005b32b  lea     r9, [rsp+478h+cchName]; lpcchName
0x18005b330  lea     r8, [rsp+478h+Name]; lpName
0x18005b335  mov     edx, ebx; dwIndex
0x18005b337  mov     rcx, [rsp+478h+hKey]; hKey
0x18005b33c  call    cs:__imp_RegEnumKeyExW
0x18005b342  test    eax, eax
0x18005b344  jnz     short loc_18005B373
0x18005b346  xorps   xmm0, xmm0
0x18005b349  movups  xmmword ptr [rsp+478h+pclsid.Data1], xmm0
0x18005b34e  lea     rdx, [rsp+478h+pclsid]; pclsid
0x18005b353  lea     rcx, [rsp+478h+Name]; lpsz
0x18005b358  call    cs:__imp_CLSIDFromString
0x18005b35e  test    eax, eax
0x18005b360  js      short loc_18005B36F
0x18005b362  lea     rdx, [rsp+478h+pclsid]
0x18005b367  mov     rcx, rdi
0x18005b36a  call    ??$emplace_back@AEAU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAU_GUID@@AEAU2@@Z; std::vector<_GUID>::emplace_back<_GUID &>(_GUID &)
0x18005b36f  inc     ebx
0x18005b371  jmp     short loc_18005B2FF
0x18005b373  mov     rcx, [rsp+478h+hKey]; hKey
0x18005b378  test    rcx, rcx
0x18005b37b  jz      short loc_18005B384
0x18005b37d  call    cs:__imp_RegCloseKey
0x18005b383  nop
0x18005b384  jmp     short $+2
0x18005b386  mov     rcx, [rsp+478h+var_18]
0x18005b38e  xor     rcx, rsp; StackCookie
0x18005b391  call    __security_check_cookie
0x18005b396  mov     rbx, [rsp+478h+arg_10]
0x18005b39e  add     rsp, 470h
0x18005b3a5  pop     rdi
0x18005b3a6  retn
```
