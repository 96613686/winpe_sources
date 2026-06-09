# RegSetValueA

- ea: `0x18004e960`
- end: `0x18004eab6`
- name: `RegSetValueA`
- size: `342`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, DWORD dwType, LPCSTR lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18004e960`

## import_xrefs

- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004e9ca`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004e9ca`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004ea92`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004ea92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18004ea38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18004ea38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ea7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ea7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18004ea69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18004ea69`

## pseudocode

```c
LSTATUS __stdcall RegSetValueA(HKEY hKey, LPCSTR lpSubKey, DWORD dwType, LPCSTR lpData, DWORD cbData)
{
  LSTATUS v8; // ebx
  unsigned __int64 v9; // rdi
  HKEY v10; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  __int64 v12; // [rsp+58h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+90h] [rbp+20h] BYREF

  hKeya = hKey;
  phkResult = 0;
  v13 = 0;
  v12 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  if ( dwType == 1 && lpData )
  {
    v8 = MapPredefinedHandleInternal(hKey, &hKeya, &v13, &v12);
    if ( !v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( lpData[v9] );
      if ( v9 >= 0xFFFFFFFF )
      {
        v8 = 87;
      }
      else
      {
        if ( !lpSubKey || !*lpSubKey )
        {
          v10 = hKeya;
          phkResult = hKeya;
LABEL_14:
          v8 = RegSetValueExA(v10, 0, 0, 1u, (const BYTE *)lpData, v9 + 1);
          if ( phkResult != hKeya )
            v8 = RegCloseKey(phkResult);
          goto LABEL_17;
        }
        v8 = RegCreateKeyExA(hKeya, lpSubKey, 0, 0, 0, 2u, 0, &phkResult, 0);
        if ( !v8 )
        {
          v10 = phkResult;
          goto LABEL_14;
        }
      }
    }
LABEL_17:
    CLOSE_LOCAL_HANDLE_INTERNAL(v13, v12);
    return v8;
  }
  return 87;
}

```

## disassembly

```asm
0x18004e960  mov     [rsp-18h+arg_8], rbx
0x18004e965  mov     [rsp-18h+arg_10], rsi
0x18004e96a  mov     [rsp-18h+hKey], rcx
0x18004e96f  push    rbp
0x18004e970  push    rdi
0x18004e971  push    r14
0x18004e973  mov     rbp, rsp
0x18004e976  sub     rsp, 70h
0x18004e97a  mov     [rbp+var_20], 0
0x18004e982  mov     r14, r9
0x18004e985  mov     [rbp+var_10], 0
0x18004e98d  mov     rsi, rdx
0x18004e990  mov     [rbp+var_18], 0
0x18004e998  cmp     rcx, 0FFFFFFFF80000004h
0x18004e99f  jnz     short loc_18004E9AB
0x18004e9a1  mov     eax, 6
0x18004e9a6  jmp     loc_18004EAA1
0x18004e9ab  cmp     r8d, 1
0x18004e9af  jnz     loc_18004EA9C
0x18004e9b5  test    r14, r14
0x18004e9b8  jz      loc_18004EA9C
0x18004e9be  lea     r9, [rbp+var_18]
0x18004e9c2  lea     r8, [rbp+var_10]
0x18004e9c6  lea     rdx, [rbp+hKey]
0x18004e9ca  call    cs:__imp_MapPredefinedHandleInternal
0x18004e9d0  mov     ebx, eax
0x18004e9d2  test    eax, eax
0x18004e9d4  jnz     loc_18004EA8A
0x18004e9da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004e9de  inc     rdi
0x18004e9e1  cmp     byte ptr [r14+rdi], 0
0x18004e9e6  jnz     short loc_18004E9DE
0x18004e9e8  mov     eax, 0FFFFFFFFh
0x18004e9ed  cmp     rdi, rax
0x18004e9f0  jnb     loc_18004EA85
0x18004e9f6  test    rsi, rsi
0x18004e9f9  jz      short loc_18004EA4A
0x18004e9fb  cmp     byte ptr [rsi], 0
0x18004e9fe  jz      short loc_18004EA4A
0x18004ea00  mov     rcx, [rbp+hKey]; hKey
0x18004ea04  lea     rax, [rbp+var_20]
0x18004ea08  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18004ea11  xor     r9d, r9d; lpClass
0x18004ea14  mov     [rsp+70h+phkResult], rax; phkResult
0x18004ea19  xor     r8d, r8d; Reserved
0x18004ea1c  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004ea25  mov     rdx, rsi; lpSubKey
0x18004ea28  mov     [rsp+70h+samDesired], 2; samDesired
0x18004ea30  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18004ea38  call    cs:__imp_RegCreateKeyExA
0x18004ea3e  mov     ebx, eax
0x18004ea40  test    eax, eax
0x18004ea42  jnz     short loc_18004EA8A
0x18004ea44  mov     rcx, [rbp+var_20]
0x18004ea48  jmp     short loc_18004EA52
0x18004ea4a  mov     rcx, [rbp+hKey]; hKey
0x18004ea4e  mov     [rbp+var_20], rcx
0x18004ea52  lea     eax, [rdi+1]
0x18004ea55  mov     r9d, 1; dwType
0x18004ea5b  mov     [rsp+70h+samDesired], eax; cbData
0x18004ea5f  xor     r8d, r8d; Reserved
0x18004ea62  xor     edx, edx; lpValueName
0x18004ea64  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x18004ea69  call    cs:__imp_RegSetValueExA
0x18004ea6f  mov     rcx, [rbp+var_20]; hKey
0x18004ea73  mov     ebx, eax
0x18004ea75  cmp     rcx, [rbp+hKey]
0x18004ea79  jz      short loc_18004EA8A
0x18004ea7b  call    cs:__imp_RegCloseKey
0x18004ea81  mov     ebx, eax
0x18004ea83  jmp     short loc_18004EA8A
0x18004ea85  mov     ebx, 57h ; 'W'
0x18004ea8a  mov     rdx, [rbp+var_18]
0x18004ea8e  mov     rcx, [rbp+var_10]
0x18004ea92  call    cs:__imp_CLOSE_LOCAL_HANDLE_INTERNAL
0x18004ea98  mov     eax, ebx
0x18004ea9a  jmp     short loc_18004EAA1
0x18004ea9c  mov     eax, 57h ; 'W'
0x18004eaa1  lea     r11, [rsp+70h+var_s0]
0x18004eaa6  mov     rbx, [r11+28h]
0x18004eaaa  mov     rsi, [r11+30h]
0x18004eaae  mov     rsp, r11
0x18004eab1  pop     r14
0x18004eab3  pop     rdi
0x18004eab4  pop     rbp
0x18004eab5  retn
```
