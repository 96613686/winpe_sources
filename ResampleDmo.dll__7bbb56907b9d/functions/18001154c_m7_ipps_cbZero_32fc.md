# m7_ipps_cbZero_32fc

- ea: `0x18001154c`
- end: `0x18001158b`
- name: `m7_ipps_cbZero_32fc`
- size: `63`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18005363c`
- `0x18005372c`
- `0x1800538f4`
- `0x180053a6c`
- `0x180055d6c`
- `0x180055e5c`
- `0x180056024`
- `0x18005619c`
- `0x1800588dc`
- `0x1800589cc`
- `0x180058b94`
- `0x180058d0c`

## callees

- `0x18001154c`

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
0x18001154c  xor     r10d, r10d
0x18001154f  lea     eax, [rdx-1]
0x180011552  cdqe
0x180011554  mov     r9d, r10d
0x180011557  test    rax, rax
0x18001155a  jle     short loc_18001157E
0x18001155c  dec     rax
0x18001155f  lea     r8, [rcx+4]
0x180011563  shr     rax, 1
0x180011566  inc     rax
0x180011569  lea     r9d, [rax+rax]
0x18001156d  mov     [r8-4], r10
0x180011571  mov     [r8+4], r10
0x180011575  lea     r8, [r8+10h]
0x180011579  dec     rax
0x18001157c  jnz     short loc_18001156D
0x18001157e  test    dl, 1
0x180011581  jz      short locret_18001158A
0x180011583  movsxd  rax, r9d
0x180011586  mov     [rcx+rax*8], r10
0x18001158a  retn
```
