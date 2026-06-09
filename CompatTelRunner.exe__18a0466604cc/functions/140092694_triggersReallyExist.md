# triggersReallyExist

- ea: `0x140092694`
- end: `0x1400927c6`
- name: `triggersReallyExist`
- size: `306`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x140054474`
- `0x14005cce4`
- `0x140060400`
- `0x140071358`

## callees

- `0x140021aac`
- `0x1400560c4`
- `0x140070c5c`
- `0x140092694`

## string_xrefs

- `0x14009273d`: `UPDATE`
- `0x140092744`: `DELETE`

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
        if ( !*(_BYTE *)(v14 + 18) || (_BYTE)v15 != 127 || a3 != 129 || a1[21] )
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
0x140092694  push    rbx
0x140092696  push    rbp
0x140092697  push    rsi
0x140092698  push    rdi
0x140092699  push    r12
0x14009269b  push    r13
0x14009269d  push    r14
0x14009269f  push    r15
0x1400926a1  sub     rsp, 28h
0x1400926a5  mov     r12, r9
0x1400926a8  mov     r14d, r8d
0x1400926ab  mov     r13, rdx
0x1400926ae  mov     r15, rcx
0x1400926b1  xor     edi, edi
0x1400926b3  call    sqlite3TriggerList
0x1400926b8  mov     rsi, rax
0x1400926bb  test    rax, rax
0x1400926be  jz      loc_14009279E
0x1400926c4  mov     r10, [r15]
0x1400926c7  mov     r9d, [r10+30h]
0x1400926cb  bt      r9, 12h
0x1400926d0  jb      short loc_140092703
0x1400926d2  mov     rcx, [r13+58h]
0x1400926d6  test    rcx, rcx
0x1400926d9  jz      short loc_140092703
0x1400926db  cmp     rax, rcx
0x1400926de  jnz     short loc_1400926E7
0x1400926e0  xor     esi, esi
0x1400926e2  jmp     loc_14009279E
0x1400926e7  cmp     [rax+40h], rdi
0x1400926eb  jz      short loc_1400926FF
0x1400926ed  mov     rdx, [rax+40h]
0x1400926f1  cmp     rdx, rcx
0x1400926f4  jz      short loc_1400926FF
0x1400926f6  mov     rax, rdx
0x1400926f9  cmp     [rdx+40h], rdi
0x1400926fd  jnz     short loc_1400926ED
0x1400926ff  mov     [rax+40h], rdi
0x140092703  mov     rbx, rsi
0x140092706  movzx   ebp, byte ptr [rbx+10h]
0x14009270a  cmp     ebp, r14d
0x14009270d  jnz     short loc_14009271F
0x14009270f  mov     rcx, [rbx+20h]
0x140092713  mov     rdx, r12
0x140092716  call    checkColumnOverlap
0x14009271b  test    eax, eax
0x14009271d  jnz     short loc_14009278B
0x14009271f  cmp     bpl, 96h
0x140092723  jnz     short loc_14009276C
0x140092725  mov     [rbx+10h], r14b
0x140092729  cmp     byte ptr [r13+3Fh], 1
0x14009272e  jnz     short loc_140092762
0x140092730  cmp     r14d, 7Fh
0x140092734  jz      short loc_14009275E
0x140092736  cmp     r14d, 80h
0x14009273d  lea     rax, aUpdate; "UPDATE"
0x140092744  lea     r8, aDelete; "DELETE"
0x14009274b  mov     rcx, r15
0x14009274e  cmovnz  r8, rax
0x140092752  lea     rdx, aSReturningIsNo; "%s RETURNING is not available on virtua"...
0x140092759  call    sqlite3ErrorMsg
0x14009275e  mov     al, 1
0x140092760  jmp     short loc_140092764
0x140092762  mov     al, 2
0x140092764  mov     [rbx+11h], al
0x140092767  movzx   eax, al
0x14009276a  jmp     short loc_14009278F
0x14009276c  cmp     byte ptr [rbx+12h], 0
0x140092770  jz      short loc_140092791
0x140092772  cmp     bpl, 7Fh
0x140092776  jnz     short loc_140092791
0x140092778  cmp     r14d, 81h
0x14009277f  jnz     short loc_140092791
0x140092781  cmp     qword ptr [r15+0A8h], 0
0x140092789  jnz     short loc_140092791
0x14009278b  movzx   eax, byte ptr [rbx+11h]
0x14009278f  or      edi, eax
0x140092791  mov     rbx, [rbx+40h]
0x140092795  test    rbx, rbx
0x140092798  jnz     loc_140092706
0x14009279e  mov     rax, [rsp+68h+arg_20]
0x1400927a6  test    rax, rax
0x1400927a9  jz      short loc_1400927AD
0x1400927ab  mov     [rax], edi
0x1400927ad  neg     edi
0x1400927af  sbb     rax, rax
0x1400927b2  and     rax, rsi
0x1400927b5  add     rsp, 28h
0x1400927b9  pop     r15
0x1400927bb  pop     r14
0x1400927bd  pop     r13
0x1400927bf  pop     r12
0x1400927c1  pop     rdi
0x1400927c2  pop     rsi
0x1400927c3  pop     rbp
0x1400927c4  pop     rbx
0x1400927c5  retn
```
