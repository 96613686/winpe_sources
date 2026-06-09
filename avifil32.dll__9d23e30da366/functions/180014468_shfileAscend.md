# shfileAscend

- ea: `0x180014468`
- end: `0x180014578`
- name: `shfileAscend`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800059c0`
- `0x1800067a0`
- `0x180009800`
- `0x18000a060`
- `0x18000b87c`
- `0x18000c410`
- `0x18000ca4c`
- `0x18000d0dc`

## callees

- `0x180014468`
- `0x180014928`
- `0x180014960`

## import_xrefs

- `WINMM!mmioSeek` at `0x1800144f4`
- `WINMM!mmioSeek` at `0x180014559`
- `WINMM!mmioSeek` at `0x1800144f4`
- `WINMM!mmioSeek` at `0x180014559`

## pseudocode

```c
__int64 __fastcall shfileAscend(__int64 a1, _DWORD *a2)
{
  int v4; // edi
  int v5; // edi
  int *v6; // r14
  int v7; // edx
  LONG v8; // edx
  __int64 v9; // rax
  LONG v10; // eax
  __int64 result; // rax
  __int64 v12; // rax
  LONG v13; // edx
  LONG v14; // edx

  if ( (a2[4] & 0x10000000) != 0 )
  {
    v4 = shfileSeek(a1, 0, 1);
    if ( v4 == -1 )
      return 263;
    v5 = v4 - a2[3];
    if ( v5 < 0 || (v5 & 1) != 0 && shfileWrite(a1, (char *)&dword_18001E6A4, 1u) != 1 )
      return 262;
    v6 = a2 + 1;
    if ( a2[1] == v5 )
      return 0;
    v7 = a2[3];
    *v6 = v5;
    v8 = v7 - 4;
    v9 = *(_QWORD *)(a1 + 16);
    if ( v9 )
    {
      *(_DWORD *)(v9 + 372) = v8;
      v10 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 372LL);
    }
    else
    {
      v10 = mmioSeek(*(HMMIO *)(a1 + 8), v8, 0);
    }
    if ( v10 == -1 )
      return 263;
    if ( shfileWrite(a1, (char *)a2 + 4, 4u) != 4 )
      return 262;
  }
  else
  {
    v6 = a2 + 1;
  }
  v12 = *(_QWORD *)(a1 + 16);
  v13 = *v6 + a2[3] + (*v6 & 1);
  if ( v12 )
  {
    *(_DWORD *)(v12 + 372) = v13;
    v14 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 372LL);
  }
  else
  {
    v14 = mmioSeek(*(HMMIO *)(a1 + 8), v13, 0);
  }
  result = 0;
  if ( v14 == -1 )
    return 263;
  return result;
}

```

## disassembly

```asm
0x180014468  push    rbx
0x18001446a  push    rsi
0x18001446b  push    rdi
0x18001446c  push    r14
0x18001446e  sub     rsp, 28h
0x180014472  test    dword ptr [rdx+10h], 10000000h
0x180014479  mov     rsi, rdx
0x18001447c  mov     rbx, rcx
0x18001447f  jz      loc_180014527
0x180014485  xor     edx, edx
0x180014487  lea     r8d, [rdx+1]
0x18001448b  call    shfileSeek
0x180014490  mov     edi, eax
0x180014492  cmp     eax, 0FFFFFFFFh
0x180014495  jz      loc_180014520
0x18001449b  sub     edi, [rsi+0Ch]
0x18001449e  js      short loc_180014515
0x1800144a0  test    dil, 1
0x1800144a4  jz      short loc_1800144C0
0x1800144a6  mov     r8d, 1
0x1800144ac  lea     rdx, dword_18001E6A4
0x1800144b3  mov     rcx, rbx
0x1800144b6  call    shfileWrite
0x1800144bb  cmp     eax, 1
0x1800144be  jnz     short loc_180014515
0x1800144c0  lea     r14, [rsi+4]
0x1800144c4  cmp     [r14], edi
0x1800144c7  jz      short loc_18001451C
0x1800144c9  mov     edx, [rsi+0Ch]
0x1800144cc  mov     [r14], edi
0x1800144cf  add     edx, 0FFFFFFFCh; lOffset
0x1800144d2  mov     rax, [rbx+10h]
0x1800144d6  test    rax, rax
0x1800144d9  jz      short loc_1800144ED
0x1800144db  mov     [rax+174h], edx
0x1800144e1  mov     rax, [rbx+10h]
0x1800144e5  mov     eax, [rax+174h]
0x1800144eb  jmp     short loc_1800144FA
0x1800144ed  mov     rcx, [rbx+8]; hmmio
0x1800144f1  xor     r8d, r8d; iOrigin
0x1800144f4  call    cs:__imp_mmioSeek
0x1800144fa  cmp     eax, 0FFFFFFFFh
0x1800144fd  jz      short loc_180014520
0x1800144ff  mov     r8d, 4
0x180014505  mov     rdx, r14
0x180014508  mov     rcx, rbx
0x18001450b  call    shfileWrite
0x180014510  cmp     eax, 4
0x180014513  jz      short loc_18001452B
0x180014515  mov     eax, 106h
0x18001451a  jmp     short loc_18001456E
0x18001451c  xor     eax, eax
0x18001451e  jmp     short loc_18001456E
0x180014520  mov     eax, 107h
0x180014525  jmp     short loc_18001456E
0x180014527  lea     r14, [rdx+4]
0x18001452b  mov     edx, [r14]
0x18001452e  mov     rax, [rbx+10h]
0x180014532  and     edx, 1
0x180014535  add     edx, [rsi+0Ch]
0x180014538  add     edx, [r14]; lOffset
0x18001453b  test    rax, rax
0x18001453e  jz      short loc_180014552
0x180014540  mov     [rax+174h], edx
0x180014546  mov     rax, [rbx+10h]
0x18001454a  mov     edx, [rax+174h]
0x180014550  jmp     short loc_180014561
0x180014552  mov     rcx, [rbx+8]; hmmio
0x180014556  xor     r8d, r8d; iOrigin
0x180014559  call    cs:__imp_mmioSeek
0x18001455f  mov     edx, eax
0x180014561  xor     eax, eax
0x180014563  mov     ecx, 107h
0x180014568  cmp     edx, 0FFFFFFFFh
0x18001456b  cmovz   eax, ecx
0x18001456e  add     rsp, 28h
0x180014572  pop     r14
0x180014574  pop     rdi
0x180014575  pop     rsi
0x180014576  pop     rbx
0x180014577  retn
```
