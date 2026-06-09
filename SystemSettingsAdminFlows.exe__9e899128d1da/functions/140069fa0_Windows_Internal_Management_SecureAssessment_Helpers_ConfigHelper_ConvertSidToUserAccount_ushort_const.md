# Windows::Internal::Management::SecureAssessment::Helpers::ConfigHelper::ConvertSidToUserAccount(ushort const *)

- ea: `0x140069fa0`
- end: `0x14006a190`
- name: `?ConvertSidToUserAccount@ConfigHelper@Helpers@SecureAssessment@Management@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14006a198`

## callees

- `0x14000c214`
- `0x14000d894`
- `0x14002a2c0`
- `0x14002a2e0`
- `0x14002ae30`
- `0x14002bc78`
- `0x140055c64`
- `0x140069f04`
- `0x140069fa0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x14006a097`
- `KERNEL32!LocalAlloc` at `0x14006a0c9`
- `KERNEL32!LocalAlloc` at `0x14006a097`
- `KERNEL32!LocalAlloc` at `0x14006a0c9`
- `KERNEL32!GetLastError` at `0x14006a061`
- `KERNEL32!GetLastError` at `0x14006a061`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14006a057`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14006a115`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14006a057`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x14006a115`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140069ffa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140069ffa`

## string_xrefs

- `0x140069fd9`: `admin\edu\secureassessment\common\inc\ConfigHelper.h`
- `0x14006a008`: `admin\edu\secureassessment\common\inc\ConfigHelper.h`
- `0x14006a076`: `admin\edu\secureassessment\common\inc\ConfigHelper.h`
- `0x14006a0ad`: `admin\edu\secureassessment\common\inc\ConfigHelper.h`
- `0x14006a0df`: `admin\edu\secureassessment\common\inc\ConfigHelper.h`
- `0x14006a123`: `admin\edu\secureassessment\common\inc\ConfigHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Management::SecureAssessment::Helpers::ConfigHelper::ConvertSidToUserAccount(
        __int64 a1,
        __int64 a2)
{
  const WCHAR *v3; // r8
  char v4; // bl
  __int64 v5; // rdx
  const char *v6; // r9
  const char *v7; // r9
  WCHAR *v8; // rdi
  const char *v9; // r9
  WCHAR *v10; // rbx
  const char *v11; // r9
  const char *v12; // r9
  __int64 v13; // rax
  int ReferencedDomainName; // [rsp+20h] [rbp-48h]
  PSID Sid; // [rsp+48h] [rbp-20h] BYREF
  WCHAR *v17; // [rsp+50h] [rbp-18h] BYREF
  WCHAR *v18; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp+38h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A8h] [rbp+40h] BYREF

  std::wstring::wstring(a1, a2);
  v4 = 1;
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"admin\\edu\\secureassessment\\common\\inc\\ConfigHelper.h",
      (const char *)0x80070057LL,
      ReferencedDomainName);
  Sid = 0;
  if ( !ConvertStringSidToSidW(v3, &Sid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC6,
      (unsigned int)"admin\\edu\\secureassessment\\common\\inc\\ConfigHelper.h",
      v6);
  cchReferencedDomainName = 0;
  cchName = 0;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() == 122 )
    v4 = 0;
  if ( v4 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xCA,
      (unsigned int)"admin\\edu\\secureassessment\\common\\inc\\ConfigHelper.h",
      v7);
  v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * (cchName + 1));
  v18 = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xCD,
      (unsigned int)"admin\\edu\\secureassessment\\common\\inc\\ConfigHelper.h",
      v9);
  v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (cchReferencedDomainName + 1));
  v17 = v10;
  if ( !v10 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xD0,
      (unsigned int)"admin\\edu\\secureassessment\\common\\inc\\ConfigHelper.h",
      v11);
  if ( !LookupAccountSidW(0, Sid, v8, &cchName, v10, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD2,
      (unsigned int)"admin\\edu\\secureassessment\\common\\inc\\ConfigHelper.h",
      v12);
  v13 = std::_WChar_traits<unsigned short>::length(v10);
  std::wstring::_Assign<unsigned short>(a1, v10, v13);
  std::wstring::append(a1, L"\\");
  std::wstring::append(a1, v8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return a1;
}

```

## disassembly

```asm
0x140069fa0  mov     [rsp-20h+arg_0], rcx
0x140069fa5  push    rbp
0x140069fa6  push    rbx
0x140069fa7  push    rsi
0x140069fa8  push    rdi
0x140069fa9  mov     rbp, rsp
0x140069fac  sub     rsp, 68h
0x140069fb0  mov     r8, rdx
0x140069fb3  mov     rsi, rcx
0x140069fb6  mov     [rbp+var_28], 0
0x140069fbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140069fc2  mov     ebx, 1
0x140069fc7  mov     [rbp+var_28], ebx
0x140069fca  mov     rcx, [rbp+20h]; this
0x140069fce  test    rdx, rdx
0x140069fd1  jnz     short loc_140069FEB
0x140069fd3  mov     r9d, 80070057h; char *
0x140069fd9  lea     r8, aAdminEduSecure_0; "admin\\edu\\secureassessment\\common\\i"...
0x140069fe0  mov     edx, 0C2h; void *
0x140069fe5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140069feb  mov     [rbp+Sid], 0
0x140069ff3  lea     rdx, [rbp+Sid]; Sid
0x140069ff7  mov     rcx, r8; StringSid
0x140069ffa  call    cs:__imp_ConvertStringSidToSidW
0x14006a000  mov     rcx, [rbp+20h]; this
0x14006a004  test    eax, eax
0x14006a006  jnz     short loc_14006A01A
0x14006a008  lea     r8, aAdminEduSecure_0; "admin\\edu\\secureassessment\\common\\i"...
0x14006a00f  mov     edx, 0C6h; void *
0x14006a014  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14006a01a  mov     [rbp+arg_8], 0
0x14006a021  mov     [rbp+cchName], 0
0x14006a028  mov     [rbp+arg_18], 0
0x14006a02f  lea     rax, [rbp+arg_18]
0x14006a033  mov     [rsp+68h+peUse], rax; peUse
0x14006a038  lea     rax, [rbp+arg_8]
0x14006a03c  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006a041  mov     [rsp+68h+ReferencedDomainName], 0; ReferencedDomainName
0x14006a04a  lea     r9, [rbp+cchName]; cchName
0x14006a04e  xor     r8d, r8d; Name
0x14006a051  mov     rdx, [rbp+Sid]; Sid
0x14006a055  xor     ecx, ecx; lpSystemName
0x14006a057  call    cs:__imp_LookupAccountSidW
0x14006a05d  test    eax, eax
0x14006a05f  jnz     short loc_14006A06C
0x14006a061  call    cs:__imp_GetLastError
0x14006a067  cmp     eax, 7Ah ; 'z'
0x14006a06a  jnz     short loc_14006A06E
0x14006a06c  xor     bl, bl
0x14006a06e  mov     rcx, [rbp+20h]; this
0x14006a072  test    bl, bl
0x14006a074  jz      short loc_14006A088
0x14006a076  lea     r8, aAdminEduSecure_0; "admin\\edu\\secureassessment\\common\\i"...
0x14006a07d  mov     edx, 0CAh; void *
0x14006a082  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14006a088  mov     edx, [rbp+cchName]
0x14006a08b  inc     edx
0x14006a08d  add     rdx, rdx; uBytes
0x14006a090  mov     ebx, 40h ; '@'
0x14006a095  mov     ecx, ebx; uFlags
0x14006a097  call    cs:__imp_LocalAlloc
0x14006a09d  mov     rdi, rax
0x14006a0a0  mov     [rbp+var_10], rax
0x14006a0a4  mov     rcx, [rbp+20h]; this
0x14006a0a8  test    rax, rax
0x14006a0ab  jnz     short loc_14006A0BF
0x14006a0ad  lea     r8, aAdminEduSecure_0; "admin\\edu\\secureassessment\\common\\i"...
0x14006a0b4  mov     edx, 0CDh; void *
0x14006a0b9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14006a0bf  mov     edx, [rbp+arg_8]
0x14006a0c2  inc     edx
0x14006a0c4  add     rdx, rdx; uBytes
0x14006a0c7  mov     ecx, ebx; uFlags
0x14006a0c9  call    cs:__imp_LocalAlloc
0x14006a0cf  mov     rbx, rax
0x14006a0d2  mov     [rbp+var_18], rax
0x14006a0d6  mov     rcx, [rbp+20h]; this
0x14006a0da  test    rax, rax
0x14006a0dd  jnz     short loc_14006A0F1
0x14006a0df  lea     r8, aAdminEduSecure_0; "admin\\edu\\secureassessment\\common\\i"...
0x14006a0e6  mov     edx, 0D0h; void *
0x14006a0eb  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14006a0f1  lea     rax, [rbp+arg_18]
0x14006a0f5  mov     [rsp+68h+peUse], rax; peUse
0x14006a0fa  lea     rax, [rbp+arg_8]
0x14006a0fe  mov     [rsp+68h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006a103  mov     [rsp+68h+ReferencedDomainName], rbx; ReferencedDomainName
0x14006a108  lea     r9, [rbp+cchName]; cchName
0x14006a10c  mov     r8, rdi; Name
0x14006a10f  mov     rdx, [rbp+Sid]; Sid
0x14006a113  xor     ecx, ecx; lpSystemName
0x14006a115  call    cs:__imp_LookupAccountSidW
0x14006a11b  mov     rcx, [rbp+20h]; this
0x14006a11f  test    eax, eax
0x14006a121  jnz     short loc_14006A135
0x14006a123  lea     r8, aAdminEduSecure_0; "admin\\edu\\secureassessment\\common\\i"...
0x14006a12a  mov     edx, 0D2h; void *
0x14006a12f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14006a135  mov     rcx, rbx
0x14006a138  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x14006a13d  mov     r8, rax
0x14006a140  mov     rdx, rbx
0x14006a143  mov     rcx, rsi
0x14006a146  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14006a14b  lea     rdx, pszSrc; "\\"
0x14006a152  mov     rcx, rsi
0x14006a155  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14006a15a  mov     rdx, rdi
0x14006a15d  mov     rcx, rsi
0x14006a160  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14006a165  nop
0x14006a166  lea     rcx, [rbp+var_18]
0x14006a16a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006a16f  nop
0x14006a170  lea     rcx, [rbp+var_10]
0x14006a174  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006a179  nop
0x14006a17a  lea     rcx, [rbp+Sid]
0x14006a17e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006a183  mov     rax, rsi
0x14006a186  add     rsp, 68h
0x14006a18a  pop     rdi
0x14006a18b  pop     rsi
0x14006a18c  pop     rbx
0x14006a18d  pop     rbp
0x14006a18e  retn
```
