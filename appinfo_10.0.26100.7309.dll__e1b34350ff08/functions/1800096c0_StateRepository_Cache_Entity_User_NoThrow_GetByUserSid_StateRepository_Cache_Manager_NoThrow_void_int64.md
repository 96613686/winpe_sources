# StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x1800096c0`
- end: `0x180009785`
- name: `?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `197`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, void *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032118`
- `0x180038de0`

## callees

- `0x180007c78`
- `0x1800096c0`
- `0x180009790`
- `0x180018400`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009716`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000976b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009716`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000976b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800096e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800096e4`

## string_xrefs

- `0x1800096f9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000974b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

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
0x1800096c0  mov     [rsp+arg_0], rbx
0x1800096c5  push    rdi; int
0x1800096c6  sub     rsp, 20h
0x1800096ca  mov     rax, rdx
0x1800096cd  mov     [rsp+28h+StringSid], 0
0x1800096d6  mov     rbx, rcx
0x1800096d9  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800096de  mov     rcx, rax; Sid
0x1800096e1  mov     rdi, r8
0x1800096e4  call    cs:__imp_ConvertSidToStringSidW
0x1800096eb  nop     dword ptr [rax+rax+00h]
0x1800096f0  test    eax, eax
0x1800096f2  jnz     short loc_180009730
0x1800096f4  mov     rcx, [rsp+28h]; this
0x1800096f9  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009700  mov     edx, 0AAh; void *
0x180009705  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000970a  mov     ebx, eax
0x18000970c  mov     rcx, [rsp+28h+StringSid]; hMem
0x180009711  test    rcx, rcx
0x180009714  jz      short loc_180009722
0x180009716  call    cs:__imp_LocalFree
0x18000971d  nop     dword ptr [rax+rax+00h]
0x180009722  mov     eax, ebx
0x180009724  mov     rbx, [rsp+28h+arg_0]
0x180009729  add     rsp, 20h
0x18000972d  pop     rdi
0x18000972e  retn
0x180009730  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 *
0x180009735  mov     r8, rdi; __int64 *
0x180009738  mov     rcx, rbx; struct StateRepository::Cache::Manager_NoThrow *
0x18000973b  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180009740  mov     ebx, eax
0x180009742  test    eax, eax
0x180009744  jns     short loc_180009761
0x180009746  mov     rcx, [rsp+28h]; this
0x18000974b  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009752  mov     r9d, eax; char *
0x180009755  mov     edx, 0ACh; void *
0x18000975a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000975f  jmp     short loc_18000970C
0x180009761  mov     rcx, [rsp+28h+StringSid]; hMem
0x180009766  test    rcx, rcx
0x180009769  jz      short loc_180009777
0x18000976b  call    cs:__imp_LocalFree
0x180009772  nop     dword ptr [rax+rax+00h]
0x180009777  mov     rbx, [rsp+28h+arg_0]
0x18000977c  xor     eax, eax
0x18000977e  add     rsp, 20h
0x180009782  pop     rdi
0x180009783  retn
```
