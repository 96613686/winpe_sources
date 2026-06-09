# Microsoft::Resources::IProfileHelpers::ReadMrtConfigUInt32Value(ushort const *,uint *,bool *)

- ea: `0x18006fb30`
- end: `0x18006fc15`
- name: `?ReadMrtConfigUInt32Value@IProfileHelpers@Resources@Microsoft@@SAJPEBGPEAIPEA_N@Z`
- size: `229`
- prototype: `static int(const unsigned __int16 *, unsigned int *, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800172a0`
- `0x1800564e0`

## callees

- `0x18006fb30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fbbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fbbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fb71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fb71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006fbaf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006fbaf`

## string_xrefs

- `0x18006fb8a`: `UseSystemMetadataPath`

## pseudocode

```c
LSTATUS __fastcall Microsoft::Resources::IProfileHelpers::ReadMrtConfigUInt32Value(
        const unsigned __int16 *a1,
        unsigned int *a2,
        bool *a3)
{
  LSTATUS result; // eax
  LSTATUS ValueW; // ebx
  const unsigned __int16 *pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+20h] BYREF

  pcbData = a1;
  hkey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Mrt", 0, 0x20119u, &hkey);
  if ( result )
  {
    *a2 = 0;
    if ( result == 2 )
      goto LABEL_4;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    LODWORD(pcbData) = 4;
    ValueW = RegGetValueW(hkey, 0, L"UseSystemMetadataPath", 0x10u, 0, a2, (LPDWORD)&pcbData);
    RegCloseKey(hkey);
    if ( !ValueW )
    {
      *a3 = 1;
      return 0;
    }
    *a2 = 0;
    if ( ValueW == 2 )
    {
LABEL_4:
      *a3 = 0;
      return 0;
    }
    if ( ValueW > 0 )
      return (unsigned __int16)ValueW | 0x80070000;
    return ValueW;
  }
  return result;
}

```

## disassembly

```asm
0x18006fb30  mov     r11, rsp
0x18006fb33  mov     [r11+10h], rbx
0x18006fb37  mov     [r11+18h], rsi
0x18006fb3b  mov     [r11+8], rcx
0x18006fb3f  push    rdi
0x18006fb40  sub     rsp, 40h
0x18006fb44  mov     rsi, r8
0x18006fb47  mov     qword ptr [r11+20h], 0
0x18006fb4f  mov     rdi, rdx
0x18006fb52  lea     rax, [r11+20h]
0x18006fb56  xor     r8d, r8d; ulOptions
0x18006fb59  mov     [r11-28h], rax
0x18006fb5d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006fb64  mov     r9d, 20119h; samDesired
0x18006fb6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fb71  call    cs:__imp_RegOpenKeyExW
0x18006fb77  test    eax, eax
0x18006fb79  jnz     short loc_18006FBE6
0x18006fb7b  mov     rcx, [rsp+48h+hkey]; hkey
0x18006fb80  lea     rax, [rsp+48h+arg_0]
0x18006fb85  mov     [rsp+48h+pcbData], rax; pcbData
0x18006fb8a  lea     r8, aUsesystemmetad; "UseSystemMetadataPath"
0x18006fb91  mov     [rsp+48h+pvData], rdi; pvData
0x18006fb96  mov     r9d, 10h; dwFlags
0x18006fb9c  xor     edx, edx; lpSubKey
0x18006fb9e  mov     [rsp+48h+pdwType], 0; pdwType
0x18006fba7  mov     dword ptr [rsp+48h+arg_0], 4
0x18006fbaf  call    cs:__imp_RegGetValueW
0x18006fbb5  mov     rcx, [rsp+48h+hkey]; hKey
0x18006fbba  mov     ebx, eax
0x18006fbbc  call    cs:__imp_RegCloseKey
0x18006fbc2  test    ebx, ebx
0x18006fbc4  jz      short loc_18006FBFF
0x18006fbc6  mov     dword ptr [rdi], 0
0x18006fbcc  cmp     ebx, 2
0x18006fbcf  jnz     short loc_18006FC04
0x18006fbd1  mov     byte ptr [rsi], 0
0x18006fbd4  xor     eax, eax
0x18006fbd6  mov     rbx, [rsp+48h+arg_8]
0x18006fbdb  mov     rsi, [rsp+48h+arg_10]
0x18006fbe0  add     rsp, 40h
0x18006fbe4  pop     rdi
0x18006fbe5  retn
0x18006fbe6  mov     dword ptr [rdi], 0
0x18006fbec  cmp     eax, 2
0x18006fbef  jz      short loc_18006FBD1
0x18006fbf1  test    eax, eax
0x18006fbf3  jle     short loc_18006FBD6
0x18006fbf5  movzx   eax, ax
0x18006fbf8  or      eax, 80070000h
0x18006fbfd  jmp     short loc_18006FBD6
0x18006fbff  mov     byte ptr [rsi], 1
0x18006fc02  jmp     short loc_18006FBD4
0x18006fc04  test    ebx, ebx
0x18006fc06  jle     short loc_18006FC11
0x18006fc08  movzx   ebx, bx
0x18006fc0b  or      ebx, 80070000h
0x18006fc11  mov     eax, ebx
0x18006fc13  jmp     short loc_18006FBD6
```
