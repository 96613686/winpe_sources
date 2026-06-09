# StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)

- ea: `0x18002eb68`
- end: `0x18002ec5b`
- name: `?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800334c8`

## callees

- `0x180007c78`
- `0x18002de38`
- `0x18002eb68`
- `0x1800351f8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ebf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ec37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ebf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ec37`

## string_xrefs

- `0x18002eb90`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002ebd8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4,
        bool *a5)
{
  int v7; // ebx
  bool *v9; // rsi
  const WCHAR *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+40h] [rbp+18h] BYREF

  v16 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 175;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 180;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)(unsigned int)v7,
        v14);
      v12 = v16;
      v16 = 0;
      if ( v12 )
        SRCacheContext_Close(v12);
      return (unsigned int)v7;
    }
  }
  v13 = v16;
  v16 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  return 0;
}

```

## disassembly

```asm
0x18002eb68  mov     rax, rsp
0x18002eb6b  mov     [rax+8], rbx
0x18002eb6f  mov     [rax+10h], rbp
0x18002eb73  mov     [rax+20h], rsi
0x18002eb77  mov     [rax+18h], r8
0x18002eb7b  push    rdi; int
0x18002eb7c  sub     rsp, 20h
0x18002eb80  mov     rbp, r9
0x18002eb83  mov     rdi, rdx
0x18002eb86  test    rdx, rdx
0x18002eb89  jnz     short loc_18002EBB0
0x18002eb8b  mov     rcx, [rsp+28h]; this
0x18002eb90  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002eb97  mov     ebx, 80070057h
0x18002eb9c  mov     edx, 0ACh; void *
0x18002eba1  mov     r9d, ebx; char *
0x18002eba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eba9  mov     eax, ebx
0x18002ebab  jmp     loc_18002EC45
0x18002ebb0  mov     rsi, [rsp+28h+arg_20]
0x18002ebb5  lea     r8, [rsp+28h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002ebba  and     [rsp+28h+arg_10], 0
0x18002ebc0  mov     r9, rsi; bool *
0x18002ebc3  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002ebc8  mov     ebx, eax
0x18002ebca  test    eax, eax
0x18002ebcc  jns     short loc_18002EC05
0x18002ebce  mov     edx, 0AFh; void *
0x18002ebd3  mov     rcx, [rsp+28h]; this
0x18002ebd8  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ebdf  mov     r9d, ebx; char *
0x18002ebe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ebe7  mov     rcx, [rsp+28h+arg_10]
0x18002ebec  and     [rsp+28h+arg_10], 0
0x18002ebf2  test    rcx, rcx
0x18002ebf5  jz      short loc_18002EBA9
0x18002ebf7  call    cs:__imp_SRCacheContext_Close
0x18002ebfe  nop     dword ptr [rax+rax+00h]
0x18002ec03  jmp     short loc_18002EBA9
0x18002ec05  cmp     byte ptr [rsi], 0
0x18002ec08  jz      short loc_18002EC27
0x18002ec0a  mov     r9, rdi
0x18002ec0d  lea     rcx, [rsp+28h+arg_10]
0x18002ec12  mov     rdx, rbp
0x18002ec15  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x18002ec1a  mov     ebx, eax
0x18002ec1c  test    eax, eax
0x18002ec1e  jns     short loc_18002EC27
0x18002ec20  mov     edx, 0B4h
0x18002ec25  jmp     short loc_18002EBD3
0x18002ec27  mov     rcx, [rsp+28h+arg_10]
0x18002ec2c  and     [rsp+28h+arg_10], 0
0x18002ec32  test    rcx, rcx
0x18002ec35  jz      short loc_18002EC43
0x18002ec37  call    cs:__imp_SRCacheContext_Close
0x18002ec3e  nop     dword ptr [rax+rax+00h]
0x18002ec43  xor     eax, eax
0x18002ec45  mov     rbx, [rsp+28h+arg_0]
0x18002ec4a  mov     rbp, [rsp+28h+arg_8]
0x18002ec4f  mov     rsi, [rsp+28h+arg_18]
0x18002ec54  add     rsp, 20h
0x18002ec58  pop     rdi
0x18002ec59  retn
```
