# sqlite3BtreeTableMoveto

- ea: `0x1800601e4`
- end: `0x1800603d1`
- name: `sqlite3BtreeTableMoveto`
- size: `493`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ed0c`
- `0x18002a050`
- `0x180060168`
- `0x180066830`

## callees

- `0x1800201c0`
- `0x1800259b0`
- `0x180025ff0`
- `0x180048ee0`
- `0x180054468`
- `0x180060134`
- `0x1800601e4`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeTableMoveto(__int64 a1, __int64 a2, char a3, int *a4)
{
  __int64 v8; // rax
  __int64 result; // rax
  char v10; // r13
  __int64 v11; // rdi
  int v12; // r15d
  int v13; // r12d
  int i; // esi
  __int64 v15; // rdx
  unsigned __int8 *v16; // rcx
  unsigned __int8 v17; // al
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // ecx
  unsigned int v21; // edx
  __int64 v22; // [rsp+70h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 && (*(_BYTE *)(a1 + 1) & 2) != 0 )
  {
    v8 = *(_QWORD *)(a1 + 48);
    if ( v8 == a2 )
    {
      *a4 = 0;
      return 0;
    }
    if ( v8 < a2 )
    {
      if ( (*(_BYTE *)(a1 + 1) & 8) != 0 )
      {
LABEL_15:
        *a4 = -1;
        return 0;
      }
      if ( v8 + 1 == a2 )
      {
        *a4 = 0;
        result = sqlite3BtreeNext(a1, a2);
        if ( (_DWORD)result )
        {
          if ( (_DWORD)result != 101 )
            return result;
        }
        else
        {
          getCellInfo(a1);
          if ( *(_QWORD *)(a1 + 48) == a2 )
            return 0;
        }
      }
    }
  }
  result = moveToRoot(a1);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result != 16 )
      return result;
    goto LABEL_15;
  }
  v10 = 1 - a3;
  while ( 2 )
  {
    v11 = *(_QWORD *)(a1 + 136);
    v12 = 0;
    v13 = *(unsigned __int16 *)(v11 + 24) - 1;
    for ( i = v13 >> v10; ; i = (v13 + v12) >> 1 )
    {
      v15 = *(_QWORD *)(v11 + 96);
      v22 = 0;
      v16 = (unsigned __int8 *)(*(_QWORD *)(v11 + 104)
                              + (unsigned __int16)(*(_WORD *)(v11 + 26) & __ROR2__(*(_WORD *)(2 * i + v15), 8)));
      if ( *(_BYTE *)(v11 + 2) )
      {
        while ( 1 )
        {
          v17 = *v16++;
          if ( v17 < 0x80u )
            break;
          if ( (unsigned __int64)v16 >= *(_QWORD *)(v11 + 88) )
            return sqlite3ReportError(11, 76482, "database corruption");
        }
      }
      sqlite3GetVarint(v16, &v22);
      v18 = v22;
      if ( v22 < a2 )
      {
        v12 = i + 1;
        if ( i + 1 > v13 )
        {
          v19 = -1;
          goto LABEL_29;
        }
        continue;
      }
      if ( v22 <= a2 )
        break;
      v13 = i - 1;
      if ( v12 > i - 1 )
      {
        v19 = 1;
LABEL_29:
        if ( *(_BYTE *)(v11 + 8) )
        {
          *(_WORD *)(a1 + 86) = i;
          v20 = 0;
          *a4 = v19;
LABEL_31:
          *(_WORD *)(a1 + 70) = 0;
          return v20;
        }
        goto LABEL_34;
      }
    }
    *(_WORD *)(a1 + 86) = i;
    if ( !*(_BYTE *)(v11 + 8) )
    {
      v12 = i;
LABEL_34:
      if ( v12 < *(unsigned __int16 *)(v11 + 24) )
        v21 = *(_DWORD *)((unsigned __int16)(*(_WORD *)(v11 + 26)
                                           & __ROR2__(*(_WORD *)(2 * v12 + *(_QWORD *)(v11 + 96)), 8))
                        + *(_QWORD *)(v11 + 80));
      else
        v21 = *(_DWORD *)(*(unsigned __int8 *)(v11 + 9) + *(_QWORD *)(v11 + 80) + 8LL);
      *(_WORD *)(a1 + 86) = v12;
      v20 = moveToChild(a1, _byteswap_ulong(v21));
      if ( v20 )
        goto LABEL_31;
      continue;
    }
    break;
  }
  *(_BYTE *)(a1 + 1) |= 2u;
  result = 0;
  *(_QWORD *)(a1 + 48) = v18;
  *(_WORD *)(a1 + 70) = 0;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x1800601e4  push    rbx
0x1800601e6  push    rbp
0x1800601e7  push    rsi
0x1800601e8  push    rdi
0x1800601e9  push    r12
0x1800601eb  push    r13
0x1800601ed  push    r14
0x1800601ef  push    r15
0x1800601f1  sub     rsp, 28h
0x1800601f5  cmp     byte ptr [rcx], 0
0x1800601f8  mov     r14, r9
0x1800601fb  mov     edi, r8d
0x1800601fe  mov     rbp, rdx
0x180060201  mov     rbx, rcx
0x180060204  jnz     short loc_18006025C
0x180060206  test    byte ptr [rcx+1], 2
0x18006020a  jz      short loc_18006025C
0x18006020c  mov     rax, [rcx+30h]
0x180060210  cmp     rax, rdx
0x180060213  jnz     short loc_180060223
0x180060215  mov     dword ptr [r9], 0
0x18006021c  xor     eax, eax
0x18006021e  jmp     loc_1800603C0
0x180060223  jge     short loc_18006025C
0x180060225  test    byte ptr [rcx+1], 8
0x180060229  jnz     short loc_180060271
0x18006022b  inc     rax
0x18006022e  cmp     rax, rbp
0x180060231  jnz     short loc_18006025C
0x180060233  mov     dword ptr [r9], 0
0x18006023a  call    sqlite3BtreeNext
0x18006023f  test    eax, eax
0x180060241  jnz     short loc_180060253
0x180060243  mov     rcx, rbx
0x180060246  call    getCellInfo
0x18006024b  cmp     [rbx+30h], rbp
0x18006024f  jz      short loc_18006021C
0x180060251  jmp     short loc_18006025C
0x180060253  cmp     eax, 65h ; 'e'
0x180060256  jnz     loc_1800603C0
0x18006025c  mov     rcx, rbx
0x18006025f  call    moveToRoot
0x180060264  test    eax, eax
0x180060266  jz      short loc_18006027A
0x180060268  cmp     eax, 10h
0x18006026b  jnz     loc_1800603C0
0x180060271  mov     dword ptr [r14], 0FFFFFFFFh
0x180060278  jmp     short loc_18006021C
0x18006027a  mov     r13d, 1
0x180060280  sub     r13d, edi
0x180060283  mov     rdi, [rbx+88h]
0x18006028a  xor     r15d, r15d
0x18006028d  mov     ecx, r13d
0x180060290  movzx   r12d, word ptr [rdi+18h]
0x180060295  dec     r12d
0x180060298  mov     esi, r12d
0x18006029b  sar     esi, cl
0x18006029d  mov     rdx, [rdi+60h]
0x1800602a1  lea     eax, [rsi+rsi]
0x1800602a4  movsxd  rcx, eax
0x1800602a7  mov     [rsp+68h+arg_0], 0
0x1800602b0  movzx   eax, word ptr [rcx+rdx]
0x1800602b4  ror     ax, 8
0x1800602b8  movzx   ecx, ax
0x1800602bb  movzx   eax, word ptr [rdi+1Ah]
0x1800602bf  and     rcx, rax
0x1800602c2  add     rcx, [rdi+68h]
0x1800602c6  cmp     byte ptr [rdi+2], 0
0x1800602ca  jz      short loc_1800602F6
0x1800602cc  mov     al, [rcx]
0x1800602ce  inc     rcx
0x1800602d1  cmp     al, 80h
0x1800602d3  jb      short loc_1800602F6
0x1800602d5  cmp     rcx, [rdi+58h]
0x1800602d9  jb      short loc_1800602CC
0x1800602db  lea     r8, aDatabaseCorrup; "database corruption"
0x1800602e2  mov     edx, 12AC2h
0x1800602e7  mov     ecx, 0Bh
0x1800602ec  call    sqlite3ReportError
0x1800602f1  jmp     loc_1800603C0
0x1800602f6  lea     rdx, [rsp+68h+arg_0]
0x1800602fb  call    sqlite3GetVarint
0x180060300  mov     rdx, [rsp+68h+arg_0]
0x180060305  cmp     rdx, rbp
0x180060308  jge     short loc_180060318
0x18006030a  lea     r15d, [rsi+1]
0x18006030e  cmp     r15d, r12d
0x180060311  jle     short loc_180060323
0x180060313  or      eax, 0FFFFFFFFh
0x180060316  jmp     short loc_180060333
0x180060318  jle     short loc_18006034C
0x18006031a  lea     r12d, [rsi-1]
0x18006031e  cmp     r15d, r12d
0x180060321  jg      short loc_18006032E
0x180060323  lea     esi, [r12+r15]
0x180060327  sar     esi, 1
0x180060329  jmp     loc_18006029D
0x18006032e  mov     eax, 1
0x180060333  cmp     byte ptr [rdi+8], 0
0x180060337  jz      short loc_180060359
0x180060339  mov     [rbx+56h], si
0x18006033d  xor     ecx, ecx
0x18006033f  mov     [r14], eax
0x180060342  xor     eax, eax
0x180060344  mov     [rbx+46h], ax
0x180060348  mov     eax, ecx
0x18006034a  jmp     short loc_1800603C0
0x18006034c  mov     [rbx+56h], si
0x180060350  cmp     byte ptr [rdi+8], 0
0x180060354  jnz     short loc_1800603AF
0x180060356  mov     r15d, esi
0x180060359  movzx   eax, word ptr [rdi+18h]
0x18006035d  cmp     r15d, eax
0x180060360  jl      short loc_180060370
0x180060362  movzx   ecx, byte ptr [rdi+9]
0x180060366  mov     rax, [rdi+50h]
0x18006036a  mov     edx, [rcx+rax+8]
0x18006036e  jmp     short loc_180060394
0x180060370  lea     eax, [r15+r15]
0x180060374  movsxd  rcx, eax
0x180060377  mov     rax, [rdi+60h]
0x18006037b  movzx   edx, word ptr [rcx+rax]
0x18006037f  movzx   eax, word ptr [rdi+1Ah]
0x180060383  ror     dx, 8
0x180060387  movzx   ecx, dx
0x18006038a  and     rcx, rax
0x18006038d  mov     rax, [rdi+50h]
0x180060391  mov     edx, [rcx+rax]
0x180060394  bswap   edx
0x180060396  mov     rcx, rbx
0x180060399  mov     [rbx+56h], r15w
0x18006039e  call    moveToChild
0x1800603a3  mov     ecx, eax
0x1800603a5  test    eax, eax
0x1800603a7  jz      loc_180060283
0x1800603ad  jmp     short loc_180060342
0x1800603af  or      byte ptr [rbx+1], 2
0x1800603b3  xor     eax, eax
0x1800603b5  mov     [rbx+30h], rdx
0x1800603b9  mov     [rbx+46h], ax
0x1800603bd  mov     [r14], eax
0x1800603c0  add     rsp, 28h
0x1800603c4  pop     r15
0x1800603c6  pop     r14
0x1800603c8  pop     r13
0x1800603ca  pop     r12
0x1800603cc  pop     rdi
0x1800603cd  pop     rsi
0x1800603ce  pop     rbp
0x1800603cf  pop     rbx
0x1800603d0  retn
```
