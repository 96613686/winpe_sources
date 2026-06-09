# StringUtils::StringToGuid(ushort const *,_GUID &)

- ea: `0x18002ec8c`
- end: `0x18002ece2`
- name: `?StringToGuid@StringUtils@@SAJPEBGAEAU_GUID@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid, UUID *Uuid)`
- caller_count: `13`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b9e0`
- `0x18001c09c`
- `0x18001c7b0`
- `0x18001cbfc`
- `0x18001d75c`
- `0x18001da18`
- `0x18001f7ec`
- `0x180024844`
- `0x180042ac8`
- `0x180042b34`
- `0x180042edc`
- `0x1800513d0`
- `0x1800557c8`

## callees

- `0x18001208c`
- `0x18002ec8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ec9c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ec9c`
- `RPCRT4!UuidFromStringW` at `0x18002ecac`
- `RPCRT4!UuidFromStringW` at `0x18002ecac`

## pseudocode

```c
__int64 __fastcall StringUtils::StringToGuid(RPC_WSTR StringUuid, UUID *Uuid)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( CLSIDFromString(StringUuid, Uuid) >= 0 )
    return 0;
  v4 = UuidFromStringW(StringUuid, Uuid);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\stringutils.cpp",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x18002ec8c  mov     [rsp+arg_0], rbx
0x18002ec91  push    rdi; int
0x18002ec92  sub     rsp, 20h
0x18002ec96  mov     rbx, rdx
0x18002ec99  mov     rdi, rcx
0x18002ec9c  call    cs:__imp_CLSIDFromString
0x18002eca2  test    eax, eax
0x18002eca4  jns     short loc_18002ECD5
0x18002eca6  mov     rdx, rbx; Uuid
0x18002eca9  mov     rcx, rdi; StringUuid
0x18002ecac  call    cs:__imp_UuidFromStringW
0x18002ecb2  mov     ebx, eax
0x18002ecb4  test    eax, eax
0x18002ecb6  jns     short loc_18002ECD5
0x18002ecb8  mov     rcx, [rsp+28h]; this
0x18002ecbd  lea     r8, aOnecoreBaseDia_14; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002ecc4  mov     r9d, eax; char *
0x18002ecc7  mov     edx, 10h; void *
0x18002eccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ecd1  mov     eax, ebx
0x18002ecd3  jmp     short loc_18002ECD7
0x18002ecd5  xor     eax, eax
0x18002ecd7  mov     rbx, [rsp+28h+arg_0]
0x18002ecdc  add     rsp, 20h
0x18002ece0  pop     rdi
0x18002ece1  retn
```
