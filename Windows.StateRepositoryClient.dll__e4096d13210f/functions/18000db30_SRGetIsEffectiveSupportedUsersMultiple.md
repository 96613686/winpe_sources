# SRGetIsEffectiveSupportedUsersMultiple

- ea: `0x18000db30`
- end: `0x18000dc18`
- name: `SRGetIsEffectiveSupportedUsersMultiple`
- size: `232`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800075e4`
- `0x1800094a4`
- `0x18000b170`
- `0x18000db30`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000dbbd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000dc03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000dbbd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000dc03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000db67`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000db67`

## string_xrefs

- `0x18000db80`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall SRGetIsEffectiveSupportedUsersMultiple(unsigned __int16 *a1, _DWORD *a2)
{
  int IsEffectiveSupportedUsersMultiple; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v8; // rcx
  __int64 *v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  char v11; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  bool v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v10 = 0;
  v11 = 1;
  v9 = &v14;
  IsEffectiveSupportedUsersMultiple = SRCacheManager_Open(0, &v10);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v9);
  if ( IsEffectiveSupportedUsersMultiple < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Manager.hpp",
      (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
      (int)v9);
    v5 = 265;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)IsEffectiveSupportedUsersMultiple,
      (int)v9);
    v6 = v14;
    v14 = 0;
    if ( v6 )
      SRCacheManager_Close(v6);
    return (unsigned int)IsEffectiveSupportedUsersMultiple;
  }
  v13 = 0;
  IsEffectiveSupportedUsersMultiple = StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(
                                        (struct StateRepository::Cache::Manager_NoThrow *)&v14,
                                        a1,
                                        &v13);
  if ( IsEffectiveSupportedUsersMultiple < 0 )
  {
    v5 = 267;
    goto LABEL_3;
  }
  v8 = v14;
  v14 = 0;
  *a2 = v13;
  if ( v8 )
    SRCacheManager_Close(v8);
  return 0;
}

```

## disassembly

```asm
0x18000db30  mov     [rsp-18h+arg_0], rbx
0x18000db35  push    rbp
0x18000db36  push    rsi
0x18000db37  push    rdi
0x18000db38  mov     rbp, rsp
0x18000db3b  sub     rsp, 40h
0x18000db3f  mov     rdi, rdx
0x18000db42  mov     [rbp+arg_18], 0
0x18000db4a  mov     rsi, rcx
0x18000db4d  mov     [rbp+var_18], 0
0x18000db55  lea     rax, [rbp+arg_18]
0x18000db59  mov     [rbp+var_10], 1
0x18000db5d  lea     rdx, [rbp+var_18]
0x18000db61  mov     [rbp+var_20], rax
0x18000db65  xor     ecx, ecx
0x18000db67  call    cs:__imp_SRCacheManager_Open
0x18000db6d  lea     rcx, [rbp+var_20]
0x18000db71  mov     ebx, eax
0x18000db73  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18000db78  test    ebx, ebx
0x18000db7a  jns     short loc_18000DBC7
0x18000db7c  mov     rcx, [rbp+18h]; this
0x18000db80  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x18000db87  mov     r9d, ebx; char *
0x18000db8a  mov     edx, 0A5h; void *
0x18000db8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db94  mov     edx, 109h; void *
0x18000db99  mov     rcx, [rbp+18h]; this
0x18000db9d  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000dba4  mov     r9d, ebx; char *
0x18000dba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbac  mov     rcx, [rbp+arg_18]
0x18000dbb0  mov     [rbp+arg_18], 0
0x18000dbb8  test    rcx, rcx
0x18000dbbb  jz      short loc_18000DBC3
0x18000dbbd  call    cs:__imp_SRCacheManager_Close
0x18000dbc3  mov     eax, ebx
0x18000dbc5  jmp     short loc_18000DC0B
0x18000dbc7  lea     r8, [rbp+arg_10]; bool *
0x18000dbcb  mov     [rbp+arg_10], 0
0x18000dbcf  mov     rdx, rsi; unsigned __int16 *
0x18000dbd2  lea     rcx, [rbp+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x18000dbd6  call    ?GetIsEffectiveSupportedUsersMultiple@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetIsEffectiveSupportedUsersMultiple(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)
0x18000dbdb  mov     ebx, eax
0x18000dbdd  test    eax, eax
0x18000dbdf  jns     short loc_18000DBE8
0x18000dbe1  mov     edx, 10Bh
0x18000dbe6  jmp     short loc_18000DB99
0x18000dbe8  mov     rcx, [rbp+arg_18]
0x18000dbec  xor     eax, eax
0x18000dbee  cmp     [rbp+arg_10], al
0x18000dbf1  mov     [rbp+arg_18], 0
0x18000dbf9  setnz   al
0x18000dbfc  mov     [rdi], eax
0x18000dbfe  test    rcx, rcx
0x18000dc01  jz      short loc_18000DC09
0x18000dc03  call    cs:__imp_SRCacheManager_Close
0x18000dc09  xor     eax, eax
0x18000dc0b  mov     rbx, [rsp+40h+arg_0]
0x18000dc10  add     rsp, 40h
0x18000dc14  pop     rdi
0x18000dc15  pop     rsi
0x18000dc16  pop     rbp
0x18000dc17  retn
```
