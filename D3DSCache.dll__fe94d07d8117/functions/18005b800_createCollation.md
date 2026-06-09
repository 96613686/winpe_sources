# createCollation

- ea: `0x18005b800`
- end: `0x18005b96d`
- name: `createCollation`
- size: `365`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800204f0`
- `0x1800944c0`
- `0x180094580`

## callees

- `0x18002b840`
- `0x180038cc0`
- `0x18003a860`
- `0x18003ce8c`
- `0x18005b800`
- `0x18007edf0`
- `0x18007f0b4`
- `0x1800a8010`

## string_xrefs

- `0x18005b88b`: `unable to delete/modify collation sequence due to active statements`

## pseudocode

```c
__int64 __fastcall createCollation(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v7; // rbp
  __int64 v8; // r12
  int v10; // ebx
  __int64 v12; // r8
  __int64 CollSeq; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r13
  __int64 v18; // r14
  __int64 v19; // r15
  void (__fastcall *v20)(_QWORD); // rax
  __int64 v21; // rax

  v7 = a4;
  v8 = a2;
  v10 = a3;
  if ( a3 == 4 || a3 == 8 )
  {
    v10 = 2;
  }
  else if ( (unsigned int)a3 - 1 > 2 )
  {
    return sqlite3ReportError(21, 182575, "misuse");
  }
  v12 = a2;
  LOBYTE(a2) = v10;
  CollSeq = sqlite3FindCollSeq(a1, a2, v12, 0);
  v17 = CollSeq;
  if ( CollSeq && *(_QWORD *)(CollSeq + 24) )
  {
    if ( *(_DWORD *)(a1 + 216) )
    {
      sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify collation sequence due to active statements", v16);
      return 5;
    }
    sqlite3ExpirePreparedStatements(a1, 0, v15);
    if ( (*(_BYTE *)(v17 + 8) & 0xF7) == v10 )
    {
      v18 = 0;
      v19 = *(_QWORD *)(findElementWithHash(a1 + 624, v8, 0) + 16);
      do
      {
        if ( *(_BYTE *)(v19 + 40 * v18 + 8) == *(_BYTE *)(v17 + 8) )
        {
          v20 = *(void (__fastcall **)(_QWORD))(v19 + 40 * v18 + 32);
          if ( v20 )
            v20(*(_QWORD *)(v19 + 40 * v18 + 16));
          *(_QWORD *)(v19 + 40 * v18 + 24) = 0;
        }
        ++v18;
      }
      while ( v18 != 3 );
      v7 = a4;
    }
  }
  LOBYTE(v14) = v10;
  v21 = sqlite3FindCollSeq(a1, v14, v8, 1);
  if ( !v21 )
    return 7;
  *(_QWORD *)(v21 + 24) = a5;
  *(_QWORD *)(v21 + 32) = a6;
  *(_QWORD *)(v21 + 16) = v7;
  *(_BYTE *)(v21 + 8) = v10 | a3 & 8;
  sqlite3Error(a1, 0);
  return 0;
}

```

## disassembly

```asm
0x18005b800  mov     [rsp+arg_18], r9
0x18005b805  push    rbx
0x18005b806  push    rbp
0x18005b807  push    rsi
0x18005b808  push    rdi
0x18005b809  push    r12
0x18005b80b  push    r13
0x18005b80d  push    r14
0x18005b80f  push    r15
0x18005b811  sub     rsp, 28h
0x18005b815  movzx   esi, r8b
0x18005b819  mov     rbp, r9
0x18005b81c  mov     r12, rdx
0x18005b81f  mov     rdi, rcx
0x18005b822  mov     ebx, esi
0x18005b824  cmp     esi, 4
0x18005b827  jz      short loc_18005B851
0x18005b829  cmp     ebx, 8
0x18005b82c  jz      short loc_18005B851
0x18005b82e  lea     eax, [rsi-1]
0x18005b831  cmp     eax, 2
0x18005b834  jbe     short loc_18005B856
0x18005b836  lea     r8, aMisuse; "misuse"
0x18005b83d  mov     edx, 2C92Fh
0x18005b842  mov     ecx, 15h
0x18005b847  call    sqlite3ReportError
0x18005b84c  jmp     loc_18005B95C
0x18005b851  mov     ebx, 2
0x18005b856  xor     r9d, r9d
0x18005b859  mov     r8, r12
0x18005b85c  mov     dl, bl
0x18005b85e  call    sqlite3FindCollSeq
0x18005b863  mov     r13, rax
0x18005b866  test    rax, rax
0x18005b869  jz      loc_18005B909
0x18005b86f  cmp     qword ptr [rax+18h], 0
0x18005b874  jz      loc_18005B909
0x18005b87a  cmp     dword ptr [rdi+0D8h], 0
0x18005b881  mov     rcx, rdi
0x18005b884  jz      short loc_18005B8A0
0x18005b886  mov     ebx, 5
0x18005b88b  lea     r8, aUnableToDelete; "unable to delete/modify collation seque"...
0x18005b892  mov     edx, ebx
0x18005b894  call    sqlite3ErrorWithMsg
0x18005b899  mov     eax, ebx
0x18005b89b  jmp     loc_18005B95C
0x18005b8a0  xor     edx, edx
0x18005b8a2  call    sqlite3ExpirePreparedStatements
0x18005b8a7  movzx   eax, byte ptr [r13+8]
0x18005b8ac  and     eax, 0FFFFFFF7h
0x18005b8af  cmp     eax, ebx
0x18005b8b1  jnz     short loc_18005B909
0x18005b8b3  lea     rcx, [rdi+270h]
0x18005b8ba  xor     r8d, r8d
0x18005b8bd  mov     rdx, r12
0x18005b8c0  call    findElementWithHash
0x18005b8c5  xor     r14d, r14d
0x18005b8c8  mov     r15, [rax+10h]
0x18005b8cc  mov     al, [r13+8]
0x18005b8d0  lea     rbp, [r14+r14*4]
0x18005b8d4  cmp     [r15+rbp*8+8], al
0x18005b8d9  jnz     short loc_18005B8F8
0x18005b8db  mov     rax, [r15+rbp*8+20h]
0x18005b8e0  test    rax, rax
0x18005b8e3  jz      short loc_18005B8EF
0x18005b8e5  mov     rcx, [r15+rbp*8+10h]
0x18005b8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8ef  mov     qword ptr [r15+rbp*8+18h], 0
0x18005b8f8  inc     r14
0x18005b8fb  cmp     r14, 3
0x18005b8ff  jnz     short loc_18005B8CC
0x18005b901  mov     rbp, [rsp+68h+arg_18]
0x18005b909  mov     r9d, 1
0x18005b90f  mov     r8, r12
0x18005b912  mov     dl, bl
0x18005b914  mov     rcx, rdi
0x18005b917  call    sqlite3FindCollSeq
0x18005b91c  mov     rcx, rax
0x18005b91f  test    rax, rax
0x18005b922  jnz     short loc_18005B929
0x18005b924  lea     eax, [rcx+7]
0x18005b927  jmp     short loc_18005B95C
0x18005b929  mov     rax, [rsp+68h+arg_20]
0x18005b931  and     sil, 8
0x18005b935  mov     [rcx+18h], rax
0x18005b939  or      sil, bl
0x18005b93c  mov     rax, [rsp+68h+arg_28]
0x18005b944  xor     edx, edx
0x18005b946  mov     [rcx+20h], rax
0x18005b94a  mov     [rcx+10h], rbp
0x18005b94e  mov     [rcx+8], sil
0x18005b952  mov     rcx, rdi
0x18005b955  call    sqlite3Error
0x18005b95a  xor     eax, eax
0x18005b95c  add     rsp, 28h
0x18005b960  pop     r15
0x18005b962  pop     r14
0x18005b964  pop     r13
0x18005b966  pop     r12
0x18005b968  pop     rdi
0x18005b969  pop     rsi
0x18005b96a  pop     rbp
0x18005b96b  pop     rbx
0x18005b96c  retn
```
