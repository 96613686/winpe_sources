# CheckTokenMembership_0

- ea: `0x180004223`
- end: `0x180004229`
- name: `CheckTokenMembership_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE TokenHandle, PSID SidToCheck, PBOOL IsMember)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004223`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall CheckTokenMembership_0(HANDLE TokenHandle, PSID SidToCheck, PBOOL IsMember)
{
  return CheckTokenMembership(TokenHandle, SidToCheck, IsMember);
}

```

## disassembly

```asm
0x180004223  jmp     cs:__imp_CheckTokenMembership
```
