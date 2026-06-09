# WSTrustCertificateTokenRequest::CreateSecurityToken(CSecureString &)

- ea: `0x18005cc6c`
- end: `0x18005cec2`
- name: `?CreateSecurityToken@WSTrustCertificateTokenRequest@@AEAAJAEAVCSecureString@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(WSTrustCertificateTokenRequest *__hidden this, struct CSecureString *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ca00`
- `0x18005cb30`

## callees

- `0x180003c20`
- `0x1800065e8`
- `0x1800067f4`
- `0x18000685c`
- `0x1800090d0`
- `0x18000a300`
- `0x18000c7ac`
- `0x18001502c`
- `0x18005cc6c`
- `0x180071e14`
- `0x1800765b0`
- `0x180076aec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64_s` at `0x18005cd02`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64_s` at `0x18005cd80`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64_s` at `0x18005cd02`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64_s` at `0x18005cd80`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18005ccf4`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18005ccf4`

## string_xrefs

- `0x18005ce70`: `<o:Security s:mustUnderstand='1' xmlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd'><u:Timestamp u:Id='_0'><u:Created>%s</u:Created><u:Expires>%s</u:Expires></u:Timestamp><o:BinarySecurityToken ValueType='%s' EncodingType='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary' u:Id='uuid-%s'>%s</o:BinarySecurityToken></o:Security>`
- `0x18005ce5e`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3`

## pseudocode

```c

```
