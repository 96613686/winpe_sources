# ConstrainedImpersonateLoggedOnUser::DuplicateImpersonationToken(void * *)

- ea: `0x1800881d0`
- end: `0x18008828a`
- name: `?DuplicateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@QEAAJPEAPEAX@Z`
- size: `186`
- prototype: `int(ConstrainedImpersonateLoggedOnUser *__hidden this, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180086f20`

## callees

- `0x18001330c`
- `0x18001332c`
- `0x1800881d0`
- `0x1800882b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180088221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008822e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180088221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008822e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180088258`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180088258`

## string_xrefs

- `0x1800881fc`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\constrainedimpersonationutil.h`
- `0x180088267`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\constrainedimpersonationutil.h`

## pseudocode

```c

```
