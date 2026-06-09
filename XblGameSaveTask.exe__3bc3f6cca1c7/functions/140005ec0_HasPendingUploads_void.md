# HasPendingUploads(void)

- ea: `0x140005ec0`
- end: `0x140005fa9`
- name: `?HasPendingUploads@@YA_NXZ`
- size: `233`
- prototype: `bool __fastcall(ConnectedStorage *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000607c`

## callees

- `0x140005ec0`
- `0x1400061e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005f8e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005f1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005f1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005f6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005f6b`

## pseudocode

```c
bool __fastcall HasPendingUploads(ConnectedStorage *a1)
{
  bool IsRunningOnConsole; // al
  const WCHAR *v2; // rdx
  HKEY v3; // rbx
  bool v4; // di
  DWORD cSubKeys; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  cSubKeys = 0;
  hKey = 0;
  IsRunningOnConsole = ConnectedStorage::IsRunningOnConsole(a1);
  v2 = L"OSDATA\\Software\\Microsoft\\XboxGameSaveStorage\\Uploads";
  if ( !IsRunningOnConsole )
    v2 = L"Software\\Microsoft\\XboxGameSaveStorage\\Uploads";
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    v3 = 0;
  }
  else
  {
    v3 = hKey;
    if ( hKey && RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
      cSubKeys = 0;
  }
  v4 = cSubKeys != 0;
  if ( v3 )
    RegCloseKey(v3);
  return v4;
}

```

## disassembly

```asm
0x140005ec0  mov     rax, rsp
0x140005ec3  mov     [rax+18h], rbx
0x140005ec7  mov     [rax+20h], rsi
0x140005ecb  push    rdi
0x140005ecc  sub     rsp, 60h
0x140005ed0  xor     esi, esi
0x140005ed2  mov     [rax+8], esi
0x140005ed5  mov     [rax+10h], rsi
0x140005ed9  call    ?IsRunningOnConsole@ConnectedStorage@@YA_NXZ; ConnectedStorage::IsRunningOnConsole(void)
0x140005ede  mov     [rsp+68h+lpdwDisposition], rsi; lpdwDisposition
0x140005ee3  lea     rcx, SubKey; "Software\\Microsoft\\XboxGameSaveStorag"...
0x140005eea  test    al, al
0x140005eec  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\XboxGameSa"...
0x140005ef3  lea     rax, [rsp+68h+hKey]
0x140005ef8  mov     [rsp+68h+phkResult], rax; phkResult
0x140005efd  cmovz   rdx, rcx; lpSubKey
0x140005f01  mov     [rsp+68h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140005f06  xor     r9d, r9d; lpClass
0x140005f09  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x140005f11  xor     r8d, r8d; Reserved
0x140005f14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005f1b  mov     [rsp+68h+dwOptions], esi; dwOptions
0x140005f1f  call    cs:__imp_RegCreateKeyExW
0x140005f25  test    eax, eax
0x140005f27  jnz     short loc_140005F7B
0x140005f29  mov     rbx, [rsp+68h+hKey]
0x140005f2e  test    rbx, rbx
0x140005f31  jz      short loc_140005F7E
0x140005f33  mov     [rsp+68h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x140005f38  lea     rax, [rsp+68h+cSubKeys]
0x140005f3d  mov     [rsp+68h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x140005f42  xor     r9d, r9d; lpReserved
0x140005f45  mov     [rsp+68h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x140005f4a  xor     r8d, r8d; lpcchClass
0x140005f4d  mov     [rsp+68h+lpdwDisposition], rsi; lpcbMaxValueNameLen
0x140005f52  xor     edx, edx; lpClass
0x140005f54  mov     [rsp+68h+phkResult], rsi; lpcValues
0x140005f59  mov     rcx, rbx; hKey
0x140005f5c  mov     [rsp+68h+lpSecurityAttributes], rsi; lpcbMaxClassLen
0x140005f61  mov     qword ptr [rsp+68h+samDesired], rsi; lpcbMaxSubKeyLen
0x140005f66  mov     qword ptr [rsp+68h+dwOptions], rax; lpcSubKeys
0x140005f6b  call    cs:__imp_RegQueryInfoKeyW
0x140005f71  test    eax, eax
0x140005f73  jz      short loc_140005F7E
0x140005f75  mov     [rsp+68h+cSubKeys], esi
0x140005f79  jmp     short loc_140005F7E
0x140005f7b  mov     rbx, rsi
0x140005f7e  cmp     [rsp+68h+cSubKeys], esi
0x140005f82  setnbe  dil
0x140005f86  test    rbx, rbx
0x140005f89  jz      short loc_140005F94
0x140005f8b  mov     rcx, rbx; hKey
0x140005f8e  call    cs:__imp_RegCloseKey
0x140005f94  lea     r11, [rsp+68h+var_8]
0x140005f99  mov     al, dil
0x140005f9c  mov     rbx, [r11+20h]
0x140005fa0  mov     rsi, [r11+28h]
0x140005fa4  mov     rsp, r11
0x140005fa7  pop     rdi
0x140005fa8  retn
```
