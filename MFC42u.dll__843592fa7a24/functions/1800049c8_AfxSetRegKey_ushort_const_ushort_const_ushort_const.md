# _AfxSetRegKey(ushort const *,ushort const *,ushort const *)

- ea: `0x1800049c8`
- end: `0x180004aca`
- name: `?_AfxSetRegKey@@YAHPEBG00@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, BYTE *lpData, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800044d0`

## callees

- `0x1800049c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004a60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004a60`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004aa5`
- `ADVAPI32!RegSetValueW` at `0x180004a0a`
- `ADVAPI32!RegSetValueW` at `0x180004a0a`

## pseudocode

```c
_BOOL8 __fastcall _AfxSetRegKey(LPCWSTR lpSubKey, BYTE *lpData, LPCWSTR lpValueName)
{
  __int64 v5; // rax
  __int64 v7; // rax
  LSTATUS v8; // ebx
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  if ( lpValueName )
  {
    hKey = 0;
    dwDisposition = 0;
    if ( !RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&lpData[2 * v7] );
      v8 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v7 + 2);
      if ( !RegCloseKey(hKey) )
        return v8 == 0;
    }
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&lpData[2 * v5] );
    if ( !RegSetValueW(HKEY_CLASSES_ROOT, lpSubKey, 1u, (LPCWSTR)lpData, 2 * v5) )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800049c8  mov     [rsp+arg_0], rbx
0x1800049cd  mov     [rsp+arg_8], rsi
0x1800049d2  push    rdi
0x1800049d3  sub     rsp, 50h
0x1800049d7  xor     esi, esi
0x1800049d9  mov     rdi, r8
0x1800049dc  mov     rbx, rdx
0x1800049df  test    r8, r8
0x1800049e2  jnz     short loc_180004A22
0x1800049e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800049e8  inc     rax
0x1800049eb  cmp     [rdx+rax*2], si
0x1800049ef  jnz     short loc_1800049E8
0x1800049f1  add     eax, eax
0x1800049f3  mov     rdx, rcx; lpSubKey
0x1800049f6  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800049fd  mov     [rsp+58h+cbData], eax; cbData
0x180004a01  mov     r9, rbx; lpData
0x180004a04  mov     r8d, 1; dwType
0x180004a0a  call    cs:__imp_RegSetValueW
0x180004a10  test    eax, eax
0x180004a12  jnz     loc_180004AB8
0x180004a18  mov     eax, 1
0x180004a1d  jmp     loc_180004ABA
0x180004a22  lea     rax, [rsp+58h+dwDisposition]
0x180004a27  mov     [rsp+58h+hKey], rsi
0x180004a2c  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180004a31  mov     rdx, rcx; lpSubKey
0x180004a34  lea     rax, [rsp+58h+hKey]
0x180004a39  mov     [rsp+58h+dwDisposition], esi
0x180004a3d  mov     [rsp+58h+phkResult], rax; phkResult
0x180004a42  xor     r9d, r9d; lpClass
0x180004a45  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180004a4a  xor     r8d, r8d; Reserved
0x180004a4d  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180004a55  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004a5c  mov     [rsp+58h+cbData], esi; dwOptions
0x180004a60  call    cs:__imp_RegCreateKeyExW
0x180004a66  test    eax, eax
0x180004a68  jnz     short loc_180004AB8
0x180004a6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a6e  inc     rax
0x180004a71  cmp     [rbx+rax*2], si
0x180004a75  jnz     short loc_180004A6E
0x180004a77  mov     rcx, [rsp+58h+hKey]; hKey
0x180004a7c  lea     eax, ds:2[rax*2]
0x180004a83  mov     [rsp+58h+samDesired], eax; cbData
0x180004a87  mov     r9d, 1; dwType
0x180004a8d  xor     r8d, r8d; Reserved
0x180004a90  mov     qword ptr [rsp+58h+cbData], rbx; lpData
0x180004a95  mov     rdx, rdi; lpValueName
0x180004a98  call    cs:__imp_RegSetValueExW
0x180004a9e  mov     rcx, [rsp+58h+hKey]; hKey
0x180004aa3  mov     ebx, eax
0x180004aa5  call    cs:__imp_RegCloseKey
0x180004aab  test    eax, eax
0x180004aad  jnz     short loc_180004AB8
0x180004aaf  test    ebx, ebx
0x180004ab1  mov     eax, esi
0x180004ab3  setz    al
0x180004ab6  jmp     short loc_180004ABA
0x180004ab8  xor     eax, eax
0x180004aba  mov     rbx, [rsp+58h+arg_0]
0x180004abf  mov     rsi, [rsp+58h+arg_8]
0x180004ac4  add     rsp, 50h
0x180004ac8  pop     rdi
0x180004ac9  retn
```
