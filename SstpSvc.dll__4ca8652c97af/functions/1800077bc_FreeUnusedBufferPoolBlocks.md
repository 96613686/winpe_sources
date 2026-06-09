# FreeUnusedBufferPoolBlocks

- ea: `0x1800077bc`
- end: `0x18000785d`
- name: `FreeUnusedBufferPoolBlocks`
- size: `161`
- prototype: `void __fastcall(unsigned int *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001160`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002d70`
- `0x180002e00`
- `0x180008490`

## callees

- `0x1800077bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000783f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000783f`

## pseudocode

```c
void __fastcall FreeUnusedBufferPoolBlocks(unsigned int *a1)
{
  unsigned int *v1; // rbx
  unsigned int *v3; // r8
  unsigned int v4; // eax
  unsigned int *v5; // rsi
  unsigned int v6; // r9d
  __int64 *v7; // rdx
  __int64 *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  unsigned int *v11; // rcx

  v1 = a1 + 6;
  v3 = (unsigned int *)*((_QWORD *)a1 + 3);
  if ( v3 != a1 + 6 )
  {
    do
    {
      v4 = v3[6];
      v5 = *(unsigned int **)v3;
      if ( v3[7] >= v4 )
      {
        v6 = 0;
        v7 = (__int64 *)(v3 + 8);
        if ( v4 )
        {
          do
          {
            v8 = (__int64 *)v7[1];
            ++v6;
            v9 = *v7;
            *v8 = *v7;
            *(_QWORD *)(v9 + 8) = v8;
            v7[1] = (__int64)v7;
            *v7 = (__int64)v7;
            v7 = (__int64 *)((char *)v7 + *a1 + 24);
          }
          while ( v6 < v3[6] );
        }
        v10 = (_QWORD *)*((_QWORD *)v3 + 1);
        v11 = *(unsigned int **)v3;
        *v10 = *(_QWORD *)v3;
        *((_QWORD *)v11 + 1) = v10;
        LODWORD(v10) = v3[6];
        *((_QWORD *)v3 + 1) = v3;
        *(_QWORD *)v3 = v3;
        a1[3] -= (unsigned int)v10;
        HeapFree(*((HANDLE *)a1 + 7), 0, v3 - 4);
      }
      v3 = v5;
    }
    while ( v5 != v1 );
  }
}

```

## disassembly

```asm
0x1800077bc  mov     [rsp+arg_0], rbx
0x1800077c1  mov     [rsp+arg_8], rsi
0x1800077c6  push    rdi
0x1800077c7  sub     rsp, 20h
0x1800077cb  lea     rbx, [rcx+18h]
0x1800077cf  mov     rdi, rcx
0x1800077d2  mov     r8, [rbx]
0x1800077d5  cmp     r8, rbx
0x1800077d8  jz      short loc_18000784D
0x1800077da  mov     eax, [r8+18h]
0x1800077de  mov     rsi, [r8]
0x1800077e1  cmp     [r8+1Ch], eax
0x1800077e5  jb      short loc_180007845
0x1800077e7  xor     r9d, r9d
0x1800077ea  lea     rdx, [r8+20h]
0x1800077ee  test    eax, eax
0x1800077f0  jz      short loc_180007819
0x1800077f2  mov     rax, [rdx+8]
0x1800077f6  inc     r9d
0x1800077f9  mov     rcx, [rdx]
0x1800077fc  mov     [rax], rcx
0x1800077ff  mov     [rcx+8], rax
0x180007803  mov     [rdx+8], rdx
0x180007807  mov     [rdx], rdx
0x18000780a  mov     eax, [rdi]
0x18000780c  add     rax, 18h
0x180007810  add     rdx, rax
0x180007813  cmp     r9d, [r8+18h]
0x180007817  jb      short loc_1800077F2
0x180007819  mov     rax, [r8+8]
0x18000781d  xor     edx, edx; dwFlags
0x18000781f  mov     rcx, [r8]
0x180007822  mov     [rax], rcx
0x180007825  mov     [rcx+8], rax
0x180007829  mov     eax, [r8+18h]
0x18000782d  mov     [r8+8], r8
0x180007831  mov     [r8], r8
0x180007834  add     r8, 0FFFFFFFFFFFFFFF0h; lpMem
0x180007838  sub     [rdi+0Ch], eax
0x18000783b  mov     rcx, [rdi+38h]; hHeap
0x18000783f  call    cs:__imp_HeapFree
0x180007845  mov     r8, rsi
0x180007848  cmp     rsi, rbx
0x18000784b  jnz     short loc_1800077DA
0x18000784d  mov     rbx, [rsp+28h+arg_0]
0x180007852  mov     rsi, [rsp+28h+arg_8]
0x180007857  add     rsp, 20h
0x18000785b  pop     rdi
0x18000785c  retn
```
