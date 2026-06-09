# triggersReallyExist

- ea: `0x180051998`
- end: `0x180051aca`
- name: `triggersReallyExist`
- size: `306`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180008c0c`
- `0x18000a954`
- `0x180019470`
- `0x1800504a8`

## callees

- `0x180011bcc`
- `0x180051998`
- `0x18006d2b8`
- `0x1800748ac`

## string_xrefs

- `0x180051a48`: `DELETE`
- `0x180051a41`: `UPDATE`

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
0x180051998  push    rbx
0x18005199a  push    rbp
0x18005199b  push    rsi
0x18005199c  push    rdi
0x18005199d  push    r12
0x18005199f  push    r13
0x1800519a1  push    r14
0x1800519a3  push    r15
0x1800519a5  sub     rsp, 28h
0x1800519a9  mov     r12, r9
0x1800519ac  mov     r14d, r8d
0x1800519af  mov     r13, rdx
0x1800519b2  mov     r15, rcx
0x1800519b5  xor     edi, edi
0x1800519b7  call    sqlite3TriggerList
0x1800519bc  mov     rsi, rax
0x1800519bf  test    rax, rax
0x1800519c2  jz      loc_180051AA2
0x1800519c8  mov     r10, [r15]
0x1800519cb  mov     r9d, [r10+30h]
0x1800519cf  bt      r9, 12h
0x1800519d4  jb      short loc_180051A07
0x1800519d6  mov     rcx, [r13+58h]
0x1800519da  test    rcx, rcx
0x1800519dd  jz      short loc_180051A07
0x1800519df  cmp     rax, rcx
0x1800519e2  jnz     short loc_1800519EB
0x1800519e4  xor     esi, esi
0x1800519e6  jmp     loc_180051AA2
0x1800519eb  cmp     [rax+40h], rdi
0x1800519ef  jz      short loc_180051A03
0x1800519f1  mov     rdx, [rax+40h]
0x1800519f5  cmp     rdx, rcx
0x1800519f8  jz      short loc_180051A03
0x1800519fa  mov     rax, rdx
0x1800519fd  cmp     [rdx+40h], rdi
0x180051a01  jnz     short loc_1800519F1
0x180051a03  mov     [rax+40h], rdi
0x180051a07  mov     rbx, rsi
0x180051a0a  movzx   ebp, byte ptr [rbx+10h]
0x180051a0e  cmp     ebp, r14d
0x180051a11  jnz     short loc_180051A23
0x180051a13  mov     rcx, [rbx+20h]
0x180051a17  mov     rdx, r12
0x180051a1a  call    checkColumnOverlap
0x180051a1f  test    eax, eax
0x180051a21  jnz     short loc_180051A8F
0x180051a23  cmp     bpl, 96h
0x180051a27  jnz     short loc_180051A70
0x180051a29  mov     [rbx+10h], r14b
0x180051a2d  cmp     byte ptr [r13+3Fh], 1
0x180051a32  jnz     short loc_180051A66
0x180051a34  cmp     r14d, 7Fh
0x180051a38  jz      short loc_180051A62
0x180051a3a  cmp     r14d, 80h
0x180051a41  lea     rax, aUpdate; "UPDATE"
0x180051a48  lea     r8, aDelete; "DELETE"
0x180051a4f  mov     rcx, r15
0x180051a52  cmovnz  r8, rax
0x180051a56  lea     rdx, aSReturningIsNo; "%s RETURNING is not available on virtua"...
0x180051a5d  call    sqlite3ErrorMsg
0x180051a62  mov     al, 1
0x180051a64  jmp     short loc_180051A68
0x180051a66  mov     al, 2
0x180051a68  mov     [rbx+11h], al
0x180051a6b  movzx   eax, al
0x180051a6e  jmp     short loc_180051A93
0x180051a70  cmp     byte ptr [rbx+12h], 0
0x180051a74  jz      short loc_180051A95
0x180051a76  cmp     bpl, 7Fh
0x180051a7a  jnz     short loc_180051A95
0x180051a7c  cmp     r14d, 81h
0x180051a83  jnz     short loc_180051A95
0x180051a85  cmp     qword ptr [r15+0B0h], 0
0x180051a8d  jnz     short loc_180051A95
0x180051a8f  movzx   eax, byte ptr [rbx+11h]
0x180051a93  or      edi, eax
0x180051a95  mov     rbx, [rbx+40h]
0x180051a99  test    rbx, rbx
0x180051a9c  jnz     loc_180051A0A
0x180051aa2  mov     rax, [rsp+68h+arg_20]
0x180051aaa  test    rax, rax
0x180051aad  jz      short loc_180051AB1
0x180051aaf  mov     [rax], edi
0x180051ab1  neg     edi
0x180051ab3  sbb     rax, rax
0x180051ab6  and     rax, rsi
0x180051ab9  add     rsp, 28h
0x180051abd  pop     r15
0x180051abf  pop     r14
0x180051ac1  pop     r13
0x180051ac3  pop     r12
0x180051ac5  pop     rdi
0x180051ac6  pop     rsi
0x180051ac7  pop     rbp
0x180051ac8  pop     rbx
0x180051ac9  retn
```
