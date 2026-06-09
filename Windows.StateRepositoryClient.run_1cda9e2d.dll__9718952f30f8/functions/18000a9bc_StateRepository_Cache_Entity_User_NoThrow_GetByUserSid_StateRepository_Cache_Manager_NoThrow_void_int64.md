# StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x18000a9bc`
- end: `0x18000aa4e`
- name: `?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, PSID Sid, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a464`
- `0x18000bf90`
- `0x180015824`

## callees

- `0x1800075c4`
- `0x1800075e4`
- `0x1800094d4`
- `0x18000a9bc`
- `0x18000aa54`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a9e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a9e0`

## string_xrefs

- `0x18000a9ef`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x18000aa1f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        PSID Sid,
        __int64 *a3)
{
  const char *v5; // r9
  unsigned int LastError; // ebx
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+48h] [rbp+20h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v7 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, StringSid, a3);
    LastError = v7;
    if ( v7 >= 0 )
      LastError = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)v7,
        v9);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
                  v5);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return LastError;
}

```

## disassembly

```asm
0x18000a9bc  mov     [rsp+arg_0], rbx
0x18000a9c1  push    rdi; int
0x18000a9c2  sub     rsp, 20h
0x18000a9c6  mov     rax, rdx
0x18000a9c9  mov     [rsp+28h+StringSid], 0
0x18000a9d2  mov     rdi, rcx
0x18000a9d5  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000a9da  mov     rcx, rax; Sid
0x18000a9dd  mov     rbx, r8
0x18000a9e0  call    cs:__imp_ConvertSidToStringSidW
0x18000a9e6  test    eax, eax
0x18000a9e8  jnz     short loc_18000AA04
0x18000a9ea  mov     rcx, [rsp+28h]; this
0x18000a9ef  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a9f6  mov     edx, 0AAh; void *
0x18000a9fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000aa00  mov     ebx, eax
0x18000aa02  jmp     short loc_18000AA37
0x18000aa04  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 *
0x18000aa09  mov     r8, rbx; __int64 *
0x18000aa0c  mov     rcx, rdi; struct StateRepository::Cache::Manager_NoThrow *
0x18000aa0f  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000aa14  mov     ebx, eax
0x18000aa16  test    eax, eax
0x18000aa18  jns     short loc_18000AA35
0x18000aa1a  mov     rcx, [rsp+28h]; this
0x18000aa1f  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18000aa26  mov     r9d, eax; char *
0x18000aa29  mov     edx, 0ACh; void *
0x18000aa2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa33  jmp     short loc_18000AA37
0x18000aa35  xor     ebx, ebx
0x18000aa37  lea     rcx, [rsp+28h+StringSid]
0x18000aa3c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000aa41  mov     eax, ebx
0x18000aa43  mov     rbx, [rsp+28h+arg_0]
0x18000aa48  add     rsp, 20h
0x18000aa4c  pop     rdi
0x18000aa4d  retn
```
