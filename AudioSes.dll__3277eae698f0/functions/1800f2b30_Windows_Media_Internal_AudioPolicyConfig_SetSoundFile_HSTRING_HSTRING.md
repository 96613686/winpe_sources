# Windows::Media::Internal::AudioPolicyConfig::SetSoundFile(HSTRING__ *,HSTRING__ *)

- ea: `0x1800f2b30`
- end: `0x1800f2d8d`
- name: `?SetSoundFile@AudioPolicyConfig@Internal@Media@Windows@@UEAAJPEAUHSTRING__@@0@Z`
- size: `605`
- prototype: `int(Windows::Media::Internal::AudioPolicyConfig *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010a90`
- `0x1800165ac`
- `0x180087e80`
- `0x18009d564`
- `0x1800c87dc`
- `0x1800c89e8`
- `0x1800f2b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f2d24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f2d24`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f2c8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f2c8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f2c45`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f2c45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800f2cd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800f2cd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2b84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2bbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2b84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2bbe`

## string_xrefs

- `0x1800f2bfa`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f2d4c`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Media::Internal::AudioPolicyConfig::SetSoundFile(
        Windows::Media::Internal::AudioPolicyConfig *this,
        HSTRING a2,
        HSTRING a3)
{
  const BYTE *StringRawBuffer; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int ValueW; // ebx
  unsigned int v9; // eax
  const char *v10; // r9
  __int64 v11; // rdx
  const BYTE *v12; // rax
  int v13; // r9d
  int v14; // ecx
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v24[264]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE pvData[528]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  pcbData = 520;
  hKey = 0;
  StringRawBuffer = (const BYTE *)WindowsGetStringRawBuffer(a3, 0);
  pdwType = (unsigned int)WindowsGetStringRawBuffer(a2, 0);
  v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\EventSounds\\Sounds");
  v6 = v5;
  if ( v5 >= 0 )
  {
    pdwType = (unsigned int)WindowsGetStringRawBuffer(a2, 0);
    v5 = StringCchPrintfW(v24, 0x104u, L"%s\\%s", L"OSDATA\\SOFTWARE\\Microsoft\\EventSounds\\Sounds");
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 1566;
      goto LABEL_5;
    }
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Sound", 2u, 0, pvData, &pcbData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v24, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
    {
      v10 = (const char *)v9;
      v11 = 1571;
LABEL_22:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
             v10,
             pdwTypea);
      goto LABEL_23;
    }
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v10 = (const char *)ValueW;
        v11 = 1595;
        goto LABEL_22;
      }
    }
    else
    {
      v12 = StringRawBuffer;
      do
      {
        v13 = *(unsigned __int16 *)&v12[pvData - StringRawBuffer];
        v14 = *(unsigned __int16 *)v12 - v13;
        if ( v14 )
          break;
        v12 += 2;
      }
      while ( v13 );
      if ( !v14 )
      {
        v15 = RegDeleteValueW(hKey, L"Sound");
        if ( v15 )
        {
          v10 = (const char *)v15;
          v11 = 1579;
          goto LABEL_22;
        }
LABEL_20:
        v6 = 0;
        goto LABEL_23;
      }
    }
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&StringRawBuffer[2 * v16] );
    v17 = RegSetValueExW(hKey, L"Sound", 0, 1u, StringRawBuffer, 2 * v16 + 2);
    if ( v17 )
    {
      v10 = (const char *)v17;
      v11 = 1589;
      goto LABEL_22;
    }
    goto LABEL_20;
  }
  v7 = 1563;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
    (const char *)(unsigned int)v5,
    pdwType);
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x1800f2b30  mov     [rsp-8+arg_0], rbx
0x1800f2b35  mov     [rsp-8+arg_18], rsi
0x1800f2b3a  push    rbp
0x1800f2b3b  push    rdi
0x1800f2b3c  push    r14
0x1800f2b3e  lea     rbp, [rsp-5A0h]
0x1800f2b46  sub     rsp, 6A0h
0x1800f2b4d  mov     rax, cs:__security_cookie
0x1800f2b54  xor     rax, rsp
0x1800f2b57  mov     [rbp+5B0h+var_20], rax
0x1800f2b5e  mov     rsi, rdx
0x1800f2b61  mov     [rsp+6B0h+var_658], 208h
0x1800f2b69  xor     r14d, r14d
0x1800f2b6c  xor     edx, edx; length
0x1800f2b6e  mov     rcx, r8; string
0x1800f2b71  mov     [rsp+6B0h+hKey], r14
0x1800f2b76  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2b7c  xor     edx, edx; length
0x1800f2b7e  mov     rcx, rsi; string
0x1800f2b81  mov     rdi, rax
0x1800f2b84  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2b8a  lea     r9, aSoftwareMicros; "Software\\Microsoft\\EventSounds\\Sound"...
0x1800f2b91  mov     edx, 104h; unsigned __int64
0x1800f2b96  lea     r8, aSS; "%s\\%s"
0x1800f2b9d  mov     [rsp+6B0h+pdwType], rax
0x1800f2ba2  lea     rcx, [rsp+6B0h+SubKey]; unsigned __int16 *
0x1800f2ba7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f2bac  mov     ebx, eax
0x1800f2bae  test    eax, eax
0x1800f2bb0  jns     short loc_1800F2BB9
0x1800f2bb2  mov     edx, 61Bh
0x1800f2bb7  jmp     short loc_1800F2BF3
0x1800f2bb9  xor     edx, edx; length
0x1800f2bbb  mov     rcx, rsi; string
0x1800f2bbe  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2bc4  lea     r9, aOsdataSoftware; "OSDATA\\SOFTWARE\\Microsoft\\EventSound"...
0x1800f2bcb  mov     edx, 104h; unsigned __int64
0x1800f2bd0  lea     r8, aSS; "%s\\%s"
0x1800f2bd7  mov     [rsp+6B0h+pdwType], rax; int
0x1800f2bdc  lea     rcx, [rbp+5B0h+var_440]; unsigned __int16 *
0x1800f2be3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f2be8  mov     ebx, eax
0x1800f2bea  test    eax, eax
0x1800f2bec  jns     short loc_1800F2C0E
0x1800f2bee  mov     edx, 61Eh; void *
0x1800f2bf3  mov     rcx, [rbp+5B8h]; this
0x1800f2bfa  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f2c01  mov     r9d, eax; char *
0x1800f2c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2c09  jmp     loc_1800F2D5A
0x1800f2c0e  lea     rax, [rsp+6B0h+var_658]
0x1800f2c13  mov     rsi, 0FFFFFFFF80000002h
0x1800f2c1a  mov     [rsp+6B0h+pcbData], rax; pcbData
0x1800f2c1f  lea     r8, aSound_0; "Sound"
0x1800f2c26  lea     rax, [rbp+5B0h+var_230]
0x1800f2c2d  mov     r9d, 2; dwFlags
0x1800f2c33  mov     [rsp+6B0h+pvData], rax; pvData
0x1800f2c38  lea     rdx, [rsp+6B0h+SubKey]; lpSubKey
0x1800f2c3d  mov     rcx, rsi; hkey
0x1800f2c40  mov     [rsp+6B0h+pdwType], r14; pdwType
0x1800f2c45  call    cs:__imp_RegGetValueW
0x1800f2c4b  xor     edx, edx
0x1800f2c4d  lea     rcx, [rsp+6B0h+hKey]
0x1800f2c52  mov     ebx, eax
0x1800f2c54  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f2c59  mov     [rsp+6B0h+lpdwDisposition], r14; lpdwDisposition
0x1800f2c5e  lea     rax, [rsp+6B0h+hKey]
0x1800f2c63  mov     [rsp+6B0h+phkResult], rax; phkResult
0x1800f2c68  lea     rdx, [rbp+5B0h+var_440]; lpSubKey
0x1800f2c6f  mov     [rsp+6B0h+pcbData], r14; lpSecurityAttributes
0x1800f2c74  xor     r9d, r9d; lpClass
0x1800f2c77  mov     dword ptr [rsp+6B0h+pvData], 2; samDesired
0x1800f2c7f  xor     r8d, r8d; Reserved
0x1800f2c82  mov     rcx, rsi; hKey
0x1800f2c85  mov     dword ptr [rsp+6B0h+pdwType], r14d; unsigned int
0x1800f2c8a  call    cs:__imp_RegCreateKeyExW
0x1800f2c90  test    eax, eax
0x1800f2c92  jz      short loc_1800F2CA1
0x1800f2c94  mov     r9d, eax
0x1800f2c97  mov     edx, 623h
0x1800f2c9c  jmp     loc_1800F2D45
0x1800f2ca1  test    ebx, ebx
0x1800f2ca3  jnz     short loc_1800F2CEC
0x1800f2ca5  lea     r8, [rbp+5B0h+var_230]
0x1800f2cac  mov     rax, rdi
0x1800f2caf  sub     r8, rdi
0x1800f2cb2  movzx   ecx, word ptr [rax]
0x1800f2cb5  movzx   r9d, word ptr [rax+r8]
0x1800f2cba  sub     ecx, r9d
0x1800f2cbd  jnz     short loc_1800F2CC8
0x1800f2cbf  add     rax, 2
0x1800f2cc3  test    r9d, r9d
0x1800f2cc6  jnz     short loc_1800F2CB2
0x1800f2cc8  test    ecx, ecx
0x1800f2cca  jnz     short loc_1800F2CF1
0x1800f2ccc  mov     rcx, [rsp+6B0h+hKey]; hKey
0x1800f2cd1  lea     rdx, aSound_0; "Sound"
0x1800f2cd8  call    cs:__imp_RegDeleteValueW
0x1800f2cde  test    eax, eax
0x1800f2ce0  jz      short loc_1800F2D38
0x1800f2ce2  mov     r9d, eax
0x1800f2ce5  mov     edx, 62Bh
0x1800f2cea  jmp     short loc_1800F2D45
0x1800f2cec  cmp     ebx, 2
0x1800f2cef  jnz     short loc_1800F2D3D
0x1800f2cf1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f2cf5  inc     rax
0x1800f2cf8  cmp     [rdi+rax*2], r14w
0x1800f2cfd  jnz     short loc_1800F2CF5
0x1800f2cff  mov     rcx, [rsp+6B0h+hKey]; hKey
0x1800f2d04  lea     eax, ds:2[rax*2]
0x1800f2d0b  mov     dword ptr [rsp+6B0h+pvData], eax; cbData
0x1800f2d0f  lea     rdx, aSound_0; "Sound"
0x1800f2d16  mov     r9d, 1; dwType
0x1800f2d1c  mov     [rsp+6B0h+pdwType], rdi; lpData
0x1800f2d21  xor     r8d, r8d; Reserved
0x1800f2d24  call    cs:__imp_RegSetValueExW
0x1800f2d2a  test    eax, eax
0x1800f2d2c  jz      short loc_1800F2D38
0x1800f2d2e  mov     r9d, eax
0x1800f2d31  mov     edx, 635h
0x1800f2d36  jmp     short loc_1800F2D45
0x1800f2d38  mov     ebx, r14d
0x1800f2d3b  jmp     short loc_1800F2D5A
0x1800f2d3d  mov     r9d, ebx; char *
0x1800f2d40  mov     edx, 63Bh; void *
0x1800f2d45  mov     rcx, [rbp+5B8h]; this
0x1800f2d4c  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f2d53  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f2d58  mov     ebx, eax
0x1800f2d5a  lea     rcx, [rsp+6B0h+hKey]
0x1800f2d5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f2d64  mov     eax, ebx
0x1800f2d66  mov     rcx, [rbp+5B0h+var_20]
0x1800f2d6d  xor     rcx, rsp; StackCookie
0x1800f2d70  call    __security_check_cookie
0x1800f2d75  lea     r11, [rsp+6B0h+var_10]
0x1800f2d7d  mov     rbx, [r11+20h]
0x1800f2d81  mov     rsi, [r11+38h]
0x1800f2d85  mov     rsp, r11
0x1800f2d88  pop     r14
0x1800f2d8a  pop     rdi
0x1800f2d8b  pop     rbp
0x1800f2d8c  retn
```
