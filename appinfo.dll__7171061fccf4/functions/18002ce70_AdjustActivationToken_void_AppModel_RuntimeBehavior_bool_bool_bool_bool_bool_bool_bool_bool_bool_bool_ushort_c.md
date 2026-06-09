# AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)

- ea: `0x18002ce70`
- end: `0x18002d2cd`
- name: `?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z`
- size: `1117`
- prototype: `__int64 __fastcall(void *, int, char, unsigned __int8, char, char, char, char, char, char, char, char, wchar_t *, wchar_t *, __int64, __int64, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bc04`
- `0x18002c480`
- `0x18002d2d4`
- `0x18002ed98`
- `0x180035dbc`

## callees

- `0x18000bde0`
- `0x18000c410`
- `0x18000d290`
- `0x18001ce1c`
- `0x18001f774`
- `0x18002ce70`
- `0x180030e20`
- `0x18003bc5c`
- `0x18003bff0`
- `0x18003c030`
- `0x18003c618`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002d128`
- `ntdll!RtlInitUnicodeString` at `0x18002d128`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18002d15b`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18002d15b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002d183`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002d183`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x18002d20f`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x18002d20f`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18002d0c3`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18002d0c3`

## string_xrefs

- `0x18002d119`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall AdjustActivationToken(
        void *a1,
        int a2,
        char a3,
        unsigned __int8 a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        wchar_t *a13,
        wchar_t *a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        _QWORD *a18)
{
  int v21; // ebx
  int v22; // edi
  int RestrictedTokenForAppContainer; // ebx
  int v24; // ecx
  int v25; // ebx
  int v26; // eax
  int v27; // ebx
  int v28; // eax
  int v29; // ecx
  unsigned int v30; // edi
  wchar_t *v31; // rbx
  int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // ebx
  wchar_t *v35; // r14
  const unsigned __int16 *v36; // r8
  HANDLE v38; // rax
  void *NewTokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v42; // [rsp+78h] [rbp-88h]
  wchar_t *Source; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  wchar_t *v46; // [rsp+A0h] [rbp-60h]
  _QWORD *v47; // [rsp+A8h] [rbp-58h]
  _BYTE pSid2[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v49[80]; // [rsp+100h] [rbp+0h] BYREF

  Source = a13;
  v46 = a14;
  v45 = a17;
  v21 = a4;
  v47 = a18;
  TokenHandle = 0;
  if ( !(unsigned __int8)IsPsmAdjustActivationTokenExPresent() )
  {
LABEL_25:
    RestrictedTokenForAppContainer = -1073741637;
    goto LABEL_64;
  }
  *a18 = 0;
  NewTokenHandle = 0;
  if ( a15 )
  {
    if ( a16 )
      goto LABEL_4;
LABEL_9:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
    RestrictedTokenForAppContainer = -1073741776;
LABEL_64:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return (unsigned int)RestrictedTokenForAppContainer;
  }
  if ( a16 )
    goto LABEL_9;
LABEL_4:
  if ( !a2 )
  {
    v22 = (v21 << 9) + 1;
    if ( a3 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &NewTokenHandle,
        0);
      RestrictedTokenForAppContainer = GetRestrictedTokenForAppContainer(a1, &NewTokenHandle);
      if ( RestrictedTokenForAppContainer < 0 )
      {
LABEL_63:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
        goto LABEL_64;
      }
      a1 = NewTokenHandle;
    }
    else
    {
      v22 |= 0x800u;
    }
    v24 = v22 | 0x20000000;
    if ( a15 )
      v24 = v22;
LABEL_35:
    v41 = 0;
    v28 = v24 | 0x2000;
    v42 = 0;
    LODWORD(DestinationString.Buffer) = 0;
    if ( !a7 )
      v28 = v24;
    BYTE4(DestinationString.Buffer) = 1;
    v29 = v28 | 0x40000010;
    if ( !a10 )
      v29 = v28;
    *(_QWORD *)&DestinationString.Length = &v41;
    v30 = v29 | 0x80000;
    if ( !a8 )
      v30 = v29;
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(
      &v41,
      0);
    v31 = Source;
    v32 = QueryApplicationCapabilitiesEx(Source, 0, 0, 0, 0, &v41, &DestinationString.Buffer, 0, 0, 0, 0);
    if ( BYTE4(DestinationString.Buffer) )
      *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 8LL) = LODWORD(DestinationString.Buffer);
    if ( (int)(v32 + 0x80000000) >= 0 && v32 != -2147024444 )
    {
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(
        &v41,
        0x80000000LL);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
      RestrictedTokenForAppContainer = -1073741823;
      goto LABEL_64;
    }
    if ( v42 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"Microsoft.appCategory.chatAgent_8wekyb3d8bbwe");
      memset_0(pSid2, 0, 0x44u);
      memset_0(v49, 0, 0x44u);
      RestrictedTokenForAppContainer = RtlDeriveCapabilitySidsFromName(&DestinationString, v49, pSid2);
      if ( RestrictedTokenForAppContainer < 0 )
      {
LABEL_62:
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(
          &v41,
          v33);
        goto LABEL_63;
      }
      v34 = 0;
      if ( v42 )
      {
        while ( !EqualSid(*(PSID *)(v41 + 8LL * v34), pSid2) )
        {
          if ( ++v34 >= v42 )
            goto LABEL_53;
        }
        v30 |= 0x1000u;
      }
LABEL_53:
      v31 = Source;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl)
      && a11
      && a2 )
    {
      v30 |= 0x200000u;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    v35 = v46;
    RestrictedTokenForAppContainer = PsmAdjustActivationTokenEx2(a1, v30, 1, v31, v46, 0, a16, a15, v45, &TokenHandle);
    AipLogDesktopAppXProcessLogPSMFlags(Source, v35, v30);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::GetImpl'::`2'::impl)
      || RestrictedTokenForAppContainer >= 0
      && (!a11
       || (RestrictedTokenForAppContainer = CiPolicyAdjustToken(TokenHandle, (v30 >> 8) & 1, v36),
           RestrictedTokenForAppContainer >= 0)) )
    {
      if ( !RestrictedTokenForAppContainer )
      {
        v38 = TokenHandle;
        TokenHandle = 0;
        *v47 = v38;
      }
    }
    goto LABEL_62;
  }
  if ( a9 )
  {
    v25 = a15 != 0 ? 1048577 : 537919489;
  }
  else
  {
    if ( a15 || a16 )
      goto LABEL_67;
    v25 = 268435457;
  }
  switch ( a2 )
  {
    case 1:
      v26 = a3 != 0 ? 1024 : 4;
      goto LABEL_21;
    case 2:
      if ( !a3 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(
                                 `wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl'::`2'::impl,
                                 0) )
        {
          v27 = v25 | 0x10100;
          goto LABEL_31;
        }
        v26 = a12 != 0 ? 65568 : 65792;
LABEL_21:
        v27 = v26 | v25;
LABEL_31:
        v24 = v27 | 0x8000;
        if ( !a5 )
          v24 = v27;
        if ( a6 )
          v24 |= 0x20000u;
        goto LABEL_35;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
      goto LABEL_25;
    case 3:
      v27 = v25 | 0x40000;
      goto LABEL_31;
  }
LABEL_67:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18002ce70  push    rbp
0x18002ce72  push    rbx
0x18002ce73  push    rsi
0x18002ce74  push    rdi
0x18002ce75  push    r12
0x18002ce77  push    r13
0x18002ce79  push    r14
0x18002ce7b  push    r15
0x18002ce7d  lea     rbp, [rsp-68h]
0x18002ce82  sub     rsp, 168h
0x18002ce89  mov     rax, cs:__security_cookie
0x18002ce90  xor     rax, rsp
0x18002ce93  mov     [rbp+0A0h+var_50], rax
0x18002ce97  mov     rax, [rbp+0A0h+arg_60]
0x18002ce9e  mov     sil, r8b
0x18002cea1  mov     rdi, [rbp+0A0h+arg_88]
0x18002cea8  mov     r14d, edx
0x18002ceab  mov     r15, [rbp+0A0h+arg_70]
0x18002ceb2  mov     r13, rcx
0x18002ceb5  mov     r12, [rbp+0A0h+arg_78]
0x18002cebc  mov     [rbp+0A0h+Source], rax
0x18002cec0  mov     rax, [rbp+0A0h+arg_68]
0x18002cec7  mov     [rbp+0A0h+var_100], rax
0x18002cecb  mov     rax, [rbp+0A0h+arg_80]
0x18002ced2  mov     [rbp+0A0h+var_108], rax
0x18002ced6  movzx   ebx, r9b
0x18002ceda  mov     [rbp+0A0h+var_F8], rdi
0x18002cede  mov     [rsp+1A0h+TokenHandle], 0
0x18002cee7  call    IsPsmAdjustActivationTokenExPresent
0x18002ceec  xor     edx, edx
0x18002ceee  test    al, al
0x18002cef0  jz      loc_18002CFD2
0x18002cef6  mov     [rdi], rdx
0x18002cef9  mov     [rsp+1A0h+NewTokenHandle], rdx
0x18002cefe  test    r15, r15
0x18002cf01  jz      short loc_18002CF43
0x18002cf03  test    r12, r12
0x18002cf06  jz      short loc_18002CF48
0x18002cf08  test    r14d, r14d
0x18002cf0b  jnz     short loc_18002CF71
0x18002cf0d  mov     edi, ebx
0x18002cf0f  shl     edi, 9
0x18002cf12  inc     edi
0x18002cf14  test    sil, sil
0x18002cf17  jz      short loc_18002CF5C
0x18002cf19  lea     rcx, [rsp+1A0h+NewTokenHandle]
0x18002cf1e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002cf23  lea     rdx, [rsp+1A0h+NewTokenHandle]; NewTokenHandle
0x18002cf28  mov     rcx, r13; ExistingTokenHandle
0x18002cf2b  call    ?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z; GetRestrictedTokenForAppContainer(void *,void * *)
0x18002cf30  xor     edx, edx
0x18002cf32  mov     ebx, eax
0x18002cf34  test    eax, eax
0x18002cf36  js      loc_18002D261
0x18002cf3c  mov     r13, [rsp+1A0h+NewTokenHandle]
0x18002cf41  jmp     short loc_18002CF60
0x18002cf43  test    r12, r12
0x18002cf46  jz      short loc_18002CF08
0x18002cf48  lea     rcx, [rsp+1A0h+NewTokenHandle]
0x18002cf4d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002cf52  mov     ebx, 0C0000030h
0x18002cf57  jmp     loc_18002D26B
0x18002cf5c  bts     edi, 0Bh
0x18002cf60  mov     ecx, edi
0x18002cf62  bts     ecx, 1Dh
0x18002cf66  test    r15, r15
0x18002cf69  cmovnz  ecx, edi
0x18002cf6c  jmp     loc_18002D033
0x18002cf71  cmp     [rbp+0A0h+arg_40], dl
0x18002cf77  jz      short loc_18002CF8F
0x18002cf79  mov     rax, r15
0x18002cf7c  neg     rax
0x18002cf7f  sbb     ebx, ebx
0x18002cf81  and     ebx, 0E0000000h
0x18002cf87  add     ebx, 20100001h
0x18002cf8d  jmp     short loc_18002CFA6
0x18002cf8f  test    r15, r15
0x18002cf92  jnz     loc_18002D294
0x18002cf98  test    r12, r12
0x18002cf9b  jnz     loc_18002D294
0x18002cfa1  mov     ebx, 10000001h
0x18002cfa6  cmp     r14d, 1
0x18002cfaa  jnz     short loc_18002CFBD
0x18002cfac  neg     sil
0x18002cfaf  sbb     eax, eax
0x18002cfb1  and     eax, 3FCh
0x18002cfb6  add     eax, 4
0x18002cfb9  or      ebx, eax
0x18002cfbb  jmp     short loc_18002D018
0x18002cfbd  cmp     r14d, 2
0x18002cfc1  jnz     short loc_18002D00A
0x18002cfc3  test    sil, sil
0x18002cfc6  jz      short loc_18002CFDC
0x18002cfc8  lea     rcx, [rsp+1A0h+NewTokenHandle]
0x18002cfcd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002cfd2  mov     ebx, 0C00000BBh
0x18002cfd7  jmp     loc_18002D26B
0x18002cfdc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte> `wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl(void)'::`2'::impl
0x18002cfe3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(void)
0x18002cfe8  xor     edx, edx
0x18002cfea  test    al, al
0x18002cfec  jz      short loc_18002D002
0x18002cfee  neg     [rbp+0A0h+arg_58]
0x18002cff4  sbb     eax, eax
0x18002cff6  and     eax, 0FFFFFF20h
0x18002cffb  add     eax, 10100h
0x18002d000  jmp     short loc_18002CFB9
0x18002d002  or      ebx, 10100h
0x18002d008  jmp     short loc_18002D018
0x18002d00a  cmp     r14d, 3
0x18002d00e  jnz     loc_18002D294
0x18002d014  bts     ebx, 12h
0x18002d018  mov     ecx, ebx
0x18002d01a  bts     ecx, 0Fh
0x18002d01e  cmp     [rbp+0A0h+arg_20], dl
0x18002d024  cmovz   ecx, ebx
0x18002d027  cmp     [rbp+0A0h+arg_28], dl
0x18002d02d  jz      short loc_18002D033
0x18002d02f  bts     ecx, 11h
0x18002d033  mov     eax, ecx
0x18002d035  mov     [rsp+1A0h+var_130], rdx
0x18002d03a  bts     eax, 0Dh
0x18002d03e  mov     [rsp+1A0h+var_128], rdx
0x18002d043  cmp     [rbp+0A0h+arg_30], dl
0x18002d049  mov     dword ptr [rbp+0A0h+DestinationString.Buffer], edx
0x18002d04c  cmovz   eax, ecx
0x18002d04f  mov     byte ptr [rbp+0A0h+DestinationString.Buffer+4], 1
0x18002d053  mov     ecx, eax
0x18002d055  or      ecx, 40000010h
0x18002d05b  cmp     [rbp+0A0h+arg_48], dl
0x18002d061  cmovz   ecx, eax
0x18002d064  lea     rax, [rsp+1A0h+var_130]
0x18002d069  mov     edi, ecx
0x18002d06b  mov     qword ptr [rbp+0A0h+DestinationString.Length], rax
0x18002d06f  bts     edi, 13h
0x18002d073  cmp     [rbp+0A0h+arg_38], dl
0x18002d079  cmovz   edi, ecx
0x18002d07c  lea     rcx, [rsp+1A0h+var_130]
0x18002d081  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18002d086  mov     rbx, [rbp+0A0h+Source]
0x18002d08a  lea     rax, [rbp+0A0h+DestinationString.Buffer]
0x18002d08e  xor     esi, esi
0x18002d090  xor     r9d, r9d
0x18002d093  mov     [rsp+1A0h+var_150], rsi
0x18002d098  xor     r8d, r8d
0x18002d09b  mov     [rsp+1A0h+var_158], rsi
0x18002d0a0  xor     edx, edx
0x18002d0a2  mov     [rsp+1A0h+var_160], rsi
0x18002d0a7  mov     rcx, rbx
0x18002d0aa  mov     [rsp+1A0h+var_168], rsi
0x18002d0af  mov     [rsp+1A0h+var_170], rax
0x18002d0b4  lea     rax, [rsp+1A0h+var_130]
0x18002d0b9  mov     [rsp+1A0h+var_178], rax
0x18002d0be  mov     [rsp+1A0h+var_180], rsi
0x18002d0c3  call    cs:__imp_QueryApplicationCapabilitiesEx
0x18002d0c9  cmp     byte ptr [rbp+0A0h+DestinationString.Buffer+4], sil
0x18002d0cd  jz      short loc_18002D0DA
0x18002d0cf  mov     rcx, qword ptr [rbp+0A0h+DestinationString.Length]
0x18002d0d3  mov     edx, dword ptr [rbp+0A0h+DestinationString.Buffer]
0x18002d0d6  mov     [rcx+8], rdx
0x18002d0da  mov     edx, 80000000h
0x18002d0df  lea     ecx, [rax+rdx]
0x18002d0e2  test    edx, ecx
0x18002d0e4  jnz     short loc_18002D10B
0x18002d0e6  cmp     eax, 800701C4h
0x18002d0eb  jz      short loc_18002D10B
0x18002d0ed  lea     rcx, [rsp+1A0h+var_130]
0x18002d0f2  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18002d0f7  lea     rcx, [rsp+1A0h+NewTokenHandle]
0x18002d0fc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002d101  mov     ebx, 0C0000001h
0x18002d106  jmp     loc_18002D26B
0x18002d10b  cmp     [rsp+1A0h+var_128], rsi
0x18002d110  jbe     loc_18002D1A2
0x18002d116  xorps   xmm0, xmm0
0x18002d119  lea     rdx, SourceString; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x18002d120  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x18002d124  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x18002d128  call    cs:__imp_RtlInitUnicodeString
0x18002d12e  mov     ebx, 44h ; 'D'
0x18002d133  lea     rcx, [rbp+0A0h+pSid2]; void *
0x18002d137  mov     r8d, ebx; Size
0x18002d13a  xor     edx, edx; Val
0x18002d13c  call    memset_0
0x18002d141  mov     r8d, ebx; Size
0x18002d144  lea     rcx, [rbp+0A0h+var_A0]; void *
0x18002d148  xor     edx, edx; Val
0x18002d14a  call    memset_0
0x18002d14f  lea     r8, [rbp+0A0h+pSid2]
0x18002d153  lea     rdx, [rbp+0A0h+var_A0]
0x18002d157  lea     rcx, [rbp+0A0h+DestinationString]
0x18002d15b  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18002d161  mov     ebx, eax
0x18002d163  test    eax, eax
0x18002d165  js      loc_18002D257
0x18002d16b  mov     ebx, esi
0x18002d16d  cmp     [rsp+1A0h+var_128], rsi
0x18002d172  jbe     short loc_18002D19E
0x18002d174  mov     rcx, [rsp+1A0h+var_130]
0x18002d179  lea     rdx, [rbp+0A0h+pSid2]; pSid2
0x18002d17d  mov     eax, ebx
0x18002d17f  mov     rcx, [rcx+rax*8]; pSid1
0x18002d183  call    cs:__imp_EqualSid
0x18002d189  test    eax, eax
0x18002d18b  jnz     short loc_18002D19A
0x18002d18d  inc     ebx
0x18002d18f  mov     eax, ebx
0x18002d191  cmp     rax, [rsp+1A0h+var_128]
0x18002d196  jb      short loc_18002D174
0x18002d198  jmp     short loc_18002D19E
0x18002d19a  bts     edi, 0Ch
0x18002d19e  mov     rbx, [rbp+0A0h+Source]
0x18002d1a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x18002d1a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x18002d1ae  mov     sil, [rbp+0A0h+arg_50]
0x18002d1b5  test    al, al
0x18002d1b7  jz      short loc_18002D1C7
0x18002d1b9  test    sil, sil
0x18002d1bc  jz      short loc_18002D1C7
0x18002d1be  test    r14d, r14d
0x18002d1c1  jz      short loc_18002D1C7
0x18002d1c3  bts     edi, 15h
0x18002d1c7  xor     edx, edx
0x18002d1c9  lea     rcx, [rsp+1A0h+TokenHandle]
0x18002d1ce  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002d1d3  mov     r14, [rbp+0A0h+var_100]
0x18002d1d7  lea     rax, [rsp+1A0h+TokenHandle]
0x18002d1dc  mov     [rsp+1A0h+var_158], rax
0x18002d1e1  mov     r9, rbx
0x18002d1e4  mov     rax, [rbp+0A0h+var_108]
0x18002d1e8  mov     r8d, 1
0x18002d1ee  mov     [rsp+1A0h+var_160], rax
0x18002d1f3  mov     edx, edi
0x18002d1f5  mov     [rsp+1A0h+var_168], r15
0x18002d1fa  mov     rcx, r13
0x18002d1fd  mov     [rsp+1A0h+var_170], r12
0x18002d202  mov     dword ptr [rsp+1A0h+var_178], 0
0x18002d20a  mov     [rsp+1A0h+var_180], r14
0x18002d20f  call    cs:__imp_PsmAdjustActivationTokenEx2
0x18002d215  mov     rcx, [rbp+0A0h+Source]; Source
0x18002d219  mov     r8d, edi; unsigned int
0x18002d21c  mov     rdx, r14; wchar_t *
0x18002d21f  mov     ebx, eax
0x18002d221  call    ?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z; AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)
0x18002d226  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchCiClaim@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchCiClaim@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchCiClaim> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::GetImpl(void)'::`2'::impl
0x18002d22d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchCiClaim@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchCiClaim>::__private_IsEnabled(void)
0x18002d232  test    al, al
0x18002d234  jz      short loc_18002D279
0x18002d236  test    ebx, ebx
0x18002d238  js      short loc_18002D257
0x18002d23a  test    sil, sil
0x18002d23d  jz      short loc_18002D279
0x18002d23f  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x18002d244  shr     edi, 8
0x18002d247  and     edi, 1
0x18002d24a  mov     edx, edi; unsigned int
0x18002d24c  call    ?CiPolicyAdjustToken@@YAJPEAXKPEBG@Z; CiPolicyAdjustToken(void *,ulong,ushort const *)
0x18002d251  mov     ebx, eax
0x18002d253  test    eax, eax
0x18002d255  jns     short loc_18002D279
0x18002d257  lea     rcx, [rsp+1A0h+var_130]
0x18002d25c  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18002d261  lea     rcx, [rsp+1A0h+NewTokenHandle]
0x18002d266  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002d26b  lea     rcx, [rsp+1A0h+TokenHandle]
0x18002d270  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002d275  mov     eax, ebx
0x18002d277  jmp     short loc_18002D2AD
0x18002d279  test    ebx, ebx
0x18002d27b  jnz     short loc_18002D257
0x18002d27d  mov     rax, [rsp+1A0h+TokenHandle]
0x18002d282  mov     rcx, [rbp+0A0h+var_F8]
0x18002d286  mov     [rsp+1A0h+TokenHandle], 0
0x18002d28f  mov     [rcx], rax
0x18002d292  jmp     short loc_18002D257
0x18002d294  lea     rcx, [rsp+1A0h+NewTokenHandle]
0x18002d299  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002d29e  lea     rcx, [rsp+1A0h+TokenHandle]
0x18002d2a3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002d2a8  mov     eax, 0C000000Dh
0x18002d2ad  mov     rcx, [rbp+0A0h+var_50]
0x18002d2b1  xor     rcx, rsp; StackCookie
0x18002d2b4  call    __security_check_cookie
0x18002d2b9  add     rsp, 168h
0x18002d2c0  pop     r15
0x18002d2c2  pop     r14
0x18002d2c4  pop     r13
0x18002d2c6  pop     r12
0x18002d2c8  pop     rdi
0x18002d2c9  pop     rsi
0x18002d2ca  pop     rbx
0x18002d2cb  pop     rbp
0x18002d2cc  retn
```
