# UserAccountStore::GetAccountFromUserSid(ushort const *,IUserAccount * *)

- ea: `0x1800166c0`
- end: `0x18001677a`
- name: `?GetAccountFromUserSid@UserAccountStore@@UEAAJPEBGPEAPEAUIUserAccount@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const unsigned __int16 *, struct IUserAccount **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18000a5c4`
- `0x18000a5e4`
- `0x180014208`
- `0x1800166c0`
- `0x180016780`
- `0x180017a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800166e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800166e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016716`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016716`

## pseudocode

```c

```
