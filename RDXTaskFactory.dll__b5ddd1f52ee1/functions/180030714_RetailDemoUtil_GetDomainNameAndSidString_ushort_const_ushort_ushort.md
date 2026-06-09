# RetailDemoUtil::GetDomainNameAndSidString(ushort const *,ushort * *,ushort * *)

- ea: `0x180030714`
- end: `0x1800308f1`
- name: `?GetDomainNameAndSidString@RetailDemoUtil@@YAXPEBGPEAPEAG1@Z`
- size: `477`
- prototype: `void __fastcall(LPCWSTR lpAccountName, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180021830`

## callees

- `0x18000e3bc`
- `0x18001094c`
- `0x18001096c`
- `0x180010a60`
- `0x180014d04`
- `0x18001e55c`
- `0x180025cd8`
- `0x180030714`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030884`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030884`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180030768`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180030848`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180030768`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180030848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800307bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800307f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800307bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800307f3`

## string_xrefs

- `0x18003079f`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800307d7`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030812`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030856`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030892`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RetailDemoUtil::GetDomainNameAndSidString(
        LPCWSTR lpAccountName,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned int Error; // eax
  char v8; // cl
  LPVOID v9; // rax
  const char *v10; // r9
  LPVOID v11; // rax
  const char *v12; // r9
  LPWSTR v13; // rdi
  const char *v14; // r9
  const char *v15; // r9
  unsigned __int16 *v16; // rax
  int ReferencedDomainName; // [rsp+20h] [rbp-50h]
  PSID Sid; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR v20; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 **v21; // [rsp+58h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-10h] BYREF
  char v23; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD cchReferencedDomainName; // [rsp+A8h] [rbp+38h] BYREF
  DWORD cbSid; // [rsp+B0h] [rbp+40h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+B8h] [rbp+48h] BYREF

  *(_QWORD *)a2 = 0;
  *a3 = 0;
  cchReferencedDomainName = 0;
  cbSid = 0;
  peUse = 0;
  if ( LookupAccountNameW(0, lpAccountName, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
  {
    Error = 0;
LABEL_5:
    v8 = 0;
    goto LABEL_6;
  }
  Error = ResultFromKnownLastError();
  if ( (int)(Error + 0x80000000) < 0 )
    goto LABEL_5;
  v8 = 1;
  if ( Error == -2147024774 )
    goto LABEL_5;
LABEL_6:
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)Error,
      ReferencedDomainName);
  Sid = 0;
  v9 = CoTaskMemAlloc(cbSid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    v9);
  if ( !Sid )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v10);
  v20 = 0;
  v11 = CoTaskMemAlloc(2LL * cchReferencedDomainName);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v20,
    v11);
  v13 = v20;
  if ( !v20 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v12);
  if ( !LookupAccountNameW(0, lpAccountName, Sid, &cbSid, v20, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v14);
  v19 = 0;
  v21 = &v19;
  StringSid = 0;
  v23 = 1;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2BE,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v15);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v21);
  v20 = 0;
  *(_QWORD *)a2 = v13;
  v16 = v19;
  v19 = 0;
  *a3 = v16;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
}

```

## disassembly

```asm
0x180030714  mov     r11, rsp
0x180030717  mov     [r11+8], rsi
0x18003071b  push    rbp
0x18003071c  push    rdi
0x18003071d  push    r12
0x18003071f  push    r14
0x180030721  push    r15
0x180030723  mov     rbp, rsp
0x180030726  sub     rsp, 70h
0x18003072a  mov     rsi, r8
0x18003072d  mov     r14, rdx
0x180030730  mov     r15, rcx
0x180030733  xor     r12d, r12d
0x180030736  mov     [rdx], r12
0x180030739  mov     [r8], r12
0x18003073c  mov     [rbp+arg_8], r12d
0x180030740  mov     [rbp+cbSid], r12d
0x180030744  mov     [rbp+arg_18], r12d
0x180030748  lea     rax, [rbp+arg_18]
0x18003074c  mov     [r11-68h], rax
0x180030750  lea     rax, [rbp+arg_8]
0x180030754  mov     [r11-70h], rax
0x180030758  mov     [r11-78h], r12
0x18003075c  lea     r9, [rbp+cbSid]; cbSid
0x180030760  xor     r8d, r8d; Sid
0x180030763  mov     rdx, rcx; lpAccountName
0x180030766  xor     ecx, ecx; lpSystemName
0x180030768  call    cs:__imp_LookupAccountNameW
0x18003076e  test    eax, eax
0x180030770  jz      short loc_180030777
0x180030772  mov     eax, r12d
0x180030775  jmp     short loc_180030791
0x180030777  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003077c  mov     edx, 80000000h
0x180030781  lea     ecx, [rax+rdx]
0x180030784  test    edx, ecx
0x180030786  jnz     short loc_180030791
0x180030788  cmp     eax, 8007007Ah
0x18003078d  mov     cl, 1
0x18003078f  jnz     short loc_180030794
0x180030791  mov     cl, r12b
0x180030794  mov     r10, [rbp+28h]
0x180030798  test    cl, cl
0x18003079a  jz      short loc_1800307B4
0x18003079c  mov     r9d, eax; char *
0x18003079f  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800307a6  mov     edx, 2B0h; void *
0x1800307ab  mov     rcx, r10; this
0x1800307ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800307b4  mov     [rbp+Sid], r12
0x1800307b8  mov     ecx, [rbp+cbSid]; cb
0x1800307bb  call    cs:__imp_CoTaskMemAlloc
0x1800307c1  mov     rdx, rax
0x1800307c4  lea     rcx, [rbp+Sid]
0x1800307c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800307cd  mov     rcx, [rbp+28h]; this
0x1800307d1  cmp     [rbp+Sid], r12
0x1800307d5  jnz     short loc_1800307E9
0x1800307d7  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800307de  mov     edx, 2B4h; void *
0x1800307e3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800307e9  mov     [rbp+var_20], r12
0x1800307ed  mov     ecx, [rbp+arg_8]
0x1800307f0  add     rcx, rcx; cb
0x1800307f3  call    cs:__imp_CoTaskMemAlloc
0x1800307f9  mov     rdx, rax
0x1800307fc  lea     rcx, [rbp+var_20]
0x180030800  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180030805  mov     rcx, [rbp+28h]; this
0x180030809  mov     rdi, [rbp+var_20]
0x18003080d  test    rdi, rdi
0x180030810  jnz     short loc_180030824
0x180030812  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030819  mov     edx, 2B8h; void *
0x18003081e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180030824  lea     rax, [rbp+arg_18]
0x180030828  mov     [rsp+70h+peUse], rax; peUse
0x18003082d  lea     rax, [rbp+arg_8]
0x180030831  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180030836  mov     [rsp+70h+ReferencedDomainName], rdi; ReferencedDomainName
0x18003083b  lea     r9, [rbp+cbSid]; cbSid
0x18003083f  mov     r8, [rbp+Sid]; Sid
0x180030843  mov     rdx, r15; lpAccountName
0x180030846  xor     ecx, ecx; lpSystemName
0x180030848  call    cs:__imp_LookupAccountNameW
0x18003084e  mov     rcx, [rbp+28h]; this
0x180030852  test    eax, eax
0x180030854  jnz     short loc_180030868
0x180030856  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003085d  mov     edx, 2BBh; void *
0x180030862  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180030868  mov     [rbp+var_28], r12
0x18003086c  lea     rax, [rbp+var_28]
0x180030870  mov     [rbp+var_18], rax
0x180030874  mov     [rbp+StringSid], r12
0x180030878  mov     [rbp+var_8], 1
0x18003087c  lea     rdx, [rbp+StringSid]; StringSid
0x180030880  mov     rcx, [rbp+Sid]; Sid
0x180030884  call    cs:__imp_ConvertSidToStringSidW
0x18003088a  mov     rcx, [rbp+28h]; this
0x18003088e  test    eax, eax
0x180030890  jnz     short loc_1800308A4
0x180030892  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030899  mov     edx, 2BEh; void *
0x18003089e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800308a4  lea     rcx, [rbp+var_18]
0x1800308a8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800308ad  mov     [rbp+var_20], r12
0x1800308b1  mov     [r14], rdi
0x1800308b4  mov     rax, [rbp+var_28]
0x1800308b8  mov     [rbp+var_28], r12
0x1800308bc  mov     [rsi], rax
0x1800308bf  lea     rcx, [rbp+var_28]
0x1800308c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800308c8  nop
0x1800308c9  lea     rcx, [rbp+var_20]
0x1800308cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800308d2  nop
0x1800308d3  lea     rcx, [rbp+Sid]
0x1800308d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800308dc  mov     rsi, [rsp+70h+arg_0]
0x1800308e4  add     rsp, 70h
0x1800308e8  pop     r15
0x1800308ea  pop     r14
0x1800308ec  pop     r12
0x1800308ee  pop     rdi
0x1800308ef  pop     rbp
0x1800308f0  retn
```
