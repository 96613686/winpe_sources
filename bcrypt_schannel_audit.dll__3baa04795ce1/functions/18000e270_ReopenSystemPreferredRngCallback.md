# ReopenSystemPreferredRngCallback

- ea: `0x18000e270`
- end: `0x18000e2bb`
- name: `ReopenSystemPreferredRngCallback`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x18000e270`
- `0x18000e2c4`

## string_xrefs

- `0x18000e2a2`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 ReopenSystemPreferredRngCallback()
{
  BCRYPT_ALG_HANDLE *v0; // rcx
  __int64 result; // rax

  v0 = &qword_180024AA8;
  if ( g_fLoadCNGDone )
    v0 = &hAlgorithm;
  result = ReopenSystemPreferredRngHandle(v0);
  if ( (int)result < 0 )
    return DebugTraceError(
             (unsigned int)result,
             "Status",
             "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c");
  return result;
}

```

## disassembly

```asm
0x18000e270  sub     rsp, 28h
0x18000e274  cmp     cs:g_fLoadCNGDone, 0
0x18000e27b  lea     rax, hAlgorithm
0x18000e282  lea     rcx, qword_180024AA8
0x18000e289  cmovnz  rcx, rax
0x18000e28d  call    ReopenSystemPreferredRngHandle
0x18000e292  test    eax, eax
0x18000e294  js      short loc_18000E29C
0x18000e296  add     rsp, 28h
0x18000e29a  retn
0x18000e29c  mov     r9d, 0B2h
0x18000e2a2  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e2a9  lea     rdx, aStatus; "Status"
0x18000e2b0  mov     ecx, eax
0x18000e2b2  add     rsp, 28h
0x18000e2b6  jmp     DebugTraceError
```
