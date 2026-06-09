# FwppXmlWrite_IPSEC_CIPHER_CONFIG

- ea: `0x180080eb4`
- end: `0x180080f77`
- name: `FwppXmlWrite_IPSEC_CIPHER_CONFIG`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180081020`

## callees

- `0x180018b74`
- `0x180032494`
- `0x180080eb4`
- `0x18008329c`

## string_xrefs

- `0x180080f3b`: `IPSEC_CIPHER_CONFIG_CBC_3DES`
- `0x180080f44`: `IPSEC_CIPHER_CONFIG_CBC_DES`
- `0x180080f17`: `IPSEC_CIPHER_CONFIG_GCM_AES_128`
- `0x180080f20`: `IPSEC_CIPHER_CONFIG_CBC_AES_256`
- `0x180080f29`: `IPSEC_CIPHER_CONFIG_CBC_AES_192`
- `0x180080f32`: `IPSEC_CIPHER_CONFIG_CBC_AES_128`
- `0x180080f5f`: `FwppXmlWrite_IPSEC_CIPHER_CONFIG`
- `0x180080f05`: `IPSEC_CIPHER_CONFIG_GCM_AES_256`
- `0x180080f0e`: `IPSEC_CIPHER_CONFIG_GCM_AES_192`
- `0x180080ef7`: `cipherConfig`
- `0x180080f4b`: `cipherConfig`

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
0x180080eb4  mov     [rsp+arg_8], rdx
0x180080eb9  push    rbx
0x180080eba  sub     rsp, 20h
0x180080ebe  movzx   r9d, byte ptr [r8]
0x180080ec2  mov     edx, r9d
0x180080ec5  sub     edx, 1
0x180080ec8  jz      short loc_180080F44
0x180080eca  sub     edx, 1
0x180080ecd  jz      short loc_180080F3B
0x180080ecf  sub     edx, 1
0x180080ed2  jz      short loc_180080F32
0x180080ed4  sub     edx, 1
0x180080ed7  jz      short loc_180080F29
0x180080ed9  sub     edx, 1
0x180080edc  jz      short loc_180080F20
0x180080ede  sub     edx, 1
0x180080ee1  jz      short loc_180080F17
0x180080ee3  sub     edx, 1
0x180080ee6  jz      short loc_180080F0E
0x180080ee8  cmp     edx, 1
0x180080eeb  jz      short loc_180080F05
0x180080eed  lea     r8, [rsp+28h+arg_8]
0x180080ef2  mov     dword ptr [rsp+28h+arg_8], r9d
0x180080ef7  lea     rdx, aCipherconfig; "cipherConfig"
0x180080efe  call    FwppXmlWrite_UINT32
0x180080f03  jmp     short loc_180080F57
0x180080f05  lea     r8, aIpsecCipherCon_4; "IPSEC_CIPHER_CONFIG_GCM_AES_256"
0x180080f0c  jmp     short loc_180080F4B
0x180080f0e  lea     r8, aIpsecCipherCon_2; "IPSEC_CIPHER_CONFIG_GCM_AES_192"
0x180080f15  jmp     short loc_180080F4B
0x180080f17  lea     r8, aIpsecCipherCon_5; "IPSEC_CIPHER_CONFIG_GCM_AES_128"
0x180080f1e  jmp     short loc_180080F4B
0x180080f20  lea     r8, aIpsecCipherCon_3; "IPSEC_CIPHER_CONFIG_CBC_AES_256"
0x180080f27  jmp     short loc_180080F4B
0x180080f29  lea     r8, aIpsecCipherCon_0; "IPSEC_CIPHER_CONFIG_CBC_AES_192"
0x180080f30  jmp     short loc_180080F4B
0x180080f32  lea     r8, aIpsecCipherCon; "IPSEC_CIPHER_CONFIG_CBC_AES_128"
0x180080f39  jmp     short loc_180080F4B
0x180080f3b  lea     r8, aIpsecCipherCon_6; "IPSEC_CIPHER_CONFIG_CBC_3DES"
0x180080f42  jmp     short loc_180080F4B
0x180080f44  lea     r8, aIpsecCipherCon_1; "IPSEC_CIPHER_CONFIG_CBC_DES"
0x180080f4b  lea     rdx, aCipherconfig; "cipherConfig"
0x180080f52  call    FwppXmlWriteElementUnsafe
0x180080f57  mov     rbx, rax
0x180080f5a  test    rax, rax
0x180080f5d  jz      short loc_180080F6E
0x180080f5f  lea     rdx, aFwppxmlwriteIp_18; "FwppXmlWrite_IPSEC_CIPHER_CONFIG"
0x180080f66  mov     rcx, rax
0x180080f69  call    WfpReportError
0x180080f6e  mov     rax, rbx
0x180080f71  add     rsp, 20h
0x180080f75  pop     rbx
0x180080f76  retn
```
