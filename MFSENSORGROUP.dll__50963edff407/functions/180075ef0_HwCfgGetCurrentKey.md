# HwCfgGetCurrentKey

- ea: `0x180075ef0`
- end: `0x180075f98`
- name: `HwCfgGetCurrentKey`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180075d04`

## callees

- `0x180075ef0`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075f46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075f46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075f75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075f85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075f75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075f85`

## pseudocode

```c
__int64 __fastcall HwCfgGetCurrentKey(__int64 a1, HKEY *a2)
{
  unsigned int RootKey; // ebx
  HKEY v4; // rcx
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( a2 )
  {
    RootKey = HwCfgGetRootKey(a1, &hKey);
    if ( RootKey || (RootKey = RegOpenKeyExW(hKey, L"Current", 0, 8u, &phkResult)) != 0 )
    {
      v4 = phkResult;
    }
    else
    {
      v4 = 0;
      *a2 = phkResult;
      phkResult = 0;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      v4 = phkResult;
    }
    if ( v4 )
      RegCloseKey(v4);
  }
  else
  {
    return 87;
  }
  return RootKey;
}

```

## disassembly

```asm
0x180075ef0  mov     [rsp+arg_0], rbx
0x180075ef5  push    rsi
0x180075ef6  sub     rsp, 30h
0x180075efa  mov     [rsp+38h+hKey], 0
0x180075f03  mov     rsi, rdx
0x180075f06  mov     [rsp+38h+arg_8], 0
0x180075f0f  test    rdx, rdx
0x180075f12  jnz     short loc_180075F19
0x180075f14  lea     ebx, [rdx+57h]
0x180075f17  jmp     short loc_180075F8B
0x180075f19  lea     rdx, [rsp+38h+hKey]
0x180075f1e  call    HwCfgGetRootKey
0x180075f23  mov     ebx, eax
0x180075f25  test    eax, eax
0x180075f27  jnz     short loc_180075F63
0x180075f29  mov     rcx, [rsp+38h+hKey]; hKey
0x180075f2e  lea     rax, [rsp+38h+arg_8]
0x180075f33  lea     r9d, [rbx+8]; samDesired
0x180075f37  mov     [rsp+38h+phkResult], rax; phkResult
0x180075f3c  xor     r8d, r8d; ulOptions
0x180075f3f  lea     rdx, aCurrent; "Current"
0x180075f46  call    cs:__imp_RegOpenKeyExW
0x180075f4c  mov     ebx, eax
0x180075f4e  test    eax, eax
0x180075f50  jnz     short loc_180075F63
0x180075f52  mov     rax, [rsp+38h+arg_8]
0x180075f57  xor     ecx, ecx
0x180075f59  mov     [rsi], rax
0x180075f5c  mov     [rsp+38h+arg_8], rcx
0x180075f61  jmp     short loc_180075F68
0x180075f63  mov     rcx, [rsp+38h+arg_8]
0x180075f68  cmp     [rsp+38h+hKey], 0
0x180075f6e  jz      short loc_180075F80
0x180075f70  mov     rcx, [rsp+38h+hKey]; hKey
0x180075f75  call    cs:__imp_RegCloseKey
0x180075f7b  mov     rcx, [rsp+38h+arg_8]; hKey
0x180075f80  test    rcx, rcx
0x180075f83  jz      short loc_180075F8B
0x180075f85  call    cs:__imp_RegCloseKey
0x180075f8b  mov     eax, ebx
0x180075f8d  mov     rbx, [rsp+38h+arg_0]
0x180075f92  add     rsp, 30h
0x180075f96  pop     rsi
0x180075f97  retn
```
