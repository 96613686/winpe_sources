# triggersReallyExist

- ea: `0x180063dc8`
- end: `0x180063efd`
- name: `triggersReallyExist`
- size: `309`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x1800167c0`
- `0x1800189c8`
- `0x180019e50`
- `0x180063d84`

## callees

- `0x180055de8`
- `0x18005ee1c`
- `0x180060ce8`
- `0x180063dc8`

## string_xrefs

- `0x180063e7b`: `DELETE`
- `0x180063e74`: `UPDATE`

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
        if ( (_BYTE)v15 == 0x97 )
        {
          *(_BYTE *)(v14 + 16) = a3;
          if ( *(_BYTE *)(a2 + 63) == 1 )
          {
            if ( a3 != 128 )
            {
              v16 = "DELETE";
              if ( a3 != 129 )
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
        if ( !*(_BYTE *)(v14 + 18) || (_BYTE)v15 != 0x80 || a3 != 130 || a1[22] )
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
0x180063dc8  push    rbx
0x180063dca  push    rbp
0x180063dcb  push    rsi
0x180063dcc  push    rdi
0x180063dcd  push    r12
0x180063dcf  push    r13
0x180063dd1  push    r14
0x180063dd3  push    r15
0x180063dd5  sub     rsp, 28h
0x180063dd9  mov     r12, r9
0x180063ddc  mov     r14d, r8d
0x180063ddf  mov     r13, rdx
0x180063de2  mov     r15, rcx
0x180063de5  xor     edi, edi
0x180063de7  call    sqlite3TriggerList
0x180063dec  mov     rsi, rax
0x180063def  test    rax, rax
0x180063df2  jz      loc_180063ED5
0x180063df8  mov     r10, [r15]
0x180063dfb  mov     r9d, [r10+30h]
0x180063dff  bt      r9, 12h
0x180063e04  jb      short loc_180063E37
0x180063e06  mov     rcx, [r13+58h]
0x180063e0a  test    rcx, rcx
0x180063e0d  jz      short loc_180063E37
0x180063e0f  cmp     rax, rcx
0x180063e12  jnz     short loc_180063E1B
0x180063e14  xor     esi, esi
0x180063e16  jmp     loc_180063ED5
0x180063e1b  cmp     [rax+40h], rdi
0x180063e1f  jz      short loc_180063E33
0x180063e21  mov     rdx, [rax+40h]
0x180063e25  cmp     rdx, rcx
0x180063e28  jz      short loc_180063E33
0x180063e2a  mov     rax, rdx
0x180063e2d  cmp     [rdx+40h], rdi
0x180063e31  jnz     short loc_180063E21
0x180063e33  mov     [rax+40h], rdi
0x180063e37  mov     rbx, rsi
0x180063e3a  movzx   ebp, byte ptr [rbx+10h]
0x180063e3e  cmp     ebp, r14d
0x180063e41  jnz     short loc_180063E53
0x180063e43  mov     rcx, [rbx+20h]
0x180063e47  mov     rdx, r12
0x180063e4a  call    checkColumnOverlap
0x180063e4f  test    eax, eax
0x180063e51  jnz     short loc_180063EC2
0x180063e53  cmp     bpl, 97h
0x180063e57  jnz     short loc_180063EA3
0x180063e59  mov     [rbx+10h], r14b
0x180063e5d  cmp     byte ptr [r13+3Fh], 1
0x180063e62  jnz     short loc_180063E99
0x180063e64  cmp     r14d, 80h
0x180063e6b  jz      short loc_180063E95
0x180063e6d  cmp     r14d, 81h
0x180063e74  lea     rax, aUpdate; "UPDATE"
0x180063e7b  lea     r8, aDelete; "DELETE"
0x180063e82  mov     rcx, r15
0x180063e85  cmovnz  r8, rax
0x180063e89  lea     rdx, aSReturningIsNo; "%s RETURNING is not available on virtua"...
0x180063e90  call    sqlite3ErrorMsg
0x180063e95  mov     al, 1
0x180063e97  jmp     short loc_180063E9B
0x180063e99  mov     al, 2
0x180063e9b  mov     [rbx+11h], al
0x180063e9e  movzx   eax, al
0x180063ea1  jmp     short loc_180063EC6
0x180063ea3  cmp     byte ptr [rbx+12h], 0
0x180063ea7  jz      short loc_180063EC8
0x180063ea9  cmp     bpl, 80h
0x180063ead  jnz     short loc_180063EC8
0x180063eaf  cmp     r14d, 82h
0x180063eb6  jnz     short loc_180063EC8
0x180063eb8  cmp     qword ptr [r15+0B0h], 0
0x180063ec0  jnz     short loc_180063EC8
0x180063ec2  movzx   eax, byte ptr [rbx+11h]
0x180063ec6  or      edi, eax
0x180063ec8  mov     rbx, [rbx+40h]
0x180063ecc  test    rbx, rbx
0x180063ecf  jnz     loc_180063E3A
0x180063ed5  mov     rax, [rsp+68h+arg_20]
0x180063edd  test    rax, rax
0x180063ee0  jz      short loc_180063EE4
0x180063ee2  mov     [rax], edi
0x180063ee4  neg     edi
0x180063ee6  sbb     rax, rax
0x180063ee9  and     rax, rsi
0x180063eec  add     rsp, 28h
0x180063ef0  pop     r15
0x180063ef2  pop     r14
0x180063ef4  pop     r13
0x180063ef6  pop     r12
0x180063ef8  pop     rdi
0x180063ef9  pop     rsi
0x180063efa  pop     rbp
0x180063efb  pop     rbx
0x180063efc  retn
```
