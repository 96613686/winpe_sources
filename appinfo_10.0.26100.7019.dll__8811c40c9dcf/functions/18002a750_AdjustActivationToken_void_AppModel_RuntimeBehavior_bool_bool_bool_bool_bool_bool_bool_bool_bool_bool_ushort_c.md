# AdjustActivationToken(void *,AppModel::RuntimeBehavior,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,ushort const *,ushort const *,unsigned __int64 *,_GUID *,ushort const *,void * *)

- ea: `0x18002a750`
- end: `0x18002ac35`
- name: `?AdjustActivationToken@@YAJPEAXW4RuntimeBehavior@AppModel@@_N222222222PEBG3PEA_KPEAU_GUID@@3PEAPEAX@Z`
- size: `1253`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028aa4`
- `0x180029ce4`
- `0x18002ac3c`
- `0x18002b828`
- `0x1800327a0`

## callees

- `0x18000c790`
- `0x18000d8e0`
- `0x18000def0`
- `0x18000f8b0`
- `0x18001a970`
- `0x18001bee0`
- `0x18002a750`
- `0x180038e3c`
- `0x1800391c4`
- `0x180039204`
- `0x1800392b8`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002aadf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002aadf`
- `ntdll!RtlInitUnicodeString` at `0x18002aa6d`
- `ntdll!RtlInitUnicodeString` at `0x18002aa6d`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18002aaa6`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18002aaa6`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x18002ab86`
- `ext-ms-win-com-psmregister-l1-3-1!PsmAdjustActivationTokenEx2` at `0x18002ab86`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18002aa01`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18002aa01`
- `api-ms-win-appmodel-lifecyclepolicy-l1-1-0!AppModelQueryLifecyclePolicy` at `0x18002a8a7`
- `api-ms-win-appmodel-lifecyclepolicy-l1-1-0!AppModelQueryLifecyclePolicy` at `0x18002a8a7`

## string_xrefs

- `0x18002aa5e`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

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
    goto LABEL_71;
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
LABEL_71:
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
        goto LABEL_71;
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
    goto LABEL_71;
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
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v41);
    v31 = QueryApplicationCapabilitiesEx(v45, 0, 0, 0, 0, &v41, &DestinationString.Buffer, 0, 0, 0, 0);
    if ( BYTE4(DestinationString.Buffer) )
      *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 8LL) = LODWORD(DestinationString.Buffer);
    if ( (int)(v31 + 0x80000000) >= 0 && v31 != -2147024444 )
    {
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v41);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&NewTokenHandle);
      RestrictedTokenForAppContainer = -1073741823;
      goto LABEL_71;
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
        wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v41);
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
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(&v41);
  }
  else
  {
    v32 = v30;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl)
    && a11
    && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl'::`2'::impl)
     || a2) )
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
0x18002a750  mov     [rsp-8+arg_8], rbx
0x18002a755  mov     [rsp-8+arg_10], rsi
0x18002a75a  mov     [rsp-8+arg_18], rdi
0x18002a75f  push    rbp
0x18002a760  push    r12
0x18002a762  push    r13
0x18002a764  push    r14
0x18002a766  push    r15
0x18002a768  lea     rbp, [rsp-70h]
0x18002a76d  sub     rsp, 170h
0x18002a774  mov     rax, cs:__security_cookie
0x18002a77b  xor     rax, rsp
0x18002a77e  mov     [rbp+90h+var_30], rax
0x18002a782  mov     rax, [rbp+90h+arg_60]
0x18002a789  mov     sil, r8b
0x18002a78c  mov     rdi, [rbp+90h+arg_88]
0x18002a793  mov     r14d, edx
0x18002a796  mov     r15, [rbp+90h+arg_70]
0x18002a79d  mov     r13, rcx
0x18002a7a0  mov     r12, [rbp+90h+arg_78]
0x18002a7a7  and     [rsp+190h+var_128], 0
0x18002a7ad  mov     [rbp+90h+var_F0], rax
0x18002a7b1  mov     rax, [rbp+90h+arg_68]
0x18002a7b8  mov     [rbp+90h+var_F8], rax
0x18002a7bc  mov     rax, [rbp+90h+arg_80]
0x18002a7c3  mov     [rbp+90h+var_E8], rax
0x18002a7c7  movzx   ebx, r9b
0x18002a7cb  mov     [rbp+90h+var_E0], rdi
0x18002a7cf  call    IsPsmAdjustActivationTokenExPresent
0x18002a7d4  test    al, al
0x18002a7d6  jz      loc_18002A8FE
0x18002a7dc  and     qword ptr [rdi], 0
0x18002a7e0  and     [rsp+190h+NewTokenHandle], 0
0x18002a7e6  test    r15, r15
0x18002a7e9  jz      short loc_18002A831
0x18002a7eb  test    r12, r12
0x18002a7ee  jz      short loc_18002A836
0x18002a7f0  test    r14d, r14d
0x18002a7f3  jnz     short loc_18002A868
0x18002a7f5  mov     edi, ebx
0x18002a7f7  shl     edi, 9
0x18002a7fa  inc     edi
0x18002a7fc  test    sil, sil
0x18002a7ff  jz      short loc_18002A851
0x18002a801  xor     edx, edx
0x18002a803  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002a808  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a80d  lea     rdx, [rsp+190h+NewTokenHandle]; NewTokenHandle
0x18002a812  mov     rcx, r13; ExistingTokenHandle
0x18002a815  call    ?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z; GetRestrictedTokenForAppContainer(void *,void * *)
0x18002a81a  xor     esi, esi
0x18002a81c  mov     ebx, eax
0x18002a81e  test    eax, eax
0x18002a820  jns     short loc_18002A84A
0x18002a822  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002a827  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a82c  jmp     loc_18002ABE0
0x18002a831  test    r12, r12
0x18002a834  jz      short loc_18002A7F0
0x18002a836  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002a83b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a840  mov     ebx, 0C0000030h
0x18002a845  jmp     loc_18002ABE0
0x18002a84a  mov     r13, [rsp+190h+NewTokenHandle]
0x18002a84f  jmp     short loc_18002A857
0x18002a851  bts     edi, 0Bh
0x18002a855  xor     esi, esi
0x18002a857  mov     ecx, edi
0x18002a859  bts     ecx, 1Dh
0x18002a85d  test    r15, r15
0x18002a860  cmovnz  ecx, edi
0x18002a863  jmp     loc_18002A960
0x18002a868  cmp     [rbp+90h+arg_40], 0
0x18002a86f  jz      short loc_18002A887
0x18002a871  mov     rax, r15
0x18002a874  neg     rax
0x18002a877  sbb     ebx, ebx
0x18002a879  and     ebx, 0E0000000h
0x18002a87f  add     ebx, 20100001h
0x18002a885  jmp     short loc_18002A8D2
0x18002a887  test    r15, r15
0x18002a88a  jnz     loc_18002ABEE
0x18002a890  test    r12, r12
0x18002a893  jnz     loc_18002ABEE
0x18002a899  mov     rcx, [rbp+90h+var_F8]
0x18002a89d  lea     rdx, [rsp+190h+var_120]
0x18002a8a2  and     [rsp+190h+var_120], r12d
0x18002a8a7  call    cs:__imp_AppModelQueryLifecyclePolicy
0x18002a8ae  nop     dword ptr [rax+rax+00h]
0x18002a8b3  mov     ebx, eax
0x18002a8b5  test    eax, eax
0x18002a8b7  js      loc_18002A822
0x18002a8bd  cmp     [rsp+190h+var_120], 10001h
0x18002a8c5  mov     ebx, 10000001h
0x18002a8ca  mov     eax, 20004001h
0x18002a8cf  cmovz   ebx, eax
0x18002a8d2  cmp     r14d, 1
0x18002a8d6  jnz     short loc_18002A8E9
0x18002a8d8  neg     sil
0x18002a8db  sbb     eax, eax
0x18002a8dd  and     eax, 3FCh
0x18002a8e2  add     eax, 4
0x18002a8e5  or      ebx, eax
0x18002a8e7  jmp     short loc_18002A941
0x18002a8e9  cmp     r14d, 2
0x18002a8ed  jnz     short loc_18002A933
0x18002a8ef  test    sil, sil
0x18002a8f2  jz      short loc_18002A908
0x18002a8f4  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002a8f9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a8fe  mov     ebx, 0C00000BBh
0x18002a903  jmp     loc_18002ABE0
0x18002a908  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte> `wil::Feature<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::GetImpl(void)'::`2'::impl
0x18002a90f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte>::__private_IsEnabled(void)
0x18002a914  xor     esi, esi
0x18002a916  test    al, al
0x18002a918  jz      short loc_18002A92B
0x18002a91a  cmp     [rbp+90h+arg_58], sil
0x18002a921  jz      short loc_18002A92B
0x18002a923  or      ebx, 10020h
0x18002a929  jmp     short loc_18002A943
0x18002a92b  or      ebx, 10100h
0x18002a931  jmp     short loc_18002A943
0x18002a933  cmp     r14d, 3
0x18002a937  jnz     loc_18002ABD1
0x18002a93d  bts     ebx, 12h
0x18002a941  xor     esi, esi
0x18002a943  mov     ecx, ebx
0x18002a945  bts     ecx, 0Fh
0x18002a949  cmp     [rbp+90h+arg_20], sil
0x18002a950  cmovz   ecx, ebx
0x18002a953  cmp     [rbp+90h+arg_28], sil
0x18002a95a  jz      short loc_18002A960
0x18002a95c  bts     ecx, 11h
0x18002a960  mov     eax, ecx
0x18002a962  bts     eax, 0Dh
0x18002a966  cmp     [rbp+90h+arg_30], sil
0x18002a96d  cmovz   eax, ecx
0x18002a970  mov     ecx, eax
0x18002a972  or      ecx, 40000010h
0x18002a978  cmp     [rbp+90h+arg_48], sil
0x18002a97f  cmovz   ecx, eax
0x18002a982  mov     edi, ecx
0x18002a984  bts     edi, 13h
0x18002a988  cmp     [rbp+90h+arg_38], sil
0x18002a98f  cmovz   edi, ecx
0x18002a992  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities> `wil::Feature<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::GetImpl(void)'::`2'::impl
0x18002a999  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::__private_IsEnabled(void)
0x18002a99e  test    al, al
0x18002a9a0  jz      loc_18002AB0D
0x18002a9a6  lea     rax, [rsp+190h+var_118]
0x18002a9ab  mov     [rsp+190h+var_118], rsi
0x18002a9b0  lea     rcx, [rsp+190h+var_118]
0x18002a9b5  mov     qword ptr [rbp+90h+DestinationString.Length], rax
0x18002a9b9  mov     [rbp+90h+var_110], rsi
0x18002a9bd  mov     dword ptr [rbp+90h+DestinationString.Buffer], esi
0x18002a9c0  mov     byte ptr [rbp+90h+DestinationString.Buffer+4], 1
0x18002a9c4  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x18002a9c9  mov     rcx, [rbp+90h+var_F0]
0x18002a9cd  lea     rax, [rbp+90h+DestinationString.Buffer]
0x18002a9d1  mov     [rsp+190h+var_140], rsi
0x18002a9d6  xor     r9d, r9d
0x18002a9d9  mov     [rsp+190h+var_148], rsi
0x18002a9de  xor     r8d, r8d
0x18002a9e1  mov     [rsp+190h+var_150], rsi
0x18002a9e6  xor     edx, edx
0x18002a9e8  mov     [rsp+190h+var_158], rsi
0x18002a9ed  mov     [rsp+190h+var_160], rax
0x18002a9f2  lea     rax, [rsp+190h+var_118]
0x18002a9f7  mov     [rsp+190h+var_168], rax
0x18002a9fc  mov     [rsp+190h+var_170], rsi
0x18002aa01  call    cs:__imp_QueryApplicationCapabilitiesEx
0x18002aa08  nop     dword ptr [rax+rax+00h]
0x18002aa0d  cmp     byte ptr [rbp+90h+DestinationString.Buffer+4], sil
0x18002aa11  jz      short loc_18002AA1E
0x18002aa13  mov     rcx, qword ptr [rbp+90h+DestinationString.Length]
0x18002aa17  mov     edx, dword ptr [rbp+90h+DestinationString.Buffer]
0x18002aa1a  mov     [rcx+8], rdx
0x18002aa1e  mov     edx, 80000000h
0x18002aa23  lea     ecx, [rax+rdx]
0x18002aa26  test    edx, ecx
0x18002aa28  jnz     short loc_18002AA4F
0x18002aa2a  cmp     eax, 800701C4h
0x18002aa2f  jz      short loc_18002AA4F
0x18002aa31  lea     rcx, [rsp+190h+var_118]
0x18002aa36  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x18002aa3b  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002aa40  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002aa45  mov     ebx, 0C0000001h
0x18002aa4a  jmp     loc_18002ABE0
0x18002aa4f  mov     ebx, edi
0x18002aa51  cmp     [rbp+90h+var_110], rsi
0x18002aa55  jbe     loc_18002AB01
0x18002aa5b  xorps   xmm0, xmm0
0x18002aa5e  lea     rdx, SourceString; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x18002aa65  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18002aa69  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x18002aa6d  call    cs:__imp_RtlInitUnicodeString
0x18002aa74  nop     dword ptr [rax+rax+00h]
0x18002aa79  mov     ebx, 44h ; 'D'
0x18002aa7e  lea     rcx, [rbp+90h+pSid2]; void *
0x18002aa82  mov     r8d, ebx; Size
0x18002aa85  xor     edx, edx; Val
0x18002aa87  call    memset_0
0x18002aa8c  mov     r8d, ebx; Size
0x18002aa8f  lea     rcx, [rbp+90h+var_80]; void *
0x18002aa93  xor     edx, edx; Val
0x18002aa95  call    memset_0
0x18002aa9a  lea     r8, [rbp+90h+pSid2]
0x18002aa9e  lea     rdx, [rbp+90h+var_80]
0x18002aaa2  lea     rcx, [rbp+90h+DestinationString]
0x18002aaa6  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18002aaad  nop     dword ptr [rax+rax+00h]
0x18002aab2  mov     ebx, eax
0x18002aab4  test    eax, eax
0x18002aab6  jns     short loc_18002AAC7
0x18002aab8  lea     rcx, [rsp+190h+var_118]
0x18002aabd  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x18002aac2  jmp     loc_18002A822
0x18002aac7  cmp     [rbp+90h+var_110], 0
0x18002aacc  mov     ebx, edi
0x18002aace  jbe     short loc_18002AAFF
0x18002aad0  xor     eax, eax
0x18002aad2  mov     rcx, [rsp+190h+var_118]
0x18002aad7  lea     rdx, [rbp+90h+pSid2]; pSid2
0x18002aadb  mov     rcx, [rcx+rax*8]; pSid1
0x18002aadf  call    cs:__imp_EqualSid
0x18002aae6  nop     dword ptr [rax+rax+00h]
0x18002aaeb  test    eax, eax
0x18002aaed  jnz     short loc_18002AAFB
0x18002aaef  inc     esi
0x18002aaf1  mov     eax, esi
0x18002aaf3  cmp     rax, [rbp+90h+var_110]
0x18002aaf7  jb      short loc_18002AAD2
0x18002aaf9  jmp     short loc_18002AAFF
0x18002aafb  bts     ebx, 0Ch
0x18002aaff  xor     esi, esi
0x18002ab01  lea     rcx, [rsp+190h+var_118]
0x18002ab06  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)
0x18002ab0b  jmp     short loc_18002AB0F
0x18002ab0d  mov     ebx, edi
0x18002ab0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x18002ab16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x18002ab1b  test    al, al
0x18002ab1d  jz      short loc_18002AB41
0x18002ab1f  cmp     [rbp+90h+arg_50], sil
0x18002ab26  jz      short loc_18002AB41
0x18002ab28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunchHosts@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchHosts@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunchHosts>::GetImpl(void)'::`2'::impl
0x18002ab2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunchHosts@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunchHosts>::__private_IsEnabled(void)
0x18002ab34  test    al, al
0x18002ab36  jz      short loc_18002AB3D
0x18002ab38  test    r14d, r14d
0x18002ab3b  jz      short loc_18002AB41
0x18002ab3d  bts     ebx, 15h
0x18002ab41  xor     edx, edx
0x18002ab43  lea     rcx, [rsp+190h+var_128]
0x18002ab48  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002ab4d  mov     r9, [rbp+90h+var_F0]
0x18002ab51  lea     rax, [rsp+190h+var_128]
0x18002ab56  mov     [rsp+190h+var_148], rax
0x18002ab5b  mov     r8d, 1
0x18002ab61  mov     rax, [rbp+90h+var_E8]
0x18002ab65  mov     edx, ebx
0x18002ab67  mov     [rsp+190h+var_150], rax
0x18002ab6c  mov     rcx, r13
0x18002ab6f  mov     [rsp+190h+var_158], r15
0x18002ab74  mov     [rsp+190h+var_160], r12
0x18002ab79  mov     dword ptr [rsp+190h+var_168], esi
0x18002ab7d  mov     rsi, [rbp+90h+var_F8]
0x18002ab81  mov     [rsp+190h+var_170], rsi
0x18002ab86  call    cs:__imp_PsmAdjustActivationTokenEx2
0x18002ab8d  nop     dword ptr [rax+rax+00h]
0x18002ab92  mov     rcx, [rbp+90h+var_F0]; unsigned __int16 *
0x18002ab96  mov     r8d, ebx; unsigned int
0x18002ab99  mov     rdx, rsi; unsigned __int16 *
0x18002ab9c  mov     edi, eax
0x18002ab9e  call    ?AipLogDesktopAppXProcessLogPSMFlags@@YAXPEBG0K@Z; AipLogDesktopAppXProcessLogPSMFlags(ushort const *,ushort const *,ulong)
0x18002aba3  test    edi, edi
0x18002aba5  jnz     short loc_18002ABB9
0x18002aba7  mov     rcx, [rsp+190h+var_128]
0x18002abac  mov     rax, [rbp+90h+var_E0]
0x18002abb0  and     [rsp+190h+var_128], 0
0x18002abb6  mov     [rax], rcx
0x18002abb9  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002abbe  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002abc3  lea     rcx, [rsp+190h+var_128]
0x18002abc8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002abcd  mov     eax, edi
0x18002abcf  jmp     short loc_18002AC07
0x18002abd1  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002abd6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002abdb  mov     ebx, 0C000000Dh
0x18002abe0  lea     rcx, [rsp+190h+var_128]
0x18002abe5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002abea  mov     eax, ebx
0x18002abec  jmp     short loc_18002AC07
0x18002abee  lea     rcx, [rsp+190h+NewTokenHandle]
0x18002abf3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002abf8  lea     rcx, [rsp+190h+var_128]
0x18002abfd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
  ... truncated ...
```
