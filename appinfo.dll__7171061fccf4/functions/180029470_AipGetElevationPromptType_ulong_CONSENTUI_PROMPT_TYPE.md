# AipGetElevationPromptType(ulong *,_CONSENTUI_PROMPT_TYPE *)

- ea: `0x180029470`
- end: `0x180029673`
- name: `?AipGetElevationPromptType@@YAKPEAKPEAW4_CONSENTUI_PROMPT_TYPE@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(unsigned int *, enum _CONSENTUI_PROMPT_TYPE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800290b4`

## callees

- `0x180029470`
- `0x180029a24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029505`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029505`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029536`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029536`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002965e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002965e`

## pseudocode

```c
__int64 __fastcall AipGetElevationPromptType(unsigned int *a1, enum _CONSENTUI_PROMPT_TYPE *a2)
{
  unsigned int v3; // ecx
  int v5; // ecx
  const WCHAR *v6; // r14
  int v7; // ebx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ebx
  DWORD cbData; // [rsp+70h] [rbp+38h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+40h] BYREF
  DWORD Type; // [rsp+80h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+50h] BYREF

  hKey = 0;
  v3 = *a1;
  cbData = 0;
  Type = 0;
  Data = 0;
  *(_DWORD *)a2 = 3;
  if ( (v3 & 0x20) != 0 )
  {
    v5 = v3 & 0x8000000;
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
  if ( (*a1 & 0x40000) != 0 )
  {
    if ( v7 == 4 )
    {
      *(_DWORD *)a2 = 3;
      goto LABEL_31;
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
           && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl'::`2'::impl))
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
      goto LABEL_42;
    }
    *(_DWORD *)a2 = 3;
    if ( v7 != 1 )
    {
LABEL_31:
      if ( (v8 & 0x8000020) != 0x8000020 )
        goto LABEL_33;
    }
LABEL_32:
    v8 |= 0x100u;
    *a1 = v8;
LABEL_33:
    if ( (v8 & 0x8000000) == 0
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl'::`2'::impl)
      || (*a1 & 0x2000020) != 0x20 )
    {
      goto LABEL_42;
    }
    v9 = *a1 | 0x8000;
    goto LABEL_41;
  }
  if ( (v8 & 0x8000020) == 0x20 )
  {
    if ( (v8 & 0x20000) == 0 )
    {
      *(_DWORD *)a2 = 1;
LABEL_42:
      v10 = 0;
      goto LABEL_44;
    }
    *(_DWORD *)a2 = 2;
    v9 = v8 | 0x100;
LABEL_41:
    *a1 = v9;
    goto LABEL_42;
  }
  v10 = 1260;
LABEL_44:
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x180029470  push    rbp
0x180029472  push    rbx
0x180029473  push    rsi
0x180029474  push    rdi
0x180029475  push    r12
0x180029477  push    r14
0x180029479  mov     rbp, rsp
0x18002947c  sub     rsp, 38h
0x180029480  mov     rdi, rcx
0x180029483  mov     [rbp+hKey], 0
0x18002948b  mov     ecx, [rcx]
0x18002948d  mov     r12d, 3
0x180029493  mov     [rbp+cbData], 0
0x18002949a  mov     rsi, rdx
0x18002949d  mov     [rbp+Type], 0
0x1800294a4  mov     [rbp+Data], 0
0x1800294ab  mov     [rdx], r12d
0x1800294ae  test    cl, 20h
0x1800294b1  jz      short loc_1800294DB
0x1800294b3  and     ecx, 8000000h
0x1800294b9  lea     r14, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x1800294c0  mov     eax, ecx
0x1800294c2  neg     eax
0x1800294c4  lea     rax, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x1800294cb  sbb     ebx, ebx
0x1800294cd  and     ebx, 0FFFFFFFDh
0x1800294d0  add     ebx, 5
0x1800294d3  test    ecx, ecx
0x1800294d5  cmovz   r14, rax
0x1800294d9  jmp     short loc_1800294E5
0x1800294db  mov     ebx, r12d
0x1800294de  lea     r14, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x1800294e5  lea     rax, [rbp+hKey]
0x1800294e9  mov     r9d, 20019h; samDesired
0x1800294ef  xor     r8d, r8d; ulOptions
0x1800294f2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800294f7  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800294fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029505  call    cs:__imp_RegOpenKeyExW
0x18002950b  test    eax, eax
0x18002950d  jnz     short loc_180029554
0x18002950f  mov     rcx, [rbp+hKey]; hKey
0x180029513  lea     rax, [rbp+cbData]
0x180029517  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002951c  lea     r9, [rbp+Type]; lpType
0x180029520  lea     rax, [rbp+Data]
0x180029524  mov     [rbp+cbData], 4
0x18002952b  xor     r8d, r8d; lpReserved
0x18002952e  mov     [rsp+38h+phkResult], rax; lpData
0x180029533  mov     rdx, r14; lpValueName
0x180029536  call    cs:__imp_RegQueryValueExW
0x18002953c  test    eax, eax
0x18002953e  jnz     short loc_180029554
0x180029540  cmp     [rbp+Type], 4
0x180029544  jnz     short loc_180029554
0x180029546  cmp     [rbp+cbData], 4
0x18002954a  jnz     short loc_180029554
0x18002954c  cmp     [rbp+Data], 6
0x180029550  cmovb   ebx, [rbp+Data]
0x180029554  mov     ecx, [rdi]
0x180029556  mov     r14d, 2
0x18002955c  bt      ecx, 12h
0x180029560  jnb     short loc_18002957B
0x180029562  cmp     ebx, 4
0x180029565  jnz     short loc_18002956C
0x180029567  mov     [rsi], r12d
0x18002956a  jmp     short loc_1800295EA
0x18002956c  cmp     ebx, r14d
0x18002956f  jz      short loc_180029576
0x180029571  cmp     ebx, r12d
0x180029574  jz      short loc_18002957B
0x180029576  mov     [rsi], r12d
0x180029579  jmp     short loc_1800295F7
0x18002957b  mov     edx, ebx
0x18002957d  test    ebx, ebx
0x18002957f  jz      loc_180029627
0x180029585  sub     edx, 1
0x180029588  jz      short loc_1800295E2
0x18002958a  sub     edx, 1
0x18002958d  jz      short loc_180029594
0x18002958f  sub     edx, 1
0x180029592  jz      short loc_1800295E2
0x180029594  test    cl, 20h
0x180029597  jz      short loc_1800295C7
0x180029599  mov     [rsi], r14d
0x18002959c  cmp     ebx, 5
0x18002959f  jz      short loc_1800295B7
0x1800295a1  bt      ecx, 1Bh
0x1800295a5  jnb     short loc_1800295CA
0x1800295a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800295ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(void)
0x1800295b3  test    al, al
0x1800295b5  jnz     short loc_1800295CA
0x1800295b7  mov     eax, [rdi]
0x1800295b9  bt      eax, 19h
0x1800295bd  jb      short loc_1800295CA
0x1800295bf  bts     eax, 0Fh
0x1800295c3  mov     [rdi], eax
0x1800295c5  jmp     short loc_1800295CA
0x1800295c7  mov     [rsi], r12d
0x1800295ca  cmp     ebx, r14d
0x1800295cd  jz      short loc_1800295DC
0x1800295cf  mov     eax, [rdi]
0x1800295d1  mov     edx, 8000020h
0x1800295d6  and     eax, edx
0x1800295d8  cmp     eax, edx
0x1800295da  jnz     short loc_18002964C
0x1800295dc  bts     dword ptr [rdi], 8
0x1800295e0  jmp     short loc_18002964C
0x1800295e2  mov     [rsi], r12d
0x1800295e5  cmp     ebx, 1
0x1800295e8  jz      short loc_1800295F7
0x1800295ea  mov     edx, 8000020h
0x1800295ef  mov     eax, ecx
0x1800295f1  and     eax, edx
0x1800295f3  cmp     eax, edx
0x1800295f5  jnz     short loc_1800295FD
0x1800295f7  bts     ecx, 8
0x1800295fb  mov     [rdi], ecx
0x1800295fd  bt      ecx, 1Bh
0x180029601  jnb     short loc_18002964C
0x180029603  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl(void)'::`2'::impl
0x18002960a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(void)
0x18002960f  test    al, al
0x180029611  jnz     short loc_18002964C
0x180029613  mov     ecx, [rdi]
0x180029615  mov     eax, ecx
0x180029617  and     eax, 2000020h
0x18002961c  cmp     eax, 20h ; ' '
0x18002961f  jnz     short loc_18002964C
0x180029621  bts     ecx, 0Fh
0x180029625  jmp     short loc_18002964A
0x180029627  mov     eax, ecx
0x180029629  mov     edx, 8000020h
0x18002962e  and     eax, edx
0x180029630  cmp     eax, 20h ; ' '
0x180029633  jnz     short loc_180029650
0x180029635  bt      ecx, 11h
0x180029639  jb      short loc_180029643
0x18002963b  mov     dword ptr [rsi], 1
0x180029641  jmp     short loc_18002964C
0x180029643  mov     [rsi], r14d
0x180029646  bts     ecx, 8
0x18002964a  mov     [rdi], ecx
0x18002964c  xor     ebx, ebx
0x18002964e  jmp     short loc_180029655
0x180029650  mov     ebx, 4ECh
0x180029655  mov     rcx, [rbp+hKey]; hKey
0x180029659  test    rcx, rcx
0x18002965c  jz      short loc_180029664
0x18002965e  call    cs:__imp_RegCloseKey
0x180029664  mov     eax, ebx
0x180029666  add     rsp, 38h
0x18002966a  pop     r14
0x18002966c  pop     r12
0x18002966e  pop     rdi
0x18002966f  pop     rsi
0x180029670  pop     rbx
0x180029671  pop     rbp
0x180029672  retn
```
