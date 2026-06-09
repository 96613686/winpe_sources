# KvpEncoder::CreateInstance(IKvpEncoder * *,ushort const *)

- ea: `0x18006bf1c`
- end: `0x18006bfe0`
- name: `?CreateInstance@KvpEncoder@@SAJPEAPEAUIKvpEncoder@@PEBG@Z`
- size: `196`
- prototype: `static int(struct IKvpEncoder **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c110`

## callees

- `0x18000cc8c`
- `0x180036ff0`
- `0x18006bf1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006bf4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006bf7a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006bfa0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006bf4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006bf7a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006bfa0`

## string_xrefs

- `0x18006bfb5`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x18006bf94`: `UriPadded`

## pseudocode

```c
__int64 __fastcall KvpEncoder::CreateInstance(struct IKvpEncoder **a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( CompareStringOrdinal(a2, -1, L"Json", -1, 1) == 2 )
  {
    v4 = 1;
    return KvpEncoder::CreateInstance(a1, v4);
  }
  if ( CompareStringOrdinal(a2, -1, L"Uri", -1, 1) == 2 )
  {
    v4 = 2;
    return KvpEncoder::CreateInstance(a1, v4);
  }
  if ( CompareStringOrdinal(a2, -1, L"UriPadded", -1, 1) == 2 )
  {
    v4 = 3;
    return KvpEncoder::CreateInstance(a1, v4);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11F,
    (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
    (const char *)0x80070057LL,
    bIgnoreCase);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18006bf1c  mov     [rsp+arg_0], rbx
0x18006bf21  mov     [rsp+arg_8], rsi
0x18006bf26  push    rdi
0x18006bf27  sub     rsp, 30h
0x18006bf2b  mov     rdi, rdx
0x18006bf2e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18006bf36  or      esi, 0FFFFFFFFh
0x18006bf39  lea     r8, aJson; "Json"
0x18006bf40  mov     rbx, rcx
0x18006bf43  mov     r9d, esi; cchCount2
0x18006bf46  mov     edx, esi; cchCount1
0x18006bf48  mov     rcx, rdi; lpString1
0x18006bf4b  call    cs:__imp_CompareStringOrdinal
0x18006bf51  cmp     eax, 2
0x18006bf54  jnz     short loc_18006BF63
0x18006bf56  lea     edx, [rsi+2]
0x18006bf59  mov     rcx, rbx
0x18006bf5c  call    ?CreateInstance@KvpEncoder@@SAJPEAPEAUIKvpEncoder@@W4KvpEncoderMethod@@@Z; KvpEncoder::CreateInstance(IKvpEncoder * *,KvpEncoderMethod)
0x18006bf61  jmp     short loc_18006BFD0
0x18006bf63  mov     r9d, esi; cchCount2
0x18006bf66  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18006bf6e  lea     r8, aUri; "Uri"
0x18006bf75  mov     edx, esi; cchCount1
0x18006bf77  mov     rcx, rdi; lpString1
0x18006bf7a  call    cs:__imp_CompareStringOrdinal
0x18006bf80  cmp     eax, 2
0x18006bf83  jnz     short loc_18006BF89
0x18006bf85  mov     edx, eax
0x18006bf87  jmp     short loc_18006BF59
0x18006bf89  mov     r9d, esi; cchCount2
0x18006bf8c  mov     [rsp+38h+bIgnoreCase], 1; int
0x18006bf94  lea     r8, aUripadded; "UriPadded"
0x18006bf9b  mov     edx, esi; cchCount1
0x18006bf9d  mov     rcx, rdi; lpString1
0x18006bfa0  call    cs:__imp_CompareStringOrdinal
0x18006bfa6  cmp     eax, 2
0x18006bfa9  jnz     short loc_18006BFB0
0x18006bfab  lea     edx, [rax+1]
0x18006bfae  jmp     short loc_18006BF59
0x18006bfb0  mov     rcx, [rsp+38h]; this
0x18006bfb5  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x18006bfbc  mov     ebx, 80070057h
0x18006bfc1  mov     edx, 11Fh; void *
0x18006bfc6  mov     r9d, ebx; char *
0x18006bfc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bfce  mov     eax, ebx
0x18006bfd0  mov     rbx, [rsp+38h+arg_0]
0x18006bfd5  mov     rsi, [rsp+38h+arg_8]
0x18006bfda  add     rsp, 30h
0x18006bfde  pop     rdi
0x18006bfdf  retn
```
