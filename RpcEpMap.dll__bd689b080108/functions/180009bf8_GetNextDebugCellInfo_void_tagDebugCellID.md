# GetNextDebugCellInfo(void *,tagDebugCellID *)

- ea: `0x180009bf8`
- end: `0x180009c9c`
- name: `?GetNextDebugCellInfo@@YAPEAUtagDebugCellUnion@@PEAXPEAUtagDebugCellID@@@Z`
- size: `164`
- prototype: `struct tagDebugCellUnion *__fastcall(_QWORD *, struct tagDebugCellID *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a50`
- `0x18000960c`
- `0x1800096c0`
- `0x180009ca4`

## callees

- `0x180009bf8`

## pseudocode

```c
struct tagDebugCellUnion *__fastcall GetNextDebugCellInfo(_QWORD *a1, struct tagDebugCellID *a2)
{
  __int64 v2; // r9
  unsigned __int64 v5; // r8
  unsigned int v6; // eax
  struct tagDebugCellUnion *i; // rdx
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rcx
  struct tagDebugCellUnion *result; // rax

  v2 = a1[1];
  v5 = *(_QWORD *)(v2 + 32) - 32LL + (unsigned int)(*(_DWORD *)(v2 + 24) * dword_180013B9C);
  v6 = *((_DWORD *)a1 + 4);
  if ( !v6 )
  {
    *((_DWORD *)a1 + 4) = 2;
    v6 = 2;
  }
  for ( i = (struct tagDebugCellUnion *)(*(_QWORD *)(v2 + 32) + 32LL * v6);
        ;
        i = (struct tagDebugCellUnion *)((char *)i + 32) )
  {
    while ( (unsigned __int64)i > v5 )
    {
      v8 = *(_QWORD *)(v2 + 40);
      if ( !v8 )
        return 0;
      v9 = dword_180013B9C;
      v2 = v8 - 40;
      a1[1] = v2;
      *((_DWORD *)a1 + 4) = 2;
      v10 = *(_QWORD *)(v2 + 32);
      i = (struct tagDebugCellUnion *)(v10 + 64);
      v5 = (unsigned int)(*(_DWORD *)(v2 + 24) * v9) + v10 - 32;
    }
    *((_WORD *)a2 + 1) = *((_WORD *)a1 + 8);
    ++*((_DWORD *)a1 + 4);
    if ( (unsigned __int8)(*(_BYTE *)i - 2) <= 3u )
      break;
  }
  result = i;
  *(_WORD *)a2 = *(_WORD *)(v2 + 28);
  return result;
}

```

## disassembly

```asm
0x180009bf8  mov     r9, [rcx+8]
0x180009bfc  mov     r11, rdx
0x180009bff  mov     r8d, cs:dword_180013B9C
0x180009c06  mov     r10, rcx
0x180009c09  imul    r8d, [r9+18h]
0x180009c0e  mov     rax, [r9+20h]
0x180009c12  add     rax, 0FFFFFFFFFFFFFFE0h
0x180009c16  add     r8, rax
0x180009c19  mov     eax, [rcx+10h]
0x180009c1c  test    eax, eax
0x180009c1e  jnz     short loc_180009C2C
0x180009c20  mov     dword ptr [rcx+10h], 2
0x180009c27  mov     eax, 2
0x180009c2c  mov     edx, eax
0x180009c2e  shl     rdx, 5
0x180009c32  add     rdx, [r9+20h]
0x180009c36  cmp     rdx, r8
0x180009c39  jbe     short loc_180009C70
0x180009c3b  mov     r9, [r9+28h]
0x180009c3f  test    r9, r9
0x180009c42  jz      short loc_180009C8C
0x180009c44  mov     eax, cs:dword_180013B9C
0x180009c4a  add     r9, 0FFFFFFFFFFFFFFD8h
0x180009c4e  mov     [r10+8], r9
0x180009c52  mov     dword ptr [r10+10h], 2
0x180009c5a  mov     rcx, [r9+20h]
0x180009c5e  imul    eax, [r9+18h]
0x180009c63  lea     r8, [rcx-20h]
0x180009c67  lea     rdx, [rcx+40h]
0x180009c6b  add     r8, rax
0x180009c6e  jmp     short loc_180009C36
0x180009c70  movzx   eax, word ptr [r10+10h]
0x180009c75  mov     [r11+2], ax
0x180009c7a  inc     dword ptr [r10+10h]
0x180009c7e  mov     al, [rdx]
0x180009c80  sub     al, 2
0x180009c82  cmp     al, 3
0x180009c84  jbe     short loc_180009C8F
0x180009c86  add     rdx, 20h ; ' '
0x180009c8a  jmp     short loc_180009C36
0x180009c8c  xor     eax, eax
0x180009c8e  retn
0x180009c8f  movzx   ecx, word ptr [r9+1Ch]
0x180009c94  mov     rax, rdx
0x180009c97  mov     [r11], cx
0x180009c9b  retn
```
