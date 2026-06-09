# CodeIntegrity::Management::LoadOneExtensionConfig

- ea: `0x18000b878`
- end: `0x18000ba15`
- name: `CodeIntegrity::Management::LoadOneExtensionConfig`
- size: `413`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x180007654`
- `0x180007678`
- `0x18000a29c`
- `0x18000a35c`
- `0x18000a3f4`
- `0x18000a900`
- `0x18000b134`
- `0x18000b878`
- `0x18000d688`
- `0x18000d730`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b8d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b8d1`
- `ntdll!RtlFreeUnicodeString` at `0x18000b9f5`
- `ntdll!RtlFreeUnicodeString` at `0x18000b9f5`
- `ntdll!NtOpenKey` at `0x18000b979`
- `ntdll!NtOpenKey` at `0x18000b979`

## string_xrefs

- `0x18000b91b`: `onecore\base\ci\management\dll\policymgmt.cpp`
- `0x18000b9b3`: `onecore\base\ci\management\dll\policymgmt.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CodeIntegrity::Management::LoadOneExtensionConfig(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        _QWORD *a3)
{
  HLOCAL v6; // rax
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // edi
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  NTSTATUS v15; // ebx
  int RegistryStringValue; // eax
  HANDLE v18; // [rsp+20h] [rbp-60h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+28h] [rbp-58h] BYREF
  HANDLE *v20; // [rsp+38h] [rbp-48h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-40h] BYREF
  char v22; // [rsp+48h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int64 v25; // [rsp+B8h] [rbp+38h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  UnicodeString = 0;
  v25 = 0;
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v18,
    -1);
  v6 = LocalAlloc(0x40u, 0x20u);
  wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset(
    &v25,
    v6);
  v7 = v25;
  if ( !v25 )
  {
    v8 = -2147024882;
    v9 = 2147942414LL;
    v10 = 180;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
      (const char *)v9,
      (int)v18);
    goto LABEL_12;
  }
  v11 = CodeIntegrity::Management::BuildRegistryPath(a1, a2);
  v12 = v11;
  if ( v11 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v20 = &v18;
    KeyHandle = 0;
    v22 = 1;
    v15 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v20);
    if ( v15 >= 0 )
    {
      RegistryStringValue = CodeIntegrity::Management::GetRegistryStringValue(v18);
      v8 = RegistryStringValue;
      if ( RegistryStringValue >= 0 )
      {
        v25 = 0;
        *a3 = v7;
        wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset(
          &v25,
          0);
        v8 = v12;
        goto LABEL_12;
      }
      v9 = (unsigned int)RegistryStringValue;
      v10 = 203;
      goto LABEL_10;
    }
    v13 = (unsigned int)v15;
    v14 = 199;
  }
  else
  {
    v13 = (unsigned int)v11;
    v14 = 185;
  }
  v8 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)v14,
         (unsigned int)"onecore\\base\\ci\\management\\dll\\policymgmt.cpp",
         (const char *)v13,
         (int)v18);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___(&v25);
  RtlFreeUnicodeString(&UnicodeString);
  return v8;
}

```

## disassembly

```asm
0x18000b878  mov     [rsp-18h+arg_0], rbx
0x18000b87d  mov     [rsp-18h+arg_8], rsi
0x18000b882  push    rbp
0x18000b883  push    rdi
0x18000b884  push    r14
0x18000b886  mov     rbp, rsp
0x18000b889  sub     rsp, 80h
0x18000b890  mov     r14, r8
0x18000b893  mov     rbx, rdx
0x18000b896  mov     rdi, rcx
0x18000b899  xorps   xmm0, xmm0
0x18000b89c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000b8a0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000b8a4  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b8a8  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18000b8ac  mov     [rbp+arg_18], 0
0x18000b8b4  mov     [rbp+var_60], 0
0x18000b8bc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b8c0  lea     rcx, [rbp+var_60]
0x18000b8c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000b8c9  mov     edx, 20h ; ' '; uBytes
0x18000b8ce  lea     ecx, [rdx+20h]; uFlags
0x18000b8d1  call    cs:__imp_LocalAlloc
0x18000b8d7  mov     rdx, rax
0x18000b8da  lea     rcx, [rbp+arg_18]
0x18000b8de  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t_____reset
0x18000b8e3  mov     rsi, [rbp+arg_18]
0x18000b8e7  test    rsi, rsi
0x18000b8ea  jnz     short loc_18000B8FE
0x18000b8ec  mov     ebx, 8007000Eh
0x18000b8f1  mov     r9d, ebx
0x18000b8f4  mov     edx, 0B4h
0x18000b8f9  jmp     loc_18000B9B3
0x18000b8fe  lea     r8, [rbp+UnicodeString]
0x18000b902  mov     rdx, rbx; struct _UNICODE_STRING *
0x18000b905  mov     rcx, rdi; struct _UNICODE_STRING *
0x18000b908  call    CodeIntegrity__Management__BuildRegistryPath
0x18000b90d  mov     edi, eax
0x18000b90f  test    eax, eax
0x18000b911  jns     short loc_18000B932
0x18000b913  mov     r9d, eax; char *
0x18000b916  mov     edx, 0B9h; void *
0x18000b91b  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b922  mov     rcx, [rbp+18h]; this
0x18000b926  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000b92b  mov     ebx, eax
0x18000b92d  jmp     loc_18000B9DD
0x18000b932  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000b939  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000b941  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000b948  lea     rax, [rbp+UnicodeString]
0x18000b94c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000b950  xorps   xmm0, xmm0
0x18000b953  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b958  lea     rax, [rbp+var_60]
0x18000b95c  mov     [rbp+var_48], rax
0x18000b960  mov     [rbp+KeyHandle], 0
0x18000b968  mov     [rbp+var_38], 1
0x18000b96c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000b970  mov     edx, 20019h; DesiredAccess
0x18000b975  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000b979  call    cs:__imp_NtOpenKey
0x18000b97f  mov     ebx, eax
0x18000b981  lea     rcx, [rbp+var_48]
0x18000b985  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18000b98a  test    ebx, ebx
0x18000b98c  jns     short loc_18000B998
0x18000b98e  mov     r9d, ebx
0x18000b991  mov     edx, 0C7h
0x18000b996  jmp     short loc_18000B91B
0x18000b998  lea     r8, [rsi+10h]
0x18000b99c  mov     rcx, [rbp+var_60]; KeyHandle
0x18000b9a0  call    CodeIntegrity__Management__GetRegistryStringValue
0x18000b9a5  mov     ebx, eax
0x18000b9a7  test    eax, eax
0x18000b9a9  jns     short loc_18000B9C5
0x18000b9ab  mov     r9d, eax; char *
0x18000b9ae  mov     edx, 0CBh; void *
0x18000b9b3  lea     r8, aOnecoreBaseCiM_3; "onecore\\base\\ci\\management\\dll\\pol"...
0x18000b9ba  mov     rcx, [rbp+18h]; this
0x18000b9be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9c3  jmp     short loc_18000B9DD
0x18000b9c5  mov     [rbp+arg_18], 0
0x18000b9cd  mov     [r14], rsi
0x18000b9d0  xor     edx, edx
0x18000b9d2  lea     rcx, [rbp+arg_18]
0x18000b9d6  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t_____reset
0x18000b9db  mov     ebx, edi
0x18000b9dd  lea     rcx, [rbp+var_60]
0x18000b9e1  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000b9e6  nop
0x18000b9e7  lea     rcx, [rbp+arg_18]
0x18000b9eb  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t______unique_storage_wil__details__resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity__Management__FreeExtRegistry_wistd__integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std__nullptr_t___
0x18000b9f0  nop
0x18000b9f1  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18000b9f5  call    cs:__imp_RtlFreeUnicodeString
0x18000b9fb  mov     eax, ebx
0x18000b9fd  lea     r11, [rsp+80h+var_s0]
0x18000ba05  mov     rbx, [r11+20h]
0x18000ba09  mov     rsi, [r11+28h]
0x18000ba0d  mov     rsp, r11
0x18000ba10  pop     r14
0x18000ba12  pop     rdi
0x18000ba13  pop     rbp
0x18000ba14  retn
```
