# DavIsUrlPathLocal

- ea: `0x180029c44`
- end: `0x180029c7c`
- name: `DavIsUrlPathLocal`
- size: `56`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800049bc`
- `0x180007e10`
- `0x1800099d0`
- `0x18001ca70`
- `0x180021f00`
- `0x180029dcc`

## callees

- `0x180029c44`

## pseudocode

```c
__int64 __fastcall DavIsUrlPathLocal(_WORD *a1)
{
  unsigned int v1; // edx
  __int64 result; // rax

  if ( !a1 )
    return 0;
  v1 = 0;
  result = 1;
  while ( *a1 && v1 < 3 )
  {
    if ( *a1 == 46 )
      return 0;
    if ( *a1 == 47 || *a1 == 92 )
      ++v1;
    ++a1;
  }
  return result;
}

```

## disassembly

```asm
0x180029c44  xor     r8d, r8d
0x180029c47  test    rcx, rcx
0x180029c4a  jz      short loc_180029C79
0x180029c4c  mov     edx, r8d
0x180029c4f  lea     eax, [r8+1]
0x180029c53  jmp     short loc_180029C72
0x180029c55  cmp     edx, 3
0x180029c58  jnb     short locret_180029C7B
0x180029c5a  cmp     word ptr [rcx], 2Eh ; '.'
0x180029c5e  jz      short loc_180029C79
0x180029c60  cmp     word ptr [rcx], 2Fh ; '/'
0x180029c64  jz      short loc_180029C6C
0x180029c66  cmp     word ptr [rcx], 5Ch ; '\'
0x180029c6a  jnz     short loc_180029C6E
0x180029c6c  add     edx, eax
0x180029c6e  add     rcx, 2
0x180029c72  cmp     [rcx], r8w
0x180029c76  jnz     short loc_180029C55
0x180029c78  retn
0x180029c79  xor     eax, eax
0x180029c7b  retn
```
