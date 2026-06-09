# shfileCreateChunk

- ea: `0x180014600`
- end: `0x18001468b`
- name: `shfileCreateChunk`
- size: `139`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800067a0`
- `0x180009800`
- `0x18000b87c`
- `0x18000c410`
- `0x18000ca4c`

## callees

- `0x180014600`
- `0x180014928`
- `0x180014960`

## pseudocode

```c
__int64 __fastcall shfileCreateChunk(__int64 a1, __int64 a2, char a3)
{
  int v6; // eax
  unsigned int v8; // ebx

  v6 = shfileSeek(a1, 0, 1);
  if ( v6 == -1 )
    return 263;
  *(_DWORD *)(a2 + 12) = v6 + 8;
  if ( (a3 & 0x20) != 0 )
  {
    *(_DWORD *)a2 = 1179011410;
LABEL_7:
    v8 = 12;
    goto LABEL_9;
  }
  if ( (a3 & 0x40) != 0 )
  {
    *(_DWORD *)a2 = 1414744396;
    goto LABEL_7;
  }
  v8 = 8;
LABEL_9:
  if ( shfileWrite(a1, (char *)a2, v8) != v8 )
    return 262;
  *(_DWORD *)(a2 + 16) = 0x10000000;
  return 0;
}

```

## disassembly

```asm
0x180014600  mov     [rsp+arg_0], rbx
0x180014605  mov     [rsp+arg_8], rsi
0x18001460a  push    rdi
0x18001460b  sub     rsp, 20h
0x18001460f  mov     rdi, rdx
0x180014612  mov     ebx, r8d
0x180014615  xor     edx, edx
0x180014617  mov     rsi, rcx
0x18001461a  lea     r8d, [rdx+1]
0x18001461e  call    shfileSeek
0x180014623  cmp     eax, 0FFFFFFFFh
0x180014626  jnz     short loc_18001462F
0x180014628  mov     eax, 107h
0x18001462d  jmp     short loc_18001467B
0x18001462f  add     eax, 8
0x180014632  mov     [rdi+0Ch], eax
0x180014635  test    bl, 20h
0x180014638  jz      short loc_180014642
0x18001463a  mov     dword ptr [rdi], 46464952h
0x180014640  jmp     short loc_18001464D
0x180014642  test    bl, 40h
0x180014645  jz      short loc_180014654
0x180014647  mov     dword ptr [rdi], 5453494Ch
0x18001464d  mov     ebx, 0Ch
0x180014652  jmp     short loc_180014659
0x180014654  mov     ebx, 8
0x180014659  mov     r8d, ebx
0x18001465c  mov     rdx, rdi
0x18001465f  mov     rcx, rsi
0x180014662  call    shfileWrite
0x180014667  cmp     eax, ebx
0x180014669  jz      short loc_180014672
0x18001466b  mov     eax, 106h
0x180014670  jmp     short loc_18001467B
0x180014672  mov     dword ptr [rdi+10h], 10000000h
0x180014679  xor     eax, eax
0x18001467b  mov     rbx, [rsp+28h+arg_0]
0x180014680  mov     rsi, [rsp+28h+arg_8]
0x180014685  add     rsp, 20h
0x180014689  pop     rdi
0x18001468a  retn
```
