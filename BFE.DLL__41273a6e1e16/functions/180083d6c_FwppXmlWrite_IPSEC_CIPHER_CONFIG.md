# FwppXmlWrite_IPSEC_CIPHER_CONFIG

- ea: `0x180083d6c`
- end: `0x180083e30`
- name: `FwppXmlWrite_IPSEC_CIPHER_CONFIG`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180083ed8`

## callees

- `0x1800197d0`
- `0x18003cbd0`
- `0x180083d6c`
- `0x180086190`

## string_xrefs

- `0x180083dea`: `IPSEC_CIPHER_CONFIG_CBC_AES_128`
- `0x180083de1`: `IPSEC_CIPHER_CONFIG_CBC_AES_192`
- `0x180083dfc`: `IPSEC_CIPHER_CONFIG_CBC_DES`
- `0x180083df3`: `IPSEC_CIPHER_CONFIG_CBC_3DES`
- `0x180083dc6`: `IPSEC_CIPHER_CONFIG_GCM_AES_192`
- `0x180083dbd`: `IPSEC_CIPHER_CONFIG_GCM_AES_256`
- `0x180083dd8`: `IPSEC_CIPHER_CONFIG_CBC_AES_256`
- `0x180083dcf`: `IPSEC_CIPHER_CONFIG_GCM_AES_128`
- `0x180083daf`: `cipherConfig`
- `0x180083e03`: `cipherConfig`
- `0x180083e17`: `FwppXmlWrite_IPSEC_CIPHER_CONFIG`

## pseudocode

```c
__int64 __fastcall FwppXmlWrite_IPSEC_CIPHER_CONFIG(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // rax
  const char *v4; // r8
  __int64 v5; // rbx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = a2;
  switch ( *a3 )
  {
    case 1:
      v4 = "IPSEC_CIPHER_CONFIG_CBC_DES";
      break;
    case 2:
      v4 = "IPSEC_CIPHER_CONFIG_CBC_3DES";
      break;
    case 3:
      v4 = "IPSEC_CIPHER_CONFIG_CBC_AES_128";
      break;
    case 4:
      v4 = "IPSEC_CIPHER_CONFIG_CBC_AES_192";
      break;
    case 5:
      v4 = "IPSEC_CIPHER_CONFIG_CBC_AES_256";
      break;
    case 6:
      v4 = "IPSEC_CIPHER_CONFIG_GCM_AES_128";
      break;
    case 7:
      v4 = "IPSEC_CIPHER_CONFIG_GCM_AES_192";
      break;
    case 8:
      v4 = "IPSEC_CIPHER_CONFIG_GCM_AES_256";
      break;
    default:
      LODWORD(v7) = (unsigned __int8)*a3;
      v3 = FwppXmlWrite_UINT32(a1, "cipherConfig", &v7);
      goto LABEL_19;
  }
  v3 = FwppXmlWriteElementUnsafe(a1, "cipherConfig", v4);
LABEL_19:
  v5 = v3;
  if ( v3 )
    WfpReportError(v3, "FwppXmlWrite_IPSEC_CIPHER_CONFIG");
  return v5;
}

```

## disassembly

```asm
0x180083d6c  mov     [rsp+arg_8], rdx
0x180083d71  push    rbx
0x180083d72  sub     rsp, 20h
0x180083d76  movzx   r9d, byte ptr [r8]
0x180083d7a  mov     edx, r9d
0x180083d7d  sub     edx, 1
0x180083d80  jz      short loc_180083DFC
0x180083d82  sub     edx, 1
0x180083d85  jz      short loc_180083DF3
0x180083d87  sub     edx, 1
0x180083d8a  jz      short loc_180083DEA
0x180083d8c  sub     edx, 1
0x180083d8f  jz      short loc_180083DE1
0x180083d91  sub     edx, 1
0x180083d94  jz      short loc_180083DD8
0x180083d96  sub     edx, 1
0x180083d99  jz      short loc_180083DCF
0x180083d9b  sub     edx, 1
0x180083d9e  jz      short loc_180083DC6
0x180083da0  cmp     edx, 1
0x180083da3  jz      short loc_180083DBD
0x180083da5  lea     r8, [rsp+28h+arg_8]
0x180083daa  mov     dword ptr [rsp+28h+arg_8], r9d
0x180083daf  lea     rdx, aCipherconfig; "cipherConfig"
0x180083db6  call    FwppXmlWrite_UINT32
0x180083dbb  jmp     short loc_180083E0F
0x180083dbd  lea     r8, aIpsecCipherCon_4; "IPSEC_CIPHER_CONFIG_GCM_AES_256"
0x180083dc4  jmp     short loc_180083E03
0x180083dc6  lea     r8, aIpsecCipherCon_2; "IPSEC_CIPHER_CONFIG_GCM_AES_192"
0x180083dcd  jmp     short loc_180083E03
0x180083dcf  lea     r8, aIpsecCipherCon_5; "IPSEC_CIPHER_CONFIG_GCM_AES_128"
0x180083dd6  jmp     short loc_180083E03
0x180083dd8  lea     r8, aIpsecCipherCon_3; "IPSEC_CIPHER_CONFIG_CBC_AES_256"
0x180083ddf  jmp     short loc_180083E03
0x180083de1  lea     r8, aIpsecCipherCon_0; "IPSEC_CIPHER_CONFIG_CBC_AES_192"
0x180083de8  jmp     short loc_180083E03
0x180083dea  lea     r8, aIpsecCipherCon; "IPSEC_CIPHER_CONFIG_CBC_AES_128"
0x180083df1  jmp     short loc_180083E03
0x180083df3  lea     r8, aIpsecCipherCon_6; "IPSEC_CIPHER_CONFIG_CBC_3DES"
0x180083dfa  jmp     short loc_180083E03
0x180083dfc  lea     r8, aIpsecCipherCon_1; "IPSEC_CIPHER_CONFIG_CBC_DES"
0x180083e03  lea     rdx, aCipherconfig; "cipherConfig"
0x180083e0a  call    FwppXmlWriteElementUnsafe
0x180083e0f  mov     rbx, rax
0x180083e12  test    rax, rax
0x180083e15  jz      short loc_180083E26
0x180083e17  lea     rdx, aFwppxmlwriteIp_18; "FwppXmlWrite_IPSEC_CIPHER_CONFIG"
0x180083e1e  mov     rcx, rax
0x180083e21  call    WfpReportError
0x180083e26  mov     rax, rbx
0x180083e29  add     rsp, 20h
0x180083e2d  pop     rbx
0x180083e2e  retn
```
