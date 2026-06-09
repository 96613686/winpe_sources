# BfindOrCreateMatchingNode

- ea: `0x18000a97c`
- end: `0x18000aa7f`
- name: `BfindOrCreateMatchingNode`
- size: `259`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0b8`
- `0x18000a460`
- `0x18000cdcc`
- `0x18003e020`

## callees

- `0x180007220`
- `0x18000a97c`
- `0x18000aa88`

## string_xrefs

- `0x18000aa36`: `BfindOrCreateMatchingNode`
- `0x18000aa2f`: `BfindOrCreateMatchingNode: this branch conflicts with the existing tree `

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
        if ( !(unsigned int)BallocElementFromMasterTable(3, a2, a5) )
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
      "BfindOrCreateMatchingNode",
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
0x18000a9af  jnz     short loc_18000AA2F
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
0x18000a9db  jz      short loc_18000AA42
0x18000a9dd  mov     eax, [rdi]
0x18000a9df  lea     rcx, [rax+rax*4]
0x18000a9e3  mov     dword ptr [rbx+rcx*4+8], 0FFFFFFFFh
0x18000a9eb  mov     edx, [rbx+rsi*4+4]
0x18000a9ef  mov     eax, [rdi]
0x18000a9f1  mov     [rbx+rsi*4+8], eax
0x18000a9f5  cmp     edx, 0FFFFFFFFh
0x18000a9f8  jz      short loc_18000AA46
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
0x18000aa2f  lea     rdx, aBfindorcreatem_0; "BfindOrCreateMatchingNode: this branch "...
0x18000aa36  lea     rcx, aBfindorcreatem; "BfindOrCreateMatchingNode"
0x18000aa3d  call    WriteDbgTraceErrorGpd
0x18000aa42  xor     eax, eax
0x18000aa44  jmp     short loc_18000AA22
0x18000aa46  mov     eax, [rdi]
0x18000aa48  lea     rcx, [rax+rax*4]
0x18000aa4c  mov     [rbx+rcx*4+4], edx
0x18000aa50  mov     eax, [rdi]
0x18000aa52  lea     rcx, [rax+rax*4]
0x18000aa56  mov     eax, [rbx+rsi*4+0Ch]
0x18000aa5a  mov     [rbx+rcx*4+0Ch], eax
0x18000aa5e  mov     eax, [rdi]
0x18000aa60  lea     rcx, [rax+rax*4]
0x18000aa64  mov     eax, [rbx+rsi*4]
0x18000aa67  mov     [rbx+rcx*4], eax
0x18000aa6a  mov     eax, [rdi]
0x18000aa6c  lea     rcx, [rax+rax*4]
0x18000aa70  mov     eax, [rbx+rsi*4+10h]
0x18000aa74  mov     [rbx+rcx*4+10h], eax
0x18000aa78  mov     [rdi], ebp
0x18000aa7a  jmp     loc_18000A9FA
```
