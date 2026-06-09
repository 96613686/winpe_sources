# sqlite3_deserialize

- ea: `0x18009c220`
- end: `0x18009c3cd`
- name: `sqlite3_deserialize`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180020a04`
- `0x180023a80`
- `0x180024640`
- `0x18002619c`
- `0x180028360`
- `0x1800310a0`
- `0x180038d00`
- `0x18003f840`
- `0x180041eb0`
- `0x180053e08`
- `0x180088dac`
- `0x18009c220`

## pseudocode

```c
__int64 __fastcall sqlite3_deserialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v6; // r14
  __int64 v11; // rdx
  int DbName; // eax
  char v14; // r12
  __int64 v15; // r13
  unsigned int v16; // edi
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  char v20; // si
  _QWORD v21[11]; // [rsp+40h] [rbp-58h] BYREF

  v6 = 0;
  v21[0] = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) )
  {
    v11 = 53815;
    return sqlite3ReportError(21, v11, "misuse");
  }
  if ( a4 < 0 )
  {
    v11 = 53817;
    return sqlite3ReportError(21, v11, "misuse");
  }
  if ( a5 < 0 )
  {
    v11 = 53818;
    return sqlite3ReportError(21, v11, "misuse");
  }
  sqlite3_mutex_enter(*(_QWORD *)(a1 + 24));
  if ( !a2 )
    a2 = **(_QWORD **)(a1 + 32);
  DbName = sqlite3FindDbName(a1, a2);
  v14 = DbName;
  if ( DbName < 0 || DbName == 1 )
    goto LABEL_20;
  v15 = sqlite3_mprintf("ATTACH x AS %Q", a2);
  if ( v15 )
  {
    v16 = sqlite3LockAndPrepare(a1, v15, 0xFFFFFFFF, 0x80u, 0, v21, 0);
    sqlite3_free(v15);
    v6 = v21[0];
    if ( v16 )
      goto LABEL_21;
    *(_DWORD *)(a1 + 200) |= 4u;
    *(_BYTE *)(a1 + 196) = v14;
    v17 = sqlite3_step(v6);
    *(_DWORD *)(a1 + 200) &= ~4u;
    if ( v17 == 101 )
    {
      v18 = memdbFromDbSchema(a1, a2);
      if ( v18 )
      {
        v19 = *(_QWORD *)(v18 + 8);
        *(_QWORD *)(v19 + 24) = a3;
        a3 = 0;
        *(_QWORD *)v19 = a4;
        *(_QWORD *)(v19 + 8) = a5;
        *(_QWORD *)(v19 + 16) = a5;
        if ( a5 < qword_1800D09F8 )
          *(_QWORD *)(v19 + 16) = qword_1800D09F8;
        v20 = a6;
        v16 = 0;
        *(_DWORD *)(v19 + 44) = a6;
        goto LABEL_22;
      }
    }
LABEL_20:
    v16 = 1;
    goto LABEL_21;
  }
  v16 = 7;
LABEL_21:
  v20 = a6;
LABEL_22:
  sqlite3_finalize(v6);
  if ( a3 )
  {
    if ( (v20 & 1) != 0 )
      sqlite3_free(a3);
  }
  sqlite3_mutex_leave(*(_QWORD *)(a1 + 24));
  return v16;
}

```

## disassembly

```asm
0x18009c220  mov     [rsp+arg_18], r9
0x18009c225  push    rbx
0x18009c226  push    rbp
0x18009c227  push    rsi
0x18009c228  push    rdi
0x18009c229  push    r12
0x18009c22b  push    r13
0x18009c22d  push    r14
0x18009c22f  push    r15
0x18009c231  sub     rsp, 58h
0x18009c235  xor     r14d, r14d
0x18009c238  mov     rdi, r9
0x18009c23b  mov     [rsp+98h+var_58], r14
0x18009c240  mov     r15, r8
0x18009c243  mov     rsi, rdx
0x18009c246  mov     rbx, rcx
0x18009c249  call    sqlite3SafetyCheckOk
0x18009c24e  test    eax, eax
0x18009c250  jnz     short loc_18009C26D
0x18009c252  mov     edx, 0D237h
0x18009c257  lea     r8, aMisuse; "misuse"
0x18009c25e  mov     ecx, 15h
0x18009c263  call    sqlite3ReportError
0x18009c268  jmp     loc_18009C3BC
0x18009c26d  test    rdi, rdi
0x18009c270  jns     short loc_18009C279
0x18009c272  mov     edx, 0D239h
0x18009c277  jmp     short loc_18009C257
0x18009c279  mov     rbp, [rsp+98h+arg_20]
0x18009c281  test    rbp, rbp
0x18009c284  jns     short loc_18009C28D
0x18009c286  mov     edx, 0D23Ah
0x18009c28b  jmp     short loc_18009C257
0x18009c28d  mov     rcx, [rbx+18h]
0x18009c291  call    sqlite3_mutex_enter
0x18009c296  test    rsi, rsi
0x18009c299  jnz     short loc_18009C2A2
0x18009c29b  mov     rax, [rbx+20h]
0x18009c29f  mov     rsi, [rax]
0x18009c2a2  mov     rdx, rsi
0x18009c2a5  mov     rcx, rbx
0x18009c2a8  call    sqlite3FindDbName
0x18009c2ad  mov     r12d, eax
0x18009c2b0  test    eax, eax
0x18009c2b2  js      loc_18009C38A
0x18009c2b8  cmp     eax, 1
0x18009c2bb  jz      loc_18009C38A
0x18009c2c1  mov     rdx, rsi
0x18009c2c4  lea     rcx, aAttachXAsQ; "ATTACH x AS %Q"
0x18009c2cb  call    sqlite3_mprintf
0x18009c2d0  mov     r13, rax
0x18009c2d3  test    rax, rax
0x18009c2d6  jnz     short loc_18009C2E0
0x18009c2d8  lea     edi, [rax+7]
0x18009c2db  jmp     loc_18009C38F
0x18009c2e0  lea     rax, [rsp+98h+var_58]
0x18009c2e5  mov     [rsp+98h+var_68], r14
0x18009c2ea  mov     [rsp+98h+var_70], rax
0x18009c2ef  mov     r9d, 80h
0x18009c2f5  or      r8d, 0FFFFFFFFh
0x18009c2f9  mov     [rsp+98h+var_78], r14
0x18009c2fe  mov     rdx, r13
0x18009c301  mov     rcx, rbx
0x18009c304  call    sqlite3LockAndPrepare
0x18009c309  mov     rcx, r13
0x18009c30c  mov     edi, eax
0x18009c30e  call    sqlite3_free
0x18009c313  mov     r14, [rsp+98h+var_58]
0x18009c318  test    edi, edi
0x18009c31a  jnz     short loc_18009C38F
0x18009c31c  or      dword ptr [rbx+0C8h], 4
0x18009c323  mov     rcx, r14
0x18009c326  mov     [rbx+0C4h], r12b
0x18009c32d  call    sqlite3_step
0x18009c332  and     dword ptr [rbx+0C8h], 0FFFFFFFBh
0x18009c339  cmp     eax, 65h ; 'e'
0x18009c33c  jnz     short loc_18009C38A
0x18009c33e  mov     rdx, rsi
0x18009c341  mov     rcx, rbx
0x18009c344  call    memdbFromDbSchema
0x18009c349  test    rax, rax
0x18009c34c  jz      short loc_18009C38A
0x18009c34e  mov     rax, [rax+8]
0x18009c352  mov     rcx, [rsp+98h+arg_18]
0x18009c35a  mov     [rax+18h], r15
0x18009c35e  xor     r15d, r15d
0x18009c361  mov     [rax], rcx
0x18009c364  mov     [rax+8], rbp
0x18009c368  mov     [rax+10h], rbp
0x18009c36c  mov     rcx, cs:qword_1800D09F8
0x18009c373  cmp     rbp, rcx
0x18009c376  jge     short loc_18009C37C
0x18009c378  mov     [rax+10h], rcx
0x18009c37c  mov     esi, [rsp+98h+arg_28]
0x18009c383  xor     edi, edi
0x18009c385  mov     [rax+2Ch], esi
0x18009c388  jmp     short loc_18009C396
0x18009c38a  mov     edi, 1
0x18009c38f  mov     esi, [rsp+98h+arg_28]
0x18009c396  mov     rcx, r14
0x18009c399  call    sqlite3_finalize
0x18009c39e  test    r15, r15
0x18009c3a1  jz      short loc_18009C3B1
0x18009c3a3  test    sil, 1
0x18009c3a7  jz      short loc_18009C3B1
0x18009c3a9  mov     rcx, r15
0x18009c3ac  call    sqlite3_free
0x18009c3b1  mov     rcx, [rbx+18h]
0x18009c3b5  call    sqlite3_mutex_leave
0x18009c3ba  mov     eax, edi
0x18009c3bc  add     rsp, 58h
0x18009c3c0  pop     r15
0x18009c3c2  pop     r14
0x18009c3c4  pop     r13
0x18009c3c6  pop     r12
0x18009c3c8  pop     rdi
0x18009c3c9  pop     rsi
0x18009c3ca  pop     rbp
0x18009c3cb  pop     rbx
0x18009c3cc  retn
```
