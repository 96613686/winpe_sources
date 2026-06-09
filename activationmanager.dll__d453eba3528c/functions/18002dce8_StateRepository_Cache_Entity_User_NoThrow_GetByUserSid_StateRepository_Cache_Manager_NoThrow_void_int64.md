# StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x18002dce8`
- end: `0x18002dd90`
- name: `?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, PSID Sid, __int64 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c930`
- `0x18002cc58`
- `0x180055aa4`

## callees

- `0x18000b5c0`
- `0x18002dce8`
- `0x18002dda0`
- `0x180044408`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd6b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002dd0c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002dd0c`

## string_xrefs

- `0x18002dd4e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18002dd7a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        PSID Sid,
        __int64 *a3)
{
  const char *v5; // r9
  int v6; // eax
  unsigned int LastError; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+48h] [rbp+20h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v6 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, StringSid, a3);
    LastError = v6;
    if ( v6 >= 0 )
    {
      if ( StringSid )
        LocalFree(StringSid);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v6,
      v9);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                  v5);
  }
  if ( StringSid )
    LocalFree(StringSid);
  return LastError;
}

```

## disassembly

```asm
0x18002dce8  mov     [rsp+arg_0], rbx
0x18002dced  push    rdi; int
0x18002dcee  sub     rsp, 20h
0x18002dcf2  mov     rax, rdx
0x18002dcf5  mov     [rsp+28h+StringSid], 0
0x18002dcfe  mov     rdi, rcx
0x18002dd01  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18002dd06  mov     rcx, rax; Sid
0x18002dd09  mov     rbx, r8
0x18002dd0c  call    cs:__imp_ConvertSidToStringSidW
0x18002dd12  test    eax, eax
0x18002dd14  jz      short loc_18002DD49
0x18002dd16  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 *
0x18002dd1b  mov     r8, rbx; __int64 *
0x18002dd1e  mov     rcx, rdi; struct StateRepository::Cache::Manager_NoThrow *
0x18002dd21  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18002dd26  mov     ebx, eax
0x18002dd28  test    eax, eax
0x18002dd2a  js      short loc_18002DD75
0x18002dd2c  mov     rcx, [rsp+28h+StringSid]; hMem
0x18002dd31  test    rcx, rcx
0x18002dd34  jz      short loc_18002DD3C
0x18002dd36  call    cs:__imp_LocalFree
0x18002dd3c  xor     eax, eax
0x18002dd3e  mov     rbx, [rsp+28h+arg_0]
0x18002dd43  add     rsp, 20h
0x18002dd47  pop     rdi
0x18002dd48  retn
0x18002dd49  mov     rcx, [rsp+28h]; this
0x18002dd4e  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dd55  mov     edx, 0AAh; void *
0x18002dd5a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dd5f  mov     ebx, eax
0x18002dd61  mov     rcx, [rsp+28h+StringSid]; hMem
0x18002dd66  test    rcx, rcx
0x18002dd69  jz      short loc_18002DD71
0x18002dd6b  call    cs:__imp_LocalFree
0x18002dd71  mov     eax, ebx
0x18002dd73  jmp     short loc_18002DD3E
0x18002dd75  mov     rcx, [rsp+28h]; this
0x18002dd7a  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002dd81  mov     r9d, ebx; char *
0x18002dd84  mov     edx, 0ACh; void *
0x18002dd89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd8e  jmp     short loc_18002DD61
```
