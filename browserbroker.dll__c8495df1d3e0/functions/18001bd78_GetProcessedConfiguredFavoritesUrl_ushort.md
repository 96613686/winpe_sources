# GetProcessedConfiguredFavoritesUrl(ushort * *)

- ea: `0x18001bd78`
- end: `0x18001be80`
- name: `?GetProcessedConfiguredFavoritesUrl@@YAJPEAPEAG@Z`
- size: `264`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008700`
- `0x180009860`

## callees

- `0x180003170`
- `0x18001bd78`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001be4c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18001be4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001be58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001be58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bdeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001be3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bdeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001be3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bdb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bdb1`

## string_xrefs

- `0x18001bdcc`: `ProcessConfiguredFavorites`
- `0x18001be1c`: `ProcessConfiguredFavorites`

## pseudocode

```c
__int64 __fastcall GetProcessedConfiguredFavoritesUrl(LPWSTR *ppwsz)
{
  LSTATUS v2; // ebx
  unsigned int v3; // edi
  BYTE *v4; // r14
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Storage\\microso"
          "ft.microsoftedge_8wekyb3d8bbwe\\MicrosoftEdge\\Favorites",
         0,
         1u,
         &hKey);
  if ( v2 )
    goto LABEL_7;
  Type = 0;
  cbData = 0;
  v2 = RegQueryValueExW(hKey, L"ProcessConfiguredFavorites", 0, &Type, 0, &cbData);
  if ( v2 )
    goto LABEL_7;
  v3 = 0;
  if ( Type == 1 )
  {
    v4 = (BYTE *)operator new[](saturated_mul(cbData, 2u));
    v2 = RegQueryValueExW(hKey, L"ProcessConfiguredFavorites", 0, 0, v4, &cbData);
    if ( !v2 )
      v3 = SHStrDupW((LPCWSTR)v4, ppwsz);
  }
  RegCloseKey(hKey);
  if ( v2 )
  {
LABEL_7:
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
    else
      return (unsigned int)v2;
  }
  return v3;
}

```

## disassembly

```asm
0x18001bd78  push    rbp
0x18001bd7a  push    rbx
0x18001bd7b  push    rsi
0x18001bd7c  push    rdi
0x18001bd7d  push    r14
0x18001bd7f  mov     rbp, rsp
0x18001bd82  sub     rsp, 30h
0x18001bd86  mov     rsi, rcx
0x18001bd89  mov     [rbp+hKey], 0
0x18001bd91  lea     rax, [rbp+hKey]
0x18001bd95  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001bd9c  mov     r9d, 1; samDesired
0x18001bda2  mov     [rsp+30h+phkResult], rax; phkResult
0x18001bda7  xor     r8d, r8d; ulOptions
0x18001bdaa  lea     rdx, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x18001bdb1  call    cs:__imp_RegOpenKeyExW
0x18001bdb7  mov     ebx, eax
0x18001bdb9  test    eax, eax
0x18001bdbb  jnz     loc_18001BE62
0x18001bdc1  mov     rcx, [rbp+hKey]; hKey
0x18001bdc5  lea     r9, [rbp+Type]; lpType
0x18001bdc9  mov     [rbp+Type], eax
0x18001bdcc  lea     rdx, aProcessconfigu; "ProcessConfiguredFavorites"
0x18001bdd3  mov     [rbp+cbData], eax
0x18001bdd6  xor     r8d, r8d; lpReserved
0x18001bdd9  lea     rax, [rbp+cbData]
0x18001bddd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001bde2  mov     [rsp+30h+phkResult], 0; lpData
0x18001bdeb  call    cs:__imp_RegQueryValueExW
0x18001bdf1  mov     ebx, eax
0x18001bdf3  test    eax, eax
0x18001bdf5  jnz     short loc_18001BE62
0x18001bdf7  xor     edi, edi
0x18001bdf9  cmp     [rbp+Type], 1
0x18001bdfd  jnz     short loc_18001BE54
0x18001bdff  mov     ecx, [rbp+cbData]
0x18001be02  lea     eax, [rbx+2]
0x18001be05  mul     rcx
0x18001be08  lea     rcx, [rdi-1]
0x18001be0c  cmovb   rax, rcx
0x18001be10  mov     rcx, rax; unsigned __int64
0x18001be13  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001be18  mov     rcx, [rbp+hKey]; hKey
0x18001be1c  lea     rdx, aProcessconfigu; "ProcessConfiguredFavorites"
0x18001be23  mov     r14, rax
0x18001be26  xor     r9d, r9d; lpType
0x18001be29  lea     rax, [rbp+cbData]
0x18001be2d  xor     r8d, r8d; lpReserved
0x18001be30  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001be35  mov     [rsp+30h+phkResult], r14; lpData
0x18001be3a  call    cs:__imp_RegQueryValueExW
0x18001be40  mov     ebx, eax
0x18001be42  test    eax, eax
0x18001be44  jnz     short loc_18001BE54
0x18001be46  mov     rdx, rsi; ppwsz
0x18001be49  mov     rcx, r14; psz
0x18001be4c  call    cs:__imp_SHStrDupW
0x18001be52  mov     edi, eax
0x18001be54  mov     rcx, [rbp+hKey]; hKey
0x18001be58  call    cs:__imp_RegCloseKey
0x18001be5e  test    ebx, ebx
0x18001be60  jz      short loc_18001BE73
0x18001be62  test    ebx, ebx
0x18001be64  jg      short loc_18001BE6A
0x18001be66  mov     edi, ebx
0x18001be68  jmp     short loc_18001BE73
0x18001be6a  movzx   edi, bx
0x18001be6d  or      edi, 80070000h
0x18001be73  mov     eax, edi
0x18001be75  add     rsp, 30h
0x18001be79  pop     r14
0x18001be7b  pop     rdi
0x18001be7c  pop     rsi
0x18001be7d  pop     rbx
0x18001be7e  pop     rbp
0x18001be7f  retn
```
