# FwCSRuleVerify

- ea: `0x1800214b0`
- end: `0x1800214da`
- name: `FwCSRuleVerify`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800214b0`

## import_xrefs

- `fwbase!Int_FWVerifyConnectionSecurityRule` at `0x1800214c3`
- `fwbase!Int_FWVerifyConnectionSecurityRule` at `0x1800214c3`

## pseudocode

```c
__int64 __fastcall FwCSRuleVerify(__int64 a1)
{
  __int64 result; // rax

  result = Int_FWVerifyConnectionSecurityRule(545, a1, a1 + 384);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800214b0  sub     rsp, 28h
0x1800214b4  mov     rdx, rcx
0x1800214b7  lea     r8, [rcx+180h]
0x1800214be  mov     ecx, 221h
0x1800214c3  call    cs:__imp_Int_FWVerifyConnectionSecurityRule
0x1800214c9  test    eax, eax
0x1800214cb  jle     short loc_1800214D5
0x1800214cd  movzx   eax, ax
0x1800214d0  or      eax, 80070000h
0x1800214d5  add     rsp, 28h
0x1800214d9  retn
```
