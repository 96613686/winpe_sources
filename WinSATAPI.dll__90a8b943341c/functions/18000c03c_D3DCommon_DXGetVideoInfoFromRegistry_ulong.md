# D3DCommon::DXGetVideoInfoFromRegistry(ulong *)

- ea: `0x18000c03c`
- end: `0x18000c13d`
- name: `?DXGetVideoInfoFromRegistry@D3DCommon@@YAJPEAK@Z`
- size: `257`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ba80`

## callees

- `0x18000c03c`
- `0x18000f638`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c10d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c10d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0f1`

## pseudocode

```c
__int64 __fastcall D3DCommon::DXGetVideoInfoFromRegistry(D3DCommon *this, HKEY *a2)
{
  int VideoRegKey; // edi
  DWORD cbData; // [rsp+30h] [rbp-9h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-1h] BYREF
  DWORD Type; // [rsp+40h] [rbp+7h] BYREF
  WCHAR ValueName[8]; // [rsp+48h] [rbp+Fh] BYREF
  __int64 v10; // [rsp+78h] [rbp+3Fh]
  int v11; // [rsp+80h] [rbp+47h]
  wchar_t v12; // [rsp+84h] [rbp+4Bh]

  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  Type = 0;
  wmemcpy(ValueName, L"HardwareInformation.MemorySize", 24);
  v11 = *(_DWORD *)L"ze";
  v12 = aHardwareinform[30];
  *(_DWORD *)this = 0;
  v10 = *(_QWORD *)L"rySize";
  VideoRegKey = D3DCommon::GetVideoRegKey((D3DCommon *)&hKey, a2);
  if ( VideoRegKey >= 0 )
  {
    cbData = 4;
    RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData);
    *(_DWORD *)this = *(_DWORD *)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)VideoRegKey;
}

```

## disassembly

```asm
0x18000c03c  mov     [rsp-8+arg_8], rsi
0x18000c041  mov     [rsp-8+arg_10], rdi
0x18000c046  push    rbp
0x18000c047  lea     rbp, [rsp-57h]
0x18000c04c  sub     rsp, 90h
0x18000c053  mov     rax, cs:__security_cookie
0x18000c05a  xor     rax, rsp
0x18000c05d  mov     [rbp+57h+var_8], rax
0x18000c061  movups  xmm0, xmmword ptr cs:aHardwareinform; "HardwareInformation.MemorySize"
0x18000c068  mov     eax, dword ptr cs:aHardwareinform+38h; "ze"
0x18000c06e  mov     rsi, rcx
0x18000c071  movups  xmm1, xmmword ptr cs:aHardwareinform+10h; "Information.MemorySize"
0x18000c078  and     dword ptr [rbp+57h+Data], 0
0x18000c07c  and     [rbp+57h+cbData], 0
0x18000c080  and     [rbp+57h+hKey], 0
0x18000c085  and     [rbp+57h+Type], 0
0x18000c089  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18000c08d  mov     [rbp+57h+var_10], eax
0x18000c090  movups  xmm0, xmmword ptr cs:aHardwareinform+20h; "ion.MemorySize"
0x18000c097  movzx   eax, word ptr cs:aHardwareinform+3Ch; ""
0x18000c09e  movups  [rbp+57h+var_38], xmm1
0x18000c0a2  mov     [rbp+57h+var_C], ax
0x18000c0a6  movups  [rbp+57h+var_28], xmm0
0x18000c0aa  movsd   xmm0, qword ptr cs:aHardwareinform+30h; "rySize"
0x18000c0b2  and     dword ptr [rcx], 0
0x18000c0b5  lea     rcx, [rbp+57h+hKey]; this
0x18000c0b9  movsd   [rbp+57h+var_18], xmm0
0x18000c0be  call    ?GetVideoRegKey@D3DCommon@@YAJPEAPEAUHKEY__@@@Z; D3DCommon::GetVideoRegKey(HKEY__ * *)
0x18000c0c3  mov     edi, eax
0x18000c0c5  test    eax, eax
0x18000c0c7  js      short loc_18000C102
0x18000c0c9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c0cd  lea     rax, [rbp+57h+cbData]
0x18000c0d1  mov     [rsp+90h+lpcbData], rax; lpcbData
0x18000c0d6  lea     r9, [rbp+57h+Type]; lpType
0x18000c0da  lea     rax, [rbp+57h+Data]
0x18000c0de  mov     [rbp+57h+cbData], 4
0x18000c0e5  xor     r8d, r8d; lpReserved
0x18000c0e8  mov     [rsp+90h+lpData], rax; lpData
0x18000c0ed  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18000c0f1  call    cs:__imp_RegQueryValueExW
0x18000c0f8  nop     dword ptr [rax+rax+00h]
0x18000c0fd  mov     eax, dword ptr [rbp+57h+Data]
0x18000c100  mov     [rsi], eax
0x18000c102  cmp     [rbp+57h+hKey], 0
0x18000c107  jz      short loc_18000C119
0x18000c109  mov     rcx, [rbp+57h+hKey]; hKey
0x18000c10d  call    cs:__imp_RegCloseKey
0x18000c114  nop     dword ptr [rax+rax+00h]
0x18000c119  mov     eax, edi
0x18000c11b  mov     rcx, [rbp+57h+var_8]
0x18000c11f  xor     rcx, rsp; StackCookie
0x18000c122  call    __security_check_cookie
0x18000c127  lea     r11, [rsp+90h+var_s0]
0x18000c12f  mov     rsi, [r11+18h]
0x18000c133  mov     rdi, [r11+20h]
0x18000c137  mov     rsp, r11
0x18000c13a  pop     rbp
0x18000c13b  retn
```
