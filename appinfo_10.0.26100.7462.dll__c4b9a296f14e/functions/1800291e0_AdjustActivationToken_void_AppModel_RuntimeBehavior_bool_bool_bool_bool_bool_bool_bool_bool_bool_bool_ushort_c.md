# AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)

- ea: `0x1800291e0`
- end: `0x1800296b5`
- name: `?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z`
- size: `1237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027534`
- `0x180027c34`
- `0x1800296bc`
- `0x18002a2a8`
- `0x180032ad0`

## callees

- `0x18000c790`
- `0x18000de30`
- `0x18000f9e0`
- `0x18001ad40`
- `0x18001c2bc`
- `0x1800291e0`
- `0x180039858`
- `0x180039ba4`
- `0x180039d88`
- `0x18003a170`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002956f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002956f`
- `ntdll!RtlInitUnicodeString` at `0x1800294fd`
- `ntdll!RtlInitUnicodeString` at `0x1800294fd`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180029536`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180029536`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x180029606`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x180029606`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180029491`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x180029491`
- `api-ms-win-appmodel-lifecyclepolicy-l1-1-0!AppModelQueryLifecyclePolicy` at `0x180029337`
- `api-ms-win-appmodel-lifecyclepolicy-l1-1-0!AppModelQueryLifecyclePolicy` at `0x180029337`

## string_xrefs

- `0x1800294ee`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

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
        unsigned __int16 *a13,
        unsigned __int16 *a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        _QWORD *a18)
{
  int v21; // ebx
  int v22; // edi
  unsigned int v23; // esi
  int RestrictedTokenForAppContainer; // ebx
  int v25; // ecx
  int v26; // ebx
  int v27; // ebx
  int v28; // eax
  int v29; // ecx
  int v30; // edi
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rax
  unsigned __int16 *v34; // rsi
  unsigned int v35; // edi
  __int64 v36; // rcx
  void *NewTokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v42; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  _QWORD *v47; // [rsp+B0h] [rbp-50h]
  _BYTE pSid2[80]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[80]; // [rsp+110h] [rbp+10h] BYREF

  v39 = 0;
  v45 = a13;
  v44 = a14;
  v46 = a17;
  v21 = a4;
  v47 = a18;
  if ( !(unsigned __int8)IsPsmAdjustActivationTokenExPresent() )
    goto LABEL_27;
  *a18 = 0;
  NewTokenHandle = 0;
  if ( a15 )
  {
    if ( a16 )
      goto LABEL_4;
LABEL_9:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
    RestrictedTokenForAppContainer = -1073741776;
    goto LABEL_70;
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
      v23 = 0;
      RestrictedTokenForAppContainer = GetRestrictedTokenForAppContainer(a1, &NewTokenHandle);
      if ( RestrictedTokenForAppContainer < 0 )
      {
LABEL_7:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
LABEL_70:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
        return (unsigned int)RestrictedTokenForAppContainer;
      }
      a1 = NewTokenHandle;
    }
    else
    {
      v22 |= 0x800u;
      v23 = 0;
    }
    v25 = v22 | 0x20000000;
    if ( a15 )
      v25 = v22;
    goto LABEL_39;
  }
  if ( a9 )
  {
    v26 = a15 != 0 ? 1048577 : 537919489;
  }
  else
  {
    if ( a15 || a16 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
      return 3221225485LL;
    }
    v40 = 0;
    RestrictedTokenForAppContainer = AppModelQueryLifecyclePolicy(v44, &v40);
    if ( RestrictedTokenForAppContainer < 0 )
      goto LABEL_7;
    v26 = 268435457;
    if ( v40 == 65537 )
      v26 = 536887297;
  }
  if ( a2 != 1 )
  {
    if ( a2 != 2 )
    {
      if ( a2 != 3 )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
        RestrictedTokenForAppContainer = -1073741811;
        goto LABEL_70;
      }
      v27 = v26 | 0x40000;
      goto LABEL_34;
    }
    if ( !a3 )
    {
      v23 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl'::`2'::impl)
        && a12 )
      {
        v27 = v26 | 0x10020;
      }
      else
      {
        v27 = v26 | 0x10100;
      }
      goto LABEL_35;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
LABEL_27:
    RestrictedTokenForAppContainer = -1073741637;
    goto LABEL_70;
  }
  v27 = (a3 != 0 ? 1024 : 4) | v26;
LABEL_34:
  v23 = 0;
LABEL_35:
  v25 = v27 | 0x8000;
  if ( !a5 )
    v25 = v27;
  if ( a6 )
    v25 |= 0x20000u;
LABEL_39:
  v28 = v25 | 0x2000;
  if ( !a7 )
    v28 = v25;
  v29 = v28 | 0x40000010;
  if ( !a10 )
    v29 = v28;
  v30 = v29 | 0x80000;
  if ( !a8 )
    v30 = v29;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::GetImpl'::`2'::impl) )
  {
    v41 = 0;
    *(_QWORD *)&DestinationString.Length = &v41;
    v42 = 0;
    LODWORD(DestinationString.Buffer) = 0;
    BYTE4(DestinationString.Buffer) = 1;
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v41);
    v31 = QueryApplicationCapabilitiesEx(v45, 0, 0, 0, 0, &v41, &DestinationString.Buffer, 0, 0, 0, 0);
    if ( BYTE4(DestinationString.Buffer) )
      *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 8LL) = LODWORD(DestinationString.Buffer);
    if ( (int)(v31 + 0x80000000) >= 0 && v31 != -2147024444 )
    {
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v41);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
      RestrictedTokenForAppContainer = -1073741823;
      goto LABEL_70;
    }
    v32 = v30;
    if ( v42 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"Microsoft.appCategory.chatAgent_8wekyb3d8bbwe");
      memset_0(pSid2, 0, 0x44u);
      memset_0(v49, 0, 0x44u);
      RestrictedTokenForAppContainer = RtlDeriveCapabilitySidsFromName(&DestinationString, v49, pSid2);
      if ( RestrictedTokenForAppContainer < 0 )
      {
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v41);
        goto LABEL_7;
      }
      v32 = v30;
      if ( v42 )
      {
        v33 = 0;
        while ( !EqualSid(*(PSID *)(v41 + 8 * v33), pSid2) )
        {
          v33 = ++v23;
          if ( v23 >= v42 )
            goto LABEL_60;
        }
        v32 = v30 | 0x1000;
      }
    }
LABEL_60:
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v41);
  }
  else
  {
    v32 = v30;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl)
    && a11
    && a2 )
  {
    v32 |= 0x200000u;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v39,
    0);
  v34 = v44;
  v35 = PsmAdjustActivationTokenEx2(a1, v32, 1, v45, v44, 0, a16, a15, v46, &v39);
  AipLogDesktopAppXProcessLogPSMFlags(v45, v34, v32);
  if ( !v35 )
  {
    v36 = v39;
    v39 = 0;
    *v47 = v36;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
  return v35;
}

```

## disassembly

```asm
0x1800291e0  mov     [rsp-8+arg_8], rbx
0x1800291e5  mov     [rsp-8+arg_10], rsi
0x1800291ea  mov     [rsp-8+arg_18], rdi
0x1800291ef  push    rbp
0x1800291f0  push    r12
0x1800291f2  push    r13
0x1800291f4  push    r14
0x1800291f6  push    r15
0x1800291f8  lea     rbp, [rsp-70h]
0x1800291fd  sub     rsp, 170h
0x180029204  mov     rax, cs:__security_cookie
0x18002920b  xor     rax, rsp
0x18002920e  mov     [rbp+90h+var_30], rax
0x180029212  mov     rax, [rbp+90h+arg_60]
0x180029219  mov     sil, r8b
0x18002921c  mov     rdi, [rbp+90h+arg_88]
0x180029223  mov     r14d, edx
0x180029226  mov     r15, [rbp+90h+arg_70]
0x18002922d  mov     r13, rcx
0x180029230  mov     r12, [rbp+90h+arg_78]
0x180029237  and     [rsp+190h+var_128], 0
0x18002923d  mov     [rbp+90h+var_F0], rax
0x180029241  mov     rax, [rbp+90h+arg_68]
0x180029248  mov     [rbp+90h+var_F8], rax
0x18002924c  mov     rax, [rbp+90h+arg_80]
0x180029253  mov     [rbp+90h+var_E8], rax
0x180029257  movzx   ebx, r9b
0x18002925b  mov     [rbp+90h+var_E0], rdi
0x18002925f  call    IsPsmAdjustActivationTokenExPresent
0x180029264  test    al, al
0x180029266  jz      loc_18002938E
0x18002926c  and     qword ptr [rdi], 0
0x180029270  and     [rsp+190h+NewTokenHandle], 0
0x180029276  test    r15, r15
0x180029279  jz      short loc_1800292C1
0x18002927b  test    r12, r12
0x18002927e  jz      short loc_1800292C6
0x180029280  test    r14d, r14d
0x180029283  jnz     short loc_1800292F8
0x180029285  mov     edi, ebx
0x180029287  shl     edi, 9
0x18002928a  inc     edi
0x18002928c  test    sil, sil
0x18002928f  jz      short loc_1800292E1
0x180029291  xor     edx, edx
0x180029293  lea     rcx, [rsp+190h+NewTokenHandle]
0x180029298  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002929d  lea     rdx, [rsp+190h+NewTokenHandle]; NewTokenHandle
0x1800292a2  mov     rcx, r13; ExistingTokenHandle
0x1800292a5  call    ?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z; GetRestrictedTokenForAppContainer(void *,void * *)
0x1800292aa  xor     esi, esi
0x1800292ac  mov     ebx, eax
0x1800292ae  test    eax, eax
0x1800292b0  jns     short loc_1800292DA
0x1800292b2  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800292b7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800292bc  jmp     loc_180029660
0x1800292c1  test    r12, r12
0x1800292c4  jz      short loc_180029280
0x1800292c6  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800292cb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800292d0  mov     ebx, 0C0000030h
0x1800292d5  jmp     loc_180029660
0x1800292da  mov     r13, [rsp+190h+NewTokenHandle]
0x1800292df  jmp     short loc_1800292E7
0x1800292e1  bts     edi, 0Bh
0x1800292e5  xor     esi, esi
0x1800292e7  mov     ecx, edi
0x1800292e9  bts     ecx, 1Dh
0x1800292ed  test    r15, r15
0x1800292f0  cmovnz  ecx, edi
0x1800292f3  jmp     loc_1800293F0
0x1800292f8  cmp     [rbp+90h+arg_40], 0
0x1800292ff  jz      short loc_180029317
0x180029301  mov     rax, r15
0x180029304  neg     rax
0x180029307  sbb     ebx, ebx
0x180029309  and     ebx, 0E0000000h
0x18002930f  add     ebx, 20100001h
0x180029315  jmp     short loc_180029362
0x180029317  test    r15, r15
0x18002931a  jnz     loc_18002966E
0x180029320  test    r12, r12
0x180029323  jnz     loc_18002966E
0x180029329  mov     rcx, [rbp+90h+var_F8]
0x18002932d  lea     rdx, [rsp+190h+var_120]
0x180029332  and     [rsp+190h+var_120], r12d
0x180029337  call    cs:__imp_AppModelQueryLifecyclePolicy
0x18002933e  nop     dword ptr [rax+rax+00h]
0x180029343  mov     ebx, eax
0x180029345  test    eax, eax
0x180029347  js      loc_1800292B2
0x18002934d  cmp     [rsp+190h+var_120], 10001h
0x180029355  mov     ebx, 10000001h
0x18002935a  mov     eax, 20004001h
0x18002935f  cmovz   ebx, eax
0x180029362  cmp     r14d, 1
0x180029366  jnz     short loc_180029379
0x180029368  neg     sil
0x18002936b  sbb     eax, eax
0x18002936d  and     eax, 3FCh
0x180029372  add     eax, 4
0x180029375  or      ebx, eax
0x180029377  jmp     short loc_1800293D1
0x180029379  cmp     r14d, 2
0x18002937d  jnz     short loc_1800293C3
0x18002937f  test    sil, sil
0x180029382  jz      short loc_180029398
0x180029384  lea     rcx, [rsp+190h+NewTokenHandle]
0x180029389  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002938e  mov     ebx, 0C00000BBh
0x180029393  jmp     loc_180029660
0x180029398  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte> `wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl(void)'::`2'::impl
0x18002939f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(void)
0x1800293a4  xor     esi, esi
0x1800293a6  test    al, al
0x1800293a8  jz      short loc_1800293BB
0x1800293aa  cmp     [rbp+90h+arg_58], sil
0x1800293b1  jz      short loc_1800293BB
0x1800293b3  or      ebx, 10020h
0x1800293b9  jmp     short loc_1800293D3
0x1800293bb  or      ebx, 10100h
0x1800293c1  jmp     short loc_1800293D3
0x1800293c3  cmp     r14d, 3
0x1800293c7  jnz     loc_180029651
0x1800293cd  bts     ebx, 12h
0x1800293d1  xor     esi, esi
0x1800293d3  mov     ecx, ebx
0x1800293d5  bts     ecx, 0Fh
0x1800293d9  cmp     [rbp+90h+arg_20], sil
0x1800293e0  cmovz   ecx, ebx
0x1800293e3  cmp     [rbp+90h+arg_28], sil
0x1800293ea  jz      short loc_1800293F0
0x1800293ec  bts     ecx, 11h
0x1800293f0  mov     eax, ecx
0x1800293f2  bts     eax, 0Dh
0x1800293f6  cmp     [rbp+90h+arg_30], sil
0x1800293fd  cmovz   eax, ecx
0x180029400  mov     ecx, eax
0x180029402  or      ecx, 40000010h
0x180029408  cmp     [rbp+90h+arg_48], sil
0x18002940f  cmovz   ecx, eax
0x180029412  mov     edi, ecx
0x180029414  bts     edi, 13h
0x180029418  cmp     [rbp+90h+arg_38], sil
0x18002941f  cmovz   edi, ecx
0x180029422  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities> `wil::Feature<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::GetImpl(void)'::`2'::impl
0x180029429  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::__private_IsEnabled(void)
0x18002942e  test    al, al
0x180029430  jz      loc_18002959D
0x180029436  lea     rax, [rsp+190h+var_118]
0x18002943b  mov     [rsp+190h+var_118], rsi
0x180029440  lea     rcx, [rsp+190h+var_118]
0x180029445  mov     qword ptr [rbp+90h+DestinationString.Length], rax
0x180029449  mov     [rbp+90h+var_110], rsi
0x18002944d  mov     dword ptr [rbp+90h+DestinationString.Buffer], esi
0x180029450  mov     byte ptr [rbp+90h+DestinationString.Buffer+4], 1
0x180029454  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180029459  mov     rcx, [rbp+90h+var_F0]
0x18002945d  lea     rax, [rbp+90h+DestinationString.Buffer]
0x180029461  mov     [rsp+190h+var_140], rsi
0x180029466  xor     r9d, r9d
0x180029469  mov     [rsp+190h+var_148], rsi
0x18002946e  xor     r8d, r8d
0x180029471  mov     [rsp+190h+var_150], rsi
0x180029476  xor     edx, edx
0x180029478  mov     [rsp+190h+var_158], rsi
0x18002947d  mov     [rsp+190h+var_160], rax
0x180029482  lea     rax, [rsp+190h+var_118]
0x180029487  mov     [rsp+190h+var_168], rax
0x18002948c  mov     [rsp+190h+var_170], rsi
0x180029491  call    cs:__imp_QueryApplicationCapabilitiesEx
0x180029498  nop     dword ptr [rax+rax+00h]
0x18002949d  cmp     byte ptr [rbp+90h+DestinationString.Buffer+4], sil
0x1800294a1  jz      short loc_1800294AE
0x1800294a3  mov     rcx, qword ptr [rbp+90h+DestinationString.Length]
0x1800294a7  mov     edx, dword ptr [rbp+90h+DestinationString.Buffer]
0x1800294aa  mov     [rcx+8], rdx
0x1800294ae  mov     edx, 80000000h
0x1800294b3  lea     ecx, [rax+rdx]
0x1800294b6  test    edx, ecx
0x1800294b8  jnz     short loc_1800294DF
0x1800294ba  cmp     eax, 800701C4h
0x1800294bf  jz      short loc_1800294DF
0x1800294c1  lea     rcx, [rsp+190h+var_118]
0x1800294c6  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x1800294cb  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800294d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800294d5  mov     ebx, 0C0000001h
0x1800294da  jmp     loc_180029660
0x1800294df  mov     ebx, edi
0x1800294e1  cmp     [rbp+90h+var_110], rsi
0x1800294e5  jbe     loc_180029591
0x1800294eb  xorps   xmm0, xmm0
0x1800294ee  lea     rdx, SourceString; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x1800294f5  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800294f9  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x1800294fd  call    cs:__imp_RtlInitUnicodeString
0x180029504  nop     dword ptr [rax+rax+00h]
0x180029509  mov     ebx, 44h ; 'D'
0x18002950e  lea     rcx, [rbp+90h+pSid2]; void *
0x180029512  mov     r8d, ebx; Size
0x180029515  xor     edx, edx; Val
0x180029517  call    memset_0
0x18002951c  mov     r8d, ebx; Size
0x18002951f  lea     rcx, [rbp+90h+var_80]; void *
0x180029523  xor     edx, edx; Val
0x180029525  call    memset_0
0x18002952a  lea     r8, [rbp+90h+pSid2]
0x18002952e  lea     rdx, [rbp+90h+var_80]
0x180029532  lea     rcx, [rbp+90h+DestinationString]
0x180029536  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18002953d  nop     dword ptr [rax+rax+00h]
0x180029542  mov     ebx, eax
0x180029544  test    eax, eax
0x180029546  jns     short loc_180029557
0x180029548  lea     rcx, [rsp+190h+var_118]
0x18002954d  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180029552  jmp     loc_1800292B2
0x180029557  cmp     [rbp+90h+var_110], 0
0x18002955c  mov     ebx, edi
0x18002955e  jbe     short loc_18002958F
0x180029560  xor     eax, eax
0x180029562  mov     rcx, [rsp+190h+var_118]
0x180029567  lea     rdx, [rbp+90h+pSid2]; pSid2
0x18002956b  mov     rcx, [rcx+rax*8]; pSid1
0x18002956f  call    cs:__imp_EqualSid
0x180029576  nop     dword ptr [rax+rax+00h]
0x18002957b  test    eax, eax
0x18002957d  jnz     short loc_18002958B
0x18002957f  inc     esi
0x180029581  mov     eax, esi
0x180029583  cmp     rax, [rbp+90h+var_110]
0x180029587  jb      short loc_180029562
0x180029589  jmp     short loc_18002958F
0x18002958b  bts     ebx, 0Ch
0x18002958f  xor     esi, esi
0x180029591  lea     rcx, [rsp+190h+var_118]
0x180029596  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18002959b  jmp     short loc_18002959F
0x18002959d  mov     ebx, edi
0x18002959f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x1800295a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x1800295ab  test    al, al
0x1800295ad  jz      short loc_1800295C1
0x1800295af  cmp     [rbp+90h+arg_50], sil
0x1800295b6  jz      short loc_1800295C1
0x1800295b8  test    r14d, r14d
0x1800295bb  jz      short loc_1800295C1
0x1800295bd  bts     ebx, 15h
0x1800295c1  xor     edx, edx
0x1800295c3  lea     rcx, [rsp+190h+var_128]
0x1800295c8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800295cd  mov     r9, [rbp+90h+var_F0]
0x1800295d1  lea     rax, [rsp+190h+var_128]
0x1800295d6  mov     [rsp+190h+var_148], rax
0x1800295db  mov     r8d, 1
0x1800295e1  mov     rax, [rbp+90h+var_E8]
0x1800295e5  mov     edx, ebx
0x1800295e7  mov     [rsp+190h+var_150], rax
0x1800295ec  mov     rcx, r13
0x1800295ef  mov     [rsp+190h+var_158], r15
0x1800295f4  mov     [rsp+190h+var_160], r12
0x1800295f9  mov     dword ptr [rsp+190h+var_168], esi
0x1800295fd  mov     rsi, [rbp+90h+var_F8]
0x180029601  mov     [rsp+190h+var_170], rsi
0x180029606  call    cs:__imp_PsmAdjustActivationTokenEx2
0x18002960d  nop     dword ptr [rax+rax+00h]
0x180029612  mov     rcx, [rbp+90h+var_F0]; unsigned __int16 *
0x180029616  mov     r8d, ebx; unsigned int
0x180029619  mov     rdx, rsi; unsigned __int16 *
0x18002961c  mov     edi, eax
0x18002961e  call    ?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z; AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)
0x180029623  test    edi, edi
0x180029625  jnz     short loc_180029639
0x180029627  mov     rcx, [rsp+190h+var_128]
0x18002962c  mov     rax, [rbp+90h+var_E0]
0x180029630  and     [rsp+190h+var_128], 0
0x180029636  mov     [rax], rcx
0x180029639  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002963e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029643  lea     rcx, [rsp+190h+var_128]
0x180029648  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002964d  mov     eax, edi
0x18002964f  jmp     short loc_180029687
0x180029651  lea     rcx, [rsp+190h+NewTokenHandle]
0x180029656  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002965b  mov     ebx, 0C000000Dh
0x180029660  lea     rcx, [rsp+190h+var_128]
0x180029665  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002966a  mov     eax, ebx
0x18002966c  jmp     short loc_180029687
0x18002966e  lea     rcx, [rsp+190h+NewTokenHandle]
0x180029673  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029678  lea     rcx, [rsp+190h+var_128]
0x18002967d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029682  mov     eax, 0C000000Dh
0x180029687  mov     rcx, [rbp+90h+var_30]
0x18002968b  xor     rcx, rsp; StackCookie
0x18002968e  call    __security_check_cookie
  ... truncated ...
```
