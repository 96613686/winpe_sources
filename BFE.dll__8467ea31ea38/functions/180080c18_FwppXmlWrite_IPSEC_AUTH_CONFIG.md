# FwppXmlWrite_IPSEC_AUTH_CONFIG

- ea: `0x180080c18`
- end: `0x180080cbf`
- name: `FwppXmlWrite_IPSEC_AUTH_CONFIG`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180080d68`

## callees

- `0x180018b74`
- `0x180032494`
- `0x180080c18`
- `0x18008329c`

## string_xrefs

- `0x180080c7a`: `IPSEC_AUTH_CONFIG_HMAC_SHA_256_128`
- `0x180080c83`: `IPSEC_AUTH_CONFIG_HMAC_SHA_1_96`
- `0x180080c8c`: `IPSEC_AUTH_CONFIG_HMAC_MD5_96`
- `0x180080ca7`: `FwppXmlWrite_IPSEC_AUTH_CONFIG`
- `0x180080c5f`: `IPSEC_AUTH_CONFIG_GCM_AES_256`
- `0x180080c68`: `IPSEC_AUTH_CONFIG_GCM_AES_192`
- `0x180080c71`: `IPSEC_AUTH_CONFIG_GCM_AES_128`
- `0x180080c51`: `authConfig`
- `0x180080c93`: `authConfig`

## pseudocode

```c
__int64 __fastcall FwppXmlWrite_IPSEC_AUTH_CONFIG(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // rax
  const char *v4; // r8
  __int64 v5; // rbx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = a2;
  if ( *a3 )
  {
    switch ( *a3 )
    {
      case 1:
        v4 = "IPSEC_AUTH_CONFIG_HMAC_SHA_1_96";
        break;
      case 2:
        v4 = "IPSEC_AUTH_CONFIG_HMAC_SHA_256_128";
        break;
      case 3:
        v4 = "IPSEC_AUTH_CONFIG_GCM_AES_128";
        break;
      case 4:
        v4 = "IPSEC_AUTH_CONFIG_GCM_AES_192";
        break;
      case 5:
        v4 = "IPSEC_AUTH_CONFIG_GCM_AES_256";
        break;
      default:
        LODWORD(v7) = (unsigned __int8)*a3;
        v3 = FwppXmlWrite_UINT32(a1, "authConfig", &v7);
        goto LABEL_15;
    }
  }
  else
  {
    v4 = "IPSEC_AUTH_CONFIG_HMAC_MD5_96";
  }
  v3 = FwppXmlWriteElementUnsafe(a1, "authConfig", v4);
LABEL_15:
  v5 = v3;
  if ( v3 )
    WfpReportError(v3, "FwppXmlWrite_IPSEC_AUTH_CONFIG");
  return v5;
}

```

## disassembly

```asm
0x180080c18  mov     [rsp+arg_8], rdx
0x180080c1d  push    rbx
0x180080c1e  sub     rsp, 20h
0x180080c22  movzx   r9d, byte ptr [r8]
0x180080c26  mov     edx, r9d
0x180080c29  test    r9d, r9d
0x180080c2c  jz      short loc_180080C8C
0x180080c2e  sub     edx, 1
0x180080c31  jz      short loc_180080C83
0x180080c33  sub     edx, 1
0x180080c36  jz      short loc_180080C7A
0x180080c38  sub     edx, 1
0x180080c3b  jz      short loc_180080C71
0x180080c3d  sub     edx, 1
0x180080c40  jz      short loc_180080C68
0x180080c42  cmp     edx, 1
0x180080c45  jz      short loc_180080C5F
0x180080c47  lea     r8, [rsp+28h+arg_8]
0x180080c4c  mov     dword ptr [rsp+28h+arg_8], r9d
0x180080c51  lea     rdx, aAuthconfig; "authConfig"
0x180080c58  call    FwppXmlWrite_UINT32
0x180080c5d  jmp     short loc_180080C9F
0x180080c5f  lea     r8, aIpsecAuthConfi_3; "IPSEC_AUTH_CONFIG_GCM_AES_256"
0x180080c66  jmp     short loc_180080C93
0x180080c68  lea     r8, aIpsecAuthConfi_4; "IPSEC_AUTH_CONFIG_GCM_AES_192"
0x180080c6f  jmp     short loc_180080C93
0x180080c71  lea     r8, aIpsecAuthConfi_1; "IPSEC_AUTH_CONFIG_GCM_AES_128"
0x180080c78  jmp     short loc_180080C93
0x180080c7a  lea     r8, aIpsecAuthConfi_2; "IPSEC_AUTH_CONFIG_HMAC_SHA_256_128"
0x180080c81  jmp     short loc_180080C93
0x180080c83  lea     r8, aIpsecAuthConfi_0; "IPSEC_AUTH_CONFIG_HMAC_SHA_1_96"
0x180080c8a  jmp     short loc_180080C93
0x180080c8c  lea     r8, aIpsecAuthConfi; "IPSEC_AUTH_CONFIG_HMAC_MD5_96"
0x180080c93  lea     rdx, aAuthconfig; "authConfig"
0x180080c9a  call    FwppXmlWriteElementUnsafe
0x180080c9f  mov     rbx, rax
0x180080ca2  test    rax, rax
0x180080ca5  jz      short loc_180080CB6
0x180080ca7  lea     rdx, aFwppxmlwriteIp_20; "FwppXmlWrite_IPSEC_AUTH_CONFIG"
0x180080cae  mov     rcx, rax
0x180080cb1  call    WfpReportError
0x180080cb6  mov     rax, rbx
0x180080cb9  add     rsp, 20h
0x180080cbd  pop     rbx
0x180080cbe  retn
```
