# ATL::CDacl::CAccessAce::GetLength(void)

- ea: `0x140012ee0`
- end: `0x140012ef6`
- name: `?GetLength@CAccessAce@CDacl@ATL@@UEBAIXZ`
- size: `22`
- prototype: `unsigned int __fastcall(ATL::CDacl::CAccessAce *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140012ee8`
- `ADVAPI32!GetLengthSid` at `0x140012ee8`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessAce::GetLength(ATL::CDacl::CAccessAce *this)
{
  return GetLengthSid((char *)this + 16) + 8;
}

```

## disassembly

```asm
0x140012ee0  sub     rsp, 28h
0x140012ee4  add     rcx, 10h; pSid
0x140012ee8  call    cs:__imp_GetLengthSid
0x140012eee  add     eax, 8
0x140012ef1  add     rsp, 28h
0x140012ef5  retn
```
