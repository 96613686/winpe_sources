# AipGetElevationPromptType(ulong *,_CONSENTUI_PROMPT_TYPE *)

- ea: `0x180025070`
- end: `0x180025280`
- name: `?AipGetElevationPromptType@@YAKPEAKPEAW4_CONSENTUI_PROMPT_TYPE@@@Z`
- size: `528`
- prototype: `unsigned int __fastcall(unsigned int *, enum _CONSENTUI_PROMPT_TYPE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024a98`

## callees

- `0x180025070`
- `0x1800258bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800250f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800250f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025130`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025130`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025263`

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
0x180025070  push    rbp
0x180025072  push    rbx
0x180025073  push    rsi
0x180025074  push    rdi
0x180025075  push    r12
0x180025077  push    r14
0x180025079  mov     rbp, rsp
0x18002507c  sub     rsp, 38h
0x180025080  and     [rbp+hKey], 0
0x180025085  mov     rdi, rcx
0x180025088  and     [rbp+cbData], 0
0x18002508c  mov     r12d, 3
0x180025092  and     [rbp+Type], 0
0x180025096  mov     rsi, rdx
0x180025099  and     [rbp+Data], 0
0x18002509d  mov     ecx, [rcx]
0x18002509f  mov     [rdx], r12d
0x1800250a2  test    cl, 20h
0x1800250a5  jz      short loc_1800250CF
0x1800250a7  and     ecx, 8000000h
0x1800250ad  lea     r14, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x1800250b4  mov     eax, ecx
0x1800250b6  neg     eax
0x1800250b8  lea     rax, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x1800250bf  sbb     ebx, ebx
0x1800250c1  and     ebx, 0FFFFFFFDh
0x1800250c4  add     ebx, 5
0x1800250c7  test    ecx, ecx
0x1800250c9  cmovz   r14, rax
0x1800250cd  jmp     short loc_1800250D9
0x1800250cf  mov     ebx, r12d
0x1800250d2  lea     r14, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x1800250d9  lea     rax, [rbp+hKey]
0x1800250dd  mov     r9d, 20019h; samDesired
0x1800250e3  xor     r8d, r8d; ulOptions
0x1800250e6  mov     [rsp+38h+phkResult], rax; phkResult
0x1800250eb  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800250f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800250f9  call    cs:__imp_RegOpenKeyExW
0x180025100  nop     dword ptr [rax+rax+00h]
0x180025105  test    eax, eax
0x180025107  jnz     short loc_180025154
0x180025109  mov     rcx, [rbp+hKey]; hKey
0x18002510d  lea     rax, [rbp+cbData]
0x180025111  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180025116  lea     r9, [rbp+Type]; lpType
0x18002511a  lea     rax, [rbp+Data]
0x18002511e  mov     [rbp+cbData], 4
0x180025125  xor     r8d, r8d; lpReserved
0x180025128  mov     [rsp+38h+phkResult], rax; lpData
0x18002512d  mov     rdx, r14; lpValueName
0x180025130  call    cs:__imp_RegQueryValueExW
0x180025137  nop     dword ptr [rax+rax+00h]
0x18002513c  test    eax, eax
0x18002513e  jnz     short loc_180025154
0x180025140  cmp     [rbp+Type], 4
0x180025144  jnz     short loc_180025154
0x180025146  cmp     [rbp+cbData], 4
0x18002514a  jnz     short loc_180025154
0x18002514c  cmp     [rbp+Data], 6
0x180025150  cmovb   ebx, [rbp+Data]
0x180025154  mov     ecx, [rdi]
0x180025156  xor     r14d, r14d
0x180025159  bt      ecx, 12h
0x18002515d  jnb     short loc_18002517B
0x18002515f  cmp     ebx, 4
0x180025162  jnz     short loc_18002516C
0x180025164  mov     [rsi], r12d
0x180025167  jmp     loc_1800251ED
0x18002516c  cmp     ebx, 2
0x18002516f  jz      short loc_180025176
0x180025171  cmp     ebx, r12d
0x180025174  jz      short loc_18002517B
0x180025176  mov     [rsi], r12d
0x180025179  jmp     short loc_1800251FA
0x18002517b  mov     edx, ebx
0x18002517d  test    ebx, ebx
0x18002517f  jz      loc_18002522A
0x180025185  sub     edx, 1
0x180025188  jz      short loc_1800251E5
0x18002518a  sub     edx, 1
0x18002518d  jz      short loc_180025194
0x18002518f  sub     edx, 1
0x180025192  jz      short loc_1800251E5
0x180025194  test    cl, 20h
0x180025197  jz      short loc_1800251CA
0x180025199  mov     dword ptr [rsi], 2
0x18002519f  cmp     ebx, 5
0x1800251a2  jz      short loc_1800251BA
0x1800251a4  bt      ecx, 1Bh
0x1800251a8  jnb     short loc_1800251CD
0x1800251aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800251b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(void)
0x1800251b6  test    al, al
0x1800251b8  jnz     short loc_1800251CD
0x1800251ba  mov     eax, [rdi]
0x1800251bc  bt      eax, 19h
0x1800251c0  jb      short loc_1800251CD
0x1800251c2  bts     eax, 0Fh
0x1800251c6  mov     [rdi], eax
0x1800251c8  jmp     short loc_1800251CD
0x1800251ca  mov     [rsi], r12d
0x1800251cd  cmp     ebx, 2
0x1800251d0  jz      short loc_1800251DF
0x1800251d2  mov     eax, [rdi]
0x1800251d4  mov     edx, 8000020h
0x1800251d9  and     eax, edx
0x1800251db  cmp     eax, edx
0x1800251dd  jnz     short loc_18002525A
0x1800251df  bts     dword ptr [rdi], 8
0x1800251e3  jmp     short loc_18002525A
0x1800251e5  mov     [rsi], r12d
0x1800251e8  cmp     ebx, 1
0x1800251eb  jz      short loc_1800251FA
0x1800251ed  mov     edx, 8000020h
0x1800251f2  mov     eax, ecx
0x1800251f4  and     eax, edx
0x1800251f6  cmp     eax, edx
0x1800251f8  jnz     short loc_180025200
0x1800251fa  bts     ecx, 8
0x1800251fe  mov     [rdi], ecx
0x180025200  bt      ecx, 1Bh
0x180025204  jnb     short loc_18002525A
0x180025206  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::GetImpl(void)'::`2'::impl
0x18002520d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoveAutoElevationForShadowAdmin>::__private_IsEnabled(void)
0x180025212  test    al, al
0x180025214  jnz     short loc_18002525A
0x180025216  mov     ecx, [rdi]
0x180025218  mov     eax, ecx
0x18002521a  and     eax, 2000020h
0x18002521f  cmp     eax, 20h ; ' '
0x180025222  jnz     short loc_18002525A
0x180025224  bts     ecx, 0Fh
0x180025228  jmp     short loc_180025250
0x18002522a  mov     eax, ecx
0x18002522c  mov     edx, 8000020h
0x180025231  and     eax, edx
0x180025233  cmp     eax, 20h ; ' '
0x180025236  jnz     short loc_180025254
0x180025238  bt      ecx, 11h
0x18002523c  jb      short loc_180025246
0x18002523e  mov     dword ptr [rsi], 1
0x180025244  jmp     short loc_18002525A
0x180025246  mov     dword ptr [rsi], 2
0x18002524c  bts     ecx, 8
0x180025250  mov     [rdi], ecx
0x180025252  jmp     short loc_18002525A
0x180025254  mov     r14d, 4ECh
0x18002525a  mov     rcx, [rbp+hKey]; hKey
0x18002525e  test    rcx, rcx
0x180025261  jz      short loc_18002526F
0x180025263  call    cs:__imp_RegCloseKey
0x18002526a  nop     dword ptr [rax+rax+00h]
0x18002526f  mov     eax, r14d
0x180025272  add     rsp, 38h
0x180025276  pop     r14
0x180025278  pop     r12
0x18002527a  pop     rdi
0x18002527b  pop     rsi
0x18002527c  pop     rbx
0x18002527d  pop     rbp
0x18002527e  retn
```
