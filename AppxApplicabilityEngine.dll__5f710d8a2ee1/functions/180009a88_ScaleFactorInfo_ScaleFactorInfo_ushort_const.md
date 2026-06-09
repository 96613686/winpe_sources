# ScaleFactorInfo::ScaleFactorInfo(ushort const *)

- ea: `0x180009a88`
- end: `0x180009bf0`
- name: `??0ScaleFactorInfo@@QEAA@PEBG@Z`
- size: `360`
- prototype: `ScaleFactorInfo *__fastcall(ScaleFactorInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009984`

## callees

- `0x180009a88`
- `0x180009bf8`
- `0x180009c84`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009b59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009bb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009bb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009b39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009b39`

## string_xrefs

- `0x180009aea`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
ScaleFactorInfo *__fastcall ScaleFactorInfo::ScaleFactorInfo(ScaleFactorInfo *this, const unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  bool v4; // sf
  int v5; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 44) = a2;
  *((_BYTE *)this + 360) = 0;
  hKey = 0;
  if ( !a2 )
  {
    v5 = OpenSystemDataRegistryPathForCurrentUser((const unsigned __int16 *)this, &hKey);
    goto LABEL_5;
  }
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s\\%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
              a2,
              L"AnyoneRead",
              L"ScaleFactors") < 0 )
    goto LABEL_7;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v4 = v3 < 0;
  if ( v3 > 0 )
  {
    v5 = (unsigned __int16)v3 | 0x80070000;
LABEL_5:
    v4 = v5 < 0;
  }
  if ( !v4 )
  {
    Type = 0;
    cbData = 320;
    if ( !RegQueryValueExW(hKey, L"ScaleFactors", 0, &Type, (LPBYTE)this + 32, &cbData)
      && Type == 3
      && (cbData & 0x1F) == 0 )
    {
      *(_DWORD *)this = cbData >> 5;
    }
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return this;
}

```

## disassembly

```asm
0x180009a88  mov     [rsp-8+arg_8], rbx
0x180009a8d  mov     [rsp-8+arg_10], rsi
0x180009a92  push    rbp
0x180009a93  lea     rbp, [rsp-170h]
0x180009a9b  sub     rsp, 270h
0x180009aa2  mov     rax, cs:__security_cookie
0x180009aa9  xor     rax, rsp
0x180009aac  mov     [rbp+170h+var_10], rax
0x180009ab3  mov     dword ptr [rcx], 0
0x180009ab9  mov     rbx, rcx
0x180009abc  mov     [rcx+160h], rdx
0x180009ac3  lea     rsi, ValueName; "ScaleFactors"
0x180009aca  mov     byte ptr [rcx+168h], 0
0x180009ad1  mov     [rsp+270h+hKey], 0
0x180009ada  test    rdx, rdx
0x180009add  jz      loc_180009BE1
0x180009ae3  mov     rax, cs:off_180026238; "AnyoneRead"
0x180009aea  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009af1  mov     [rsp+270h+var_240], rsi
0x180009af6  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180009afd  mov     [rsp+270h+lpcbData], rax
0x180009b02  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x180009b07  mov     [rsp+270h+phkResult], rdx
0x180009b0c  mov     edx, 104h; unsigned __int64
0x180009b11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009b16  test    eax, eax
0x180009b18  js      short loc_180009B4F
0x180009b1a  lea     rax, [rsp+270h+hKey]
0x180009b1f  mov     r9d, 20019h; samDesired
0x180009b25  xor     r8d, r8d; ulOptions
0x180009b28  mov     [rsp+270h+phkResult], rax; phkResult
0x180009b2d  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180009b32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009b39  call    cs:__imp_RegOpenKeyExW
0x180009b3f  test    eax, eax
0x180009b41  jle     short loc_180009B4D
0x180009b43  movzx   eax, ax
0x180009b46  or      eax, 80070000h
0x180009b4b  test    eax, eax
0x180009b4d  jns     short loc_180009B86
0x180009b4f  mov     rcx, [rsp+270h+hKey]; hKey
0x180009b54  test    rcx, rcx
0x180009b57  jz      short loc_180009B5F
0x180009b59  call    cs:__imp_RegCloseKey
0x180009b5f  mov     rax, rbx
0x180009b62  mov     rcx, [rbp+170h+var_10]
0x180009b69  xor     rcx, rsp; StackCookie
0x180009b6c  call    __security_check_cookie
0x180009b71  lea     r11, [rsp+270h+var_s0]
0x180009b79  mov     rbx, [r11+18h]
0x180009b7d  mov     rsi, [r11+20h]
0x180009b81  mov     rsp, r11
0x180009b84  pop     rbp
0x180009b85  retn
0x180009b86  lea     rcx, [rsp+270h+cbData]
0x180009b8b  mov     [rsp+270h+Type], 0
0x180009b93  mov     [rsp+270h+lpcbData], rcx; lpcbData
0x180009b98  lea     rax, [rbx+20h]
0x180009b9c  mov     rcx, [rsp+270h+hKey]; hKey
0x180009ba1  lea     r9, [rsp+270h+Type]; lpType
0x180009ba6  xor     r8d, r8d; lpReserved
0x180009ba9  mov     [rsp+270h+cbData], 140h
0x180009bb1  mov     rdx, rsi; lpValueName
0x180009bb4  mov     [rsp+270h+phkResult], rax; lpData
0x180009bb9  call    cs:__imp_RegQueryValueExW
0x180009bbf  test    eax, eax
0x180009bc1  jnz     short loc_180009B4F
0x180009bc3  cmp     [rsp+270h+Type], 3
0x180009bc8  jnz     short loc_180009B4F
0x180009bca  mov     ecx, [rsp+270h+cbData]
0x180009bce  test    cl, 1Fh
0x180009bd1  jnz     loc_180009B4F
0x180009bd7  shr     ecx, 5; unsigned __int16 *
0x180009bda  mov     [rbx], ecx
0x180009bdc  jmp     loc_180009B4F
0x180009be1  lea     rdx, [rsp+270h+hKey]; HKEY *
0x180009be6  call    ?OpenSystemDataRegistryPathForCurrentUser@@YAJPEBGPEAPEAUHKEY__@@@Z; OpenSystemDataRegistryPathForCurrentUser(ushort const *,HKEY__ * *)
0x180009beb  jmp     loc_180009B4B
```
