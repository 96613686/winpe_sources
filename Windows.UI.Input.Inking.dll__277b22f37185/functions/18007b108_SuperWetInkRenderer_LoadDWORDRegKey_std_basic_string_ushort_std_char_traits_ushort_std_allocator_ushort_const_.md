# SuperWetInkRenderer::LoadDWORDRegKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18007b108`
- end: `0x18007b1cc`
- name: `?LoadDWORDRegKey@SuperWetInkRenderer@@SAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z`
- size: `196`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007b1d4`
- `0x18007ccc0`
- `0x18007d198`
- `0x18007df50`

## callees

- `0x180079e58`
- `0x18007b108`
- `0x18007b95c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b150`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b150`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007b196`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007b196`

## pseudocode

```c
__int64 __fastcall SuperWetInkRenderer::LoadDWORDRegKey(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  const WCHAR *v5; // rcx
  unsigned int v6; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  if ( (unsigned __int8)((__int64 (*)(void))std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged)() )
    v5 = *(const WCHAR **)v5;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey) )
    goto LABEL_9;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(a2) )
    a2 = *(const WCHAR **)a2;
  if ( RegQueryValueExW(hKey, a2, 0, &Type, Data, &cbData) || Type != 4 || (v6 = *(_DWORD *)Data, cbData != 4) )
LABEL_9:
    v6 = a3;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x18007b108  mov     [rsp-8+arg_8], rbx
0x18007b10d  mov     [rsp-8+arg_10], rdi
0x18007b112  push    rbp
0x18007b113  mov     rbp, rsp
0x18007b116  sub     rsp, 40h
0x18007b11a  mov     edi, r8d
0x18007b11d  mov     [rbp+hKey], 0
0x18007b125  mov     rbx, rdx
0x18007b128  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18007b12d  test    al, al
0x18007b12f  jz      short loc_18007B134
0x18007b131  mov     rcx, [rcx]
0x18007b134  lea     rax, [rbp+hKey]
0x18007b138  mov     rdx, rcx; lpSubKey
0x18007b13b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007b142  mov     [rsp+40h+phkResult], rax; phkResult
0x18007b147  mov     r9d, 20019h; samDesired
0x18007b14d  xor     r8d, r8d; ulOptions
0x18007b150  call    cs:__imp_RegOpenKeyExW
0x18007b156  test    eax, eax
0x18007b158  jnz     short loc_18007B1AF
0x18007b15a  mov     rcx, rbx
0x18007b15d  mov     dword ptr [rbp+Data], eax
0x18007b160  mov     [rbp+Type], eax
0x18007b163  mov     [rbp+cbData], 4
0x18007b16a  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18007b16f  test    al, al
0x18007b171  jz      short loc_18007B176
0x18007b173  mov     rbx, [rbx]
0x18007b176  mov     rcx, [rbp+hKey]; hKey
0x18007b17a  lea     rax, [rbp+cbData]
0x18007b17e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18007b183  lea     r9, [rbp+Type]; lpType
0x18007b187  lea     rax, [rbp+Data]
0x18007b18b  xor     r8d, r8d; lpReserved
0x18007b18e  mov     rdx, rbx; lpValueName
0x18007b191  mov     [rsp+40h+phkResult], rax; lpData
0x18007b196  call    cs:__imp_RegQueryValueExW
0x18007b19c  test    eax, eax
0x18007b19e  jnz     short loc_18007B1AF
0x18007b1a0  cmp     [rbp+Type], 4
0x18007b1a4  jnz     short loc_18007B1AF
0x18007b1a6  cmp     [rbp+cbData], 4
0x18007b1aa  mov     ebx, dword ptr [rbp+Data]
0x18007b1ad  jz      short loc_18007B1B1
0x18007b1af  mov     ebx, edi
0x18007b1b1  lea     rcx, [rbp+hKey]
0x18007b1b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007b1ba  mov     rdi, [rsp+40h+arg_10]
0x18007b1bf  mov     eax, ebx
0x18007b1c1  mov     rbx, [rsp+40h+arg_8]
0x18007b1c6  add     rsp, 40h
0x18007b1ca  pop     rbp
0x18007b1cb  retn
```
