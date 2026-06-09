# FwppXmlWrite_IPSEC_TOKEN0

- ea: `0x180082380`
- end: `0x18008250f`
- name: `FwppXmlWrite_IPSEC_TOKEN0`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180018b74`
- `0x180032494`
- `0x180032530`
- `0x180032620`
- `0x1800561f0`
- `0x180082380`
- `0x18008329c`

## string_xrefs

- `0x180082403`: `FwppXmlWrite_IPSEC_TOKEN_TYPE`
- `0x1800823dc`: `IPSEC_TOKEN_TYPE_IMPERSONATION`
- `0x1800823e5`: `IPSEC_TOKEN_TYPE_MACHINE`
- `0x18008249c`: `IPSEC_TOKEN_MODE_MAIN`
- `0x180082464`: `FwppXmlWrite_IPSEC_TOKEN_PRINCIPAL`
- `0x18008243d`: `IPSEC_TOKEN_PRINCIPAL_PEER`
- `0x180082446`: `IPSEC_TOKEN_PRINCIPAL_LOCAL`
- `0x1800824ba`: `FwppXmlWrite_IPSEC_TOKEN_MODE`
- `0x180082493`: `IPSEC_TOKEN_MODE_EXTENDED`
- `0x1800824f4`: `FwppXmlWrite_IPSEC_TOKEN0`
- `0x1800824cd`: `token`

## pseudocode

```c
__int64 __fastcall FwppXmlWrite_IPSEC_TOKEN0(__int64 a1, __int64 a2, int *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  const char *v8; // r8
  const char *v9; // rdx
  int v10; // edx
  __int64 v11; // rax
  const char *v12; // r8
  int v13; // edx
  __int64 v14; // rax
  const char *v15; // r8
  int v17; // [rsp+78h] [rbp+20h] BYREF

  v6 = FwppXmlWriteStartTagWithAttr(a1, a2, 1, 0, 0);
  if ( v6 )
    goto LABEL_29;
  if ( *a3 )
  {
    if ( *a3 != 1 )
    {
      v17 = *a3;
      v7 = FwppXmlWrite_UINT32(a1, "type", &v17);
      goto LABEL_8;
    }
    v8 = "IPSEC_TOKEN_TYPE_IMPERSONATION";
  }
  else
  {
    v8 = "IPSEC_TOKEN_TYPE_MACHINE";
  }
  v7 = FwppXmlWriteElementUnsafe(a1, "type", v8);
LABEL_8:
  v6 = v7;
  if ( v7 )
  {
    v9 = "FwppXmlWrite_IPSEC_TOKEN_TYPE";
LABEL_10:
    WfpReportError(v6, v9);
LABEL_30:
    WfpReportError(v6, "FwppXmlWrite_IPSEC_TOKEN0");
    return v6;
  }
  v10 = a3[1];
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      v17 = a3[1];
      v11 = FwppXmlWrite_UINT32(a1, "principal", &v17);
      goto LABEL_17;
    }
    v12 = "IPSEC_TOKEN_PRINCIPAL_PEER";
  }
  else
  {
    v12 = "IPSEC_TOKEN_PRINCIPAL_LOCAL";
  }
  v11 = FwppXmlWriteElementUnsafe(a1, "principal", v12);
LABEL_17:
  v6 = v11;
  if ( v11 )
  {
    v9 = "FwppXmlWrite_IPSEC_TOKEN_PRINCIPAL";
    goto LABEL_10;
  }
  v13 = a3[2];
  if ( !v13 )
  {
    v15 = "IPSEC_TOKEN_MODE_MAIN";
    goto LABEL_24;
  }
  if ( v13 == 1 )
  {
    v15 = "IPSEC_TOKEN_MODE_EXTENDED";
LABEL_24:
    v14 = FwppXmlWriteElementUnsafe(a1, "mode", v15);
    goto LABEL_25;
  }
  v17 = a3[2];
  v14 = FwppXmlWrite_UINT32(a1, "mode", &v17);
LABEL_25:
  v6 = v14;
  if ( v14 )
  {
    v9 = "FwppXmlWrite_IPSEC_TOKEN_MODE";
    goto LABEL_10;
  }
  v6 = FwppXmlWrite_UINT64(a1, "token", a3 + 4);
  if ( !v6 )
    v6 = FwppXmlWriteEndTag(a1, a2);
LABEL_29:
  if ( v6 )
    goto LABEL_30;
  return v6;
}

```

## disassembly

```asm
0x180082380  push    rbx
0x180082382  push    rbp
0x180082383  push    rsi
0x180082384  push    rdi
0x180082385  sub     rsp, 38h
0x180082389  xor     r9d, r9d
0x18008238c  mov     [rsp+58h+var_38], 0
0x180082395  mov     rsi, r8
0x180082398  mov     rbp, rdx
0x18008239b  mov     rdi, rcx
0x18008239e  lea     r8d, [r9+1]
0x1800823a2  call    FwppXmlWriteStartTagWithAttr
0x1800823a7  mov     rbx, rax
0x1800823aa  test    rax, rax
0x1800823ad  jnz     loc_1800824EF
0x1800823b3  mov     r8d, [rsi]
0x1800823b6  test    r8d, r8d
0x1800823b9  jz      short loc_1800823E5
0x1800823bb  cmp     r8d, 1
0x1800823bf  jz      short loc_1800823DC
0x1800823c1  mov     [rsp+58h+arg_18], r8d
0x1800823c6  lea     rdx, aType; "type"
0x1800823cd  lea     r8, [rsp+58h+arg_18]
0x1800823d2  mov     rcx, rdi
0x1800823d5  call    FwppXmlWrite_UINT32
0x1800823da  jmp     short loc_1800823FB
0x1800823dc  lea     r8, aIpsecTokenType_0; "IPSEC_TOKEN_TYPE_IMPERSONATION"
0x1800823e3  jmp     short loc_1800823EC
0x1800823e5  lea     r8, aIpsecTokenType; "IPSEC_TOKEN_TYPE_MACHINE"
0x1800823ec  lea     rdx, aType; "type"
0x1800823f3  mov     rcx, rdi
0x1800823f6  call    FwppXmlWriteElementUnsafe
0x1800823fb  mov     rbx, rax
0x1800823fe  test    rax, rax
0x180082401  jz      short loc_180082417
0x180082403  lea     rdx, aFwppxmlwriteIp_26; "FwppXmlWrite_IPSEC_TOKEN_TYPE"
0x18008240a  mov     rcx, rbx
0x18008240d  call    WfpReportError
0x180082412  jmp     loc_1800824F4
0x180082417  mov     edx, [rsi+4]
0x18008241a  test    edx, edx
0x18008241c  jz      short loc_180082446
0x18008241e  cmp     edx, 1
0x180082421  jz      short loc_18008243D
0x180082423  mov     [rsp+58h+arg_18], edx
0x180082427  lea     r8, [rsp+58h+arg_18]
0x18008242c  lea     rdx, aPrincipal; "principal"
0x180082433  mov     rcx, rdi
0x180082436  call    FwppXmlWrite_UINT32
0x18008243b  jmp     short loc_18008245C
0x18008243d  lea     r8, aIpsecTokenPrin; "IPSEC_TOKEN_PRINCIPAL_PEER"
0x180082444  jmp     short loc_18008244D
0x180082446  lea     r8, aIpsecTokenPrin_0; "IPSEC_TOKEN_PRINCIPAL_LOCAL"
0x18008244d  lea     rdx, aPrincipal; "principal"
0x180082454  mov     rcx, rdi
0x180082457  call    FwppXmlWriteElementUnsafe
0x18008245c  mov     rbx, rax
0x18008245f  test    rax, rax
0x180082462  jz      short loc_18008246D
0x180082464  lea     rdx, aFwppxmlwriteIp_39; "FwppXmlWrite_IPSEC_TOKEN_PRINCIPAL"
0x18008246b  jmp     short loc_18008240A
0x18008246d  mov     edx, [rsi+8]
0x180082470  test    edx, edx
0x180082472  jz      short loc_18008249C
0x180082474  cmp     edx, 1
0x180082477  jz      short loc_180082493
0x180082479  mov     [rsp+58h+arg_18], edx
0x18008247d  lea     r8, [rsp+58h+arg_18]
0x180082482  lea     rdx, aMode; "mode"
0x180082489  mov     rcx, rdi
0x18008248c  call    FwppXmlWrite_UINT32
0x180082491  jmp     short loc_1800824B2
0x180082493  lea     r8, aIpsecTokenMode; "IPSEC_TOKEN_MODE_EXTENDED"
0x18008249a  jmp     short loc_1800824A3
0x18008249c  lea     r8, aIpsecTokenMode_0; "IPSEC_TOKEN_MODE_MAIN"
0x1800824a3  lea     rdx, aMode; "mode"
0x1800824aa  mov     rcx, rdi
0x1800824ad  call    FwppXmlWriteElementUnsafe
0x1800824b2  mov     rbx, rax
0x1800824b5  test    rax, rax
0x1800824b8  jz      short loc_1800824C6
0x1800824ba  lea     rdx, aFwppxmlwriteIp_28; "FwppXmlWrite_IPSEC_TOKEN_MODE"
0x1800824c1  jmp     loc_18008240A
0x1800824c6  lea     r8, [rsi+10h]
0x1800824ca  mov     rcx, rdi
0x1800824cd  lea     rdx, aToken; "token"
0x1800824d4  call    FwppXmlWrite_UINT64
0x1800824d9  mov     rbx, rax
0x1800824dc  test    rax, rax
0x1800824df  jnz     short loc_1800824EF
0x1800824e1  mov     rdx, rbp
0x1800824e4  mov     rcx, rdi
0x1800824e7  call    FwppXmlWriteEndTag
0x1800824ec  mov     rbx, rax
0x1800824ef  test    rbx, rbx
0x1800824f2  jz      short loc_180082503
0x1800824f4  lea     rdx, aFwppxmlwriteIp_33; "FwppXmlWrite_IPSEC_TOKEN0"
0x1800824fb  mov     rcx, rbx
0x1800824fe  call    WfpReportError
0x180082503  mov     rax, rbx
0x180082506  add     rsp, 38h
0x18008250a  pop     rdi
0x18008250b  pop     rsi
0x18008250c  pop     rbp
0x18008250d  pop     rbx
0x18008250e  retn
```
