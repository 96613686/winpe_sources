# Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)

- ea: `0x18000b5b0`
- end: `0x18000b6ea`
- name: `?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, REGSAM, char *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800171d8`
- `0x18001edfc`
- `0x1800200e4`
- `0x180022894`
- `0x180022c10`
- `0x180023090`

## callees

- `0x18000b5b0`
- `0x18000b7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b662`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b681`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b681`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b5e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b5e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b631`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b673`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b69f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b631`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b673`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b69f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6cf`

## string_xrefs

- `0x18000b60c`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x18000b600`: `Failed to open registry key with name '%ws'`

## pseudocode

```c
__int64 __fastcall Csl::OpenRegistryKey(__int64 a1, const WCHAR *a2, REGSAM a3, char *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v9; // rbx
  HKEY v10; // rcx
  HKEY v11; // rbp
  DWORD LastError; // edi
  char v13; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, a3, &hKey);
  if ( v6 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  else if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x81,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
           (const char *)v6,
           (unsigned int)"Failed to open registry key with name '%ws'",
           (const char *)a2);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  else
  {
    v9 = hKey;
    v10 = 0;
    hKey = 0;
    if ( a4 == &v13 )
    {
      if ( v9 )
      {
        RegCloseKey(v9);
        v10 = hKey;
      }
    }
    else
    {
      v11 = *(HKEY *)a4;
      if ( *(_QWORD *)a4 )
      {
        LastError = GetLastError();
        RegCloseKey(v11);
        SetLastError(LastError);
        v10 = hKey;
      }
      *(_QWORD *)a4 = v9;
    }
    if ( v10 )
      RegCloseKey(v10);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b5b0  mov     r11, rsp
0x18000b5b3  mov     [r11+8], rcx
0x18000b5b7  push    rbx
0x18000b5b8  push    rbp
0x18000b5b9  push    rsi
0x18000b5ba  push    rdi
0x18000b5bb  sub     rsp, 48h
0x18000b5bf  mov     rsi, r9
0x18000b5c2  mov     qword ptr [r11+8], 0
0x18000b5ca  mov     r9d, r8d; samDesired
0x18000b5cd  lea     rax, [r11+8]
0x18000b5d1  xor     r8d, r8d; ulOptions
0x18000b5d4  mov     [r11-48h], rax
0x18000b5d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b5df  mov     rbx, rdx
0x18000b5e2  call    cs:__imp_RegOpenKeyExW
0x18000b5e9  nop     dword ptr [rax+rax+00h]
0x18000b5ee  cmp     eax, 2
0x18000b5f1  jz      loc_18000B6C5
0x18000b5f7  test    eax, eax
0x18000b5f9  jz      short loc_18000B644
0x18000b5fb  mov     rcx, [rsp+68h]; this
0x18000b600  lea     rdx, aFailedToOpenRe; "Failed to open registry key with name '"...
0x18000b607  mov     [rsp+68h+var_40], rbx; char *
0x18000b60c  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b613  mov     qword ptr [rsp+68h+var_48], rdx; unsigned int
0x18000b618  mov     r9d, eax; char *
0x18000b61b  mov     edx, 81h; void *
0x18000b620  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b625  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b62a  mov     ebx, eax
0x18000b62c  test    rcx, rcx
0x18000b62f  jz      short loc_18000B63D
0x18000b631  call    cs:__imp_RegCloseKey
0x18000b638  nop     dword ptr [rax+rax+00h]
0x18000b63d  mov     eax, ebx
0x18000b63f  jmp     loc_18000B6E0
0x18000b644  mov     rbx, [rsp+68h+hKey]
0x18000b649  lea     rax, [rsp+68h+var_38]
0x18000b64e  xor     ecx, ecx
0x18000b650  mov     [rsp+68h+hKey], rcx
0x18000b655  cmp     rsi, rax
0x18000b658  jz      short loc_18000B697
0x18000b65a  mov     rbp, [rsi]
0x18000b65d  test    rbp, rbp
0x18000b660  jz      short loc_18000B692
0x18000b662  call    cs:__imp_GetLastError
0x18000b669  nop     dword ptr [rax+rax+00h]
0x18000b66e  mov     rcx, rbp; hKey
0x18000b671  mov     edi, eax
0x18000b673  call    cs:__imp_RegCloseKey
0x18000b67a  nop     dword ptr [rax+rax+00h]
0x18000b67f  mov     ecx, edi; dwErrCode
0x18000b681  call    cs:__imp_SetLastError
0x18000b688  nop     dword ptr [rax+rax+00h]
0x18000b68d  mov     rcx, [rsp+68h+hKey]
0x18000b692  mov     [rsi], rbx
0x18000b695  jmp     short loc_18000B6B0
0x18000b697  test    rbx, rbx
0x18000b69a  jz      short loc_18000B6B0
0x18000b69c  mov     rcx, rbx; hKey
0x18000b69f  call    cs:__imp_RegCloseKey
0x18000b6a6  nop     dword ptr [rax+rax+00h]
0x18000b6ab  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b6b0  test    rcx, rcx
0x18000b6b3  jz      short loc_18000B6C1
0x18000b6b5  call    cs:__imp_RegCloseKey
0x18000b6bc  nop     dword ptr [rax+rax+00h]
0x18000b6c1  xor     eax, eax
0x18000b6c3  jmp     short loc_18000B6E0
0x18000b6c5  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b6ca  test    rcx, rcx
0x18000b6cd  jz      short loc_18000B6DB
0x18000b6cf  call    cs:__imp_RegCloseKey
0x18000b6d6  nop     dword ptr [rax+rax+00h]
0x18000b6db  mov     eax, 80070002h
0x18000b6e0  add     rsp, 48h
0x18000b6e4  pop     rdi
0x18000b6e5  pop     rsi
0x18000b6e6  pop     rbp
0x18000b6e7  pop     rbx
0x18000b6e8  retn
```
