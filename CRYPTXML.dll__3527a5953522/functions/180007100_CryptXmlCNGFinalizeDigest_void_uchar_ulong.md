# CryptXmlCNGFinalizeDigest(void *,uchar *,ulong)

- ea: `0x180007100`
- end: `0x18000716f`
- name: `?CryptXmlCNGFinalizeDigest@@YAJPEAXPEAEK@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180007100`
- `0x180014ce0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18000710d`
- `bcrypt!BCryptFinishHash` at `0x18000710d`

## string_xrefs

- `0x18000711f`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`

## pseudocode

```c
__int64 __fastcall CryptXmlCNGFinalizeDigest(BCRYPT_HASH_HANDLE *a1, unsigned __int8 *a2, ULONG a3)
{
  NTSTATUS v3; // eax
  int v4; // ebx
  const char *v5; // rax

  v3 = BCryptFinishHash(a1[2], a2, a3, 0);
  if ( v3 >= 0 )
    return 0;
  v4 = v3 | 0x10000000;
  v5 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v4, v5, 271, "BCryptFinishHash");
  if ( v4 >= 0 )
    return (unsigned int)v4;
  else
    return 2148081931LL;
}

```

## disassembly

```asm
0x180007100  push    rbx
0x180007102  sub     rsp, 30h
0x180007106  mov     rcx, [rcx+10h]; hHash
0x18000710a  xor     r9d, r9d; dwFlags
0x18000710d  call    cs:__imp_BCryptFinishHash
0x180007114  nop     dword ptr [rax+rax+00h]
0x180007119  mov     ebx, eax
0x18000711b  test    eax, eax
0x18000711d  jns     short loc_180007166
0x18000711f  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180007126  bts     ebx, 1Ch
0x18000712a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000712f  mov     r8, rax
0x180007132  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x180007139  lea     rax, aBcryptfinishha_0; "BCryptFinishHash"
0x180007140  mov     r9d, 10Fh
0x180007146  mov     edx, ebx
0x180007148  mov     [rsp+38h+var_18], rax
0x18000714d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007152  test    ebx, ebx
0x180007154  jns     short loc_180007162
0x180007156  mov     eax, 8009210Bh
0x18000715b  add     rsp, 30h
0x18000715f  pop     rbx
0x180007160  retn
0x180007162  mov     eax, ebx
0x180007164  jmp     short loc_180007168
0x180007166  xor     eax, eax
0x180007168  add     rsp, 30h
0x18000716c  pop     rbx
0x18000716d  retn
```
