# CryptXmlSetHMACSecret

- ea: `0x180017170`
- end: `0x18001721d`
- name: `CryptXmlSetHMACSecret`
- size: `173`
- prototype: `HRESULT __stdcall(HCRYPTXML hSignature, const BYTE *pbSecret, ULONG cbSecret)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180009478`
- `0x180014ce0`
- `0x180017170`
- `0x180019010`

## string_xrefs

- `0x18001719f`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800171e2`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlSetHMACSecret(HCRYPTXML hSignature, const BYTE *pbSecret, ULONG cbSecret)
{
  HRESULT v6; // edi
  const char *v7; // rax
  int v8; // r9d
  void (__fastcall *v9)(HCRYPTXML); // rax

  if ( !hSignature || !pbSecret || !cbSecret )
  {
    v6 = -2147024809;
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v8 = 610;
    goto LABEL_9;
  }
  if ( *(_DWORD *)hSignature != 1145324610 )
  {
    v6 = -2146885370;
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v8 = 617;
LABEL_9:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v6, v7, v8);
    return v6;
  }
  I_CryptXmlLock(hSignature);
  *((_DWORD *)hSignature + 554) = cbSecret;
  v6 = 0;
  *((_QWORD *)hSignature + 276) = pbSecret;
  v9 = (void (__fastcall *)(HCRYPTXML))*((_QWORD *)hSignature + 16);
  if ( v9 )
    v9(hSignature);
  return v6;
}

```

## disassembly

```asm
0x180017170  mov     [rsp+arg_0], rbx
0x180017175  mov     [rsp+arg_8], rsi
0x18001717a  push    rdi
0x18001717b  sub     rsp, 20h
0x18001717f  mov     edi, r8d
0x180017182  mov     rsi, rdx
0x180017185  mov     rbx, rcx
0x180017188  test    rcx, rcx
0x18001718b  jz      short loc_1800171E2
0x18001718d  test    rdx, rdx
0x180017190  jz      short loc_1800171E2
0x180017192  test    r8d, r8d
0x180017195  jz      short loc_1800171E2
0x180017197  cmp     dword ptr [rcx], 44444442h
0x18001719d  jz      short loc_1800171B8
0x18001719f  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800171a6  mov     edi, 80092106h
0x1800171ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800171b0  mov     r9d, 269h
0x1800171b6  jmp     short loc_1800171F9
0x1800171b8  call    I_CryptXmlLock
0x1800171bd  mov     [rbx+8A8h], edi
0x1800171c3  xor     edi, edi
0x1800171c5  mov     [rbx+8A0h], rsi
0x1800171cc  mov     rax, [rbx+80h]
0x1800171d3  test    rax, rax
0x1800171d6  jz      short loc_18001720A
0x1800171d8  mov     rcx, rbx
0x1800171db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e0  jmp     short loc_18001720A
0x1800171e2  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800171e9  mov     edi, 80070057h
0x1800171ee  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800171f3  mov     r9d, 262h
0x1800171f9  mov     r8, rax
0x1800171fc  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180017203  mov     edx, edi
0x180017205  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001720a  mov     rbx, [rsp+28h+arg_0]
0x18001720f  mov     eax, edi
0x180017211  mov     rsi, [rsp+28h+arg_8]
0x180017216  add     rsp, 20h
0x18001721a  pop     rdi
0x18001721b  retn
```
