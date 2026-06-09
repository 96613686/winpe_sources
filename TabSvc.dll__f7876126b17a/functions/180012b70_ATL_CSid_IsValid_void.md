# ATL::CSid::IsValid(void)

- ea: `0x180012b70`
- end: `0x180012b95`
- name: `?IsValid@CSid@ATL@@QEBA_NXZ`
- size: `37`
- prototype: `bool __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c264`

## callees

- `0x180012b70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180012b7e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180012b7e`

## pseudocode

```c
bool __fastcall ATL::CSid::IsValid(ATL::CSid *this)
{
  return *((_BYTE *)this + 76) && IsValidSid((char *)this + 8);
}

```

## disassembly

```asm
0x180012b70  sub     rsp, 28h
0x180012b74  cmp     byte ptr [rcx+4Ch], 0
0x180012b78  jz      short loc_180012B8E
0x180012b7a  add     rcx, 8; pSid
0x180012b7e  call    cs:__imp_IsValidSid
0x180012b84  test    eax, eax
0x180012b86  setnz   al
0x180012b89  add     rsp, 28h
0x180012b8d  retn
0x180012b8e  xor     al, al
0x180012b90  add     rsp, 28h
0x180012b94  retn
```
