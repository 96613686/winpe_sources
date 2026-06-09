# computeLimitRegisters

- ea: `0x180013570`
- end: `0x1800136db`
- name: `computeLimitRegisters`
- size: `363`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180037194`
- `0x180043968`
- `0x180044538`
- `0x180070c50`

## callees

- `0x180010810`
- `0x1800119e0`
- `0x180013570`
- `0x1800136e4`
- `0x180014360`
- `0x1800573d8`

## pseudocode

```c
void __fastcall computeLimitRegisters(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // rbp
  unsigned int v7; // r15d
  int Vdbe; // r12d
  __int64 v9; // r14
  __int16 v10; // ax
  unsigned int v11; // r8d
  int v12; // edx
  unsigned int v13; // edi
  int v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = 0;
  if ( !*(_DWORD *)(a2 + 8) )
  {
    v6 = *(_QWORD *)(a2 + 96);
    if ( v6 )
    {
      v7 = ++*(_DWORD *)(a1 + 60);
      *(_DWORD *)(a2 + 8) = v7;
      Vdbe = sqlite3GetVdbe();
      if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v6 + 16), &v14, a1) )
      {
        v9 = v14;
        sqlite3VdbeAddOp3(Vdbe, 71, v14, v7, 0);
        if ( (_DWORD)v9 )
        {
          if ( (int)v9 >= 0 )
          {
            v10 = sqlite3LogEst(v9);
            if ( *(__int16 *)(a2 + 2) > v10 )
            {
              *(_DWORD *)(a2 + 4) |= 0x4000u;
              *(_WORD *)(a2 + 2) = v10;
            }
          }
          goto LABEL_8;
        }
        v11 = 0;
        v12 = 9;
      }
      else
      {
        sqlite3ExprCode(a1, *(_QWORD *)(v6 + 16), v7);
        sqlite3VdbeAddOp3(Vdbe, 13, v7, 0, 0);
        v11 = v7;
        v12 = 17;
      }
      sqlite3VdbeAddOp3(Vdbe, v12, v11, a3, 0);
LABEL_8:
      if ( *(_QWORD *)(v6 + 24) )
      {
        v13 = *(_DWORD *)(a1 + 60) + 1;
        *(_DWORD *)(a1 + 60) = v13;
        *(_DWORD *)(a2 + 12) = v13;
        ++*(_DWORD *)(a1 + 60);
        sqlite3ExprCode(a1, *(_QWORD *)(v6 + 24), v13);
        sqlite3VdbeAddOp3(Vdbe, 13, v13, 0, 0);
        sqlite3VdbeAddOp3(Vdbe, 160, v7, v13 + 1, v13);
      }
    }
  }
}

```

## disassembly

```asm
0x180013570  push    rbx
0x180013572  push    rsi
0x180013573  push    rdi
0x180013574  push    r13
0x180013576  sub     rsp, 38h
0x18001357a  xor     r13d, r13d
0x18001357d  mov     edi, r8d
0x180013580  mov     rbx, rdx
0x180013583  mov     rsi, rcx
0x180013586  mov     [rsp+58h+arg_8], r13d
0x18001358b  cmp     [rdx+8], r13d
0x18001358f  jz      short loc_18001359B
0x180013591  add     rsp, 38h
0x180013595  pop     r13
0x180013597  pop     rdi
0x180013598  pop     rsi
0x180013599  pop     rbx
0x18001359a  retn
0x18001359b  mov     [rsp+58h+arg_0], rbp
0x1800135a0  mov     rbp, [rdx+60h]
0x1800135a4  test    rbp, rbp
0x1800135a7  jnz     short loc_1800135B0
0x1800135a9  mov     rbp, [rsp+58h+arg_0]
0x1800135ae  jmp     short loc_180013591
0x1800135b0  inc     dword ptr [rcx+3Ch]
0x1800135b3  mov     [rsp+58h+arg_10], r12
0x1800135b8  mov     [rsp+58h+var_28], r15
0x1800135bd  mov     r15d, [rcx+3Ch]
0x1800135c1  mov     [rdx+8], r15d
0x1800135c5  mov     [rsp+58h+arg_18], r14
0x1800135ca  call    sqlite3GetVdbe
0x1800135cf  mov     rcx, [rbp+10h]
0x1800135d3  lea     rdx, [rsp+58h+arg_8]
0x1800135d8  mov     r8, rsi
0x1800135db  mov     r12, rax
0x1800135de  call    sqlite3ExprIsInteger
0x1800135e3  test    eax, eax
0x1800135e5  jz      short loc_180013658
0x1800135e7  movsxd  r14, [rsp+58h+arg_8]
0x1800135ec  mov     r9d, r15d
0x1800135ef  mov     r8d, r14d
0x1800135f2  mov     [rsp+58h+var_38], r13d
0x1800135f7  mov     edx, 47h ; 'G'
0x1800135fc  mov     rcx, r12
0x1800135ff  call    sqlite3VdbeAddOp3
0x180013604  test    r14d, r14d
0x180013607  jz      short loc_18001363E
0x180013609  js      short loc_180013624
0x18001360b  mov     rcx, r14
0x18001360e  call    sqlite3LogEst
0x180013613  cmp     [rbx+2], ax
0x180013617  jle     short loc_180013624
0x180013619  or      dword ptr [rbx+4], 4000h
0x180013620  mov     [rbx+2], ax
0x180013624  mov     r14, [rsp+58h+arg_18]
0x180013629  cmp     [rbp+18h], r13
0x18001362d  jnz     short loc_180013689
0x18001362f  mov     r12, [rsp+58h+arg_10]
0x180013634  mov     r15, [rsp+58h+var_28]
0x180013639  jmp     loc_1800135A9
0x18001363e  xor     r8d, r8d
0x180013641  mov     edx, 9
0x180013646  mov     r9d, edi
0x180013649  mov     [rsp+58h+var_38], r13d
0x18001364e  mov     rcx, r12
0x180013651  call    sqlite3VdbeAddOp3
0x180013656  jmp     short loc_180013624
0x180013658  mov     rdx, [rbp+10h]
0x18001365c  mov     r8d, r15d
0x18001365f  mov     rcx, rsi
0x180013662  call    sqlite3ExprCode
0x180013667  xor     r9d, r9d
0x18001366a  mov     [rsp+58h+var_38], r13d
0x18001366f  mov     r8d, r15d
0x180013672  mov     edx, 0Dh
0x180013677  mov     rcx, r12
0x18001367a  call    sqlite3VdbeAddOp3
0x18001367f  mov     r8d, r15d
0x180013682  mov     edx, 11h
0x180013687  jmp     short loc_180013646
0x180013689  mov     edi, [rsi+3Ch]
0x18001368c  mov     rcx, rsi
0x18001368f  inc     edi
0x180013691  mov     [rsi+3Ch], edi
0x180013694  mov     r8d, edi
0x180013697  mov     [rbx+0Ch], edi
0x18001369a  inc     dword ptr [rsi+3Ch]
0x18001369d  mov     rdx, [rbp+18h]
0x1800136a1  call    sqlite3ExprCode
0x1800136a6  xor     r9d, r9d
0x1800136a9  mov     [rsp+58h+var_38], r13d
0x1800136ae  mov     r8d, edi
0x1800136b1  mov     edx, 0Dh
0x1800136b6  mov     rcx, r12
0x1800136b9  call    sqlite3VdbeAddOp3
0x1800136be  lea     r9d, [rdi+1]
0x1800136c2  mov     [rsp+58h+var_38], edi
0x1800136c6  mov     r8d, r15d
0x1800136c9  mov     edx, 0A0h
0x1800136ce  mov     rcx, r12
0x1800136d1  call    sqlite3VdbeAddOp3
0x1800136d6  jmp     loc_18001362F
```
