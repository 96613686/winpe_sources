# jsonAppendChar

- ea: `0x180072b08`
- end: `0x180072b23`
- name: `jsonAppendChar`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD *, char)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180072d74`
- `0x180073178`
- `0x180073280`
- `0x180073450`
- `0x180074920`
- `0x180075ef0`
- `0x180076000`
- `0x180076180`
- `0x180077320`
- `0x180077360`
- `0x18007750c`

## callees

- `0x180072b2c`

## pseudocode

```c
__int64 __fastcall jsonAppendChar(_QWORD *a1, char a2)
{
  unsigned __int64 v2; // r8
  __int64 result; // rax

  v2 = a1[3];
  if ( v2 >= a1[2] )
    return jsonAppendCharExpand();
  result = a1[1];
  *(_BYTE *)(v2 + result) = a2;
  ++a1[3];
  return result;
}

```

## disassembly

```asm
0x180072b08  mov     r8, [rcx+18h]
0x180072b0c  cmp     r8, [rcx+10h]
0x180072b10  jnb     jsonAppendCharExpand
0x180072b16  mov     rax, [rcx+8]
0x180072b1a  mov     [r8+rax], dl
0x180072b1e  inc     qword ptr [rcx+18h]
0x180072b22  retn
```
