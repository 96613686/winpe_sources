# GetTrustedEnvironment

- ea: `0x18000b094`
- end: `0x18000b0bb`
- name: `GetTrustedEnvironment`
- size: `39`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180005280`
- `0x1800070d0`
- `0x18000997c`
- `0x18000a768`
- `0x1800101c0`
- `0x1800129ac`
- `0x180014510`
- `0x180014740`
- `0x180016068`
- `0x180019b1c`
- `0x18001a61c`

## callees

- `0x18000b094`
- `0x18000b0c4`
- `0x18000b160`

## pseudocode

```c
__int64 GetTrustedEnvironment()
{
  __int64 result; // rax

  result = IsEnclave();
  if ( !(_DWORD)result )
    result = (unsigned int)IsTrustlet() != 0 ? 4 : 1;
  g_TrustedEnvironment = result;
  return result;
}

```

## disassembly

```asm
0x18000b094  sub     rsp, 28h
0x18000b098  call    IsEnclave
0x18000b09d  test    eax, eax
0x18000b09f  jnz     short loc_18000B0AF
0x18000b0a1  call    IsTrustlet
0x18000b0a6  neg     eax
0x18000b0a8  sbb     eax, eax
0x18000b0aa  and     eax, 3
0x18000b0ad  inc     eax
0x18000b0af  mov     cs:g_TrustedEnvironment, eax
0x18000b0b5  add     rsp, 28h
0x18000b0b9  retn
```
