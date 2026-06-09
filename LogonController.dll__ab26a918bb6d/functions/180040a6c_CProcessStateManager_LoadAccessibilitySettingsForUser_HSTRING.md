# CProcessStateManager::_LoadAccessibilitySettingsForUser(HSTRING__ *)

- ea: `0x180040a6c`
- end: `0x180040d62`
- name: `?_LoadAccessibilitySettingsForUser@CProcessStateManager@@AEAAXPEAUHSTRING__@@@Z`
- size: `758`
- prototype: `void(CProcessStateManager *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800268e0`

## callees

- `0x180004b70`
- `0x180040a6c`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040ad2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040bda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040c33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040c8b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040bda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040c33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040c8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040b3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040b3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040b6b`

## string_xrefs

- `0x180040ae9`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`
- `0x180040ad8`: `Accessibility`

## pseudocode

```c
void __fastcall CProcessStateManager::_LoadAccessibilitySettingsForUser(CProcessStateManager *this, HSTRING a2)
{
  PCWSTR StringRawBuffer; // rax
  LSTATUS v4; // eax
  bool v5; // sf
  HKEY v6; // rcx
  LSTATUS ValueW; // eax
  bool v8; // sf
  LSTATUS v9; // eax
  bool v10; // sf
  bool v11; // di
  LSTATUS v12; // eax
  signed int v13; // ecx
  int v14; // eax
  int v15; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pdwType; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[256]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 53) )
  {
    *((_DWORD *)this + 111) = 1;
    *((_BYTE *)this + 452) = 1;
    *((_DWORD *)this + 112) = 100;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    if ( (int)StringCchPrintfW(
                SubKey,
                0xFFu,
                L"%s\\%s\\%s\\%s",
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                StringRawBuffer,
                L"AnyoneRead",
                L"Accessibility") >= 0 )
    {
      hKey = 0;
      v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v5 = v4 < 0;
      if ( v4 > 0 )
        v5 = 1;
      if ( v5 )
        goto LABEL_6;
      pvData = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hKey, 0, L"CaretWidth", 0x10u, 0, &pvData, &pcbData);
      v8 = ValueW < 0;
      if ( ValueW > 0 )
        v8 = 1;
      if ( !v8 )
      {
        v14 = pvData;
        *((_DWORD *)this + 111) = pvData;
        if ( v14 < 1 )
          *((_DWORD *)this + 111) = 1;
      }
      v20 = 0;
      pcbData = 4;
      v9 = RegGetValueW(hKey, 0, L"TextScaleFactor", 0x10u, 0, &v20, &pcbData);
      v10 = v9 < 0;
      if ( v9 > 0 )
        v10 = 1;
      if ( !v10 )
      {
        v15 = v20;
        *((_DWORD *)this + 112) = v20;
        if ( v15 >= 100 )
        {
          if ( v15 > 225 )
            *((_DWORD *)this + 112) = 225;
        }
        else
        {
          *((_DWORD *)this + 112) = 100;
        }
      }
      pcbData = 4;
      v11 = 0;
      pdwType = 0;
      v12 = RegGetValueW(hKey, 0, L"Transparency", 0x10000012u, &pdwType, &v17, &pcbData);
      v13 = v12;
      if ( v12 )
      {
        if ( v12 == 234 )
        {
          LOWORD(v13) = 13;
        }
        else if ( v12 <= 0 )
        {
          goto LABEL_19;
        }
        goto LABEL_18;
      }
      LOWORD(v13) = 13;
      if ( pdwType == 4 )
      {
        if ( v17 <= 1 )
        {
          v13 = 0;
          v11 = v17 == 1;
          goto LABEL_19;
        }
      }
      else if ( pcbData == 4 && (unsigned __int16)(v17 - 48) <= 1u )
      {
        v11 = (_WORD)v17 == 49;
        v13 = 0;
LABEL_19:
        if ( v13 >= 0 )
          *((_BYTE *)this + 452) = v11;
LABEL_6:
        v6 = hKey;
        hKey = 0;
        if ( v6 )
          RegCloseKey(v6);
        return;
      }
LABEL_18:
      v13 = (unsigned __int16)v13 | 0x80070000;
      goto LABEL_19;
    }
  }
}

```

## disassembly

```asm
0x180040a6c  mov     [rsp-8+arg_10], rbx
0x180040a71  mov     [rsp-8+arg_18], rdi
0x180040a76  push    rbp
0x180040a77  push    r12
0x180040a79  push    r14
0x180040a7b  lea     rbp, [rsp-170h]
0x180040a83  sub     rsp, 270h
0x180040a8a  mov     rax, cs:__security_cookie
0x180040a91  xor     rax, rsp
0x180040a94  mov     [rbp+180h+var_20], rax
0x180040a9b  cmp     qword ptr [rcx+1A8h], 0
0x180040aa3  mov     rax, rdx
0x180040aa6  mov     rbx, rcx
0x180040aa9  jz      loc_180040B71
0x180040aaf  mov     r14d, 1
0x180040ab5  xor     edx, edx; length
0x180040ab7  mov     [rcx+1BCh], r14d
0x180040abe  mov     [rcx+1C4h], r14b
0x180040ac5  lea     edi, [r14+63h]
0x180040ac9  mov     [rcx+1C0h], edi
0x180040acf  mov     rcx, rax; string
0x180040ad2  call    cs:__imp_WindowsGetStringRawBuffer
0x180040ad8  lea     rcx, aAccessibility; "Accessibility"
0x180040adf  mov     edx, 0FFh; unsigned __int64
0x180040ae4  mov     [rsp+280h+pcbData], rcx
0x180040ae9  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180040af0  mov     rcx, cs:off_18009E008; "AnyoneRead"
0x180040af7  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180040afe  mov     [rsp+280h+pvData], rcx
0x180040b03  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180040b08  mov     [rsp+280h+phkResult], rax
0x180040b0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040b12  test    eax, eax
0x180040b14  js      short loc_180040B71
0x180040b16  lea     rax, [rsp+280h+hKey]
0x180040b1b  mov     [rsp+280h+hKey], 0
0x180040b24  mov     r9d, 20019h; samDesired
0x180040b2a  mov     [rsp+280h+phkResult], rax; phkResult
0x180040b2f  xor     r8d, r8d; ulOptions
0x180040b32  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180040b37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040b3e  call    cs:__imp_RegOpenKeyExW
0x180040b44  mov     r12d, 80070000h
0x180040b4a  test    eax, eax
0x180040b4c  jle     short loc_180040B56
0x180040b4e  movzx   eax, ax
0x180040b51  or      eax, r12d
0x180040b54  test    eax, eax
0x180040b56  jns     short loc_180040B99
0x180040b58  mov     rcx, [rsp+280h+hKey]; hKey
0x180040b5d  mov     [rsp+280h+hKey], 0
0x180040b66  test    rcx, rcx
0x180040b69  jz      short loc_180040B71
0x180040b6b  call    cs:__imp_RegCloseKey
0x180040b71  mov     rcx, [rbp+180h+var_20]
0x180040b78  xor     rcx, rsp; StackCookie
0x180040b7b  call    __security_check_cookie
0x180040b80  lea     r11, [rsp+280h+var_10]
0x180040b88  mov     rbx, [r11+30h]
0x180040b8c  mov     rdi, [r11+38h]
0x180040b90  mov     rsp, r11
0x180040b93  pop     r14
0x180040b95  pop     r12
0x180040b97  pop     rbp
0x180040b98  retn
0x180040b99  mov     rcx, [rsp+280h+hKey]; hkey
0x180040b9e  lea     rax, [rsp+280h+var_240]
0x180040ba3  mov     [rsp+280h+pcbData], rax; pcbData
0x180040ba8  lea     r8, aCaretwidth; "CaretWidth"
0x180040baf  lea     rax, [rsp+280h+var_230]
0x180040bb4  mov     [rsp+280h+var_230], 0
0x180040bbc  mov     [rsp+280h+pvData], rax; pvData
0x180040bc1  mov     r9d, 10h; dwFlags
0x180040bc7  xor     edx, edx; lpSubKey
0x180040bc9  mov     [rsp+280h+phkResult], 0; pdwType
0x180040bd2  mov     [rsp+280h+var_240], 4
0x180040bda  call    cs:__imp_RegGetValueW
0x180040be0  test    eax, eax
0x180040be2  jle     short loc_180040BEC
0x180040be4  movzx   eax, ax
0x180040be7  or      eax, r12d
0x180040bea  test    eax, eax
0x180040bec  jns     loc_180040D08
0x180040bf2  mov     rcx, [rsp+280h+hKey]; hkey
0x180040bf7  lea     rax, [rsp+280h+var_240]
0x180040bfc  mov     [rsp+280h+pcbData], rax; pcbData
0x180040c01  lea     r8, aTextscalefacto; "TextScaleFactor"
0x180040c08  lea     rax, [rsp+280h+var_22C]
0x180040c0d  mov     [rsp+280h+var_22C], 0
0x180040c15  mov     [rsp+280h+pvData], rax; pvData
0x180040c1a  mov     r9d, 10h; dwFlags
0x180040c20  xor     edx, edx; lpSubKey
0x180040c22  mov     [rsp+280h+phkResult], 0; pdwType
0x180040c2b  mov     [rsp+280h+var_240], 4
0x180040c33  call    cs:__imp_RegGetValueW
0x180040c39  test    eax, eax
0x180040c3b  jle     short loc_180040C45
0x180040c3d  movzx   eax, ax
0x180040c40  or      eax, r12d
0x180040c43  test    eax, eax
0x180040c45  jns     loc_180040D27
0x180040c4b  mov     rcx, [rsp+280h+hKey]; hkey
0x180040c50  lea     rax, [rsp+280h+var_240]
0x180040c55  mov     [rsp+280h+pcbData], rax; pcbData
0x180040c5a  lea     r8, aTransparency; "Transparency"
0x180040c61  lea     rax, [rsp+280h+var_23C]
0x180040c66  mov     [rsp+280h+var_240], 4
0x180040c6e  mov     [rsp+280h+pvData], rax; pvData
0x180040c73  xor     edi, edi
0x180040c75  lea     rax, [rsp+280h+pdwType]
0x180040c7a  mov     [rsp+280h+pdwType], edi
0x180040c7e  mov     r9d, 10000012h; dwFlags
0x180040c84  mov     [rsp+280h+phkResult], rax; pdwType
0x180040c89  xor     edx, edx; lpSubKey
0x180040c8b  call    cs:__imp_RegGetValueW
0x180040c91  mov     ecx, eax
0x180040c93  test    eax, eax
0x180040c95  jz      short loc_180040CC0
0x180040c97  cmp     eax, 0EAh
0x180040c9c  jz      loc_180040D58
0x180040ca2  test    eax, eax
0x180040ca4  jle     short loc_180040CAC
0x180040ca6  movzx   ecx, cx
0x180040ca9  or      ecx, r12d
0x180040cac  test    ecx, ecx
0x180040cae  js      loc_180040B58
0x180040cb4  mov     [rbx+1C4h], dil
0x180040cbb  jmp     loc_180040B58
0x180040cc0  cmp     [rsp+280h+pdwType], 4
0x180040cc5  mov     ecx, 0Dh
0x180040cca  jnz     short loc_180040CE0
0x180040ccc  cmp     [rsp+280h+var_23C], r14d
0x180040cd1  ja      short loc_180040CA6
0x180040cd3  xor     ecx, ecx
0x180040cd5  cmp     [rsp+280h+var_23C], r14d
0x180040cda  setz    dil
0x180040cde  jmp     short loc_180040CAC
0x180040ce0  cmp     [rsp+280h+var_240], 4
0x180040ce5  jnz     short loc_180040CA6
0x180040ce7  movzx   eax, word ptr [rsp+280h+var_23C]
0x180040cec  sub     ax, 30h ; '0'
0x180040cf0  cmp     ax, r14w
0x180040cf4  ja      short loc_180040CA6
0x180040cf6  mov     eax, 31h ; '1'
0x180040cfb  cmp     ax, word ptr [rsp+280h+var_23C]
0x180040d00  setz    dil
0x180040d04  xor     ecx, ecx
0x180040d06  jmp     short loc_180040CAC
0x180040d08  mov     eax, [rsp+280h+var_230]
0x180040d0c  mov     [rbx+1BCh], eax
0x180040d12  cmp     eax, r14d
0x180040d15  jge     loc_180040BF2
0x180040d1b  mov     [rbx+1BCh], r14d
0x180040d22  jmp     loc_180040BF2
0x180040d27  mov     eax, [rsp+280h+var_22C]
0x180040d2b  mov     [rbx+1C0h], eax
0x180040d31  cmp     eax, edi
0x180040d33  jge     short loc_180040D40
0x180040d35  mov     [rbx+1C0h], edi
0x180040d3b  jmp     loc_180040C4B
0x180040d40  mov     ecx, 0E1h
0x180040d45  cmp     eax, ecx
0x180040d47  jle     loc_180040C4B
0x180040d4d  mov     [rbx+1C0h], ecx
0x180040d53  jmp     loc_180040C4B
0x180040d58  mov     ecx, 0Dh
0x180040d5d  jmp     loc_180040CA6
```
