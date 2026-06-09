# AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)

- ea: `0x180029110`
- end: `0x1800295e5`
- name: `?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z`
- size: `1237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027464`
- `0x1800286a4`
- `0x1800295ec`
- `0x18002a1d8`
- `0x180032810`

## callees

- `0x18000c790`
- `0x18000de30`
- `0x18000f9e0`
- `0x18001ad40`
- `0x18001c2bc`
- `0x180029110`
- `0x1800394dc`
- `0x180039828`
- `0x180039a0c`
- `0x180039df0`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002949f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002949f`
- `ntdll!RtlInitUnicodeString` at `0x18002942d`
- `ntdll!RtlInitUnicodeString` at `0x18002942d`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180029466`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180029466`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x180029536`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x180029536`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x1800293c1`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x1800293c1`
- `api-ms-win-appmodel-lifecyclepolicy-l1-1-0!AppModelQueryLifecyclePolicy` at `0x180029267`
- `api-ms-win-appmodel-lifecyclepolicy-l1-1-0!AppModelQueryLifecyclePolicy` at `0x180029267`

## string_xrefs

- `0x18002941e`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

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
0x180029110  mov     [rsp-8+arg_8], rbx
0x180029115  mov     [rsp-8+arg_10], rsi
0x18002911a  mov     [rsp-8+arg_18], rdi
0x18002911f  push    rbp
0x180029120  push    r12
0x180029122  push    r13
0x180029124  push    r14
0x180029126  push    r15
0x180029128  lea     rbp, [rsp-70h]
0x18002912d  sub     rsp, 170h
0x180029134  mov     rax, cs:__security_cookie
0x18002913b  xor     rax, rsp
0x18002913e  mov     [rbp+90h+var_30], rax
0x180029142  mov     rax, [rbp+90h+arg_60]
0x180029149  mov     sil, r8b
0x18002914c  mov     rdi, [rbp+90h+arg_88]
0x180029153  mov     r14d, edx
0x180029156  mov     r15, [rbp+90h+arg_70]
0x18002915d  mov     r13, rcx
0x180029160  mov     r12, [rbp+90h+arg_78]
0x180029167  and     [rsp+190h+var_128], 0
0x18002916d  mov     [rbp+90h+var_F0], rax
0x180029171  mov     rax, [rbp+90h+arg_68]
0x180029178  mov     [rbp+90h+var_F8], rax
0x18002917c  mov     rax, [rbp+90h+arg_80]
0x180029183  mov     [rbp+90h+var_E8], rax
0x180029187  movzx   ebx, r9b
0x18002918b  mov     [rbp+90h+var_E0], rdi
0x18002918f  call    IsPsmAdjustActivationTokenExPresent
0x180029194  test    al, al
0x180029196  jz      loc_1800292BE
0x18002919c  and     qword ptr [rdi], 0
0x1800291a0  and     [rsp+190h+NewTokenHandle], 0
0x1800291a6  test    r15, r15
0x1800291a9  jz      short loc_1800291F1
0x1800291ab  test    r12, r12
0x1800291ae  jz      short loc_1800291F6
0x1800291b0  test    r14d, r14d
0x1800291b3  jnz     short loc_180029228
0x1800291b5  mov     edi, ebx
0x1800291b7  shl     edi, 9
0x1800291ba  inc     edi
0x1800291bc  test    sil, sil
0x1800291bf  jz      short loc_180029211
0x1800291c1  xor     edx, edx
0x1800291c3  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800291c8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800291cd  lea     rdx, [rsp+190h+NewTokenHandle]; NewTokenHandle
0x1800291d2  mov     rcx, r13; ExistingTokenHandle
0x1800291d5  call    ?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z; GetRestrictedTokenForAppContainer(void *,void * *)
0x1800291da  xor     esi, esi
0x1800291dc  mov     ebx, eax
0x1800291de  test    eax, eax
0x1800291e0  jns     short loc_18002920A
0x1800291e2  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800291e7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800291ec  jmp     loc_180029590
0x1800291f1  test    r12, r12
0x1800291f4  jz      short loc_1800291B0
0x1800291f6  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800291fb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029200  mov     ebx, 0C0000030h
0x180029205  jmp     loc_180029590
0x18002920a  mov     r13, [rsp+190h+NewTokenHandle]
0x18002920f  jmp     short loc_180029217
0x180029211  bts     edi, 0Bh
0x180029215  xor     esi, esi
0x180029217  mov     ecx, edi
0x180029219  bts     ecx, 1Dh
0x18002921d  test    r15, r15
0x180029220  cmovnz  ecx, edi
0x180029223  jmp     loc_180029320
0x180029228  cmp     [rbp+90h+arg_40], 0
0x18002922f  jz      short loc_180029247
0x180029231  mov     rax, r15
0x180029234  neg     rax
0x180029237  sbb     ebx, ebx
0x180029239  and     ebx, 0E0000000h
0x18002923f  add     ebx, 20100001h
0x180029245  jmp     short loc_180029292
0x180029247  test    r15, r15
0x18002924a  jnz     loc_18002959E
0x180029250  test    r12, r12
0x180029253  jnz     loc_18002959E
0x180029259  mov     rcx, [rbp+90h+var_F8]
0x18002925d  lea     rdx, [rsp+190h+var_120]
0x180029262  and     [rsp+190h+var_120], r12d
0x180029267  call    cs:__imp_AppModelQueryLifecyclePolicy
0x18002926e  nop     dword ptr [rax+rax+00h]
0x180029273  mov     ebx, eax
0x180029275  test    eax, eax
0x180029277  js      loc_1800291E2
0x18002927d  cmp     [rsp+190h+var_120], 10001h
0x180029285  mov     ebx, 10000001h
0x18002928a  mov     eax, 20004001h
0x18002928f  cmovz   ebx, eax
0x180029292  cmp     r14d, 1
0x180029296  jnz     short loc_1800292A9
0x180029298  neg     sil
0x18002929b  sbb     eax, eax
0x18002929d  and     eax, 3FCh
0x1800292a2  add     eax, 4
0x1800292a5  or      ebx, eax
0x1800292a7  jmp     short loc_180029301
0x1800292a9  cmp     r14d, 2
0x1800292ad  jnz     short loc_1800292F3
0x1800292af  test    sil, sil
0x1800292b2  jz      short loc_1800292C8
0x1800292b4  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800292b9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800292be  mov     ebx, 0C00000BBh
0x1800292c3  jmp     loc_180029590
0x1800292c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte> `wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl(void)'::`2'::impl
0x1800292cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(void)
0x1800292d4  xor     esi, esi
0x1800292d6  test    al, al
0x1800292d8  jz      short loc_1800292EB
0x1800292da  cmp     [rbp+90h+arg_58], sil
0x1800292e1  jz      short loc_1800292EB
0x1800292e3  or      ebx, 10020h
0x1800292e9  jmp     short loc_180029303
0x1800292eb  or      ebx, 10100h
0x1800292f1  jmp     short loc_180029303
0x1800292f3  cmp     r14d, 3
0x1800292f7  jnz     loc_180029581
0x1800292fd  bts     ebx, 12h
0x180029301  xor     esi, esi
0x180029303  mov     ecx, ebx
0x180029305  bts     ecx, 0Fh
0x180029309  cmp     [rbp+90h+arg_20], sil
0x180029310  cmovz   ecx, ebx
0x180029313  cmp     [rbp+90h+arg_28], sil
0x18002931a  jz      short loc_180029320
0x18002931c  bts     ecx, 11h
0x180029320  mov     eax, ecx
0x180029322  bts     eax, 0Dh
0x180029326  cmp     [rbp+90h+arg_30], sil
0x18002932d  cmovz   eax, ecx
0x180029330  mov     ecx, eax
0x180029332  or      ecx, 40000010h
0x180029338  cmp     [rbp+90h+arg_48], sil
0x18002933f  cmovz   ecx, eax
0x180029342  mov     edi, ecx
0x180029344  bts     edi, 13h
0x180029348  cmp     [rbp+90h+arg_38], sil
0x18002934f  cmovz   edi, ecx
0x180029352  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities> `wil::Feature<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::GetImpl(void)'::`2'::impl
0x180029359  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::__private_IsEnabled(void)
0x18002935e  test    al, al
0x180029360  jz      loc_1800294CD
0x180029366  lea     rax, [rsp+190h+var_118]
0x18002936b  mov     [rsp+190h+var_118], rsi
0x180029370  lea     rcx, [rsp+190h+var_118]
0x180029375  mov     qword ptr [rbp+90h+DestinationString.Length], rax
0x180029379  mov     [rbp+90h+var_110], rsi
0x18002937d  mov     dword ptr [rbp+90h+DestinationString.Buffer], esi
0x180029380  mov     byte ptr [rbp+90h+DestinationString.Buffer+4], 1
0x180029384  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180029389  mov     rcx, [rbp+90h+var_F0]
0x18002938d  lea     rax, [rbp+90h+DestinationString.Buffer]
0x180029391  mov     [rsp+190h+var_140], rsi
0x180029396  xor     r9d, r9d
0x180029399  mov     [rsp+190h+var_148], rsi
0x18002939e  xor     r8d, r8d
0x1800293a1  mov     [rsp+190h+var_150], rsi
0x1800293a6  xor     edx, edx
0x1800293a8  mov     [rsp+190h+var_158], rsi
0x1800293ad  mov     [rsp+190h+var_160], rax
0x1800293b2  lea     rax, [rsp+190h+var_118]
0x1800293b7  mov     [rsp+190h+var_168], rax
0x1800293bc  mov     [rsp+190h+var_170], rsi
0x1800293c1  call    cs:__imp_QueryApplicationCapabilitiesEx
0x1800293c8  nop     dword ptr [rax+rax+00h]
0x1800293cd  cmp     byte ptr [rbp+90h+DestinationString.Buffer+4], sil
0x1800293d1  jz      short loc_1800293DE
0x1800293d3  mov     rcx, qword ptr [rbp+90h+DestinationString.Length]
0x1800293d7  mov     edx, dword ptr [rbp+90h+DestinationString.Buffer]
0x1800293da  mov     [rcx+8], rdx
0x1800293de  mov     edx, 80000000h
0x1800293e3  lea     ecx, [rax+rdx]
0x1800293e6  test    edx, ecx
0x1800293e8  jnz     short loc_18002940F
0x1800293ea  cmp     eax, 800701C4h
0x1800293ef  jz      short loc_18002940F
0x1800293f1  lea     rcx, [rsp+190h+var_118]
0x1800293f6  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x1800293fb  lea     rcx, [rsp+190h+NewTokenHandle]
0x180029400  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029405  mov     ebx, 0C0000001h
0x18002940a  jmp     loc_180029590
0x18002940f  mov     ebx, edi
0x180029411  cmp     [rbp+90h+var_110], rsi
0x180029415  jbe     loc_1800294C1
0x18002941b  xorps   xmm0, xmm0
0x18002941e  lea     rdx, SourceString; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x180029425  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x180029429  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18002942d  call    cs:__imp_RtlInitUnicodeString
0x180029434  nop     dword ptr [rax+rax+00h]
0x180029439  mov     ebx, 44h ; 'D'
0x18002943e  lea     rcx, [rbp+90h+pSid2]; void *
0x180029442  mov     r8d, ebx; Size
0x180029445  xor     edx, edx; Val
0x180029447  call    memset_0
0x18002944c  mov     r8d, ebx; Size
0x18002944f  lea     rcx, [rbp+90h+var_80]; void *
0x180029453  xor     edx, edx; Val
0x180029455  call    memset_0
0x18002945a  lea     r8, [rbp+90h+pSid2]
0x18002945e  lea     rdx, [rbp+90h+var_80]
0x180029462  lea     rcx, [rbp+90h+DestinationString]
0x180029466  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18002946d  nop     dword ptr [rax+rax+00h]
0x180029472  mov     ebx, eax
0x180029474  test    eax, eax
0x180029476  jns     short loc_180029487
0x180029478  lea     rcx, [rsp+190h+var_118]
0x18002947d  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x180029482  jmp     loc_1800291E2
0x180029487  cmp     [rbp+90h+var_110], 0
0x18002948c  mov     ebx, edi
0x18002948e  jbe     short loc_1800294BF
0x180029490  xor     eax, eax
0x180029492  mov     rcx, [rsp+190h+var_118]
0x180029497  lea     rdx, [rbp+90h+pSid2]; pSid2
0x18002949b  mov     rcx, [rcx+rax*8]; pSid1
0x18002949f  call    cs:__imp_EqualSid
0x1800294a6  nop     dword ptr [rax+rax+00h]
0x1800294ab  test    eax, eax
0x1800294ad  jnz     short loc_1800294BB
0x1800294af  inc     esi
0x1800294b1  mov     eax, esi
0x1800294b3  cmp     rax, [rbp+90h+var_110]
0x1800294b7  jb      short loc_180029492
0x1800294b9  jmp     short loc_1800294BF
0x1800294bb  bts     ebx, 0Ch
0x1800294bf  xor     esi, esi
0x1800294c1  lea     rcx, [rsp+190h+var_118]
0x1800294c6  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x1800294cb  jmp     short loc_1800294CF
0x1800294cd  mov     ebx, edi
0x1800294cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x1800294d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x1800294db  test    al, al
0x1800294dd  jz      short loc_1800294F1
0x1800294df  cmp     [rbp+90h+arg_50], sil
0x1800294e6  jz      short loc_1800294F1
0x1800294e8  test    r14d, r14d
0x1800294eb  jz      short loc_1800294F1
0x1800294ed  bts     ebx, 15h
0x1800294f1  xor     edx, edx
0x1800294f3  lea     rcx, [rsp+190h+var_128]
0x1800294f8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800294fd  mov     r9, [rbp+90h+var_F0]
0x180029501  lea     rax, [rsp+190h+var_128]
0x180029506  mov     [rsp+190h+var_148], rax
0x18002950b  mov     r8d, 1
0x180029511  mov     rax, [rbp+90h+var_E8]
0x180029515  mov     edx, ebx
0x180029517  mov     [rsp+190h+var_150], rax
0x18002951c  mov     rcx, r13
0x18002951f  mov     [rsp+190h+var_158], r15
0x180029524  mov     [rsp+190h+var_160], r12
0x180029529  mov     dword ptr [rsp+190h+var_168], esi
0x18002952d  mov     rsi, [rbp+90h+var_F8]
0x180029531  mov     [rsp+190h+var_170], rsi
0x180029536  call    cs:__imp_PsmAdjustActivationTokenEx2
0x18002953d  nop     dword ptr [rax+rax+00h]
0x180029542  mov     rcx, [rbp+90h+var_F0]; unsigned __int16 *
0x180029546  mov     r8d, ebx; unsigned int
0x180029549  mov     rdx, rsi; unsigned __int16 *
0x18002954c  mov     edi, eax
0x18002954e  call    ?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z; AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)
0x180029553  test    edi, edi
0x180029555  jnz     short loc_180029569
0x180029557  mov     rcx, [rsp+190h+var_128]
0x18002955c  mov     rax, [rbp+90h+var_E0]
0x180029560  and     [rsp+190h+var_128], 0
0x180029566  mov     [rax], rcx
0x180029569  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002956e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029573  lea     rcx, [rsp+190h+var_128]
0x180029578  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002957d  mov     eax, edi
0x18002957f  jmp     short loc_1800295B7
0x180029581  lea     rcx, [rsp+190h+NewTokenHandle]
0x180029586  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002958b  mov     ebx, 0C000000Dh
0x180029590  lea     rcx, [rsp+190h+var_128]
0x180029595  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002959a  mov     eax, ebx
0x18002959c  jmp     short loc_1800295B7
0x18002959e  lea     rcx, [rsp+190h+NewTokenHandle]
0x1800295a3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800295a8  lea     rcx, [rsp+190h+var_128]
0x1800295ad  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800295b2  mov     eax, 0C000000Dh
0x1800295b7  mov     rcx, [rbp+90h+var_30]
0x1800295bb  xor     rcx, rsp; StackCookie
0x1800295be  call    __security_check_cookie
  ... truncated ...
```
