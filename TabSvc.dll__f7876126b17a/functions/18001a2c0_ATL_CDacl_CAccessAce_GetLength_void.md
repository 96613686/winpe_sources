# ATL::CDacl::CAccessAce::GetLength(void)

- ea: `0x18001a2c0`
- end: `0x18001a2d6`
- name: `?GetLength@CAccessAce@CDacl@ATL@@UEBAIXZ`
- size: `22`
- prototype: `__int64 __fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a2c8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a2c8`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessAce::GetLength(ATL::CDacl::CAccessAce *this)
{
  return GetLengthSid((char *)this + 16) + 8;
}

```

## disassembly

```asm
0x18001a2c0  sub     rsp, 28h
0x18001a2c4  add     rcx, 10h; pSid
0x18001a2c8  call    cs:__imp_GetLengthSid
0x18001a2ce  add     eax, 8
0x18001a2d1  add     rsp, 28h
0x18001a2d5  retn
```
