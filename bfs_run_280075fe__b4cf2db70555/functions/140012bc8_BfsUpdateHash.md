# BfsUpdateHash

- ea: `0x140012bc8`
- end: `0x140012bed`
- name: `BfsUpdateHash`
- size: `37`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140006c24`
- `0x140006d20`
- `0x140007044`
- `0x140007250`
- `0x140008e84`
- `0x140009114`
- `0x14000a4bc`
- `0x14000b338`
- `0x14000b4c4`
- `0x14000c8cc`
- `0x14000d848`

## callees

- `0x140012bc8`

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
0x140012bc8  xor     r10d, r10d
0x140012bcb  mov     r11d, edx
0x140012bce  test    edx, edx
0x140012bd0  jz      short locret_140012BEC
0x140012bd2  mov     r9, [r8]
0x140012bd5  movzx   edx, byte ptr [r10+rcx]
0x140012bda  inc     r10d
0x140012bdd  imul    r9, 25h ; '%'
0x140012be1  add     r9, rdx
0x140012be4  cmp     r10d, r11d
0x140012be7  jb      short loc_140012BD5
0x140012be9  mov     [r8], r9
0x140012bec  retn
```
