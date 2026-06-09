# createCollation

- ea: `0x180037b34`
- end: `0x180037ce7`
- name: `createCollation`
- size: `435`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18003182c`
- `0x1800379d0`
- `0x18005ee40`
- `0x18009b340`

## callees

- `0x180009760`
- `0x180011a10`
- `0x180020928`
- `0x1800257e0`
- `0x1800272fc`
- `0x180031f78`
- `0x180037b34`
- `0x1800b0010`

## string_xrefs

- `0x180037c16`: `unable to delete/modify collation sequence due to active statements`

## pseudocode

```c
__int64 __fastcall createCollation(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v7; // rbp
  __int64 v8; // r12
  int v10; // edi
  __int64 v11; // r8
  __int64 CollSeq; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r13
  __int64 v16; // rax
  bool v17; // zf
  __int64 v19; // r14
  __int64 v20; // r15
  void (__fastcall *v21)(_QWORD); // rax

  v7 = a4;
  v8 = a2;
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
      183006,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    return 21;
  }
  v11 = a2;
  LOBYTE(a2) = v10;
  CollSeq = sqlite3FindCollSeq(a1, a2, v11, 0);
  v15 = CollSeq;
  if ( CollSeq && *(_QWORD *)(CollSeq + 24) )
  {
    if ( *(_DWORD *)(a1 + 216) )
    {
      sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify collation sequence due to active statements");
      return 5;
    }
    sqlite3ExpirePreparedStatements(a1, 0, v14);
    if ( (*(_BYTE *)(v15 + 8) & 0xF7) == v10 )
    {
      v19 = 0;
      v20 = *(_QWORD *)(findElementWithHash(a1 + 624, v8, 0) + 16);
      do
      {
        if ( *(_BYTE *)(v20 + 40 * v19 + 8) == *(_BYTE *)(v15 + 8) )
        {
          v21 = *(void (__fastcall **)(_QWORD))(v20 + 40 * v19 + 32);
          if ( v21 )
            v21(*(_QWORD *)(v20 + 40 * v19 + 16));
          *(_QWORD *)(v20 + 40 * v19 + 24) = 0;
        }
        ++v19;
      }
      while ( v19 != 3 );
      v7 = a4;
    }
  }
  LOBYTE(v13) = v10;
  v16 = sqlite3FindCollSeq(a1, v13, v8, 1);
  if ( !v16 )
    return 7;
  *(_QWORD *)(v16 + 24) = a5;
  *(_QWORD *)(v16 + 32) = a6;
  *(_QWORD *)(v16 + 16) = v7;
  *(_BYTE *)(v16 + 8) = v10 | a3 & 8;
  v17 = *(_QWORD *)(a1 + 400) == 0;
  *(_DWORD *)(a1 + 80) = 0;
  if ( v17 )
    *(_DWORD *)(a1 + 84) = -1;
  else
    sqlite3ErrorFinish(a1, 0);
  return 0;
}

```

## disassembly

```asm
0x180037b34  mov     [rsp+arg_18], r9
0x180037b39  push    rbx
0x180037b3a  push    rbp
0x180037b3b  push    rsi
0x180037b3c  push    rdi
0x180037b3d  push    r12
0x180037b3f  push    r13
0x180037b41  push    r14
0x180037b43  push    r15
0x180037b45  sub     rsp, 38h
0x180037b49  movzx   esi, r8b
0x180037b4d  mov     rbp, r9
0x180037b50  mov     r12, rdx
0x180037b53  mov     rbx, rcx
0x180037b56  mov     edi, esi
0x180037b58  cmp     esi, 4
0x180037b5b  jz      loc_180037C6B
0x180037b61  cmp     esi, 8
0x180037b64  jz      loc_180037C6B
0x180037b6a  lea     eax, [rsi-1]
0x180037b6d  cmp     eax, 2
0x180037b70  ja      loc_180037C34
0x180037b76  xor     r9d, r9d
0x180037b79  mov     r8, r12
0x180037b7c  mov     dl, dil
0x180037b7f  call    sqlite3FindCollSeq
0x180037b84  mov     r13, rax
0x180037b87  test    rax, rax
0x180037b8a  jnz     short loc_180037BFE
0x180037b8c  mov     r9d, 1
0x180037b92  mov     r8, r12
0x180037b95  mov     dl, dil
0x180037b98  mov     rcx, rbx
0x180037b9b  call    sqlite3FindCollSeq
0x180037ba0  mov     rcx, rax
0x180037ba3  test    rax, rax
0x180037ba6  jz      loc_180037C64
0x180037bac  mov     rax, [rsp+78h+arg_20]
0x180037bb4  and     sil, 8
0x180037bb8  mov     [rcx+18h], rax
0x180037bbc  or      sil, dil
0x180037bbf  mov     rax, [rsp+78h+arg_28]
0x180037bc7  mov     [rcx+20h], rax
0x180037bcb  mov     [rcx+10h], rbp
0x180037bcf  mov     [rcx+8], sil
0x180037bd3  cmp     qword ptr [rbx+190h], 0
0x180037bdb  mov     dword ptr [rbx+50h], 0
0x180037be2  jnz     short loc_180037C28
0x180037be4  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x180037beb  xor     eax, eax
0x180037bed  add     rsp, 38h
0x180037bf1  pop     r15
0x180037bf3  pop     r14
0x180037bf5  pop     r13
0x180037bf7  pop     r12
0x180037bf9  pop     rdi
0x180037bfa  pop     rsi
0x180037bfb  pop     rbp
0x180037bfc  pop     rbx
0x180037bfd  retn
0x180037bfe  cmp     qword ptr [rax+18h], 0
0x180037c03  jz      short loc_180037B8C
0x180037c05  cmp     dword ptr [rbx+0D8h], 0
0x180037c0c  mov     rcx, rbx
0x180037c0f  jz      short loc_180037C75
0x180037c11  mov     edi, 5
0x180037c16  lea     r8, aUnableToDelete; "unable to delete/modify collation seque"...
0x180037c1d  mov     edx, edi
0x180037c1f  call    sqlite3ErrorWithMsg
0x180037c24  mov     eax, edi
0x180037c26  jmp     short loc_180037BED
0x180037c28  xor     edx, edx
0x180037c2a  mov     rcx, rbx
0x180037c2d  call    sqlite3ErrorFinish
0x180037c32  jmp     short loc_180037BEB
0x180037c34  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x180037c3b  mov     ebx, 15h
0x180037c40  mov     ecx, ebx
0x180037c42  mov     [rsp+78h+var_58], rax
0x180037c47  mov     r9d, 2CADEh
0x180037c4d  lea     r8, aMisuse; "misuse"
0x180037c54  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180037c5b  call    sqlite3_log
0x180037c60  mov     eax, ebx
0x180037c62  jmp     short loc_180037BED
0x180037c64  mov     eax, 7
0x180037c69  jmp     short loc_180037BED
0x180037c6b  mov     edi, 2
0x180037c70  jmp     loc_180037B76
0x180037c75  xor     edx, edx
0x180037c77  call    sqlite3ExpirePreparedStatements
0x180037c7c  movzx   eax, byte ptr [r13+8]
0x180037c81  and     eax, 0FFFFFFF7h
0x180037c84  cmp     eax, edi
0x180037c86  jnz     loc_180037B8C
0x180037c8c  lea     rcx, [rbx+270h]
0x180037c93  xor     r8d, r8d
0x180037c96  mov     rdx, r12
0x180037c99  call    findElementWithHash
0x180037c9e  xor     r14d, r14d
0x180037ca1  mov     r15, [rax+10h]
0x180037ca5  mov     al, [r13+8]
0x180037ca9  lea     rbp, [r14+r14*4]
0x180037cad  cmp     [r15+rbp*8+8], al
0x180037cb2  jnz     short loc_180037CD1
0x180037cb4  mov     rax, [r15+rbp*8+20h]
0x180037cb9  test    rax, rax
0x180037cbc  jz      short loc_180037CC8
0x180037cbe  mov     rcx, [r15+rbp*8+10h]
0x180037cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cc8  mov     qword ptr [r15+rbp*8+18h], 0
0x180037cd1  inc     r14
0x180037cd4  cmp     r14, 3
0x180037cd8  jnz     short loc_180037CA5
0x180037cda  mov     rbp, [rsp+78h+arg_18]
0x180037ce2  jmp     loc_180037B8C
```
