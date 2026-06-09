# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::get_CapabilityName(HSTRING__ * *)

- ea: `0x18001fe90`
- end: `0x18001fef0`
- name: `?get_CapabilityName@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001b5ac`
- `0x18001fe90`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001febf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001febf`

## string_xrefs

- `0x18001fea7`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001fed1`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::get_CapabilityName(
        HSTRING *this,
        HSTRING *a2)
{
  HRESULT v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)0x80004003LL,
        v5);
    v2 = WindowsDuplicateString(this[16], a2);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v2,
        v5);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x28,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001fe90  sub     rsp, 28h
0x18001fe94  mov     rax, rcx
0x18001fe97  mov     rcx, [rsp+28h]; this
0x18001fe9c  test    rdx, rdx
0x18001fe9f  jnz     short loc_18001FEB8
0x18001fea1  mov     r9d, 80004003h; char *
0x18001fea7  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001feae  mov     edx, 24h ; '$'; void *
0x18001feb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001feb8  mov     rcx, [rax+80h]; string
0x18001febf  call    cs:__imp_WindowsDuplicateString
0x18001fec5  mov     rcx, [rsp+28h]; this
0x18001feca  test    eax, eax
0x18001fecc  jns     short loc_18001FEE2
0x18001fece  mov     r9d, eax; char *
0x18001fed1  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001fed8  mov     edx, 25h ; '%'; void *
0x18001fedd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001fee2  xor     eax, eax
0x18001fee4  jmp     short loc_18001FEEA
0x18001fee6  mov     eax, [rsp+28h+arg_8]
0x18001feea  add     rsp, 28h
0x18001feee  retn
```
