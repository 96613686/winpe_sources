# QueryRootKeyObjects

- ea: `0x180006908`
- end: `0x180006cb0`
- name: `QueryRootKeyObjects`
- size: `936`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005330`
- `0x1800058a0`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180001fdc`
- `0x180006908`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180006a1f`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180006ae6`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180006a1f`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180006ae6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006b7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180006b7e`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180006c4f`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180006c4f`

## string_xrefs

- `0x180006a40`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180006c70`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x18000699b`: `msKds-CreateTime`
- `0x180006b02`: `msKds-CreateTime`

## pseudocode

```c
__int64 __fastcall QueryRootKeyObjects(LDAP *a1, WCHAR *a2, __int64 a3, __int64 a4, __int64 a5, PLDAPMessage *res)
{
  unsigned int v8; // r9d
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // r14d
  __int64 v13; // rbx
  int v14; // r15d
  int v15; // eax
  int v16; // esi
  int v17; // eax
  unsigned __int64 v18; // rbx
  wchar_t *v19; // rax
  wchar_t *v20; // rdi
  unsigned int v21; // r9d
  unsigned int v22; // ecx
  wchar_t *v23; // rdx
  wchar_t *v24; // rcx
  wchar_t *v25; // rax
  signed int v26; // eax
  PWSTR attrs[14]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[48]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v32[48]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v33[48]; // [rsp+150h] [rbp+50h] BYREF
  wchar_t Buffer[48]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v35[48]; // [rsp+210h] [rbp+110h] BYREF

  memset_0(v33, 0, 0x54u);
  memset_0(Buffer, 0, 0x58u);
  attrs[12] = 0;
  attrs[0] = (PWSTR)L"msKds-KDFAlgorithmID";
  attrs[2] = (PWSTR)L"msKds-UseStartTime";
  attrs[1] = (PWSTR)L"msKds-KDFParam";
  attrs[3] = (PWSTR)L"msKds-CreateTime";
  attrs[4] = (PWSTR)L"msKds-RootKeyData";
  attrs[5] = (PWSTR)L"msKds-Version";
  attrs[6] = (PWSTR)L"msKds-DomainID";
  attrs[7] = L"cn";
  attrs[8] = (PWSTR)L"msKds-SecretAgreementAlgorithmID";
  attrs[9] = (PWSTR)L"msKds-SecretAgreementParam";
  attrs[10] = (PWSTR)L"msKds-PrivateKeyLength";
  attrs[11] = (PWSTR)L"msKds-PublicKeyLength";
  if ( !a5 )
  {
    v13 = 62;
    v12 = 0;
    goto LABEL_10;
  }
  if ( !(unsigned int)_o__ui64tow_s(a5, v31, 21) )
  {
    v11 = swprintf_s(Buffer, 0x2Cu, L"(%s<=%s)", L"msKds-UseStartTime", v31);
    v12 = v11;
    if ( v11 < 0 )
    {
      v8 = 557;
      goto LABEL_4;
    }
    v13 = 2LL * v11 + 62;
LABEL_10:
    v14 = 0;
    if ( a3 )
    {
      v15 = swprintf_s(v35, 0x2Au, L"(cn=%s)", a3);
      v14 = v15;
      if ( v15 < 0 )
      {
        v8 = 574;
        goto LABEL_4;
      }
      v13 += 2LL * v15;
    }
    v16 = 0;
    if ( a4 )
    {
      if ( (unsigned int)_o__ui64tow_s(a4, v32, 21) )
      {
        v8 = 586;
        goto LABEL_4;
      }
      v17 = swprintf_s(v33, 0x2Au, L"(%s>=%s)", L"msKds-CreateTime", v32);
      v16 = v17;
      if ( v17 < 0 )
      {
        v8 = 598;
        goto LABEL_4;
      }
      v13 += 2LL * v17;
    }
    v18 = v13 + 8;
    v19 = (wchar_t *)SIDKeyProvAlloc(v18);
    v20 = v19;
    if ( !v19 )
    {
      v9 = -2147024882;
      v8 = 612;
      v10 = -2147024882;
      goto LABEL_5;
    }
    if ( v12 || v16 || v14 )
    {
      v23 = v33;
      if ( !a4 )
        v23 = (wchar_t *)&dword_18001D4F4;
      v24 = Buffer;
      v25 = v35;
      if ( !a5 )
        v24 = (wchar_t *)&dword_18001D4F4;
      if ( !a3 )
        v25 = (wchar_t *)&dword_18001D4F4;
      if ( swprintf_s(v20, v18 >> 1, L"(&%s%s%s%s)", L"(objectClass=msKds-ProvRootKey)", v25, v24, v23) < 0 )
      {
        v21 = 630;
        goto LABEL_27;
      }
    }
    else if ( (int)_o_wcscpy_s(v19, v18 >> 1, L"(objectClass=msKds-ProvRootKey)") < 0 )
    {
      v21 = 642;
LABEL_27:
      v9 = -2147467259;
      v22 = -2147467259;
      goto LABEL_41;
    }
    v9 = 0;
    v26 = ldap_search_ext_sW(a1, a2, 1u, v20, attrs, 0, 0, 0, 0, 0, res);
    if ( !v26 )
    {
LABEL_42:
      SIDKeyProvFree(v20);
      return v9;
    }
    if ( v26 > 0 )
      v9 = (unsigned __int16)v26 | 0x80070000;
    else
      v9 = v26;
    v21 = 663;
    v22 = v9;
LABEL_41:
    SidKeyDebugTraceError(v22, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v21);
    goto LABEL_42;
  }
  v8 = 545;
LABEL_4:
  v9 = -2147467259;
  v10 = -2147467259;
LABEL_5:
  SidKeyDebugTraceError(v10, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v8);
  return v9;
}

```

## disassembly

```asm
0x180006908  push    rbp
0x18000690a  push    rbx
0x18000690b  push    rsi
0x18000690c  push    rdi
0x18000690d  push    r12
0x18000690f  push    r13
0x180006911  push    r14
0x180006913  push    r15
0x180006915  lea     rbp, [rsp-188h]
0x18000691d  sub     rsp, 288h
0x180006924  mov     rax, cs:__security_cookie
0x18000692b  xor     rax, rsp
0x18000692e  mov     [rbp+1C0h+var_50], rax
0x180006935  mov     rax, [rbp+1C0h+arg_28]
0x18000693c  mov     r12, r8
0x18000693f  mov     [rsp+2C0h+base], rdx
0x180006944  mov     r13, r9
0x180006947  xor     edx, edx; Val
0x180006949  mov     [rsp+2C0h+ld], rcx
0x18000694e  lea     rcx, [rbp+1C0h+var_170]; void *
0x180006952  mov     [rsp+2C0h+var_260], rax
0x180006957  lea     r8d, [rdx+54h]; Size
0x18000695b  call    memset_0
0x180006960  xor     edx, edx; Val
0x180006962  lea     rcx, [rbp+1C0h+Buffer]; void *
0x180006969  lea     r8d, [rdx+58h]; Size
0x18000696d  call    memset_0
0x180006972  lea     rax, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x180006979  mov     [rbp+1C0h+var_1E0], 0
0x180006981  mov     [rbp+1C0h+var_240], rax
0x180006985  lea     rbx, aMskdsUsestartt; "msKds-UseStartTime"
0x18000698c  lea     rax, aMskdsKdfparam; "msKds-KDFParam"
0x180006993  mov     [rbp+1C0h+var_230], rbx
0x180006997  mov     [rbp+1C0h+var_238], rax
0x18000699b  lea     rax, aMskdsCreatetim; "msKds-CreateTime"
0x1800069a2  mov     [rbp+1C0h+var_228], rax
0x1800069a6  lea     rax, aMskdsRootkeyda; "msKds-RootKeyData"
0x1800069ad  mov     [rbp+1C0h+var_220], rax
0x1800069b1  lea     rax, aMskdsVersion; "msKds-Version"
0x1800069b8  mov     [rbp+1C0h+var_218], rax
0x1800069bc  lea     rax, aMskdsDomainid; "msKds-DomainID"
0x1800069c3  mov     [rbp+1C0h+var_210], rax
0x1800069c7  lea     rax, aCn; "cn"
0x1800069ce  mov     [rbp+1C0h+var_208], rax
0x1800069d2  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x1800069d9  mov     [rbp+1C0h+var_200], rax
0x1800069dd  lea     rax, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x1800069e4  mov     [rbp+1C0h+var_1F8], rax
0x1800069e8  lea     rax, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x1800069ef  mov     [rbp+1C0h+var_1F0], rax
0x1800069f3  lea     rax, aMskdsPublickey; "msKds-PublicKeyLength"
0x1800069fa  mov     [rbp+1C0h+var_1E8], rax
0x1800069fe  mov     rax, [rbp+1C0h+arg_20]
0x180006a05  test    rax, rax
0x180006a08  jz      loc_180006A8E
0x180006a0e  mov     r9d, 0Ah
0x180006a14  lea     rdx, [rbp+1C0h+var_1D0]
0x180006a18  mov     rcx, rax
0x180006a1b  lea     r8d, [r9+0Bh]
0x180006a1f  call    cs:__imp__o__ui64tow_s
0x180006a25  test    eax, eax
0x180006a27  jz      short loc_180006A51
0x180006a29  mov     r9d, 221h; unsigned int
0x180006a2f  mov     ebx, 80004005h
0x180006a34  mov     ecx, 80004005h; unsigned int
0x180006a39  lea     rdx, aHr; "hr"
0x180006a40  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180006a47  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180006a4c  jmp     loc_180006C8B
0x180006a51  lea     rax, [rbp+1C0h+var_1D0]
0x180006a55  mov     r9, rbx
0x180006a58  lea     r8, aSS_0; "(%s<=%s)"
0x180006a5f  mov     [rsp+2C0h+attrs], rax
0x180006a64  mov     edx, 2Ch ; ','; BufferCount
0x180006a69  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x180006a70  call    swprintf_s
0x180006a75  movsxd  r14, eax
0x180006a78  test    eax, eax
0x180006a7a  jns     short loc_180006A84
0x180006a7c  mov     r9d, 22Dh
0x180006a82  jmp     short loc_180006A2F
0x180006a84  lea     rbx, ds:3Eh[r14*2]
0x180006a8c  jmp     short loc_180006A96
0x180006a8e  mov     ebx, 3Eh ; '>'
0x180006a93  xor     r14d, r14d
0x180006a96  xor     r15d, r15d
0x180006a99  lea     edi, [r15+2Ah]
0x180006a9d  test    r12, r12
0x180006aa0  jz      short loc_180006AD0
0x180006aa2  mov     r9, r12
0x180006aa5  lea     r8, aCnS; "(cn=%s)"
0x180006aac  mov     edx, edi; BufferCount
0x180006aae  lea     rcx, [rbp+1C0h+var_B0]; Buffer
0x180006ab5  call    swprintf_s
0x180006aba  movsxd  r15, eax
0x180006abd  test    eax, eax
0x180006abf  jns     short loc_180006ACC
0x180006ac1  mov     r9d, 23Eh
0x180006ac7  jmp     loc_180006A2F
0x180006acc  lea     rbx, [rbx+r15*2]
0x180006ad0  xor     esi, esi
0x180006ad2  test    r13, r13
0x180006ad5  jz      short loc_180006B34
0x180006ad7  lea     r9d, [rsi+0Ah]
0x180006adb  mov     rcx, r13
0x180006ade  lea     r8d, [rsi+15h]
0x180006ae2  lea     rdx, [rbp+1C0h+var_1A0]
0x180006ae6  call    cs:__imp__o__ui64tow_s
0x180006aec  test    eax, eax
0x180006aee  jz      short loc_180006AFB
0x180006af0  mov     r9d, 24Ah
0x180006af6  jmp     loc_180006A2F
0x180006afb  lea     rax, [rbp+1C0h+var_1A0]
0x180006aff  mov     rdx, rdi; BufferCount
0x180006b02  lea     r9, aMskdsCreatetim; "msKds-CreateTime"
0x180006b09  mov     [rsp+2C0h+attrs], rax
0x180006b0e  lea     r8, aSS_1; "(%s>=%s)"
0x180006b15  lea     rcx, [rbp+1C0h+var_170]; Buffer
0x180006b19  call    swprintf_s
0x180006b1e  movsxd  rsi, eax
0x180006b21  test    eax, eax
0x180006b23  jns     short loc_180006B30
0x180006b25  mov     r9d, 256h
0x180006b2b  jmp     loc_180006A2F
0x180006b30  lea     rbx, [rbx+rsi*2]
0x180006b34  add     rbx, 8
0x180006b38  mov     rcx, rbx; unsigned __int64
0x180006b3b  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180006b40  mov     rdi, rax
0x180006b43  test    rax, rax
0x180006b46  jnz     short loc_180006B5D
0x180006b48  mov     ebx, 8007000Eh
0x180006b4d  mov     r9d, 264h
0x180006b53  mov     ecx, 8007000Eh
0x180006b58  jmp     loc_180006A39
0x180006b5d  test    r14d, r14d
0x180006b60  jnz     short loc_180006BA1
0x180006b62  xor     r14d, r14d
0x180006b65  test    esi, esi
0x180006b67  jnz     short loc_180006BA4
0x180006b69  test    r15d, r15d
0x180006b6c  jnz     short loc_180006BA4
0x180006b6e  shr     rbx, 1
0x180006b71  lea     r8, aObjectclassMsk; "(objectClass=msKds-ProvRootKey)"
0x180006b78  mov     rdx, rbx
0x180006b7b  mov     rcx, rdi
0x180006b7e  call    cs:__imp__o_wcscpy_s
0x180006b84  test    eax, eax
0x180006b86  jns     loc_180006C0D
0x180006b8c  mov     r9d, 282h
0x180006b92  mov     ebx, 80004005h
0x180006b97  mov     ecx, 80004005h
0x180006b9c  jmp     loc_180006C70
0x180006ba1  xor     r14d, r14d
0x180006ba4  lea     r8, dword_18001D4F4
0x180006bab  test    r13, r13
0x180006bae  lea     rdx, [rbp+1C0h+var_170]
0x180006bb2  cmovz   rdx, r8
0x180006bb6  lea     rcx, [rbp+1C0h+Buffer]
0x180006bbd  cmp     [rbp+1C0h+arg_20], r14
0x180006bc4  lea     rax, [rbp+1C0h+var_B0]
0x180006bcb  mov     [rsp+2C0h+ServerControls], rdx
0x180006bd0  lea     r9, aObjectclassMsk; "(objectClass=msKds-ProvRootKey)"
0x180006bd7  cmovz   rcx, r8
0x180006bdb  test    r12, r12
0x180006bde  mov     qword ptr [rsp+2C0h+attrsonly], rcx
0x180006be3  mov     rcx, rdi; Buffer
0x180006be6  cmovz   rax, r8
0x180006bea  shr     rbx, 1
0x180006bed  mov     rdx, rbx; BufferCount
0x180006bf0  mov     [rsp+2C0h+attrs], rax
0x180006bf5  lea     r8, aSSSS; "(&%s%s%s%s)"
0x180006bfc  call    swprintf_s
0x180006c01  test    eax, eax
0x180006c03  jns     short loc_180006C0D
0x180006c05  mov     r9d, 276h
0x180006c0b  jmp     short loc_180006B92
0x180006c0d  mov     rax, [rsp+2C0h+var_260]
0x180006c12  mov     r9, rdi; filter
0x180006c15  mov     rdx, [rsp+2C0h+base]; base
0x180006c1a  mov     r8d, 1; scope
0x180006c20  mov     rcx, [rsp+2C0h+ld]; ld
0x180006c25  mov     ebx, r14d
0x180006c28  mov     [rsp+2C0h+res], rax; res
0x180006c2d  lea     rax, [rbp+1C0h+var_240]
0x180006c31  mov     [rsp+2C0h+SizeLimit], r14d; SizeLimit
0x180006c36  mov     [rsp+2C0h+timeout], r14; timeout
0x180006c3b  mov     [rsp+2C0h+ClientControls], r14; ClientControls
0x180006c40  mov     [rsp+2C0h+ServerControls], r14; ServerControls
0x180006c45  mov     [rsp+2C0h+attrsonly], r14d; attrsonly
0x180006c4a  mov     [rsp+2C0h+attrs], rax; attrs
0x180006c4f  call    cs:__imp_ldap_search_ext_sW
0x180006c55  test    eax, eax
0x180006c57  jz      short loc_180006C83
0x180006c59  jg      short loc_180006C5F
0x180006c5b  mov     ebx, eax
0x180006c5d  jmp     short loc_180006C68
0x180006c5f  movzx   ebx, ax
0x180006c62  or      ebx, 80070000h
0x180006c68  mov     r9d, 297h; unsigned int
0x180006c6e  mov     ecx, ebx; unsigned int
0x180006c70  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180006c77  lea     rdx, aHr; "hr"
0x180006c7e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180006c83  mov     rcx, rdi; lpMem
0x180006c86  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180006c8b  mov     eax, ebx
0x180006c8d  mov     rcx, [rbp+1C0h+var_50]
0x180006c94  xor     rcx, rsp; StackCookie
0x180006c97  call    __security_check_cookie
0x180006c9c  add     rsp, 288h
0x180006ca3  pop     r15
0x180006ca5  pop     r14
0x180006ca7  pop     r13
0x180006ca9  pop     r12
0x180006cab  pop     rdi
0x180006cac  pop     rsi
0x180006cad  pop     rbx
0x180006cae  pop     rbp
0x180006caf  retn
```
