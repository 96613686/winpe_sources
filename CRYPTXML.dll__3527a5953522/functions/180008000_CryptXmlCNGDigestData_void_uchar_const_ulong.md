# CryptXmlCNGDigestData(void *,uchar const *,ulong)

- ea: `0x180008000`
- end: `0x18000806f`
- name: `?CryptXmlCNGDigestData@@YAJPEAXPEBEK@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180008000`
- `0x180014ce0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000800d`
- `bcrypt!BCryptHashData` at `0x18000800d`

## string_xrefs

- `0x18000801f`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`

## pseudocode

```c
__int64 __fastcall CryptXmlCNGDigestData(BCRYPT_HASH_HANDLE *a1, UCHAR *a2, ULONG a3)
{
  NTSTATUS v3; // eax
  int v4; // ebx
  const char *v5; // rax

  v3 = BCryptHashData(a1[2], a2, a3, 0);
  if ( v3 >= 0 )
    return 0;
  v4 = v3 | 0x10000000;
  v5 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v4, v5, 226, "BCryptHashData");
  if ( v4 >= 0 )
    return (unsigned int)v4;
  else
    return 2148081931LL;
}

```

## disassembly

```asm
0x180008000  push    rbx
0x180008002  sub     rsp, 30h
0x180008006  mov     rcx, [rcx+10h]; hHash
0x18000800a  xor     r9d, r9d; dwFlags
0x18000800d  call    cs:__imp_BCryptHashData
0x180008014  nop     dword ptr [rax+rax+00h]
0x180008019  mov     ebx, eax
0x18000801b  test    eax, eax
0x18000801d  jns     short loc_180008066
0x18000801f  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008026  bts     ebx, 1Ch
0x18000802a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000802f  mov     r8, rax
0x180008032  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x180008039  lea     rax, aBcrypthashdata_0; "BCryptHashData"
0x180008040  mov     r9d, 0E2h
0x180008046  mov     edx, ebx
0x180008048  mov     [rsp+38h+var_18], rax
0x18000804d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008052  test    ebx, ebx
0x180008054  jns     short loc_180008062
0x180008056  mov     eax, 8009210Bh
0x18000805b  add     rsp, 30h
0x18000805f  pop     rbx
0x180008060  retn
0x180008062  mov     eax, ebx
0x180008064  jmp     short loc_180008068
0x180008066  xor     eax, eax
0x180008068  add     rsp, 30h
0x18000806c  pop     rbx
0x18000806d  retn
```
