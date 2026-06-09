# AiCheckLUA(ulong,ulong *,ELEVATION_REASON,void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,char const *,void * *)

- ea: `0x18003f14c`
- end: `0x18003f356`
- name: `?AiCheckLUA@@YAKKPEAKW4ELEVATION_REASON@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKPEBDPEAPEAX@Z`
- size: `522`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, int, void *, __int64, __int64, __int64, int TokenInformation, int, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18002ed98`
- `0x18003d070`
- `0x180040d64`

## callees

- `0x180010dd4`
- `0x180011dd8`
- `0x180017528`
- `0x180017680`
- `0x180026630`
- `0x1800290b4`
- `0x18003ef28`
- `0x18003f14c`
- `0x1800461e8`

## import_xrefs

- `ntdll!NtClose` at `0x18003f33f`
- `ntdll!NtClose` at `0x18003f33f`
- `ntdll!RtlNtStatusToDosError` at `0x18003f328`
- `ntdll!RtlNtStatusToDosError` at `0x18003f328`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003f195`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003f2cc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003f195`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003f2cc`
- `ntdll!NtSetInformationToken` at `0x18003f31c`
- `ntdll!NtSetInformationToken` at `0x18003f31c`

## pseudocode

```c
__int64 __fastcall AiCheckLUA(
        unsigned int a1,
        unsigned int *a2,
        int a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int TokenInformation,
        int a9,
        __int64 a10,
        _QWORD *a11)
{
  _QWORD *v11; // r14
  NTSTATUS v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rdx
  HANDLE v22; // rsi
  char IsEnabled; // al
  __int64 v24; // rcx
  NTSTATUS v25; // eax
  ULONG v26; // eax
  int v27; // eax
  int v29; // [rsp+50h] [rbp-10h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-8h] BYREF

  v11 = a11;
  v29 = 0;
  TokenHandle = 0;
  *a11 = 0;
  v16 = AipRequireElevationPrompt(a1, a2, a4);
  if ( v16 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v16);
  v18 = *a2 & 8;
  if ( (*(_BYTE *)a2 & 0x10) != 0 )
  {
    v17 = 0;
    if ( !v18 )
      return v17;
  }
  else if ( !v18 )
  {
LABEL_8:
    v17 = AipCheckSignatureRequiredPolicy(&v29);
    if ( v17 )
      return v17;
    if ( v29 )
      *a2 = *a2 & 0xFFF7FFF7 | 8;
    goto LABEL_11;
  }
  if ( (*a2 & 0x80000) != 0 )
    goto LABEL_8;
LABEL_11:
  v17 = AipCheckAutomaticAdminPolicy(&v29);
  if ( v17 )
    return v17;
  if ( v29 )
    *a2 |= 0x4000000u;
  if ( (unsigned int)LUAIsShadowAdminEnabled(v19) )
    *a2 |= 0x8000000u;
  v20 = AiLaunchConsentUI(a4, a5, a6, a7, TokenInformation, *a2, a3, a9, a10, &TokenHandle);
  v22 = TokenHandle;
  v17 = v20;
  if ( v20 )
    goto LABEL_38;
  if ( !TokenHandle )
  {
    if ( (*(_BYTE *)a2 & 0x10) == 0 )
      return 1223;
    return v17;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                v21);
  v24 = *a2 & 0x2000000;
  if ( IsEnabled )
  {
    if ( (_DWORD)v24 || (unsigned int)LUAIsShadowAdminEnabled(v24) && (*(_BYTE *)a2 & 4) != 0 && !a1 )
      goto LABEL_25;
  }
  else if ( (_DWORD)v24 )
  {
LABEL_25:
    *v11 = 0;
    goto LABEL_38;
  }
  v25 = AiCheckForElevatedUser(v22, &v29);
  if ( v25 < 0 )
    goto LABEL_28;
  if ( !v29 )
    goto LABEL_31;
  if ( (*a2 & 0x240) == 0x240 )
    goto LABEL_35;
  v25 = AiCheckForAdminUser(v22, 1, &v29);
  if ( v25 < 0 )
  {
LABEL_28:
    v26 = RtlNtStatusToDosErrorNoTeb(v25);
LABEL_29:
    v17 = v26;
    goto LABEL_38;
  }
  if ( v29 )
  {
LABEL_35:
    v27 = NtSetInformationToken(v22, TokenSessionId, &TokenInformation, 4u);
    if ( v27 < 0 )
    {
      v26 = RtlNtStatusToDosError(v27);
      goto LABEL_29;
    }
    *v11 = v22;
    v22 = 0;
    v17 = 0;
  }
  else
  {
LABEL_31:
    v17 = 740;
  }
LABEL_38:
  if ( v22 )
    NtClose(v22);
  return v17;
}

```

## disassembly

```asm
0x18003f14c  push    rbp
0x18003f14e  push    rbx
0x18003f14f  push    rsi
0x18003f150  push    rdi
0x18003f151  push    r12
0x18003f153  push    r14
0x18003f155  push    r15
0x18003f157  mov     rbp, rsp
0x18003f15a  sub     rsp, 60h
0x18003f15e  mov     r14, [rbp+arg_50]
0x18003f165  mov     r12d, r8d
0x18003f168  mov     r8, r9; void *
0x18003f16b  mov     [rbp+var_10], 0
0x18003f172  mov     rsi, r9
0x18003f175  mov     [rbp+TokenHandle], 0
0x18003f17d  mov     rdi, rdx
0x18003f180  mov     r15d, ecx
0x18003f183  mov     qword ptr [r14], 0
0x18003f18a  call    ?AipRequireElevationPrompt@@YAJKPEAKPEAX@Z; AipRequireElevationPrompt(ulong,ulong *,void *)
0x18003f18f  test    eax, eax
0x18003f191  jns     short loc_18003F1A2
0x18003f193  mov     ecx, eax; Status
0x18003f195  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003f19b  mov     ebx, eax
0x18003f19d  jmp     loc_18003F345
0x18003f1a2  mov     eax, [rdi]
0x18003f1a4  and     eax, 8
0x18003f1a7  test    byte ptr [rdi], 10h
0x18003f1aa  jz      short loc_18003F1B8
0x18003f1ac  xor     ebx, ebx
0x18003f1ae  test    eax, eax
0x18003f1b0  jz      loc_18003F345
0x18003f1b6  jmp     short loc_18003F1BC
0x18003f1b8  test    eax, eax
0x18003f1ba  jz      short loc_18003F1C4
0x18003f1bc  test    dword ptr [rdi], 80000h
0x18003f1c2  jz      short loc_18003F1E7
0x18003f1c4  lea     rcx, [rbp+var_10]; int *
0x18003f1c8  call    ?AipCheckSignatureRequiredPolicy@@YAKPEAH@Z; AipCheckSignatureRequiredPolicy(int *)
0x18003f1cd  mov     ebx, eax
0x18003f1cf  test    eax, eax
0x18003f1d1  jnz     loc_18003F345
0x18003f1d7  cmp     [rbp+var_10], eax
0x18003f1da  jz      short loc_18003F1E7
0x18003f1dc  mov     eax, [rdi]
0x18003f1de  btr     eax, 13h
0x18003f1e2  or      eax, 8
0x18003f1e5  mov     [rdi], eax
0x18003f1e7  lea     rcx, [rbp+var_10]; int *
0x18003f1eb  call    ?AipCheckAutomaticAdminPolicy@@YAKPEAH@Z; AipCheckAutomaticAdminPolicy(int *)
0x18003f1f0  mov     ebx, eax
0x18003f1f2  test    eax, eax
0x18003f1f4  jnz     loc_18003F345
0x18003f1fa  cmp     [rbp+var_10], eax
0x18003f1fd  jz      short loc_18003F203
0x18003f1ff  bts     dword ptr [rdi], 1Ah
0x18003f203  call    LUAIsShadowAdminEnabled
0x18003f208  test    eax, eax
0x18003f20a  jz      short loc_18003F210
0x18003f20c  bts     dword ptr [rdi], 1Bh
0x18003f210  mov     r9, [rbp+arg_30]
0x18003f214  lea     rax, [rbp+TokenHandle]
0x18003f218  mov     r8, [rbp+arg_28]
0x18003f21c  mov     rcx, rsi
0x18003f21f  mov     rdx, [rbp+arg_20]
0x18003f223  mov     [rsp+60h+var_18], rax
0x18003f228  mov     rax, [rbp+arg_48]
0x18003f22f  mov     [rsp+60h+var_20], rax
0x18003f234  mov     eax, [rbp+arg_40]
0x18003f23a  mov     [rsp+60h+var_28], eax
0x18003f23e  mov     eax, [rdi]
0x18003f240  mov     [rsp+60h+var_30], r12d
0x18003f245  mov     [rsp+60h+var_38], eax
0x18003f249  mov     eax, [rbp+TokenInformation]
0x18003f24c  mov     [rsp+60h+var_40], eax
0x18003f250  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18003f255  mov     rsi, [rbp+TokenHandle]
0x18003f259  mov     ebx, eax
0x18003f25b  test    eax, eax
0x18003f25d  jnz     loc_18003F337
0x18003f263  test    rsi, rsi
0x18003f266  jnz     short loc_18003F27B
0x18003f268  test    byte ptr [rdi], 10h
0x18003f26b  jnz     loc_18003F345
0x18003f271  mov     ebx, 4C7h
0x18003f276  jmp     loc_18003F345
0x18003f27b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003f282  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003f287  mov     ecx, [rdi]
0x18003f289  and     ecx, 2000000h
0x18003f28f  test    al, al
0x18003f291  jz      short loc_18003F2B6
0x18003f293  test    ecx, ecx
0x18003f295  jnz     short loc_18003F2AA
0x18003f297  call    LUAIsShadowAdminEnabled
0x18003f29c  test    eax, eax
0x18003f29e  jz      short loc_18003F2BA
0x18003f2a0  test    byte ptr [rdi], 4
0x18003f2a3  jz      short loc_18003F2BA
0x18003f2a5  test    r15d, r15d
0x18003f2a8  jnz     short loc_18003F2BA
0x18003f2aa  mov     qword ptr [r14], 0
0x18003f2b1  jmp     loc_18003F337
0x18003f2b6  test    ecx, ecx
0x18003f2b8  jnz     short loc_18003F2AA
0x18003f2ba  lea     rdx, [rbp+var_10]; int *
0x18003f2be  mov     rcx, rsi; void *
0x18003f2c1  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003f2c6  test    eax, eax
0x18003f2c8  jns     short loc_18003F2D6
0x18003f2ca  mov     ecx, eax; Status
0x18003f2cc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003f2d2  mov     ebx, eax
0x18003f2d4  jmp     short loc_18003F337
0x18003f2d6  cmp     [rbp+var_10], 0
0x18003f2da  jnz     short loc_18003F2E3
0x18003f2dc  mov     ebx, 2E4h
0x18003f2e1  jmp     short loc_18003F337
0x18003f2e3  mov     eax, [rdi]
0x18003f2e5  mov     ecx, 240h
0x18003f2ea  and     eax, ecx
0x18003f2ec  cmp     eax, ecx
0x18003f2ee  jz      short loc_18003F30B
0x18003f2f0  lea     r8, [rbp+var_10]; int *
0x18003f2f4  mov     edx, 1; int
0x18003f2f9  mov     rcx, rsi; Handle
0x18003f2fc  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003f301  test    eax, eax
0x18003f303  js      short loc_18003F2CA
0x18003f305  cmp     [rbp+var_10], 0
0x18003f309  jz      short loc_18003F2DC
0x18003f30b  mov     r9d, 4; TokenInformationLength
0x18003f311  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003f315  mov     rcx, rsi; TokenHandle
0x18003f318  lea     edx, [r9+8]; TokenInformationClass
0x18003f31c  call    cs:__imp_NtSetInformationToken
0x18003f322  test    eax, eax
0x18003f324  jns     short loc_18003F330
0x18003f326  mov     ecx, eax; Status
0x18003f328  call    cs:__imp_RtlNtStatusToDosError
0x18003f32e  jmp     short loc_18003F2D2
0x18003f330  mov     [r14], rsi
0x18003f333  xor     esi, esi
0x18003f335  xor     ebx, ebx
0x18003f337  test    rsi, rsi
0x18003f33a  jz      short loc_18003F345
0x18003f33c  mov     rcx, rsi; Handle
0x18003f33f  call    cs:__imp_NtClose
0x18003f345  mov     eax, ebx
0x18003f347  add     rsp, 60h
0x18003f34b  pop     r15
0x18003f34d  pop     r14
0x18003f34f  pop     r12
0x18003f351  pop     rdi
0x18003f352  pop     rsi
0x18003f353  pop     rbx
0x18003f354  pop     rbp
0x18003f355  retn
```
