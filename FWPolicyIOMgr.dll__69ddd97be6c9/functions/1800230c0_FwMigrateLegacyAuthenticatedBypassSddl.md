# FwMigrateLegacyAuthenticatedBypassSddl

- ea: `0x1800230c0`
- end: `0x1800230e0`
- name: `FwMigrateLegacyAuthenticatedBypassSddl`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a8fc`
- `0x18002ad4c`
- `0x180031964`
- `0x180032050`

## callees

- `0x1800230c0`

## import_xrefs

- `fwbase!Int_FwValidateAndMigrateSecurityDescriptor` at `0x1800230c9`
- `fwbase!Int_FwValidateAndMigrateSecurityDescriptor` at `0x1800230c9`

## pseudocode

```c
__int64 __fastcall FwMigrateLegacyAuthenticatedBypassSddl(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = Int_FwValidateAndMigrateSecurityDescriptor(a1, 0, a2);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800230c0  sub     rsp, 28h
0x1800230c4  mov     r8, rdx
0x1800230c7  xor     edx, edx
0x1800230c9  call    cs:__imp_Int_FwValidateAndMigrateSecurityDescriptor
0x1800230cf  test    eax, eax
0x1800230d1  jle     short loc_1800230DB
0x1800230d3  movzx   eax, ax
0x1800230d6  or      eax, 80070000h
0x1800230db  add     rsp, 28h
0x1800230df  retn
```
