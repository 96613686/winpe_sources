# Sha256Helper::ComputeSha256(void *,ulong,uchar *)

- ea: `0x1801a0b94`
- end: `0x1801a0c5e`
- name: `?ComputeSha256@Sha256Helper@@SAJPEAXKPEAE@Z`
- size: `202`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1801a1554`

## callees

- `0x1801a0b94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0c2c`
- `CRYPTSP!CryptGetHashParam` at `0x1801a0c22`
- `CRYPTSP!CryptGetHashParam` at `0x1801a0c22`
- `CRYPTSP!CryptDestroyHash` at `0x1801a0c46`
- `CRYPTSP!CryptDestroyHash` at `0x1801a0c46`
- `CRYPTSP!CryptCreateHash` at `0x1801a0bce`
- `CRYPTSP!CryptCreateHash` at `0x1801a0bce`
- `CRYPTSP!CryptHashData` at `0x1801a0bfa`
- `CRYPTSP!CryptHashData` at `0x1801a0bfa`

## pseudocode

```c

```
