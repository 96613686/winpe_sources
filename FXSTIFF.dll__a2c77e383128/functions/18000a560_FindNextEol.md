# FindNextEol

- ea: `0x18000a560`
- end: `0x18000a696`
- name: `FindNextEol`
- size: `310`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, unsigned __int64, unsigned __int64 *, _BYTE *, int, _DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac38`
- `0x18000b604`
- `0x18000c660`
- `0x18000cab0`

## callees

- `0x18000a560`

## pseudocode

```c
__int64 __fastcall FindNextEol(
        __int64 a1,
        unsigned __int8 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4,
        _BYTE *a5,
        int a6,
        _DWORD *a7)
{
  __int64 v8; // r10
  unsigned __int8 v9; // dl
  int v10; // esi
  unsigned __int64 v11; // r8
  unsigned __int8 v12; // r10
  _DWORD *v13; // rax
  int v14; // edx
  __int64 v15; // rax

  v8 = a2 >> 3;
  *a7 = 0;
  v9 = a2 - 8 * (a2 >> 3);
  v10 = v8 + a1;
  v11 = v8 + a1 + 1;
  v12 = *((_BYTE *)&qword_18001BCB8[3] + *(unsigned __int8 *)(v8 + a1));
  if ( v12 <= v9 )
  {
    v12 = v9;
  }
  else if ( a6 == 1 )
  {
    *a7 = 1;
  }
  while ( 1 )
  {
    if ( !*(_BYTE *)v11 )
    {
      while ( (v11 & 3) != 0 )
      {
        if ( *(_BYTE *)v11 )
          goto LABEL_15;
        if ( ++v11 >= a3 )
          return 0;
      }
      v13 = (_DWORD *)v11;
      while ( !*v13 )
      {
        if ( (unsigned __int64)++v13 >= a3 )
          return 0;
      }
      v11 = (unsigned __int64)v13;
      if ( !*(_BYTE *)v13 )
      {
        do
          ++v11;
        while ( !*(_BYTE *)v11 );
      }
    }
LABEL_15:
    if ( v11 >= a3 )
      return 0;
    v14 = *((unsigned __int8 *)qword_180043DF0 + *(unsigned __int8 *)v11);
    *a5 = v14;
    if ( v14 + 8 * ((_DWORD)v11 - v10) - (unsigned int)v12 >= 0xB )
      break;
    if ( a6 == 1 )
      *a7 = 1;
    v15 = *(unsigned __int8 *)v11;
    v10 = v11++;
    if ( v11 >= a3 )
      return 0;
    v12 = *((_BYTE *)&qword_18001BCB8[3] + v15);
  }
  *a4 = v11 & 0xFFFFFFFFFFFFFFFCuLL;
  *a5 += ((8 * v11) & 0x18) + 1;
  if ( *a5 > 0x1Fu )
  {
    *a5 -= 32;
    *a4 += 4LL;
  }
  return 1;
}

```

## disassembly

```asm
0x18000a560  push    rbx
0x18000a562  push    rsi
0x18000a563  push    rdi
0x18000a564  push    r15
0x18000a566  mov     rdi, [rsp+20h+arg_30]
0x18000a56b  lea     r15, cs:180000000h
0x18000a572  mov     al, dl
0x18000a574  mov     r11, r8
0x18000a577  shr     al, 3
0x18000a57a  mov     rbx, r9
0x18000a57d  movzx   r10d, al
0x18000a581  mov     al, r10b
0x18000a584  mov     dword ptr [rdi], 0
0x18000a58a  shl     al, 3
0x18000a58d  sub     dl, al
0x18000a58f  lea     rsi, [r10+rcx]
0x18000a593  movzx   eax, byte ptr [rsi]
0x18000a596  lea     r8, [rsi+1]
0x18000a59a  mov     r10b, [rax+r15+1BCD0h]
0x18000a5a2  cmp     r10b, dl
0x18000a5a5  jbe     short loc_18000A5B6
0x18000a5a7  cmp     [rsp+20h+arg_28], 1
0x18000a5ac  jnz     short loc_18000A5B9
0x18000a5ae  mov     dword ptr [rdi], 1
0x18000a5b4  jmp     short loc_18000A5B9
0x18000a5b6  mov     r10b, dl
0x18000a5b9  mov     r9, [rsp+20h+arg_20]
0x18000a5be  cmp     byte ptr [r8], 0
0x18000a5c2  jnz     short loc_18000A60A
0x18000a5c4  jmp     short loc_18000A5D8
0x18000a5c6  cmp     byte ptr [r8], 0
0x18000a5ca  jnz     short loc_18000A60A
0x18000a5cc  inc     r8
0x18000a5cf  cmp     r8, r11
0x18000a5d2  jnb     loc_18000A68E
0x18000a5d8  test    r8b, 3
0x18000a5dc  jnz     short loc_18000A5C6
0x18000a5de  cmp     dword ptr [r8], 0
0x18000a5e2  mov     rax, r8
0x18000a5e5  jnz     short loc_18000A5F9
0x18000a5e7  add     rax, 4
0x18000a5eb  cmp     rax, r11
0x18000a5ee  jnb     loc_18000A68E
0x18000a5f4  cmp     dword ptr [rax], 0
0x18000a5f7  jz      short loc_18000A5E7
0x18000a5f9  cmp     byte ptr [rax], 0
0x18000a5fc  mov     r8, rax
0x18000a5ff  jnz     short loc_18000A60A
0x18000a601  inc     r8
0x18000a604  cmp     byte ptr [r8], 0
0x18000a608  jz      short loc_18000A601
0x18000a60a  cmp     r8, r11
0x18000a60d  jnb     short loc_18000A68E
0x18000a60f  movzx   eax, byte ptr [r8]
0x18000a613  mov     ecx, r8d
0x18000a616  sub     ecx, esi
0x18000a618  shl     ecx, 3
0x18000a61b  movzx   edx, byte ptr [rax+r15+43DF0h]
0x18000a624  movzx   eax, r10b
0x18000a628  sub     ecx, eax
0x18000a62a  mov     [r9], dl
0x18000a62d  add     ecx, edx
0x18000a62f  cmp     ecx, 0Bh
0x18000a632  jnb     short loc_18000A65D
0x18000a634  cmp     [rsp+20h+arg_28], 1
0x18000a639  jnz     short loc_18000A641
0x18000a63b  mov     dword ptr [rdi], 1
0x18000a641  movzx   eax, byte ptr [r8]
0x18000a645  mov     rsi, r8
0x18000a648  inc     r8
0x18000a64b  cmp     r8, r11
0x18000a64e  jnb     short loc_18000A68E
0x18000a650  mov     r10b, [rax+r15+1BCD0h]
0x18000a658  jmp     loc_18000A5BE
0x18000a65d  mov     rax, r8
0x18000a660  shl     r8b, 3
0x18000a664  and     r8b, 18h
0x18000a668  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000a66c  inc     r8b
0x18000a66f  mov     [rbx], rax
0x18000a672  add     [r9], r8b
0x18000a675  mov     cl, [r9]
0x18000a678  cmp     cl, 1Fh
0x18000a67b  jbe     short loc_18000A687
0x18000a67d  sub     cl, 20h ; ' '
0x18000a680  mov     [r9], cl
0x18000a683  add     qword ptr [rbx], 4
0x18000a687  mov     eax, 1
0x18000a68c  jmp     short loc_18000A690
0x18000a68e  xor     eax, eax
0x18000a690  pop     r15
0x18000a692  pop     rdi
0x18000a693  pop     rsi
0x18000a694  pop     rbx
0x18000a695  retn
```
