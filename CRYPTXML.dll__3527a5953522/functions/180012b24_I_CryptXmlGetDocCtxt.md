# I_CryptXmlGetDocCtxt

- ea: `0x180012b24`
- end: `0x180012b3d`
- name: `I_CryptXmlGetDocCtxt`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012600`
- `0x180015ea0`
- `0x1800160e4`
- `0x180017224`

## callees

- `0x180012b24`

## pseudocode

```c
__int64 __fastcall I_CryptXmlGetDocCtxt(__int64 a1)
{
  __int64 result; // rax

  result = 0;
  while ( a1 )
  {
    if ( *(_DWORD *)a1 == 1145324609 )
      return a1;
    a1 = *(_QWORD *)(a1 + 80);
  }
  return result;
}

```

## disassembly

```asm
0x180012b24  xor     eax, eax
0x180012b26  test    rcx, rcx
0x180012b29  jz      short locret_180012B3C
0x180012b2b  cmp     dword ptr [rcx], 44444441h
0x180012b31  jz      short loc_180012B39
0x180012b33  mov     rcx, [rcx+50h]
0x180012b37  jmp     short loc_180012B26
0x180012b39  mov     rax, rcx
0x180012b3c  retn
```
