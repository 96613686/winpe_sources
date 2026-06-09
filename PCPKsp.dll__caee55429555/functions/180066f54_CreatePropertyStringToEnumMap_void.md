# CreatePropertyStringToEnumMap(void)

- ea: `0x180066f54`
- end: `0x180067d63`
- name: `?CreatePropertyStringToEnumMap@@YA?BV?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@XZ`
- size: `3599`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066e9c`

## callees

- `0x180022ea8`
- `0x180023868`

## string_xrefs

- `0x180067b58`: `Security Descr Support`
- `0x180067b7a`: `Security Descr`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CreatePropertyStringToEnumMap(_QWORD *a1)
{
  const wchar_t *v3; // [rsp+28h] [rbp-28h] BYREF
  int v4; // [rsp+30h] [rbp-20h]
  _BYTE v5[24]; // [rsp+38h] [rbp-18h] BYREF

  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_Tree_node<std::pair<unsigned short const * const,enum KspProp>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,enum KspProp>,void *>>>(a1);
  v3 = L"AlgorithmName";
  v4 = 1;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"BlockLength";
  v4 = 2;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"ECCPRIVATEBLOB";
  v4 = 3;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"KeyDataBlob";
  v4 = 4;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"KeyLength";
  v4 = 5;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"KeyLengths";
  v4 = 6;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"KeyStrength";
  v4 = 7;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"OpaqueKeyBlob";
  v4 = 8;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PaddingSchemes";
  v4 = 9;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PRIVATEBLOB";
  v4 = 10;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"RSAFULLPRIVATEBLOB";
  v4 = 11;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"RSAPRIVATEBLOB";
  v4 = 12;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"SignatureLength";
  v4 = 13;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"MSSP/UI Internal Flags";
  v4 = 14;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"MSSP/UI Password Hash";
  v4 = 15;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"MSSP/UI Password Hash Alg";
  v4 = 16;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Algorithm Name";
  v4 = 17;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Algorithm Group";
  v4 = 18;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Block Length";
  v4 = 19;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"SmartCardKeyCertificate";
  v4 = 20;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"KeyCertificateFromTpmNvram";
  v4 = 21;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Export Policy";
  v4 = 22;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Impl Type";
  v4 = 23;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Key Type";
  v4 = 24;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Key Usage";
  v4 = 25;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Modified";
  v4 = 26;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Length";
  v4 = 27;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Lengths";
  v4 = 28;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Max Name Length";
  v4 = 29;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Name";
  v4 = 30;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"ECCCurveNameList";
  v4 = 31;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"ECCCurveName";
  v4 = 32;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"ECCParameters";
  v4 = 33;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_AIKSTORE";
  v4 = 34;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_ALTERNATE_KEY_STORAGE_LOCATION";
  v4 = 35;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_CHANGEPASSWORD";
  v4 = 36;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_ECC_EKNVCERT";
  v4 = 37;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_ECC_EKCERT";
  v4 = 38;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_ECC_EKPUB";
  v4 = 39;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_EKSTORE";
  v4 = 40;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_EKCERT";
  v4 = 41;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_EKNVCERT";
  v4 = 42;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_EKPUB";
  v4 = 43;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_EXPORT_ALLOWED";
  v4 = 44;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_HMAC_AUTH_NONCE";
  v4 = 45;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_HMAC_AUTH_POLICYINFO";
  v4 = 46;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_HMAC_AUTH_POLICYREF";
  v4 = 47;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_HMAC_AUTH_SIGNATURE";
  v4 = 48;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_HMAC_AUTH_TICKET";
  v4 = 49;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_INTERMEDIATE_CA_EKCERT";
  v4 = 50;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_KEY_CREATIONHASH";
  v4 = 51;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_KEY_CREATIONTICKET";
  v4 = 52;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_KEY_USAGE_POLICY";
  v4 = 53;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM12_KEYATTESTATION";
  v4 = 54;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_MIGRATIONPASSWORD";
  v4 = 55;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_NO_DA_PROTECTION";
  v4 = 56;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PASSWORD_REQUIRED";
  v4 = 57;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PCRTABLE_ALGORITHM";
  v4 = 58;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PCRTABLE";
  v4 = 59;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORM_BINDING_PCRALGID";
  v4 = 60;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORM_BINDING_PCRDIGEST";
  v4 = 61;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORM_BINDING_PCRDIGESTLIST";
  v4 = 62;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORM_BINDING_PCRMASK";
  v4 = 63;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORM_TYPE";
  v4 = 64;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORMHANDLE";
  v4 = 65;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PROVIDERMHANDLE";
  v4 = 66;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PROVIDER_VERSION";
  v4 = 67;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PSS Salt Size";
  v4 = 68;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_RAW_POLICYDIGEST";
  v4 = 69;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_RSA_EKCERT";
  v4 = 70;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_RSA_EKNVCERT";
  v4 = 71;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_RSA_EKPUB";
  v4 = 72;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_RSA_SCHEME_HASH_ALG";
  v4 = 73;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_RSA_SCHEME";
  v4 = 74;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_SESSIONID";
  v4 = 75;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_SRKPUB";
  v4 = 76;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_STORAGEPARENT";
  v4 = 77;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_SYMMETRIC_KEYBITS";
  v4 = 78;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM12_IDACTIVATION";
  v4 = 79;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM12_IDBINDING";
  v4 = 80;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM2BNAME";
  v4 = 81;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM_FW_VERSION";
  v4 = 82;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED";
  v4 = 83;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY";
  v4 = 84;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM_MANUFACTURER_ID";
  v4 = 85;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM_VERSION";
  v4 = 86;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_USAGEAUTH";
  v4 = 87;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"SmartCardPin";
  v4 = 88;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Provider Handle";
  v4 = 89;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Security Descr Support";
  v4 = 90;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Security Descr";
  v4 = 91;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"UI Policy";
  v4 = 92;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Unique Name";
  v4 = 93;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Use Context";
  v4 = 94;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"SmartCardUserCertStore";
  v4 = 95;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"Version";
  v4 = 96;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"HWND Handle";
  v4 = 97;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_INVALIDATE_HANDLE";
  v4 = 98;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_KEY_USAGE_POLICY";
  v4 = 99;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PASSWORD";
  v4 = 100;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_PLATFORM_CLAIM";
  v4 = 101;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM12_IDCERTIFICATION";
  v4 = 102;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_TPM12_SETIDBINDING";
  v4 = 103;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  v3 = L"PCP_SDDIDK_CONTEXT";
  v4 = 104;
  std::map<unsigned short const *,enum KspProp,PropertyIdentifierCompare,std::allocator<std::pair<unsigned short const * const,enum KspProp>>>::insert<std::pair<unsigned short const *,enum KspProp>,0>(
    a1,
    v5,
    &v3);
  return a1;
}

```

## disassembly

```asm
0x180066f54  mov     [rsp-8+arg_8], rbx
0x180066f59  mov     [rsp-8+arg_10], rdi
0x180066f5e  mov     [rsp-8+arg_0], rcx
0x180066f63  push    rbp
0x180066f64  mov     rbp, rsp
0x180066f67  sub     rsp, 50h
0x180066f6b  mov     rbx, rcx
0x180066f6e  xor     eax, eax
0x180066f70  mov     [rbp+var_30], eax
0x180066f73  mov     [rcx], rax
0x180066f76  mov     [rcx+8], rax
0x180066f7a  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@QEBGW4KspProp@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@QEBGW4KspProp@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@QEBGW4KspProp@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<ushort const * const,KspProp>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<ushort const * const,KspProp>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,KspProp>,void *>> &)
0x180066f7f  mov     [rbx], rax
0x180066f82  mov     ecx, 1
0x180066f87  mov     [rbp+var_30], ecx
0x180066f8a  lea     rax, aAlgorithmname; "AlgorithmName"
0x180066f91  mov     [rbp+var_28], rax
0x180066f95  mov     [rbp+var_20], ecx
0x180066f98  lea     r8, [rbp+var_28]
0x180066f9c  lea     rdx, [rbp+var_18]
0x180066fa0  mov     rcx, rbx
0x180066fa3  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180066fa8  lea     rax, aBlocklength; "BlockLength"
0x180066faf  mov     [rbp+var_28], rax
0x180066fb3  mov     [rbp+var_20], 2
0x180066fba  lea     r8, [rbp+var_28]
0x180066fbe  lea     rdx, [rbp+var_18]
0x180066fc2  mov     rcx, rbx
0x180066fc5  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180066fca  lea     rax, aEccprivateblob; "ECCPRIVATEBLOB"
0x180066fd1  mov     [rbp+var_28], rax
0x180066fd5  mov     [rbp+var_20], 3
0x180066fdc  lea     r8, [rbp+var_28]
0x180066fe0  lea     rdx, [rbp+var_18]
0x180066fe4  mov     rcx, rbx
0x180066fe7  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180066fec  lea     rax, aKeydatablob; "KeyDataBlob"
0x180066ff3  mov     [rbp+var_28], rax
0x180066ff7  mov     [rbp+var_20], 4
0x180066ffe  lea     r8, [rbp+var_28]
0x180067002  lea     rdx, [rbp+var_18]
0x180067006  mov     rcx, rbx
0x180067009  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006700e  lea     rax, aKeylength; "KeyLength"
0x180067015  mov     [rbp+var_28], rax
0x180067019  mov     [rbp+var_20], 5
0x180067020  lea     r8, [rbp+var_28]
0x180067024  lea     rdx, [rbp+var_18]
0x180067028  mov     rcx, rbx
0x18006702b  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067030  lea     rax, aKeylengths; "KeyLengths"
0x180067037  mov     [rbp+var_28], rax
0x18006703b  mov     [rbp+var_20], 6
0x180067042  lea     r8, [rbp+var_28]
0x180067046  lea     rdx, [rbp+var_18]
0x18006704a  mov     rcx, rbx
0x18006704d  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067052  lea     rax, aKeystrength; "KeyStrength"
0x180067059  mov     [rbp+var_28], rax
0x18006705d  mov     [rbp+var_20], 7
0x180067064  lea     r8, [rbp+var_28]
0x180067068  lea     rdx, [rbp+var_18]
0x18006706c  mov     rcx, rbx
0x18006706f  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067074  lea     rax, aOpaquekeyblob; "OpaqueKeyBlob"
0x18006707b  mov     [rbp+var_28], rax
0x18006707f  mov     [rbp+var_20], 8
0x180067086  lea     r8, [rbp+var_28]
0x18006708a  lea     rdx, [rbp+var_18]
0x18006708e  mov     rcx, rbx
0x180067091  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067096  lea     rax, aPaddingschemes; "PaddingSchemes"
0x18006709d  mov     [rbp+var_28], rax
0x1800670a1  mov     [rbp+var_20], 9
0x1800670a8  lea     r8, [rbp+var_28]
0x1800670ac  lea     rdx, [rbp+var_18]
0x1800670b0  mov     rcx, rbx
0x1800670b3  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800670b8  lea     rax, aPrivateblob; "PRIVATEBLOB"
0x1800670bf  mov     [rbp+var_28], rax
0x1800670c3  mov     [rbp+var_20], 0Ah
0x1800670ca  lea     r8, [rbp+var_28]
0x1800670ce  lea     rdx, [rbp+var_18]
0x1800670d2  mov     rcx, rbx
0x1800670d5  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800670da  lea     rax, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x1800670e1  mov     [rbp+var_28], rax
0x1800670e5  mov     [rbp+var_20], 0Bh
0x1800670ec  lea     r8, [rbp+var_28]
0x1800670f0  lea     rdx, [rbp+var_18]
0x1800670f4  mov     rcx, rbx
0x1800670f7  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800670fc  lea     rax, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180067103  mov     [rbp+var_28], rax
0x180067107  mov     [rbp+var_20], 0Ch
0x18006710e  lea     r8, [rbp+var_28]
0x180067112  lea     rdx, [rbp+var_18]
0x180067116  mov     rcx, rbx
0x180067119  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006711e  lea     rax, aSignaturelengt; "SignatureLength"
0x180067125  mov     [rbp+var_28], rax
0x180067129  mov     [rbp+var_20], 0Dh
0x180067130  lea     r8, [rbp+var_28]
0x180067134  lea     rdx, [rbp+var_18]
0x180067138  mov     rcx, rbx
0x18006713b  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067140  lea     rax, aMsspUiInternal; "MSSP/UI Internal Flags"
0x180067147  mov     [rbp+var_28], rax
0x18006714b  mov     [rbp+var_20], 0Eh
0x180067152  lea     r8, [rbp+var_28]
0x180067156  lea     rdx, [rbp+var_18]
0x18006715a  mov     rcx, rbx
0x18006715d  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067162  lea     rax, aMsspUiPassword; "MSSP/UI Password Hash"
0x180067169  mov     [rbp+var_28], rax
0x18006716d  mov     [rbp+var_20], 0Fh
0x180067174  lea     r8, [rbp+var_28]
0x180067178  lea     rdx, [rbp+var_18]
0x18006717c  mov     rcx, rbx
0x18006717f  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067184  lea     rax, aMsspUiPassword_0; "MSSP/UI Password Hash Alg"
0x18006718b  mov     [rbp+var_28], rax
0x18006718f  mov     [rbp+var_20], 10h
0x180067196  lea     r8, [rbp+var_28]
0x18006719a  lea     rdx, [rbp+var_18]
0x18006719e  mov     rcx, rbx
0x1800671a1  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800671a6  lea     rax, aAlgorithmName; "Algorithm Name"
0x1800671ad  mov     [rbp+var_28], rax
0x1800671b1  mov     [rbp+var_20], 11h
0x1800671b8  lea     r8, [rbp+var_28]
0x1800671bc  lea     rdx, [rbp+var_18]
0x1800671c0  mov     rcx, rbx
0x1800671c3  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800671c8  lea     rax, aAlgorithmGroup; "Algorithm Group"
0x1800671cf  mov     [rbp+var_28], rax
0x1800671d3  mov     [rbp+var_20], 12h
0x1800671da  lea     r8, [rbp+var_28]
0x1800671de  lea     rdx, [rbp+var_18]
0x1800671e2  mov     rcx, rbx
0x1800671e5  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800671ea  lea     rax, aBlockLength; "Block Length"
0x1800671f1  mov     [rbp+var_28], rax
0x1800671f5  mov     [rbp+var_20], 13h
0x1800671fc  lea     r8, [rbp+var_28]
0x180067200  lea     rdx, [rbp+var_18]
0x180067204  mov     rcx, rbx
0x180067207  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006720c  lea     rax, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180067213  mov     [rbp+var_28], rax
0x180067217  mov     [rbp+var_20], 14h
0x18006721e  lea     r8, [rbp+var_28]
0x180067222  lea     rdx, [rbp+var_18]
0x180067226  mov     rcx, rbx
0x180067229  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006722e  lea     rax, aKeycertificate; "KeyCertificateFromTpmNvram"
0x180067235  mov     [rbp+var_28], rax
0x180067239  mov     [rbp+var_20], 15h
0x180067240  lea     r8, [rbp+var_28]
0x180067244  lea     rdx, [rbp+var_18]
0x180067248  mov     rcx, rbx
0x18006724b  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067250  lea     rax, aExportPolicy; "Export Policy"
0x180067257  mov     [rbp+var_28], rax
0x18006725b  mov     [rbp+var_20], 16h
0x180067262  lea     r8, [rbp+var_28]
0x180067266  lea     rdx, [rbp+var_18]
0x18006726a  mov     rcx, rbx
0x18006726d  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067272  lea     rax, aImplType; "Impl Type"
0x180067279  mov     [rbp+var_28], rax
0x18006727d  mov     [rbp+var_20], 17h
0x180067284  lea     r8, [rbp+var_28]
0x180067288  lea     rdx, [rbp+var_18]
0x18006728c  mov     rcx, rbx
0x18006728f  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067294  lea     rax, aKeyType; "Key Type"
0x18006729b  mov     [rbp+var_28], rax
0x18006729f  mov     [rbp+var_20], 18h
0x1800672a6  lea     r8, [rbp+var_28]
0x1800672aa  lea     rdx, [rbp+var_18]
0x1800672ae  mov     rcx, rbx
0x1800672b1  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800672b6  lea     rax, aKeyUsage; "Key Usage"
0x1800672bd  mov     [rbp+var_28], rax
0x1800672c1  mov     [rbp+var_20], 19h
0x1800672c8  lea     r8, [rbp+var_28]
0x1800672cc  lea     rdx, [rbp+var_18]
0x1800672d0  mov     rcx, rbx
0x1800672d3  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800672d8  lea     rax, aModified; "Modified"
0x1800672df  mov     [rbp+var_28], rax
0x1800672e3  mov     [rbp+var_20], 1Ah
0x1800672ea  lea     r8, [rbp+var_28]
0x1800672ee  lea     rdx, [rbp+var_18]
0x1800672f2  mov     rcx, rbx
0x1800672f5  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800672fa  lea     rax, aLength; "Length"
0x180067301  mov     [rbp+var_28], rax
0x180067305  mov     [rbp+var_20], 1Bh
0x18006730c  lea     r8, [rbp+var_28]
0x180067310  lea     rdx, [rbp+var_18]
0x180067314  mov     rcx, rbx
0x180067317  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006731c  lea     rax, aLengths; "Lengths"
0x180067323  mov     [rbp+var_28], rax
0x180067327  mov     [rbp+var_20], 1Ch
0x18006732e  lea     r8, [rbp+var_28]
0x180067332  lea     rdx, [rbp+var_18]
0x180067336  mov     rcx, rbx
0x180067339  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006733e  lea     rax, aMaxNameLength; "Max Name Length"
0x180067345  mov     [rbp+var_28], rax
0x180067349  mov     [rbp+var_20], 1Dh
0x180067350  lea     r8, [rbp+var_28]
0x180067354  lea     rdx, [rbp+var_18]
0x180067358  mov     rcx, rbx
0x18006735b  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067360  lea     rax, aName; "Name"
0x180067367  mov     [rbp+var_28], rax
0x18006736b  mov     [rbp+var_20], 1Eh
0x180067372  lea     r8, [rbp+var_28]
0x180067376  lea     rdx, [rbp+var_18]
0x18006737a  mov     rcx, rbx
0x18006737d  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067382  lea     rax, aEcccurvenameli; "ECCCurveNameList"
0x180067389  mov     [rbp+var_28], rax
0x18006738d  mov     [rbp+var_20], 1Fh
0x180067394  lea     r8, [rbp+var_28]
0x180067398  lea     rdx, [rbp+var_18]
0x18006739c  mov     rcx, rbx
0x18006739f  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800673a4  lea     rax, aEcccurvename; "ECCCurveName"
0x1800673ab  mov     [rbp+var_28], rax
0x1800673af  mov     [rbp+var_20], 20h ; ' '
0x1800673b6  lea     r8, [rbp+var_28]
0x1800673ba  lea     rdx, [rbp+var_18]
0x1800673be  mov     rcx, rbx
0x1800673c1  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800673c6  lea     rax, aEccparameters; "ECCParameters"
0x1800673cd  mov     [rbp+var_28], rax
0x1800673d1  mov     [rbp+var_20], 21h ; '!'
0x1800673d8  lea     r8, [rbp+var_28]
0x1800673dc  lea     rdx, [rbp+var_18]
0x1800673e0  mov     rcx, rbx
0x1800673e3  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800673e8  lea     rax, aPcpAikstore; "PCP_AIKSTORE"
0x1800673ef  mov     [rbp+var_28], rax
0x1800673f3  mov     [rbp+var_20], 22h ; '"'
0x1800673fa  lea     r8, [rbp+var_28]
0x1800673fe  lea     rdx, [rbp+var_18]
0x180067402  mov     rcx, rbx
0x180067405  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006740a  lea     rax, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180067411  mov     [rbp+var_28], rax
0x180067415  mov     [rbp+var_20], 23h ; '#'
0x18006741c  lea     r8, [rbp+var_28]
0x180067420  lea     rdx, [rbp+var_18]
0x180067424  mov     rcx, rbx
0x180067427  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006742c  lea     rax, aPcpChangepassw; "PCP_CHANGEPASSWORD"
0x180067433  mov     [rbp+var_28], rax
0x180067437  mov     [rbp+var_20], 24h ; '$'
0x18006743e  lea     r8, [rbp+var_28]
0x180067442  lea     rdx, [rbp+var_18]
0x180067446  mov     rcx, rbx
0x180067449  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x18006744e  lea     rax, aPcpEccEknvcert; "PCP_ECC_EKNVCERT"
0x180067455  mov     [rbp+var_28], rax
0x180067459  mov     [rbp+var_20], 25h ; '%'
0x180067460  lea     r8, [rbp+var_28]
0x180067464  lea     rdx, [rbp+var_18]
0x180067468  mov     rcx, rbx
0x18006746b  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067470  lea     rax, aPcpEccEkcert; "PCP_ECC_EKCERT"
0x180067477  mov     [rbp+var_28], rax
0x18006747b  mov     [rbp+var_20], 26h ; '&'
0x180067482  lea     r8, [rbp+var_28]
0x180067486  lea     rdx, [rbp+var_18]
0x18006748a  mov     rcx, rbx
0x18006748d  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x180067492  lea     rax, aPcpEccEkpub; "PCP_ECC_EKPUB"
0x180067499  mov     [rbp+var_28], rax
0x18006749d  mov     [rbp+var_20], 27h ; '''
0x1800674a4  lea     r8, [rbp+var_28]
0x1800674a8  lea     rdx, [rbp+var_18]
0x1800674ac  mov     rcx, rbx
0x1800674af  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800674b4  lea     rax, aPcpEkstore; "PCP_EKSTORE"
0x1800674bb  mov     [rbp+var_28], rax
0x1800674bf  mov     [rbp+var_20], 28h ; '('
0x1800674c6  lea     r8, [rbp+var_28]
0x1800674ca  lea     rdx, [rbp+var_18]
0x1800674ce  mov     rcx, rbx
0x1800674d1  call    ??$insert@U?$pair@PEBGW4KspProp@@@std@@$0A@@?$map@PEBGW4KspProp@@VPropertyIdentifierCompare@@V?$allocator@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGW4KspProp@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGW4KspProp@@@1@@Z; std::map<ushort const *,KspProp,PropertyIdentifierCompare,std::allocator<std::pair<ushort const * const,KspProp>>>::insert<std::pair<ushort const *,KspProp>,0>(std::pair<ushort const *,KspProp> &&)
0x1800674d6  lea     rax, aPcpEkcert; "PCP_EKCERT"
0x1800674dd  mov     [rbp+var_28], rax
0x1800674e1  mov     [rbp+var_20], 29h ; ')'
0x1800674e8  lea     r8, [rbp+var_28]
0x1800674ec  lea     rdx, [rbp+var_18]
  ... truncated ...
```
