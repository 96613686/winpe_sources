# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)

- ea: `0x180018eb8`
- end: `0x180019427`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `1391`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800182fc`
- `0x1800526e0`

## callees

- `0x1800183c4`
- `0x180018be0`
- `0x180018eb8`
- `0x18001a1f0`
- `0x18006bf84`
- `0x18006bfa4`
- `0x18006db64`
- `0x18006de58`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800192c5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800192c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019286`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800192e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019412`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800192e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019412`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180018f52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180018f52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018f76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001902c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800190ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800190ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001912a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019356`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800193a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018f76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001902c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800190ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800190ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001912a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019356`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800193a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180019008`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180019008`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800190a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019232`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019259`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019322`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019390`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800193eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800190a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019232`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019259`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019322`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019390`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800193eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019203`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180019203`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180019050`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180019050`

## string_xrefs

- `0x180019067`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019177`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001919c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180019368`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001908a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800190c7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180019100`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800191bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800192ff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001932f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800193bb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800191f2`: `UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 *a4,
        bool *a5)
{
  int LastError; // ebx
  unsigned __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  LPCWSTR v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  __int64 v17; // rcx
  LPCWSTR v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int Field_String; // eax
  __int64 v25; // rcx
  LPCWSTR v26; // rcx
  const char *v27; // r9
  BOOL v28; // r15d
  __int64 *v29; // rbx
  PSID v30; // r14
  void *v31; // rdi
  PSID v32; // rbx
  DWORD LengthSid; // eax
  PSID v34; // rcx
  LPCWSTR v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  LPCWSTR v38; // rcx
  LPCWSTR v39; // rcx
  LPCWSTR StringSid; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v41; // [rsp+28h] [rbp-D8h] BYREF
  __int64 *p_StringSid; // [rsp+30h] [rbp-D0h]
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  char v44; // [rsp+40h] [rbp-C0h]
  PSID pSid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v47[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v49[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+268h] [rbp+168h]
  __int64 v51; // [rsp+270h] [rbp+170h]
  _BYTE *v52; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v46 = 0;
  *a5 = 0;
  LastError = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, a2, (__int64 *)&v46);
  if ( LastError < 0 )
  {
    v20 = 245;
    goto LABEL_24;
  }
  v8 = v46;
  if ( !v46 )
    return 0;
  v9 = *(_QWORD *)a1;
  p_StringSid = (__int64 *)&StringSid;
  v41 = 0;
  StringSid = 0;
  Sid = 0;
  v44 = 1;
  LastError = SRCacheContext_Open(v9, L"User\\Data", 0, &Sid);
  if ( v44 )
  {
    v10 = *p_StringSid;
    *p_StringSid = (__int64)Sid;
    if ( v10 )
      SRCacheContext_Close(v10);
  }
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)LastError,
      (int)StringSid);
    v23 = 267;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)LastError,
      (int)StringSid);
    goto LABEL_18;
  }
  if ( !StringSid )
  {
    LastError = -2140733422;
    v23 = 268;
    goto LABEL_34;
  }
  v48 = 0;
  memset_0(v49, 0, sizeof(v49));
  v50 = 0;
  v52 = v49;
  v51 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v48, v8);
  LastError = v11;
  if ( v11 >= 0 )
  {
    p_StringSid = &v41;
    Sid = 0;
    v44 = 1;
    LastError = SRCacheContext_OpenSubContext(StringSid, v52, 0, &Sid);
    if ( v44 )
    {
      v12 = *p_StringSid;
      *p_StringSid = (__int64)Sid;
      if ( v12 )
        SRCacheContext_Close(v12);
    }
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)LastError,
        (int)StringSid);
      v15 = 272;
      goto LABEL_15;
    }
    v13 = StringSid;
    *a5 = v41 != 0;
    v14 = SRCacheContext_AddToCache(v13, L"User\\Data");
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v14,
        (int)StringSid);
      v15 = 274;
LABEL_15:
      v16 = (unsigned int)LastError;
      goto LABEL_16;
    }
    v37 = v48;
    v48 = 0;
    if ( v37 )
      SRCache_Free(v37);
    v38 = StringSid;
    StringSid = 0;
    if ( v38 )
      SRCacheContext_Close(v38);
    v22 = v41;
    if ( !*a5 )
    {
LABEL_27:
      v41 = 0;
      if ( v22 )
        SRCacheContext_Close(v22);
      return 0;
    }
    StringSid = 0;
    p_StringSid = (__int64 *)&StringSid;
    Sid = 0;
    v44 = 1;
    Field_String = SRCacheContext_GetField_String(v41, L"UserSid", &Sid);
    LastError = Field_String;
    if ( Field_String < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_String,
        (int)StringSid);
    else
      LastError = 0;
    if ( v44 )
    {
      v25 = *p_StringSid;
      *p_StringSid = (__int64)Sid;
      if ( v25 )
        SRCache_Free(v25);
    }
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x347,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)LastError,
        (int)StringSid);
      v35 = StringSid;
      StringSid = 0;
      if ( v35 )
        SRCache_Free(v35);
    }
    else
    {
      v26 = StringSid;
      if ( !StringSid )
      {
        a4[10] = 0;
LABEL_44:
        StringSid = 0;
        if ( v26 )
          SRCache_Free(v26);
        *a4 = v8;
LABEL_26:
        v22 = v41;
        goto LABEL_27;
      }
      pSid = 0;
      p_StringSid = (__int64 *)&pSid;
      Sid = 0;
      v44 = 1;
      v28 = ConvertStringSidToSidW(StringSid, &Sid);
      if ( v44 )
      {
        v29 = p_StringSid;
        v30 = Sid;
        v31 = (void *)*p_StringSid;
        if ( *p_StringSid )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v47);
          LocalFree(v31);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v47);
        }
        *v29 = (__int64)v30;
      }
      if ( v28 )
      {
        v32 = pSid;
        LengthSid = GetLengthSid(pSid);
        memcpy_0(a4 + 1, v32, LengthSid);
        v34 = pSid;
        a4[10] = (unsigned __int64)(a4 + 1);
        if ( v34 )
          LocalFree(v34);
        v26 = StringSid;
        goto LABEL_44;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x34F,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                    v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid);
      v39 = StringSid;
      StringSid = 0;
      if ( v39 )
        SRCache_Free(v39);
      if ( LastError >= 0 )
        goto LABEL_26;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)LastError,
      (int)StringSid);
    v36 = v41;
    v41 = 0;
    if ( v36 )
      SRCacheContext_Close(v36);
    goto LABEL_23;
  }
  v16 = (unsigned int)v11;
  v15 = 271;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
    (const char *)v16,
    (int)StringSid);
  v17 = v48;
  v48 = 0;
  if ( v17 )
    SRCache_Free(v17);
LABEL_18:
  v18 = StringSid;
  StringSid = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9B,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
    (const char *)(unsigned int)LastError,
    (int)StringSid);
  v19 = v41;
  v41 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  if ( LastError < 0 )
  {
LABEL_23:
    v20 = 248;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)LastError,
      (int)StringSid);
    return (unsigned int)LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x180018eb8  mov     [rsp-8+arg_10], rbx
0x180018ebd  push    rbp
0x180018ebe  push    rsi
0x180018ebf  push    rdi
0x180018ec0  push    r12
0x180018ec2  push    r13
0x180018ec4  push    r14
0x180018ec6  push    r15
0x180018ec8  lea     rbp, [rsp-190h]
0x180018ed0  sub     rsp, 290h
0x180018ed7  mov     rax, cs:__security_cookie
0x180018ede  xor     rax, rsp
0x180018ee1  mov     [rbp+1C0h+var_40], rax
0x180018ee8  mov     rdi, [rbp+1C0h+arg_20]
0x180018eef  lea     r8, [rsp+2C0h+var_270]; __int64 *
0x180018ef4  xor     r13d, r13d
0x180018ef7  mov     r12, r9
0x180018efa  mov     r14, rcx
0x180018efd  mov     [rsp+2C0h+var_270], r13
0x180018f02  mov     [rdi], r13b
0x180018f05  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180018f0a  mov     ebx, eax
0x180018f0c  test    eax, eax
0x180018f0e  js      loc_180019169
0x180018f14  mov     rsi, [rsp+2C0h+var_270]
0x180018f19  test    rsi, rsi
0x180018f1c  jz      loc_180019130
0x180018f22  mov     rcx, [r14]
0x180018f25  lea     rax, [rsp+2C0h+StringSid]
0x180018f2a  lea     r9, [rsp+2C0h+Sid]
0x180018f2f  mov     [rsp+2C0h+var_290], rax
0x180018f34  xor     r8d, r8d
0x180018f37  mov     [rsp+2C0h+var_298], r13
0x180018f3c  lea     rdx, aUserData; "User\\Data"
0x180018f43  mov     [rsp+2C0h+StringSid], r13; int
0x180018f48  mov     [rsp+2C0h+Sid], r13
0x180018f4d  mov     [rsp+2C0h+var_280], 1
0x180018f52  call    cs:__imp_SRCacheContext_Open
0x180018f58  mov     ebx, eax
0x180018f5a  cmp     [rsp+2C0h+var_280], r13b
0x180018f5f  jz      short loc_180018F7C
0x180018f61  mov     rdx, [rsp+2C0h+var_290]
0x180018f66  mov     rax, [rsp+2C0h+Sid]
0x180018f6b  mov     rcx, [rdx]
0x180018f6e  mov     [rdx], rax
0x180018f71  test    rcx, rcx
0x180018f74  jz      short loc_180018F7C
0x180018f76  call    cs:__imp_SRCacheContext_Close
0x180018f7c  test    ebx, ebx
0x180018f7e  js      loc_180019195
0x180018f84  cmp     [rsp+2C0h+StringSid], r13
0x180018f89  setnz   al
0x180018f8c  test    al, al
0x180018f8e  jz      loc_1800193F6
0x180018f94  xor     edx, edx; Val
0x180018f96  mov     [rsp+2C0h+var_260], r13
0x180018f9b  mov     r8d, 200h; Size
0x180018fa1  lea     rcx, [rsp+2C0h+var_258]; void *
0x180018fa6  call    memset_0
0x180018fab  lea     rax, [rsp+2C0h+var_258]
0x180018fb0  mov     [rbp+1C0h+var_58], r13
0x180018fb7  mov     rdx, rsi; unsigned __int64
0x180018fba  mov     [rbp+1C0h+var_48], rax
0x180018fc1  lea     rcx, [rsp+2C0h+var_260]; this
0x180018fc6  mov     [rbp+1C0h+var_50], 100h
0x180018fd1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180018fd6  mov     ebx, eax
0x180018fd8  test    eax, eax
0x180018fda  js      loc_18001915C
0x180018fe0  mov     rdx, [rbp+1C0h+var_48]
0x180018fe7  lea     rax, [rsp+2C0h+var_298]
0x180018fec  mov     rcx, [rsp+2C0h+StringSid]
0x180018ff1  lea     r9, [rsp+2C0h+Sid]
0x180018ff6  xor     r8d, r8d
0x180018ff9  mov     [rsp+2C0h+var_290], rax
0x180018ffe  mov     [rsp+2C0h+Sid], r13
0x180019003  mov     [rsp+2C0h+var_280], 1
0x180019008  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001900e  mov     ebx, eax
0x180019010  cmp     [rsp+2C0h+var_280], r13b
0x180019015  jz      short loc_180019032
0x180019017  mov     rdx, [rsp+2C0h+var_290]
0x18001901c  mov     rax, [rsp+2C0h+Sid]
0x180019021  mov     rcx, [rdx]
0x180019024  mov     [rdx], rax
0x180019027  test    rcx, rcx
0x18001902a  jz      short loc_180019032
0x18001902c  call    cs:__imp_SRCacheContext_Close
0x180019032  test    ebx, ebx
0x180019034  js      loc_180019170
0x18001903a  cmp     [rsp+2C0h+var_298], r13
0x18001903f  lea     rdx, aUserData; "User\\Data"
0x180019046  mov     rcx, [rsp+2C0h+StringSid]
0x18001904b  setnz   al
0x18001904e  mov     [rdi], al
0x180019050  call    cs:__imp_SRCacheContext_AddToCache
0x180019056  mov     ebx, eax
0x180019058  test    eax, eax
0x18001905a  jns     loc_180019381
0x180019060  mov     rcx, [rbp+1C8h]; this
0x180019067  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001906e  mov     r9d, eax; char *
0x180019071  mov     edx, 1A6h; void *
0x180019076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001907b  mov     edx, 112h; void *
0x180019080  mov     r9d, ebx; char *
0x180019083  mov     rcx, [rbp+1C8h]; this
0x18001908a  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019096  mov     rcx, [rsp+2C0h+var_260]
0x18001909b  mov     [rsp+2C0h+var_260], r13
0x1800190a0  test    rcx, rcx
0x1800190a3  jz      short loc_1800190AB
0x1800190a5  call    cs:__imp_SRCache_Free
0x1800190ab  mov     rcx, [rsp+2C0h+StringSid]
0x1800190b0  mov     [rsp+2C0h+StringSid], r13; int
0x1800190b5  test    rcx, rcx
0x1800190b8  jz      short loc_1800190C0
0x1800190ba  call    cs:__imp_SRCacheContext_Close
0x1800190c0  mov     rcx, [rbp+1C8h]; this
0x1800190c7  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800190ce  mov     r9d, ebx; char *
0x1800190d1  mov     edx, 9Bh; void *
0x1800190d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800190db  mov     rcx, [rsp+2C0h+var_298]
0x1800190e0  mov     [rsp+2C0h+var_298], r13
0x1800190e5  test    rcx, rcx
0x1800190e8  jz      short loc_1800190F0
0x1800190ea  call    cs:__imp_SRCacheContext_Close
0x1800190f0  test    ebx, ebx
0x1800190f2  jns     short loc_180019130
0x1800190f4  mov     edx, 0F8h; void *
0x1800190f9  mov     rcx, [rbp+1C8h]; this
0x180019100  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019107  mov     r9d, ebx; char *
0x18001910a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001910f  mov     eax, ebx
0x180019111  jmp     short loc_180019132
0x180019113  test    ebx, ebx
0x180019115  js      loc_180019328
0x18001911b  mov     rcx, [rsp+2C0h+var_298]
0x180019120  mov     [rsp+2C0h+var_298], r13
0x180019125  test    rcx, rcx
0x180019128  jz      short loc_180019130
0x18001912a  call    cs:__imp_SRCacheContext_Close
0x180019130  xor     eax, eax
0x180019132  mov     rcx, [rbp+1C0h+var_40]
0x180019139  xor     rcx, rsp; StackCookie
0x18001913c  call    __security_check_cookie
0x180019141  mov     rbx, [rsp+2C0h+arg_10]
0x180019149  add     rsp, 290h
0x180019150  pop     r15
0x180019152  pop     r14
0x180019154  pop     r13
0x180019156  pop     r12
0x180019158  pop     rdi
0x180019159  pop     rsi
0x18001915a  pop     rbp
0x18001915b  retn
0x18001915c  mov     r9d, eax
0x18001915f  mov     edx, 10Fh
0x180019164  jmp     loc_180019083
0x180019169  mov     edx, 0F5h
0x18001916e  jmp     short loc_1800190F9
0x180019170  mov     rcx, [rbp+1C8h]; this
0x180019177  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001917e  mov     r9d, ebx; char *
0x180019181  mov     edx, 1B0h; void *
0x180019186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001918b  mov     edx, 110h
0x180019190  jmp     loc_180019080
0x180019195  mov     rcx, [rbp+1C8h]; this
0x18001919c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800191a3  mov     r9d, ebx; char *
0x1800191a6  mov     edx, 18Ch; void *
0x1800191ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800191b0  mov     edx, 10Bh; void *
0x1800191b5  mov     rcx, [rbp+1C8h]; this
0x1800191bc  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800191c3  mov     r9d, ebx; char *
0x1800191c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800191cb  jmp     loc_1800190AB
0x1800191d0  mov     rcx, [rsp+2C0h+var_298]
0x1800191d5  cmp     [rdi], r13b
0x1800191d8  jz      loc_180019120
0x1800191de  lea     rax, [rsp+2C0h+StringSid]
0x1800191e3  mov     [rsp+2C0h+StringSid], r13; int
0x1800191e8  lea     r8, [rsp+2C0h+Sid]
0x1800191ed  mov     [rsp+2C0h+var_290], rax
0x1800191f2  lea     rdx, aUsersid; "UserSid"
0x1800191f9  mov     [rsp+2C0h+Sid], r13
0x1800191fe  mov     [rsp+2C0h+var_280], 1
0x180019203  call    cs:__imp_SRCacheContext_GetField_String
0x180019209  mov     ebx, eax
0x18001920b  test    eax, eax
0x18001920d  js      loc_180019361
0x180019213  mov     ebx, r13d
0x180019216  cmp     [rsp+2C0h+var_280], r13b
0x18001921b  jz      short loc_180019238
0x18001921d  mov     rdx, [rsp+2C0h+var_290]
0x180019222  mov     rax, [rsp+2C0h+Sid]
0x180019227  mov     rcx, [rdx]
0x18001922a  mov     [rdx], rax
0x18001922d  test    rcx, rcx
0x180019230  jz      short loc_180019238
0x180019232  call    cs:__imp_SRCache_Free
0x180019238  test    ebx, ebx
0x18001923a  js      loc_1800192F8
0x180019240  mov     rcx, [rsp+2C0h+StringSid]; StringSid
0x180019245  test    rcx, rcx
0x180019248  jnz     short loc_180019268
0x18001924a  mov     [r12+50h], r13
0x18001924f  mov     [rsp+2C0h+StringSid], r13
0x180019254  test    rcx, rcx
0x180019257  jz      short loc_18001925F
0x180019259  call    cs:__imp_SRCache_Free
0x18001925f  mov     [r12], rsi
0x180019263  jmp     loc_18001911B
0x180019268  lea     rax, [rsp+2C0h+pSid]
0x18001926d  mov     [rsp+2C0h+pSid], r13
0x180019272  lea     rdx, [rsp+2C0h+Sid]; Sid
0x180019277  mov     [rsp+2C0h+var_290], rax
0x18001927c  mov     [rsp+2C0h+Sid], r13
0x180019281  mov     [rsp+2C0h+var_280], 1
0x180019286  call    cs:__imp_ConvertStringSidToSidW
0x18001928c  mov     r15d, eax
0x18001928f  cmp     [rsp+2C0h+var_280], r13b
0x180019294  jz      short loc_1800192AF
0x180019296  mov     rbx, [rsp+2C0h+var_290]
0x18001929b  mov     r14, [rsp+2C0h+Sid]
0x1800192a0  mov     rdi, [rbx]
0x1800192a3  test    rdi, rdi
0x1800192a6  jnz     loc_180019405
0x1800192ac  mov     [rbx], r14
0x1800192af  test    r15d, r15d
0x1800192b2  jz      loc_1800193B4
0x1800192b8  mov     rbx, [rsp+2C0h+pSid]
0x1800192bd  lea     rdi, [r12+8]
0x1800192c2  mov     rcx, rbx; pSid
0x1800192c5  call    cs:__imp_GetLengthSid
0x1800192cb  mov     r8d, eax; Size
0x1800192ce  mov     rdx, rbx; Src
0x1800192d1  mov     rcx, rdi; void *
0x1800192d4  call    memcpy_0
0x1800192d9  mov     rcx, [rsp+2C0h+pSid]; hMem
0x1800192de  mov     [r12+50h], rdi
0x1800192e3  test    rcx, rcx
0x1800192e6  jz      short loc_1800192EE
0x1800192e8  call    cs:__imp_LocalFree
0x1800192ee  mov     rcx, [rsp+2C0h+StringSid]
0x1800192f3  jmp     loc_18001924F
0x1800192f8  mov     rcx, [rbp+1C8h]; this
0x1800192ff  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019306  mov     r9d, ebx; char *
0x180019309  mov     edx, 347h; void *
0x18001930e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019313  mov     rcx, [rsp+2C0h+StringSid]
0x180019318  mov     [rsp+2C0h+StringSid], r13; int
0x18001931d  test    rcx, rcx
0x180019320  jz      short loc_180019328
0x180019322  call    cs:__imp_SRCache_Free
0x180019328  mov     rcx, [rbp+1C8h]; this
0x18001932f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019336  mov     r9d, ebx; char *
0x180019339  mov     edx, 0A0h; void *
0x18001933e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019343  mov     rcx, [rsp+2C0h+var_298]
0x180019348  mov     [rsp+2C0h+var_298], r13
0x18001934d  test    rcx, rcx
0x180019350  jz      loc_1800190F4
0x180019356  call    cs:__imp_SRCacheContext_Close
0x18001935c  jmp     loc_1800190F4
0x180019361  mov     rcx, [rbp+1C8h]; this
0x180019368  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001936f  mov     r9d, eax; char *
0x180019372  mov     edx, 246h; void *
0x180019377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001937c  jmp     loc_180019216
0x180019381  mov     rcx, [rsp+2C0h+var_260]
0x180019386  mov     [rsp+2C0h+var_260], r13
0x18001938b  test    rcx, rcx
0x18001938e  jz      short loc_180019396
0x180019390  call    cs:__imp_SRCache_Free
0x180019396  mov     rcx, [rsp+2C0h+StringSid]
0x18001939b  mov     [rsp+2C0h+StringSid], r13
0x1800193a0  test    rcx, rcx
0x1800193a3  jz      loc_1800191D0
0x1800193a9  call    cs:__imp_SRCacheContext_Close
0x1800193af  jmp     loc_1800191D0
0x1800193b4  mov     rcx, [rbp+1C8h]; this
0x1800193bb  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800193c2  mov     edx, 34Fh; void *
0x1800193c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800193cc  lea     rcx, [rsp+2C0h+pSid]
0x1800193d1  mov     ebx, eax
0x1800193d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800193d8  mov     rcx, [rsp+2C0h+StringSid]
0x1800193dd  mov     [rsp+2C0h+StringSid], r13
0x1800193e2  test    rcx, rcx
0x1800193e5  jz      loc_180019113
  ... truncated ...
```
