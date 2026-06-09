# GetCallerTokenHandleForIdentification(void)

- ea: `0x1800362a0`
- end: `0x180036312`
- name: `?GetCallerTokenHandleForIdentification@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `114`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a1ec`
- `0x18002ce04`
- `0x18002e4a0`
- `0x1800308a0`
- `0x180031a2c`
- `0x180033418`
- `0x180036318`
- `0x180036fd4`

## callees

- `0x180006b8c`
- `0x180012a98`
- `0x1800362a0`
- `0x180039900`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800362ca`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800362ca`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800362a9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800362a9`

## string_xrefs

- `0x180036300`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCallerTokenHandleForIdentification(__int64 a1)
{
  HRESULT v2; // eax
  unsigned int v4; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
  {
    if ( v2 != -2147417833 )
    {
      v4 = wil::verify_hresult<long>((unsigned int)v2);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)v4,
        v5);
    }
    wil::open_current_access_token(a1, 10);
  }
  else
  {
    wil::open_current_access_token(a1, 14);
    CoRevertToSelf();
  }
  return a1;
}

```

## disassembly

```asm
0x1800362a0  push    rbx
0x1800362a2  sub     rsp, 30h
0x1800362a6  mov     rbx, rcx
0x1800362a9  call    cs:__imp_CoImpersonateClient
0x1800362af  test    eax, eax
0x1800362b1  js      short loc_1800362D9
0x1800362b3  mov     [rsp+38h+arg_8], 1
0x1800362b8  mov     edx, 0Eh
0x1800362bd  lea     r8d, [rdx-0Dh]
0x1800362c1  mov     rcx, rbx
0x1800362c4  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x1800362c9  nop
0x1800362ca  call    cs:__imp_CoRevertToSelf
0x1800362d0  mov     rax, rbx
0x1800362d3  add     rsp, 30h
0x1800362d7  pop     rbx
0x1800362d8  retn
0x1800362d9  cmp     eax, 80010117h
0x1800362de  jnz     short loc_1800362F1
0x1800362e0  xor     r8d, r8d
0x1800362e3  lea     edx, [r8+0Ah]
0x1800362e7  mov     rcx, rbx
0x1800362ea  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x1800362ef  jmp     short loc_1800362D0
0x1800362f1  mov     ecx, eax
0x1800362f3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800362f8  mov     r9d, eax; char *
0x1800362fb  mov     rcx, [rsp+38h]; this
0x180036300  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036307  mov     edx, 13Eh; void *
0x18003630c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
