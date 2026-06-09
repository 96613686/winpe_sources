# vdbeColumnFromOverflow

- ea: `0x1800621d0`
- end: `0x1800623c1`
- name: `vdbeColumnFromOverflow`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002a050`

## callees

- `0x18000f720`
- `0x1800209e8`
- `0x180020a94`
- `0x180020d40`
- `0x18002105c`
- `0x18004b5e4`
- `0x1800621d0`
- `0x1800623c8`
- `0x180065e8c`
- `0x180086490`

## pseudocode

```c
__int64 __fastcall vdbeColumnFromOverflow(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        int a6,
        __int64 a7)
{
  int v10; // eax
  int v11; // edx
  __int64 v12; // r8
  unsigned int v13; // r9d
  __int64 v14; // r14
  __int64 result; // rax
  char v16; // bl
  __int64 v17; // rax
  char **v18; // rsi
  char *v19; // rbx
  __int64 v20; // r9
  char *v21; // rbx
  char *v22; // rax
  unsigned int v23; // r11d
  char v26; // [rsp+A0h] [rbp+38h]

  v10 = sqlite3VdbeSerialTypeLen(a3);
  v14 = v10;
  if ( v10 > *(_DWORD *)(v12 + 136) )
    return 18;
  v16 = *(_BYTE *)(a7 + 22);
  v26 = v16;
  if ( v10 > 4000 && !*(_QWORD *)(a1 + 56) )
  {
    if ( (*(_BYTE *)(a1 + 8) & 0x10) == 0 )
    {
      v17 = sqlite3DbMallocZero(v12, 32);
      *(_QWORD *)(a1 + 112) = v17;
      if ( !v17 )
        return 7;
      *(_DWORD *)(a1 + 8) |= 0x10u;
      v11 = a2;
    }
    v18 = *(char ***)(a1 + 112);
    if ( *v18 )
    {
      if ( *((_DWORD *)v18 + 4) == v11 && *((_DWORD *)v18 + 5) == a5 && *((_DWORD *)v18 + 6) == a6 )
      {
        v19 = v18[1];
        if ( v19 == (char *)sqlite3BtreeOffset(*(_QWORD *)(a1 + 48)) )
        {
          v21 = *v18;
LABEL_20:
          ++*((_QWORD *)v21 - 1);
          if ( (a3 & 1) != 0 )
          {
            LOBYTE(v20) = v26;
            v23 = sqlite3VdbeMemSetStr(a7, v21, v14, v20, sqlite3RCStrUnref);
LABEL_27:
            *(_WORD *)(a7 + 20) |= 0x200u;
            goto LABEL_28;
          }
          v23 = sqlite3VdbeMemSetStr(a7, v21, v14, 0, sqlite3RCStrUnref);
          goto LABEL_28;
        }
      }
    }
    if ( *v18 )
      sqlite3RCStrUnref(*v18);
    v22 = (char *)sqlite3RCStrNew(v14 + 3);
    *v18 = v22;
    v21 = v22;
    if ( v22 )
    {
      result = accessPayload(*(_QWORD *)(a1 + 48), a4, v14, v22, 0);
      if ( (_DWORD)result )
        return result;
      *(_WORD *)&v21[v14] = 0;
      v21[v14 + 2] = 0;
      *((_DWORD *)v18 + 4) = a2;
      *((_DWORD *)v18 + 5) = a5;
      *((_DWORD *)v18 + 6) = a6;
      v18[1] = (char *)sqlite3BtreeOffset(*(_QWORD *)(a1 + 48));
      goto LABEL_20;
    }
    return 7;
  }
  result = sqlite3VdbeMemFromBtree(*(_QWORD *)(a1 + 48), v13, (unsigned int)v10, a7);
  if ( (_DWORD)result )
    return result;
  sqlite3VdbeSerialGet(*(_QWORD *)(a7 + 8), a3, a7);
  if ( (a3 & 1) != 0 && v16 == 1 )
  {
    *(_BYTE *)(v14 + *(_QWORD *)(a7 + 8)) = v23;
    goto LABEL_27;
  }
LABEL_28:
  *(_WORD *)(a7 + 20) &= ~0x4000u;
  return v23;
}

```

## disassembly

```asm
0x1800621d0  mov     [rsp+arg_0], rbx
0x1800621d5  mov     [rsp+arg_18], r9
0x1800621da  mov     [rsp+arg_8], edx
0x1800621de  push    rbp
0x1800621df  push    rsi
0x1800621e0  push    rdi
0x1800621e1  push    r12
0x1800621e3  push    r13
0x1800621e5  push    r14
0x1800621e7  push    r15
0x1800621e9  sub     rsp, 30h
0x1800621ed  mov     rdi, [rsp+68h+arg_30]
0x1800621f5  mov     r15d, r8d
0x1800621f8  mov     rbp, rcx
0x1800621fb  mov     ecx, r15d
0x1800621fe  mov     r8, [rdi+18h]
0x180062202  call    sqlite3VdbeSerialTypeLen
0x180062207  movsxd  r14, eax
0x18006220a  cmp     r14d, [r8+88h]
0x180062211  jle     short loc_18006221D
0x180062213  mov     eax, 12h
0x180062218  jmp     loc_1800623AC
0x18006221d  mov     bl, [rdi+16h]
0x180062220  mov     byte ptr [rsp+68h+arg_30], bl
0x180062227  cmp     r14d, 0FA0h
0x18006222e  jle     loc_18006235C
0x180062234  cmp     qword ptr [rbp+38h], 0
0x180062239  jnz     loc_18006235C
0x18006223f  test    byte ptr [rbp+8], 10h
0x180062243  jnz     short loc_180062263
0x180062245  mov     edx, 20h ; ' '
0x18006224a  mov     rcx, r8
0x18006224d  call    sqlite3DbMallocZero
0x180062252  mov     [rbp+70h], rax
0x180062256  test    rax, rax
0x180062259  jz      short loc_1800622C6
0x18006225b  or      dword ptr [rbp+8], 10h
0x18006225f  mov     edx, [rsp+68h+arg_8]
0x180062263  mov     rsi, [rbp+70h]
0x180062267  mov     r12d, [rsp+68h+arg_28]
0x18006226f  mov     r13d, [rsp+68h+arg_20]
0x180062277  cmp     qword ptr [rsi], 0
0x18006227b  jz      short loc_1800622A5
0x18006227d  cmp     [rsi+10h], edx
0x180062280  jnz     short loc_1800622A5
0x180062282  cmp     [rsi+14h], r13d
0x180062286  jnz     short loc_1800622A5
0x180062288  cmp     [rsi+18h], r12d
0x18006228c  jnz     short loc_1800622A5
0x18006228e  mov     rcx, [rbp+30h]
0x180062292  mov     rbx, [rsi+8]
0x180062296  call    sqlite3BtreeOffset
0x18006229b  cmp     rbx, rax
0x18006229e  jnz     short loc_1800622A5
0x1800622a0  mov     rbx, [rsi]
0x1800622a3  jmp     short loc_18006231E
0x1800622a5  mov     rcx, [rsi]
0x1800622a8  test    rcx, rcx
0x1800622ab  jz      short loc_1800622B2
0x1800622ad  call    sqlite3RCStrUnref
0x1800622b2  lea     rcx, [r14+3]
0x1800622b6  call    sqlite3RCStrNew
0x1800622bb  mov     [rsi], rax
0x1800622be  mov     rbx, rax
0x1800622c1  test    rax, rax
0x1800622c4  jnz     short loc_1800622D0
0x1800622c6  mov     eax, 7
0x1800622cb  jmp     loc_1800623AC
0x1800622d0  mov     edx, dword ptr [rsp+68h+arg_18]
0x1800622d7  mov     r9, rbx
0x1800622da  mov     rcx, [rbp+30h]
0x1800622de  mov     r8d, r14d
0x1800622e1  mov     dword ptr [rsp+68h+var_48], 0
0x1800622e9  call    accessPayload
0x1800622ee  xor     ecx, ecx
0x1800622f0  test    eax, eax
0x1800622f2  jnz     loc_1800623AC
0x1800622f8  mov     eax, [rsp+68h+arg_8]
0x1800622fc  mov     [r14+rbx], cx
0x180062301  mov     [r14+rbx+2], cl
0x180062306  mov     [rsi+10h], eax
0x180062309  mov     [rsi+14h], r13d
0x18006230d  mov     [rsi+18h], r12d
0x180062311  mov     rcx, [rbp+30h]
0x180062315  call    sqlite3BtreeOffset
0x18006231a  mov     [rsi+8], rax
0x18006231e  inc     qword ptr [rbx-8]
0x180062322  lea     rax, sqlite3RCStrUnref
0x180062329  mov     [rsp+68h+var_48], rax
0x18006232e  mov     r8, r14
0x180062331  mov     rdx, rbx
0x180062334  mov     rcx, rdi
0x180062337  test    r15b, 1
0x18006233b  jz      short loc_18006234F
0x18006233d  mov     r9b, byte ptr [rsp+68h+arg_30]
0x180062345  call    sqlite3VdbeMemSetStr
0x18006234a  mov     r11d, eax
0x18006234d  jmp     short loc_180062397
0x18006234f  xor     r9d, r9d
0x180062352  call    sqlite3VdbeMemSetStr
0x180062357  mov     r11d, eax
0x18006235a  jmp     short loc_1800623A0
0x18006235c  mov     rcx, [rbp+30h]
0x180062360  mov     edx, r9d
0x180062363  mov     r9, rdi
0x180062366  mov     r8d, r14d
0x180062369  call    sqlite3VdbeMemFromBtree
0x18006236e  mov     r11d, eax
0x180062371  test    eax, eax
0x180062373  jnz     short loc_1800623AC
0x180062375  mov     rcx, [rdi+8]
0x180062379  mov     r8, rdi
0x18006237c  mov     edx, r15d
0x18006237f  call    sqlite3VdbeSerialGet
0x180062384  test    r15b, 1
0x180062388  jz      short loc_1800623A0
0x18006238a  cmp     bl, 1
0x18006238d  jnz     short loc_1800623A0
0x18006238f  mov     rax, [rdi+8]
0x180062393  mov     [r14+rax], r11b
0x180062397  mov     eax, 200h
0x18006239c  or      [rdi+14h], ax
0x1800623a0  mov     eax, 0BFFFh
0x1800623a5  and     [rdi+14h], ax
0x1800623a9  mov     eax, r11d
0x1800623ac  mov     rbx, [rsp+68h+arg_0]
0x1800623b1  add     rsp, 30h
0x1800623b5  pop     r15
0x1800623b7  pop     r14
0x1800623b9  pop     r13
0x1800623bb  pop     r12
0x1800623bd  pop     rdi
0x1800623be  pop     rsi
0x1800623bf  pop     rbp
0x1800623c0  retn
```
