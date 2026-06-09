# ConstrainedImpersonateLoggedOnUser::DuplicateImpersonationToken(void * *)

- ea: `0x180027310`
- end: `0x1800273ca`
- name: `?DuplicateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@QEAAJPEAPEAX@Z`
- size: `186`
- prototype: `int(ConstrainedImpersonateLoggedOnUser *__hidden this, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180022520`
- `0x180022744`
- `0x180022968`
- `0x180022b8c`

## callees

- `0x180006e8c`
- `0x180006eac`
- `0x180027310`
- `0x1800276dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002736e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002736e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180027398`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180027398`

## string_xrefs

- `0x18002733c`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x1800273a7`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c

```
