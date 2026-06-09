# FwppXmlWrite_IPSEC_TOKEN0

- ea: `0x180085260`
- end: `0x1800853f0`
- name: `FwppXmlWrite_IPSEC_TOKEN0`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800197d0`
- `0x18003cbd0`
- `0x18003cc6c`
- `0x18003cd5c`
- `0x180058060`
- `0x180085260`
- `0x180086190`

## string_xrefs

- `0x1800852c5`: `IPSEC_TOKEN_TYPE_MACHINE`
- `0x180085326`: `IPSEC_TOKEN_PRINCIPAL_LOCAL`
- `0x18008531d`: `IPSEC_TOKEN_PRINCIPAL_PEER`
- `0x1800852bc`: `IPSEC_TOKEN_TYPE_IMPERSONATION`
- `0x1800852e3`: `FwppXmlWrite_IPSEC_TOKEN_TYPE`
- `0x180085373`: `IPSEC_TOKEN_MODE_EXTENDED`
- `0x18008539a`: `FwppXmlWrite_IPSEC_TOKEN_MODE`
- `0x180085344`: `FwppXmlWrite_IPSEC_TOKEN_PRINCIPAL`
- `0x18008537c`: `IPSEC_TOKEN_MODE_MAIN`
- `0x1800853ad`: `token`
- `0x1800853d4`: `FwppXmlWrite_IPSEC_TOKEN0`

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
0x180085260  push    rbx
0x180085262  push    rbp
0x180085263  push    rsi
0x180085264  push    rdi
0x180085265  sub     rsp, 38h
0x180085269  xor     r9d, r9d
0x18008526c  mov     [rsp+58h+var_38], 0
0x180085275  mov     rsi, r8
0x180085278  mov     rbp, rdx
0x18008527b  mov     rdi, rcx
0x18008527e  lea     r8d, [r9+1]
0x180085282  call    FwppXmlWriteStartTagWithAttr
0x180085287  mov     rbx, rax
0x18008528a  test    rax, rax
0x18008528d  jnz     loc_1800853CF
0x180085293  mov     r8d, [rsi]
0x180085296  test    r8d, r8d
0x180085299  jz      short loc_1800852C5
0x18008529b  cmp     r8d, 1
0x18008529f  jz      short loc_1800852BC
0x1800852a1  mov     [rsp+58h+arg_18], r8d
0x1800852a6  lea     rdx, aType; "type"
0x1800852ad  lea     r8, [rsp+58h+arg_18]
0x1800852b2  mov     rcx, rdi
0x1800852b5  call    FwppXmlWrite_UINT32
0x1800852ba  jmp     short loc_1800852DB
0x1800852bc  lea     r8, aIpsecTokenType_0; "IPSEC_TOKEN_TYPE_IMPERSONATION"
0x1800852c3  jmp     short loc_1800852CC
0x1800852c5  lea     r8, aIpsecTokenType; "IPSEC_TOKEN_TYPE_MACHINE"
0x1800852cc  lea     rdx, aType; "type"
0x1800852d3  mov     rcx, rdi
0x1800852d6  call    FwppXmlWriteElementUnsafe
0x1800852db  mov     rbx, rax
0x1800852de  test    rax, rax
0x1800852e1  jz      short loc_1800852F7
0x1800852e3  lea     rdx, aFwppxmlwriteIp_26; "FwppXmlWrite_IPSEC_TOKEN_TYPE"
0x1800852ea  mov     rcx, rbx
0x1800852ed  call    WfpReportError
0x1800852f2  jmp     loc_1800853D4
0x1800852f7  mov     edx, [rsi+4]
0x1800852fa  test    edx, edx
0x1800852fc  jz      short loc_180085326
0x1800852fe  cmp     edx, 1
0x180085301  jz      short loc_18008531D
0x180085303  mov     [rsp+58h+arg_18], edx
0x180085307  lea     r8, [rsp+58h+arg_18]
0x18008530c  lea     rdx, aPrincipal; "principal"
0x180085313  mov     rcx, rdi
0x180085316  call    FwppXmlWrite_UINT32
0x18008531b  jmp     short loc_18008533C
0x18008531d  lea     r8, aIpsecTokenPrin; "IPSEC_TOKEN_PRINCIPAL_PEER"
0x180085324  jmp     short loc_18008532D
0x180085326  lea     r8, aIpsecTokenPrin_0; "IPSEC_TOKEN_PRINCIPAL_LOCAL"
0x18008532d  lea     rdx, aPrincipal; "principal"
0x180085334  mov     rcx, rdi
0x180085337  call    FwppXmlWriteElementUnsafe
0x18008533c  mov     rbx, rax
0x18008533f  test    rax, rax
0x180085342  jz      short loc_18008534D
0x180085344  lea     rdx, aFwppxmlwriteIp_39; "FwppXmlWrite_IPSEC_TOKEN_PRINCIPAL"
0x18008534b  jmp     short loc_1800852EA
0x18008534d  mov     edx, [rsi+8]
0x180085350  test    edx, edx
0x180085352  jz      short loc_18008537C
0x180085354  cmp     edx, 1
0x180085357  jz      short loc_180085373
0x180085359  mov     [rsp+58h+arg_18], edx
0x18008535d  lea     r8, [rsp+58h+arg_18]
0x180085362  lea     rdx, aMode; "mode"
0x180085369  mov     rcx, rdi
0x18008536c  call    FwppXmlWrite_UINT32
0x180085371  jmp     short loc_180085392
0x180085373  lea     r8, aIpsecTokenMode; "IPSEC_TOKEN_MODE_EXTENDED"
0x18008537a  jmp     short loc_180085383
0x18008537c  lea     r8, aIpsecTokenMode_0; "IPSEC_TOKEN_MODE_MAIN"
0x180085383  lea     rdx, aMode; "mode"
0x18008538a  mov     rcx, rdi
0x18008538d  call    FwppXmlWriteElementUnsafe
0x180085392  mov     rbx, rax
0x180085395  test    rax, rax
0x180085398  jz      short loc_1800853A6
0x18008539a  lea     rdx, aFwppxmlwriteIp_28; "FwppXmlWrite_IPSEC_TOKEN_MODE"
0x1800853a1  jmp     loc_1800852EA
0x1800853a6  lea     r8, [rsi+10h]
0x1800853aa  mov     rcx, rdi
0x1800853ad  lea     rdx, aToken; "token"
0x1800853b4  call    FwppXmlWrite_UINT64
0x1800853b9  mov     rbx, rax
0x1800853bc  test    rax, rax
0x1800853bf  jnz     short loc_1800853CF
0x1800853c1  mov     rdx, rbp
0x1800853c4  mov     rcx, rdi
0x1800853c7  call    FwppXmlWriteEndTag
0x1800853cc  mov     rbx, rax
0x1800853cf  test    rbx, rbx
0x1800853d2  jz      short loc_1800853E3
0x1800853d4  lea     rdx, aFwppxmlwriteIp_33; "FwppXmlWrite_IPSEC_TOKEN0"
0x1800853db  mov     rcx, rbx
0x1800853de  call    WfpReportError
0x1800853e3  mov     rax, rbx
0x1800853e6  add     rsp, 38h
0x1800853ea  pop     rdi
0x1800853eb  pop     rsi
0x1800853ec  pop     rbp
0x1800853ed  pop     rbx
0x1800853ee  retn
```
