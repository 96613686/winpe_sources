# Csl::HashBytes(uchar *,ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,Csl::HashAlgorithm)

- ea: `0x18002c6f8`
- end: `0x18002cbac`
- name: `?HashBytes@Csl@@YAJPEAEKAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4HashAlgorithm@1@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800fa4d8`
- `0x180121dec`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x180016774`
- `0x18002ba20`
- `0x18002c6f8`
- `0x18002df48`
- `0x18002e004`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002c779`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002c779`
- `bcrypt!BCryptDestroyHash` at `0x18002c837`
- `bcrypt!BCryptDestroyHash` at `0x18002c95a`
- `bcrypt!BCryptDestroyHash` at `0x18002ca8b`
- `bcrypt!BCryptDestroyHash` at `0x18002cb6a`
- `bcrypt!BCryptDestroyHash` at `0x18002c837`
- `bcrypt!BCryptDestroyHash` at `0x18002c95a`
- `bcrypt!BCryptDestroyHash` at `0x18002ca8b`
- `bcrypt!BCryptDestroyHash` at `0x18002cb6a`
- `bcrypt!BCryptHashData` at `0x18002c855`
- `bcrypt!BCryptHashData` at `0x18002c855`
- `bcrypt!BCryptCreateHash` at `0x18002c800`
- `bcrypt!BCryptCreateHash` at `0x18002c800`
- `bcrypt!BCryptFinishHash` at `0x18002c90e`
- `bcrypt!BCryptFinishHash` at `0x18002c90e`
- `bcrypt!BCryptGetProperty` at `0x18002c8a0`
- `bcrypt!BCryptGetProperty` at `0x18002c8a0`
- `CRYPT32!CryptBinaryToStringW` at `0x18002c9e3`
- `CRYPT32!CryptBinaryToStringW` at `0x18002cade`
- `CRYPT32!CryptBinaryToStringW` at `0x18002c9e3`
- `CRYPT32!CryptBinaryToStringW` at `0x18002cade`

## pseudocode

```c

```
