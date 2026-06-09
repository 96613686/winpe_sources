# StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x180064150`
- end: `0x1800641fc`
- name: `?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `172`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, void *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006323c`

## callees

- `0x18002c8d0`
- `0x180064150`
- `0x180064204`
- `0x180083aa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800641d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800641da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800641d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800641da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180064174`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180064174`

## string_xrefs

- `0x180064199`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800641e7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        void *a2,
        __int64 *a3)
{
  const char *v5; // r9
  int v6; // eax
  unsigned int LastError; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+48h] [rbp+20h] BYREF

  StringSid = 0;
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                  v5);
    goto LABEL_4;
  }
  v6 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, StringSid, a3);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v6,
      v9);
LABEL_4:
    if ( StringSid )
      LocalFree(StringSid);
    return LastError;
  }
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x180064150  mov     [rsp+arg_0], rbx
0x180064155  push    rdi; int
0x180064156  sub     rsp, 20h
0x18006415a  mov     rax, rdx
0x18006415d  mov     [rsp+28h+StringSid], 0
0x180064166  mov     rdi, rcx
0x180064169  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18006416e  mov     rcx, rax; Sid
0x180064171  mov     rbx, r8
0x180064174  call    cs:__imp_ConvertSidToStringSidW
0x18006417a  test    eax, eax
0x18006417c  jz      short loc_1800641E2
0x18006417e  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 *
0x180064183  mov     r8, rbx; __int64 *
0x180064186  mov     rcx, rdi; struct StateRepository::Cache::Manager_NoThrow *
0x180064189  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18006418e  mov     ebx, eax
0x180064190  test    eax, eax
0x180064192  jns     short loc_1800641C4
0x180064194  mov     rcx, [rsp+28h]; this
0x180064199  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800641a0  mov     r9d, eax; char *
0x1800641a3  mov     edx, 0ACh; void *
0x1800641a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800641ad  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800641b2  test    rcx, rcx
0x1800641b5  jnz     short loc_1800641D2
0x1800641b7  mov     eax, ebx
0x1800641b9  mov     rbx, [rsp+28h+arg_0]
0x1800641be  add     rsp, 20h
0x1800641c2  pop     rdi
0x1800641c3  retn
0x1800641c4  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800641c9  test    rcx, rcx
0x1800641cc  jnz     short loc_1800641DA
0x1800641ce  xor     eax, eax
0x1800641d0  jmp     short loc_1800641B9
0x1800641d2  call    cs:__imp_LocalFree
0x1800641d8  jmp     short loc_1800641B7
0x1800641da  call    cs:__imp_LocalFree
0x1800641e0  jmp     short loc_1800641CE
0x1800641e2  mov     rcx, [rsp+28h]; this
0x1800641e7  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800641ee  mov     edx, 0AAh; void *
0x1800641f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800641f8  mov     ebx, eax
0x1800641fa  jmp     short loc_1800641AD
```
