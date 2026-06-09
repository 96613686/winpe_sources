# triggersReallyExist

- ea: `0x1800311c0`
- end: `0x180031384`
- name: `triggersReallyExist`
- size: `452`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18002f9a4`
- `0x180041fd0`

## callees

- `0x180014464`
- `0x18002e290`
- `0x1800311c0`
- `0x180057b38`

## string_xrefs

- `0x1800312f4`: `DELETE`
- `0x1800312ed`: `UPDATE`

## pseudocode

```c
__int64 __fastcall triggersReallyExist(__int64 a1, __int64 a2, int a3, __int64 a4, _DWORD *a5)
{
  int v5; // esi
  __int64 v6; // rdi
  __int64 v9; // r13
  _QWORD *v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rbp
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  int v18; // ebp
  const char *v19; // r8
  int v20; // eax
  __int64 v22; // [rsp+60h] [rbp+8h]
  __int64 v23; // [rsp+68h] [rbp+10h]
  __int64 v24; // [rsp+78h] [rbp+20h]

  v24 = a4;
  v22 = a1;
  v5 = 0;
  v6 = *(_QWORD *)(a2 + 88);
  v23 = v6;
  v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 56LL);
  v10 = *(_QWORD **)(v9 + 64);
  if ( v10 )
  {
    while ( 1 )
    {
      v11 = v10[2];
      v12 = *(_QWORD *)(v11 + 48);
      if ( v12 == *(_QWORD *)(a2 + 96) )
      {
        v13 = *(_QWORD *)(v11 + 8);
        if ( v13 )
        {
          if ( !(unsigned int)sqlite3StrICmp(v13, *(_QWORD *)a2) && (v12 != v9 || *(_BYTE *)(v11 + 18)) )
            goto LABEL_9;
        }
      }
      if ( *(_BYTE *)(v11 + 16) == 0x96 )
        break;
LABEL_10:
      v10 = (_QWORD *)*v10;
      if ( !v10 )
      {
        a1 = v22;
        a4 = v24;
        v23 = v6;
        goto LABEL_12;
      }
    }
    *(_QWORD *)(v11 + 8) = *(_QWORD *)a2;
    *(_QWORD *)(v11 + 48) = *(_QWORD *)(a2 + 96);
LABEL_9:
    *(_QWORD *)(v11 + 64) = v6;
    v6 = v11;
    goto LABEL_10;
  }
LABEL_12:
  if ( !v6 )
    goto LABEL_41;
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x40000) == 0 )
  {
    v14 = *(_QWORD *)(a2 + 88);
    if ( v14 )
    {
      if ( v6 == v14 )
      {
        v6 = 0;
        goto LABEL_41;
      }
      v15 = v6;
      if ( *(_QWORD *)(v6 + 64) )
      {
        do
        {
          v16 = *(_QWORD *)(v15 + 64);
          if ( v16 == v14 )
            break;
          v15 = *(_QWORD *)(v15 + 64);
        }
        while ( *(_QWORD *)(v16 + 64) );
      }
      *(_QWORD *)(v15 + 64) = 0;
    }
  }
  v17 = v6;
  do
  {
    v18 = *(unsigned __int8 *)(v17 + 16);
    if ( v18 == a3 && (unsigned int)checkColumnOverlap(*(_QWORD *)(v17 + 32), a4) )
    {
LABEL_37:
      v20 = *(unsigned __int8 *)(v17 + 17);
LABEL_38:
      v5 |= v20;
      goto LABEL_39;
    }
    if ( (_BYTE)v18 == 0x96 )
    {
      *(_BYTE *)(v17 + 16) = a3;
      if ( *(_BYTE *)(a2 + 63) == 1 )
      {
        if ( a3 != 127 )
        {
          v19 = "DELETE";
          if ( a3 != 128 )
            v19 = "UPDATE";
          sqlite3ErrorMsg(v22, "%s RETURNING is not available on virtual tables", v19);
        }
        LOBYTE(v20) = 1;
      }
      else
      {
        LOBYTE(v20) = 2;
      }
      *(_BYTE *)(v17 + 17) = v20;
      v20 = (unsigned __int8)v20;
      goto LABEL_38;
    }
    if ( *(_BYTE *)(v17 + 18) && (_BYTE)v18 == 127 && a3 == 129 && !*(_QWORD *)(v22 + 176) )
      goto LABEL_37;
LABEL_39:
    v17 = *(_QWORD *)(v17 + 64);
    a4 = v24;
  }
  while ( v17 );
  v6 = v23;
LABEL_41:
  if ( a5 )
    *a5 = v5;
  return v6 & -(__int64)(v5 != 0);
}

```

## disassembly

```asm
0x1800311c0  mov     [rsp+arg_10], rbx
0x1800311c5  mov     [rsp+arg_18], r9
0x1800311ca  mov     [rsp+arg_0], rcx
0x1800311cf  push    rbp
0x1800311d0  push    rsi
0x1800311d1  push    rdi
0x1800311d2  push    r12
0x1800311d4  push    r13
0x1800311d6  push    r14
0x1800311d8  push    r15
0x1800311da  sub     rsp, 20h
0x1800311de  mov     rax, [rcx]
0x1800311e1  xor     esi, esi
0x1800311e3  mov     rdi, [rdx+58h]
0x1800311e7  mov     r12d, r8d
0x1800311ea  mov     r15, rdx
0x1800311ed  mov     [rsp+58h+arg_8], rdi
0x1800311f2  mov     r10, [rax+20h]
0x1800311f6  mov     r13, [r10+38h]
0x1800311fa  mov     r14, [r13+40h]
0x1800311fe  test    r14, r14
0x180031201  jz      short loc_180031264
0x180031203  mov     rbx, [r14+10h]
0x180031207  mov     rbp, [rbx+30h]
0x18003120b  cmp     rbp, [r15+60h]
0x18003120f  jnz     short loc_180031231
0x180031211  mov     rcx, [rbx+8]
0x180031215  test    rcx, rcx
0x180031218  jz      short loc_180031231
0x18003121a  mov     rdx, [r15]
0x18003121d  call    sqlite3StrICmp
0x180031222  test    eax, eax
0x180031224  jnz     short loc_180031231
0x180031226  cmp     rbp, r13
0x180031229  jnz     short loc_180031246
0x18003122b  cmp     [rbx+12h], sil
0x18003122f  jnz     short loc_180031246
0x180031231  cmp     byte ptr [rbx+10h], 96h
0x180031235  jnz     short loc_18003124D
0x180031237  mov     rax, [r15]
0x18003123a  mov     [rbx+8], rax
0x18003123e  mov     rax, [r15+60h]
0x180031242  mov     [rbx+30h], rax
0x180031246  mov     [rbx+40h], rdi
0x18003124a  mov     rdi, rbx
0x18003124d  mov     r14, [r14]
0x180031250  test    r14, r14
0x180031253  jnz     short loc_180031203
0x180031255  mov     rcx, [rsp+58h+arg_0]
0x18003125a  mov     r9, [rsp+58h+arg_18]
0x18003125f  mov     [rsp+58h+arg_8], rdi
0x180031264  test    rdi, rdi
0x180031267  jz      loc_180031358
0x18003126d  mov     rax, [rcx]
0x180031270  mov     ecx, [rax+30h]
0x180031273  bt      rcx, 12h
0x180031278  jb      short loc_1800312AE
0x18003127a  mov     rcx, [r15+58h]
0x18003127e  test    rcx, rcx
0x180031281  jz      short loc_1800312AE
0x180031283  cmp     rdi, rcx
0x180031286  jnz     short loc_18003128F
0x180031288  xor     edi, edi
0x18003128a  jmp     loc_180031358
0x18003128f  mov     rax, rdi
0x180031292  cmp     [rdi+40h], rsi
0x180031296  jz      short loc_1800312AA
0x180031298  mov     rdx, [rax+40h]
0x18003129c  cmp     rdx, rcx
0x18003129f  jz      short loc_1800312AA
0x1800312a1  mov     rax, rdx
0x1800312a4  cmp     [rdx+40h], rsi
0x1800312a8  jnz     short loc_180031298
0x1800312aa  mov     [rax+40h], rsi
0x1800312ae  mov     rbx, rdi
0x1800312b1  mov     rdi, [rsp+58h+arg_0]
0x1800312b6  movzx   ebp, byte ptr [rbx+10h]
0x1800312ba  cmp     ebp, r12d
0x1800312bd  jnz     short loc_1800312CF
0x1800312bf  mov     rcx, [rbx+20h]
0x1800312c3  mov     rdx, r9
0x1800312c6  call    checkColumnOverlap
0x1800312cb  test    eax, eax
0x1800312cd  jnz     short loc_18003133B
0x1800312cf  cmp     bpl, 96h
0x1800312d3  jnz     short loc_18003131C
0x1800312d5  mov     [rbx+10h], r12b
0x1800312d9  cmp     byte ptr [r15+3Fh], 1
0x1800312de  jnz     short loc_180031312
0x1800312e0  cmp     r12d, 7Fh
0x1800312e4  jz      short loc_18003130E
0x1800312e6  cmp     r12d, 80h
0x1800312ed  lea     rax, aUpdate; "UPDATE"
0x1800312f4  lea     r8, aDelete; "DELETE"
0x1800312fb  mov     rcx, rdi
0x1800312fe  cmovnz  r8, rax
0x180031302  lea     rdx, aSReturningIsNo; "%s RETURNING is not available on virtua"...
0x180031309  call    sqlite3ErrorMsg
0x18003130e  mov     al, 1
0x180031310  jmp     short loc_180031314
0x180031312  mov     al, 2
0x180031314  mov     [rbx+11h], al
0x180031317  movzx   eax, al
0x18003131a  jmp     short loc_18003133F
0x18003131c  cmp     byte ptr [rbx+12h], 0
0x180031320  jz      short loc_180031341
0x180031322  cmp     bpl, 7Fh
0x180031326  jnz     short loc_180031341
0x180031328  cmp     r12d, 81h
0x18003132f  jnz     short loc_180031341
0x180031331  cmp     qword ptr [rdi+0B0h], 0
0x180031339  jnz     short loc_180031341
0x18003133b  movzx   eax, byte ptr [rbx+11h]
0x18003133f  or      esi, eax
0x180031341  mov     rbx, [rbx+40h]
0x180031345  mov     r9, [rsp+58h+arg_18]
0x18003134a  test    rbx, rbx
0x18003134d  jnz     loc_1800312B6
0x180031353  mov     rdi, [rsp+58h+arg_8]
0x180031358  mov     rax, [rsp+58h+arg_20]
0x180031360  test    rax, rax
0x180031363  jz      short loc_180031367
0x180031365  mov     [rax], esi
0x180031367  mov     rbx, [rsp+58h+arg_10]
0x18003136c  neg     esi
0x18003136e  sbb     rax, rax
0x180031371  and     rax, rdi
0x180031374  add     rsp, 20h
0x180031378  pop     r15
0x18003137a  pop     r14
0x18003137c  pop     r13
0x18003137e  pop     r12
0x180031380  pop     rdi
0x180031381  pop     rsi
0x180031382  pop     rbp
0x180031383  retn
```
