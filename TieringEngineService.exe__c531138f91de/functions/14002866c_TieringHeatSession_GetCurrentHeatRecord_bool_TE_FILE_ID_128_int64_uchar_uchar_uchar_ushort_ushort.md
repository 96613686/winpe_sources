# TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)

- ea: `0x14002866c`
- end: `0x140028840`
- name: `?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z`
- size: `468`
- prototype: `JET_ERR __fastcall(TieringHeatSession *this, unsigned __int8, struct TE_FILE_ID_128 *, __int64 *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `15`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400211a4`
- `0x140024b60`
- `0x140026e90`
- `0x140027908`
- `0x140028848`
- `0x140028e7c`
- `0x140029268`
- `0x140029840`
- `0x140029f6c`
- `0x14002ac14`
- `0x14002b15c`
- `0x14002beec`
- `0x14002c60c`
- `0x140030e10`
- `0x140031e04`

## callees

- `0x140002323`
- `0x14002866c`
- `0x14002a86c`
- `0x14003fbb0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x14002881e`
- `ESENT!JetRetrieveColumns` at `0x14002881e`

## pseudocode

```c
JET_ERR __fastcall TieringHeatSession::GetCurrentHeatRecord(
        TieringHeatSession *this,
        unsigned __int8 a2,
        struct TE_FILE_ID_128 *a3,
        __int64 *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned __int8 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9)
{
  JET_GRBIT v10; // esi
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  JET_RETRIEVECOLUMN pretrievecolumn[7]; // [rsp+20h] [rbp-E0h] BYREF

  v10 = a2;
  v13 = 0;
  TieringHeatSession::SetupColumnIds(this);
  memset_0(pretrievecolumn, 0, sizeof(pretrievecolumn));
  if ( a3 )
  {
    v13 = 1;
    pretrievecolumn[0].columnid = *((_DWORD *)this + 13);
    pretrievecolumn[0].pvData = a3;
    pretrievecolumn[0].itagSequence = 1;
    pretrievecolumn[0].grbit = v10;
    pretrievecolumn[0].cbData = 16;
  }
  if ( a4 )
  {
    v14 = v13++;
    pretrievecolumn[v14].columnid = *((_DWORD *)this + 14);
    pretrievecolumn[v14].pvData = a4;
    pretrievecolumn[v14].itagSequence = 1;
    pretrievecolumn[v14].grbit = v10;
    pretrievecolumn[v14].cbData = 8;
  }
  if ( a5 )
  {
    v15 = v13++;
    pretrievecolumn[v15].columnid = *((_DWORD *)this + 15);
    pretrievecolumn[v15].pvData = a5;
    pretrievecolumn[v15].itagSequence = 1;
    pretrievecolumn[v15].grbit = v10;
    pretrievecolumn[v15].cbData = 1;
  }
  if ( a6 )
  {
    v16 = v13++;
    pretrievecolumn[v16].columnid = *((_DWORD *)this + 16);
    pretrievecolumn[v16].pvData = a6;
    pretrievecolumn[v16].itagSequence = 1;
    pretrievecolumn[v16].grbit = v10;
    pretrievecolumn[v16].cbData = 1;
  }
  if ( a7 )
  {
    v17 = v13++;
    pretrievecolumn[v17].columnid = *((_DWORD *)this + 17);
    pretrievecolumn[v17].pvData = a7;
    pretrievecolumn[v17].itagSequence = 1;
    pretrievecolumn[v17].grbit = v10;
    pretrievecolumn[v17].cbData = 1;
  }
  if ( a8 )
  {
    v18 = v13++;
    pretrievecolumn[v18].columnid = *((_DWORD *)this + 20);
    pretrievecolumn[v18].pvData = a8;
    pretrievecolumn[v18].itagSequence = 1;
    pretrievecolumn[v18].grbit = v10;
    pretrievecolumn[v18].cbData = 2;
  }
  if ( a9 )
  {
    v19 = v13++;
    pretrievecolumn[v19].columnid = *((_DWORD *)this + 21);
    pretrievecolumn[v19].pvData = a9;
    pretrievecolumn[v19].itagSequence = 1;
    pretrievecolumn[v19].grbit = v10;
    pretrievecolumn[v19].cbData = 14;
  }
  return JetRetrieveColumns(*((_QWORD *)this + 1), *((_QWORD *)this + 3), pretrievecolumn, v13);
}

```

## disassembly

```asm
0x14002866c  push    rbp
0x14002866e  push    rbx
0x14002866f  push    rsi
0x140028670  push    rdi
0x140028671  push    r14
0x140028673  push    r15
0x140028675  lea     rbp, [rsp-88h]
0x14002867d  sub     rsp, 188h
0x140028684  mov     rax, cs:__security_cookie
0x14002868b  xor     rax, rsp
0x14002868e  mov     [rbp+0B0h+var_40], rax
0x140028692  mov     r14, r9
0x140028695  movzx   esi, dl
0x140028698  mov     r15, r8
0x14002869b  mov     rdi, rcx
0x14002869e  xor     ebx, ebx
0x1400286a0  call    ?SetupColumnIds@TieringHeatSession@@QEAAXXZ; TieringHeatSession::SetupColumnIds(void)
0x1400286a5  xor     edx, edx; Val
0x1400286a7  lea     rcx, [rsp+1B0h+pretrievecolumn]; void *
0x1400286ac  mov     r8d, 150h; Size
0x1400286b2  call    memset_0
0x1400286b7  lea     r8d, [rbx+1]
0x1400286bb  test    r15, r15
0x1400286be  jz      short loc_1400286E0
0x1400286c0  mov     eax, [rdi+34h]
0x1400286c3  mov     ebx, r8d
0x1400286c6  mov     [rsp+1B0h+pretrievecolumn.columnid], eax
0x1400286ca  mov     [rsp+1B0h+pretrievecolumn.pvData], r15
0x1400286cf  mov     [rsp+1B0h+pretrievecolumn.itagSequence], r8d
0x1400286d4  mov     [rsp+1B0h+pretrievecolumn.grbit], esi
0x1400286d8  mov     [rsp+1B0h+pretrievecolumn.cbData], 10h
0x1400286e0  test    r14, r14
0x1400286e3  jz      short loc_14002870E
0x1400286e5  mov     eax, ebx
0x1400286e7  lea     rcx, [rax+rax*2]
0x1400286eb  mov     eax, [rdi+38h]
0x1400286ee  add     rcx, rcx
0x1400286f1  add     ebx, r8d
0x1400286f4  mov     [rsp+rcx*8+1B0h+pretrievecolumn.columnid], eax
0x1400286f8  mov     [rsp+rcx*8+1B0h+pretrievecolumn.pvData], r14
0x1400286fd  mov     [rsp+rcx*8+1B0h+pretrievecolumn.itagSequence], r8d
0x140028702  mov     [rsp+rcx*8+1B0h+pretrievecolumn.grbit], esi
0x140028706  mov     [rsp+rcx*8+1B0h+pretrievecolumn.cbData], 8
0x14002870e  mov     rdx, [rbp+0B0h+arg_20]
0x140028715  test    rdx, rdx
0x140028718  jz      short loc_140028740
0x14002871a  mov     eax, ebx
0x14002871c  lea     rcx, [rax+rax*2]
0x140028720  mov     eax, [rdi+3Ch]
0x140028723  add     rcx, rcx
0x140028726  add     ebx, r8d
0x140028729  mov     [rsp+rcx*8+1B0h+pretrievecolumn.columnid], eax
0x14002872d  mov     [rsp+rcx*8+1B0h+pretrievecolumn.pvData], rdx
0x140028732  mov     [rsp+rcx*8+1B0h+pretrievecolumn.itagSequence], r8d
0x140028737  mov     [rsp+rcx*8+1B0h+pretrievecolumn.grbit], esi
0x14002873b  mov     [rsp+rcx*8+1B0h+pretrievecolumn.cbData], r8d
0x140028740  mov     rdx, [rbp+0B0h+arg_28]
0x140028747  test    rdx, rdx
0x14002874a  jz      short loc_140028772
0x14002874c  mov     eax, ebx
0x14002874e  lea     rcx, [rax+rax*2]
0x140028752  mov     eax, [rdi+40h]
0x140028755  add     rcx, rcx
0x140028758  add     ebx, r8d
0x14002875b  mov     [rsp+rcx*8+1B0h+pretrievecolumn.columnid], eax
0x14002875f  mov     [rsp+rcx*8+1B0h+pretrievecolumn.pvData], rdx
0x140028764  mov     [rsp+rcx*8+1B0h+pretrievecolumn.itagSequence], r8d
0x140028769  mov     [rsp+rcx*8+1B0h+pretrievecolumn.grbit], esi
0x14002876d  mov     [rsp+rcx*8+1B0h+pretrievecolumn.cbData], r8d
0x140028772  mov     rdx, [rbp+0B0h+arg_30]
0x140028779  test    rdx, rdx
0x14002877c  jz      short loc_1400287A4
0x14002877e  mov     eax, ebx
0x140028780  lea     rcx, [rax+rax*2]
0x140028784  mov     eax, [rdi+44h]
0x140028787  add     rcx, rcx
0x14002878a  add     ebx, r8d
0x14002878d  mov     [rsp+rcx*8+1B0h+pretrievecolumn.columnid], eax
0x140028791  mov     [rsp+rcx*8+1B0h+pretrievecolumn.pvData], rdx
0x140028796  mov     [rsp+rcx*8+1B0h+pretrievecolumn.itagSequence], r8d
0x14002879b  mov     [rsp+rcx*8+1B0h+pretrievecolumn.grbit], esi
0x14002879f  mov     [rsp+rcx*8+1B0h+pretrievecolumn.cbData], r8d
0x1400287a4  mov     rdx, [rbp+0B0h+arg_38]
0x1400287ab  test    rdx, rdx
0x1400287ae  jz      short loc_1400287D9
0x1400287b0  mov     eax, ebx
0x1400287b2  lea     rcx, [rax+rax*2]
0x1400287b6  mov     eax, [rdi+50h]
0x1400287b9  add     rcx, rcx
0x1400287bc  add     ebx, r8d
0x1400287bf  mov     [rsp+rcx*8+1B0h+pretrievecolumn.columnid], eax
0x1400287c3  mov     [rsp+rcx*8+1B0h+pretrievecolumn.pvData], rdx
0x1400287c8  mov     [rsp+rcx*8+1B0h+pretrievecolumn.itagSequence], r8d
0x1400287cd  mov     [rsp+rcx*8+1B0h+pretrievecolumn.grbit], esi
0x1400287d1  mov     [rsp+rcx*8+1B0h+pretrievecolumn.cbData], 2
0x1400287d9  mov     rcx, [rbp+0B0h+arg_40]
0x1400287e0  test    rcx, rcx
0x1400287e3  jz      short loc_14002880E
0x1400287e5  mov     eax, ebx
0x1400287e7  lea     rdx, [rax+rax*2]
0x1400287eb  mov     eax, [rdi+54h]
0x1400287ee  add     rdx, rdx
0x1400287f1  add     ebx, r8d
0x1400287f4  mov     [rsp+rdx*8+1B0h+pretrievecolumn.columnid], eax
0x1400287f8  mov     [rsp+rdx*8+1B0h+pretrievecolumn.pvData], rcx
0x1400287fd  mov     [rsp+rdx*8+1B0h+pretrievecolumn.itagSequence], r8d
0x140028802  mov     [rsp+rdx*8+1B0h+pretrievecolumn.grbit], esi
0x140028806  mov     [rsp+rdx*8+1B0h+pretrievecolumn.cbData], 0Eh
0x14002880e  mov     rdx, [rdi+18h]; tableid
0x140028812  lea     r8, [rsp+1B0h+pretrievecolumn]; pretrievecolumn
0x140028817  mov     rcx, [rdi+8]; sesid
0x14002881b  mov     r9d, ebx; cretrievecolumn
0x14002881e  call    cs:__imp_JetRetrieveColumns
0x140028824  mov     rcx, [rbp+0B0h+var_40]
0x140028828  xor     rcx, rsp; StackCookie
0x14002882b  call    __security_check_cookie
0x140028830  add     rsp, 188h
0x140028837  pop     r15
0x140028839  pop     r14
0x14002883b  pop     rdi
0x14002883c  pop     rsi
0x14002883d  pop     rbx
0x14002883e  pop     rbp
0x14002883f  retn
```
