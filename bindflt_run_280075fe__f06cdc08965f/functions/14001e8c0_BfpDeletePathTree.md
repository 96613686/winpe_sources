# BfpDeletePathTree

- ea: `0x14001e8c0`
- end: `0x14001e992`
- name: `BfpDeletePathTree`
- size: `210`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e818`
- `0x14001e854`
- `0x14002001c`
- `0x140020228`

## callees

- `0x14001e818`
- `0x14001e8c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e90d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e90d`

## pseudocode

```c
void __fastcall BfpDeletePathTree(unsigned __int64 P, __int64 a2)
{
  bool v2; // zf
  unsigned __int64 v4; // rcx
  int v6; // esi
  char v7; // al
  unsigned __int64 v8; // rax
  _QWORD *v9; // rdx
  unsigned __int64 v10; // rdi

  v2 = (*(_BYTE *)(P + 8) & 1) == 0;
  v4 = *(_QWORD *)P;
  if ( !v2 && v4 )
    v4 ^= P;
  v6 = *(_BYTE *)(P + 8) & 1;
  if ( v4 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v8 = *(_QWORD *)v4;
        if ( !*(_QWORD *)v4 )
          break;
        v9 = (_QWORD *)v4;
LABEL_12:
        if ( v6 )
          v4 ^= v8;
        else
          v4 = v8;
        *v9 = 0;
      }
      v9 = (_QWORD *)(v4 + 8);
      v8 = *(_QWORD *)(v4 + 8);
      if ( v8 )
        goto LABEL_12;
      v10 = *(_QWORD *)(v4 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v6 && v10 )
        v10 ^= v4;
      BfpRBTreeDeletePathTierNode(v4, a2);
      if ( !v10 )
        break;
      v4 = v10;
    }
  }
  v7 = *(_BYTE *)(P + 8);
  *(_QWORD *)P = 0;
  *(_QWORD *)(P + 8) = 0;
  if ( (v7 & 1) != 0 )
    *(_BYTE *)(P + 8) = 1;
  ExFreePoolWithTag((PVOID)P, 0x706D4642u);
}

```

## disassembly

```asm
0x14001e8c0  push    rbx
0x14001e8c2  push    rbp
0x14001e8c3  push    rsi
0x14001e8c4  push    rdi
0x14001e8c5  sub     rsp, 28h
0x14001e8c9  test    byte ptr [rcx+8], 1
0x14001e8cd  mov     rbx, rcx
0x14001e8d0  mov     rcx, [rcx]
0x14001e8d3  mov     rbp, rdx
0x14001e8d6  jnz     loc_14001E977
0x14001e8dc  movzx   esi, byte ptr [rbx+8]
0x14001e8e0  and     esi, 1
0x14001e8e3  test    rcx, rcx
0x14001e8e6  jnz     short loc_14001E923
0x14001e8e8  movzx   eax, byte ptr [rbx+8]
0x14001e8ec  mov     qword ptr [rbx], 0
0x14001e8f3  mov     qword ptr [rbx+8], 0
0x14001e8fb  bt      eax, 0
0x14001e8ff  jb      loc_14001E989
0x14001e905  mov     edx, 706D4642h; Tag
0x14001e90a  mov     rcx, rbx; P
0x14001e90d  call    cs:__imp_ExFreePoolWithTag
0x14001e914  nop     dword ptr [rax+rax+00h]
0x14001e919  add     rsp, 28h
0x14001e91d  pop     rdi
0x14001e91e  pop     rsi
0x14001e91f  pop     rbp
0x14001e920  pop     rbx
0x14001e921  retn
0x14001e923  mov     rax, [rcx]
0x14001e926  test    rax, rax
0x14001e929  jnz     short loc_14001E955
0x14001e92b  lea     rdx, [rcx+8]
0x14001e92f  mov     rax, [rdx]
0x14001e932  test    rax, rax
0x14001e935  jnz     short loc_14001E958
0x14001e937  mov     rdi, [rcx+10h]
0x14001e93b  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14001e93f  test    esi, esi
0x14001e941  jnz     short loc_14001E96D
0x14001e943  mov     rdx, rbp
0x14001e946  call    BfpRBTreeDeletePathTierNode
0x14001e94b  test    rdi, rdi
0x14001e94e  jz      short loc_14001E8E8
0x14001e950  mov     rcx, rdi
0x14001e953  jmp     short loc_14001E923
0x14001e955  mov     rdx, rcx
0x14001e958  test    esi, esi
0x14001e95a  jnz     short loc_14001E968
0x14001e95c  mov     rcx, rax
0x14001e95f  mov     qword ptr [rdx], 0
0x14001e966  jmp     short loc_14001E923
0x14001e968  xor     rcx, rax
0x14001e96b  jmp     short loc_14001E95F
0x14001e96d  test    rdi, rdi
0x14001e970  jz      short loc_14001E943
0x14001e972  xor     rdi, rcx
0x14001e975  jmp     short loc_14001E943
0x14001e977  test    rcx, rcx
0x14001e97a  jz      short loc_14001E984
0x14001e97c  xor     rcx, rbx
0x14001e97f  jmp     loc_14001E8DC
0x14001e984  jmp     loc_14001E8DC
0x14001e989  mov     byte ptr [rbx+8], 1
0x14001e98d  jmp     loc_14001E905
```
