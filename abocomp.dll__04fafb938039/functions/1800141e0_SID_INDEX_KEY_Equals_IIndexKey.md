# SID_INDEX_KEY::Equals(IIndexKey *)

- ea: `0x1800141e0`
- end: `0x1800141ef`
- name: `?Equals@SID_INDEX_KEY@@UEBAHPEAVIIndexKey@@@Z`
- size: `15`
- prototype: `__int64 __fastcall(SID_INDEX_KEY *__hidden this, struct IIndexKey *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800141e8`

## pseudocode

```c
BOOL __fastcall SID_INDEX_KEY::Equals(PSID *this, PSID *a2)
{
  return EqualSid(this[1], a2[1]);
}

```

## disassembly

```asm
0x1800141e0  mov     rdx, [rdx+8]
0x1800141e4  mov     rcx, [rcx+8]
0x1800141e8  jmp     cs:__imp_EqualSid
```
