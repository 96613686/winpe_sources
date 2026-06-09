# RetailDemoUtil::GetGroupName(void *,ushort * *)

- ea: `0x1800308f8`
- end: `0x180030a5c`
- name: `?GetGroupName@RetailDemoUtil@@YAXPEAXPEAPEAG@Z`
- size: `356`
- prototype: `void __fastcall(PSID Sid, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180031d7c`

## callees

- `0x18000e3bc`
- `0x18001094c`
- `0x18001096c`
- `0x180014d04`
- `0x180025cd8`
- `0x1800308f8`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180030948`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180030a0e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180030948`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180030a0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800309c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800309c6`

## string_xrefs

- `0x180030961`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800309ae`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800309d9`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x180030a1c`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RetailDemoUtil::GetGroupName(PSID Sid, WCHAR **a2, unsigned __int16 **a3)
{
  unsigned int Error; // eax
  char v6; // cl
  WCHAR *v7; // rbx
  const char *v8; // r9
  WCHAR *v9; // rax
  const char *v10; // r9
  const char *v11; // r9
  int ReferencedDomainName; // [rsp+20h] [rbp-40h]
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-20h] BYREF
  WCHAR *v14; // [rsp+48h] [rbp-18h] BYREF
  WCHAR *v15; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+98h] [rbp+38h] BYREF

  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    Error = 0;
LABEL_3:
    v6 = 0;
    goto LABEL_4;
  }
  Error = ResultFromKnownLastError();
  if ( (int)(Error + 0x80000000) < 0 || Error == -2147024774 )
    goto LABEL_3;
  v6 = 1;
LABEL_4:
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CB,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      (const char *)Error,
      ReferencedDomainName);
  v7 = (WCHAR *)CoTaskMemAlloc(2LL * cchName);
  v14 = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2CE,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v8);
  v9 = (WCHAR *)CoTaskMemAlloc(2LL * cchReferencedDomainName);
  v15 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v10);
  if ( !LookupAccountSidW(0, Sid, v7, &cchName, v9, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D3,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v11);
  v14 = 0;
  *a2 = v7;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
}

```

## disassembly

```asm
0x1800308f8  mov     r11, rsp
0x1800308fb  mov     [r11+8], rbx
0x1800308ff  push    rbp
0x180030900  push    rsi
0x180030901  push    rdi
0x180030902  mov     rbp, rsp
0x180030905  sub     rsp, 60h
0x180030909  mov     rdi, rdx
0x18003090c  mov     rsi, rcx
0x18003090f  mov     [rbp+cchName], 0
0x180030916  mov     [rbp+arg_10], 0
0x18003091d  mov     [rbp+var_20], 0
0x180030924  lea     rax, [rbp+var_20]
0x180030928  mov     [r11-48h], rax
0x18003092c  lea     rax, [rbp+arg_10]
0x180030930  mov     [r11-50h], rax
0x180030934  mov     qword ptr [r11-58h], 0
0x18003093c  lea     r9, [rbp+cchName]; cchName
0x180030940  xor     r8d, r8d; Name
0x180030943  mov     rdx, rcx; Sid
0x180030946  xor     ecx, ecx; lpSystemName
0x180030948  call    cs:__imp_LookupAccountSidW
0x18003094e  test    eax, eax
0x180030950  jz      short loc_180030976
0x180030952  xor     eax, eax
0x180030954  xor     cl, cl
0x180030956  mov     r10, [rbp+18h]
0x18003095a  test    cl, cl
0x18003095c  jz      short loc_180030992
0x18003095e  mov     r9d, eax; char *
0x180030961  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030968  mov     edx, 2CBh; void *
0x18003096d  mov     rcx, r10; this
0x180030970  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030976  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003097b  mov     edx, 80000000h
0x180030980  lea     ecx, [rax+rdx]
0x180030983  test    edx, ecx
0x180030985  jnz     short loc_180030954
0x180030987  cmp     eax, 8007007Ah
0x18003098c  jz      short loc_180030954
0x18003098e  mov     cl, 1
0x180030990  jmp     short loc_180030956
0x180030992  mov     ecx, [rbp+cchName]
0x180030995  add     rcx, rcx; cb
0x180030998  call    cs:__imp_CoTaskMemAlloc
0x18003099e  mov     rbx, rax
0x1800309a1  mov     [rbp+var_18], rax
0x1800309a5  mov     rcx, [rbp+18h]; this
0x1800309a9  test    rax, rax
0x1800309ac  jnz     short loc_1800309C0
0x1800309ae  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800309b5  mov     edx, 2CEh; void *
0x1800309ba  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800309c0  mov     ecx, [rbp+arg_10]
0x1800309c3  add     rcx, rcx; cb
0x1800309c6  call    cs:__imp_CoTaskMemAlloc
0x1800309cc  mov     [rbp+var_10], rax
0x1800309d0  mov     rcx, [rbp+18h]; this
0x1800309d4  test    rax, rax
0x1800309d7  jnz     short loc_1800309EB
0x1800309d9  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800309e0  mov     edx, 2D1h; void *
0x1800309e5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800309eb  lea     rcx, [rbp+var_20]
0x1800309ef  mov     [rsp+60h+peUse], rcx; peUse
0x1800309f4  lea     rcx, [rbp+arg_10]
0x1800309f8  mov     [rsp+60h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800309fd  mov     [rsp+60h+ReferencedDomainName], rax; ReferencedDomainName
0x180030a02  lea     r9, [rbp+cchName]; cchName
0x180030a06  mov     r8, rbx; Name
0x180030a09  mov     rdx, rsi; Sid
0x180030a0c  xor     ecx, ecx; lpSystemName
0x180030a0e  call    cs:__imp_LookupAccountSidW
0x180030a14  mov     rcx, [rbp+18h]; this
0x180030a18  test    eax, eax
0x180030a1a  jnz     short loc_180030A2E
0x180030a1c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030a23  mov     edx, 2D3h; void *
0x180030a28  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180030a2e  mov     [rbp+var_18], 0
0x180030a36  mov     [rdi], rbx
0x180030a39  lea     rcx, [rbp+var_10]
0x180030a3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030a42  nop
0x180030a43  lea     rcx, [rbp+var_18]
0x180030a47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030a4c  mov     rbx, [rsp+60h+arg_0]
0x180030a54  add     rsp, 60h
0x180030a58  pop     rdi
0x180030a59  pop     rsi
0x180030a5a  pop     rbp
0x180030a5b  retn
```
