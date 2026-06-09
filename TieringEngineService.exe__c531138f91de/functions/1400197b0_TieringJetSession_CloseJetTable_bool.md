# TieringJetSession::CloseJetTable(bool)

- ea: `0x1400197b0`
- end: `0x1400198fe`
- name: `?CloseJetTable@TieringJetSession@@QEAAJ_N@Z`
- size: `334`
- prototype: `__int64 __fastcall(TieringJetSession *this, char)`
- caller_count: `20`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c444`
- `0x14000c648`
- `0x14000d5f0`
- `0x14000ef74`
- `0x14000f108`
- `0x1400108e0`
- `0x140010d1c`
- `0x1400122fc`
- `0x140017120`
- `0x1400188b8`
- `0x1400211a4`
- `0x14002eef0`
- `0x140036390`
- `0x14003cfb4`
- `0x14003d800`
- `0x14003db78`
- `0x14003ddd4`
- `0x14003e49c`
- `0x14003eba8`
- `0x14003f4d8`

## callees

- `0x140009a04`
- `0x1400197b0`
- `0x140019904`
- `0x140019a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019825`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019825`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400197ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400197ed`

## pseudocode

```c
__int64 __fastcall TieringJetSession::CloseJetTable(TieringJetSession *this, char a2)
{
  TieringJetDatabase **v3; // rdi
  RTL_SRWLOCK *v4; // rsi
  TieringJetDatabase *v5; // rcx
  TieringJetDatabase *v6; // rax

  if ( *(_BYTE *)this )
  {
    v3 = (TieringJetDatabase **)((char *)this + 40);
    if ( a2 || *((_BYTE *)*v3 + 77) )
    {
      TieringJetDatabase::CloseJetTableObjects(
        *v3,
        (unsigned __int64 *)this + 1,
        (unsigned int *)this + 4,
        (unsigned __int64 *)this + 3);
LABEL_19:
      *(_BYTE *)this = 0;
      goto LABEL_20;
    }
    v4 = (RTL_SRWLOCK *)(*(_QWORD *)*v3 + 24LL);
    AcquireSRWLockExclusive(v4);
    v5 = *v3;
    if ( *((_BYTE *)*v3 + 77) )
      goto LABEL_7;
    if ( *((_BYTE *)this + 33) )
    {
      if ( *((_BYTE *)v5 + 40) )
      {
LABEL_7:
        TieringJetDatabase::CloseJetTableObjects(
          v5,
          (unsigned __int64 *)this + 1,
          (unsigned int *)this + 4,
          (unsigned __int64 *)this + 3);
LABEL_8:
        if ( v4 )
          ReleaseSRWLockExclusive(v4);
        goto LABEL_19;
      }
    }
    else if ( *((_BYTE *)v5 + 8) )
    {
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        &WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids,
        *((_QWORD *)v5 + 14));
    }
    v6 = *v3;
    if ( *((_BYTE *)this + 33) )
    {
      *((_BYTE *)v6 + 40) = 1;
      *((_QWORD *)*v3 + 6) = *((_QWORD *)this + 1);
      *((_DWORD *)*v3 + 14) = *((_DWORD *)this + 4);
      *((_QWORD *)*v3 + 8) = *((_QWORD *)this + 3);
    }
    else
    {
      *((_BYTE *)v6 + 8) = 1;
      *((_QWORD *)*v3 + 2) = *((_QWORD *)this + 1);
      *((_DWORD *)*v3 + 6) = *((_DWORD *)this + 4);
      *((_QWORD *)*v3 + 4) = *((_QWORD *)this + 3);
    }
    goto LABEL_8;
  }
LABEL_20:
  if ( *((_BYTE *)this + 34) )
    TieringJetSession::DecrementSessionCount(this);
  return 0;
}

```

## disassembly

```asm
0x1400197b0  mov     [rsp+arg_0], rbx
0x1400197b5  mov     [rsp+arg_8], rsi
0x1400197ba  push    rdi
0x1400197bb  sub     rsp, 20h
0x1400197bf  cmp     byte ptr [rcx], 0
0x1400197c2  mov     rbx, rcx
0x1400197c5  jz      loc_1400198DE
0x1400197cb  lea     rdi, [rcx+28h]
0x1400197cf  test    dl, dl
0x1400197d1  jnz     loc_1400198C7
0x1400197d7  mov     rax, [rdi]
0x1400197da  cmp     [rax+4Dh], dl
0x1400197dd  jnz     loc_1400198C7
0x1400197e3  mov     rsi, [rax]
0x1400197e6  add     rsi, 18h
0x1400197ea  mov     rcx, rsi; SRWLock
0x1400197ed  call    cs:__imp_AcquireSRWLockExclusive
0x1400197f3  mov     rcx, [rdi]; this
0x1400197f6  cmp     byte ptr [rcx+4Dh], 0
0x1400197fa  jnz     short loc_140019808
0x1400197fc  cmp     byte ptr [rbx+21h], 0
0x140019800  jz      short loc_140019830
0x140019802  cmp     byte ptr [rcx+28h], 0
0x140019806  jz      short loc_140019836
0x140019808  lea     r9, [rbx+18h]; unsigned __int64 *
0x14001980c  lea     r8, [rbx+10h]; unsigned int *
0x140019810  lea     rdx, [rbx+8]; unsigned __int64 *
0x140019814  call    ?CloseJetTableObjects@TieringJetDatabase@@QEAAJPEA_KPEAK0@Z; TieringJetDatabase::CloseJetTableObjects(unsigned __int64 *,ulong *,unsigned __int64 *)
0x140019819  test    rsi, rsi
0x14001981c  jz      loc_1400198DB
0x140019822  mov     rcx, rsi; SRWLock
0x140019825  call    cs:__imp_ReleaseSRWLockExclusive
0x14001982b  jmp     loc_1400198DB
0x140019830  cmp     byte ptr [rcx+8], 0
0x140019834  jnz     short loc_140019808
0x140019836  mov     rax, cs:WPP_GLOBAL_Control
0x14001983d  lea     rdx, WPP_GLOBAL_Control
0x140019844  cmp     rax, rdx
0x140019847  jz      short loc_14001986E
0x140019849  test    byte ptr [rax+1Ch], 1
0x14001984d  jz      short loc_14001986E
0x14001984f  cmp     byte ptr [rax+19h], 4
0x140019853  jb      short loc_14001986E
0x140019855  mov     r9, [rcx+70h]
0x140019859  lea     r8, WPP_3466781eb6a73755fef64d54a5e95e41_Traceguids
0x140019860  mov     rcx, [rax+10h]
0x140019864  mov     edx, 76h ; 'v'
0x140019869  call    WPP_SF_S
0x14001986e  cmp     byte ptr [rbx+21h], 0
0x140019872  mov     rax, [rdi]
0x140019875  jz      short loc_14001989F
0x140019877  mov     byte ptr [rax+28h], 1
0x14001987b  mov     rax, [rbx+8]
0x14001987f  mov     rcx, [rdi]
0x140019882  mov     [rcx+30h], rax
0x140019886  mov     rcx, [rdi]
0x140019889  mov     eax, [rbx+10h]
0x14001988c  mov     [rcx+38h], eax
0x14001988f  mov     rcx, [rdi]
0x140019892  mov     rax, [rbx+18h]
0x140019896  mov     [rcx+40h], rax
0x14001989a  jmp     loc_140019819
0x14001989f  mov     byte ptr [rax+8], 1
0x1400198a3  mov     rax, [rbx+8]
0x1400198a7  mov     rcx, [rdi]
0x1400198aa  mov     [rcx+10h], rax
0x1400198ae  mov     rcx, [rdi]
0x1400198b1  mov     eax, [rbx+10h]
0x1400198b4  mov     [rcx+18h], eax
0x1400198b7  mov     rcx, [rdi]
0x1400198ba  mov     rax, [rbx+18h]
0x1400198be  mov     [rcx+20h], rax
0x1400198c2  jmp     loc_140019819
0x1400198c7  lea     r9, [rcx+18h]; unsigned __int64 *
0x1400198cb  lea     r8, [rcx+10h]; unsigned int *
0x1400198cf  lea     rdx, [rcx+8]; unsigned __int64 *
0x1400198d3  mov     rcx, [rdi]; this
0x1400198d6  call    ?CloseJetTableObjects@TieringJetDatabase@@QEAAJPEA_KPEAK0@Z; TieringJetDatabase::CloseJetTableObjects(unsigned __int64 *,ulong *,unsigned __int64 *)
0x1400198db  mov     byte ptr [rbx], 0
0x1400198de  cmp     byte ptr [rbx+22h], 0
0x1400198e2  jz      short loc_1400198EC
0x1400198e4  mov     rcx, rbx; this
0x1400198e7  call    ?DecrementSessionCount@TieringJetSession@@AEAAXXZ; TieringJetSession::DecrementSessionCount(void)
0x1400198ec  mov     rbx, [rsp+28h+arg_0]
0x1400198f1  xor     eax, eax
0x1400198f3  mov     rsi, [rsp+28h+arg_8]
0x1400198f8  add     rsp, 20h
0x1400198fc  pop     rdi
0x1400198fd  retn
```
