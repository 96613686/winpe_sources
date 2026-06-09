# sub_18001CDDC

- ea: `0x18001cddc`
- end: `0x18001ced7`
- name: `sub_18001CDDC`
- size: `251`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d640`

## callees

- `0x18001cddc`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001ce72`
- `ADVAPI32!RegQueryValueExW` at `0x18001ce72`
- `ADVAPI32!RegCloseKey` at `0x18001ce9e`
- `ADVAPI32!RegCloseKey` at `0x18001cec4`
- `ADVAPI32!RegCloseKey` at `0x18001ce9e`
- `ADVAPI32!RegCloseKey` at `0x18001cec4`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ce23`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ce23`

## string_xrefs

- `0x18001ce15`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Media Center\Service\Content Security\Shared`

## pseudocode

```c
__int64 __fastcall sub_18001CDDC(__int64 a1)
{
  HKEY v1; // rbx
  __int64 Type; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Type = a1;
  if ( byte_180089864 )
    return byte_180089865 == 0;
  byte_180089864 = 1;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Media Center\\Service\\Content Security\\Shared",
          0,
          0x20019u,
          &hKey) )
  {
    v1 = hKey;
    Data = 0;
    LODWORD(Type) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"License Renewal Testing Enabled", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData)
      && (_DWORD)Type == 4 )
    {
      if ( Data )
        byte_180089865 = 1;
      if ( v1 )
        RegCloseKey(v1);
      return byte_180089865 == 0;
    }
    if ( v1 )
      RegCloseKey(v1);
  }
  return 1;
}

```

## disassembly

```asm
0x18001cddc  mov     r11, rsp
0x18001cddf  mov     [r11+8], rcx
0x18001cde3  push    rbx
0x18001cde4  sub     rsp, 30h
0x18001cde8  cmp     cs:byte_180089864, 0
0x18001cdef  jnz     loc_18001CEAA
0x18001cdf5  lea     rax, [r11+20h]
0x18001cdf9  mov     cs:byte_180089864, 1
0x18001ce00  mov     r9d, 20019h; samDesired
0x18001ce06  mov     [r11-18h], rax
0x18001ce0a  xor     r8d, r8d; ulOptions
0x18001ce0d  mov     qword ptr [r11+20h], 0
0x18001ce15  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ce1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ce23  call    cs:RegOpenKeyExW
0x18001ce2a  nop     dword ptr [rax+rax+00h]
0x18001ce2f  test    eax, eax
0x18001ce31  jnz     loc_18001CED0
0x18001ce37  mov     rbx, [rsp+38h+hKey]
0x18001ce3c  lea     r9, [rsp+38h+Type]; lpType
0x18001ce41  mov     [rsp+38h+Data], eax
0x18001ce45  lea     rdx, aLicenseRenewal; "License Renewal Testing Enabled"
0x18001ce4c  mov     dword ptr [rsp+38h+Type], eax
0x18001ce50  xor     r8d, r8d; lpReserved
0x18001ce53  lea     rax, [rsp+38h+cbData]
0x18001ce58  mov     [rsp+38h+cbData], 4
0x18001ce60  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001ce65  mov     rcx, rbx; hKey
0x18001ce68  lea     rax, [rsp+38h+Data]
0x18001ce6d  mov     [rsp+38h+lpData], rax; lpData
0x18001ce72  call    cs:RegQueryValueExW
0x18001ce79  nop     dword ptr [rax+rax+00h]
0x18001ce7e  test    eax, eax
0x18001ce80  jnz     short loc_18001CEBC
0x18001ce82  cmp     dword ptr [rsp+38h+Type], 4
0x18001ce87  jnz     short loc_18001CEBC
0x18001ce89  cmp     [rsp+38h+Data], eax
0x18001ce8d  jz      short loc_18001CE96
0x18001ce8f  mov     cs:byte_180089865, 1
0x18001ce96  test    rbx, rbx
0x18001ce99  jz      short loc_18001CEAA
0x18001ce9b  mov     rcx, rbx; hKey
0x18001ce9e  call    cs:RegCloseKey
0x18001cea5  nop     dword ptr [rax+rax+00h]
0x18001ceaa  xor     eax, eax
0x18001ceac  cmp     cs:byte_180089865, al
0x18001ceb2  setz    al
0x18001ceb5  add     rsp, 30h
0x18001ceb9  pop     rbx
0x18001ceba  retn
0x18001cebc  test    rbx, rbx
0x18001cebf  jz      short loc_18001CED0
0x18001cec1  mov     rcx, rbx; hKey
0x18001cec4  call    cs:RegCloseKey
0x18001cecb  nop     dword ptr [rax+rax+00h]
0x18001ced0  mov     eax, 1
0x18001ced5  jmp     short loc_18001CEB5
```
