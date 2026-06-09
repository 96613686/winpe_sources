# triggersReallyExist

- ea: `0x1800b1a74`
- end: `0x1800b1ba6`
- name: `triggersReallyExist`
- size: `306`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180071d34`
- `0x18007ab30`
- `0x18007e280`
- `0x18008fe18`

## callees

- `0x18003c1ec`
- `0x180073aec`
- `0x18008f71c`
- `0x1800b1a74`

## string_xrefs

- `0x1800b1b24`: `DELETE`
- `0x1800b1b1d`: `UPDATE`

## pseudocode

```c
__int64 __fastcall triggersReallyExist(_QWORD *a1, __int64 a2, int a3, __int64 a4, _DWORD *a5)
{
  int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rbx
  int v15; // ebp
  const char *v16; // r8
  int v17; // eax

  v9 = 0;
  v10 = sqlite3TriggerList(a1, a2);
  v11 = v10;
  if ( v10 )
  {
    if ( (*(_DWORD *)(*a1 + 48LL) & 0x40000LL) == 0 )
    {
      v12 = *(_QWORD *)(a2 + 88);
      if ( v12 )
      {
        if ( v10 == v12 )
        {
          v11 = 0;
          goto LABEL_29;
        }
        if ( *(_QWORD *)(v10 + 64) )
        {
          do
          {
            v13 = *(_QWORD *)(v10 + 64);
            if ( v13 == v12 )
              break;
            v10 = *(_QWORD *)(v10 + 64);
          }
          while ( *(_QWORD *)(v13 + 64) );
        }
        *(_QWORD *)(v10 + 64) = 0;
      }
    }
    v14 = v11;
    do
    {
      v15 = *(unsigned __int8 *)(v14 + 16);
      if ( v15 != a3 || !(unsigned int)checkColumnOverlap(*(_QWORD *)(v14 + 32), a4) )
      {
        if ( (_BYTE)v15 == 0x96 )
        {
          *(_BYTE *)(v14 + 16) = a3;
          if ( *(_BYTE *)(a2 + 63) == 1 )
          {
            if ( a3 != 127 )
            {
              v16 = "DELETE";
              if ( a3 != 128 )
                v16 = "UPDATE";
              sqlite3ErrorMsg(a1, "%s RETURNING is not available on virtual tables", v16);
            }
            LOBYTE(v17) = 1;
          }
          else
          {
            LOBYTE(v17) = 2;
          }
          *(_BYTE *)(v14 + 17) = v17;
          v17 = (unsigned __int8)v17;
          goto LABEL_27;
        }
        if ( !*(_BYTE *)(v14 + 18) || (_BYTE)v15 != 127 || a3 != 129 || a1[22] )
          goto LABEL_28;
      }
      v17 = *(unsigned __int8 *)(v14 + 17);
LABEL_27:
      v9 |= v17;
LABEL_28:
      v14 = *(_QWORD *)(v14 + 64);
    }
    while ( v14 );
  }
LABEL_29:
  if ( a5 )
    *a5 = v9;
  return v11 & -(__int64)(v9 != 0);
}

```

## disassembly

```asm
0x1800b1a74  push    rbx
0x1800b1a76  push    rbp
0x1800b1a77  push    rsi
0x1800b1a78  push    rdi
0x1800b1a79  push    r12
0x1800b1a7b  push    r13
0x1800b1a7d  push    r14
0x1800b1a7f  push    r15
0x1800b1a81  sub     rsp, 28h
0x1800b1a85  mov     r12, r9
0x1800b1a88  mov     r14d, r8d
0x1800b1a8b  mov     r13, rdx
0x1800b1a8e  mov     r15, rcx
0x1800b1a91  xor     edi, edi
0x1800b1a93  call    sqlite3TriggerList
0x1800b1a98  mov     rsi, rax
0x1800b1a9b  test    rax, rax
0x1800b1a9e  jz      loc_1800B1B7E
0x1800b1aa4  mov     r10, [r15]
0x1800b1aa7  mov     r9d, [r10+30h]
0x1800b1aab  bt      r9, 12h
0x1800b1ab0  jb      short loc_1800B1AE3
0x1800b1ab2  mov     rcx, [r13+58h]
0x1800b1ab6  test    rcx, rcx
0x1800b1ab9  jz      short loc_1800B1AE3
0x1800b1abb  cmp     rax, rcx
0x1800b1abe  jnz     short loc_1800B1AC7
0x1800b1ac0  xor     esi, esi
0x1800b1ac2  jmp     loc_1800B1B7E
0x1800b1ac7  cmp     [rax+40h], rdi
0x1800b1acb  jz      short loc_1800B1ADF
0x1800b1acd  mov     rdx, [rax+40h]
0x1800b1ad1  cmp     rdx, rcx
0x1800b1ad4  jz      short loc_1800B1ADF
0x1800b1ad6  mov     rax, rdx
0x1800b1ad9  cmp     [rdx+40h], rdi
0x1800b1add  jnz     short loc_1800B1ACD
0x1800b1adf  mov     [rax+40h], rdi
0x1800b1ae3  mov     rbx, rsi
0x1800b1ae6  movzx   ebp, byte ptr [rbx+10h]
0x1800b1aea  cmp     ebp, r14d
0x1800b1aed  jnz     short loc_1800B1AFF
0x1800b1aef  mov     rcx, [rbx+20h]
0x1800b1af3  mov     rdx, r12
0x1800b1af6  call    checkColumnOverlap
0x1800b1afb  test    eax, eax
0x1800b1afd  jnz     short loc_1800B1B6B
0x1800b1aff  cmp     bpl, 96h
0x1800b1b03  jnz     short loc_1800B1B4C
0x1800b1b05  mov     [rbx+10h], r14b
0x1800b1b09  cmp     byte ptr [r13+3Fh], 1
0x1800b1b0e  jnz     short loc_1800B1B42
0x1800b1b10  cmp     r14d, 7Fh
0x1800b1b14  jz      short loc_1800B1B3E
0x1800b1b16  cmp     r14d, 80h
0x1800b1b1d  lea     rax, aUpdate; "UPDATE"
0x1800b1b24  lea     r8, aDelete; "DELETE"
0x1800b1b2b  mov     rcx, r15
0x1800b1b2e  cmovnz  r8, rax
0x1800b1b32  lea     rdx, aSReturningIsNo; "%s RETURNING is not available on virtua"...
0x1800b1b39  call    sqlite3ErrorMsg
0x1800b1b3e  mov     al, 1
0x1800b1b40  jmp     short loc_1800B1B44
0x1800b1b42  mov     al, 2
0x1800b1b44  mov     [rbx+11h], al
0x1800b1b47  movzx   eax, al
0x1800b1b4a  jmp     short loc_1800B1B6F
0x1800b1b4c  cmp     byte ptr [rbx+12h], 0
0x1800b1b50  jz      short loc_1800B1B71
0x1800b1b52  cmp     bpl, 7Fh
0x1800b1b56  jnz     short loc_1800B1B71
0x1800b1b58  cmp     r14d, 81h
0x1800b1b5f  jnz     short loc_1800B1B71
0x1800b1b61  cmp     qword ptr [r15+0B0h], 0
0x1800b1b69  jnz     short loc_1800B1B71
0x1800b1b6b  movzx   eax, byte ptr [rbx+11h]
0x1800b1b6f  or      edi, eax
0x1800b1b71  mov     rbx, [rbx+40h]
0x1800b1b75  test    rbx, rbx
0x1800b1b78  jnz     loc_1800B1AE6
0x1800b1b7e  mov     rax, [rsp+68h+arg_20]
0x1800b1b86  test    rax, rax
0x1800b1b89  jz      short loc_1800B1B8D
0x1800b1b8b  mov     [rax], edi
0x1800b1b8d  neg     edi
0x1800b1b8f  sbb     rax, rax
0x1800b1b92  and     rax, rsi
0x1800b1b95  add     rsp, 28h
0x1800b1b99  pop     r15
0x1800b1b9b  pop     r14
0x1800b1b9d  pop     r13
0x1800b1b9f  pop     r12
0x1800b1ba1  pop     rdi
0x1800b1ba2  pop     rsi
0x1800b1ba3  pop     rbp
0x1800b1ba4  pop     rbx
0x1800b1ba5  retn
```
