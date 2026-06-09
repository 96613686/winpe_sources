# CheckRedirectDisabledValueLocation(ushort const *)

- ea: `0x1800249b0`
- end: `0x180024b18`
- name: `?CheckRedirectDisabledValueLocation@@YA_NPEBG@Z`
- size: `360`
- prototype: `bool __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024b20`

## callees

- `0x18001be10`
- `0x1800249b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024a9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024a9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024aef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024aef`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024a78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024a78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024a3a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024a3a`

## pseudocode

```c
char __fastcall CheckRedirectDisabledValueLocation(LPCWSTR lpSubKey)
{
  char v1; // bl
  DWORD v2; // edi
  LSTATUS i; // eax
  DWORD cbData; // [rsp+58h] [rbp+7h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp+Bh] BYREF
  DWORD cchValueName; // [rsp+60h] [rbp+Fh] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp+13h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+17h] BYREF
  DWORD v10; // [rsp+70h] [rbp+1Fh] BYREF
  WCHAR ValueName[20]; // [rsp+78h] [rbp+27h] BYREF

  hKey = 0;
  v10 = 0;
  v1 = 0;
  cchValueName = 20;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20019u, 0, &hKey, &v10) )
    return v1;
  v2 = 0;
  for ( i = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, Data, &cbData);
        i;
        i = RegEnumValueW(hKey, v2, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
  {
    if ( i != 234 )
      goto LABEL_10;
LABEL_8:
    cchValueName = 20;
    ++v2;
    cbData = 4;
  }
  if ( Type != 4 || (unsigned int)_o__wcsicmp(ValueName, L"fEnableSmartCard") )
    goto LABEL_8;
  v1 = 1;
  g_bRedirectDisabled = *(_DWORD *)Data == 0;
LABEL_10:
  RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x1800249b0  mov     r11, rsp
0x1800249b3  mov     [r11+10h], rbx
0x1800249b7  mov     [r11+18h], rdi
0x1800249bb  push    rbp
0x1800249bc  lea     rbp, [r11-5Fh]
0x1800249c0  sub     rsp, 0A0h
0x1800249c7  mov     rax, cs:__security_cookie
0x1800249ce  xor     rax, rsp
0x1800249d1  mov     [rbp+57h+var_8], rax
0x1800249d5  lea     rax, [rbp+57h+var_38]
0x1800249d9  mov     [rbp+57h+hKey], 0
0x1800249e1  mov     [r11-68h], rax
0x1800249e5  mov     rdx, rcx; lpSubKey
0x1800249e8  lea     rax, [rbp+57h+hKey]
0x1800249ec  mov     [rbp+57h+var_38], 0
0x1800249f3  mov     [r11-70h], rax
0x1800249f7  xor     r9d, r9d; lpClass
0x1800249fa  mov     qword ptr [r11-78h], 0
0x180024a02  xor     r8d, r8d; Reserved
0x180024a05  mov     [rsp+0A0h+samDesired], 20019h; samDesired
0x180024a0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024a14  mov     [rsp+0A0h+dwOptions], 0; dwOptions
0x180024a1c  xor     bl, bl
0x180024a1e  mov     [rbp+57h+cchValueName], 14h
0x180024a25  mov     [rbp+57h+Type], 0
0x180024a2c  mov     dword ptr [rbp+57h+Data], 0
0x180024a33  mov     [rbp+57h+cbData], 4
0x180024a3a  call    cs:__imp_RegCreateKeyExW
0x180024a40  test    eax, eax
0x180024a42  jnz     loc_180024AF5
0x180024a48  lea     rax, [rbp+57h+cbData]
0x180024a4c  xor     edi, edi
0x180024a4e  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x180024a53  xor     edx, edx; dwIndex
0x180024a55  lea     rax, [rbp+57h+Data]
0x180024a59  mov     [rsp+0A0h+lpData], rax; lpData
0x180024a5e  lea     rax, [rbp+57h+Type]
0x180024a62  mov     qword ptr [rsp+0A0h+samDesired], rax; lpType
0x180024a67  mov     qword ptr [rsp+0A0h+dwOptions], rdi; lpReserved
0x180024a6c  mov     rcx, [rbp+57h+hKey]; hKey
0x180024a70  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180024a74  lea     r8, [rbp+57h+ValueName]; lpValueName
0x180024a78  call    cs:__imp_RegEnumValueW
0x180024a7e  test    eax, eax
0x180024a80  jz      short loc_180024A8B
0x180024a82  cmp     eax, 0EAh
0x180024a87  jnz     short loc_180024AEB
0x180024a89  jmp     short loc_180024AA6
0x180024a8b  cmp     [rbp+57h+Type], 4
0x180024a8f  jnz     short loc_180024AA6
0x180024a91  lea     rdx, aFenablesmartca; "fEnableSmartCard"
0x180024a98  lea     rcx, [rbp+57h+ValueName]
0x180024a9c  call    cs:__imp__o__wcsicmp
0x180024aa2  test    eax, eax
0x180024aa4  jz      short loc_180024ADE
0x180024aa6  lea     rax, [rbp+57h+cbData]
0x180024aaa  mov     [rbp+57h+cchValueName], 14h
0x180024ab1  mov     [rsp+0A0h+lpcbData], rax
0x180024ab6  inc     edi
0x180024ab8  lea     rax, [rbp+57h+Data]
0x180024abc  mov     [rbp+57h+cbData], 4
0x180024ac3  mov     [rsp+0A0h+lpData], rax
0x180024ac8  mov     edx, edi
0x180024aca  lea     rax, [rbp+57h+Type]
0x180024ace  mov     qword ptr [rsp+0A0h+samDesired], rax
0x180024ad3  mov     qword ptr [rsp+0A0h+dwOptions], 0
0x180024adc  jmp     short loc_180024A6C
0x180024ade  cmp     dword ptr [rbp+57h+Data], 0
0x180024ae2  mov     bl, 1
0x180024ae4  setz    cs:?g_bRedirectDisabled@@3_NA; bool g_bRedirectDisabled
0x180024aeb  mov     rcx, [rbp+57h+hKey]; hKey
0x180024aef  call    cs:__imp_RegCloseKey
0x180024af5  mov     al, bl
0x180024af7  mov     rcx, [rbp+57h+var_8]
0x180024afb  xor     rcx, rsp; StackCookie
0x180024afe  call    __security_check_cookie
0x180024b03  lea     r11, [rsp+0A0h+var_s0]
0x180024b0b  mov     rbx, [r11+18h]
0x180024b0f  mov     rdi, [r11+20h]
0x180024b13  mov     rsp, r11
0x180024b16  pop     rbp
0x180024b17  retn
```
