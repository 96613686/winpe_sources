# ATL::CDacl::CAccessAce::GetLength(void)

- ea: `0x1800203e0`
- end: `0x1800203f6`
- name: `?GetLength@CAccessAce@CDacl@ATL@@UEBAIXZ`
- size: `22`
- prototype: `unsigned int __fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800203e8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800203e8`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessAce::GetLength(ATL::CDacl::CAccessAce *this)
{
  return GetLengthSid((char *)this + 16) + 8;
}

```

## disassembly

```asm
0x1800203e0  sub     rsp, 28h
0x1800203e4  add     rcx, 10h; pSid
0x1800203e8  call    cs:__imp_GetLengthSid
0x1800203ee  add     eax, 8
0x1800203f1  add     rsp, 28h
0x1800203f5  retn
```
