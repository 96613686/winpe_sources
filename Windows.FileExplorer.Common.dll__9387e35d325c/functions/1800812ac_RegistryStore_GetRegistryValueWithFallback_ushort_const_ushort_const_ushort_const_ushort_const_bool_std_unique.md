# RegistryStore::GetRegistryValueWithFallback(ushort const *,ushort const *,ushort const *,ushort const *,bool,std::unique_ptr<RegistryDataEntry,void * (*)(void *)> &)

- ea: `0x1800812ac`
- end: `0x1800816f9`
- name: `?GetRegistryValueWithFallback@RegistryStore@@QEAAJPEBG000_NAEAV?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@Z`
- size: `1101`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f75c`
- `0x180080e3c`

## callees

- `0x1800077c8`
- `0x180015fa0`
- `0x180016440`
- `0x18002aa38`
- `0x18002fed4`
- `0x180030bcc`
- `0x180037780`
- `0x180080668`
- `0x1800806dc`
- `0x180080700`
- `0x180080d60`
- `0x1800812ac`
- `0x18008336c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008155d`
- `ntdll!NtOpenKey` at `0x1800813d2`
- `ntdll!NtOpenKey` at `0x18008147a`
- `ntdll!NtOpenKey` at `0x1800813d2`
- `ntdll!NtOpenKey` at `0x18008147a`
- `ntdll!RtlQueryRegistryValueWithFallback` at `0x18008152a`
- `ntdll!RtlQueryRegistryValueWithFallback` at `0x18008165d`
- `ntdll!RtlQueryRegistryValueWithFallback` at `0x18008152a`
- `ntdll!RtlQueryRegistryValueWithFallback` at `0x18008165d`
- `ntdll!RtlInitUnicodeString` at `0x180081358`
- `ntdll!RtlInitUnicodeString` at `0x180081382`
- `ntdll!RtlInitUnicodeString` at `0x1800814f3`
- `ntdll!RtlInitUnicodeString` at `0x180081358`
- `ntdll!RtlInitUnicodeString` at `0x180081382`
- `ntdll!RtlInitUnicodeString` at `0x1800814f3`

## string_xrefs

- `0x180081402`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x1800814a8`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x1800815b7`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081671`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RegistryStore::GetRegistryValueWithFallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7)
{
  __int64 v11; // r14
  const WCHAR *v12; // rdx
  const WCHAR *v13; // rdx
  unsigned int v14; // ebx
  NTSTATUS v15; // esi
  NTSTATUS v16; // edi
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // ebx
  const WCHAR *v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  void *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // eax
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B8h]
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v34; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v36; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES v37; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  HLOCAL (__stdcall *v39)(HLOCAL); // [rsp+E8h] [rbp-18h] BYREF
  void *KeyHandle; // [rsp+F0h] [rbp-10h] BYREF
  char v41; // [rsp+F8h] [rbp-8h]
  PCWSTR v42[4]; // [rsp+108h] [rbp+8h] BYREF
  PCWSTR SourceString[4]; // [rsp+128h] [rbp+28h] BYREF
  PCWSTR v44[4]; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  std::wstring::wstring(&v39, a5);
  RegistryStore::GetPathWithUserSid(a1, v44, &v39);
  std::wstring::_Tidy_deallocate(&v39);
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a3 + 2 * v11) );
  DestinationString = 0;
  v36 = 0;
  std::operator+<unsigned short>(SourceString, a1 + 8, a2);
  v12 = (const WCHAR *)SourceString;
  if ( SourceString[3] > (PCWSTR)7 )
    v12 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v12);
  std::operator+<unsigned short>(v42, a1 + 8, a3);
  v13 = (const WCHAR *)v42;
  if ( v42[3] > (PCWSTR)7 )
    v13 = v42[0];
  RtlInitUnicodeString(&v36, v13);
  v14 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v33 = 0;
  v39 = (HLOCAL (__stdcall *)(HLOCAL))&v33;
  KeyHandle = 0;
  v41 = 1;
  v15 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v39);
  if ( !v15 || v15 == -1073741772 )
  {
    memset(&v37, 0, sizeof(v37));
    v31 = 0;
    v16 = -1073741772;
    if ( v11 )
    {
      v37.Length = 48;
      v11 = 0;
      v37.RootDirectory = 0;
      v37.Attributes = 64;
      v37.ObjectName = &v36;
      *(_OWORD *)&v37.SecurityDescriptor = 0;
      v39 = (HLOCAL (__stdcall *)(HLOCAL))&v31;
      KeyHandle = 0;
      v41 = 1;
      v16 = NtOpenKey(&KeyHandle, 0x20019u, &v37);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v39);
      if ( v16 )
      {
        if ( v16 != -1073741772 )
        {
          if ( v16 < 0 )
          {
            v17 = (unsigned int)v16;
            v18 = 312;
LABEL_16:
            v14 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)v18,
                    (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
                    (const char *)v17,
                    v29);
LABEL_17:
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
            goto LABEL_44;
          }
          goto LABEL_43;
        }
      }
    }
    v19 = v11;
    if ( v15 == -1073741772 && v16 == -1073741772 )
      v19 = -1073741772;
    v34 = 0;
    v20 = (const WCHAR *)v44;
    if ( v44[3] > (PCWSTR)7 )
      v20 = v44[0];
    RtlInitUnicodeString(&v34, v20);
    v21 = (unsigned int)v11;
    v32 = v11;
    if ( !v19 )
    {
      v29 = v11;
      v22 = RtlQueryRegistryValueWithFallback(v33, v31, &v34, 0);
      v19 = v22;
      if ( v22 && v22 != -1073741772 && v22 != -2147483643 )
      {
        if ( v22 < 0 )
        {
          v17 = (unsigned int)v22;
          v18 = 346;
          goto LABEL_16;
        }
LABEL_43:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
        v14 = v11;
        goto LABEL_44;
      }
      v21 = v32;
    }
    v39 = LocalFree;
    KeyHandle = (void *)v11;
    if ( v19 == -1073741772 )
    {
      LOBYTE(v29) = v11;
      v23 = RegistryDataEntry::Create(v21, a4, a5, 3);
      std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(&v39, v23);
      v24 = KeyHandle;
      if ( !KeyHandle )
      {
        v25 = 357;
LABEL_33:
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
          (const char *)0x8007000ELL,
          v29);
LABEL_34:
        std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(&v39);
        goto LABEL_17;
      }
    }
    else
    {
      if ( a6 )
        v21 = (unsigned int)v11;
      LOBYTE(v29) = v11;
      v26 = RegistryDataEntry::Create(v21, a4, a5, 2);
      std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(&v39, v26);
      v24 = KeyHandle;
      if ( !KeyHandle )
      {
        v25 = 369;
        goto LABEL_33;
      }
      if ( !a6 )
      {
        v30 = (int)KeyHandle;
        v27 = RtlQueryRegistryValueWithFallback(v33, v31, &v34, v32);
        if ( v27 < 0 )
        {
          v14 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x17C,
                  (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
                  (const char *)(unsigned int)v27,
                  v30);
          goto LABEL_34;
        }
      }
    }
    KeyHandle = (void *)v11;
    std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(a7, v24);
    std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(&v39);
    goto LABEL_43;
  }
  if ( v15 < 0 )
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x124,
            (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
            (const char *)(unsigned int)v15,
            v29);
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
  std::wstring::_Tidy_deallocate(v42);
  std::wstring::_Tidy_deallocate(SourceString);
  std::wstring::_Tidy_deallocate(v44);
  return v14;
}

```

## disassembly

```asm
0x1800812ac  push    rbp
0x1800812ae  push    rbx
0x1800812af  push    rsi
0x1800812b0  push    rdi
0x1800812b1  push    r12
0x1800812b3  push    r13
0x1800812b5  push    r14
0x1800812b7  push    r15
0x1800812b9  lea     rbp, [rsp-78h]
0x1800812be  sub     rsp, 178h
0x1800812c5  mov     rax, cs:__security_cookie
0x1800812cc  xor     rax, rsp
0x1800812cf  mov     [rbp+0B0h+var_48], rax
0x1800812d3  mov     r12, r9
0x1800812d6  mov     rdi, r8
0x1800812d9  mov     rsi, rdx
0x1800812dc  mov     rbx, rcx
0x1800812df  mov     r15, [rbp+0B0h+arg_20]
0x1800812e6  mov     r13, [rbp+0B0h+arg_30]
0x1800812ed  mov     rdx, r15
0x1800812f0  lea     rcx, [rbp+0B0h+var_C8]
0x1800812f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800812f9  nop
0x1800812fa  lea     r8, [rbp+0B0h+var_C8]
0x1800812fe  lea     rdx, [rbp+0B0h+var_68]
0x180081302  mov     rcx, rbx
0x180081305  call    ?GetPathWithUserSid@RegistryStore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; RegistryStore::GetPathWithUserSid(std::wstring const &)
0x18008130a  nop
0x18008130b  lea     rcx, [rbp+0B0h+var_C8]
0x18008130f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180081314  or      r14, 0FFFFFFFFFFFFFFFFh
0x180081318  xor     eax, eax
0x18008131a  inc     r14
0x18008131d  cmp     [rdi+r14*2], ax
0x180081322  jnz     short loc_18008131A
0x180081324  xorps   xmm0, xmm0
0x180081327  movups  xmmword ptr [rsp+1B0h+DestinationString.Length], xmm0
0x18008132c  xorps   xmm1, xmm1
0x18008132f  movups  xmmword ptr [rsp+1B0h+var_138.Length], xmm1
0x180081334  mov     r8, rsi
0x180081337  lea     rdx, [rbx+8]
0x18008133b  lea     rcx, [rbp+0B0h+SourceString]
0x18008133f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180081344  nop
0x180081345  lea     rdx, [rbp+0B0h+SourceString]
0x180081349  cmp     [rbp+0B0h+var_70], 7
0x18008134e  cmova   rdx, [rbp+0B0h+SourceString]; SourceString
0x180081353  lea     rcx, [rsp+1B0h+DestinationString]; DestinationString
0x180081358  call    cs:__imp_RtlInitUnicodeString
0x18008135e  mov     r8, rdi
0x180081361  lea     rdx, [rbx+8]
0x180081365  lea     rcx, [rbp+0B0h+var_A8]
0x180081369  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18008136e  nop
0x18008136f  lea     rdx, [rbp+0B0h+var_A8]
0x180081373  cmp     [rbp+0B0h+var_90], 7
0x180081378  cmova   rdx, [rbp+0B0h+var_A8]; SourceString
0x18008137d  lea     rcx, [rsp+1B0h+var_138]; DestinationString
0x180081382  call    cs:__imp_RtlInitUnicodeString
0x180081388  xor     ebx, ebx
0x18008138a  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x180081392  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], 40h ; '@'
0x18008139a  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rbx
0x18008139e  lea     rax, [rsp+1B0h+DestinationString]
0x1800813a3  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x1800813a7  xorps   xmm0, xmm0
0x1800813aa  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800813af  mov     [rsp+1B0h+var_160], rbx
0x1800813b4  lea     rax, [rsp+1B0h+var_160]
0x1800813b9  mov     [rbp+0B0h+var_C8], rax
0x1800813bd  mov     [rbp+0B0h+KeyHandle], rbx
0x1800813c1  mov     [rbp+0B0h+var_B8], 1
0x1800813c5  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x1800813c9  mov     edx, 20019h; DesiredAccess
0x1800813ce  lea     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x1800813d2  call    cs:__imp_NtOpenKey
0x1800813d8  mov     esi, eax
0x1800813da  lea     rcx, [rbp+0B0h+var_C8]
0x1800813de  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800813e3  mov     eax, 0C0000034h
0x1800813e8  test    esi, esi
0x1800813ea  jz      short loc_18008141A
0x1800813ec  cmp     esi, eax
0x1800813ee  jz      short loc_18008141A
0x1800813f0  test    esi, esi
0x1800813f2  jns     loc_1800816AF
0x1800813f8  mov     rcx, [rbp+0B8h]; this
0x1800813ff  mov     r9d, esi; char *
0x180081402  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081409  mov     edx, 124h; void *
0x18008140e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180081413  mov     ebx, eax
0x180081415  jmp     loc_1800816AF
0x18008141a  xorps   xmm0, xmm0
0x18008141d  movups  xmmword ptr [rbp+0B0h+var_128.Length], xmm0
0x180081421  movups  xmmword ptr [rbp+0B0h+var_128.ObjectName], xmm0
0x180081425  movups  xmmword ptr [rbp+0B0h+var_128.SecurityDescriptor], xmm0
0x180081429  mov     [rsp+1B0h+var_170], rbx
0x18008142e  mov     edi, eax
0x180081430  test    r14, r14
0x180081433  jz      loc_1800814CC
0x180081439  mov     [rbp+0B0h+var_128.Length], 30h ; '0'
0x180081440  xor     r14d, r14d
0x180081443  mov     [rbp+0B0h+var_128.RootDirectory], r14
0x180081447  mov     [rbp+0B0h+var_128.Attributes], 40h ; '@'
0x18008144e  lea     rax, [rsp+1B0h+var_138]
0x180081453  mov     [rbp+0B0h+var_128.ObjectName], rax
0x180081457  movdqu  xmmword ptr [rbp+0B0h+var_128.SecurityDescriptor], xmm0
0x18008145c  lea     rax, [rsp+1B0h+var_170]
0x180081461  mov     [rbp+0B0h+var_C8], rax
0x180081465  mov     [rbp+0B0h+KeyHandle], r14
0x180081469  mov     [rbp+0B0h+var_B8], 1
0x18008146d  lea     r8, [rbp+0B0h+var_128]; ObjectAttributes
0x180081471  mov     edx, 20019h; DesiredAccess
0x180081476  lea     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x18008147a  call    cs:__imp_NtOpenKey
0x180081480  mov     edi, eax
0x180081482  lea     rcx, [rbp+0B0h+var_C8]
0x180081486  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18008148b  mov     eax, 0C0000034h
0x180081490  test    edi, edi
0x180081492  jz      short loc_1800814CC
0x180081494  cmp     edi, eax
0x180081496  jz      short loc_1800814CC
0x180081498  test    edi, edi
0x18008149a  jns     loc_1800816A2
0x1800814a0  mov     r9d, edi; char *
0x1800814a3  mov     edx, 138h; void *
0x1800814a8  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x1800814af  mov     rcx, [rbp+0B8h]; this
0x1800814b6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800814bb  mov     ebx, eax
0x1800814bd  lea     rcx, [rsp+1B0h+var_170]
0x1800814c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800814c7  jmp     loc_1800816AF
0x1800814cc  mov     ebx, r14d
0x1800814cf  cmp     esi, eax
0x1800814d1  jnz     short loc_1800814D8
0x1800814d3  cmp     edi, eax
0x1800814d5  cmovz   ebx, eax
0x1800814d8  xorps   xmm0, xmm0
0x1800814db  movups  xmmword ptr [rsp+1B0h+var_158.Length], xmm0
0x1800814e0  lea     rdx, [rbp+0B0h+var_68]
0x1800814e4  cmp     [rbp+0B0h+var_50], 7
0x1800814e9  cmova   rdx, [rbp+0B0h+var_68]; SourceString
0x1800814ee  lea     rcx, [rsp+1B0h+var_158]; DestinationString
0x1800814f3  call    cs:__imp_RtlInitUnicodeString
0x1800814f9  mov     ecx, r14d
0x1800814fc  mov     [rsp+1B0h+var_168], ecx
0x180081500  test    ebx, ebx
0x180081502  jnz     short loc_18008155D
0x180081504  lea     rax, [rsp+1B0h+var_168]
0x180081509  mov     [rsp+1B0h+var_180], rax
0x18008150e  mov     [rsp+1B0h+var_188], r14
0x180081513  mov     qword ptr [rsp+1B0h+var_190], r14
0x180081518  xor     r9d, r9d
0x18008151b  lea     r8, [rsp+1B0h+var_158]
0x180081520  mov     rdx, [rsp+1B0h+var_170]
0x180081525  mov     rcx, [rsp+1B0h+var_160]
0x18008152a  call    cs:__imp_RtlQueryRegistryValueWithFallback
0x180081530  mov     ebx, eax
0x180081532  test    eax, eax
0x180081534  jz      short loc_180081559
0x180081536  cmp     eax, 0C0000034h
0x18008153b  jz      short loc_180081559
0x18008153d  cmp     eax, 80000005h
0x180081542  jz      short loc_180081559
0x180081544  test    eax, eax
0x180081546  jns     loc_1800816A2
0x18008154c  mov     r9d, eax
0x18008154f  mov     edx, 15Ah
0x180081554  jmp     loc_1800814A8
0x180081559  mov     ecx, [rsp+1B0h+var_168]
0x18008155d  mov     rax, cs:__imp_LocalFree
0x180081564  mov     [rbp+0B0h+var_C8], rax
0x180081568  mov     [rbp+0B0h+KeyHandle], r14
0x18008156c  mov     r8, r15
0x18008156f  mov     rdx, r12
0x180081572  cmp     ebx, 0C0000034h
0x180081578  jnz     short loc_1800815DB
0x18008157a  mov     [rsp+1B0h+var_178], r14
0x18008157f  mov     byte ptr [rsp+1B0h+var_188], r14b
0x180081584  mov     byte ptr [rsp+1B0h+var_190], r14b; int
0x180081589  mov     r9d, 3
0x18008158f  call    ?Create@RegistryDataEntry@@SAPEAU1@KPEBG0W4SettingsRegistryAction@@_N2PEBX_K@Z; RegistryDataEntry::Create(ulong,ushort const *,ushort const *,SettingsRegistryAction,bool,bool,void const *,unsigned __int64)
0x180081594  mov     rdx, rax
0x180081597  lea     rcx, [rbp+0B0h+var_C8]
0x18008159b  call    ?reset@?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@QEAAXPEAURegistryDataEntry@@@Z; std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(RegistryDataEntry *)
0x1800815a0  mov     rbx, [rbp+0B0h+KeyHandle]
0x1800815a4  test    rbx, rbx
0x1800815a7  jnz     loc_180081689
0x1800815ad  mov     edx, 165h; void *
0x1800815b2  mov     ebx, 8007000Eh
0x1800815b7  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x1800815be  mov     r9d, ebx; char *
0x1800815c1  mov     rcx, [rbp+0B8h]; this
0x1800815c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800815cd  lea     rcx, [rbp+0B0h+var_C8]
0x1800815d1  call    ??1?$unique_ptr@URegistryData@@P6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(void)
0x1800815d6  jmp     loc_1800814BD
0x1800815db  mov     dil, [rbp+0B0h+arg_28]
0x1800815e2  test    dil, dil
0x1800815e5  cmovnz  ecx, r14d
0x1800815e9  mov     eax, ecx
0x1800815eb  mov     [rsp+1B0h+var_178], rax
0x1800815f0  mov     byte ptr [rsp+1B0h+var_188], dil
0x1800815f5  mov     byte ptr [rsp+1B0h+var_190], r14b
0x1800815fa  mov     r9d, 2
0x180081600  call    ?Create@RegistryDataEntry@@SAPEAU1@KPEBG0W4SettingsRegistryAction@@_N2PEBX_K@Z; RegistryDataEntry::Create(ulong,ushort const *,ushort const *,SettingsRegistryAction,bool,bool,void const *,unsigned __int64)
0x180081605  mov     rdx, rax
0x180081608  lea     rcx, [rbp+0B0h+var_C8]
0x18008160c  call    ?reset@?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@QEAAXPEAURegistryDataEntry@@@Z; std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(RegistryDataEntry *)
0x180081611  mov     rbx, [rbp+0B0h+KeyHandle]
0x180081615  test    rbx, rbx
0x180081618  jnz     short loc_180081621
0x18008161a  mov     edx, 171h
0x18008161f  jmp     short loc_1800815B2
0x180081621  test    dil, dil
0x180081624  jnz     short loc_180081689
0x180081626  mov     r8, [rbx+10h]
0x18008162a  add     r8, 2Ah ; '*'
0x18008162e  add     r8, [rbx+8]
0x180081632  add     r8, rbx
0x180081635  lea     rax, [rsp+1B0h+var_168]
0x18008163a  mov     [rsp+1B0h+var_180], rax
0x18008163f  mov     [rsp+1B0h+var_188], r8
0x180081644  mov     qword ptr [rsp+1B0h+var_190], rbx; int
0x180081649  mov     r9d, [rsp+1B0h+var_168]
0x18008164e  lea     r8, [rsp+1B0h+var_158]
0x180081653  mov     rdx, [rsp+1B0h+var_170]
0x180081658  mov     rcx, [rsp+1B0h+var_160]
0x18008165d  call    cs:__imp_RtlQueryRegistryValueWithFallback
0x180081663  test    eax, eax
0x180081665  jns     short loc_180081689
0x180081667  mov     rcx, [rbp+0B8h]; this
0x18008166e  mov     r9d, eax; char *
0x180081671  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180081678  mov     edx, 17Ch; void *
0x18008167d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180081682  mov     ebx, eax
0x180081684  jmp     loc_1800815CD
0x180081689  mov     [rbp+0B0h+KeyHandle], r14
0x18008168d  mov     rdx, rbx
0x180081690  mov     rcx, r13
0x180081693  call    ?reset@?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@QEAAXPEAURegistryDataEntry@@@Z; std::unique_ptr<RegistryDataEntry,void * (*)(void *)>::reset(RegistryDataEntry *)
0x180081698  lea     rcx, [rbp+0B0h+var_C8]
0x18008169c  call    ??1?$unique_ptr@URegistryData@@P6APEAXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<RegistryData,void * (*)(void *)>::~unique_ptr<RegistryData,void * (*)(void *)>(void)
0x1800816a1  nop
0x1800816a2  lea     rcx, [rsp+1B0h+var_170]
0x1800816a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800816ac  mov     ebx, r14d
0x1800816af  lea     rcx, [rsp+1B0h+var_160]
0x1800816b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800816b9  nop
0x1800816ba  lea     rcx, [rbp+0B0h+var_A8]
0x1800816be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800816c3  nop
0x1800816c4  lea     rcx, [rbp+0B0h+SourceString]
0x1800816c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800816cd  nop
0x1800816ce  lea     rcx, [rbp+0B0h+var_68]
0x1800816d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800816d7  mov     eax, ebx
0x1800816d9  mov     rcx, [rbp+0B0h+var_48]
0x1800816dd  xor     rcx, rsp; StackCookie
0x1800816e0  call    __security_check_cookie
0x1800816e5  add     rsp, 178h
0x1800816ec  pop     r15
0x1800816ee  pop     r14
0x1800816f0  pop     r13
0x1800816f2  pop     r12
0x1800816f4  pop     rdi
0x1800816f5  pop     rsi
0x1800816f6  pop     rbx
0x1800816f7  pop     rbp
0x1800816f8  retn
```
