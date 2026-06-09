# BfindOrCreateMatchingNode

- ea: `0x18000a97c`
- end: `0x18000aa80`
- name: `BfindOrCreateMatchingNode`
- size: `260`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, int, int, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0b0`
- `0x18000a45c`
- `0x18000ce0c`
- `0x18003eeb0`

## callees

- `0x180007150`
- `0x18000a97c`
- `0x18000aa88`

## string_xrefs

- `0x18000aa37`: `BfindOrCreateMatchingNode`
- `0x18000aa30`: `BfindOrCreateMatchingNode: this branch conflicts with the existing tree `

## pseudocode

```c
__int64 __fastcall BfindOrCreateMatchingNode(unsigned int a1, unsigned int *a2, int a3, int a4, __int64 a5)
{
  unsigned int v5; // ebp
  __int64 v9; // rbx
  unsigned int v10; // eax
  int v11; // edx

  v5 = a1;
  v9 = *(_QWORD *)(a5 + 72);
  if ( *(_DWORD *)(v9 + 20LL * a1) == a3 )
  {
    *a2 = a1;
    while ( *(_DWORD *)(v9 + 20LL * v5 + 4) != a4 )
    {
      v10 = *(_DWORD *)(v9 + 20LL * v5 + 8);
      if ( v10 == -1 )
      {
        if ( !(unsigned int)BallocElementFromMasterTable(3, a2, (_DWORD *)a5) )
          return 0;
        *(_DWORD *)(v9 + 20LL * *a2 + 8) = -1;
        v11 = *(_DWORD *)(v9 + 20LL * v5 + 4);
        *(_DWORD *)(v9 + 20LL * v5 + 8) = *a2;
        if ( v11 == -1 )
        {
          *(_DWORD *)(v9 + 20LL * *a2 + 4) = -1;
          *(_DWORD *)(v9 + 20LL * *a2 + 12) = *(_DWORD *)(v9 + 20LL * v5 + 12);
          *(_DWORD *)(v9 + 20LL * *a2) = *(_DWORD *)(v9 + 20LL * v5);
          *(_DWORD *)(v9 + 20LL * *a2 + 16) = *(_DWORD *)(v9 + 20LL * v5 + 16);
          *a2 = v5;
        }
        *(_DWORD *)(v9 + 20LL * *a2 + 4) = a4;
        *(_DWORD *)(v9 + 20LL * *a2) = a3;
        *(_DWORD *)(v9 + 20LL * *a2 + 16) = 2;
        return 1;
      }
      *a2 = v10;
      v5 = v10;
    }
    return 1;
  }
  else
  {
    WriteDbgTraceErrorGpd(
      (__int64)"BfindOrCreateMatchingNode",
      "BfindOrCreateMatchingNode: this branch conflicts with the existing tree ");
    return 0;
  }
}

```

## disassembly

```asm
0x18000a97c  push    rbx
0x18000a97e  push    rbp
0x18000a97f  push    rsi
0x18000a980  push    rdi
0x18000a981  push    r14
0x18000a983  push    r15
0x18000a985  sub     rsp, 28h
0x18000a989  mov     ebp, ecx
0x18000a98b  mov     r15d, r8d
0x18000a98e  mov     r8, [rsp+58h+arg_20]
0x18000a996  mov     r14d, r9d
0x18000a999  mov     rdi, rdx
0x18000a99c  lea     r10, ds:0[rbp*4]
0x18000a9a4  mov     rbx, [r8+48h]
0x18000a9a8  add     r10, rbp
0x18000a9ab  cmp     [rbx+r10*4], r15d
0x18000a9af  jnz     short loc_18000AA30
0x18000a9b1  mov     [rdx], ebp
0x18000a9b3  mov     eax, ebp
0x18000a9b5  lea     rsi, [rax+rax*4]
0x18000a9b9  cmp     [rbx+rsi*4+4], r14d
0x18000a9be  jz      short loc_18000AA1D
0x18000a9c0  mov     eax, [rbx+rsi*4+8]
0x18000a9c4  cmp     eax, 0FFFFFFFFh
0x18000a9c7  jz      short loc_18000A9CF
0x18000a9c9  mov     [rdx], eax
0x18000a9cb  mov     ebp, eax
0x18000a9cd  jmp     short loc_18000A9B3
0x18000a9cf  mov     ecx, 3
0x18000a9d4  call    BallocElementFromMasterTable
0x18000a9d9  test    eax, eax
0x18000a9db  jz      short loc_18000AA43
0x18000a9dd  mov     eax, [rdi]
0x18000a9df  lea     rcx, [rax+rax*4]
0x18000a9e3  mov     dword ptr [rbx+rcx*4+8], 0FFFFFFFFh
0x18000a9eb  mov     edx, [rbx+rsi*4+4]
0x18000a9ef  mov     eax, [rdi]
0x18000a9f1  mov     [rbx+rsi*4+8], eax
0x18000a9f5  cmp     edx, 0FFFFFFFFh
0x18000a9f8  jz      short loc_18000AA47
0x18000a9fa  mov     eax, [rdi]
0x18000a9fc  lea     rcx, [rax+rax*4]
0x18000aa00  mov     [rbx+rcx*4+4], r14d
0x18000aa05  mov     eax, [rdi]
0x18000aa07  lea     rcx, [rax+rax*4]
0x18000aa0b  mov     [rbx+rcx*4], r15d
0x18000aa0f  mov     eax, [rdi]
0x18000aa11  lea     rcx, [rax+rax*4]
0x18000aa15  mov     dword ptr [rbx+rcx*4+10h], 2
0x18000aa1d  mov     eax, 1
0x18000aa22  add     rsp, 28h
0x18000aa26  pop     r15
0x18000aa28  pop     r14
0x18000aa2a  pop     rdi
0x18000aa2b  pop     rsi
0x18000aa2c  pop     rbp
0x18000aa2d  pop     rbx
0x18000aa2e  retn
0x18000aa30  lea     rdx, aBfindorcreatem_0; "BfindOrCreateMatchingNode: this branch "...
0x18000aa37  lea     rcx, aBfindorcreatem; "BfindOrCreateMatchingNode"
0x18000aa3e  call    WriteDbgTraceErrorGpd
0x18000aa43  xor     eax, eax
0x18000aa45  jmp     short loc_18000AA22
0x18000aa47  mov     eax, [rdi]
0x18000aa49  lea     rcx, [rax+rax*4]
0x18000aa4d  mov     [rbx+rcx*4+4], edx
0x18000aa51  mov     eax, [rdi]
0x18000aa53  lea     rcx, [rax+rax*4]
0x18000aa57  mov     eax, [rbx+rsi*4+0Ch]
0x18000aa5b  mov     [rbx+rcx*4+0Ch], eax
0x18000aa5f  mov     eax, [rdi]
0x18000aa61  lea     rcx, [rax+rax*4]
0x18000aa65  mov     eax, [rbx+rsi*4]
0x18000aa68  mov     [rbx+rcx*4], eax
0x18000aa6b  mov     eax, [rdi]
0x18000aa6d  lea     rcx, [rax+rax*4]
0x18000aa71  mov     eax, [rbx+rsi*4+10h]
0x18000aa75  mov     [rbx+rcx*4+10h], eax
0x18000aa79  mov     [rdi], ebp
0x18000aa7b  jmp     loc_18000A9FA
```
