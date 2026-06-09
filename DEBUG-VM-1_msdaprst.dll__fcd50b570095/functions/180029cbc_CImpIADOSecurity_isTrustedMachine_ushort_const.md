# CImpIADOSecurity::isTrustedMachine(ushort const *)

- ea: `0x180029cbc`
- end: `0x180029d0a`
- name: `?isTrustedMachine@CImpIADOSecurity@@AEAAJPEBG@Z`
- size: `78`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029410`
- `0x1800295b0`

## callees

- `0x180029a14`
- `0x180029bf8`
- `0x180029cbc`

## pseudocode

```c
_BOOL8 __fastcall CImpIADOSecurity::isTrustedMachine(CImpIADOSecurity *this, const unsigned __int16 *a2)
{
  CImpIADOSecurity *v2; // rcx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]

  v5 = HIDWORD(this);
  v4 = 4;
  return (int)CImpIADOSecurity::getZone(this, a2, &v4, 0) < 0
      || v4
      || (int)CImpIADOSecurity::getPolicy(v2, 0, &v4) < 0
      || v4 != 0;
}

```

## disassembly

```asm
0x180029cbc  mov     qword ptr [rsp+arg_0], rcx
0x180029cc1  sub     rsp, 28h
0x180029cc5  xor     r9d, r9d; struct IInternetSecurityManager **
0x180029cc8  mov     [rsp+28h+arg_0], 4
0x180029cd0  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x180029cd5  call    ?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z; CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)
0x180029cda  test    eax, eax
0x180029cdc  js      short loc_180029D00
0x180029cde  cmp     [rsp+28h+arg_0], 0
0x180029ce3  jnz     short loc_180029D00
0x180029ce5  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x180029cea  xor     edx, edx; unsigned int
0x180029cec  call    ?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z; CImpIADOSecurity::getPolicy(ulong,ulong *)
0x180029cf1  test    eax, eax
0x180029cf3  js      short loc_180029D00
0x180029cf5  xor     eax, eax
0x180029cf7  cmp     [rsp+28h+arg_0], eax
0x180029cfb  setnz   al
0x180029cfe  jmp     short loc_180029D05
0x180029d00  mov     eax, 1
0x180029d05  add     rsp, 28h
0x180029d09  retn
```
