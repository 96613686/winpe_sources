# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x1800197fc`
- end: `0x1800199db`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `479`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *, __int64 *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031ccc`

## callees

- `0x18000720c`
- `0x18000d930`
- `0x18000eed0`
- `0x180011414`
- `0x1800197fc`
- `0x18001a0d4`
- `0x18002b020`
- `0x180046e02`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019951`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019951`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001990c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001990c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800198d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019983`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800198d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019983`

## string_xrefs

- `0x180019855`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800198ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180019925`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18001987f`: `PackageSID`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 *a2,
        const WCHAR *a3,
        __int64 a4)
{
  int Field; // ebx
  __int64 v8; // rdx
  LPCWSTR v10; // rcx
  LPCWSTR v11; // rcx
  BOOL v12; // ebx
  const char *v13; // r9
  PSID v14; // rbx
  DWORD LengthSid; // eax
  PSID pSid; // [rsp+20h] [rbp-28h] BYREF
  __int64 *p_StringSid; // [rsp+28h] [rbp-20h] BYREF
  PSID Sid; // [rsp+30h] [rbp-18h] BYREF
  char v19; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  LPCWSTR StringSid; // [rsp+90h] [rbp+48h] BYREF

  StringSid = a3;
  Sid = 0;
  p_StringSid = a2 + 1;
  v19 = 1;
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
  p_StringSid = (__int64 *)&StringSid;
  Sid = 0;
  v19 = 1;
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
  v11 = StringSid;
  if ( StringSid )
  {
    pSid = 0;
    p_StringSid = (__int64 *)&pSid;
    Sid = 0;
    v19 = 1;
    v12 = ConvertStringSidToSidW(StringSid, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_StringSid);
    if ( !v12 )
    {
      Field = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x315,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                v13);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
LABEL_7:
      v10 = StringSid;
      StringSid = 0;
      if ( v10 )
        SRCache_Free(v10);
      return (unsigned int)Field;
    }
    v14 = pSid;
    LengthSid = GetLengthSid(pSid);
    memcpy_0(a2 + 2, v14, LengthSid);
    a2[11] = (__int64)(a2 + 2);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
    v11 = StringSid;
  }
  else
  {
    a2[11] = 0;
  }
  StringSid = 0;
  if ( v11 )
    SRCache_Free(v11);
  Sid = 0;
  p_StringSid = a2 + 12;
  v19 = 1;
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
0x1800197fc  mov     [rsp-30h+StringSid], r8
0x180019801  push    rbp
0x180019802  push    rbx
0x180019803  push    rsi
0x180019804  push    rdi
0x180019805  push    r14
0x180019807  push    r15
0x180019809  mov     rbp, rsp
0x18001980c  sub     rsp, 48h
0x180019810  lea     rax, [rdx+8]
0x180019814  mov     [rbp+Sid], 0
0x18001981c  mov     rsi, rdx
0x18001981f  mov     [rbp+var_20], rax
0x180019823  lea     rdx, aPackagefamilyn; "PackageFamilyName"
0x18001982a  mov     [rbp+var_10], 1
0x18001982e  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180019832  mov     r15, r9
0x180019835  mov     r14, rcx
0x180019838  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001983d  lea     rcx, [rbp+var_20]
0x180019841  mov     ebx, eax
0x180019843  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180019848  test    ebx, ebx
0x18001984a  jns     short loc_18001986B
0x18001984c  mov     edx, 307h; void *
0x180019851  mov     rcx, [rbp+30h]; this
0x180019855  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001985c  mov     r9d, ebx; char *
0x18001985f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019864  mov     eax, ebx
0x180019866  jmp     loc_1800199CE
0x18001986b  lea     rax, [rbp+StringSid]
0x18001986f  mov     [rbp+StringSid], 0
0x180019877  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18001987b  mov     [rbp+var_20], rax
0x18001987f  lea     rdx, aPackagesid; "PackageSID"
0x180019886  mov     [rbp+Sid], 0
0x18001988e  mov     rcx, r14; this
0x180019891  mov     [rbp+var_10], 1
0x180019895  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001989a  lea     rcx, [rbp+var_20]
0x18001989e  mov     ebx, eax
0x1800198a0  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800198a5  test    ebx, ebx
0x1800198a7  jns     short loc_1800198DA
0x1800198a9  mov     rcx, [rbp+30h]; this
0x1800198ad  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800198b4  mov     r9d, ebx; char *
0x1800198b7  mov     edx, 30Dh; void *
0x1800198bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198c1  mov     rcx, [rbp+StringSid]
0x1800198c5  mov     [rbp+StringSid], 0
0x1800198cd  test    rcx, rcx
0x1800198d0  jz      short loc_180019864
0x1800198d2  call    cs:__imp_SRCache_Free
0x1800198d8  jmp     short loc_180019864
0x1800198da  mov     rcx, [rbp+StringSid]; StringSid
0x1800198de  test    rcx, rcx
0x1800198e1  jnz     short loc_1800198EC
0x1800198e3  mov     [rsi+58h], rcx
0x1800198e7  jmp     loc_180019976
0x1800198ec  lea     rax, [rbp+pSid]
0x1800198f0  mov     [rbp+pSid], 0
0x1800198f8  lea     rdx, [rbp+Sid]; Sid
0x1800198fc  mov     [rbp+var_20], rax
0x180019900  mov     [rbp+Sid], 0
0x180019908  mov     [rbp+var_10], 1
0x18001990c  call    cs:__imp_ConvertStringSidToSidW
0x180019912  lea     rcx, [rbp+var_20]
0x180019916  mov     ebx, eax
0x180019918  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18001991d  test    ebx, ebx
0x18001991f  jnz     short loc_180019946
0x180019921  mov     rcx, [rbp+30h]; this
0x180019925  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001992c  mov     edx, 315h; void *
0x180019931  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019936  lea     rcx, [rbp+pSid]
0x18001993a  mov     ebx, eax
0x18001993c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019941  jmp     loc_1800198C1
0x180019946  mov     rbx, [rbp+pSid]
0x18001994a  lea     rdi, [rsi+10h]
0x18001994e  mov     rcx, rbx; pSid
0x180019951  call    cs:__imp_GetLengthSid
0x180019957  mov     r8d, eax; Size
0x18001995a  mov     rdx, rbx; Src
0x18001995d  mov     rcx, rdi; void *
0x180019960  call    memcpy_0
0x180019965  lea     rcx, [rbp+pSid]
0x180019969  mov     [rsi+58h], rdi
0x18001996d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180019972  mov     rcx, [rbp+StringSid]
0x180019976  mov     [rbp+StringSid], 0
0x18001997e  test    rcx, rcx
0x180019981  jz      short loc_180019989
0x180019983  call    cs:__imp_SRCache_Free
0x180019989  lea     rax, [rsi+60h]
0x18001998d  mov     [rbp+Sid], 0
0x180019995  lea     r8, [rbp+Sid]; unsigned __int16 **
0x180019999  mov     [rbp+var_20], rax
0x18001999d  lea     rdx, aPublisher; "Publisher"
0x1800199a4  mov     [rbp+var_10], 1
0x1800199a8  mov     rcx, r14; this
0x1800199ab  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800199b0  lea     rcx, [rbp+var_20]
0x1800199b4  mov     ebx, eax
0x1800199b6  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800199bb  test    ebx, ebx
0x1800199bd  jns     short loc_1800199C9
0x1800199bf  mov     edx, 31Ch
0x1800199c4  jmp     loc_180019851
0x1800199c9  mov     [rsi], r15
0x1800199cc  xor     eax, eax
0x1800199ce  add     rsp, 48h
0x1800199d2  pop     r15
0x1800199d4  pop     r14
0x1800199d6  pop     rdi
0x1800199d7  pop     rsi
0x1800199d8  pop     rbx
0x1800199d9  pop     rbp
0x1800199da  retn
```
