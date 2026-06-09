# FwppXmlWrite_IPSEC_AUTH_CONFIG

- ea: `0x180083acc`
- end: `0x180083b74`
- name: `FwppXmlWrite_IPSEC_AUTH_CONFIG`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180083c1c`

## callees

- `0x1800197d0`
- `0x18003cbd0`
- `0x180083acc`
- `0x180086190`

## string_xrefs

- `0x180083b40`: `IPSEC_AUTH_CONFIG_HMAC_MD5_96`
- `0x180083b25`: `IPSEC_AUTH_CONFIG_GCM_AES_128`
- `0x180083b1c`: `IPSEC_AUTH_CONFIG_GCM_AES_192`
- `0x180083b37`: `IPSEC_AUTH_CONFIG_HMAC_SHA_1_96`
- `0x180083b2e`: `IPSEC_AUTH_CONFIG_HMAC_SHA_256_128`
- `0x180083b13`: `IPSEC_AUTH_CONFIG_GCM_AES_256`
- `0x180083b5b`: `FwppXmlWrite_IPSEC_AUTH_CONFIG`
- `0x180083b05`: `authConfig`
- `0x180083b47`: `authConfig`

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
0x180083acc  mov     [rsp+arg_8], rdx
0x180083ad1  push    rbx
0x180083ad2  sub     rsp, 20h
0x180083ad6  movzx   r9d, byte ptr [r8]
0x180083ada  mov     edx, r9d
0x180083add  test    r9d, r9d
0x180083ae0  jz      short loc_180083B40
0x180083ae2  sub     edx, 1
0x180083ae5  jz      short loc_180083B37
0x180083ae7  sub     edx, 1
0x180083aea  jz      short loc_180083B2E
0x180083aec  sub     edx, 1
0x180083aef  jz      short loc_180083B25
0x180083af1  sub     edx, 1
0x180083af4  jz      short loc_180083B1C
0x180083af6  cmp     edx, 1
0x180083af9  jz      short loc_180083B13
0x180083afb  lea     r8, [rsp+28h+arg_8]
0x180083b00  mov     dword ptr [rsp+28h+arg_8], r9d
0x180083b05  lea     rdx, aAuthconfig; "authConfig"
0x180083b0c  call    FwppXmlWrite_UINT32
0x180083b11  jmp     short loc_180083B53
0x180083b13  lea     r8, aIpsecAuthConfi_3; "IPSEC_AUTH_CONFIG_GCM_AES_256"
0x180083b1a  jmp     short loc_180083B47
0x180083b1c  lea     r8, aIpsecAuthConfi_4; "IPSEC_AUTH_CONFIG_GCM_AES_192"
0x180083b23  jmp     short loc_180083B47
0x180083b25  lea     r8, aIpsecAuthConfi_1; "IPSEC_AUTH_CONFIG_GCM_AES_128"
0x180083b2c  jmp     short loc_180083B47
0x180083b2e  lea     r8, aIpsecAuthConfi_2; "IPSEC_AUTH_CONFIG_HMAC_SHA_256_128"
0x180083b35  jmp     short loc_180083B47
0x180083b37  lea     r8, aIpsecAuthConfi_0; "IPSEC_AUTH_CONFIG_HMAC_SHA_1_96"
0x180083b3e  jmp     short loc_180083B47
0x180083b40  lea     r8, aIpsecAuthConfi; "IPSEC_AUTH_CONFIG_HMAC_MD5_96"
0x180083b47  lea     rdx, aAuthconfig; "authConfig"
0x180083b4e  call    FwppXmlWriteElementUnsafe
0x180083b53  mov     rbx, rax
0x180083b56  test    rax, rax
0x180083b59  jz      short loc_180083B6A
0x180083b5b  lea     rdx, aFwppxmlwriteIp_20; "FwppXmlWrite_IPSEC_AUTH_CONFIG"
0x180083b62  mov     rcx, rax
0x180083b65  call    WfpReportError
0x180083b6a  mov     rax, rbx
0x180083b6d  add     rsp, 20h
0x180083b71  pop     rbx
0x180083b72  retn
```
