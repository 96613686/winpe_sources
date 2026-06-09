# ATL::CSid::IsValid(void)

- ea: `0x180023504`
- end: `0x180023526`
- name: `?IsValid@CSid@ATL@@QEBA_NXZ`
- size: `34`
- prototype: `bool __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c3d0`

## callees

- `0x180023504`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180023512`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180023512`

## pseudocode

```c
bool __fastcall ATL::CSid::IsValid(ATL::CSid *this)
{
  return *((_BYTE *)this + 76) && IsValidSid((char *)this + 8);
}

```

## disassembly

```asm
0x180023504  sub     rsp, 28h
0x180023508  cmp     byte ptr [rcx+4Ch], 0
0x18002350c  jz      short loc_180023522
0x18002350e  add     rcx, 8; pSid
0x180023512  call    cs:__imp_IsValidSid
0x180023518  test    eax, eax
0x18002351a  setnz   al
0x18002351d  add     rsp, 28h
0x180023521  retn
0x180023522  xor     al, al
0x180023524  jmp     short loc_18002351D
```
