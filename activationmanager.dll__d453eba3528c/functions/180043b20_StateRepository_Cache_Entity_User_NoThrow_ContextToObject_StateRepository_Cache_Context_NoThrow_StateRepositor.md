# StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)

- ea: `0x180043b20`
- end: `0x180043c78`
- name: `?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008de44`

## callees

- `0x18000b5c0`
- `0x18002f980`
- `0x180030470`
- `0x18003a02c`
- `0x180043b20`
- `0x180044408`
- `0x180050cf0`
- `0x18005d2b9`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043c28`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043c28`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180043be3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180043be3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180043ba4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180043c5a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180043ba4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180043c5a`

## string_xrefs

- `0x180043b7f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180043bfc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180043b51`: `UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // ebx
  LPCWSTR v7; // rcx
  LPCWSTR v9; // rcx
  BOOL v10; // ebx
  const char *v11; // r9
  PSID v12; // rbx
  DWORD LengthSid; // eax
  PSID pSid; // [rsp+20h] [rbp-20h] BYREF
  void *p_StringSid; // [rsp+28h] [rbp-18h] BYREF
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  char v17; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPCWSTR StringSid; // [rsp+70h] [rbp+30h] BYREF

  StringSid = 0;
  Sid = 0;
  p_StringSid = &StringSid;
  v17 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"UserSid", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
LABEL_3:
    v7 = StringSid;
    StringSid = 0;
    if ( v7 )
      SRCache_Free(v7);
    return (unsigned int)Field;
  }
  v9 = StringSid;
  if ( StringSid )
  {
    pSid = 0;
    p_StringSid = &pSid;
    Sid = 0;
    v17 = 1;
    v10 = ConvertStringSidToSidW(StringSid, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_StringSid);
    if ( !v10 )
    {
      Field = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x34F,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                v11);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
      goto LABEL_3;
    }
    v12 = pSid;
    LengthSid = GetLengthSid(pSid);
    memcpy_0(a2 + 1, v12, LengthSid);
    a2[10] = a2 + 1;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid);
    v9 = StringSid;
  }
  else
  {
    a2[10] = 0;
  }
  StringSid = 0;
  if ( v9 )
    SRCache_Free(v9);
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x180043b20  mov     [rsp-18h+arg_0], rbx
0x180043b25  mov     [rsp-18h+arg_8], rsi
0x180043b2a  mov     [rsp-18h+StringSid], r8
0x180043b2f  push    rbp
0x180043b30  push    rdi
0x180043b31  push    r14
0x180043b33  mov     rbp, rsp
0x180043b36  sub     rsp, 40h
0x180043b3a  mov     rsi, rdx
0x180043b3d  mov     [rbp+StringSid], 0
0x180043b45  lea     rax, [rbp+StringSid]
0x180043b49  mov     [rbp+Sid], 0
0x180043b51  lea     rdx, aUsersid; "UserSid"
0x180043b58  mov     [rbp+var_18], rax
0x180043b5c  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180043b60  mov     [rbp+var_8], 1
0x180043b64  mov     r14, r9
0x180043b67  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180043b6c  lea     rcx, [rbp+var_18]
0x180043b70  mov     ebx, eax
0x180043b72  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180043b77  test    ebx, ebx
0x180043b79  jns     short loc_180043BB1
0x180043b7b  mov     rcx, [rbp+18h]; this
0x180043b7f  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180043b86  mov     r9d, ebx; char *
0x180043b89  mov     edx, 347h; void *
0x180043b8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043b93  mov     rcx, [rbp+StringSid]
0x180043b97  mov     [rbp+StringSid], 0
0x180043b9f  test    rcx, rcx
0x180043ba2  jz      short loc_180043BAA
0x180043ba4  call    cs:__imp_SRCache_Free
0x180043baa  mov     eax, ebx
0x180043bac  jmp     loc_180043C65
0x180043bb1  mov     rcx, [rbp+StringSid]; StringSid
0x180043bb5  test    rcx, rcx
0x180043bb8  jnz     short loc_180043BC3
0x180043bba  mov     [rsi+50h], rcx
0x180043bbe  jmp     loc_180043C4D
0x180043bc3  lea     rax, [rbp+pSid]
0x180043bc7  mov     [rbp+pSid], 0
0x180043bcf  lea     rdx, [rbp+Sid]; Sid
0x180043bd3  mov     [rbp+var_18], rax
0x180043bd7  mov     [rbp+Sid], 0
0x180043bdf  mov     [rbp+var_8], 1
0x180043be3  call    cs:__imp_ConvertStringSidToSidW
0x180043be9  lea     rcx, [rbp+var_18]
0x180043bed  mov     ebx, eax
0x180043bef  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180043bf4  test    ebx, ebx
0x180043bf6  jnz     short loc_180043C1D
0x180043bf8  mov     rcx, [rbp+18h]; this
0x180043bfc  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180043c03  mov     edx, 34Fh; void *
0x180043c08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043c0d  lea     rcx, [rbp+pSid]
0x180043c11  mov     ebx, eax
0x180043c13  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180043c18  jmp     loc_180043B93
0x180043c1d  mov     rbx, [rbp+pSid]
0x180043c21  lea     rdi, [rsi+8]
0x180043c25  mov     rcx, rbx; pSid
0x180043c28  call    cs:__imp_GetLengthSid
0x180043c2e  mov     r8d, eax; Size
0x180043c31  mov     rdx, rbx; Src
0x180043c34  mov     rcx, rdi; void *
0x180043c37  call    memcpy_0
0x180043c3c  lea     rcx, [rbp+pSid]
0x180043c40  mov     [rsi+50h], rdi
0x180043c44  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180043c49  mov     rcx, [rbp+StringSid]
0x180043c4d  mov     [rbp+StringSid], 0
0x180043c55  test    rcx, rcx
0x180043c58  jz      short loc_180043C60
0x180043c5a  call    cs:__imp_SRCache_Free
0x180043c60  mov     [rsi], r14
0x180043c63  xor     eax, eax
0x180043c65  mov     rbx, [rsp+40h+arg_0]
0x180043c6a  mov     rsi, [rsp+40h+arg_8]
0x180043c6f  add     rsp, 40h
0x180043c73  pop     r14
0x180043c75  pop     rdi
0x180043c76  pop     rbp
0x180043c77  retn
```
