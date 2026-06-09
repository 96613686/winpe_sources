# TieringMovementSession::GetCurrentMovementRecord(unsigned __int64,ulong *,TE_FILE_ID_128 *,__int64 *)

- ea: `0x14001d960`
- end: `0x14001da75`
- name: `?GetCurrentMovementRecord@TieringMovementSession@@QEAAJ_KPEAKPEAUTE_FILE_ID_128@@PEA_J@Z`
- size: `277`
- prototype: `JET_ERR __fastcall(TieringMovementSession *this, JET_TABLEID, unsigned int *, struct TE_FILE_ID_128 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140021a28`

## callees

- `0x140002323`
- `0x14001d960`
- `0x14003fbb0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x14001da47`
- `ESENT!JetRetrieveColumns` at `0x14001da47`

## pseudocode

```c
JET_ERR __fastcall TieringMovementSession::GetCurrentMovementRecord(
        TieringMovementSession *this,
        JET_TABLEID a2,
        unsigned int *a3,
        struct TE_FILE_ID_128 *a4,
        __int64 *a5)
{
  unsigned int v6; // ebx
  __int64 v10; // rdi
  JET_COLUMNID *v11; // rdi
  JET_COLUMNID v12; // eax
  __int64 v13; // rcx
  JET_COLUMNID v14; // eax
  __int64 v15; // r8
  JET_RETRIEVECOLUMN pretrievecolumn[3]; // [rsp+20h] [rbp-71h] BYREF

  v6 = 0;
  v10 = 32;
  if ( a2 != *((_QWORD *)this + 2) )
    v10 = 44;
  v11 = (JET_COLUMNID *)((char *)this + v10);
  memset_0(pretrievecolumn, 0, sizeof(pretrievecolumn));
  if ( a3 )
  {
    v6 = 1;
    pretrievecolumn[0].columnid = *v11;
    pretrievecolumn[0].pvData = a3;
    pretrievecolumn[0].itagSequence = 1;
    pretrievecolumn[0].grbit = 1;
    pretrievecolumn[0].cbData = 4;
  }
  if ( a4 )
  {
    v12 = v11[v6];
    v13 = v6++;
    pretrievecolumn[v13].columnid = v12;
    pretrievecolumn[v13].pvData = a4;
    pretrievecolumn[v13].itagSequence = 1;
    pretrievecolumn[v13].grbit = 1;
    pretrievecolumn[v13].cbData = 16;
  }
  if ( a5 )
  {
    v14 = v11[v6];
    v15 = v6++;
    pretrievecolumn[v15].columnid = v14;
    pretrievecolumn[v15].pvData = a5;
    pretrievecolumn[v15].itagSequence = 1;
    pretrievecolumn[v15].grbit = 1;
    pretrievecolumn[v15].cbData = 8;
  }
  return JetRetrieveColumns(*((_QWORD *)this + 1), a2, pretrievecolumn, v6);
}

```

## disassembly

```asm
0x14001d960  mov     [rsp-8+arg_10], rbx
0x14001d965  mov     [rsp-8+arg_18], rsi
0x14001d96a  push    rbp
0x14001d96b  push    rdi
0x14001d96c  push    r12
0x14001d96e  push    r14
0x14001d970  push    r15
0x14001d972  lea     rbp, [rsp-2Fh]
0x14001d977  sub     rsp, 0C0h
0x14001d97e  mov     rax, cs:__security_cookie
0x14001d985  xor     rax, rsp
0x14001d988  mov     [rbp+4Fh+var_30], rax
0x14001d98c  mov     r15, rcx
0x14001d98f  xor     ebx, ebx
0x14001d991  mov     r14, r8
0x14001d994  mov     r12, rdx
0x14001d997  mov     rsi, r9
0x14001d99a  cmp     rdx, [r15+10h]
0x14001d99e  lea     ecx, [rbx+2Ch]
0x14001d9a1  lea     r8d, [rcx+64h]; Size
0x14001d9a5  lea     edi, [rbx+20h]
0x14001d9a8  cmovnz  edi, ecx
0x14001d9ab  xor     edx, edx; Val
0x14001d9ad  lea     rcx, [rbp+4Fh+pretrievecolumn]; void *
0x14001d9b1  add     rdi, r15
0x14001d9b4  call    memset_0
0x14001d9b9  lea     edx, [rbx+1]
0x14001d9bc  test    r14, r14
0x14001d9bf  jz      short loc_14001D9D9
0x14001d9c1  mov     eax, [rdi]
0x14001d9c3  mov     ebx, edx
0x14001d9c5  mov     [rbp+4Fh+pretrievecolumn.columnid], eax
0x14001d9c8  mov     [rbp+4Fh+pretrievecolumn.pvData], r14
0x14001d9cc  mov     [rbp+4Fh+pretrievecolumn.itagSequence], edx
0x14001d9cf  mov     [rbp+4Fh+pretrievecolumn.grbit], edx
0x14001d9d2  mov     [rbp+4Fh+pretrievecolumn.cbData], 4
0x14001d9d9  test    rsi, rsi
0x14001d9dc  jz      short loc_14001DA05
0x14001d9de  mov     eax, ebx
0x14001d9e0  lea     rcx, [rax+rax*2]
0x14001d9e4  mov     eax, [rdi+rax*4]
0x14001d9e7  add     rcx, rcx
0x14001d9ea  add     ebx, edx
0x14001d9ec  mov     [rbp+rcx*8+4Fh+pretrievecolumn.columnid], eax
0x14001d9f0  mov     [rbp+rcx*8+4Fh+pretrievecolumn.pvData], rsi
0x14001d9f5  mov     [rbp+rcx*8+4Fh+pretrievecolumn.itagSequence], edx
0x14001d9f9  mov     [rbp+rcx*8+4Fh+pretrievecolumn.grbit], edx
0x14001d9fd  mov     [rbp+rcx*8+4Fh+pretrievecolumn.cbData], 10h
0x14001da05  mov     r9, [rbp+4Fh+arg_20]
0x14001da09  test    r9, r9
0x14001da0c  jz      short loc_14001DA39
0x14001da0e  mov     eax, ebx
0x14001da10  lea     r8, [rax+rax*2]
0x14001da14  mov     eax, [rdi+rax*4]
0x14001da17  add     r8, r8
0x14001da1a  add     ebx, edx
0x14001da1c  mov     [rbp+r8*8+4Fh+pretrievecolumn.columnid], eax
0x14001da21  mov     [rbp+r8*8+4Fh+pretrievecolumn.pvData], r9
0x14001da26  mov     [rbp+r8*8+4Fh+pretrievecolumn.itagSequence], edx
0x14001da2b  mov     [rbp+r8*8+4Fh+pretrievecolumn.grbit], edx
0x14001da30  mov     [rbp+r8*8+4Fh+pretrievecolumn.cbData], 8
0x14001da39  mov     rcx, [r15+8]; sesid
0x14001da3d  lea     r8, [rbp+4Fh+pretrievecolumn]; pretrievecolumn
0x14001da41  mov     r9d, ebx; cretrievecolumn
0x14001da44  mov     rdx, r12; tableid
0x14001da47  call    cs:__imp_JetRetrieveColumns
0x14001da4d  mov     rcx, [rbp+4Fh+var_30]
0x14001da51  xor     rcx, rsp; StackCookie
0x14001da54  call    __security_check_cookie
0x14001da59  lea     r11, [rsp+0E0h+var_20]
0x14001da61  mov     rbx, [r11+40h]
0x14001da65  mov     rsi, [r11+48h]
0x14001da69  mov     rsp, r11
0x14001da6c  pop     r15
0x14001da6e  pop     r14
0x14001da70  pop     r12
0x14001da72  pop     rdi
0x14001da73  pop     rbp
0x14001da74  retn
```
