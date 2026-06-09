# SecurityManager::Sha256HashData(uchar *,uint,uchar * const)

- ea: `0x1402749ac`
- end: `0x140274a89`
- name: `?Sha256HashData@SecurityManager@@AEAAJPEAEIQEAE@Z`
- size: `221`
- prototype: `int(SecurityManager *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400de630`
- `0x140273cd0`

## callees

- `0x140132940`
- `0x1402749ac`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x140274a44`
- `bcrypt!BCryptFinishHash` at `0x140274a44`
- `bcrypt!BCryptDestroyHash` at `0x140274a64`
- `bcrypt!BCryptDestroyHash` at `0x140274a64`
- `bcrypt!BCryptHashData` at `0x140274a21`
- `bcrypt!BCryptHashData` at `0x140274a21`
- `bcrypt!BCryptCreateHash` at `0x140274a01`
- `bcrypt!BCryptCreateHash` at `0x140274a01`

## pseudocode

```c

```
