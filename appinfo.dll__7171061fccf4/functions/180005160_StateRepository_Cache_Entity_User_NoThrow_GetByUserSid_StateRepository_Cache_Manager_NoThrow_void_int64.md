# StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x180005160`
- end: `0x180005211`
- name: `?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `177`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, void *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018228`
- `0x180035698`

## callees

- `0x180005160`
- `0x180006670`
- `0x18000720c`
- `0x18001a0d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005184`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005184`

## string_xrefs

- `0x180005193`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800051de`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        void *a2,
        __int64 *a3)
{
  const char *v5; // r9
  unsigned int LastError; // ebx
  int v8; // eax
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
LABEL_3:
    if ( StringSid )
      LocalFree(StringSid);
    return LastError;
  }
  v8 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, StringSid, a3);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v8,
      v9);
    goto LABEL_3;
  }
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x180005160  mov     [rsp+arg_0], rbx
0x180005165  push    rdi; int
0x180005166  sub     rsp, 20h
0x18000516a  mov     rax, rdx
0x18000516d  mov     [rsp+28h+StringSid], 0
0x180005176  mov     rbx, rcx
0x180005179  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000517e  mov     rcx, rax; Sid
0x180005181  mov     rdi, r8
0x180005184  call    cs:__imp_ConvertSidToStringSidW
0x18000518a  test    eax, eax
0x18000518c  jnz     short loc_1800051C3
0x18000518e  mov     rcx, [rsp+28h]; this
0x180005193  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000519a  mov     edx, 0AAh; void *
0x18000519f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800051a4  mov     ebx, eax
0x1800051a6  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800051ab  test    rcx, rcx
0x1800051ae  jz      short loc_1800051B6
0x1800051b0  call    cs:__imp_LocalFree
0x1800051b6  mov     eax, ebx
0x1800051b8  mov     rbx, [rsp+28h+arg_0]
0x1800051bd  add     rsp, 20h
0x1800051c1  pop     rdi
0x1800051c2  retn
0x1800051c3  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 *
0x1800051c8  mov     r8, rdi; __int64 *
0x1800051cb  mov     rcx, rbx; struct StateRepository::Cache::Manager_NoThrow *
0x1800051ce  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800051d3  mov     ebx, eax
0x1800051d5  test    eax, eax
0x1800051d7  jns     short loc_1800051F4
0x1800051d9  mov     rcx, [rsp+28h]; this
0x1800051de  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800051e5  mov     r9d, eax; char *
0x1800051e8  mov     edx, 0ACh; void *
0x1800051ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051f2  jmp     short loc_1800051A6
0x1800051f4  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800051f9  test    rcx, rcx
0x1800051fc  jz      short loc_180005204
0x1800051fe  call    cs:__imp_LocalFree
0x180005204  mov     rbx, [rsp+28h+arg_0]
0x180005209  xor     eax, eax
0x18000520b  add     rsp, 20h
0x18000520f  pop     rdi
0x180005210  retn
```
