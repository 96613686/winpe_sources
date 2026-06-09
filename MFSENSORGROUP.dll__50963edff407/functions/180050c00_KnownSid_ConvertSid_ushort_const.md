# KnownSid::ConvertSid(ushort const *)

- ea: `0x180050c00`
- end: `0x180050c36`
- name: `?ConvertSid@KnownSid@@QEAA_NPEBG@Z`
- size: `54`
- prototype: `bool __fastcall(PSID *Sid, LPCWSTR StringSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800512a8`

## callees

- `0x180050bc8`
- `0x180050c00`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050c1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050c1b`

## pseudocode

```c
bool __fastcall KnownSid::ConvertSid(PSID *Sid, LPCWSTR StringSid)
{
  BOOL v4; // eax

  KnownSid::Cleanup((KnownSid *)Sid);
  v4 = ConvertStringSidToSidW(StringSid, Sid);
  if ( v4 )
  {
    *((_BYTE *)Sid + 8) = 0;
    LOBYTE(v4) = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180050c00  mov     [rsp+arg_0], rbx
0x180050c05  push    rdi
0x180050c06  sub     rsp, 20h
0x180050c0a  mov     rbx, rdx
0x180050c0d  mov     rdi, rcx
0x180050c10  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x180050c15  mov     rdx, rdi; Sid
0x180050c18  mov     rcx, rbx; StringSid
0x180050c1b  call    cs:__imp_ConvertStringSidToSidW
0x180050c21  test    eax, eax
0x180050c23  jz      short loc_180050C2B
0x180050c25  mov     byte ptr [rdi+8], 0
0x180050c29  mov     al, 1
0x180050c2b  mov     rbx, [rsp+28h+arg_0]
0x180050c30  add     rsp, 20h
0x180050c34  pop     rdi
0x180050c35  retn
```
