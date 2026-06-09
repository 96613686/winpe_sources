# BfpCanRemoveMapping

- ea: `0x14000f544`
- end: `0x14000f600`
- name: `BfpCanRemoveMapping`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f3d0`
- `0x14000f544`

## callees

- `0x14000f544`
- `0x140017bb8`

## pseudocode

```c
__int64 __fastcall BfpCanRemoveMapping(__int64 a1, _BYTE *a2)
{
  int v2; // eax
  __int64 v5; // rdi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  char v9; // dl

  v2 = *(_DWORD *)(a1 - 8);
  if ( (v2 & 1) != 0 )
  {
    *a2 = 0;
    return 0;
  }
  if ( (v2 & 2) == 0 )
  {
    v5 = *(_QWORD *)(a1 + 72);
    if ( !BfpPathTreeEmpty(v5) )
    {
      v6 = *(_QWORD *)v5;
      if ( *(_QWORD *)v5 )
      {
        while ( 1 )
        {
          if ( (int)BfpCanRemoveMapping(v6, a2) < 0 )
            return 0;
          v7 = *(_QWORD *)v6;
          if ( !*(_QWORD *)v6 )
          {
            v7 = *(_QWORD *)(v6 + 8);
            if ( !v7 )
              break;
          }
          if ( (*(_BYTE *)(v5 + 8) & 1) != 0 )
            v6 ^= v7;
          else
LABEL_23:
            v6 = v7;
        }
        v8 = v6;
        v9 = *(_BYTE *)(v5 + 8) & 1;
        while ( 1 )
        {
          v8 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v9 )
          {
            if ( !v8 )
              return 0;
            v8 ^= v6;
          }
          if ( !v8 )
            return 0;
          v7 = *(_QWORD *)(v8 + 8);
          if ( v9 )
          {
            if ( !v7 )
              goto LABEL_22;
            v7 ^= v8;
          }
          if ( v7 && v7 != v6 )
            goto LABEL_23;
LABEL_22:
          v6 = v8;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000f544  mov     [rsp+arg_0], rbx
0x14000f549  mov     [rsp+arg_8], rsi
0x14000f54e  push    rdi
0x14000f54f  sub     rsp, 20h
0x14000f553  mov     eax, [rcx-8]
0x14000f556  mov     rsi, rdx
0x14000f559  test    al, 1
0x14000f55b  jz      short loc_14000F573
0x14000f55d  mov     byte ptr [rdx], 0
0x14000f560  mov     rbx, [rsp+28h+arg_0]
0x14000f565  xor     eax, eax
0x14000f567  mov     rsi, [rsp+28h+arg_8]
0x14000f56c  add     rsp, 20h
0x14000f570  pop     rdi
0x14000f571  retn
0x14000f573  test    al, 2
0x14000f575  jnz     short loc_14000F560
0x14000f577  mov     rdi, [rcx+48h]
0x14000f57b  mov     rcx, rdi
0x14000f57e  call    BfpPathTreeEmpty
0x14000f583  test    al, al
0x14000f585  jnz     short loc_14000F560
0x14000f587  mov     rbx, [rdi]
0x14000f58a  test    rbx, rbx
0x14000f58d  jz      short loc_14000F560
0x14000f58f  mov     rdx, rsi
0x14000f592  mov     rcx, rbx
0x14000f595  call    BfpCanRemoveMapping
0x14000f59a  test    eax, eax
0x14000f59c  js      short loc_14000F560
0x14000f59e  mov     rcx, [rbx]
0x14000f5a1  test    rcx, rcx
0x14000f5a4  jz      short loc_14000F5B1
0x14000f5a6  test    byte ptr [rdi+8], 1
0x14000f5aa  jz      short loc_14000F5FB
0x14000f5ac  xor     rbx, rcx
0x14000f5af  jmp     short loc_14000F58F
0x14000f5b1  mov     rcx, [rbx+8]
0x14000f5b5  test    rcx, rcx
0x14000f5b8  jnz     short loc_14000F5A6
0x14000f5ba  mov     dl, [rdi+8]
0x14000f5bd  mov     rax, rbx
0x14000f5c0  and     dl, 1
0x14000f5c3  mov     rax, [rax+10h]
0x14000f5c7  and     rax, 0FFFFFFFFFFFFFFFCh
0x14000f5cb  test    dl, dl
0x14000f5cd  jz      short loc_14000F5D7
0x14000f5cf  test    rax, rax
0x14000f5d2  jz      short loc_14000F560
0x14000f5d4  xor     rax, rbx
0x14000f5d7  test    rax, rax
0x14000f5da  jz      short loc_14000F560
0x14000f5dc  mov     rcx, [rax+8]
0x14000f5e0  test    dl, dl
0x14000f5e2  jz      short loc_14000F5EC
0x14000f5e4  test    rcx, rcx
0x14000f5e7  jz      short loc_14000F5F6
0x14000f5e9  xor     rcx, rax
0x14000f5ec  test    rcx, rcx
0x14000f5ef  jz      short loc_14000F5F6
0x14000f5f1  cmp     rcx, rbx
0x14000f5f4  jnz     short loc_14000F5FB
0x14000f5f6  mov     rbx, rax
0x14000f5f9  jmp     short loc_14000F5C3
0x14000f5fb  mov     rbx, rcx
0x14000f5fe  jmp     short loc_14000F58F
```
