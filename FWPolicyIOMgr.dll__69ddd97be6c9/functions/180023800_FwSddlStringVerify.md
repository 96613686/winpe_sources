# FwSddlStringVerify

- ea: `0x180023800`
- end: `0x18002381d`
- name: `FwSddlStringVerify`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180023800`

## import_xrefs

- `fwbase!Int_FwValidateSecurityDescriptor` at `0x180023806`
- `fwbase!Int_FwValidateSecurityDescriptor` at `0x180023806`

## pseudocode

```c
__int64 __fastcall FwSddlStringVerify(__int64 a1)
{
  __int64 result; // rax

  result = Int_FwValidateSecurityDescriptor(a1, 0);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180023800  sub     rsp, 28h
0x180023804  xor     edx, edx
0x180023806  call    cs:__imp_Int_FwValidateSecurityDescriptor
0x18002380c  test    eax, eax
0x18002380e  jle     short loc_180023818
0x180023810  movzx   eax, ax
0x180023813  or      eax, 80070000h
0x180023818  add     rsp, 28h
0x18002381c  retn
```
