# FillBitCache

- ea: `0x18003e3ec`
- end: `0x18003e48b`
- name: `FillBitCache`
- size: `159`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18003dd44`
- `0x18003df38`
- `0x18003e494`
- `0x18005d094`
- `0x18005d100`
- `0x18005d170`
- `0x18005d1f8`
- `0x18005d26c`
- `0x18005d308`
- `0x18005d730`

## callees

- `0x18003e3ec`

## pseudocode

```c
char *__fastcall FillBitCache(unsigned int *a1, unsigned int a2)
{
  unsigned __int64 v2; // r11
  unsigned int *v4; // r9
  unsigned int v5; // r10d
  unsigned int v6; // ecx
  char *result; // rax
  unsigned int v8; // eax
  unsigned int v9; // edx

  v2 = *((_QWORD *)a1 + 1);
  v4 = (unsigned int *)*((_QWORD *)a1 + 2);
  v5 = *a1;
  if ( (unsigned __int64)v4 <= v2 - 4 )
  {
    v8 = (32 - v5) & 0xFFFFFFF8;
    v9 = _byteswap_ulong(*v4);
    if ( v5 )
      v9 = (a1[1] << v8) | (v9 >> (32 - v8));
    a1[1] = v9;
    *a1 = v8 + v5;
    result = (char *)v4 + (v8 >> 3);
    *((_QWORD *)a1 + 2) = result;
  }
  else
  {
    v6 = a1[1];
    do
    {
      if ( (unsigned __int64)v4 >= v2 )
      {
        v4 = (unsigned int *)*((_QWORD *)a1 + 3);
        *((_QWORD *)a1 + 2) = v4;
        a1[11] = 1;
      }
      result = (char *)*(unsigned __int8 *)v4;
      v5 += 8;
      v4 = (unsigned int *)((char *)v4 + 1);
      v6 = (unsigned int)result | (v6 << 8);
      *((_QWORD *)a1 + 2) = v4;
      a1[1] = v6;
      *a1 = v5;
    }
    while ( v5 < a2 );
  }
  return result;
}

```

## disassembly

```asm
0x18003e3ec  mov     [rsp+arg_0], rbx
0x18003e3f1  mov     r11, [rcx+8]
0x18003e3f5  mov     r8, rcx
0x18003e3f8  mov     r9, [rcx+10h]
0x18003e3fc  mov     r10d, [rcx]
0x18003e3ff  lea     rax, [r11-4]
0x18003e403  cmp     r9, rax
0x18003e406  jbe     short loc_18003E447
0x18003e408  mov     ecx, [rcx+4]
0x18003e40b  cmp     r9, r11
0x18003e40e  jb      short loc_18003E420
0x18003e410  mov     r9, [r8+18h]
0x18003e414  mov     [r8+10h], r9
0x18003e418  mov     dword ptr [r8+2Ch], 1
0x18003e420  movzx   eax, byte ptr [r9]
0x18003e424  add     r10d, 8
0x18003e428  shl     ecx, 8
0x18003e42b  inc     r9
0x18003e42e  or      ecx, eax
0x18003e430  mov     [r8+10h], r9
0x18003e434  mov     [r8+4], ecx
0x18003e438  mov     [r8], r10d
0x18003e43b  cmp     r10d, edx
0x18003e43e  jb      short loc_18003E40B
0x18003e440  mov     rbx, [rsp+arg_0]
0x18003e445  retn
0x18003e447  mov     edx, [r9]
0x18003e44a  mov     ecx, 20h ; ' '
0x18003e44f  mov     eax, ecx
0x18003e451  sub     eax, r10d
0x18003e454  and     eax, 0FFFFFFF8h
0x18003e457  mov     ebx, eax
0x18003e459  mov     r11d, eax
0x18003e45c  shr     ebx, 3
0x18003e45f  bswap   edx
0x18003e461  test    r10d, r10d
0x18003e464  jz      short loc_18003E475
0x18003e466  sub     cl, r11b
0x18003e469  shr     edx, cl
0x18003e46b  mov     ecx, eax
0x18003e46d  mov     eax, [r8+4]
0x18003e471  shl     eax, cl
0x18003e473  or      edx, eax
0x18003e475  lea     eax, [r11+r10]
0x18003e479  mov     [r8+4], edx
0x18003e47d  mov     [r8], eax
0x18003e480  mov     eax, ebx
0x18003e482  add     rax, r9
0x18003e485  mov     [r8+10h], rax
0x18003e489  jmp     short loc_18003E440
```
