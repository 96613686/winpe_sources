# BfsUpdateHash

- ea: `0x140012d00`
- end: `0x140012d25`
- name: `BfsUpdateHash`
- size: `37`
- prototype: `void __fastcall(__int64, unsigned int, __int64 *)`
- caller_count: `11`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140006db4`
- `0x140006eb0`
- `0x1400071d4`
- `0x1400073e0`
- `0x140009014`
- `0x1400092a4`
- `0x14000a64c`
- `0x14000b4c8`
- `0x14000b654`
- `0x14000ca5c`
- `0x14000d9dc`

## callees

- `0x140012d00`

## pseudocode

```c
void __fastcall BfsUpdateHash(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r9
  __int64 v6; // rdx

  v3 = 0;
  if ( a2 )
  {
    v5 = *a3;
    do
    {
      v6 = *(unsigned __int8 *)(v3 + a1);
      v3 = (unsigned int)(v3 + 1);
      v5 = v6 + 37 * v5;
    }
    while ( (unsigned int)v3 < a2 );
    *a3 = v5;
  }
}

```

## disassembly

```asm
0x140012d00  xor     r10d, r10d
0x140012d03  mov     r11d, edx
0x140012d06  test    edx, edx
0x140012d08  jz      short locret_140012D24
0x140012d0a  mov     r9, [r8]
0x140012d0d  movzx   edx, byte ptr [r10+rcx]
0x140012d12  inc     r10d
0x140012d15  imul    r9, 25h ; '%'
0x140012d19  add     r9, rdx
0x140012d1c  cmp     r10d, r11d
0x140012d1f  jb      short loc_140012D0D
0x140012d21  mov     [r8], r9
0x140012d24  retn
```
