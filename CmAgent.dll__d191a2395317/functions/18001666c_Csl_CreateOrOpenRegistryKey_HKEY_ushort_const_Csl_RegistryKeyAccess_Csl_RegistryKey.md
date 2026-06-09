# Csl::CreateOrOpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)

- ea: `0x18001666c`
- end: `0x1800167c9`
- name: `?CreateOrOpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z`
- size: `349`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005050`
- `0x1800178e0`

## callees

- `0x18000b7e0`
- `0x18001666c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001674f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001674f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001676e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001676e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800166cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800166cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001671a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001678f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800167a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001671a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001678f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800167a8`

## string_xrefs

- `0x1800166e2`: `Failed to create registry key with name '%ws'`
- `0x1800166ee`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::CreateOrOpenRegistryKey(__int64 a1, const WCHAR *a2, __int64 a3, char *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v8; // rbx
  HKEY v9; // rcx
  HKEY v10; // rbp
  DWORD LastError; // edi
  char v13; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF
  DWORD v16; // [rsp+90h] [rbp+18h] BYREF

  v16 = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x2001Fu, 0, &hKey, &v16);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x3A,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
           (const char *)v6,
           (unsigned int)"Failed to create registry key with name '%ws'",
           (const char *)a2);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v8 = hKey;
    v9 = 0;
    hKey = 0;
    if ( a4 == &v13 )
    {
      if ( v8 )
      {
        RegCloseKey(v8);
        v9 = hKey;
      }
    }
    else
    {
      v10 = *(HKEY *)a4;
      if ( *(_QWORD *)a4 )
      {
        LastError = GetLastError();
        RegCloseKey(v10);
        SetLastError(LastError);
        v9 = hKey;
      }
      *(_QWORD *)a4 = v8;
    }
    if ( v9 )
      RegCloseKey(v9);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18001666c  mov     r11, rsp
0x18001666f  mov     [r11+10h], rbx
0x180016673  mov     [r11+18h], r8d
0x180016677  mov     [r11+8], rcx
0x18001667b  push    rbp
0x18001667c  push    rsi
0x18001667d  push    rdi
0x18001667e  sub     rsp, 60h
0x180016682  lea     rax, [r11+18h]
0x180016686  mov     dword ptr [r11+18h], 0
0x18001668e  mov     [r11-38h], rax
0x180016692  mov     rsi, r9
0x180016695  lea     rax, [r11+8]
0x180016699  mov     qword ptr [r11+8], 0
0x1800166a1  mov     [r11-40h], rax
0x1800166a5  xor     r9d, r9d; lpClass
0x1800166a8  mov     qword ptr [r11-48h], 0
0x1800166b0  xor     r8d, r8d; Reserved
0x1800166b3  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800166bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800166c2  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800166ca  mov     rbx, rdx
0x1800166cd  call    cs:__imp_RegCreateKeyExW
0x1800166d4  nop     dword ptr [rax+rax+00h]
0x1800166d9  test    eax, eax
0x1800166db  jz      short loc_18001672B
0x1800166dd  mov     rcx, [rsp+78h]; this
0x1800166e2  lea     rdx, aFailedToCreate; "Failed to create registry key with name"...
0x1800166e9  mov     qword ptr [rsp+78h+samDesired], rbx; char *
0x1800166ee  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800166f5  mov     qword ptr [rsp+78h+dwOptions], rdx; unsigned int
0x1800166fa  mov     r9d, eax; char *
0x1800166fd  mov     edx, 3Ah ; ':'; void *
0x180016702  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180016707  mov     rcx, [rsp+78h+hKey]; hKey
0x18001670f  mov     ebx, eax
0x180016711  test    rcx, rcx
0x180016714  jz      loc_1800167B6
0x18001671a  call    cs:__imp_RegCloseKey
0x180016721  nop     dword ptr [rax+rax+00h]
0x180016726  jmp     loc_1800167B6
0x18001672b  mov     rbx, [rsp+78h+hKey]
0x180016733  lea     rax, [rsp+78h+var_28]
0x180016738  xor     ecx, ecx
0x18001673a  mov     [rsp+78h+hKey], rcx
0x180016742  cmp     rsi, rax
0x180016745  jz      short loc_180016787
0x180016747  mov     rbp, [rsi]
0x18001674a  test    rbp, rbp
0x18001674d  jz      short loc_180016782
0x18001674f  call    cs:__imp_GetLastError
0x180016756  nop     dword ptr [rax+rax+00h]
0x18001675b  mov     rcx, rbp; hKey
0x18001675e  mov     edi, eax
0x180016760  call    cs:__imp_RegCloseKey
0x180016767  nop     dword ptr [rax+rax+00h]
0x18001676c  mov     ecx, edi; dwErrCode
0x18001676e  call    cs:__imp_SetLastError
0x180016775  nop     dword ptr [rax+rax+00h]
0x18001677a  mov     rcx, [rsp+78h+hKey]
0x180016782  mov     [rsi], rbx
0x180016785  jmp     short loc_1800167A3
0x180016787  test    rbx, rbx
0x18001678a  jz      short loc_1800167A3
0x18001678c  mov     rcx, rbx; hKey
0x18001678f  call    cs:__imp_RegCloseKey
0x180016796  nop     dword ptr [rax+rax+00h]
0x18001679b  mov     rcx, [rsp+78h+hKey]; hKey
0x1800167a3  test    rcx, rcx
0x1800167a6  jz      short loc_1800167B4
0x1800167a8  call    cs:__imp_RegCloseKey
0x1800167af  nop     dword ptr [rax+rax+00h]
0x1800167b4  xor     ebx, ebx
0x1800167b6  mov     eax, ebx
0x1800167b8  mov     rbx, [rsp+78h+arg_8]
0x1800167c0  add     rsp, 60h
0x1800167c4  pop     rdi
0x1800167c5  pop     rsi
0x1800167c6  pop     rbp
0x1800167c7  retn
```
