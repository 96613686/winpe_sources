# MsvpCredentialToCachePasswords

- ea: `0x180008760`
- end: `0x180008775`
- name: `MsvpCredentialToCachePasswords`
- size: `21`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008760`

## pseudocode

```c
char __fastcall MsvpCredentialToCachePasswords(__int64 a1, __int64 a2)
{
  char result; // al

  result = *(_BYTE *)(a1 + 9);
  *(_BYTE *)(a2 + 32) = result;
  if ( *(_BYTE *)(a1 + 9) )
    *(_OWORD *)a2 = *(_OWORD *)(a1 + 38);
  return result;
}

```

## disassembly

```asm
0x180008760  mov     al, [rcx+9]
0x180008763  mov     [rdx+20h], al
0x180008766  cmp     byte ptr [rcx+9], 0
0x18000876a  jz      short locret_180008774
0x18000876c  movups  xmm0, xmmword ptr [rcx+26h]
0x180008770  movdqu  xmmword ptr [rdx], xmm0
0x180008774  retn
```
