# createCollation

- ea: `0x180004194`
- end: `0x180004397`
- name: `createCollation`
- size: `515`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180001fbc`
- `0x18008d7a0`
- `0x18008d860`

## callees

- `0x180004194`
- `0x180005460`
- `0x180016250`
- `0x1800275f0`
- `0x1800284f8`
- `0x180054798`
- `0x18005cf6c`
- `0x18009a010`

## string_xrefs

- `0x1800042ee`: `unable to delete/modify collation sequence due to active statements`

## pseudocode

```c
__int64 __fastcall createCollation(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v7; // r14
  unsigned int v10; // esi
  __int64 v11; // rdi
  __int64 v12; // rcx
  bool v13; // zf
  __int64 v14; // rax
  __int64 CollSeqEntry; // rax
  __int64 v17; // r14
  __int64 v18; // r13
  void (__fastcall *v19)(_QWORD); // rax

  v7 = a4;
  v10 = a3;
  if ( a3 == 4 || a3 == 8 )
  {
    v10 = 2;
  }
  else if ( (unsigned int)a3 - 1 > 2 )
  {
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      183895,
      "2aabe05e2e8cae4847a802ee2daddc1d7413d8fc560254d93ee3e72c14685b6c");
    return 21;
  }
  if ( a2 )
  {
    CollSeqEntry = findCollSeqEntry(a1, a2, 0);
    v11 = CollSeqEntry;
    if ( CollSeqEntry )
      v11 = CollSeqEntry + 40 * (v10 - 1LL);
  }
  else
  {
    v11 = *(_QWORD *)(a1 + 16);
  }
  if ( v11 && *(_QWORD *)(v11 + 24) )
  {
    if ( *(_DWORD *)(a1 + 216) )
    {
      sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify collation sequence due to active statements", a4);
      return 5;
    }
    sqlite3ExpirePreparedStatements(a1, 0);
    if ( (*(_BYTE *)(v11 + 8) & 0xF7) == v10 )
    {
      v17 = 0;
      v18 = *(_QWORD *)(findElementWithHash(a1 + 624, a2, 0) + 16);
      do
      {
        if ( *(_BYTE *)(v18 + 40 * v17 + 8) == *(_BYTE *)(v11 + 8) )
        {
          v19 = *(void (__fastcall **)(_QWORD))(v18 + 40 * v17 + 32);
          if ( v19 )
            v19(*(_QWORD *)(v18 + 40 * v17 + 16));
          *(_QWORD *)(v18 + 40 * v17 + 24) = 0;
        }
        ++v17;
      }
      while ( v17 != 3 );
      v7 = a4;
    }
  }
  if ( a2 )
  {
    v14 = findCollSeqEntry(a1, a2, 1);
    if ( !v14 )
      return 7;
    v12 = v14 + 8 * (5LL * v10 - 5);
  }
  else
  {
    v12 = *(_QWORD *)(a1 + 16);
  }
  if ( !v12 )
    return 7;
  *(_QWORD *)(v12 + 24) = a5;
  *(_QWORD *)(v12 + 32) = a6;
  *(_QWORD *)(v12 + 16) = v7;
  *(_BYTE *)(v12 + 8) = v10 | a3 & 8;
  v13 = *(_QWORD *)(a1 + 400) == 0;
  *(_DWORD *)(a1 + 80) = 0;
  if ( v13 )
    *(_DWORD *)(a1 + 84) = -1;
  else
    sqlite3ErrorFinish(a1, 0);
  return 0;
}

```

## disassembly

```asm
0x180004194  mov     [rsp+arg_18], r9
0x180004199  push    rbx
0x18000419a  push    rbp
0x18000419b  push    rsi
0x18000419c  push    rdi
0x18000419d  push    r12
0x18000419f  push    r13
0x1800041a1  push    r14
0x1800041a3  push    r15
0x1800041a5  sub     rsp, 38h
0x1800041a9  movzx   r15d, r8b
0x1800041ad  mov     r14, r9
0x1800041b0  mov     rbp, rdx
0x1800041b3  mov     rbx, rcx
0x1800041b6  mov     esi, r15d
0x1800041b9  cmp     r15d, 4
0x1800041bd  jz      loc_1800042D3
0x1800041c3  cmp     r15d, 8
0x1800041c7  jz      loc_1800042D3
0x1800041cd  lea     eax, [r15-1]
0x1800041d1  cmp     eax, 2
0x1800041d4  ja      loc_1800042A3
0x1800041da  test    rbp, rbp
0x1800041dd  jnz     loc_18000427D
0x1800041e3  mov     rdi, [rcx+10h]
0x1800041e7  test    rdi, rdi
0x1800041ea  jz      short loc_1800041F7
0x1800041ec  cmp     qword ptr [rdi+18h], 0
0x1800041f1  jnz     loc_1800042DD
0x1800041f7  test    rbp, rbp
0x1800041fa  jnz     short loc_18000424D
0x1800041fc  mov     rcx, [rbx+10h]
0x180004200  test    rcx, rcx
0x180004203  jz      short loc_180004267
0x180004205  mov     rax, [rsp+78h+arg_20]
0x18000420d  and     r15b, 8
0x180004211  mov     [rcx+18h], rax
0x180004215  or      r15b, sil
0x180004218  mov     rax, [rsp+78h+arg_28]
0x180004220  mov     [rcx+20h], rax
0x180004224  mov     [rcx+10h], r14
0x180004228  mov     [rcx+8], r15b
0x18000422c  cmp     qword ptr [rbx+190h], 0
0x180004234  mov     dword ptr [rbx+50h], 0
0x18000423b  jnz     loc_180004386
0x180004241  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x180004248  jmp     loc_180004390
0x18000424d  mov     r8d, 1
0x180004253  mov     rdx, rbp
0x180004256  mov     rcx, rbx
0x180004259  call    findCollSeqEntry
0x18000425e  test    rax, rax
0x180004261  jnz     loc_180004373
0x180004267  mov     eax, 7
0x18000426c  add     rsp, 38h
0x180004270  pop     r15
0x180004272  pop     r14
0x180004274  pop     r13
0x180004276  pop     r12
0x180004278  pop     rdi
0x180004279  pop     rsi
0x18000427a  pop     rbp
0x18000427b  pop     rbx
0x18000427c  retn
0x18000427d  xor     r8d, r8d
0x180004280  call    findCollSeqEntry
0x180004285  mov     rdi, rax
0x180004288  test    rax, rax
0x18000428b  jz      loc_1800041E7
0x180004291  mov     edi, esi
0x180004293  dec     rdi
0x180004296  lea     rdi, [rdi+rdi*4]
0x18000429a  lea     rdi, [rax+rdi*8]
0x18000429e  jmp     loc_1800041E7
0x1800042a3  lea     rax, a20241207203959+14h; "2aabe05e2e8cae4847a802ee2daddc1d7413d8f"...
0x1800042aa  mov     ebx, 15h
0x1800042af  mov     ecx, ebx
0x1800042b1  mov     [rsp+78h+var_58], rax
0x1800042b6  mov     r9d, 2CE57h
0x1800042bc  lea     r8, aMisuse; "misuse"
0x1800042c3  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x1800042ca  call    sqlite3_log
0x1800042cf  mov     eax, ebx
0x1800042d1  jmp     short loc_18000426C
0x1800042d3  mov     esi, 2
0x1800042d8  jmp     loc_1800041DA
0x1800042dd  cmp     dword ptr [rbx+0D8h], 0
0x1800042e4  mov     rcx, rbx
0x1800042e7  jz      short loc_180004303
0x1800042e9  mov     edi, 5
0x1800042ee  lea     r8, aUnableToDelete; "unable to delete/modify collation seque"...
0x1800042f5  mov     edx, edi
0x1800042f7  call    sqlite3ErrorWithMsg
0x1800042fc  mov     eax, edi
0x1800042fe  jmp     loc_18000426C
0x180004303  xor     edx, edx
0x180004305  call    sqlite3ExpirePreparedStatements
0x18000430a  movzx   eax, byte ptr [rdi+8]
0x18000430e  and     eax, 0FFFFFFF7h
0x180004311  cmp     eax, esi
0x180004313  jnz     loc_1800041F7
0x180004319  lea     rcx, [rbx+270h]
0x180004320  xor     r8d, r8d
0x180004323  mov     rdx, rbp
0x180004326  call    findElementWithHash
0x18000432b  xor     r14d, r14d
0x18000432e  mov     r13, [rax+10h]
0x180004332  mov     al, [rdi+8]
0x180004335  lea     r12, [r14+r14*4]
0x180004339  cmp     [r13+r12*8+8], al
0x18000433e  jnz     short loc_18000435D
0x180004340  mov     rax, [r13+r12*8+20h]
0x180004345  test    rax, rax
0x180004348  jz      short loc_180004354
0x18000434a  mov     rcx, [r13+r12*8+10h]
0x18000434f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004354  mov     qword ptr [r13+r12*8+18h], 0
0x18000435d  inc     r14
0x180004360  cmp     r14, 3
0x180004364  jnz     short loc_180004332
0x180004366  mov     r14, [rsp+78h+arg_18]
0x18000436e  jmp     loc_1800041F7
0x180004373  mov     ecx, esi
0x180004375  lea     rcx, [rcx+rcx*4]
0x180004379  lea     rcx, [rcx-5]
0x18000437d  lea     rcx, [rax+rcx*8]
0x180004381  jmp     loc_180004200
0x180004386  xor     edx, edx
0x180004388  mov     rcx, rbx
0x18000438b  call    sqlite3ErrorFinish
0x180004390  xor     eax, eax
0x180004392  jmp     loc_18000426C
```
