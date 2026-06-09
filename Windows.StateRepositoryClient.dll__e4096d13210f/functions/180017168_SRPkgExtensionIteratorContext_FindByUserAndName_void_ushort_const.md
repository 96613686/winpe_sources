# SRPkgExtensionIteratorContext::FindByUserAndName(void *,ushort const *)

- ea: `0x180017168`
- end: `0x1800172ee`
- name: `?FindByUserAndName@SRPkgExtensionIteratorContext@@QEAAJPEAXPEBG@Z`
- size: `390`
- prototype: `__int64 __fastcall(SRPkgExtensionIteratorContext *__hidden this, PSID pSid1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018040`

## callees

- `0x180002980`
- `0x180002e50`
- `0x1800075e4`
- `0x1800090ec`
- `0x180013190`
- `0x18001370c`
- `0x180017168`
- `0x180017c9c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800171ae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017212`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800171ae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017212`

## string_xrefs

- `0x1800172a5`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x1800171de`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`
- `0x180017263`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`
- `0x1800172bd`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_pkgextension.cpp`

## pseudocode

```c
__int64 __fastcall SRPkgExtensionIteratorContext::FindByUserAndName(
        SRPkgExtensionIteratorContext *this,
        PSID pSid1,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int token_information; // eax
  int v9; // edi
  void *v11; // rdi
  char *v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-40h]
  int v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+20h] [rbp-40h]
  int v19; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  _DWORD pSid2[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  pSid2[0] = 257;
  pSid2[1] = 83886080;
  pSid2[2] = 18;
  if ( pSid1 )
  {
    *((_BYTE *)this + 505) = EqualSid(pSid1, pSid2);
  }
  else
  {
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, 0);
    v9 = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
        (const char *)(unsigned int)token_information,
        v16);
      if ( Block )
        operator delete(Block);
      return (unsigned int)v9;
    }
    v11 = Block;
    *((_BYTE *)this + 505) = EqualSid(*(PSID *)Block, pSid2);
    if ( v11 )
      operator delete(v11);
  }
  LOBYTE(v19) = 0;
  v12 = (char *)this + 416;
  if ( pSid1 )
  {
    v9 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(this, pSid1, v7, v12, &v19);
    if ( v9 < 0 )
    {
      v13 = 93;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
        (const char *)(unsigned int)v9,
        v17);
      return (unsigned int)v9;
    }
  }
  else
  {
    v9 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(this, v6, v7, v12, &v19);
    if ( v9 < 0 )
    {
      v13 = 97;
      goto LABEL_12;
    }
  }
  if ( !(_BYTE)v19 )
    return 0;
  v14 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(
          (SRPkgExtensionIteratorContext *)((char *)this + 8),
          this,
          a3);
  v15 = v14;
  if ( v14 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C2,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
    (const char *)(unsigned int)v14,
    v17);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x68,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_pkgextension.cpp",
    (const char *)v15,
    v18);
  return v15;
}

```

## disassembly

```asm
0x180017168  push    rbp
0x18001716a  push    rbx
0x18001716b  push    rsi
0x18001716c  push    rdi
0x18001716d  push    r14
0x18001716f  mov     rbp, rsp
0x180017172  sub     rsp, 60h
0x180017176  mov     rax, cs:__security_cookie
0x18001717d  xor     rax, rsp
0x180017180  mov     [rbp+var_10], rax
0x180017184  mov     [rbp+pSid2], 101h
0x18001718b  mov     r14, r8
0x18001718e  mov     [rbp+var_1C], 5000000h
0x180017195  mov     rsi, rdx
0x180017198  mov     [rbp+var_18], 12h
0x18001719f  mov     rbx, rcx
0x1800171a2  test    rdx, rdx
0x1800171a5  jz      short loc_1800171C1
0x1800171a7  lea     rdx, [rbp+pSid2]; pSid2
0x1800171ab  mov     rcx, rsi; pSid1
0x1800171ae  call    cs:__imp_EqualSid
0x1800171b4  test    eax, eax
0x1800171b6  setnz   al
0x1800171b9  mov     [rbx+1F9h], al
0x1800171bf  jmp     short loc_180017230
0x1800171c1  xor     edx, edx
0x1800171c3  mov     [rbp+Block], 0
0x1800171cb  lea     rcx, [rbp+Block]
0x1800171cf  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800171d4  mov     edi, eax
0x1800171d6  test    eax, eax
0x1800171d8  jns     short loc_180017207
0x1800171da  mov     rcx, [rbp+28h]; this
0x1800171de  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x1800171e5  mov     r9d, eax; char *
0x1800171e8  mov     edx, 3Eh ; '>'; void *
0x1800171ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171f2  mov     rcx, [rbp+Block]; Block
0x1800171f6  test    rcx, rcx
0x1800171f9  jz      short loc_180017200
0x1800171fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017200  mov     eax, edi
0x180017202  jmp     loc_1800172D7
0x180017207  mov     rdi, [rbp+Block]
0x18001720b  lea     rdx, [rbp+pSid2]; pSid2
0x18001720f  mov     rcx, [rdi]; pSid1
0x180017212  call    cs:__imp_EqualSid
0x180017218  test    eax, eax
0x18001721a  setnz   al
0x18001721d  mov     [rbx+1F9h], al
0x180017223  test    rdi, rdi
0x180017226  jz      short loc_180017230
0x180017228  mov     rcx, rdi; Block
0x18001722b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017230  mov     byte ptr [rbp+var_30], 0
0x180017234  lea     rax, [rbp+var_30]
0x180017238  mov     qword ptr [rsp+60h+var_40], rax; int
0x18001723d  lea     r9, [rbx+1A0h]
0x180017244  mov     rcx, rbx
0x180017247  test    rsi, rsi
0x18001724a  jz      short loc_180017274
0x18001724c  mov     rdx, rsi
0x18001724f  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180017254  mov     edi, eax
0x180017256  test    eax, eax
0x180017258  jns     short loc_180017286
0x18001725a  mov     edx, 5Dh ; ']'; void *
0x18001725f  mov     rcx, [rbp+28h]; this
0x180017263  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x18001726a  mov     r9d, edi; char *
0x18001726d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017272  jmp     short loc_180017200
0x180017274  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180017279  mov     edi, eax
0x18001727b  test    eax, eax
0x18001727d  jns     short loc_180017286
0x18001727f  mov     edx, 61h ; 'a'
0x180017284  jmp     short loc_18001725F
0x180017286  cmp     byte ptr [rbp+var_30], 0
0x18001728a  jz      short loc_1800172D5
0x18001728c  lea     rcx, [rbx+8]; this
0x180017290  mov     r8, r14; unsigned __int16 *
0x180017293  mov     rdx, rbx; struct StateRepository::Cache::Manager_NoThrow *
0x180017296  call    ?OpenByName@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x18001729b  mov     ebx, eax
0x18001729d  test    eax, eax
0x18001729f  jns     short loc_1800172D5
0x1800172a1  mov     rcx, [rbp+28h]; this
0x1800172a5  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x1800172ac  mov     r9d, eax; char *
0x1800172af  mov     edx, 2C2h; void *
0x1800172b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172b9  mov     rcx, [rbp+28h]; this
0x1800172bd  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x1800172c4  mov     r9d, ebx; char *
0x1800172c7  mov     edx, 68h ; 'h'; void *
0x1800172cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172d1  mov     eax, ebx
0x1800172d3  jmp     short loc_1800172D7
0x1800172d5  xor     eax, eax
0x1800172d7  mov     rcx, [rbp+var_10]
0x1800172db  xor     rcx, rsp; StackCookie
0x1800172de  call    __security_check_cookie
0x1800172e3  add     rsp, 60h
0x1800172e7  pop     r14
0x1800172e9  pop     rdi
0x1800172ea  pop     rsi
0x1800172eb  pop     rbx
0x1800172ec  pop     rbp
0x1800172ed  retn
```
