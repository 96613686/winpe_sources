# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x18002c818`
- end: `0x18002ca0f`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d548`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000edb0`
- `0x180012634`
- `0x180018400`
- `0x180027174`
- `0x18002c818`
- `0x1800444a2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c972`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002c972`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c927`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c927`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c8ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c9a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c8ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c9a7`

## string_xrefs

- `0x18002c879`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c8cb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c946`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c8a1`: `PackageSID`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        _QWORD *a2,
        const WCHAR *a3,
        __int64 a4)
{
  int Field; // ebx
  __int64 v8; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  LPCWSTR v12; // rcx
  LPCWSTR v13; // rcx
  BOOL v14; // ebx
  const char *v15; // r9
  PSID v16; // rbx
  DWORD LengthSid; // eax
  PSID pSid; // [rsp+20h] [rbp-20h] BYREF
  void *p_StringSid; // [rsp+28h] [rbp-18h] BYREF
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  char v21; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPCWSTR StringSid; // [rsp+70h] [rbp+30h] BYREF

  StringSid = a3;
  Sid = 0;
  p_StringSid = a2 + 1;
  v21 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamilyName", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    v8 = 775;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
    return (unsigned int)Field;
  }
  StringSid = 0;
  Sid = 0;
  p_StringSid = &StringSid;
  v21 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageSID", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)Field,
      (int)pSid);
    goto LABEL_7;
  }
  v13 = StringSid;
  if ( StringSid )
  {
    pSid = 0;
    Sid = 0;
    p_StringSid = &pSid;
    v21 = 1;
    v14 = ConvertStringSidToSidW(StringSid, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_StringSid);
    if ( !v14 )
    {
      Field = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x315,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
LABEL_7:
      v12 = StringSid;
      StringSid = 0;
      if ( v12 )
        SRCache_Free(v12, v11);
      return (unsigned int)Field;
    }
    v16 = pSid;
    LengthSid = GetLengthSid(pSid);
    memcpy_0(a2 + 2, v16, LengthSid);
    a2[11] = a2 + 2;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
    v13 = StringSid;
  }
  else
  {
    a2[11] = 0;
  }
  StringSid = 0;
  if ( v13 )
    SRCache_Free(v13, v10);
  Sid = 0;
  p_StringSid = a2 + 12;
  v21 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Publisher", (unsigned __int16 **)&Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&p_StringSid);
  if ( Field < 0 )
  {
    v8 = 796;
    goto LABEL_3;
  }
  *a2 = a4;
  return 0;
}

```

## disassembly

```asm
0x18002c818  mov     rax, rsp
0x18002c81b  mov     [rax+8], rbx
0x18002c81f  mov     [rax+10h], rsi
0x18002c823  mov     [rax+20h], rdi
0x18002c827  mov     [rax+18h], r8
0x18002c82b  push    rbp
0x18002c82c  push    r14
0x18002c82e  push    r15
0x18002c830  mov     rbp, rsp
0x18002c833  sub     rsp, 40h
0x18002c837  and     [rbp+Sid], 0
0x18002c83c  lea     rax, [rdx+8]
0x18002c840  mov     rsi, rdx
0x18002c843  mov     [rbp+var_18], rax
0x18002c847  lea     rdx, aPackagefamilyn; "PackageFamilyName"
0x18002c84e  mov     [rbp+var_8], 1
0x18002c852  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002c856  mov     r15, r9
0x18002c859  mov     r14, rcx
0x18002c85c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002c861  lea     rcx, [rbp+var_18]
0x18002c865  mov     ebx, eax
0x18002c867  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002c86c  test    ebx, ebx
0x18002c86e  jns     short loc_18002C88F
0x18002c870  mov     edx, 307h; void *
0x18002c875  mov     rcx, [rbp+18h]; this
0x18002c879  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c880  mov     r9d, ebx; char *
0x18002c883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c888  mov     eax, ebx
0x18002c88a  jmp     loc_18002C9F5
0x18002c88f  and     [rbp+StringSid], 0
0x18002c894  lea     rax, [rbp+StringSid]
0x18002c898  and     [rbp+Sid], 0
0x18002c89d  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002c8a1  lea     rdx, aPackagesid; "PackageSID"
0x18002c8a8  mov     [rbp+var_18], rax
0x18002c8ac  mov     rcx, r14; this
0x18002c8af  mov     [rbp+var_8], 1
0x18002c8b3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002c8b8  lea     rcx, [rbp+var_18]
0x18002c8bc  mov     ebx, eax
0x18002c8be  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002c8c3  test    ebx, ebx
0x18002c8c5  jns     short loc_18002C8FB
0x18002c8c7  mov     rcx, [rbp+18h]; this
0x18002c8cb  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c8d2  mov     r9d, ebx; char *
0x18002c8d5  mov     edx, 30Dh; void *
0x18002c8da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8df  mov     rcx, [rbp+StringSid]
0x18002c8e3  and     [rbp+StringSid], 0
0x18002c8e8  test    rcx, rcx
0x18002c8eb  jz      short loc_18002C888
0x18002c8ed  call    cs:__imp_SRCache_Free
0x18002c8f4  nop     dword ptr [rax+rax+00h]
0x18002c8f9  jmp     short loc_18002C888
0x18002c8fb  mov     rcx, [rbp+StringSid]; StringSid
0x18002c8ff  test    rcx, rcx
0x18002c902  jnz     short loc_18002C90D
0x18002c904  and     [rsi+58h], rcx
0x18002c908  jmp     loc_18002C99D
0x18002c90d  and     [rbp+pSid], 0
0x18002c912  lea     rax, [rbp+pSid]
0x18002c916  and     [rbp+Sid], 0
0x18002c91b  lea     rdx, [rbp+Sid]; Sid
0x18002c91f  mov     [rbp+var_18], rax
0x18002c923  mov     [rbp+var_8], 1
0x18002c927  call    cs:__imp_ConvertStringSidToSidW
0x18002c92e  nop     dword ptr [rax+rax+00h]
0x18002c933  lea     rcx, [rbp+var_18]
0x18002c937  mov     ebx, eax
0x18002c939  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002c93e  test    ebx, ebx
0x18002c940  jnz     short loc_18002C967
0x18002c942  mov     rcx, [rbp+18h]; this
0x18002c946  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c94d  mov     edx, 315h; void *
0x18002c952  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c957  lea     rcx, [rbp+pSid]
0x18002c95b  mov     ebx, eax
0x18002c95d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c962  jmp     loc_18002C8DF
0x18002c967  mov     rbx, [rbp+pSid]
0x18002c96b  lea     rdi, [rsi+10h]
0x18002c96f  mov     rcx, rbx; pSid
0x18002c972  call    cs:__imp_GetLengthSid
0x18002c979  nop     dword ptr [rax+rax+00h]
0x18002c97e  mov     r8d, eax; Size
0x18002c981  mov     rdx, rbx; Src
0x18002c984  mov     rcx, rdi; void *
0x18002c987  call    memcpy_0
0x18002c98c  lea     rcx, [rbp+pSid]
0x18002c990  mov     [rsi+58h], rdi
0x18002c994  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002c999  mov     rcx, [rbp+StringSid]
0x18002c99d  and     [rbp+StringSid], 0
0x18002c9a2  test    rcx, rcx
0x18002c9a5  jz      short loc_18002C9B3
0x18002c9a7  call    cs:__imp_SRCache_Free
0x18002c9ae  nop     dword ptr [rax+rax+00h]
0x18002c9b3  and     [rbp+Sid], 0
0x18002c9b8  lea     rax, [rsi+60h]
0x18002c9bc  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002c9c0  mov     [rbp+var_18], rax
0x18002c9c4  lea     rdx, aPublisher; "Publisher"
0x18002c9cb  mov     [rbp+var_8], 1
0x18002c9cf  mov     rcx, r14; this
0x18002c9d2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002c9d7  lea     rcx, [rbp+var_18]
0x18002c9db  mov     ebx, eax
0x18002c9dd  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002c9e2  test    ebx, ebx
0x18002c9e4  jns     short loc_18002C9F0
0x18002c9e6  mov     edx, 31Ch
0x18002c9eb  jmp     loc_18002C875
0x18002c9f0  mov     [rsi], r15
0x18002c9f3  xor     eax, eax
0x18002c9f5  mov     rbx, [rsp+40h+arg_0]
0x18002c9fa  mov     rsi, [rsp+40h+arg_8]
0x18002c9ff  mov     rdi, [rsp+40h+arg_18]
0x18002ca04  add     rsp, 40h
0x18002ca08  pop     r15
0x18002ca0a  pop     r14
0x18002ca0c  pop     rbp
0x18002ca0d  retn
```
