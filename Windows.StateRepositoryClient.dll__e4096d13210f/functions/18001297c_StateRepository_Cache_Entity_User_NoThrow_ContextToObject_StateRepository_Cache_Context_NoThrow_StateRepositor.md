# StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)

- ea: `0x18001297c`
- end: `0x180012ad4`
- name: `?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `344`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800130b0`

## callees

- `0x1800075c4`
- `0x1800075e4`
- `0x180009444`
- `0x1800094d4`
- `0x18000b130`
- `0x180012110`
- `0x18001297c`
- `0x180026690`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012a84`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012a84`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012a3f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012a3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012a00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012ab6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012a00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180012ab6`

## string_xrefs

- `0x1800129db`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x180012a58`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x1800129ad`: `UserSid`

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
  __int64 *p_StringSid; // [rsp+28h] [rbp-18h] BYREF
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  char v17; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPCWSTR StringSid; // [rsp+70h] [rbp+30h] BYREF

  StringSid = 0;
  Sid = 0;
  p_StringSid = (__int64 *)&StringSid;
  v17 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"UserSid", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
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
    p_StringSid = (__int64 *)&pSid;
    Sid = 0;
    v17 = 1;
    v10 = ConvertStringSidToSidW(StringSid, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_StringSid);
    if ( !v10 )
    {
      Field = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x34F,
                (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
                v11);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
      goto LABEL_3;
    }
    v12 = pSid;
    LengthSid = GetLengthSid(pSid);
    memcpy_0(a2 + 1, v12, LengthSid);
    a2[10] = a2 + 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
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
0x18001297c  mov     [rsp-18h+arg_0], rbx
0x180012981  mov     [rsp-18h+arg_8], rsi
0x180012986  mov     [rsp-18h+StringSid], r8
0x18001298b  push    rbp
0x18001298c  push    rdi
0x18001298d  push    r14
0x18001298f  mov     rbp, rsp
0x180012992  sub     rsp, 40h
0x180012996  mov     rsi, rdx
0x180012999  mov     [rbp+StringSid], 0
0x1800129a1  lea     rax, [rbp+StringSid]
0x1800129a5  mov     [rbp+Sid], 0
0x1800129ad  lea     rdx, aUsersid; "UserSid"
0x1800129b4  mov     [rbp+var_18], rax
0x1800129b8  lea     r8, [rbp+Sid]; unsigned __int16 **
0x1800129bc  mov     [rbp+var_8], 1
0x1800129c0  mov     r14, r9
0x1800129c3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800129c8  lea     rcx, [rbp+var_18]
0x1800129cc  mov     ebx, eax
0x1800129ce  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800129d3  test    ebx, ebx
0x1800129d5  jns     short loc_180012A0D
0x1800129d7  mov     rcx, [rbp+18h]; this
0x1800129db  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x1800129e2  mov     r9d, ebx; char *
0x1800129e5  mov     edx, 347h; void *
0x1800129ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129ef  mov     rcx, [rbp+StringSid]
0x1800129f3  mov     [rbp+StringSid], 0
0x1800129fb  test    rcx, rcx
0x1800129fe  jz      short loc_180012A06
0x180012a00  call    cs:__imp_SRCache_Free
0x180012a06  mov     eax, ebx
0x180012a08  jmp     loc_180012AC1
0x180012a0d  mov     rcx, [rbp+StringSid]; StringSid
0x180012a11  test    rcx, rcx
0x180012a14  jnz     short loc_180012A1F
0x180012a16  mov     [rsi+50h], rcx
0x180012a1a  jmp     loc_180012AA9
0x180012a1f  lea     rax, [rbp+pSid]
0x180012a23  mov     [rbp+pSid], 0
0x180012a2b  lea     rdx, [rbp+Sid]; Sid
0x180012a2f  mov     [rbp+var_18], rax
0x180012a33  mov     [rbp+Sid], 0
0x180012a3b  mov     [rbp+var_8], 1
0x180012a3f  call    cs:__imp_ConvertStringSidToSidW
0x180012a45  lea     rcx, [rbp+var_18]
0x180012a49  mov     ebx, eax
0x180012a4b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180012a50  test    ebx, ebx
0x180012a52  jnz     short loc_180012A79
0x180012a54  mov     rcx, [rbp+18h]; this
0x180012a58  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x180012a5f  mov     edx, 34Fh; void *
0x180012a64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012a69  lea     rcx, [rbp+pSid]
0x180012a6d  mov     ebx, eax
0x180012a6f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012a74  jmp     loc_1800129EF
0x180012a79  mov     rbx, [rbp+pSid]
0x180012a7d  lea     rdi, [rsi+8]
0x180012a81  mov     rcx, rbx; pSid
0x180012a84  call    cs:__imp_GetLengthSid
0x180012a8a  mov     r8d, eax; Size
0x180012a8d  mov     rdx, rbx; Src
0x180012a90  mov     rcx, rdi; void *
0x180012a93  call    memcpy_0
0x180012a98  lea     rcx, [rbp+pSid]
0x180012a9c  mov     [rsi+50h], rdi
0x180012aa0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012aa5  mov     rcx, [rbp+StringSid]
0x180012aa9  mov     [rbp+StringSid], 0
0x180012ab1  test    rcx, rcx
0x180012ab4  jz      short loc_180012ABC
0x180012ab6  call    cs:__imp_SRCache_Free
0x180012abc  mov     [rsi], r14
0x180012abf  xor     eax, eax
0x180012ac1  mov     rbx, [rsp+40h+arg_0]
0x180012ac6  mov     rsi, [rsp+40h+arg_8]
0x180012acb  add     rsp, 40h
0x180012acf  pop     r14
0x180012ad1  pop     rdi
0x180012ad2  pop     rbp
0x180012ad3  retn
```
