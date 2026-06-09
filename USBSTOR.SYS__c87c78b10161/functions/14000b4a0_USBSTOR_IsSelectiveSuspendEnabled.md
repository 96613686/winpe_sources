# USBSTOR_IsSelectiveSuspendEnabled

- ea: `0x14000b4a0`
- end: `0x14000b4c2`
- name: `USBSTOR_IsSelectiveSuspendEnabled`
- size: `34`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b0bc`
- `0x14000b420`
- `0x140020c90`
- `0x140028d30`

## callees

- `0x14000b4a0`

## pseudocode

```c
char __fastcall USBSTOR_IsSelectiveSuspendEnabled(__int64 a1)
{
  char result; // al
  int v2; // eax

  result = *(_BYTE *)(a1 + 2041);
  if ( result == -1 )
  {
    v2 = *(_DWORD *)(a1 + 132);
    return (v2 & 0x80u) != 0 && (v2 & 0x400) == 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000b4a0  movzx   eax, byte ptr [rcx+7F9h]
0x14000b4a7  cmp     al, 0FFh
0x14000b4a9  jnz     short locret_14000B4B7
0x14000b4ab  mov     eax, [rcx+84h]
0x14000b4b1  test    al, al
0x14000b4b3  js      short loc_14000B4B9
0x14000b4b5  xor     al, al
0x14000b4b7  retn
0x14000b4b9  bt      eax, 0Ah
0x14000b4bd  jb      short loc_14000B4B5
0x14000b4bf  mov     al, 1
0x14000b4c1  retn
```
