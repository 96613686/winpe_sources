# computeLimitRegisters

- ea: `0x180014034`
- end: `0x180014262`
- name: `computeLimitRegisters`
- size: `558`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005650`
- `0x1800658bc`
- `0x1800711f4`
- `0x180080260`

## callees

- `0x18000d04c`
- `0x180013fac`
- `0x180014034`
- `0x180015eb0`
- `0x1800168c0`

## pseudocode

```c
void __fastcall computeLimitRegisters(__int64 a1, __int64 a2, int a3)
{
  bool v3; // zf
  __int64 v7; // r14
  unsigned int v8; // r12d
  int Vdbe; // r15d
  unsigned __int64 v10; // rbx
  __int16 v11; // dx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int16 v14; // dx
  __int16 v15; // cx
  __int16 v16; // cx
  unsigned int v17; // ebx
  unsigned int v18; // r8d
  int v19; // edx
  int v20; // [rsp+68h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a2 + 8) == 0;
  v20 = 0;
  if ( v3 )
  {
    v7 = *(_QWORD *)(a2 + 96);
    if ( v7 )
    {
      v8 = ++*(_DWORD *)(a1 + 56);
      *(_DWORD *)(a2 + 8) = v8;
      Vdbe = sqlite3GetVdbe();
      if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v7 + 16), &v20) )
      {
        v10 = v20;
        sqlite3VdbeAddOp3(Vdbe, 71, v20, v8, 0);
        if ( (_DWORD)v10 )
        {
          if ( (v10 & 0x80000000) != 0LL )
            goto LABEL_14;
          v11 = 40;
          v12 = v10;
          v13 = v10;
          if ( v10 >= 8 )
          {
            if ( v10 > 0xFF )
            {
              do
              {
                v11 += 40;
                v13 >>= 4;
              }
              while ( v13 > 0xFF );
            }
            while ( v13 > 0xF )
            {
              v11 += 10;
              v13 >>= 1;
            }
          }
          else
          {
            if ( v10 < 2 )
            {
              v14 = 0;
              goto LABEL_9;
            }
            do
            {
              v11 -= 10;
              v13 *= 2LL;
            }
            while ( v13 < 8 );
          }
          v14 = *((_WORD *)qword_1800BE458 + (v13 & 7)) + v11 - 10;
LABEL_9:
          if ( *(__int16 *)(a2 + 2) <= v14 )
            goto LABEL_14;
          v15 = 40;
          if ( v10 >= 8 )
          {
            while ( v12 > 0xFF )
            {
              v15 += 40;
              v12 >>= 4;
            }
            while ( v12 > 0xF )
            {
              v15 += 10;
              v12 >>= 1;
            }
          }
          else
          {
            if ( v10 < 2 )
            {
              v16 = 0;
LABEL_13:
              *(_DWORD *)(a2 + 4) |= 0x4000u;
              *(_WORD *)(a2 + 2) = v16;
              goto LABEL_14;
            }
            do
            {
              v15 -= 10;
              v12 *= 2LL;
            }
            while ( v12 < 8 );
          }
          v16 = *((_WORD *)qword_1800BE458 + (v12 & 7)) + v15 - 10;
          goto LABEL_13;
        }
        v18 = 0;
        v19 = 9;
      }
      else
      {
        sqlite3ExprCode(a1, *(_QWORD *)(v7 + 16), v8);
        sqlite3VdbeAddOp3(Vdbe, 13, v8, 0, 0);
        v18 = v8;
        v19 = 17;
      }
      sqlite3VdbeAddOp3(Vdbe, v19, v18, a3, 0);
LABEL_14:
      if ( *(_QWORD *)(v7 + 24) )
      {
        v17 = *(_DWORD *)(a1 + 56) + 1;
        *(_DWORD *)(a1 + 56) = v17;
        *(_DWORD *)(a2 + 12) = v17;
        ++*(_DWORD *)(a1 + 56);
        sqlite3ExprCode(a1, *(_QWORD *)(v7 + 24), v17);
        sqlite3VdbeAddOp3(Vdbe, 13, v17, 0, 0);
        sqlite3VdbeAddOp3(Vdbe, 160, v8, v17 + 1, v17);
      }
    }
  }
}

```

## disassembly

```asm
0x180014034  mov     [rsp+arg_0], rbx
0x180014039  mov     [rsp+arg_10], rbp
0x18001403e  push    rsi
0x18001403f  push    rdi
0x180014040  push    r12
0x180014042  push    r14
0x180014044  push    r15
0x180014046  sub     rsp, 30h
0x18001404a  cmp     dword ptr [rdx+8], 0
0x18001404e  mov     esi, r8d
0x180014051  mov     rdi, rdx
0x180014054  mov     [rsp+58h+arg_8], 0
0x18001405c  mov     rbp, rcx
0x18001405f  jnz     loc_180014125
0x180014065  mov     r14, [rdx+60h]
0x180014069  test    r14, r14
0x18001406c  jz      loc_180014125
0x180014072  inc     dword ptr [rcx+38h]
0x180014075  mov     r12d, [rcx+38h]
0x180014079  mov     [rdx+8], r12d
0x18001407d  call    sqlite3GetVdbe
0x180014082  mov     rcx, [r14+10h]
0x180014086  lea     rdx, [rsp+58h+arg_8]
0x18001408b  mov     r15, rax
0x18001408e  call    sqlite3ExprIsInteger
0x180014093  test    eax, eax
0x180014095  jz      loc_18001422F
0x18001409b  movsxd  rbx, [rsp+58h+arg_8]
0x1800140a0  mov     r9d, r12d
0x1800140a3  mov     r8d, ebx
0x1800140a6  mov     [rsp+58h+var_38], 0
0x1800140ae  mov     edx, 47h ; 'G'
0x1800140b3  mov     rcx, r15
0x1800140b6  call    sqlite3VdbeAddOp3
0x1800140bb  test    ebx, ebx
0x1800140bd  jz      loc_1800141EC
0x1800140c3  js      short loc_18001411E
0x1800140c5  lea     r11, qword_1800BE458
0x1800140cc  mov     r9d, 28h ; '('
0x1800140d2  movzx   edx, r9w
0x1800140d6  mov     rax, rbx
0x1800140d9  mov     rcx, rbx
0x1800140dc  mov     r8d, 0FFh
0x1800140e2  mov     r10w, 0Ah
0x1800140e7  cmp     rbx, 8
0x1800140eb  jnb     short loc_180014166
0x1800140ed  cmp     rax, 2
0x1800140f1  jnb     loc_18001420B
0x1800140f7  xor     edx, edx
0x1800140f9  cmp     [rdi+2], dx
0x1800140fd  jle     short loc_18001411E
0x1800140ff  movzx   ecx, r9w
0x180014103  cmp     rax, 8
0x180014107  jnb     short loc_180014144
0x180014109  cmp     rax, 2
0x18001410d  jnb     loc_18001421D
0x180014113  xor     ecx, ecx
0x180014115  bts     dword ptr [rdi+4], 0Eh
0x18001411a  mov     [rdi+2], cx
0x18001411e  cmp     qword ptr [r14+18h], 0
0x180014123  jnz     short loc_180014198
0x180014125  mov     rbx, [rsp+58h+arg_0]
0x18001412a  mov     rbp, [rsp+58h+arg_10]
0x18001412f  add     rsp, 30h
0x180014133  pop     r15
0x180014135  pop     r14
0x180014137  pop     r12
0x180014139  pop     rdi
0x18001413a  pop     rsi
0x18001413b  retn
0x18001413c  add     cx, r9w
0x180014140  shr     rax, 4
0x180014144  cmp     rax, r8
0x180014147  ja      short loc_18001413C
0x180014149  jmp     short loc_180014152
0x18001414b  add     cx, r10w
0x18001414f  shr     rax, 1
0x180014152  cmp     rax, 0Fh
0x180014156  ja      short loc_18001414B
0x180014158  and     eax, 7
0x18001415b  add     cx, [r11+rax*2]
0x180014160  sub     cx, r10w
0x180014164  jmp     short loc_180014115
0x180014166  cmp     rax, r8
0x180014169  jbe     short loc_180014181
0x18001416b  add     dx, r9w
0x18001416f  shr     rcx, 4
0x180014173  cmp     rcx, r8
0x180014176  jbe     short loc_180014181
0x180014178  jmp     short loc_18001416B
0x18001417a  add     dx, r10w
0x18001417e  shr     rcx, 1
0x180014181  cmp     rcx, 0Fh
0x180014185  ja      short loc_18001417A
0x180014187  and     ecx, 7
0x18001418a  add     dx, [r11+rcx*2]
0x18001418f  sub     dx, r10w
0x180014193  jmp     loc_1800140F9
0x180014198  mov     ebx, [rbp+38h]
0x18001419b  mov     rcx, rbp
0x18001419e  inc     ebx
0x1800141a0  mov     [rbp+38h], ebx
0x1800141a3  mov     r8d, ebx
0x1800141a6  mov     [rdi+0Ch], ebx
0x1800141a9  inc     dword ptr [rbp+38h]
0x1800141ac  mov     rdx, [r14+18h]
0x1800141b0  call    sqlite3ExprCode
0x1800141b5  xor     r9d, r9d
0x1800141b8  mov     [rsp+58h+var_38], 0
0x1800141c0  mov     r8d, ebx
0x1800141c3  mov     rcx, r15
0x1800141c6  lea     edx, [r9+0Dh]
0x1800141ca  call    sqlite3VdbeAddOp3
0x1800141cf  lea     r9d, [rbx+1]
0x1800141d3  mov     [rsp+58h+var_38], ebx
0x1800141d7  mov     r8d, r12d
0x1800141da  mov     edx, 0A0h
0x1800141df  mov     rcx, r15
0x1800141e2  call    sqlite3VdbeAddOp3
0x1800141e7  jmp     loc_180014125
0x1800141ec  xor     r8d, r8d
0x1800141ef  lea     edx, [r8+9]
0x1800141f3  mov     r9d, esi
0x1800141f6  mov     [rsp+58h+var_38], 0
0x1800141fe  mov     rcx, r15
0x180014201  call    sqlite3VdbeAddOp3
0x180014206  jmp     loc_18001411E
0x18001420b  add     dx, 0FFF6h
0x18001420f  add     rcx, rcx
0x180014212  cmp     rcx, 8
0x180014216  jb      short loc_18001420B
0x180014218  jmp     loc_180014187
0x18001421d  add     cx, 0FFF6h
0x180014221  add     rax, rax
0x180014224  cmp     rax, 8
0x180014228  jb      short loc_18001421D
0x18001422a  jmp     loc_180014158
0x18001422f  mov     rdx, [r14+10h]
0x180014233  mov     r8d, r12d
0x180014236  mov     rcx, rbp
0x180014239  call    sqlite3ExprCode
0x18001423e  xor     r9d, r9d
0x180014241  mov     [rsp+58h+var_38], 0
0x180014249  mov     r8d, r12d
0x18001424c  mov     rcx, r15
0x18001424f  lea     edx, [r9+0Dh]
0x180014253  call    sqlite3VdbeAddOp3
0x180014258  mov     r8d, r12d
0x18001425b  mov     edx, 11h
0x180014260  jmp     short loc_1800141F3
```
