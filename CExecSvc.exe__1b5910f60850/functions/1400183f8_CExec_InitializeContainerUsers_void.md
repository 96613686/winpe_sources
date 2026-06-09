# CExec::InitializeContainerUsers(void)

- ea: `0x1400183f8`
- end: `0x1400186d7`
- name: `?InitializeContainerUsers@CExec@@YAXXZ`
- size: `735`
- prototype: `void __fastcall(CExec *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140010b20`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140008160`
- `0x140014f3c`
- `0x140015410`
- `0x14001611c`
- `0x140016210`
- `0x1400183f8`
- `0x14001a950`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018654`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018654`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018676`
- `ntdll!RtlInitUnicodeString` at `0x1400184fa`
- `ntdll!RtlInitUnicodeString` at `0x14001852e`
- `ntdll!RtlInitUnicodeString` at `0x14001853f`
- `ntdll!RtlInitUnicodeString` at `0x14001855b`
- `ntdll!RtlInitUnicodeString` at `0x14001856f`
- `ntdll!RtlInitUnicodeString` at `0x1400184fa`
- `ntdll!RtlInitUnicodeString` at `0x14001852e`
- `ntdll!RtlInitUnicodeString` at `0x14001853f`
- `ntdll!RtlInitUnicodeString` at `0x14001855b`
- `ntdll!RtlInitUnicodeString` at `0x14001856f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1400185ba`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1400185ba`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14001860d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14001860d`

## string_xrefs

- `0x1400186c5`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400185d7`: `SeServiceLogonRight`

## pseudocode

```c
void __fastcall CExec::InitializeContainerUsers(CExec *this)
{
  unsigned int v1; // r8d
  unsigned int v2; // r8d
  unsigned int v3; // eax
  NTSTATUS v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  _SID_IDENTIFIER_AUTHORITY v7; // [rsp+30h] [rbp-D0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v8; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v9; // [rsp+40h] [rbp-C0h]
  PVOID PolicyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[32]; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v14[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v15[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v16[32]; // [rsp+E0h] [rbp-20h] BYREF
  HLOCAL v17[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v18[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v19[32]; // [rsp+130h] [rbp+30h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES DestinationString; // [rsp+150h] [rbp+50h] BYREF
  struct _UNICODE_STRING v21; // [rsp+180h] [rbp+80h] BYREF
  struct _UNICODE_STRING v22; // [rsp+190h] [rbp+90h] BYREF
  HLOCAL v23; // [rsp+1A0h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  memset_0(v17, 0, 0x50u);
  *(_DWORD *)v7.Value = 0;
  *(_WORD *)&v7.Value[4] = 1280;
  Vml::VmSid::VmSid((Vml::VmSid *)v17, &v7, 1u, 93);
  memset_0(v14, 0, 0x50u);
  *(_DWORD *)v8.Value = 0;
  *(_WORD *)&v8.Value[4] = 1280;
  Vml::VmSid::VmSid((Vml::VmSid *)v14, &v8, 3u, 93, 2, 1);
  memset_0(hMem, 0, 0x50u);
  *(_DWORD *)v7.Value = 0;
  *(_WORD *)&v7.Value[4] = 1280;
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, &v7, 3u, 93);
  memset(&DestinationString, 0, sizeof(DestinationString));
  RtlInitUnicodeString((PUNICODE_STRING)&DestinationString, L"User Manager");
  DestinationString.SecurityDescriptor = v17[0];
  CExec::AddLsaMappings((CExec *)&DestinationString, (struct _LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *)1, v1);
  memset_0(&DestinationString, 0, 0x60u);
  RtlInitUnicodeString((PUNICODE_STRING)&DestinationString, L"User Manager");
  RtlInitUnicodeString((PUNICODE_STRING)&DestinationString.ObjectName, L"ContainerAdministrator");
  DestinationString.SecurityDescriptor = v14[0];
  RtlInitUnicodeString(&v21, L"User Manager");
  RtlInitUnicodeString(&v22, L"ContainerUser");
  v23 = hMem[0];
  CExec::AddLsaMappings((CExec *)&DestinationString, (struct _LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *)2, v2);
  PolicyHandle[0] = 0;
  v9 = 0;
  memset(&DestinationString, 0, sizeof(DestinationString));
  v3 = LsaOpenPolicy(0, &DestinationString, 0x810u, PolicyHandle);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -1073741790 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x1C24,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v3,
      2);
  Vml::VmLsaPolicy::AddAccountRight((Vml::VmLsaPolicy *)PolicyHandle, v14[0], L"SeServiceLogonRight");
  Vml::VmLsaPolicy::AddAccountRight((Vml::VmLsaPolicy *)PolicyHandle, hMem[0], L"SeInteractiveLogonRight");
  if ( PolicyHandle[0] )
  {
    v4 = LsaClose(PolicyHandle[0]);
    if ( v4 < 0 )
      wil::details::in1diag3::_FailFast_NtStatus(retaddr, v5, v6, (const char *)(unsigned int)v4, 2);
    PolicyHandle[0] = 0;
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  std::wstring::~wstring(v13);
  std::wstring::~wstring(v12);
  if ( v14[0] )
    LocalFree(v14[0]);
  std::wstring::~wstring(v16);
  std::wstring::~wstring(v15);
  if ( v17[0] )
    LocalFree(v17[0]);
  std::wstring::~wstring(v19);
  std::wstring::~wstring(v18);
}

```

## disassembly

```asm
0x1400183f8  mov     [rsp-8+arg_0], rsi
0x1400183fd  mov     [rsp-8+arg_8], r12
0x140018402  push    rbp
0x140018403  lea     rbp, [rsp-0C0h]
0x14001840b  sub     rsp, 1C0h
0x140018412  mov     rax, cs:__security_cookie
0x140018419  xor     rax, rsp
0x14001841c  mov     [rbp+0C0h+var_10], rax
0x140018423  mov     esi, 50h ; 'P'
0x140018428  mov     r8d, esi; Size
0x14001842b  xor     edx, edx; Val
0x14001842d  lea     rcx, [rbp+0C0h+var_C0]; void *
0x140018431  call    memset_0
0x140018436  xor     r12d, r12d
0x140018439  mov     dword ptr [rsp+1C0h+var_190.Value], r12d
0x14001843e  mov     word ptr [rsp+1C0h+var_190.Value+4], 500h
0x140018445  lea     r9d, [rsi+0Dh]
0x140018449  lea     r8d, [rsi-4Fh]; unsigned __int8
0x14001844d  lea     rdx, [rsp+1C0h+var_190]; struct _SID_IDENTIFIER_AUTHORITY *
0x140018452  lea     rcx, [rbp+0C0h+var_C0]; this
0x140018456  call    ??0VmSid@Vml@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Vml::VmSid::VmSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x14001845b  nop
0x14001845c  mov     r8d, esi; Size
0x14001845f  xor     edx, edx; Val
0x140018461  lea     rcx, [rbp+0C0h+var_110]; void *
0x140018465  call    memset_0
0x14001846a  mov     dword ptr [rsp+1C0h+var_188.Value], r12d
0x14001846f  mov     word ptr [rsp+1C0h+var_188.Value+4], 500h
0x140018476  mov     [rsp+1C0h+var_198], 1
0x14001847e  mov     [rsp+1C0h+var_1A0], 2
0x140018486  lea     r9d, [rsi+0Dh]
0x14001848a  lea     r8d, [rsi-4Dh]; unsigned __int8
0x14001848e  lea     rdx, [rsp+1C0h+var_188]; struct _SID_IDENTIFIER_AUTHORITY *
0x140018493  lea     rcx, [rbp+0C0h+var_110]; this
0x140018497  call    ??0VmSid@Vml@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Vml::VmSid::VmSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x14001849c  nop
0x14001849d  mov     r8d, esi; Size
0x1400184a0  xor     edx, edx; Val
0x1400184a2  lea     rcx, [rsp+1C0h+hMem]; void *
0x1400184a7  call    memset_0
0x1400184ac  mov     dword ptr [rsp+1C0h+var_190.Value], r12d
0x1400184b1  mov     word ptr [rsp+1C0h+var_190.Value+4], 500h
0x1400184b8  mov     [rsp+1C0h+var_198], 2
0x1400184c0  mov     [rsp+1C0h+var_1A0], 2; int
0x1400184c8  lea     r9d, [rsi+0Dh]
0x1400184cc  lea     r8d, [rsi-4Dh]; unsigned __int8
0x1400184d0  lea     rdx, [rsp+1C0h+var_190]; struct _SID_IDENTIFIER_AUTHORITY *
0x1400184d5  lea     rcx, [rsp+1C0h+hMem]; this
0x1400184da  call    ??0VmSid@Vml@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Vml::VmSid::VmSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x1400184df  nop
0x1400184e0  xorps   xmm0, xmm0
0x1400184e3  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x1400184e7  movups  xmmword ptr [rbp+0C0h+var_60.Length], xmm0
0x1400184eb  movups  [rbp+0C0h+var_50], xmm0
0x1400184ef  lea     rdx, SourceString; "User Manager"
0x1400184f6  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x1400184fa  call    cs:__imp_RtlInitUnicodeString
0x140018500  mov     rax, [rbp+0C0h+var_C0]
0x140018504  mov     qword ptr [rbp+0C0h+var_50], rax
0x140018508  lea     edx, [rsi-4Fh]; struct _LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *
0x14001850b  lea     rcx, [rbp+0C0h+DestinationString]; this
0x14001850f  call    ?AddLsaMappings@CExec@@YAXPEAU_LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT@@K@Z; CExec::AddLsaMappings(_LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *,ulong)
0x140018514  xor     edx, edx; Val
0x140018516  lea     r8d, [rsi+10h]; Size
0x14001851a  lea     rcx, [rbp+0C0h+DestinationString]; void *
0x14001851e  call    memset_0
0x140018523  lea     rdx, SourceString; "User Manager"
0x14001852a  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x14001852e  call    cs:__imp_RtlInitUnicodeString
0x140018534  lea     rdx, aContaineradmin; "ContainerAdministrator"
0x14001853b  lea     rcx, [rbp+0C0h+var_60]; DestinationString
0x14001853f  call    cs:__imp_RtlInitUnicodeString
0x140018545  mov     rax, [rbp+0C0h+var_110]
0x140018549  mov     qword ptr [rbp+0C0h+var_50], rax
0x14001854d  lea     rdx, SourceString; "User Manager"
0x140018554  lea     rcx, [rbp+0C0h+var_40]; DestinationString
0x14001855b  call    cs:__imp_RtlInitUnicodeString
0x140018561  lea     rdx, aContaineruser; "ContainerUser"
0x140018568  lea     rcx, [rbp+0C0h+var_30]; DestinationString
0x14001856f  call    cs:__imp_RtlInitUnicodeString
0x140018575  mov     rax, [rsp+1C0h+hMem]
0x14001857a  mov     [rbp+0C0h+var_20], rax
0x140018581  lea     edx, [rsi-4Eh]; struct _LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *
0x140018584  lea     rcx, [rbp+0C0h+DestinationString]; this
0x140018588  call    ?AddLsaMappings@CExec@@YAXPEAU_LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT@@K@Z; CExec::AddLsaMappings(_LSA_SID_NAME_MAPPING_OPERATION_ADD_INPUT *,ulong)
0x14001858d  mov     [rsp+1C0h+PolicyHandle], r12
0x140018592  xorps   xmm0, xmm0
0x140018595  movups  [rsp+1C0h+var_180], xmm0
0x14001859a  xorps   xmm1, xmm1
0x14001859d  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x1400185a1  movups  xmmword ptr [rbp+0C0h+var_60.Length], xmm1
0x1400185a5  movups  [rbp+0C0h+var_50], xmm1
0x1400185a9  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x1400185ae  mov     r8d, 810h; DesiredAccess
0x1400185b4  lea     rdx, [rbp+0C0h+DestinationString]; ObjectAttributes
0x1400185b8  xor     ecx, ecx; SystemName
0x1400185ba  call    cs:__imp_LsaOpenPolicy
0x1400185c0  mov     edx, 80000000h
0x1400185c5  lea     ecx, [rax+rdx]
0x1400185c8  test    edx, ecx
0x1400185ca  jnz     short loc_1400185D7
0x1400185cc  cmp     eax, 0C0000022h
0x1400185d1  jnz     loc_1400186BB
0x1400185d7  lea     r8, aSeservicelogon; "SeServiceLogonRight"
0x1400185de  mov     rdx, [rbp+0C0h+var_110]; void *
0x1400185e2  lea     rcx, [rsp+1C0h+PolicyHandle]; this
0x1400185e7  call    ?AddAccountRight@VmLsaPolicy@Vml@@QEAAXPEAXPEBG@Z; Vml::VmLsaPolicy::AddAccountRight(void *,ushort const *)
0x1400185ec  lea     r8, aSeinteractivel; "SeInteractiveLogonRight"
0x1400185f3  mov     rdx, [rsp+1C0h+hMem]; void *
0x1400185f8  lea     rcx, [rsp+1C0h+PolicyHandle]; this
0x1400185fd  call    ?AddAccountRight@VmLsaPolicy@Vml@@QEAAXPEAXPEBG@Z; Vml::VmLsaPolicy::AddAccountRight(void *,ushort const *)
0x140018602  nop
0x140018603  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x140018608  test    rcx, rcx
0x14001860b  jz      short loc_140018627
0x14001860d  call    cs:__imp_LsaClose
0x140018613  mov     rcx, [rbp+0C8h]; this
0x14001861a  test    eax, eax
0x14001861c  js      loc_1400186B2
0x140018622  mov     [rsp+1C0h+PolicyHandle], r12
0x140018627  mov     rcx, [rsp+1C0h+hMem]; hMem
0x14001862c  test    rcx, rcx
0x14001862f  jz      short loc_140018637
0x140018631  call    cs:__imp_LocalFree
0x140018637  lea     rcx, [rbp+0C0h+var_130]
0x14001863b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018640  lea     rcx, [rsp+1C0h+var_150]
0x140018645  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001864a  nop
0x14001864b  mov     rcx, [rbp+0C0h+var_110]; hMem
0x14001864f  test    rcx, rcx
0x140018652  jz      short loc_14001865A
0x140018654  call    cs:__imp_LocalFree
0x14001865a  lea     rcx, [rbp+0C0h+var_E0]
0x14001865e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018663  lea     rcx, [rbp+0C0h+var_100]
0x140018667  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001866c  nop
0x14001866d  mov     rcx, [rbp+0C0h+var_C0]; hMem
0x140018671  test    rcx, rcx
0x140018674  jz      short loc_14001867C
0x140018676  call    cs:__imp_LocalFree
0x14001867c  lea     rcx, [rbp+0C0h+var_90]
0x140018680  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018685  lea     rcx, [rbp+0C0h+var_B0]
0x140018689  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001868e  mov     rcx, [rbp+0C0h+var_10]
0x140018695  xor     rcx, rsp; StackCookie
0x140018698  call    __security_check_cookie
0x14001869d  lea     r11, [rsp+1C0h+var_s0]
0x1400186a5  mov     rsi, [r11+10h]
0x1400186a9  mov     r12, [r11+18h]
0x1400186ad  mov     rsp, r11
0x1400186b0  pop     rbp
0x1400186b1  retn
0x1400186b2  mov     r9d, eax; char *
0x1400186b5  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x1400186bb  mov     rcx, [rbp+0C8h]; this
0x1400186c2  mov     r9d, eax; char *
0x1400186c5  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400186cc  mov     edx, 1C24h; void *
0x1400186d1  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
