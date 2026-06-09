# StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)

- ea: `0x180049460`
- end: `0x1800496d1`
- name: `?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `625`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c020`
- `0x1800496e0`
- `0x1800f5ed4`

## callees

- `0x1800220f0`
- `0x180028d1c`
- `0x18002fba0`
- `0x180049460`
- `0x18004cb70`
- `0x180058768`
- `0x1800cab48`
- `0x1800f42bc`
- `0x180188eb9`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800495a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800495a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18004950a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18004950a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800494d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049536`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004955a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800496a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800494d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049536`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004955a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049631`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800496a7`

## string_xrefs

- `0x18004966c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180049686`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800496b3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800494f7`: `PackageSID`
- `0x18004964a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int Field_String; // eax
  __int64 v12; // rcx
  LPCWSTR v13; // rcx
  BOOL v15; // ebx
  const char *v16; // r9
  PSID v17; // rbx
  DWORD LengthSid; // eax
  PSID v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  LPCWSTR v22; // rcx
  PSID pSid; // [rsp+20h] [rbp-28h] BYREF
  __int64 *p_StringSid; // [rsp+28h] [rbp-20h] BYREF
  PSID Sid; // [rsp+30h] [rbp-18h] BYREF
  char v26; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  LPCWSTR StringSid; // [rsp+A0h] [rbp+58h] BYREF

  if ( a3 && (a3 & 1) == 0 )
  {
LABEL_3:
    if ( (a3 & 2) == 0 )
      goto LABEL_21;
LABEL_10:
    v10 = *(_QWORD *)a1;
    p_StringSid = (__int64 *)&StringSid;
    StringSid = 0;
    Sid = 0;
    v26 = 1;
    Field_String = SRCacheContext_GetField_String(v10, L"PackageSID", &Sid);
    Field = Field_String;
    if ( Field_String < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_String,
        (int)pSid);
    else
      Field = 0;
    if ( v26 )
    {
      v12 = *p_StringSid;
      *p_StringSid = (__int64)Sid;
      if ( v12 )
        SRCache_Free(v12);
    }
    if ( Field < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)(unsigned int)Field,
        (int)pSid);
    }
    else
    {
      v13 = StringSid;
      if ( !StringSid )
      {
        a2[11] = 0;
        goto LABEL_18;
      }
      pSid = 0;
      p_StringSid = (__int64 *)&pSid;
      Sid = 0;
      v26 = 1;
      v15 = ConvertStringSidToSidW(StringSid, &Sid);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_StringSid);
      if ( v15 )
      {
        v17 = pSid;
        LengthSid = GetLengthSid(pSid);
        memcpy_0(a2 + 2, v17, LengthSid);
        v19 = pSid;
        a2[11] = (__int64)(a2 + 2);
        if ( v19 )
          LocalFree(v19);
        v13 = StringSid;
LABEL_18:
        StringSid = 0;
        if ( v13 )
          SRCache_Free(v13);
        if ( !a3 )
        {
LABEL_27:
          Sid = 0;
          p_StringSid = a2 + 12;
          v26 = 1;
          Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Publisher", (unsigned __int16 **)&Sid);
          if ( v26 )
          {
            v20 = *p_StringSid;
            *p_StringSid = (__int64)Sid;
            if ( v20 )
              SRCache_Free(v20);
          }
          if ( Field >= 0 )
            goto LABEL_22;
          v21 = 796;
          goto LABEL_34;
        }
LABEL_21:
        if ( (a3 & 4) == 0 )
        {
LABEL_22:
          *a2 = a4;
          return 0;
        }
        goto LABEL_27;
      }
      Field = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x315,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
                v16);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
    }
    v22 = StringSid;
    StringSid = 0;
    if ( v22 )
      SRCache_Free(v22);
    return (unsigned int)Field;
  }
  Sid = 0;
  p_StringSid = a2 + 1;
  v26 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamilyName", (unsigned __int16 **)&Sid);
  if ( v26 )
  {
    v9 = *p_StringSid;
    *p_StringSid = (__int64)Sid;
    if ( v9 )
      SRCache_Free(v9);
  }
  if ( Field >= 0 )
  {
    if ( !a3 )
      goto LABEL_10;
    goto LABEL_3;
  }
  v21 = 775;
LABEL_34:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
    (const char *)(unsigned int)Field,
    (int)pSid);
  return (unsigned int)Field;
}

```

## disassembly

```asm
0x180049460  push    rbp
0x180049462  push    rbx
0x180049463  push    rsi
0x180049464  push    rdi
0x180049465  push    r12
0x180049467  push    r13
0x180049469  push    r14
0x18004946b  push    r15
0x18004946d  mov     rbp, rsp
0x180049470  sub     rsp, 48h
0x180049474  xor     r13d, r13d
0x180049477  mov     r12, r9
0x18004947a  mov     rsi, r8
0x18004947d  mov     r14, rdx
0x180049480  mov     r15, rcx
0x180049483  test    r8, r8
0x180049486  jz      short loc_18004949A
0x180049488  test    sil, 1
0x18004948c  jnz     short loc_18004949A
0x18004948e  test    sil, 2
0x180049492  jz      loc_180049569
0x180049498  jmp     short loc_1800494E8
0x18004949a  lea     rax, [rdx+8]
0x18004949e  mov     [rbp+Sid], r13
0x1800494a2  lea     rdx, aPackagefamilyn_9; "PackageFamilyName"
0x1800494a9  mov     [rbp+var_20], rax
0x1800494ad  lea     r8, [rbp+Sid]; unsigned __int16 **
0x1800494b1  mov     [rbp+var_10], 1
0x1800494b5  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800494ba  mov     ebx, eax
0x1800494bc  cmp     [rbp+var_10], r13b
0x1800494c0  jz      short loc_1800494DB
0x1800494c2  mov     r8, [rbp+var_20]
0x1800494c6  mov     rdx, [rbp+Sid]
0x1800494ca  mov     rcx, [r8]
0x1800494cd  mov     [r8], rdx
0x1800494d0  test    rcx, rcx
0x1800494d3  jz      short loc_1800494DB
0x1800494d5  call    cs:__imp_SRCache_Free
0x1800494db  test    ebx, ebx
0x1800494dd  js      loc_180049663
0x1800494e3  test    rsi, rsi
0x1800494e6  jnz     short loc_18004948E
0x1800494e8  mov     rcx, [r15]
0x1800494eb  lea     rax, [rbp+StringSid]
0x1800494ef  lea     r8, [rbp+Sid]
0x1800494f3  mov     [rbp+var_20], rax
0x1800494f7  lea     rdx, aPackagesid; "PackageSID"
0x1800494fe  mov     [rbp+StringSid], r13
0x180049502  mov     [rbp+Sid], r13
0x180049506  mov     [rbp+var_10], 1
0x18004950a  call    cs:__imp_SRCacheContext_GetField_String
0x180049510  mov     ebx, eax
0x180049512  test    eax, eax
0x180049514  js      loc_180049646
0x18004951a  mov     ebx, r13d
0x18004951d  cmp     [rbp+var_10], r13b
0x180049521  jz      short loc_18004953C
0x180049523  mov     rdx, [rbp+var_20]
0x180049527  mov     rax, [rbp+Sid]
0x18004952b  mov     rcx, [rdx]
0x18004952e  mov     [rdx], rax
0x180049531  test    rcx, rcx
0x180049534  jz      short loc_18004953C
0x180049536  call    cs:__imp_SRCache_Free
0x18004953c  test    ebx, ebx
0x18004953e  js      loc_180049682
0x180049544  mov     rcx, [rbp+StringSid]; StringSid
0x180049548  test    rcx, rcx
0x18004954b  jnz     short loc_180049589
0x18004954d  mov     [r14+58h], r13
0x180049551  mov     [rbp+StringSid], r13
0x180049555  test    rcx, rcx
0x180049558  jz      short loc_180049560
0x18004955a  call    cs:__imp_SRCache_Free
0x180049560  test    rsi, rsi
0x180049563  jz      loc_1800495F3
0x180049569  test    sil, 4
0x18004956d  jnz     loc_1800495F3
0x180049573  mov     [r14], r12
0x180049576  xor     eax, eax
0x180049578  add     rsp, 48h
0x18004957c  pop     r15
0x18004957e  pop     r14
0x180049580  pop     r13
0x180049582  pop     r12
0x180049584  pop     rdi
0x180049585  pop     rsi
0x180049586  pop     rbx
0x180049587  pop     rbp
0x180049588  retn
0x180049589  lea     rax, [rbp+pSid]
0x18004958d  mov     [rbp+pSid], r13
0x180049591  lea     rdx, [rbp+Sid]; Sid
0x180049595  mov     [rbp+var_20], rax
0x180049599  mov     [rbp+Sid], r13
0x18004959d  mov     [rbp+var_10], 1
0x1800495a1  call    cs:__imp_ConvertStringSidToSidW
0x1800495a7  lea     rcx, [rbp+var_20]
0x1800495ab  mov     ebx, eax
0x1800495ad  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800495b2  test    ebx, ebx
0x1800495b4  jz      loc_1800496AF
0x1800495ba  mov     rbx, [rbp+pSid]
0x1800495be  lea     rdi, [r14+10h]
0x1800495c2  mov     rcx, rbx; pSid
0x1800495c5  call    GetLengthSid
0x1800495ca  mov     r8d, eax; Size
0x1800495cd  mov     rdx, rbx; Src
0x1800495d0  mov     rcx, rdi; void *
0x1800495d3  call    memcpy_0
0x1800495d8  mov     rcx, [rbp+pSid]; hMem
0x1800495dc  mov     [r14+58h], rdi
0x1800495e0  test    rcx, rcx
0x1800495e3  jz      short loc_1800495EA
0x1800495e5  call    LocalFree
0x1800495ea  mov     rcx, [rbp+StringSid]
0x1800495ee  jmp     loc_180049551
0x1800495f3  lea     rax, [r14+60h]
0x1800495f7  mov     [rbp+Sid], r13
0x1800495fb  lea     r8, [rbp+Sid]; unsigned __int16 **
0x1800495ff  mov     [rbp+var_20], rax
0x180049603  lea     rdx, aPublisher; "Publisher"
0x18004960a  mov     [rbp+var_10], 1
0x18004960e  mov     rcx, r15; this
0x180049611  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180049616  mov     ebx, eax
0x180049618  cmp     [rbp+var_10], r13b
0x18004961c  jz      short loc_180049637
0x18004961e  mov     r8, [rbp+var_20]
0x180049622  mov     rdx, [rbp+Sid]
0x180049626  mov     rcx, [r8]
0x180049629  mov     [r8], rdx
0x18004962c  test    rcx, rcx
0x18004962f  jz      short loc_180049637
0x180049631  call    cs:__imp_SRCache_Free
0x180049637  test    ebx, ebx
0x180049639  jns     loc_180049573
0x18004963f  mov     edx, 31Ch
0x180049644  jmp     short loc_180049668
0x180049646  mov     rcx, [rbp+40h]; this
0x18004964a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049651  mov     r9d, eax; char *
0x180049654  mov     edx, 246h; void *
0x180049659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004965e  jmp     loc_18004951D
0x180049663  mov     edx, 307h; void *
0x180049668  mov     rcx, [rbp+40h]; this
0x18004966c  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049673  mov     r9d, ebx; char *
0x180049676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004967b  mov     eax, ebx
0x18004967d  jmp     loc_180049578
0x180049682  mov     rcx, [rbp+40h]; this
0x180049686  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004968d  mov     r9d, ebx; char *
0x180049690  mov     edx, 30Dh; void *
0x180049695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004969a  mov     rcx, [rbp+StringSid]
0x18004969e  mov     [rbp+StringSid], r13
0x1800496a2  test    rcx, rcx
0x1800496a5  jz      short loc_18004967B
0x1800496a7  call    cs:__imp_SRCache_Free
0x1800496ad  jmp     short loc_18004967B
0x1800496af  mov     rcx, [rbp+40h]; this
0x1800496b3  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800496ba  mov     edx, 315h; void *
0x1800496bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800496c4  lea     rcx, [rbp+pSid]
0x1800496c8  mov     ebx, eax
0x1800496ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800496cf  jmp     short loc_18004969A
```
