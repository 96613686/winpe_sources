# sqlite3_deserialize

- ea: `0x18008e280`
- end: `0x18008e42d`
- name: `sqlite3_deserialize`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x180001110`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x180014928`
- `0x180027aa0`
- `0x180028c94`
- `0x180029bd0`
- `0x1800303e0`
- `0x180060134`
- `0x180079b9c`
- `0x18008e280`

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
    v11 = 53816;
    return sqlite3ReportError(21, v11, "misuse");
  }
  if ( a4 < 0 )
  {
    v11 = 53818;
    return sqlite3ReportError(21, v11, "misuse");
  }
  if ( a5 < 0 )
  {
    v11 = 53819;
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
    v16 = sqlite3LockAndPrepare(a1, v15, -1, 128, 0, (__int64)v21, 0);
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
        if ( a5 < qword_1800B57B8 )
          *(_QWORD *)(v19 + 16) = qword_1800B57B8;
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
0x18008e280  mov     [rsp+arg_18], r9
0x18008e285  push    rbx
0x18008e286  push    rbp
0x18008e287  push    rsi
0x18008e288  push    rdi
0x18008e289  push    r12
0x18008e28b  push    r13
0x18008e28d  push    r14
0x18008e28f  push    r15
0x18008e291  sub     rsp, 58h
0x18008e295  xor     r14d, r14d
0x18008e298  mov     rdi, r9
0x18008e29b  mov     [rsp+98h+var_58], r14
0x18008e2a0  mov     r15, r8
0x18008e2a3  mov     rsi, rdx
0x18008e2a6  mov     rbx, rcx
0x18008e2a9  call    sqlite3SafetyCheckOk
0x18008e2ae  test    eax, eax
0x18008e2b0  jnz     short loc_18008E2CD
0x18008e2b2  mov     edx, 0D238h
0x18008e2b7  lea     r8, aMisuse; "misuse"
0x18008e2be  mov     ecx, 15h
0x18008e2c3  call    sqlite3ReportError
0x18008e2c8  jmp     loc_18008E41C
0x18008e2cd  test    rdi, rdi
0x18008e2d0  jns     short loc_18008E2D9
0x18008e2d2  mov     edx, 0D23Ah
0x18008e2d7  jmp     short loc_18008E2B7
0x18008e2d9  mov     rbp, [rsp+98h+arg_20]
0x18008e2e1  test    rbp, rbp
0x18008e2e4  jns     short loc_18008E2ED
0x18008e2e6  mov     edx, 0D23Bh
0x18008e2eb  jmp     short loc_18008E2B7
0x18008e2ed  mov     rcx, [rbx+18h]
0x18008e2f1  call    sqlite3_mutex_enter
0x18008e2f6  test    rsi, rsi
0x18008e2f9  jnz     short loc_18008E302
0x18008e2fb  mov     rax, [rbx+20h]
0x18008e2ff  mov     rsi, [rax]
0x18008e302  mov     rdx, rsi
0x18008e305  mov     rcx, rbx
0x18008e308  call    sqlite3FindDbName
0x18008e30d  mov     r12d, eax
0x18008e310  test    eax, eax
0x18008e312  js      loc_18008E3EA
0x18008e318  cmp     eax, 1
0x18008e31b  jz      loc_18008E3EA
0x18008e321  mov     rdx, rsi
0x18008e324  lea     rcx, aAttachXAsQ; "ATTACH x AS %Q"
0x18008e32b  call    sqlite3_mprintf
0x18008e330  mov     r13, rax
0x18008e333  test    rax, rax
0x18008e336  jnz     short loc_18008E340
0x18008e338  lea     edi, [rax+7]
0x18008e33b  jmp     loc_18008E3EF
0x18008e340  lea     rax, [rsp+98h+var_58]
0x18008e345  mov     [rsp+98h+var_68], r14
0x18008e34a  mov     [rsp+98h+var_70], rax
0x18008e34f  mov     r9d, 80h
0x18008e355  or      r8d, 0FFFFFFFFh
0x18008e359  mov     [rsp+98h+var_78], r14
0x18008e35e  mov     rdx, r13
0x18008e361  mov     rcx, rbx
0x18008e364  call    sqlite3LockAndPrepare
0x18008e369  mov     rcx, r13
0x18008e36c  mov     edi, eax
0x18008e36e  call    sqlite3_free
0x18008e373  mov     r14, [rsp+98h+var_58]
0x18008e378  test    edi, edi
0x18008e37a  jnz     short loc_18008E3EF
0x18008e37c  or      dword ptr [rbx+0C8h], 4
0x18008e383  mov     rcx, r14
0x18008e386  mov     [rbx+0C4h], r12b
0x18008e38d  call    sqlite3_step
0x18008e392  and     dword ptr [rbx+0C8h], 0FFFFFFFBh
0x18008e399  cmp     eax, 65h ; 'e'
0x18008e39c  jnz     short loc_18008E3EA
0x18008e39e  mov     rdx, rsi
0x18008e3a1  mov     rcx, rbx
0x18008e3a4  call    memdbFromDbSchema
0x18008e3a9  test    rax, rax
0x18008e3ac  jz      short loc_18008E3EA
0x18008e3ae  mov     rax, [rax+8]
0x18008e3b2  mov     rcx, [rsp+98h+arg_18]
0x18008e3ba  mov     [rax+18h], r15
0x18008e3be  xor     r15d, r15d
0x18008e3c1  mov     [rax], rcx
0x18008e3c4  mov     [rax+8], rbp
0x18008e3c8  mov     [rax+10h], rbp
0x18008e3cc  mov     rcx, cs:qword_1800B57B8
0x18008e3d3  cmp     rbp, rcx
0x18008e3d6  jge     short loc_18008E3DC
0x18008e3d8  mov     [rax+10h], rcx
0x18008e3dc  mov     esi, [rsp+98h+arg_28]
0x18008e3e3  xor     edi, edi
0x18008e3e5  mov     [rax+2Ch], esi
0x18008e3e8  jmp     short loc_18008E3F6
0x18008e3ea  mov     edi, 1
0x18008e3ef  mov     esi, [rsp+98h+arg_28]
0x18008e3f6  mov     rcx, r14
0x18008e3f9  call    sqlite3_finalize
0x18008e3fe  test    r15, r15
0x18008e401  jz      short loc_18008E411
0x18008e403  test    sil, 1
0x18008e407  jz      short loc_18008E411
0x18008e409  mov     rcx, r15
0x18008e40c  call    sqlite3_free
0x18008e411  mov     rcx, [rbx+18h]
0x18008e415  call    sqlite3_mutex_leave
0x18008e41a  mov     eax, edi
0x18008e41c  add     rsp, 58h
0x18008e420  pop     r15
0x18008e422  pop     r14
0x18008e424  pop     r13
0x18008e426  pop     r12
0x18008e428  pop     rdi
0x18008e429  pop     rsi
0x18008e42a  pop     rbp
0x18008e42b  pop     rbx
0x18008e42c  retn
```
