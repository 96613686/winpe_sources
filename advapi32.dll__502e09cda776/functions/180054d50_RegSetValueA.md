# RegSetValueA

- ea: `0x180054d50`
- end: `0x180054ec5`
- name: `RegSetValueA`
- size: `373`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, DWORD dwType, LPCSTR lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180054d50`

## import_xrefs

- `KERNELBASE!MapPredefinedHandleInternal` at `0x180054dba`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180054dba`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180054e9a`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180054e9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180054e2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180054e2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054e7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054e7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180054e65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180054e65`

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
0x180054d50  mov     [rsp-18h+arg_8], rbx
0x180054d55  mov     [rsp-18h+arg_10], rsi
0x180054d5a  mov     [rsp-18h+hKey], rcx
0x180054d5f  push    rbp
0x180054d60  push    rdi
0x180054d61  push    r14
0x180054d63  mov     rbp, rsp
0x180054d66  sub     rsp, 70h
0x180054d6a  mov     [rbp+var_20], 0
0x180054d72  mov     r14, r9
0x180054d75  mov     [rbp+var_10], 0
0x180054d7d  mov     rsi, rdx
0x180054d80  mov     [rbp+var_18], 0
0x180054d88  cmp     rcx, 0FFFFFFFF80000004h
0x180054d8f  jnz     short loc_180054D9B
0x180054d91  mov     eax, 6
0x180054d96  jmp     loc_180054EAF
0x180054d9b  cmp     r8d, 1
0x180054d9f  jnz     loc_180054EAA
0x180054da5  test    r14, r14
0x180054da8  jz      loc_180054EAA
0x180054dae  lea     r9, [rbp+var_18]
0x180054db2  lea     r8, [rbp+var_10]
0x180054db6  lea     rdx, [rbp+hKey]
0x180054dba  call    cs:__imp_MapPredefinedHandleInternal
0x180054dc1  nop     dword ptr [rax+rax+00h]
0x180054dc6  mov     ebx, eax
0x180054dc8  test    eax, eax
0x180054dca  jnz     loc_180054E92
0x180054dd0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180054dd4  inc     rdi
0x180054dd7  cmp     byte ptr [r14+rdi], 0
0x180054ddc  jnz     short loc_180054DD4
0x180054dde  mov     eax, 0FFFFFFFFh
0x180054de3  cmp     rdi, rax
0x180054de6  jnb     loc_180054E8D
0x180054dec  test    rsi, rsi
0x180054def  jz      short loc_180054E46
0x180054df1  cmp     byte ptr [rsi], 0
0x180054df4  jz      short loc_180054E46
0x180054df6  mov     rcx, [rbp+hKey]; hKey
0x180054dfa  lea     rax, [rbp+var_20]
0x180054dfe  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180054e07  xor     r9d, r9d; lpClass
0x180054e0a  mov     [rsp+70h+phkResult], rax; phkResult
0x180054e0f  xor     r8d, r8d; Reserved
0x180054e12  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180054e1b  mov     rdx, rsi; lpSubKey
0x180054e1e  mov     [rsp+70h+samDesired], 2; samDesired
0x180054e26  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180054e2e  call    cs:__imp_RegCreateKeyExA
0x180054e35  nop     dword ptr [rax+rax+00h]
0x180054e3a  mov     ebx, eax
0x180054e3c  test    eax, eax
0x180054e3e  jnz     short loc_180054E92
0x180054e40  mov     rcx, [rbp+var_20]
0x180054e44  jmp     short loc_180054E4E
0x180054e46  mov     rcx, [rbp+hKey]; hKey
0x180054e4a  mov     [rbp+var_20], rcx
0x180054e4e  lea     eax, [rdi+1]
0x180054e51  mov     r9d, 1; dwType
0x180054e57  mov     [rsp+70h+samDesired], eax; cbData
0x180054e5b  xor     r8d, r8d; Reserved
0x180054e5e  xor     edx, edx; lpValueName
0x180054e60  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x180054e65  call    cs:__imp_RegSetValueExA
0x180054e6c  nop     dword ptr [rax+rax+00h]
0x180054e71  mov     rcx, [rbp+var_20]; hKey
0x180054e75  mov     ebx, eax
0x180054e77  cmp     rcx, [rbp+hKey]
0x180054e7b  jz      short loc_180054E92
0x180054e7d  call    cs:__imp_RegCloseKey
0x180054e84  nop     dword ptr [rax+rax+00h]
0x180054e89  mov     ebx, eax
0x180054e8b  jmp     short loc_180054E92
0x180054e8d  mov     ebx, 57h ; 'W'
0x180054e92  mov     rdx, [rbp+var_18]
0x180054e96  mov     rcx, [rbp+var_10]
0x180054e9a  call    cs:__imp_CLOSE_LOCAL_HANDLE_INTERNAL
0x180054ea1  nop     dword ptr [rax+rax+00h]
0x180054ea6  mov     eax, ebx
0x180054ea8  jmp     short loc_180054EAF
0x180054eaa  mov     eax, 57h ; 'W'
0x180054eaf  lea     r11, [rsp+70h+var_s0]
0x180054eb4  mov     rbx, [r11+28h]
0x180054eb8  mov     rsi, [r11+30h]
0x180054ebc  mov     rsp, r11
0x180054ebf  pop     r14
0x180054ec1  pop     rdi
0x180054ec2  pop     rbp
0x180054ec3  retn
```
