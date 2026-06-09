# m7_ipps_cbZero_32fc

- ea: `0x18001fe1c`
- end: `0x18001fe5b`
- name: `m7_ipps_cbZero_32fc`
- size: `63`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180059468`
- `0x180059558`
- `0x180059720`
- `0x180059898`
- `0x18005bb98`
- `0x18005bc88`
- `0x18005be50`
- `0x18005bfc8`
- `0x18005e6fc`
- `0x18005e7ec`
- `0x18005e9b4`
- `0x18005eb2c`

## callees

- `0x18001fe1c`

## pseudocode

```c
signed __int64 __fastcall m7_ipps_cbZero_32fc(__int64 a1, int a2)
{
  signed __int64 result; // rax
  int v3; // r9d
  __int64 v4; // r8

  result = a2 - 1;
  v3 = 0;
  if ( result > 0 )
  {
    v4 = a1 + 4;
    result = ((unsigned __int64)(result - 1) >> 1) + 1;
    v3 = 2 * result;
    do
    {
      *(_QWORD *)(v4 - 4) = 0;
      *(_QWORD *)(v4 + 4) = 0;
      v4 += 16;
      --result;
    }
    while ( result );
  }
  if ( (a2 & 1) != 0 )
  {
    result = v3;
    *(_QWORD *)(a1 + 8LL * v3) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001fe1c  xor     r10d, r10d
0x18001fe1f  lea     eax, [rdx-1]
0x18001fe22  cdqe
0x18001fe24  mov     r9d, r10d
0x18001fe27  test    rax, rax
0x18001fe2a  jle     short loc_18001FE4E
0x18001fe2c  dec     rax
0x18001fe2f  lea     r8, [rcx+4]
0x18001fe33  shr     rax, 1
0x18001fe36  inc     rax
0x18001fe39  lea     r9d, [rax+rax]
0x18001fe3d  mov     [r8-4], r10
0x18001fe41  mov     [r8+4], r10
0x18001fe45  lea     r8, [r8+10h]
0x18001fe49  dec     rax
0x18001fe4c  jnz     short loc_18001FE3D
0x18001fe4e  test    dl, 1
0x18001fe51  jz      short locret_18001FE5A
0x18001fe53  movsxd  rax, r9d
0x18001fe56  mov     [rcx+rax*8], r10
0x18001fe5a  retn
```
