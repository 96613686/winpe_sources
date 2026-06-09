# HwCfgGetCurrentKey

- ea: `0x14001a534`
- end: `0x14001a5e1`
- name: `HwCfgGetCurrentKey`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001a460`

## callees

- `0x14001a534`
- `0x14001a5e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a58f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a58f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a5be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a5ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a5be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a5ce`

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
    RootKey = HwCfgGetRootKey(8u, &hKey);
    if ( RootKey || (RootKey = RegOpenKeyExW(hKey, L"Current", 0, 2u, &phkResult)) != 0 )
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
0x14001a534  mov     [rsp+arg_0], rbx
0x14001a539  push    rsi
0x14001a53a  sub     rsp, 30h
0x14001a53e  mov     [rsp+38h+hKey], 0
0x14001a547  mov     rsi, rdx
0x14001a54a  mov     [rsp+38h+arg_8], 0
0x14001a553  test    rdx, rdx
0x14001a556  jnz     short loc_14001A55D
0x14001a558  lea     ebx, [rdx+57h]
0x14001a55b  jmp     short loc_14001A5D4
0x14001a55d  lea     rdx, [rsp+38h+hKey]
0x14001a562  mov     ecx, 8; samDesired
0x14001a567  call    HwCfgGetRootKey
0x14001a56c  mov     ebx, eax
0x14001a56e  test    eax, eax
0x14001a570  jnz     short loc_14001A5AC
0x14001a572  mov     rcx, [rsp+38h+hKey]; hKey
0x14001a577  lea     rax, [rsp+38h+arg_8]
0x14001a57c  lea     r9d, [rbx+2]; samDesired
0x14001a580  mov     [rsp+38h+phkResult], rax; phkResult
0x14001a585  xor     r8d, r8d; ulOptions
0x14001a588  lea     rdx, aCurrent; "Current"
0x14001a58f  call    cs:__imp_RegOpenKeyExW
0x14001a595  mov     ebx, eax
0x14001a597  test    eax, eax
0x14001a599  jnz     short loc_14001A5AC
0x14001a59b  mov     rax, [rsp+38h+arg_8]
0x14001a5a0  xor     ecx, ecx
0x14001a5a2  mov     [rsi], rax
0x14001a5a5  mov     [rsp+38h+arg_8], rcx
0x14001a5aa  jmp     short loc_14001A5B1
0x14001a5ac  mov     rcx, [rsp+38h+arg_8]
0x14001a5b1  cmp     [rsp+38h+hKey], 0
0x14001a5b7  jz      short loc_14001A5C9
0x14001a5b9  mov     rcx, [rsp+38h+hKey]; hKey
0x14001a5be  call    cs:__imp_RegCloseKey
0x14001a5c4  mov     rcx, [rsp+38h+arg_8]; hKey
0x14001a5c9  test    rcx, rcx
0x14001a5cc  jz      short loc_14001A5D4
0x14001a5ce  call    cs:__imp_RegCloseKey
0x14001a5d4  mov     eax, ebx
0x14001a5d6  mov     rbx, [rsp+38h+arg_0]
0x14001a5db  add     rsp, 30h
0x14001a5df  pop     rsi
0x14001a5e0  retn
```
