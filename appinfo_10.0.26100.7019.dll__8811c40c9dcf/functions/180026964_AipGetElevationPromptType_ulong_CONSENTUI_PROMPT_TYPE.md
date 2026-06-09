# AipGetElevationPromptType(ulong *,_CONSENTUI_PROMPT_TYPE *)

- ea: `0x180026964`
- end: `0x180026b74`
- name: `?AipGetElevationPromptType@@YAKPEAKPEAW4_CONSENTUI_PROMPT_TYPE@@@Z`
- size: `528`
- prototype: `unsigned int __fastcall(unsigned int *, enum _CONSENTUI_PROMPT_TYPE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800263a8`

## callees

- `0x180026964`
- `0x180026f00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800269ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800269ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026a24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b57`

## pseudocode

```c
__int64 __fastcall AipGetElevationPromptType(unsigned int *a1, enum _CONSENTUI_PROMPT_TYPE *a2)
{
  unsigned int v4; // ecx
  int v5; // ecx
  const WCHAR *v6; // r14
  int v7; // ebx
  unsigned int v8; // ecx
  unsigned int v9; // r14d
  unsigned int v10; // ecx
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+40h] BYREF
  DWORD Type; // [rsp+80h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+50h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  v4 = *a1;
  *(_DWORD *)a2 = 3;
  if ( (v4 & 0x20) != 0 )
  {
    v5 = v4 & 0x8000000;
    v6 = L"ConsentPromptBehaviorEnhancedAdmin";
    v7 = v5 != 0 ? 2 : 5;
    if ( !v5 )
      v6 = L"ConsentPromptBehaviorAdmin";
  }
  else
  {
    v7 = 3;
    v6 = L"ConsentPromptBehaviorUser";
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, v6, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 && Data < 6 )
      v7 = Data;
  }
  v8 = *a1;
  v9 = 0;
  if ( (*a1 & 0x40000) != 0 )
  {
    if ( v7 == 4 )
    {
      *(_DWORD *)a2 = 3;
LABEL_31:
      if ( (v8 & 0x8000020) != 0x8000020 )
      {
LABEL_33:
        if ( (v8 & 0x8000000) != 0
          && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl'::`2'::impl)
          && (*a1 & 0x2000020) == 0x20 )
        {
          v10 = *a1 | 0x8000;
LABEL_41:
          *a1 = v10;
          goto LABEL_43;
        }
        goto LABEL_43;
      }
LABEL_32:
      v8 |= 0x100u;
      *a1 = v8;
      goto LABEL_33;
    }
    if ( v7 != 3 )
    {
      *(_DWORD *)a2 = 3;
      goto LABEL_32;
    }
  }
  if ( v7 )
  {
    if ( v7 != 1 && v7 != 3 )
    {
      if ( (v8 & 0x20) != 0 )
      {
        *(_DWORD *)a2 = 2;
        if ( (v7 == 5
           || (v8 & 0x8000000) != 0
           && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl'::`2'::impl))
          && (*a1 & 0x2000000) == 0 )
        {
          *a1 |= 0x8000u;
        }
      }
      else
      {
        *(_DWORD *)a2 = 3;
      }
      if ( v7 == 2 || (*a1 & 0x8000020) == 0x8000020 )
        *a1 |= 0x100u;
      goto LABEL_43;
    }
    *(_DWORD *)a2 = 3;
    if ( v7 == 1 )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( (v8 & 0x8000020) == 0x20 )
  {
    if ( (v8 & 0x20000) == 0 )
    {
      *(_DWORD *)a2 = 1;
      goto LABEL_43;
    }
    *(_DWORD *)a2 = 2;
    v10 = v8 | 0x100;
    goto LABEL_41;
  }
  v9 = 1260;
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180026964  push    rbp
0x180026966  push    rbx
0x180026967  push    rsi
0x180026968  push    rdi
0x180026969  push    r12
0x18002696b  push    r14
0x18002696d  mov     rbp, rsp
0x180026970  sub     rsp, 38h
0x180026974  and     [rbp+hKey], 0
0x180026979  mov     rdi, rcx
0x18002697c  and     [rbp+cbData], 0
0x180026980  mov     r12d, 3
0x180026986  and     [rbp+Type], 0
0x18002698a  mov     rsi, rdx
0x18002698d  and     [rbp+Data], 0
0x180026991  mov     ecx, [rcx]
0x180026993  mov     [rdx], r12d
0x180026996  test    cl, 20h
0x180026999  jz      short loc_1800269C3
0x18002699b  and     ecx, 8000000h
0x1800269a1  lea     r14, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x1800269a8  mov     eax, ecx
0x1800269aa  neg     eax
0x1800269ac  lea     rax, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x1800269b3  sbb     ebx, ebx
0x1800269b5  and     ebx, 0FFFFFFFDh
0x1800269b8  add     ebx, 5
0x1800269bb  test    ecx, ecx
0x1800269bd  cmovz   r14, rax
0x1800269c1  jmp     short loc_1800269CD
0x1800269c3  mov     ebx, r12d
0x1800269c6  lea     r14, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x1800269cd  lea     rax, [rbp+hKey]
0x1800269d1  mov     r9d, 20019h; samDesired
0x1800269d7  xor     r8d, r8d; ulOptions
0x1800269da  mov     [rsp+38h+phkResult], rax; phkResult
0x1800269df  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800269e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800269ed  call    cs:__imp_RegOpenKeyExW
0x1800269f4  nop     dword ptr [rax+rax+00h]
0x1800269f9  test    eax, eax
0x1800269fb  jnz     short loc_180026A48
0x1800269fd  mov     rcx, [rbp+hKey]; hKey
0x180026a01  lea     rax, [rbp+cbData]
0x180026a05  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180026a0a  lea     r9, [rbp+Type]; lpType
0x180026a0e  lea     rax, [rbp+Data]
0x180026a12  mov     [rbp+cbData], 4
0x180026a19  xor     r8d, r8d; lpReserved
0x180026a1c  mov     [rsp+38h+phkResult], rax; lpData
0x180026a21  mov     rdx, r14; lpValueName
0x180026a24  call    cs:__imp_RegQueryValueExW
0x180026a2b  nop     dword ptr [rax+rax+00h]
0x180026a30  test    eax, eax
0x180026a32  jnz     short loc_180026A48
0x180026a34  cmp     [rbp+Type], 4
0x180026a38  jnz     short loc_180026A48
0x180026a3a  cmp     [rbp+cbData], 4
0x180026a3e  jnz     short loc_180026A48
0x180026a40  cmp     [rbp+Data], 6
0x180026a44  cmovb   ebx, [rbp+Data]
0x180026a48  mov     ecx, [rdi]
0x180026a4a  xor     r14d, r14d
0x180026a4d  bt      ecx, 12h
0x180026a51  jnb     short loc_180026A6F
0x180026a53  cmp     ebx, 4
0x180026a56  jnz     short loc_180026A60
0x180026a58  mov     [rsi], r12d
0x180026a5b  jmp     loc_180026AE1
0x180026a60  cmp     ebx, 2
0x180026a63  jz      short loc_180026A6A
0x180026a65  cmp     ebx, r12d
0x180026a68  jz      short loc_180026A6F
0x180026a6a  mov     [rsi], r12d
0x180026a6d  jmp     short loc_180026AEE
0x180026a6f  mov     edx, ebx
0x180026a71  test    ebx, ebx
0x180026a73  jz      loc_180026B1E
0x180026a79  sub     edx, 1
0x180026a7c  jz      short loc_180026AD9
0x180026a7e  sub     edx, 1
0x180026a81  jz      short loc_180026A88
0x180026a83  sub     edx, 1
0x180026a86  jz      short loc_180026AD9
0x180026a88  test    cl, 20h
0x180026a8b  jz      short loc_180026ABE
0x180026a8d  mov     dword ptr [rsi], 2
0x180026a93  cmp     ebx, 5
0x180026a96  jz      short loc_180026AAE
0x180026a98  bt      ecx, 1Bh
0x180026a9c  jnb     short loc_180026AC1
0x180026a9e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl(void)'::`2'::impl
0x180026aa5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(void)
0x180026aaa  test    al, al
0x180026aac  jnz     short loc_180026AC1
0x180026aae  mov     eax, [rdi]
0x180026ab0  bt      eax, 19h
0x180026ab4  jb      short loc_180026AC1
0x180026ab6  bts     eax, 0Fh
0x180026aba  mov     [rdi], eax
0x180026abc  jmp     short loc_180026AC1
0x180026abe  mov     [rsi], r12d
0x180026ac1  cmp     ebx, 2
0x180026ac4  jz      short loc_180026AD3
0x180026ac6  mov     eax, [rdi]
0x180026ac8  mov     edx, 8000020h
0x180026acd  and     eax, edx
0x180026acf  cmp     eax, edx
0x180026ad1  jnz     short loc_180026B4E
0x180026ad3  bts     dword ptr [rdi], 8
0x180026ad7  jmp     short loc_180026B4E
0x180026ad9  mov     [rsi], r12d
0x180026adc  cmp     ebx, 1
0x180026adf  jz      short loc_180026AEE
0x180026ae1  mov     edx, 8000020h
0x180026ae6  mov     eax, ecx
0x180026ae8  and     eax, edx
0x180026aea  cmp     eax, edx
0x180026aec  jnz     short loc_180026AF4
0x180026aee  bts     ecx, 8
0x180026af2  mov     [rdi], ecx
0x180026af4  bt      ecx, 1Bh
0x180026af8  jnb     short loc_180026B4E
0x180026afa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl(void)'::`2'::impl
0x180026b01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(void)
0x180026b06  test    al, al
0x180026b08  jnz     short loc_180026B4E
0x180026b0a  mov     ecx, [rdi]
0x180026b0c  mov     eax, ecx
0x180026b0e  and     eax, 2000020h
0x180026b13  cmp     eax, 20h ; ' '
0x180026b16  jnz     short loc_180026B4E
0x180026b18  bts     ecx, 0Fh
0x180026b1c  jmp     short loc_180026B44
0x180026b1e  mov     eax, ecx
0x180026b20  mov     edx, 8000020h
0x180026b25  and     eax, edx
0x180026b27  cmp     eax, 20h ; ' '
0x180026b2a  jnz     short loc_180026B48
0x180026b2c  bt      ecx, 11h
0x180026b30  jb      short loc_180026B3A
0x180026b32  mov     dword ptr [rsi], 1
0x180026b38  jmp     short loc_180026B4E
0x180026b3a  mov     dword ptr [rsi], 2
0x180026b40  bts     ecx, 8
0x180026b44  mov     [rdi], ecx
0x180026b46  jmp     short loc_180026B4E
0x180026b48  mov     r14d, 4ECh
0x180026b4e  mov     rcx, [rbp+hKey]; hKey
0x180026b52  test    rcx, rcx
0x180026b55  jz      short loc_180026B63
0x180026b57  call    cs:__imp_RegCloseKey
0x180026b5e  nop     dword ptr [rax+rax+00h]
0x180026b63  mov     eax, r14d
0x180026b66  add     rsp, 38h
0x180026b6a  pop     r14
0x180026b6c  pop     r12
0x180026b6e  pop     rdi
0x180026b6f  pop     rsi
0x180026b70  pop     rbx
0x180026b71  pop     rbp
0x180026b72  retn
```
