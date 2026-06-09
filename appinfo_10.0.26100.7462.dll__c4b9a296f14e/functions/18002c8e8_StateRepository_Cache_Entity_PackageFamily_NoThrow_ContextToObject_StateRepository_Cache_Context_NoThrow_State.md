# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x18002c8e8`
- end: `0x18002cadf`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d618`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000edb0`
- `0x180012634`
- `0x180018400`
- `0x180027244`
- `0x18002c8e8`
- `0x1800449e2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ca42`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ca42`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c9f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c9f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c9bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ca77`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c9bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002ca77`

## string_xrefs

- `0x18002c949`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c99b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002ca16`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c971`: `PackageSID`

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
0x18002c8e8  mov     rax, rsp
0x18002c8eb  mov     [rax+8], rbx
0x18002c8ef  mov     [rax+10h], rsi
0x18002c8f3  mov     [rax+20h], rdi
0x18002c8f7  mov     [rax+18h], r8
0x18002c8fb  push    rbp
0x18002c8fc  push    r14
0x18002c8fe  push    r15
0x18002c900  mov     rbp, rsp
0x18002c903  sub     rsp, 40h
0x18002c907  and     [rbp+Sid], 0
0x18002c90c  lea     rax, [rdx+8]
0x18002c910  mov     rsi, rdx
0x18002c913  mov     [rbp+var_18], rax
0x18002c917  lea     rdx, aPackagefamilyn; "PackageFamilyName"
0x18002c91e  mov     [rbp+var_8], 1
0x18002c922  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002c926  mov     r15, r9
0x18002c929  mov     r14, rcx
0x18002c92c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002c931  lea     rcx, [rbp+var_18]
0x18002c935  mov     ebx, eax
0x18002c937  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002c93c  test    ebx, ebx
0x18002c93e  jns     short loc_18002C95F
0x18002c940  mov     edx, 307h; void *
0x18002c945  mov     rcx, [rbp+18h]; this
0x18002c949  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c950  mov     r9d, ebx; char *
0x18002c953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c958  mov     eax, ebx
0x18002c95a  jmp     loc_18002CAC5
0x18002c95f  and     [rbp+StringSid], 0
0x18002c964  lea     rax, [rbp+StringSid]
0x18002c968  and     [rbp+Sid], 0
0x18002c96d  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002c971  lea     rdx, aPackagesid; "PackageSID"
0x18002c978  mov     [rbp+var_18], rax
0x18002c97c  mov     rcx, r14; this
0x18002c97f  mov     [rbp+var_8], 1
0x18002c983  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002c988  lea     rcx, [rbp+var_18]
0x18002c98c  mov     ebx, eax
0x18002c98e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002c993  test    ebx, ebx
0x18002c995  jns     short loc_18002C9CB
0x18002c997  mov     rcx, [rbp+18h]; this
0x18002c99b  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c9a2  mov     r9d, ebx; char *
0x18002c9a5  mov     edx, 30Dh; void *
0x18002c9aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9af  mov     rcx, [rbp+StringSid]
0x18002c9b3  and     [rbp+StringSid], 0
0x18002c9b8  test    rcx, rcx
0x18002c9bb  jz      short loc_18002C958
0x18002c9bd  call    cs:__imp_SRCache_Free
0x18002c9c4  nop     dword ptr [rax+rax+00h]
0x18002c9c9  jmp     short loc_18002C958
0x18002c9cb  mov     rcx, [rbp+StringSid]; StringSid
0x18002c9cf  test    rcx, rcx
0x18002c9d2  jnz     short loc_18002C9DD
0x18002c9d4  and     [rsi+58h], rcx
0x18002c9d8  jmp     loc_18002CA6D
0x18002c9dd  and     [rbp+pSid], 0
0x18002c9e2  lea     rax, [rbp+pSid]
0x18002c9e6  and     [rbp+Sid], 0
0x18002c9eb  lea     rdx, [rbp+Sid]; Sid
0x18002c9ef  mov     [rbp+var_18], rax
0x18002c9f3  mov     [rbp+var_8], 1
0x18002c9f7  call    cs:__imp_ConvertStringSidToSidW
0x18002c9fe  nop     dword ptr [rax+rax+00h]
0x18002ca03  lea     rcx, [rbp+var_18]
0x18002ca07  mov     ebx, eax
0x18002ca09  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002ca0e  test    ebx, ebx
0x18002ca10  jnz     short loc_18002CA37
0x18002ca12  mov     rcx, [rbp+18h]; this
0x18002ca16  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ca1d  mov     edx, 315h; void *
0x18002ca22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ca27  lea     rcx, [rbp+pSid]
0x18002ca2b  mov     ebx, eax
0x18002ca2d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ca32  jmp     loc_18002C9AF
0x18002ca37  mov     rbx, [rbp+pSid]
0x18002ca3b  lea     rdi, [rsi+10h]
0x18002ca3f  mov     rcx, rbx; pSid
0x18002ca42  call    cs:__imp_GetLengthSid
0x18002ca49  nop     dword ptr [rax+rax+00h]
0x18002ca4e  mov     r8d, eax; Size
0x18002ca51  mov     rdx, rbx; Src
0x18002ca54  mov     rcx, rdi; void *
0x18002ca57  call    memcpy_0
0x18002ca5c  lea     rcx, [rbp+pSid]
0x18002ca60  mov     [rsi+58h], rdi
0x18002ca64  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ca69  mov     rcx, [rbp+StringSid]
0x18002ca6d  and     [rbp+StringSid], 0
0x18002ca72  test    rcx, rcx
0x18002ca75  jz      short loc_18002CA83
0x18002ca77  call    cs:__imp_SRCache_Free
0x18002ca7e  nop     dword ptr [rax+rax+00h]
0x18002ca83  and     [rbp+Sid], 0
0x18002ca88  lea     rax, [rsi+60h]
0x18002ca8c  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002ca90  mov     [rbp+var_18], rax
0x18002ca94  lea     rdx, aPublisher; "Publisher"
0x18002ca9b  mov     [rbp+var_8], 1
0x18002ca9f  mov     rcx, r14; this
0x18002caa2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002caa7  lea     rcx, [rbp+var_18]
0x18002caab  mov     ebx, eax
0x18002caad  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002cab2  test    ebx, ebx
0x18002cab4  jns     short loc_18002CAC0
0x18002cab6  mov     edx, 31Ch
0x18002cabb  jmp     loc_18002C945
0x18002cac0  mov     [rsi], r15
0x18002cac3  xor     eax, eax
0x18002cac5  mov     rbx, [rsp+40h+arg_0]
0x18002caca  mov     rsi, [rsp+40h+arg_8]
0x18002cacf  mov     rdi, [rsp+40h+arg_18]
0x18002cad4  add     rsp, 40h
0x18002cad8  pop     r15
0x18002cada  pop     r14
0x18002cadc  pop     rbp
0x18002cadd  retn
```
