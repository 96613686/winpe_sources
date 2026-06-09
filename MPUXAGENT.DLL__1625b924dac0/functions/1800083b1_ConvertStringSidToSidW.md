# ConvertStringSidToSidW

- ea: `0x1800083b1`
- end: `0x1800083b7`
- name: `ConvertStringSidToSidW`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR StringSid, PSID *Sid)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1800067b4`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x1800083b1`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall ConvertStringSidToSidW(LPCWSTR StringSid, PSID *Sid)
{
  return __imp_ConvertStringSidToSidW(StringSid, Sid);
}

```

## disassembly

```asm
0x1800083b1  jmp     cs:__imp_ConvertStringSidToSidW
```
