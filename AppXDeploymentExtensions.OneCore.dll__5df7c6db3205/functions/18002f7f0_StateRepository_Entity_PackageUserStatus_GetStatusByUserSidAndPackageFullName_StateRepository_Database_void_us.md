# StateRepository::Entity::PackageUserStatus::GetStatusByUserSidAndPackageFullName(StateRepository::Database &,void *,ushort const *,StateRepository::PackageStatus &)

- ea: `0x18002f7f0`
- end: `0x18002fa97`
- name: `?GetStatusByUserSidAndPackageFullName@PackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEBGAEAW4PackageStatus@3@@Z`
- size: `679`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, PSID pSid, const unsigned __int16 *, enum StateRepository::PackageStatus *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086220`
- `0x1801e5fe4`

## callees

- `0x180027364`
- `0x1800273e0`
- `0x1800276b8`
- `0x1800276d0`
- `0x18002788c`
- `0x18002f7f0`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800bba3c`
- `0x18018ca78`
- `0x180211010`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x18002f9a5`
- `StateRepository.Core!sqlite3_db_handle` at `0x18002f9a5`
- `StateRepository.Core!sqlite3_errcode` at `0x18002f9ae`
- `StateRepository.Core!sqlite3_errcode` at `0x18002f9ae`
- `StateRepository.Core!sqlite3_column_int` at `0x18002f962`
- `StateRepository.Core!sqlite3_column_int` at `0x18002f962`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002f84d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002f84d`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x18002f9f8`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x18002f9f8`

## string_xrefs

- `0x18002f8c8`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002f93f`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002f988`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002f8f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002f825`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x18002f9d9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x18002fa06`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x18002fa4e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x18002f88a`: `SELECT pus.Status FROM PackageUserStatus AS pus INNER JOIN User AS u ON u._UserID=pus.User INNER JOIN PackageIdentity AS pi ON pi._PackageIdentityID=pus.PackageIdentity WHERE u.UserSid=? AND pi.PackageFullName=?;`

## pseudocode

```c

```
