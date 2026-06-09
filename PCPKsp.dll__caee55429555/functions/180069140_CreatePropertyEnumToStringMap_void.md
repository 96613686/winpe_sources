# CreatePropertyEnumToStringMap(void)

- ea: `0x180069140`
- end: `0x180069f4f`
- name: `?CreatePropertyEnumToStringMap@@YA?BV?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@XZ`
- size: `3599`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180069088`

## callees

- `0x180023868`
- `0x180043780`

## string_xrefs

- `0x180069d4b`: `Security Descr Support`
- `0x180069d6d`: `Security Descr`

## pseudocode

```c
_QWORD *__fastcall CreatePropertyEnumToStringMap(_QWORD *a1)
{
  int v3; // [rsp+28h] [rbp-28h] BYREF
  const wchar_t *v4; // [rsp+30h] [rbp-20h]
  _BYTE v5[24]; // [rsp+38h] [rbp-18h] BYREF

  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_Tree_node<std::pair<unsigned short const * const,enum KspProp>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,enum KspProp>,void *>>>(a1);
  v3 = 1;
  v4 = L"AlgorithmName";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 2;
  v4 = L"BlockLength";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 3;
  v4 = L"ECCPRIVATEBLOB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 4;
  v4 = L"KeyDataBlob";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 5;
  v4 = L"KeyLength";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 6;
  v4 = L"KeyLengths";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 7;
  v4 = L"KeyStrength";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 8;
  v4 = L"OpaqueKeyBlob";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 9;
  v4 = L"PaddingSchemes";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 10;
  v4 = L"PRIVATEBLOB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 11;
  v4 = L"RSAFULLPRIVATEBLOB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 12;
  v4 = L"RSAPRIVATEBLOB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 13;
  v4 = L"SignatureLength";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 14;
  v4 = L"MSSP/UI Internal Flags";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 15;
  v4 = L"MSSP/UI Password Hash";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 16;
  v4 = L"MSSP/UI Password Hash Alg";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 17;
  v4 = L"Algorithm Name";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 18;
  v4 = L"Algorithm Group";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 19;
  v4 = L"Block Length";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 20;
  v4 = L"SmartCardKeyCertificate";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 21;
  v4 = L"KeyCertificateFromTpmNvram";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 22;
  v4 = L"Export Policy";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 23;
  v4 = L"Impl Type";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 24;
  v4 = L"Key Type";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 25;
  v4 = L"Key Usage";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 26;
  v4 = L"Modified";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 27;
  v4 = L"Length";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 28;
  v4 = L"Lengths";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 29;
  v4 = L"Max Name Length";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 30;
  v4 = L"Name";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 31;
  v4 = L"ECCCurveNameList";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 32;
  v4 = L"ECCCurveName";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 33;
  v4 = L"ECCParameters";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 34;
  v4 = L"PCP_AIKSTORE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 35;
  v4 = L"PCP_ALTERNATE_KEY_STORAGE_LOCATION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 36;
  v4 = L"PCP_CHANGEPASSWORD";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 37;
  v4 = L"PCP_ECC_EKNVCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 38;
  v4 = L"PCP_ECC_EKCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 39;
  v4 = L"PCP_ECC_EKPUB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 40;
  v4 = L"PCP_EKSTORE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 41;
  v4 = L"PCP_EKCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 42;
  v4 = L"PCP_EKNVCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 43;
  v4 = L"PCP_EKPUB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 44;
  v4 = L"PCP_EXPORT_ALLOWED";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 45;
  v4 = L"PCP_HMAC_AUTH_NONCE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 46;
  v4 = L"PCP_HMAC_AUTH_POLICYINFO";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 47;
  v4 = L"PCP_HMAC_AUTH_POLICYREF";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 48;
  v4 = L"PCP_HMAC_AUTH_SIGNATURE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 49;
  v4 = L"PCP_HMAC_AUTH_TICKET";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 50;
  v4 = L"PCP_INTERMEDIATE_CA_EKCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 51;
  v4 = L"PCP_KEY_CREATIONHASH";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 52;
  v4 = L"PCP_KEY_CREATIONTICKET";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 53;
  v4 = L"PCP_KEY_USAGE_POLICY";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 54;
  v4 = L"PCP_TPM12_KEYATTESTATION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 55;
  v4 = L"PCP_MIGRATIONPASSWORD";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 56;
  v4 = L"PCP_NO_DA_PROTECTION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 57;
  v4 = L"PCP_PASSWORD_REQUIRED";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 58;
  v4 = L"PCP_PCRTABLE_ALGORITHM";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 59;
  v4 = L"PCP_PCRTABLE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 60;
  v4 = L"PCP_PLATFORM_BINDING_PCRALGID";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 61;
  v4 = L"PCP_PLATFORM_BINDING_PCRDIGEST";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 62;
  v4 = L"PCP_PLATFORM_BINDING_PCRDIGESTLIST";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 63;
  v4 = L"PCP_PLATFORM_BINDING_PCRMASK";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 64;
  v4 = L"PCP_PLATFORM_TYPE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 65;
  v4 = L"PCP_PLATFORMHANDLE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 66;
  v4 = L"PCP_PROVIDERMHANDLE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 67;
  v4 = L"PCP_PROVIDER_VERSION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 68;
  v4 = L"PSS Salt Size";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 69;
  v4 = L"PCP_RAW_POLICYDIGEST";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 70;
  v4 = L"PCP_RSA_EKCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 71;
  v4 = L"PCP_RSA_EKNVCERT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 72;
  v4 = L"PCP_RSA_EKPUB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 73;
  v4 = L"PCP_RSA_SCHEME_HASH_ALG";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 74;
  v4 = L"PCP_RSA_SCHEME";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 75;
  v4 = L"PCP_SESSIONID";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 76;
  v4 = L"PCP_SRKPUB";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 77;
  v4 = L"PCP_STORAGEPARENT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 78;
  v4 = L"PCP_SYMMETRIC_KEYBITS";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 79;
  v4 = L"PCP_TPM12_IDACTIVATION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 80;
  v4 = L"PCP_TPM12_IDBINDING";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 81;
  v4 = L"PCP_TPM2BNAME";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 82;
  v4 = L"PCP_TPM_FW_VERSION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 83;
  v4 = L"PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 84;
  v4 = L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 85;
  v4 = L"PCP_TPM_MANUFACTURER_ID";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 86;
  v4 = L"PCP_TPM_VERSION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 87;
  v4 = L"PCP_USAGEAUTH";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 88;
  v4 = L"SmartCardPin";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 89;
  v4 = L"Provider Handle";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 90;
  v4 = L"Security Descr Support";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 91;
  v4 = L"Security Descr";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 92;
  v4 = L"UI Policy";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 93;
  v4 = L"Unique Name";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 94;
  v4 = L"Use Context";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 95;
  v4 = L"SmartCardUserCertStore";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 96;
  v4 = L"Version";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 97;
  v4 = L"HWND Handle";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 98;
  v4 = L"PCP_INVALIDATE_HANDLE";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 99;
  v4 = L"PCP_KEY_USAGE_POLICY";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 100;
  v4 = L"PCP_PASSWORD";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 101;
  v4 = L"PCP_PLATFORM_CLAIM";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 102;
  v4 = L"PCP_TPM12_IDCERTIFICATION";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 103;
  v4 = L"PCP_TPM12_SETIDBINDING";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  v3 = 104;
  v4 = L"PCP_SDDIDK_CONTEXT";
  std::map<enum KspProp,unsigned short const *>::insert<std::pair<enum KspProp,unsigned short const *>,0>(a1, v5, &v3);
  return a1;
}

```

## disassembly

```asm
0x180069140  mov     [rsp-8+arg_8], rbx
0x180069145  mov     [rsp-8+arg_10], rdi
0x18006914a  mov     [rsp-8+arg_0], rcx
0x18006914f  push    rbp
0x180069150  mov     rbp, rsp
0x180069153  sub     rsp, 50h
0x180069157  mov     rbx, rcx
0x18006915a  xor     eax, eax
0x18006915c  mov     [rbp+var_30], eax
0x18006915f  mov     [rcx], rax
0x180069162  mov     [rcx+8], rax
0x180069166  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@QEBGW4KspProp@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@QEBGW4KspProp@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@QEBGW4KspProp@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<ushort const * const,KspProp>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<ushort const * const,KspProp>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,KspProp>,void *>> &)
0x18006916b  mov     [rbx], rax
0x18006916e  mov     eax, 1
0x180069173  mov     [rbp+var_30], eax
0x180069176  mov     [rbp+var_28], eax
0x180069179  lea     rax, aAlgorithmname; "AlgorithmName"
0x180069180  mov     [rbp+var_20], rax
0x180069184  lea     r8, [rbp+var_28]
0x180069188  lea     rdx, [rbp+var_18]
0x18006918c  mov     rcx, rbx
0x18006918f  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069194  mov     [rbp+var_28], 2
0x18006919b  lea     rax, aBlocklength; "BlockLength"
0x1800691a2  mov     [rbp+var_20], rax
0x1800691a6  lea     r8, [rbp+var_28]
0x1800691aa  lea     rdx, [rbp+var_18]
0x1800691ae  mov     rcx, rbx
0x1800691b1  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800691b6  mov     [rbp+var_28], 3
0x1800691bd  lea     rax, aEccprivateblob; "ECCPRIVATEBLOB"
0x1800691c4  mov     [rbp+var_20], rax
0x1800691c8  lea     r8, [rbp+var_28]
0x1800691cc  lea     rdx, [rbp+var_18]
0x1800691d0  mov     rcx, rbx
0x1800691d3  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800691d8  mov     [rbp+var_28], 4
0x1800691df  lea     rax, aKeydatablob; "KeyDataBlob"
0x1800691e6  mov     [rbp+var_20], rax
0x1800691ea  lea     r8, [rbp+var_28]
0x1800691ee  lea     rdx, [rbp+var_18]
0x1800691f2  mov     rcx, rbx
0x1800691f5  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800691fa  mov     [rbp+var_28], 5
0x180069201  lea     rax, aKeylength; "KeyLength"
0x180069208  mov     [rbp+var_20], rax
0x18006920c  lea     r8, [rbp+var_28]
0x180069210  lea     rdx, [rbp+var_18]
0x180069214  mov     rcx, rbx
0x180069217  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006921c  mov     [rbp+var_28], 6
0x180069223  lea     rax, aKeylengths; "KeyLengths"
0x18006922a  mov     [rbp+var_20], rax
0x18006922e  lea     r8, [rbp+var_28]
0x180069232  lea     rdx, [rbp+var_18]
0x180069236  mov     rcx, rbx
0x180069239  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006923e  mov     [rbp+var_28], 7
0x180069245  lea     rax, aKeystrength; "KeyStrength"
0x18006924c  mov     [rbp+var_20], rax
0x180069250  lea     r8, [rbp+var_28]
0x180069254  lea     rdx, [rbp+var_18]
0x180069258  mov     rcx, rbx
0x18006925b  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069260  mov     [rbp+var_28], 8
0x180069267  lea     rax, aOpaquekeyblob; "OpaqueKeyBlob"
0x18006926e  mov     [rbp+var_20], rax
0x180069272  lea     r8, [rbp+var_28]
0x180069276  lea     rdx, [rbp+var_18]
0x18006927a  mov     rcx, rbx
0x18006927d  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069282  mov     [rbp+var_28], 9
0x180069289  lea     rax, aPaddingschemes; "PaddingSchemes"
0x180069290  mov     [rbp+var_20], rax
0x180069294  lea     r8, [rbp+var_28]
0x180069298  lea     rdx, [rbp+var_18]
0x18006929c  mov     rcx, rbx
0x18006929f  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800692a4  mov     [rbp+var_28], 0Ah
0x1800692ab  lea     rax, aPrivateblob; "PRIVATEBLOB"
0x1800692b2  mov     [rbp+var_20], rax
0x1800692b6  lea     r8, [rbp+var_28]
0x1800692ba  lea     rdx, [rbp+var_18]
0x1800692be  mov     rcx, rbx
0x1800692c1  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800692c6  mov     [rbp+var_28], 0Bh
0x1800692cd  lea     rax, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x1800692d4  mov     [rbp+var_20], rax
0x1800692d8  lea     r8, [rbp+var_28]
0x1800692dc  lea     rdx, [rbp+var_18]
0x1800692e0  mov     rcx, rbx
0x1800692e3  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800692e8  mov     [rbp+var_28], 0Ch
0x1800692ef  lea     rax, aRsaprivateblob; "RSAPRIVATEBLOB"
0x1800692f6  mov     [rbp+var_20], rax
0x1800692fa  lea     r8, [rbp+var_28]
0x1800692fe  lea     rdx, [rbp+var_18]
0x180069302  mov     rcx, rbx
0x180069305  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006930a  mov     [rbp+var_28], 0Dh
0x180069311  lea     rax, aSignaturelengt; "SignatureLength"
0x180069318  mov     [rbp+var_20], rax
0x18006931c  lea     r8, [rbp+var_28]
0x180069320  lea     rdx, [rbp+var_18]
0x180069324  mov     rcx, rbx
0x180069327  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006932c  mov     [rbp+var_28], 0Eh
0x180069333  lea     rax, aMsspUiInternal; "MSSP/UI Internal Flags"
0x18006933a  mov     [rbp+var_20], rax
0x18006933e  lea     r8, [rbp+var_28]
0x180069342  lea     rdx, [rbp+var_18]
0x180069346  mov     rcx, rbx
0x180069349  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006934e  mov     [rbp+var_28], 0Fh
0x180069355  lea     rax, aMsspUiPassword; "MSSP/UI Password Hash"
0x18006935c  mov     [rbp+var_20], rax
0x180069360  lea     r8, [rbp+var_28]
0x180069364  lea     rdx, [rbp+var_18]
0x180069368  mov     rcx, rbx
0x18006936b  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069370  mov     [rbp+var_28], 10h
0x180069377  lea     rax, aMsspUiPassword_0; "MSSP/UI Password Hash Alg"
0x18006937e  mov     [rbp+var_20], rax
0x180069382  lea     r8, [rbp+var_28]
0x180069386  lea     rdx, [rbp+var_18]
0x18006938a  mov     rcx, rbx
0x18006938d  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069392  mov     [rbp+var_28], 11h
0x180069399  lea     rax, aAlgorithmName; "Algorithm Name"
0x1800693a0  mov     [rbp+var_20], rax
0x1800693a4  lea     r8, [rbp+var_28]
0x1800693a8  lea     rdx, [rbp+var_18]
0x1800693ac  mov     rcx, rbx
0x1800693af  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800693b4  mov     [rbp+var_28], 12h
0x1800693bb  lea     rax, aAlgorithmGroup; "Algorithm Group"
0x1800693c2  mov     [rbp+var_20], rax
0x1800693c6  lea     r8, [rbp+var_28]
0x1800693ca  lea     rdx, [rbp+var_18]
0x1800693ce  mov     rcx, rbx
0x1800693d1  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800693d6  mov     [rbp+var_28], 13h
0x1800693dd  lea     rax, aBlockLength; "Block Length"
0x1800693e4  mov     [rbp+var_20], rax
0x1800693e8  lea     r8, [rbp+var_28]
0x1800693ec  lea     rdx, [rbp+var_18]
0x1800693f0  mov     rcx, rbx
0x1800693f3  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800693f8  mov     [rbp+var_28], 14h
0x1800693ff  lea     rax, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180069406  mov     [rbp+var_20], rax
0x18006940a  lea     r8, [rbp+var_28]
0x18006940e  lea     rdx, [rbp+var_18]
0x180069412  mov     rcx, rbx
0x180069415  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006941a  mov     [rbp+var_28], 15h
0x180069421  lea     rax, aKeycertificate; "KeyCertificateFromTpmNvram"
0x180069428  mov     [rbp+var_20], rax
0x18006942c  lea     r8, [rbp+var_28]
0x180069430  lea     rdx, [rbp+var_18]
0x180069434  mov     rcx, rbx
0x180069437  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006943c  mov     [rbp+var_28], 16h
0x180069443  lea     rax, aExportPolicy; "Export Policy"
0x18006944a  mov     [rbp+var_20], rax
0x18006944e  lea     r8, [rbp+var_28]
0x180069452  lea     rdx, [rbp+var_18]
0x180069456  mov     rcx, rbx
0x180069459  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006945e  mov     [rbp+var_28], 17h
0x180069465  lea     rax, aImplType; "Impl Type"
0x18006946c  mov     [rbp+var_20], rax
0x180069470  lea     r8, [rbp+var_28]
0x180069474  lea     rdx, [rbp+var_18]
0x180069478  mov     rcx, rbx
0x18006947b  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069480  mov     [rbp+var_28], 18h
0x180069487  lea     rax, aKeyType; "Key Type"
0x18006948e  mov     [rbp+var_20], rax
0x180069492  lea     r8, [rbp+var_28]
0x180069496  lea     rdx, [rbp+var_18]
0x18006949a  mov     rcx, rbx
0x18006949d  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800694a2  mov     [rbp+var_28], 19h
0x1800694a9  lea     rax, aKeyUsage; "Key Usage"
0x1800694b0  mov     [rbp+var_20], rax
0x1800694b4  lea     r8, [rbp+var_28]
0x1800694b8  lea     rdx, [rbp+var_18]
0x1800694bc  mov     rcx, rbx
0x1800694bf  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800694c4  mov     [rbp+var_28], 1Ah
0x1800694cb  lea     rax, aModified; "Modified"
0x1800694d2  mov     [rbp+var_20], rax
0x1800694d6  lea     r8, [rbp+var_28]
0x1800694da  lea     rdx, [rbp+var_18]
0x1800694de  mov     rcx, rbx
0x1800694e1  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800694e6  mov     [rbp+var_28], 1Bh
0x1800694ed  lea     rax, aLength; "Length"
0x1800694f4  mov     [rbp+var_20], rax
0x1800694f8  lea     r8, [rbp+var_28]
0x1800694fc  lea     rdx, [rbp+var_18]
0x180069500  mov     rcx, rbx
0x180069503  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069508  mov     [rbp+var_28], 1Ch
0x18006950f  lea     rax, aLengths; "Lengths"
0x180069516  mov     [rbp+var_20], rax
0x18006951a  lea     r8, [rbp+var_28]
0x18006951e  lea     rdx, [rbp+var_18]
0x180069522  mov     rcx, rbx
0x180069525  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006952a  mov     [rbp+var_28], 1Dh
0x180069531  lea     rax, aMaxNameLength; "Max Name Length"
0x180069538  mov     [rbp+var_20], rax
0x18006953c  lea     r8, [rbp+var_28]
0x180069540  lea     rdx, [rbp+var_18]
0x180069544  mov     rcx, rbx
0x180069547  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006954c  mov     [rbp+var_28], 1Eh
0x180069553  lea     rax, aName; "Name"
0x18006955a  mov     [rbp+var_20], rax
0x18006955e  lea     r8, [rbp+var_28]
0x180069562  lea     rdx, [rbp+var_18]
0x180069566  mov     rcx, rbx
0x180069569  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006956e  mov     [rbp+var_28], 1Fh
0x180069575  lea     rax, aEcccurvenameli; "ECCCurveNameList"
0x18006957c  mov     [rbp+var_20], rax
0x180069580  lea     r8, [rbp+var_28]
0x180069584  lea     rdx, [rbp+var_18]
0x180069588  mov     rcx, rbx
0x18006958b  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069590  mov     [rbp+var_28], 20h ; ' '
0x180069597  lea     rax, aEcccurvename; "ECCCurveName"
0x18006959e  mov     [rbp+var_20], rax
0x1800695a2  lea     r8, [rbp+var_28]
0x1800695a6  lea     rdx, [rbp+var_18]
0x1800695aa  mov     rcx, rbx
0x1800695ad  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800695b2  mov     [rbp+var_28], 21h ; '!'
0x1800695b9  lea     rax, aEccparameters; "ECCParameters"
0x1800695c0  mov     [rbp+var_20], rax
0x1800695c4  lea     r8, [rbp+var_28]
0x1800695c8  lea     rdx, [rbp+var_18]
0x1800695cc  mov     rcx, rbx
0x1800695cf  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800695d4  mov     [rbp+var_28], 22h ; '"'
0x1800695db  lea     rax, aPcpAikstore; "PCP_AIKSTORE"
0x1800695e2  mov     [rbp+var_20], rax
0x1800695e6  lea     r8, [rbp+var_28]
0x1800695ea  lea     rdx, [rbp+var_18]
0x1800695ee  mov     rcx, rbx
0x1800695f1  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800695f6  mov     [rbp+var_28], 23h ; '#'
0x1800695fd  lea     rax, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180069604  mov     [rbp+var_20], rax
0x180069608  lea     r8, [rbp+var_28]
0x18006960c  lea     rdx, [rbp+var_18]
0x180069610  mov     rcx, rbx
0x180069613  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x180069618  mov     [rbp+var_28], 24h ; '$'
0x18006961f  lea     rax, aPcpChangepassw; "PCP_CHANGEPASSWORD"
0x180069626  mov     [rbp+var_20], rax
0x18006962a  lea     r8, [rbp+var_28]
0x18006962e  lea     rdx, [rbp+var_18]
0x180069632  mov     rcx, rbx
0x180069635  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006963a  mov     [rbp+var_28], 25h ; '%'
0x180069641  lea     rax, aPcpEccEknvcert; "PCP_ECC_EKNVCERT"
0x180069648  mov     [rbp+var_20], rax
0x18006964c  lea     r8, [rbp+var_28]
0x180069650  lea     rdx, [rbp+var_18]
0x180069654  mov     rcx, rbx
0x180069657  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006965c  mov     [rbp+var_28], 26h ; '&'
0x180069663  lea     rax, aPcpEccEkcert; "PCP_ECC_EKCERT"
0x18006966a  mov     [rbp+var_20], rax
0x18006966e  lea     r8, [rbp+var_28]
0x180069672  lea     rdx, [rbp+var_18]
0x180069676  mov     rcx, rbx
0x180069679  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x18006967e  mov     [rbp+var_28], 27h ; '''
0x180069685  lea     rax, aPcpEccEkpub; "PCP_ECC_EKPUB"
0x18006968c  mov     [rbp+var_20], rax
0x180069690  lea     r8, [rbp+var_28]
0x180069694  lea     rdx, [rbp+var_18]
0x180069698  mov     rcx, rbx
0x18006969b  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800696a0  mov     [rbp+var_28], 28h ; '('
0x1800696a7  lea     rax, aPcpEkstore; "PCP_EKSTORE"
0x1800696ae  mov     [rbp+var_20], rax
0x1800696b2  lea     r8, [rbp+var_28]
0x1800696b6  lea     rdx, [rbp+var_18]
0x1800696ba  mov     rcx, rbx
0x1800696bd  call    ??$insert@U?$pair@W4KspProp@@PEBG@std@@$0A@@?$map@W4KspProp@@PEBGU?$less@W4KspProp@@@std@@V?$allocator@U?$pair@$$CBW4KspProp@@PEBG@std@@@3@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4KspProp@@PEBG@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4KspProp@@PEBG@1@@Z; std::map<KspProp,ushort const *>::insert<std::pair<KspProp,ushort const *>,0>(std::pair<KspProp,ushort const *> &&)
0x1800696c2  mov     [rbp+var_28], 29h ; ')'
0x1800696c9  lea     rax, aPcpEkcert; "PCP_EKCERT"
0x1800696d0  mov     [rbp+var_20], rax
0x1800696d4  lea     r8, [rbp+var_28]
0x1800696d8  lea     rdx, [rbp+var_18]
  ... truncated ...
```
