# I_CryptXmlImportPublicKeyExtension

- ea: `0x180012838`
- end: `0x1800129f6`
- name: `I_CryptXmlImportPublicKeyExtension`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800013a0`

## callees

- `0x1800070d0`
- `0x1800113d0`
- `0x180012838`
- `0x18001429c`
- `0x180014ce0`
- `0x180015384`
- `0x180016c38`
- `0x180018625`
- `0x180018640`
- `0x180019010`

## string_xrefs

- `0x1800128ce`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180012965`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800129a4`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlImportPublicKeyExtension(int *a1, _QWORD *a2)
{
  const WCHAR *v4; // rbx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int KeyValueInnerElementName; // ebx
  const char *v10; // rax
  int v11; // r9d
  __int64 (__fastcall *KeyProc)(__int128 *, _QWORD *); // rsi
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v15; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR v17[256]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = 0;
  v16 = 0;
  v15 = 0;
  memset_0(v17, 0, sizeof(v17));
  *a2 = 0;
  v5 = *a1;
  v14 = 255;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          KeyValueInnerElementName = I_XmlGetKeyValueInnerElementName(a1 + 2, v17, &v14);
          if ( KeyValueInnerElementName < 0 )
          {
            v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
            v11 = 2655;
LABEL_7:
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", KeyValueInnerElementName, v10, v11);
            goto LABEL_21;
          }
          v4 = v17;
          v15 = *(_OWORD *)(a1 + 2);
        }
      }
      else
      {
        v4 = L"ECDSAKeyValue";
      }
    }
    else
    {
      v4 = L"RSAKeyValue";
    }
  }
  else
  {
    v4 = L"DSAKeyValue";
  }
  KeyProc = (__int64 (__fastcall *)(__int128 *, _QWORD *))GetCreateKeyProc(v4);
  if ( KeyProc )
  {
    if ( *a1 != 4 )
    {
      LODWORD(v15) = 1;
      KeyValueInnerElementName = I_CryptXmlEncodeInnerKeyValue(1u, (__int64)a1, (__int64)&v16);
      if ( KeyValueInnerElementName < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        v11 = 2690;
        goto LABEL_7;
      }
      *((_QWORD *)&v15 + 1) = v16;
      DWORD1(v15) = DWORD2(v16);
    }
    KeyValueInnerElementName = KeyProc(&v15, a2);
    if ( KeyValueInnerElementName < 0 )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      v11 = 2704;
      goto LABEL_7;
    }
    KeyValueInnerElementName = 0;
  }
  else
  {
    KeyValueInnerElementName = -2147467263;
  }
LABEL_21:
  if ( (_QWORD)v16 )
    CryptXmlFree(v16);
  return (unsigned int)KeyValueInnerElementName;
}

```

## disassembly

```asm
0x180012838  mov     [rsp-8+arg_10], rbx
0x18001283d  mov     [rsp-8+arg_18], rsi
0x180012842  push    rbp
0x180012843  push    rdi
0x180012844  push    r14
0x180012846  lea     rbp, [rsp-160h]
0x18001284e  sub     rsp, 260h
0x180012855  mov     rax, cs:__security_cookie
0x18001285c  xor     rax, rsp
0x18001285f  mov     [rbp+170h+var_20], rax
0x180012866  mov     r14, rdx
0x180012869  mov     rdi, rcx
0x18001286c  xorps   xmm0, xmm0
0x18001286f  lea     rcx, [rsp+270h+var_220]; void *
0x180012874  xorps   xmm1, xmm1
0x180012877  xor     edx, edx; Val
0x180012879  mov     r8d, 200h; Size
0x18001287f  xor     ebx, ebx
0x180012881  movups  [rsp+270h+var_238], xmm0
0x180012886  movups  [rsp+270h+var_248], xmm1
0x18001288b  call    memset_0
0x180012890  mov     [r14], rbx
0x180012893  mov     ecx, [rdi]
0x180012895  mov     [rsp+270h+var_250], 0FFh
0x18001289d  sub     ecx, 1
0x1800128a0  jz      loc_180012926
0x1800128a6  sub     ecx, 1
0x1800128a9  jz      short loc_18001291D
0x1800128ab  sub     ecx, 1
0x1800128ae  jz      short loc_180012914
0x1800128b0  cmp     ecx, 1
0x1800128b3  jnz     short loc_18001292D
0x1800128b5  lea     r8, [rsp+270h+var_250]
0x1800128ba  lea     rdx, [rsp+270h+var_220]
0x1800128bf  lea     rcx, [rdi+8]
0x1800128c3  call    I_XmlGetKeyValueInnerElementName
0x1800128c8  mov     ebx, eax
0x1800128ca  test    eax, eax
0x1800128cc  jns     short loc_1800128F6
0x1800128ce  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800128d5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800128da  mov     r9d, 0A5Fh
0x1800128e0  mov     r8, rax
0x1800128e3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800128ea  mov     edx, ebx
0x1800128ec  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800128f1  jmp     loc_1800129BD
0x1800128f6  mov     eax, [rdi+8]
0x1800128f9  lea     rbx, [rsp+270h+var_220]
0x1800128fe  mov     dword ptr [rsp+270h+var_248], eax
0x180012902  mov     rax, [rdi+10h]
0x180012906  mov     qword ptr [rsp+270h+var_248+8], rax
0x18001290b  mov     eax, [rdi+0Ch]
0x18001290e  mov     dword ptr [rsp+270h+var_248+4], eax
0x180012912  jmp     short loc_18001292D
0x180012914  lea     rbx, aEcdsakeyvalue; "ECDSAKeyValue"
0x18001291b  jmp     short loc_18001292D
0x18001291d  lea     rbx, aRsakeyvalue; "RSAKeyValue"
0x180012924  jmp     short loc_18001292D
0x180012926  lea     rbx, aDsakeyvalue_0; "DSAKeyValue"
0x18001292d  mov     rcx, rbx; lpString2
0x180012930  call    _GetCreateKeyProc
0x180012935  mov     rsi, rax
0x180012938  test    rax, rax
0x18001293b  jnz     short loc_180012944
0x18001293d  mov     ebx, 80004001h
0x180012942  jmp     short loc_1800129BD
0x180012944  cmp     dword ptr [rdi], 4
0x180012947  jz      short loc_18001298E
0x180012949  mov     ecx, 1
0x18001294e  lea     r8, [rsp+270h+var_238]
0x180012953  mov     rdx, rdi
0x180012956  mov     dword ptr [rsp+270h+var_248], ecx
0x18001295a  call    I_CryptXmlEncodeInnerKeyValue
0x18001295f  mov     ebx, eax
0x180012961  test    eax, eax
0x180012963  jns     short loc_18001297C
0x180012965  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001296c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012971  mov     r9d, 0A82h
0x180012977  jmp     loc_1800128E0
0x18001297c  mov     rax, qword ptr [rsp+270h+var_238]
0x180012981  mov     qword ptr [rsp+270h+var_248+8], rax
0x180012986  mov     eax, dword ptr [rsp+270h+var_238+8]
0x18001298a  mov     dword ptr [rsp+270h+var_248+4], eax
0x18001298e  mov     rdx, r14
0x180012991  lea     rcx, [rsp+270h+var_248]
0x180012996  mov     rax, rsi
0x180012999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001299e  mov     ebx, eax
0x1800129a0  test    eax, eax
0x1800129a2  jns     short loc_1800129BB
0x1800129a4  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800129ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800129b0  mov     r9d, 0A90h
0x1800129b6  jmp     loc_1800128E0
0x1800129bb  xor     ebx, ebx
0x1800129bd  mov     rcx, qword ptr [rsp+270h+var_238]
0x1800129c2  test    rcx, rcx
0x1800129c5  jz      short loc_1800129CC
0x1800129c7  call    CryptXmlFree
0x1800129cc  mov     eax, ebx
0x1800129ce  mov     rcx, [rbp+170h+var_20]
0x1800129d5  xor     rcx, rsp; StackCookie
0x1800129d8  call    __security_check_cookie
0x1800129dd  lea     r11, [rsp+270h+var_10]
0x1800129e5  mov     rbx, [r11+30h]
0x1800129e9  mov     rsi, [r11+38h]
0x1800129ed  mov     rsp, r11
0x1800129f0  pop     r14
0x1800129f2  pop     rdi
0x1800129f3  pop     rbp
0x1800129f4  retn
```
