# SRAppExtensionIteratorContext::FindByUserAndName(void *,ushort const *)

- ea: `0x180012adc`
- end: `0x180012c62`
- name: `?FindByUserAndName@SRAppExtensionIteratorContext@@QEAAJPEAXPEBG@Z`
- size: `390`
- prototype: `__int64 __fastcall(SRAppExtensionIteratorContext *__hidden this, PSID pSid1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014b20`

## callees

- `0x180002980`
- `0x180002e50`
- `0x1800075e4`
- `0x1800090ec`
- `0x180012adc`
- `0x180013190`
- `0x18001370c`
- `0x180014784`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012b22`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012b86`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012b22`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012b86`

## string_xrefs

- `0x180012c19`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180012b52`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`
- `0x180012bd7`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`
- `0x180012c31`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\apiset_appextension.cpp`

## pseudocode

```c
__int64 __fastcall SRAppExtensionIteratorContext::FindByUserAndName(
        SRAppExtensionIteratorContext *this,
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
    *((_BYTE *)this + 617) = EqualSid(pSid1, pSid2);
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
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
        (const char *)(unsigned int)token_information,
        v16);
      if ( Block )
        operator delete(Block);
      return (unsigned int)v9;
    }
    v11 = Block;
    *((_BYTE *)this + 617) = EqualSid(*(PSID *)Block, pSid2);
    if ( v11 )
      operator delete(v11);
  }
  LOBYTE(v19) = 0;
  v12 = (char *)this + 528;
  if ( pSid1 )
  {
    v9 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(this, pSid1, v7, v12, &v19);
    if ( v9 < 0 )
    {
      v13 = 94;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
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
      v13 = 98;
      goto LABEL_12;
    }
  }
  if ( !(_BYTE)v19 )
    return 0;
  v14 = StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(
          (SRAppExtensionIteratorContext *)((char *)this + 8),
          this,
          a3);
  v15 = v14;
  if ( v14 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C2,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
    (const char *)(unsigned int)v14,
    v17);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_appextension.cpp",
    (const char *)v15,
    v18);
  return v15;
}

```

## disassembly

```asm
0x180012adc  push    rbp
0x180012ade  push    rbx
0x180012adf  push    rsi
0x180012ae0  push    rdi
0x180012ae1  push    r14
0x180012ae3  mov     rbp, rsp
0x180012ae6  sub     rsp, 60h
0x180012aea  mov     rax, cs:__security_cookie
0x180012af1  xor     rax, rsp
0x180012af4  mov     [rbp+var_10], rax
0x180012af8  mov     [rbp+pSid2], 101h
0x180012aff  mov     r14, r8
0x180012b02  mov     [rbp+var_1C], 5000000h
0x180012b09  mov     rsi, rdx
0x180012b0c  mov     [rbp+var_18], 12h
0x180012b13  mov     rbx, rcx
0x180012b16  test    rdx, rdx
0x180012b19  jz      short loc_180012B35
0x180012b1b  lea     rdx, [rbp+pSid2]; pSid2
0x180012b1f  mov     rcx, rsi; pSid1
0x180012b22  call    cs:__imp_EqualSid
0x180012b28  test    eax, eax
0x180012b2a  setnz   al
0x180012b2d  mov     [rbx+269h], al
0x180012b33  jmp     short loc_180012BA4
0x180012b35  xor     edx, edx
0x180012b37  mov     [rbp+Block], 0
0x180012b3f  lea     rcx, [rbp+Block]
0x180012b43  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180012b48  mov     edi, eax
0x180012b4a  test    eax, eax
0x180012b4c  jns     short loc_180012B7B
0x180012b4e  mov     rcx, [rbp+28h]; this
0x180012b52  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180012b59  mov     r9d, eax; char *
0x180012b5c  mov     edx, 3Fh ; '?'; void *
0x180012b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b66  mov     rcx, [rbp+Block]; Block
0x180012b6a  test    rcx, rcx
0x180012b6d  jz      short loc_180012B74
0x180012b6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b74  mov     eax, edi
0x180012b76  jmp     loc_180012C4B
0x180012b7b  mov     rdi, [rbp+Block]
0x180012b7f  lea     rdx, [rbp+pSid2]; pSid2
0x180012b83  mov     rcx, [rdi]; pSid1
0x180012b86  call    cs:__imp_EqualSid
0x180012b8c  test    eax, eax
0x180012b8e  setnz   al
0x180012b91  mov     [rbx+269h], al
0x180012b97  test    rdi, rdi
0x180012b9a  jz      short loc_180012BA4
0x180012b9c  mov     rcx, rdi; Block
0x180012b9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012ba4  mov     byte ptr [rbp+var_30], 0
0x180012ba8  lea     rax, [rbp+var_30]
0x180012bac  mov     qword ptr [rsp+60h+var_40], rax; int
0x180012bb1  lea     r9, [rbx+210h]
0x180012bb8  mov     rcx, rbx
0x180012bbb  test    rsi, rsi
0x180012bbe  jz      short loc_180012BE8
0x180012bc0  mov     rdx, rsi
0x180012bc3  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180012bc8  mov     edi, eax
0x180012bca  test    eax, eax
0x180012bcc  jns     short loc_180012BFA
0x180012bce  mov     edx, 5Eh ; '^'; void *
0x180012bd3  mov     rcx, [rbp+28h]; this
0x180012bd7  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180012bde  mov     r9d, edi; char *
0x180012be1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012be6  jmp     short loc_180012B74
0x180012be8  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x180012bed  mov     edi, eax
0x180012bef  test    eax, eax
0x180012bf1  jns     short loc_180012BFA
0x180012bf3  mov     edx, 62h ; 'b'
0x180012bf8  jmp     short loc_180012BD3
0x180012bfa  cmp     byte ptr [rbp+var_30], 0
0x180012bfe  jz      short loc_180012C49
0x180012c00  lea     rcx, [rbx+8]; this
0x180012c04  mov     r8, r14; unsigned __int16 *
0x180012c07  mov     rdx, rbx; struct StateRepository::Cache::Manager_NoThrow *
0x180012c0a  call    ?OpenByName@AppExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x180012c0f  mov     ebx, eax
0x180012c11  test    eax, eax
0x180012c13  jns     short loc_180012C49
0x180012c15  mov     rcx, [rbp+28h]; this
0x180012c19  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180012c20  mov     r9d, eax; char *
0x180012c23  mov     edx, 2C2h; void *
0x180012c28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c2d  mov     rcx, [rbp+28h]; this
0x180012c31  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x180012c38  mov     r9d, ebx; char *
0x180012c3b  mov     edx, 69h ; 'i'; void *
0x180012c40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c45  mov     eax, ebx
0x180012c47  jmp     short loc_180012C4B
0x180012c49  xor     eax, eax
0x180012c4b  mov     rcx, [rbp+var_10]
0x180012c4f  xor     rcx, rsp; StackCookie
0x180012c52  call    __security_check_cookie
0x180012c57  add     rsp, 60h
0x180012c5b  pop     r14
0x180012c5d  pop     rdi
0x180012c5e  pop     rsi
0x180012c5f  pop     rbx
0x180012c60  pop     rbp
0x180012c61  retn
```
