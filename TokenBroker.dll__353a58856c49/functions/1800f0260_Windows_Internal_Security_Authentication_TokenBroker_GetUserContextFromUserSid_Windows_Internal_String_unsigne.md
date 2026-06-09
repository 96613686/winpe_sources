# Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromUserSid(Windows::Internal::String &,unsigned __int64 &)

- ea: `0x1800f0260`
- end: `0x1800f039b`
- name: `?GetUserContextFromUserSid@TokenBroker@Authentication@Security@Internal@Windows@@YAJAEAVString@45@AEA_K@Z`
- size: `315`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct Windows::Internal::String *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180074e0c`

## callees

- `0x18000bd40`
- `0x18001a510`
- `0x1800286a4`
- `0x1800435d4`
- `0x180055498`
- `0x1800f0260`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f0287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f02ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f0319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f0287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f02ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f0319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f035a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f035a`
- `ntdll!RtlEqualSid` at `0x1800f0338`
- `ntdll!RtlEqualSid` at `0x1800f0338`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f02f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f0326`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f02f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f0326`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x1800f0294`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x1800f0294`

## string_xrefs

- `0x1800f0375`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromUserSid(
        HSTRING *this,
        struct Windows::Internal::String *a2,
        unsigned __int64 *a3)
{
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 *v6; // rdx
  unsigned int v7; // edi
  struct Windows::Internal::String *v8; // r8
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  PSID Sid2; // [rsp+50h] [rbp+28h] BYREF
  HSTRING string; // [rsp+58h] [rbp+30h] BYREF
  PSID Sid; // [rsp+60h] [rbp+38h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v17; // [rsp+68h] [rbp+40h] BYREF

  *(_QWORD *)a2 = 0;
  v17 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*this, 0);
  v7 = UMgrQueryUserContextFromSid(StringRawBuffer, &v17);
  if ( v7 == -2147023584 )
  {
    if ( (int)Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(
                (Windows::Internal::Security::Authentication::TokenBroker *)&v17,
                v6) < 0 )
      goto LABEL_13;
    Sid = 0;
    string = 0;
    if ( (int)Windows::Internal::Security::Authentication::TokenBroker::GetUserSidFromUserContext(
                v17,
                (unsigned __int64)&string,
                v8) >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &Sid,
        0);
      v9 = WindowsGetStringRawBuffer(string, 0);
      if ( ConvertStringSidToSidW(v9, &Sid) )
      {
        Sid2 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &Sid2,
          0);
        v10 = WindowsGetStringRawBuffer(*this, 0);
        if ( ConvertStringSidToSidW(v10, &Sid2) && RtlEqualSid(Sid, Sid2) )
          v7 = 0;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid2);
      }
    }
    if ( string )
      WindowsDeleteString(string);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  }
  if ( (v7 & 0x80000000) == 0 )
  {
    *(_QWORD *)a2 = v17;
    return v7;
  }
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA50,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
    (const char *)v7,
    v12);
  return v7;
}

```

## disassembly

```asm
0x1800f0260  push    rbp
0x1800f0262  push    rsi
0x1800f0263  push    rdi
0x1800f0264  push    r14
0x1800f0266  mov     rbp, rsp
0x1800f0269  sub     rsp, 28h
0x1800f026d  mov     rsi, rdx
0x1800f0270  mov     r14, rcx
0x1800f0273  mov     qword ptr [rdx], 0
0x1800f027a  mov     [rbp+arg_18], 0
0x1800f0282  xor     edx, edx; length
0x1800f0284  mov     rcx, [rcx]; string
0x1800f0287  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f028d  lea     rdx, [rbp+arg_18]
0x1800f0291  mov     rcx, rax
0x1800f0294  call    cs:__imp_UMgrQueryUserContextFromSid
0x1800f029a  mov     edi, eax
0x1800f029c  cmp     eax, 80070520h
0x1800f02a1  jnz     loc_1800F036A
0x1800f02a7  lea     rcx, [rbp+arg_18]; this
0x1800f02ab  call    ?GetCurrentUserContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(unsigned __int64 *)
0x1800f02b0  test    eax, eax
0x1800f02b2  js      loc_1800F036E
0x1800f02b8  mov     [rbp+Sid], 0
0x1800f02c0  mov     [rbp+string], 0
0x1800f02c8  lea     rdx, [rbp+string]; unsigned __int64
0x1800f02cc  mov     rcx, [rbp+arg_18]; this
0x1800f02d0  call    ?GetUserSidFromUserContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_KAEAVString@45@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserSidFromUserContext(unsigned __int64,Windows::Internal::String &)
0x1800f02d5  test    eax, eax
0x1800f02d7  js      short loc_1800F034F
0x1800f02d9  xor     edx, edx
0x1800f02db  lea     rcx, [rbp+Sid]
0x1800f02df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800f02e4  xor     edx, edx; length
0x1800f02e6  mov     rcx, [rbp+string]; string
0x1800f02ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f02f0  lea     rdx, [rbp+Sid]; Sid
0x1800f02f4  mov     rcx, rax; StringSid
0x1800f02f7  call    cs:__imp_ConvertStringSidToSidW
0x1800f02fd  test    eax, eax
0x1800f02ff  jz      short loc_1800F034F
0x1800f0301  mov     [rbp+Sid2], 0
0x1800f0309  xor     edx, edx
0x1800f030b  lea     rcx, [rbp+Sid2]
0x1800f030f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800f0314  xor     edx, edx; length
0x1800f0316  mov     rcx, [r14]; string
0x1800f0319  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f031f  lea     rdx, [rbp+Sid2]; Sid
0x1800f0323  mov     rcx, rax; StringSid
0x1800f0326  call    cs:__imp_ConvertStringSidToSidW
0x1800f032c  test    eax, eax
0x1800f032e  jz      short loc_1800F0345
0x1800f0330  mov     rdx, [rbp+Sid2]; Sid2
0x1800f0334  mov     rcx, [rbp+Sid]; Sid1
0x1800f0338  call    cs:__imp_RtlEqualSid
0x1800f033e  xor     ecx, ecx
0x1800f0340  test    al, al
0x1800f0342  cmovnz  edi, ecx
0x1800f0345  lea     rcx, [rbp+Sid2]
0x1800f0349  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800f034e  nop
0x1800f034f  cmp     [rbp+string], 0
0x1800f0354  jz      short loc_1800F0361
0x1800f0356  mov     rcx, [rbp+string]; string
0x1800f035a  call    cs:__imp_WindowsDeleteString
0x1800f0360  nop
0x1800f0361  lea     rcx, [rbp+Sid]
0x1800f0365  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800f036a  test    edi, edi
0x1800f036c  jns     short loc_1800F0388
0x1800f036e  mov     rcx, [rbp+20h]; this
0x1800f0372  mov     r9d, edi; char *
0x1800f0375  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f037c  mov     edx, 0A50h; void *
0x1800f0381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0386  jmp     short loc_1800F038F
0x1800f0388  mov     rax, [rbp+arg_18]
0x1800f038c  mov     [rsi], rax
0x1800f038f  mov     eax, edi
0x1800f0391  add     rsp, 28h
0x1800f0395  pop     r14
0x1800f0397  pop     rdi
0x1800f0398  pop     rsi
0x1800f0399  pop     rbp
0x1800f039a  retn
```
