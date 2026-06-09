# HwCfgIndexToGuid

- ea: `0x14001a7e0`
- end: `0x14001a9e8`
- name: `HwCfgIndexToGuid`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14001c160`

## callees

- `0x14001a5e8`
- `0x14001a7e0`
- `0x140045ed2`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14001a8ed`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001a8ed`
- `ntdll!RtlGUIDFromString` at `0x14001a8ff`
- `ntdll!RtlGUIDFromString` at `0x14001a8ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14001a8c0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14001a8c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a921`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a9ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a9ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a9bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001a956`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001a956`

## pseudocode

```c
__int64 __fastcall HwCfgIndexToGuid(int a1, void *a2)
{
  unsigned int RootKey; // ebx
  DWORD i; // esi
  LSTATUS v6; // eax
  DWORD cchName; // [rsp+40h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-55h] BYREF
  DWORD Type; // [rsp+48h] [rbp-51h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-4Dh] BYREF
  HKEY v12; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  GUID Guid; // [rsp+70h] [rbp-29h] BYREF
  WCHAR Name[40]; // [rsp+80h] [rbp-19h] BYREF

  v12 = 0;
  hKey = 0;
  cchName = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  DestinationString = 0;
  Guid = 0;
  if ( !a2 )
    return 87;
  RootKey = HwCfgGetRootKey(0x20019u, &v12);
  if ( RootKey )
    goto LABEL_21;
  for ( i = 0; ; ++i )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    cchName = 39;
    v6 = RegEnumKeyExW(v12, i, Name, &cchName, 0, 0, 0, 0);
    RootKey = v6;
    if ( v6 == 234 )
      continue;
    if ( v6 )
      break;
    if ( cchName >= 0x26
      && !RtlInitUnicodeStringEx(&DestinationString, Name)
      && !RtlGUIDFromString(&DestinationString, &Guid)
      && !RegOpenKeyExW(v12, Name, 0, RootKey + 1, &hKey) )
    {
      cbData = 4;
      RootKey = RegQueryValueExW(hKey, L"Id", 0, &Type, Data, &cbData);
      if ( !RootKey && Type == 4 && cbData == 4 && a1 == *(_DWORD *)Data )
      {
        memcpy_0(a2, Name, 2LL * (cchName + 1));
        goto LABEL_21;
      }
    }
  }
  if ( v6 == 259 )
    RootKey = 1168;
LABEL_21:
  if ( v12 )
    RegCloseKey(v12);
  if ( hKey )
    RegCloseKey(hKey);
  return RootKey;
}

```

## disassembly

```asm
0x14001a7e0  mov     [rsp-8+arg_0], rbx
0x14001a7e5  mov     [rsp-8+arg_10], rsi
0x14001a7ea  push    rbp
0x14001a7eb  push    r14
0x14001a7ed  push    r15
0x14001a7ef  lea     rbp, [rsp-47h]
0x14001a7f4  sub     rsp, 0E0h
0x14001a7fb  mov     rax, cs:__security_cookie
0x14001a802  xor     rax, rsp
0x14001a805  mov     [rbp+57h+var_20], rax
0x14001a809  mov     [rbp+57h+var_A0], 0
0x14001a811  xorps   xmm0, xmm0
0x14001a814  mov     [rbp+57h+hKey], 0
0x14001a81c  xorps   xmm1, xmm1
0x14001a81f  mov     [rbp+57h+cchName], 0
0x14001a826  mov     r14, rdx
0x14001a829  mov     [rbp+57h+Type], 0
0x14001a830  mov     r15d, ecx
0x14001a833  mov     [rbp+57h+cbData], 0
0x14001a83a  mov     dword ptr [rbp+57h+Data], 0
0x14001a841  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001a845  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x14001a849  test    rdx, rdx
0x14001a84c  jnz     short loc_14001A856
0x14001a84e  lea     ebx, [rdx+57h]
0x14001a851  jmp     loc_14001A9C1
0x14001a856  lea     rdx, [rbp+57h+var_A0]
0x14001a85a  mov     ecx, 20019h; samDesired
0x14001a85f  call    HwCfgGetRootKey
0x14001a864  mov     ebx, eax
0x14001a866  test    eax, eax
0x14001a868  jnz     loc_14001A9A1
0x14001a86e  xor     esi, esi
0x14001a870  mov     rcx, [rbp+57h+hKey]; hKey
0x14001a874  test    rcx, rcx
0x14001a877  jz      short loc_14001A887
0x14001a879  call    cs:__imp_RegCloseKey
0x14001a87f  mov     [rbp+57h+hKey], 0
0x14001a887  mov     rcx, [rbp+57h+var_A0]; hKey
0x14001a88b  lea     r9, [rbp+57h+cchName]; lpcchName
0x14001a88f  mov     [rsp+0F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14001a898  lea     r8, [rbp+57h+Name]; lpName
0x14001a89c  mov     [rsp+0F0h+lpcchClass], 0; lpcchClass
0x14001a8a5  mov     edx, esi; dwIndex
0x14001a8a7  mov     [rsp+0F0h+lpClass], 0; lpClass
0x14001a8b0  mov     [rsp+0F0h+lpReserved], 0; lpReserved
0x14001a8b9  mov     [rbp+57h+cchName], 27h ; '''
0x14001a8c0  call    cs:__imp_RegEnumKeyExW
0x14001a8c6  mov     ebx, eax
0x14001a8c8  cmp     eax, 0EAh
0x14001a8cd  jz      loc_14001A974
0x14001a8d3  test    eax, eax
0x14001a8d5  jnz     loc_14001A993
0x14001a8db  cmp     [rbp+57h+cchName], 26h ; '&'
0x14001a8df  jb      loc_14001A974
0x14001a8e5  lea     rdx, [rbp+57h+Name]; SourceString
0x14001a8e9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001a8ed  call    cs:__imp_RtlInitUnicodeStringEx
0x14001a8f3  test    eax, eax
0x14001a8f5  jnz     short loc_14001A974
0x14001a8f7  lea     rdx, [rbp+57h+Guid]; Guid
0x14001a8fb  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x14001a8ff  call    cs:__imp_RtlGUIDFromString
0x14001a905  test    eax, eax
0x14001a907  jnz     short loc_14001A974
0x14001a909  mov     rcx, [rbp+57h+var_A0]; hKey
0x14001a90d  lea     rax, [rbp+57h+hKey]
0x14001a911  lea     r9d, [rbx+1]; samDesired
0x14001a915  mov     [rsp+0F0h+lpReserved], rax; phkResult
0x14001a91a  xor     r8d, r8d; ulOptions
0x14001a91d  lea     rdx, [rbp+57h+Name]; lpSubKey
0x14001a921  call    cs:__imp_RegOpenKeyExW
0x14001a927  test    eax, eax
0x14001a929  jnz     short loc_14001A974
0x14001a92b  mov     rcx, [rbp+57h+hKey]; hKey
0x14001a92f  lea     rax, [rbp+57h+cbData]
0x14001a933  mov     [rsp+0F0h+lpClass], rax; lpcbData
0x14001a938  lea     r9, [rbp+57h+Type]; lpType
0x14001a93c  lea     rax, [rbp+57h+Data]
0x14001a940  mov     [rbp+57h+cbData], 4
0x14001a947  xor     r8d, r8d; lpReserved
0x14001a94a  mov     [rsp+0F0h+lpReserved], rax; lpData
0x14001a94f  lea     rdx, aId; "Id"
0x14001a956  call    cs:__imp_RegQueryValueExW
0x14001a95c  mov     ebx, eax
0x14001a95e  test    eax, eax
0x14001a960  jnz     short loc_14001A974
0x14001a962  cmp     [rbp+57h+Type], 4
0x14001a966  jnz     short loc_14001A974
0x14001a968  cmp     [rbp+57h+cbData], 4
0x14001a96c  jnz     short loc_14001A974
0x14001a96e  cmp     r15d, dword ptr [rbp+57h+Data]
0x14001a972  jz      short loc_14001A97B
0x14001a974  inc     esi
0x14001a976  jmp     loc_14001A870
0x14001a97b  mov     r8d, [rbp+57h+cchName]
0x14001a97f  lea     rdx, [rbp+57h+Name]; Src
0x14001a983  inc     r8d
0x14001a986  mov     rcx, r14; void *
0x14001a989  add     r8, r8; Size
0x14001a98c  call    memcpy_0
0x14001a991  jmp     short loc_14001A9A1
0x14001a993  cmp     ebx, 103h
0x14001a999  mov     eax, 490h
0x14001a99e  cmovz   ebx, eax
0x14001a9a1  cmp     [rbp+57h+var_A0], 0
0x14001a9a6  jz      short loc_14001A9B2
0x14001a9a8  mov     rcx, [rbp+57h+var_A0]; hKey
0x14001a9ac  call    cs:__imp_RegCloseKey
0x14001a9b2  mov     rcx, [rbp+57h+hKey]; hKey
0x14001a9b6  test    rcx, rcx
0x14001a9b9  jz      short loc_14001A9C1
0x14001a9bb  call    cs:__imp_RegCloseKey
0x14001a9c1  mov     eax, ebx
0x14001a9c3  mov     rcx, [rbp+57h+var_20]
0x14001a9c7  xor     rcx, rsp; StackCookie
0x14001a9ca  call    __security_check_cookie
0x14001a9cf  lea     r11, [rsp+0F0h+var_10]
0x14001a9d7  mov     rbx, [r11+20h]
0x14001a9db  mov     rsi, [r11+30h]
0x14001a9df  mov     rsp, r11
0x14001a9e2  pop     r15
0x14001a9e4  pop     r14
0x14001a9e6  pop     rbp
0x14001a9e7  retn
```
