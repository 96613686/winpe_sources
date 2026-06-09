# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x18002de38`
- end: `0x18002e02f`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002eb68`

## callees

- `0x180007ae0`
- `0x180007c78`
- `0x18000ee70`
- `0x1800124f4`
- `0x180018150`
- `0x1800287b4`
- `0x18002de38`
- `0x180042912`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002df92`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002df92`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002df47`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002df47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002df0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dfc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002df0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002dfc7`

## string_xrefs

- `0x18002de99`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002deeb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002df66`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002dec1`: `PackageSID`

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
0x18002de38  mov     rax, rsp
0x18002de3b  mov     [rax+8], rbx
0x18002de3f  mov     [rax+10h], rsi
0x18002de43  mov     [rax+20h], rdi
0x18002de47  mov     [rax+18h], r8
0x18002de4b  push    rbp
0x18002de4c  push    r14
0x18002de4e  push    r15
0x18002de50  mov     rbp, rsp
0x18002de53  sub     rsp, 40h
0x18002de57  and     [rbp+Sid], 0
0x18002de5c  lea     rax, [rdx+8]
0x18002de60  mov     rsi, rdx
0x18002de63  mov     [rbp+var_18], rax
0x18002de67  lea     rdx, aPackagefamilyn; "PackageFamilyName"
0x18002de6e  mov     [rbp+var_8], 1
0x18002de72  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002de76  mov     r15, r9
0x18002de79  mov     r14, rcx
0x18002de7c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002de81  lea     rcx, [rbp+var_18]
0x18002de85  mov     ebx, eax
0x18002de87  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002de8c  test    ebx, ebx
0x18002de8e  jns     short loc_18002DEAF
0x18002de90  mov     edx, 307h; void *
0x18002de95  mov     rcx, [rbp+18h]; this
0x18002de99  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dea0  mov     r9d, ebx; char *
0x18002dea3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dea8  mov     eax, ebx
0x18002deaa  jmp     loc_18002E015
0x18002deaf  and     [rbp+StringSid], 0
0x18002deb4  lea     rax, [rbp+StringSid]
0x18002deb8  and     [rbp+Sid], 0
0x18002debd  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002dec1  lea     rdx, aPackagesid; "PackageSID"
0x18002dec8  mov     [rbp+var_18], rax
0x18002decc  mov     rcx, r14; this
0x18002decf  mov     [rbp+var_8], 1
0x18002ded3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002ded8  lea     rcx, [rbp+var_18]
0x18002dedc  mov     ebx, eax
0x18002dede  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002dee3  test    ebx, ebx
0x18002dee5  jns     short loc_18002DF1B
0x18002dee7  mov     rcx, [rbp+18h]; this
0x18002deeb  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002def2  mov     r9d, ebx; char *
0x18002def5  mov     edx, 30Dh; void *
0x18002defa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002deff  mov     rcx, [rbp+StringSid]
0x18002df03  and     [rbp+StringSid], 0
0x18002df08  test    rcx, rcx
0x18002df0b  jz      short loc_18002DEA8
0x18002df0d  call    cs:__imp_SRCache_Free
0x18002df14  nop     dword ptr [rax+rax+00h]
0x18002df19  jmp     short loc_18002DEA8
0x18002df1b  mov     rcx, [rbp+StringSid]; StringSid
0x18002df1f  test    rcx, rcx
0x18002df22  jnz     short loc_18002DF2D
0x18002df24  and     [rsi+58h], rcx
0x18002df28  jmp     loc_18002DFBD
0x18002df2d  and     [rbp+pSid], 0
0x18002df32  lea     rax, [rbp+pSid]
0x18002df36  and     [rbp+Sid], 0
0x18002df3b  lea     rdx, [rbp+Sid]; Sid
0x18002df3f  mov     [rbp+var_18], rax
0x18002df43  mov     [rbp+var_8], 1
0x18002df47  call    cs:__imp_ConvertStringSidToSidW
0x18002df4e  nop     dword ptr [rax+rax+00h]
0x18002df53  lea     rcx, [rbp+var_18]
0x18002df57  mov     ebx, eax
0x18002df59  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002df5e  test    ebx, ebx
0x18002df60  jnz     short loc_18002DF87
0x18002df62  mov     rcx, [rbp+18h]; this
0x18002df66  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002df6d  mov     edx, 315h; void *
0x18002df72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002df77  lea     rcx, [rbp+pSid]
0x18002df7b  mov     ebx, eax
0x18002df7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002df82  jmp     loc_18002DEFF
0x18002df87  mov     rbx, [rbp+pSid]
0x18002df8b  lea     rdi, [rsi+10h]
0x18002df8f  mov     rcx, rbx; pSid
0x18002df92  call    cs:__imp_GetLengthSid
0x18002df99  nop     dword ptr [rax+rax+00h]
0x18002df9e  mov     r8d, eax; Size
0x18002dfa1  mov     rdx, rbx; Src
0x18002dfa4  mov     rcx, rdi; void *
0x18002dfa7  call    memcpy_0
0x18002dfac  lea     rcx, [rbp+pSid]
0x18002dfb0  mov     [rsi+58h], rdi
0x18002dfb4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dfb9  mov     rcx, [rbp+StringSid]
0x18002dfbd  and     [rbp+StringSid], 0
0x18002dfc2  test    rcx, rcx
0x18002dfc5  jz      short loc_18002DFD3
0x18002dfc7  call    cs:__imp_SRCache_Free
0x18002dfce  nop     dword ptr [rax+rax+00h]
0x18002dfd3  and     [rbp+Sid], 0
0x18002dfd8  lea     rax, [rsi+60h]
0x18002dfdc  lea     r8, [rbp+Sid]; unsigned __int16 **
0x18002dfe0  mov     [rbp+var_18], rax
0x18002dfe4  lea     rdx, aPublisher; "Publisher"
0x18002dfeb  mov     [rbp+var_8], 1
0x18002dfef  mov     rcx, r14; this
0x18002dff2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18002dff7  lea     rcx, [rbp+var_18]
0x18002dffb  mov     ebx, eax
0x18002dffd  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18002e002  test    ebx, ebx
0x18002e004  jns     short loc_18002E010
0x18002e006  mov     edx, 31Ch
0x18002e00b  jmp     loc_18002DE95
0x18002e010  mov     [rsi], r15
0x18002e013  xor     eax, eax
0x18002e015  mov     rbx, [rsp+40h+arg_0]
0x18002e01a  mov     rsi, [rsp+40h+arg_8]
0x18002e01f  mov     rdi, [rsp+40h+arg_18]
0x18002e024  add     rsp, 40h
0x18002e028  pop     r15
0x18002e02a  pop     r14
0x18002e02c  pop     rbp
0x18002e02d  retn
```
