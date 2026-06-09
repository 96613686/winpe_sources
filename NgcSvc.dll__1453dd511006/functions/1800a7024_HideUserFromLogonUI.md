# HideUserFromLogonUI

- ea: `0x1800a7024`
- end: `0x1800a73bc`
- name: `HideUserFromLogonUI`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a5e58`

## callees

- `0x180033350`
- `0x180033c84`
- `0x18004826c`
- `0x18005cee0`
- `0x18005dd44`
- `0x1800a588c`
- `0x1800a58bc`
- `0x1800a7024`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800a723b`
- `ntdll!RtlInitUnicodeString` at `0x1800a723b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800a70bd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800a70bd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800a70dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800a70dd`
- `SAMLIB!SamOpenUser` at `0x1800a72ec`
- `SAMLIB!SamOpenUser` at `0x1800a72ec`
- `SAMLIB!SamConnect` at `0x1800a71c4`
- `SAMLIB!SamConnect` at `0x1800a71c4`
- `SAMLIB!SamLookupNamesInDomain` at `0x1800a727e`
- `SAMLIB!SamLookupNamesInDomain` at `0x1800a727e`
- `SAMLIB!SamCloseHandle` at `0x1800a719d`
- `SAMLIB!SamCloseHandle` at `0x1800a71ef`
- `SAMLIB!SamCloseHandle` at `0x1800a72c0`
- `SAMLIB!SamCloseHandle` at `0x1800a719d`
- `SAMLIB!SamCloseHandle` at `0x1800a71ef`
- `SAMLIB!SamCloseHandle` at `0x1800a72c0`
- `SAMLIB!SamOpenDomain` at `0x1800a721c`
- `SAMLIB!SamOpenDomain` at `0x1800a721c`
- `SAMLIB!SamSetInformationUser` at `0x1800a7319`
- `SAMLIB!SamSetInformationUser` at `0x1800a7319`
- `SAMLIB!SamFreeMemory` at `0x1800a7121`
- `SAMLIB!SamFreeMemory` at `0x1800a7136`
- `SAMLIB!SamFreeMemory` at `0x1800a7163`
- `SAMLIB!SamFreeMemory` at `0x1800a7346`
- `SAMLIB!SamFreeMemory` at `0x1800a735b`
- `SAMLIB!SamFreeMemory` at `0x1800a7384`
- `SAMLIB!SamFreeMemory` at `0x1800a7121`
- `SAMLIB!SamFreeMemory` at `0x1800a7136`
- `SAMLIB!SamFreeMemory` at `0x1800a7163`
- `SAMLIB!SamFreeMemory` at `0x1800a7346`
- `SAMLIB!SamFreeMemory` at `0x1800a735b`
- `SAMLIB!SamFreeMemory` at `0x1800a7384`

## string_xrefs

- `0x1800a70fa`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 HideUserFromLogonUI()
{
  NTSTATUS v0; // eax
  __int64 v1; // rdx
  unsigned __int64 v2; // r9
  unsigned int v3; // ebx
  unsigned int *v4; // rcx
  __int64 v5; // rcx
  PVOID v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rbx
  int v9; // ebx
  __int64 v10; // rbx
  unsigned int *v11; // rcx
  __int64 v12; // rcx
  PVOID v13; // rcx
  __int64 *v15; // [rsp+20h] [rbp-E0h]
  unsigned int *v16; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Buffer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  unsigned int **v25; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-58h] BYREF
  char v27; // [rsp+B0h] [rbp-50h]
  __int64 *v28; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-40h] BYREF
  char v30; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v32[10]; // [rsp+E0h] [rbp-20h] BYREF
  char v33; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  Buffer = 0;
  v21 = 0;
  v19 = 0;
  v18 = 0;
  v16 = 0;
  DestinationString = 0;
  v20 = 0;
  memset_0(v32, 0, 0xA8u);
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  PolicyHandle = 0;
  v0 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v0 < 0 )
  {
    v1 = 1799;
LABEL_5:
    v2 = (unsigned int)v0;
LABEL_6:
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v1,
           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
           (const char *)v2,
           (int)v15);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
    v4 = v16;
    v16 = 0;
    if ( v4 )
      SamFreeMemory();
    v5 = v18;
    v18 = 0;
    if ( v5 )
      SamFreeMemory();
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
    v6 = Buffer;
    Buffer = 0;
    if ( v6 )
      SamFreeMemory();
    goto LABEL_35;
  }
  v0 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v0 < 0 )
  {
    v1 = 1804;
    goto LABEL_5;
  }
  ObjectAttributes.Length = 48;
  v7 = v21;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v21 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v22);
    SamCloseHandle(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
  }
  v21 = 0;
  v0 = SamConnect(0, &v21, 32, &ObjectAttributes);
  if ( v0 < 0 )
  {
    v1 = 1811;
    goto LABEL_5;
  }
  v8 = v19;
  if ( v19 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v22);
    SamCloseHandle(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
  }
  v19 = 0;
  v0 = SamOpenDomain(v21, 0x2000000, *((_QWORD *)Buffer + 2), &v19);
  if ( v0 < 0 )
  {
    v1 = 1817;
    goto LABEL_5;
  }
  RtlInitUnicodeString(&DestinationString, L"CDFAccount");
  v28 = &v18;
  v29 = 0;
  v25 = &v16;
  v30 = 1;
  v15 = &v29;
  v26 = 0;
  v27 = 1;
  v9 = SamLookupNamesInDomain(v19, 1, &DestinationString, &v26);
  wil::details::out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>(&v25);
  wil::details::out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned long,wil::function_deleter<long (*)(void *),&long SamFreeMemory(void *)>>>(&v28);
  if ( v9 < 0 )
  {
    v2 = (unsigned int)v9;
    v1 = 1825;
    goto LABEL_6;
  }
  v10 = v20;
  if ( v20 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v22);
    SamCloseHandle(v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
  }
  v20 = 0;
  v0 = SamOpenUser(v19, 0x2000000, *v16, &v20);
  if ( v0 < 0 )
  {
    v1 = 1831;
    goto LABEL_5;
  }
  v32[0] = 0x4000;
  v33 = 1;
  v0 = SamSetInformationUser(v20, 28, v32);
  if ( v0 < 0 )
  {
    v1 = 1838;
    goto LABEL_5;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
  v11 = v16;
  v16 = 0;
  if ( v11 )
    SamFreeMemory();
  v12 = v18;
  v18 = 0;
  if ( v12 )
    SamFreeMemory();
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
  v13 = Buffer;
  Buffer = 0;
  if ( v13 )
    SamFreeMemory();
  v3 = 0;
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v3;
}

```

## disassembly

```asm
0x1800a7024  mov     [rsp-8+arg_0], rbx
0x1800a7029  mov     [rsp-8+arg_8], rdi
0x1800a702e  push    rbp
0x1800a702f  lea     rbp, [rsp-0A0h]
0x1800a7037  sub     rsp, 1A0h
0x1800a703e  mov     rax, cs:__security_cookie
0x1800a7045  xor     rax, rsp
0x1800a7048  mov     [rbp+0A0h+var_10], rax
0x1800a704f  xor     edi, edi
0x1800a7051  mov     qword ptr [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1800a705a  xorps   xmm0, xmm0
0x1800a705d  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], rdi
0x1800a7061  xor     edx, edx; Val
0x1800a7063  mov     [rsp+1A0h+Buffer], rdi
0x1800a7068  mov     r8d, 0A8h; Size
0x1800a706e  mov     [rsp+1A0h+var_148], rdi
0x1800a7073  lea     rcx, [rbp+0A0h+var_C0]; void *
0x1800a7077  mov     [rsp+1A0h+var_158], rdi
0x1800a707c  mov     [rsp+1A0h+var_160], rdi
0x1800a7081  mov     [rsp+1A0h+var_170], rdi
0x1800a7086  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1800a708a  mov     [rsp+1A0h+var_150], rdi
0x1800a708f  call    memset_0
0x1800a7094  xorps   xmm0, xmm0
0x1800a7097  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rdi
0x1800a709c  lea     r9, [rsp+1A0h+PolicyHandle]; PolicyHandle
0x1800a70a1  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rdi
0x1800a70a5  lea     r8d, [rdi+1]; DesiredAccess
0x1800a70a9  mov     [rsp+1A0h+PolicyHandle], rdi
0x1800a70ae  lea     rdx, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x1800a70b3  xor     ecx, ecx; SystemName
0x1800a70b5  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a70ba  lea     ebx, [rdi+30h]
0x1800a70bd  call    cs:__imp_LsaOpenPolicy
0x1800a70c3  test    eax, eax
0x1800a70c5  jns     short loc_1800A70CE
0x1800a70c7  mov     edx, 707h
0x1800a70cc  jmp     short loc_1800A70F0
0x1800a70ce  mov     rcx, [rsp+1A0h+PolicyHandle]; PolicyHandle
0x1800a70d3  lea     r8, [rsp+1A0h+Buffer]; Buffer
0x1800a70d8  mov     edx, 5; InformationClass
0x1800a70dd  call    cs:__imp_LsaQueryInformationPolicy
0x1800a70e3  test    eax, eax
0x1800a70e5  jns     loc_1800A716E
0x1800a70eb  mov     edx, 70Ch; void *
0x1800a70f0  mov     r9d, eax; char *
0x1800a70f3  mov     rcx, [rbp+0A8h]; this
0x1800a70fa  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a7101  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a7106  lea     rcx, [rsp+1A0h+var_150]
0x1800a710b  mov     ebx, eax
0x1800a710d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a7112  mov     rcx, [rsp+1A0h+var_170]
0x1800a7117  mov     [rsp+1A0h+var_170], rdi
0x1800a711c  test    rcx, rcx
0x1800a711f  jz      short loc_1800A7127
0x1800a7121  call    cs:__imp_SamFreeMemory
0x1800a7127  mov     rcx, [rsp+1A0h+var_160]
0x1800a712c  mov     [rsp+1A0h+var_160], rdi
0x1800a7131  test    rcx, rcx
0x1800a7134  jz      short loc_1800A713C
0x1800a7136  call    cs:__imp_SamFreeMemory
0x1800a713c  lea     rcx, [rsp+1A0h+var_158]
0x1800a7141  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a7146  lea     rcx, [rsp+1A0h+var_148]
0x1800a714b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a7150  mov     rcx, [rsp+1A0h+Buffer]
0x1800a7155  mov     [rsp+1A0h+Buffer], rdi
0x1800a715a  test    rcx, rcx
0x1800a715d  jz      loc_1800A738C
0x1800a7163  call    cs:__imp_SamFreeMemory
0x1800a7169  jmp     loc_1800A738C
0x1800a716e  mov     [rsp+1A0h+ObjectAttributes.Length], ebx
0x1800a7172  xorps   xmm0, xmm0
0x1800a7175  mov     rbx, [rsp+1A0h+var_148]
0x1800a717a  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rdi
0x1800a717f  mov     [rbp+0A0h+ObjectAttributes.Attributes], edi
0x1800a7182  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rdi
0x1800a7186  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a718b  test    rbx, rbx
0x1800a718e  jz      short loc_1800A71AD
0x1800a7190  lea     rcx, [rsp+1A0h+var_140]; this
0x1800a7195  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a719a  mov     rcx, rbx
0x1800a719d  call    cs:__imp_SamCloseHandle
0x1800a71a3  lea     rcx, [rsp+1A0h+var_140]; this
0x1800a71a8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a71ad  lea     r9, [rsp+1A0h+ObjectAttributes]
0x1800a71b2  mov     [rsp+1A0h+var_148], rdi
0x1800a71b7  mov     r8d, 20h ; ' '
0x1800a71bd  lea     rdx, [rsp+1A0h+var_148]
0x1800a71c2  xor     ecx, ecx
0x1800a71c4  call    cs:__imp_SamConnect
0x1800a71ca  test    eax, eax
0x1800a71cc  jns     short loc_1800A71D8
0x1800a71ce  mov     edx, 713h
0x1800a71d3  jmp     loc_1800A70F0
0x1800a71d8  mov     rbx, [rsp+1A0h+var_158]
0x1800a71dd  test    rbx, rbx
0x1800a71e0  jz      short loc_1800A71FF
0x1800a71e2  lea     rcx, [rsp+1A0h+var_140]; this
0x1800a71e7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a71ec  mov     rcx, rbx
0x1800a71ef  call    cs:__imp_SamCloseHandle
0x1800a71f5  lea     rcx, [rsp+1A0h+var_140]; this
0x1800a71fa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a71ff  mov     r8, [rsp+1A0h+Buffer]
0x1800a7204  lea     r9, [rsp+1A0h+var_158]
0x1800a7209  mov     rcx, [rsp+1A0h+var_148]
0x1800a720e  mov     edx, 2000000h
0x1800a7213  mov     [rsp+1A0h+var_158], rdi
0x1800a7218  mov     r8, [r8+10h]
0x1800a721c  call    cs:__imp_SamOpenDomain
0x1800a7222  test    eax, eax
0x1800a7224  jns     short loc_1800A7230
0x1800a7226  mov     edx, 719h
0x1800a722b  jmp     loc_1800A70F0
0x1800a7230  lea     rdx, AccountName; "CDFAccount"
0x1800a7237  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1800a723b  call    cs:__imp_RtlInitUnicodeString
0x1800a7241  mov     rcx, [rsp+1A0h+var_158]
0x1800a7246  lea     rax, [rsp+1A0h+var_160]
0x1800a724b  mov     [rbp+0A0h+var_E8], rax
0x1800a724f  lea     r9, [rbp+0A0h+var_F8]
0x1800a7253  lea     rax, [rsp+1A0h+var_170]
0x1800a7258  mov     [rbp+0A0h+var_E0], rdi
0x1800a725c  mov     [rbp+0A0h+var_100], rax
0x1800a7260  lea     r8, [rbp+0A0h+DestinationString]
0x1800a7264  lea     rax, [rbp+0A0h+var_E0]
0x1800a7268  mov     [rbp+0A0h+var_D8], 1
0x1800a726c  mov     edx, 1
0x1800a7271  mov     [rsp+1A0h+var_180], rax
0x1800a7276  mov     [rbp+0A0h+var_F8], rdi
0x1800a727a  mov     [rbp+0A0h+var_F0], 1
0x1800a727e  call    cs:__imp_SamLookupNamesInDomain
0x1800a7284  lea     rcx, [rbp+0A0h+var_100]
0x1800a7288  mov     ebx, eax
0x1800a728a  call    ??1?$out_param_t@V?$unique_ptr@KU?$function_deleter@P6AJPEAX@Z$1?SamFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>(void)
0x1800a728f  lea     rcx, [rbp+0A0h+var_E8]
0x1800a7293  call    ??1?$out_param_t@V?$unique_ptr@KU?$function_deleter@P6AJPEAX@Z$1?SamFreeMemory@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<ulong,wil::function_deleter<long (*)(void *),&SamFreeMemory(void *)>>>(void)
0x1800a7298  test    ebx, ebx
0x1800a729a  jns     short loc_1800A72A9
0x1800a729c  mov     r9d, ebx
0x1800a729f  mov     edx, 721h
0x1800a72a4  jmp     loc_1800A70F3
0x1800a72a9  mov     rbx, [rsp+1A0h+var_150]
0x1800a72ae  test    rbx, rbx
0x1800a72b1  jz      short loc_1800A72D0
0x1800a72b3  lea     rcx, [rsp+1A0h+var_140]; this
0x1800a72b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a72bd  mov     rcx, rbx
0x1800a72c0  call    cs:__imp_SamCloseHandle
0x1800a72c6  lea     rcx, [rsp+1A0h+var_140]; this
0x1800a72cb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a72d0  mov     r8, [rsp+1A0h+var_170]
0x1800a72d5  lea     r9, [rsp+1A0h+var_150]
0x1800a72da  mov     rcx, [rsp+1A0h+var_158]
0x1800a72df  mov     edx, 2000000h
0x1800a72e4  mov     [rsp+1A0h+var_150], rdi
0x1800a72e9  mov     r8d, [r8]
0x1800a72ec  call    cs:__imp_SamOpenUser
0x1800a72f2  test    eax, eax
0x1800a72f4  jns     short loc_1800A7300
0x1800a72f6  mov     edx, 727h
0x1800a72fb  jmp     loc_1800A70F0
0x1800a7300  mov     rcx, [rsp+1A0h+var_150]
0x1800a7305  lea     r8, [rbp+0A0h+var_C0]
0x1800a7309  mov     edx, 1Ch
0x1800a730e  mov     [rbp+0A0h+var_C0], 4000h
0x1800a7315  mov     [rbp+0A0h+var_98], 1
0x1800a7319  call    cs:__imp_SamSetInformationUser
0x1800a731f  test    eax, eax
0x1800a7321  jns     short loc_1800A732D
0x1800a7323  mov     edx, 72Eh
0x1800a7328  jmp     loc_1800A70F0
0x1800a732d  lea     rcx, [rsp+1A0h+var_150]
0x1800a7332  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a7337  mov     rcx, [rsp+1A0h+var_170]
0x1800a733c  mov     [rsp+1A0h+var_170], rdi
0x1800a7341  test    rcx, rcx
0x1800a7344  jz      short loc_1800A734C
0x1800a7346  call    cs:__imp_SamFreeMemory
0x1800a734c  mov     rcx, [rsp+1A0h+var_160]
0x1800a7351  mov     [rsp+1A0h+var_160], rdi
0x1800a7356  test    rcx, rcx
0x1800a7359  jz      short loc_1800A7361
0x1800a735b  call    cs:__imp_SamFreeMemory
0x1800a7361  lea     rcx, [rsp+1A0h+var_158]
0x1800a7366  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a736b  lea     rcx, [rsp+1A0h+var_148]
0x1800a7370  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a7375  mov     rcx, [rsp+1A0h+Buffer]
0x1800a737a  mov     [rsp+1A0h+Buffer], rdi
0x1800a737f  test    rcx, rcx
0x1800a7382  jz      short loc_1800A738A
0x1800a7384  call    cs:__imp_SamFreeMemory
0x1800a738a  mov     ebx, edi
0x1800a738c  lea     rcx, [rsp+1A0h+PolicyHandle]
0x1800a7391  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?SamCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&SamCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a7396  mov     eax, ebx
0x1800a7398  mov     rcx, [rbp+0A0h+var_10]
0x1800a739f  xor     rcx, rsp; StackCookie
0x1800a73a2  call    __security_check_cookie
0x1800a73a7  lea     r11, [rsp+1A0h+var_s0]
0x1800a73af  mov     rbx, [r11+10h]
0x1800a73b3  mov     rdi, [r11+18h]
0x1800a73b7  mov     rsp, r11
0x1800a73ba  pop     rbp
0x1800a73bb  retn
```
