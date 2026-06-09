# DiacriticsInspection::IsUpdated(IMigrationContext *)

- ea: `0x180010a58`
- end: `0x180010c49`
- name: `?IsUpdated@DiacriticsInspection@@YA_NPEAUIMigrationContext@@@Z`
- size: `497`
- prototype: `char __fastcall(struct IUnknown *this, struct IMigrationContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800149a0`

## callees

- `0x1800026f0`
- `0x180010a58`
- `0x180011220`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180010ac2`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180010ac2`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180010adc`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180010adc`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180010aab`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180010aab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010ba6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010ba6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010c10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010c10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010bda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010bda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c1b`

## pseudocode

```c
char __fastcall DiacriticsInspection::IsUpdated(struct IUnknown *this, struct IMigrationContext *a2)
{
  char v3; // bl
  LCID v4; // eax
  __int16 SystemDefaultLCID; // cx
  __int64 v6; // rdx
  ULONG pulNumLanguages; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v10[9]; // [rsp+48h] [rbp-B8h]
  __int16 v11; // [rsp+6Ch] [rbp-94h]
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pwszLanguagesBuffer[264]; // [rsp+80h] [rbp-80h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 256;
  v3 = 0;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer)
    || !pulNumLanguages )
  {
    goto LABEL_6;
  }
  v4 = LocaleNameToLCID(pwszLanguagesBuffer, 0);
  SystemDefaultLCID = v4;
  if ( v4 != 4096 )
  {
    if ( v4 )
      goto LABEL_7;
LABEL_6:
    SystemDefaultLCID = GetSystemDefaultLCID();
    goto LABEL_7;
  }
  SystemDefaultLCID = 127;
LABEL_7:
  v10[0] = 68289553;
  v11 = 1101;
  v6 = 0;
  v10[1] = 72614995;
  v10[2] = 71697465;
  v10[3] = 71894087;
  v10[4] = 72025162;
  v10[5] = 72287310;
  v10[6] = 71631959;
  v10[7] = 72091717;
  v10[8] = 73073736;
  while ( SystemDefaultLCID != *((_WORD *)v10 + v6) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0x13 )
      return v3;
  }
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 4;
  MapRegKeyPathIfNeeded(this, (OLECHAR *)L"SOFTWARE\\Microsoft\\Windows Search");
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          pwszLanguagesBuffer,
          L"SystemIndexNormalization",
          0x18u,
          0,
          &pulNumLanguages,
          &pcchLanguagesBuffer)
    && (pulNumLanguages & 2) == 0 )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pwszLanguagesBuffer, 0, 0x40000000u, &phkResult) )
    {
      pulNumLanguages |= 2u;
      RegSetValueExW(phkResult, L"SystemIndexNormalization", 0, 4u, (const BYTE *)&pulNumLanguages, 4u);
      RegCloseKey(phkResult);
      return 1;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180010a58  mov     [rsp-8+arg_8], rbx
0x180010a5d  mov     [rsp-8+arg_10], rdi
0x180010a62  push    rbp
0x180010a63  lea     rbp, [rsp-1A0h]
0x180010a6b  sub     rsp, 2A0h
0x180010a72  mov     rax, cs:__security_cookie
0x180010a79  xor     rax, rsp
0x180010a7c  mov     [rbp+1A0h+var_10], rax
0x180010a83  mov     rdi, rcx
0x180010a86  mov     [rsp+2A0h+pulNumLanguages], 0
0x180010a8e  mov     ecx, 8; dwFlags
0x180010a93  mov     [rsp+2A0h+pcchLanguagesBuffer], 100h
0x180010a9b  lea     r9, [rsp+2A0h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180010aa0  xor     bl, bl
0x180010aa2  lea     r8, [rbp+1A0h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180010aa6  lea     rdx, [rsp+2A0h+pulNumLanguages]; pulNumLanguages
0x180010aab  call    cs:__imp_GetSystemPreferredUILanguages
0x180010ab1  test    eax, eax
0x180010ab3  jz      short loc_180010ADC
0x180010ab5  cmp     [rsp+2A0h+pulNumLanguages], 0
0x180010aba  jbe     short loc_180010ADC
0x180010abc  xor     edx, edx; dwFlags
0x180010abe  lea     rcx, [rbp+1A0h+pwszLanguagesBuffer]; lpName
0x180010ac2  call    cs:__imp_LocaleNameToLCID
0x180010ac8  mov     ecx, eax
0x180010aca  cmp     eax, 1000h
0x180010acf  jnz     short loc_180010AD8
0x180010ad1  mov     ecx, 7Fh
0x180010ad6  jmp     short loc_180010AE4
0x180010ad8  test    eax, eax
0x180010ada  jnz     short loc_180010AE4
0x180010adc  call    cs:__imp_GetSystemDefaultLCID
0x180010ae2  mov     ecx, eax
0x180010ae4  mov     eax, 44Dh
0x180010ae9  mov     [rsp+2A0h+var_258], 4120411h
0x180010af1  mov     [rsp+2A0h+var_234], ax
0x180010af6  xor     edx, edx
0x180010af8  mov     [rsp+2A0h+var_254], 4540453h
0x180010b00  mov     [rsp+2A0h+var_250], 4460439h
0x180010b08  mov     [rsp+2A0h+var_24C], 4490447h
0x180010b10  mov     [rsp+2A0h+var_248], 44B044Ah
0x180010b18  mov     [rsp+2A0h+var_244], 44F044Eh
0x180010b20  mov     [rsp+2A0h+var_240], 4450457h
0x180010b28  mov     [rsp+2A0h+var_23C], 44C0845h
0x180010b30  mov     [rsp+2A0h+var_238], 45B0448h
0x180010b38  cmp     cx, word ptr [rsp+rdx*2+2A0h+var_258]
0x180010b3d  jz      short loc_180010B4B
0x180010b3f  inc     edx
0x180010b41  cmp     edx, 13h
0x180010b44  jb      short loc_180010B38
0x180010b46  jmp     loc_180010C23
0x180010b4b  lea     r8, [rbp+1A0h+pwszLanguagesBuffer]
0x180010b4f  mov     [rsp+2A0h+pulNumLanguages], 0
0x180010b57  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Search"
0x180010b5e  mov     [rsp+2A0h+pcchLanguagesBuffer], 4
0x180010b66  mov     rcx, rdi; struct IUnknown *
0x180010b69  call    MapRegKeyPathIfNeeded
0x180010b6e  lea     rax, [rsp+2A0h+pcchLanguagesBuffer]
0x180010b73  mov     rdi, 0FFFFFFFF80000002h
0x180010b7a  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180010b7f  lea     r8, Value; "SystemIndexNormalization"
0x180010b86  lea     rax, [rsp+2A0h+pulNumLanguages]
0x180010b8b  mov     r9d, 18h; dwFlags
0x180010b91  mov     [rsp+2A0h+pvData], rax; pvData
0x180010b96  lea     rdx, [rbp+1A0h+pwszLanguagesBuffer]; lpSubKey
0x180010b9a  mov     rcx, rdi; hkey
0x180010b9d  mov     [rsp+2A0h+pdwType], 0; pdwType
0x180010ba6  call    cs:__imp_RegGetValueW
0x180010bac  test    eax, eax
0x180010bae  jnz     short loc_180010C23
0x180010bb0  test    byte ptr [rsp+2A0h+pulNumLanguages], 2
0x180010bb5  jnz     short loc_180010C23
0x180010bb7  lea     rax, [rsp+2A0h+phkResult]
0x180010bbc  mov     [rsp+2A0h+phkResult], 0
0x180010bc5  mov     r9d, 40000000h; samDesired
0x180010bcb  mov     [rsp+2A0h+pdwType], rax; phkResult
0x180010bd0  xor     r8d, r8d; ulOptions
0x180010bd3  lea     rdx, [rbp+1A0h+pwszLanguagesBuffer]; lpSubKey
0x180010bd7  mov     rcx, rdi; hKey
0x180010bda  call    cs:__imp_RegOpenKeyExW
0x180010be0  test    eax, eax
0x180010be2  jnz     short loc_180010C23
0x180010be4  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x180010be9  lea     rax, [rsp+2A0h+pulNumLanguages]
0x180010bee  or      [rsp+2A0h+pulNumLanguages], 2
0x180010bf3  lea     rdx, Value; "SystemIndexNormalization"
0x180010bfa  mov     dword ptr [rsp+2A0h+pvData], 4; cbData
0x180010c02  mov     r9d, 4; dwType
0x180010c08  xor     r8d, r8d; Reserved
0x180010c0b  mov     [rsp+2A0h+pdwType], rax; lpData
0x180010c10  call    cs:__imp_RegSetValueExW
0x180010c16  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x180010c1b  call    cs:__imp_RegCloseKey
0x180010c21  mov     bl, 1
0x180010c23  mov     al, bl
0x180010c25  mov     rcx, [rbp+1A0h+var_10]
0x180010c2c  xor     rcx, rsp; StackCookie
0x180010c2f  call    __security_check_cookie
0x180010c34  lea     r11, [rsp+2A0h+var_s0]
0x180010c3c  mov     rbx, [r11+18h]
0x180010c40  mov     rdi, [r11+20h]
0x180010c44  mov     rsp, r11
0x180010c47  pop     rbp
0x180010c48  retn
```
