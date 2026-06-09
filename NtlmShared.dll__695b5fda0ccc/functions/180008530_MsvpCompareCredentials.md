# MsvpCompareCredentials

- ea: `0x180008530`
- end: `0x1800085d9`
- name: `MsvpCompareCredentials`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008530`

## pseudocode

```c
void __fastcall MsvpCompareCredentials(__int64 a1, __int64 a2, int *a3, _DWORD *a4, int *a5)
{
  int v8; // r10d
  char v9; // r8
  __int64 i; // rdx
  char v11; // cl
  char v12; // al
  int v13; // eax
  char v14; // r8
  __int64 j; // rdx
  char v16; // cl
  char v17; // al

  v8 = 1;
  if ( a3 )
  {
    if ( !*(_BYTE *)(a1 + 9) )
      goto LABEL_8;
    if ( !*(_BYTE *)(a2 + 9) )
      goto LABEL_8;
    v9 = 0;
    for ( i = 0; i != 16; ++i )
    {
      v11 = *(_BYTE *)(i + a2 + 38);
      v12 = *(_BYTE *)(i + a1 + 38);
      v9 |= v12 ^ v11;
    }
    if ( !v9 )
      v13 = 1;
    else
LABEL_8:
      v13 = 0;
    *a3 = v13;
  }
  if ( a4 )
    *a4 = 0;
  if ( a5 )
  {
    if ( !*(_BYTE *)(a1 + 10) )
      goto LABEL_18;
    if ( !*(_BYTE *)(a2 + 10) )
      goto LABEL_18;
    v14 = 0;
    for ( j = 0; j != 20; ++j )
    {
      v16 = *(_BYTE *)(j + a2 + 70);
      v17 = *(_BYTE *)(j + a1 + 70);
      v14 |= v17 ^ v16;
    }
    if ( v14 )
LABEL_18:
      v8 = 0;
    *a5 = v8;
  }
}

```

## disassembly

```asm
0x180008530  mov     [rsp+arg_0], rbx
0x180008535  mov     [rsp+arg_8], rdi
0x18000853a  mov     rdi, r8
0x18000853d  mov     r11, rdx
0x180008540  mov     rbx, rcx
0x180008543  mov     r10d, 1
0x180008549  test    r8, r8
0x18000854c  jz      short loc_180008584
0x18000854e  cmp     byte ptr [rcx+9], 0
0x180008552  jz      short loc_180008580
0x180008554  cmp     byte ptr [rdx+9], 0
0x180008558  jz      short loc_180008580
0x18000855a  xor     r8b, r8b
0x18000855d  xor     edx, edx
0x18000855f  mov     cl, [rdx+r11+26h]
0x180008564  mov     al, [rdx+rbx+26h]
0x180008568  add     rdx, r10
0x18000856b  xor     cl, al
0x18000856d  or      r8b, cl
0x180008570  cmp     rdx, 10h
0x180008574  jnz     short loc_18000855F
0x180008576  test    r8b, r8b
0x180008579  jnz     short loc_180008580
0x18000857b  mov     eax, r10d
0x18000857e  jmp     short loc_180008582
0x180008580  xor     eax, eax
0x180008582  mov     [rdi], eax
0x180008584  test    r9, r9
0x180008587  jz      short loc_180008590
0x180008589  mov     dword ptr [r9], 0
0x180008590  mov     r9, [rsp+arg_20]
0x180008595  test    r9, r9
0x180008598  jz      short loc_1800085CE
0x18000859a  cmp     byte ptr [rbx+0Ah], 0
0x18000859e  jz      short loc_1800085C8
0x1800085a0  cmp     byte ptr [r11+0Ah], 0
0x1800085a5  jz      short loc_1800085C8
0x1800085a7  xor     r8b, r8b
0x1800085aa  xor     edx, edx
0x1800085ac  mov     cl, [rdx+r11+46h]
0x1800085b1  mov     al, [rdx+rbx+46h]
0x1800085b5  add     rdx, r10
0x1800085b8  xor     cl, al
0x1800085ba  or      r8b, cl
0x1800085bd  cmp     rdx, 14h
0x1800085c1  jnz     short loc_1800085AC
0x1800085c3  test    r8b, r8b
0x1800085c6  jz      short loc_1800085CB
0x1800085c8  xor     r10d, r10d
0x1800085cb  mov     [r9], r10d
0x1800085ce  mov     rbx, [rsp+arg_0]
0x1800085d3  mov     rdi, [rsp+arg_8]
0x1800085d8  retn
```
