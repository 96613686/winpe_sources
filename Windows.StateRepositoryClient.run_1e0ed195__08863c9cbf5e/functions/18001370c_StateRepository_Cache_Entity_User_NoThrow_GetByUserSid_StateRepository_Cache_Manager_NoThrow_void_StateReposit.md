# StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)

- ea: `0x18001370c`
- end: `0x1800137fe`
- name: `?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012adc`
- `0x180013190`
- `0x180017168`

## callees

- `0x1800075c4`
- `0x1800075e4`
- `0x1800094d4`
- `0x18000aa54`
- `0x1800130b0`
- `0x18001370c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180013733`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180013733`

## string_xrefs

- `0x180013742`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x1800137ba`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x1800137ce`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        void *a2,
        __int64 a3,
        _QWORD *a4,
        bool *a5)
{
  const char *v7; // r9
  int LastError; // ebx
  bool *v9; // rdi
  unsigned __int16 *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-48h]
  int v15; // [rsp+20h] [rbp-48h]
  __int64 v16[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int16 *v18; // [rsp+80h] [rbp+18h] BYREF

  v18 = 0;
  if ( ConvertSidToStringSidW(a2, &v18) )
  {
    v9 = a5;
    v10 = v18;
    v16[0] = 0;
    *a5 = 0;
    LastError = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, v10, v16);
    if ( LastError >= 0 )
    {
      if ( !v16[0]
        || (LastError = StateRepository::Cache::Entity::User_NoThrow::Get(a1, v16[0], v11, a4, v9), LastError >= 0) )
      {
        LastError = 0;
        goto LABEL_10;
      }
      v12 = 248;
    }
    else
    {
      v12 = 245;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)LastError,
      v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)LastError,
      v15);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
                  v7);
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001370c  mov     r11, rsp
0x18001370f  mov     [r11+18h], r8
0x180013713  push    rbx
0x180013714  push    rbp
0x180013715  push    rsi
0x180013716  push    rdi
0x180013717  sub     rsp, 48h
0x18001371b  mov     rax, rdx
0x18001371e  mov     qword ptr [r11+18h], 0
0x180013726  mov     rsi, rcx
0x180013729  lea     rdx, [r11+18h]; StringSid
0x18001372d  mov     rcx, rax; Sid
0x180013730  mov     rbp, r9
0x180013733  call    cs:__imp_ConvertSidToStringSidW
0x180013739  test    eax, eax
0x18001373b  jnz     short loc_18001375A
0x18001373d  mov     rcx, [rsp+68h]; this
0x180013742  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x180013749  mov     edx, 0DCh; void *
0x18001374e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013753  mov     ebx, eax
0x180013755  jmp     loc_1800137E6
0x18001375a  mov     rdi, [rsp+68h+arg_20]
0x180013762  lea     r8, [rsp+68h+var_38]; __int64 *
0x180013767  mov     rdx, [rsp+68h+arg_10]; unsigned __int16 *
0x18001376f  mov     rcx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180013772  mov     [rsp+68h+var_38], 0
0x18001377b  mov     byte ptr [rdi], 0
0x18001377e  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180013783  mov     ebx, eax
0x180013785  test    eax, eax
0x180013787  jns     short loc_180013790
0x180013789  mov     edx, 0F5h
0x18001378e  jmp     short loc_1800137B5
0x180013790  mov     rdx, [rsp+68h+var_38]
0x180013795  test    rdx, rdx
0x180013798  jz      short loc_1800137E4
0x18001379a  mov     r9, rbp
0x18001379d  mov     qword ptr [rsp+68h+var_48], rdi; int
0x1800137a2  mov     rcx, rsi
0x1800137a5  call    ?Get@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x1800137aa  mov     ebx, eax
0x1800137ac  test    eax, eax
0x1800137ae  jns     short loc_1800137E4
0x1800137b0  mov     edx, 0F8h; void *
0x1800137b5  mov     rcx, [rsp+68h]; this
0x1800137ba  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x1800137c1  mov     r9d, ebx; char *
0x1800137c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137c9  mov     rcx, [rsp+68h]; this
0x1800137ce  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x1800137d5  mov     r9d, ebx; char *
0x1800137d8  mov     edx, 0DEh; void *
0x1800137dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137e2  jmp     short loc_1800137E6
0x1800137e4  xor     ebx, ebx
0x1800137e6  lea     rcx, [rsp+68h+arg_10]
0x1800137ee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800137f3  mov     eax, ebx
0x1800137f5  add     rsp, 48h
0x1800137f9  pop     rdi
0x1800137fa  pop     rsi
0x1800137fb  pop     rbp
0x1800137fc  pop     rbx
0x1800137fd  retn
```
