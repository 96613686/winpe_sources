# CMetaData::mdReadTableData(DBCOLUMNUPDATEINFO *,ushort *,ushort *)

- ea: `0x18000443c`
- end: `0x180004792`
- name: `?mdReadTableData@CMetaData@@AEAAXPEAUDBCOLUMNUPDATEINFO@@PEAG1@Z`
- size: `854`
- prototype: `void __fastcall(CMetaData *__hidden this, struct DBCOLUMNUPDATEINFO *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180003638`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x180002650`
- `0x1800027c0`
- `0x1800027f0`
- `0x180002864`
- `0x18000443c`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e012`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMetaData::mdReadTableData(
        CMetaData *this,
        unsigned __int16 **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r12
  unsigned __int8 *v7; // r10
  __int64 v8; // rbx
  unsigned __int8 *v9; // rdi
  unsigned __int16 **v10; // r15
  unsigned __int16 **v11; // r14
  int v12; // r11d
  __int16 v13; // bx
  __int64 v14; // rax
  unsigned int v15; // ebx
  unsigned __int128 v16; // rax
  unsigned __int64 v17; // kr00_8
  unsigned __int8 *v18; // r12
  __int64 v19; // rax
  unsigned int v20; // ebx
  unsigned __int128 v21; // rax
  unsigned __int64 v22; // kr10_8
  int v23; // eax
  int v24; // ebx
  unsigned __int8 *v25; // r15
  __int64 v26; // rax
  unsigned int v27; // ebx
  unsigned __int128 v28; // rax
  unsigned __int64 v29; // kr20_8
  int v30; // eax
  int v31; // ebx
  unsigned int v32; // r9d
  unsigned __int128 v33; // rax
  unsigned __int8 *v34; // rbx
  unsigned __int8 *v35; // rcx
  unsigned __int8 *v36; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int8 *v37; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *v38; // [rsp+40h] [rbp-18h]
  unsigned __int8 *v39; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int8 *v40; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 *v41; // [rsp+B0h] [rbp+58h]
  unsigned __int16 *v42; // [rsp+B8h] [rbp+60h]

  v42 = a4;
  v41 = a3;
  v4 = a4;
  v7 = 0;
  if ( a2[11] )
  {
    v8 = *((_QWORD *)this + 6);
    v9 = (unsigned __int8 *)v8;
    v10 = a2 + 12;
    v11 = a2 + 13;
    if ( v8 )
    {
      while ( !(unsigned int)fSameString(*(unsigned __int16 **)v9, a2[11])
           || !(unsigned int)fSameString(*((unsigned __int16 **)v9 + 1), *v10)
           || !(unsigned int)fSameString(*((unsigned __int16 **)v9 + 2), *v11) )
      {
        v9 = (unsigned __int8 *)*((_QWORD *)v9 + 6);
        if ( !v9 )
          goto LABEL_9;
      }
      if ( v9 )
        goto LABEL_36;
LABEL_9:
      v13 = *(_WORD *)(v8 + 40);
    }
    else
    {
      v13 = 0;
    }
    v36 = v7;
    v40 = v7;
    v39 = v7;
    v9 = MMMAlloc(0x38u, (unsigned int)a2);
    v37 = v9;
    OnNullThrowOOM(v9);
    *((_WORD *)v9 + 20) = v13 + 1;
    v14 = -1;
    do
      ++v14;
    while ( a2[11][v14] );
    v15 = v14 + 1;
    v17 = (unsigned int)(v14 + 1);
    v16 = (unsigned int)(v14 + 1) * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v17, 2u) )
      LODWORD(v16) = -1;
    v38 = MMMAlloc(v16, DWORD2(v16));
    v36 = v38;
    OnNullThrowOOM(v38);
    StringCchCopyW((unsigned __int16 *)v38, v15, a2[11]);
    v18 = 0;
    if ( *v10 )
    {
      v19 = -1;
      do
        ++v19;
      while ( (*v10)[v19] );
      v20 = v19 + 1;
      v22 = (unsigned int)(v19 + 1);
      v21 = (unsigned int)(v19 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v22, 2u) )
        LODWORD(v21) = -1;
      v18 = MMMAlloc(v21, DWORD2(v21));
      v40 = v18;
      OnNullThrowOOM(v18);
      v23 = StringCchCopyW((unsigned __int16 *)v18, v20, *v10);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800483F0[0] )
            bidTraceW(off_1800481B8[0], 985088, off_1800483F0[0], (unsigned int)v23, 962);
        }
        ThrowHR(v24);
      }
    }
    v25 = 0;
    if ( *v11 )
    {
      v26 = -1;
      do
        ++v26;
      while ( (*v11)[v26] );
      v27 = v26 + 1;
      v29 = (unsigned int)(v26 + 1);
      v28 = (unsigned int)(v26 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v29, 2u) )
        LODWORD(v28) = -1;
      v25 = MMMAlloc(v28, DWORD2(v28));
      v39 = v25;
      OnNullThrowOOM(v25);
      v30 = StringCchCopyW((unsigned __int16 *)v25, v27, *v11);
      v31 = v30;
      if ( v30 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800483E8[0] )
          bidTraceW(off_1800481B8[0], 992256, off_1800483E8[0], (unsigned int)v30, 969);
        ThrowHR(v31);
      }
    }
    *((_DWORD *)v9 + 6) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 6) = *((_QWORD *)this + 6);
    v36 = 0;
    *(_QWORD *)v9 = v38;
    v40 = 0;
    *((_QWORD *)v9 + 1) = v18;
    v39 = 0;
    *((_QWORD *)v9 + 2) = v25;
    v37 = 0;
    *((_QWORD *)this + 6) = v9;
    CAutoP<_GUID>::~CAutoP<_GUID>(&v39);
    CAutoP<_GUID>::~CAutoP<_GUID>(&v40);
    CAutoP<_GUID>::~CAutoP<_GUID>(&v36);
    CAutoP<_GUID>::~CAutoP<_GUID>(&v37);
    v4 = v42;
    LOWORD(v7) = 0;
    v12 = -1;
LABEL_36:
    if ( *((_WORD *)a2 + 56) != (_WORD)v7 )
    {
      v32 = *((unsigned __int16 *)v9 + 13);
      if ( v32 == 10 * (v32 / 0xA) )
      {
        v33 = (v32 + 10) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v32 + 10, 2u) )
          LODWORD(v33) = v12;
        v34 = MMMAlloc(v33, DWORD2(v33));
        OnNullThrowOOM(v34);
        memcpy_0(v34, *((const void **)v9 + 4), 2LL * *((unsigned __int16 *)v9 + 13));
        v35 = (unsigned __int8 *)*((_QWORD *)v9 + 4);
        if ( v35 )
          MMMFree(v35);
        *((_QWORD *)v9 + 4) = v34;
      }
      *(_WORD *)(*((_QWORD *)v9 + 4) + 2LL * (unsigned __int16)(*((_WORD *)v9 + 13))++) = *((_WORD *)a2 + 8);
    }
    *v41 = *((_WORD *)v9 + 20);
    *v4 = ++*((_WORD *)v9 + 12);
  }
}

```

## disassembly

```asm
0x18000443c  mov     [rsp-40h+arg_18], r9
0x180004441  mov     [rsp-40h+arg_10], r8
0x180004446  push    rbp
0x180004447  push    rbx
0x180004448  push    rsi
0x180004449  push    rdi
0x18000444a  push    r12
0x18000444c  push    r13
0x18000444e  push    r14
0x180004450  push    r15
0x180004452  mov     rbp, rsp
0x180004455  sub     rsp, 58h
0x180004459  mov     r12, r9
0x18000445c  mov     rsi, rdx
0x18000445f  mov     r13, rcx
0x180004462  xor     r10d, r10d
0x180004465  cmp     [rdx+58h], r10
0x180004469  jz      loc_180004781
0x18000446f  mov     rbx, [rcx+30h]
0x180004473  mov     rdi, rbx
0x180004476  lea     r15, [rdx+60h]
0x18000447a  lea     r14, [rdx+68h]
0x18000447e  or      r11, 0FFFFFFFFFFFFFFFFh
0x180004482  test    rbx, rbx
0x180004485  jz      short loc_1800044D1
0x180004487  mov     rdx, [rsi+58h]; unsigned __int16 *
0x18000448b  mov     rcx, [rdi]; unsigned __int16 *
0x18000448e  call    ?fSameString@@YAHPEAG0@Z; fSameString(ushort *,ushort *)
0x180004493  test    eax, eax
0x180004495  jz      short loc_1800044B7
0x180004497  mov     rdx, [r15]; unsigned __int16 *
0x18000449a  mov     rcx, [rdi+8]; unsigned __int16 *
0x18000449e  call    ?fSameString@@YAHPEAG0@Z; fSameString(ushort *,ushort *)
0x1800044a3  test    eax, eax
0x1800044a5  jz      short loc_1800044B7
0x1800044a7  mov     rdx, [r14]; unsigned __int16 *
0x1800044aa  mov     rcx, [rdi+10h]; unsigned __int16 *
0x1800044ae  call    ?fSameString@@YAHPEAG0@Z; fSameString(ushort *,ushort *)
0x1800044b3  test    eax, eax
0x1800044b5  jnz     short loc_1800044C2
0x1800044b7  mov     rdi, [rdi+30h]
0x1800044bb  test    rdi, rdi
0x1800044be  jnz     short loc_180004487
0x1800044c0  jmp     short loc_1800044CB
0x1800044c2  test    rdi, rdi
0x1800044c5  jnz     loc_1800046EA
0x1800044cb  movzx   ebx, word ptr [rbx+28h]
0x1800044cf  jmp     short loc_1800044D4
0x1800044d1  mov     ebx, r10d
0x1800044d4  mov     [rbp+var_28], r10
0x1800044d8  mov     [rbp+arg_8], r10
0x1800044dc  mov     [rbp+arg_0], r10
0x1800044e0  mov     ecx, 38h ; '8'; unsigned int
0x1800044e5  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800044ea  mov     rdi, rax
0x1800044ed  mov     [rbp+var_20], rax
0x1800044f1  mov     rcx, rax; void *
0x1800044f4  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800044f9  inc     bx
0x1800044fc  mov     [rdi+28h], bx
0x180004500  mov     rcx, [rsi+58h]
0x180004504  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004508  mov     rax, r8
0x18000450b  xor     edx, edx; unsigned int
0x18000450d  inc     rax
0x180004510  cmp     [rcx+rax*2], dx
0x180004514  jnz     short loc_18000450D
0x180004516  lea     ebx, [rax+1]
0x180004519  mov     eax, 2
0x18000451e  mul     rbx
0x180004521  cmovb   rax, r8
0x180004525  mov     ecx, eax; unsigned int
0x180004527  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000452c  mov     r12, rax
0x18000452f  mov     [rbp+var_18], rax
0x180004533  mov     [rbp+var_28], rax
0x180004537  mov     rcx, rax; void *
0x18000453a  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000453f  mov     r8, [rsi+58h]; unsigned __int16 *
0x180004543  mov     edx, ebx; unsigned __int64
0x180004545  mov     rcx, r12; unsigned __int16 *
0x180004548  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000454d  mov     r11, [r15]
0x180004550  xor     edx, edx; unsigned int
0x180004552  mov     r12d, edx
0x180004555  test    r11, r11
0x180004558  jz      loc_1800045E9
0x18000455e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004562  mov     rax, rcx
0x180004565  inc     rax
0x180004568  cmp     [r11+rax*2], dx
0x18000456d  jnz     short loc_180004565
0x18000456f  lea     ebx, [rax+1]
0x180004572  mov     eax, 2
0x180004577  mul     rbx
0x18000457a  cmovb   rax, rcx
0x18000457e  mov     ecx, eax; unsigned int
0x180004580  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004585  mov     r12, rax
0x180004588  mov     [rbp+arg_8], rax
0x18000458c  mov     rcx, rax; void *
0x18000458f  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004594  mov     r8, [r15]; unsigned __int16 *
0x180004597  mov     edx, ebx; unsigned __int64
0x180004599  mov     rcx, r12; unsigned __int16 *
0x18000459c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800045a1  mov     ebx, eax
0x1800045a3  xor     edx, edx
0x1800045a5  test    eax, eax
0x1800045a7  jns     short loc_1800045E9
0x1800045a9  test    byte ptr cs:_bidGblFlags, 2
0x1800045b0  jz      short loc_1800045E1
0x1800045b2  mov     rcx, cs:off_1800483F0; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x1800045b9  test    rcx, rcx
0x1800045bc  jz      short loc_1800045E1
0x1800045be  mov     [rsp+58h+var_38], 3C2h
0x1800045c6  mov     r9d, eax
0x1800045c9  mov     r8, cs:off_1800483F0; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x1800045d0  mov     edx, 0F0800h
0x1800045d5  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800045dc  call    _bidTraceW
0x1800045e1  mov     ecx, ebx; int
0x1800045e3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800045e9  mov     rcx, [r14]
0x1800045ec  mov     r15, rdx
0x1800045ef  test    rcx, rcx
0x1800045f2  jz      loc_180004682
0x1800045f8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800045fc  mov     rax, r8
0x1800045ff  inc     rax
0x180004602  cmp     [rcx+rax*2], dx
0x180004606  jnz     short loc_1800045FF
0x180004608  lea     ebx, [rax+1]
0x18000460b  mov     eax, 2
0x180004610  mul     rbx
0x180004613  cmovb   rax, r8
0x180004617  mov     ecx, eax; unsigned int
0x180004619  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000461e  mov     r15, rax
0x180004621  mov     [rbp+arg_0], rax
0x180004625  mov     rcx, rax; void *
0x180004628  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000462d  mov     r8, [r14]; unsigned __int16 *
0x180004630  mov     edx, ebx; unsigned __int64
0x180004632  mov     rcx, r15; unsigned __int16 *
0x180004635  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000463a  mov     ebx, eax
0x18000463c  xor     edx, edx
0x18000463e  test    eax, eax
0x180004640  jns     short loc_180004682
0x180004642  test    byte ptr cs:_bidGblFlags, 2
0x180004649  jz      short loc_18000467A
0x18000464b  mov     rcx, cs:off_1800483E8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004652  test    rcx, rcx
0x180004655  jz      short loc_18000467A
0x180004657  mov     [rsp+58h+var_38], 3C9h
0x18000465f  mov     r9d, eax
0x180004662  mov     r8, cs:off_1800483E8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004669  mov     edx, 0F2400h
0x18000466e  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180004675  call    _bidTraceW
0x18000467a  mov     ecx, ebx; int
0x18000467c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004682  mov     dword ptr [rdi+18h], 0
0x180004689  mov     [rdi+20h], rdx
0x18000468d  mov     rax, [r13+30h]
0x180004691  mov     [rdi+30h], rax
0x180004695  mov     [rbp+var_28], rdx
0x180004699  mov     rax, [rbp+var_18]
0x18000469d  mov     [rdi], rax
0x1800046a0  mov     [rbp+arg_8], rdx
0x1800046a4  mov     [rdi+8], r12
0x1800046a8  mov     [rbp+arg_0], rdx
0x1800046ac  mov     [rdi+10h], r15
0x1800046b0  mov     [rbp+var_20], rdx
0x1800046b4  mov     [r13+30h], rdi
0x1800046b8  lea     rcx, [rbp+arg_0]
0x1800046bc  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800046c1  nop
0x1800046c2  lea     rcx, [rbp+arg_8]
0x1800046c6  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800046cb  nop
0x1800046cc  lea     rcx, [rbp+var_28]
0x1800046d0  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800046d5  nop
0x1800046d6  lea     rcx, [rbp+var_20]
0x1800046da  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x1800046df  mov     r12, [rbp+arg_18]
0x1800046e3  xor     r10d, r10d
0x1800046e6  or      r11, 0FFFFFFFFFFFFFFFFh
0x1800046ea  cmp     [rsi+70h], r10w
0x1800046ef  jz      short loc_180004769
0x1800046f1  movzx   r9d, word ptr [rdi+1Ah]
0x1800046f6  mov     eax, 0CCCCCCCDh
0x1800046fb  mul     r9d
0x1800046fe  shr     edx, 3
0x180004701  lea     r8d, [rdx+rdx*4]
0x180004705  add     r8d, r8d
0x180004708  cmp     r9d, r8d
0x18000470b  jnz     short loc_180004755
0x18000470d  lea     edx, [r9+0Ah]; unsigned int
0x180004711  mov     eax, 2
0x180004716  mul     rdx
0x180004719  cmovb   rax, r11
0x18000471d  mov     ecx, eax; unsigned int
0x18000471f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004724  mov     rbx, rax
0x180004727  mov     rcx, rax; void *
0x18000472a  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000472f  movzx   r8d, word ptr [rdi+1Ah]
0x180004734  add     r8, r8; Size
0x180004737  mov     rdx, [rdi+20h]; Src
0x18000473b  mov     rcx, rbx; void *
0x18000473e  call    memcpy_0
0x180004743  mov     rcx, [rdi+20h]; unsigned __int8 *
0x180004747  test    rcx, rcx
0x18000474a  jz      short loc_180004751
0x18000474c  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180004751  mov     [rdi+20h], rbx
0x180004755  movzx   edx, word ptr [rdi+1Ah]
0x180004759  mov     rcx, [rdi+20h]
0x18000475d  movzx   eax, word ptr [rsi+10h]
0x180004761  mov     [rcx+rdx*2], ax
0x180004765  inc     word ptr [rdi+1Ah]
0x180004769  movzx   eax, word ptr [rdi+28h]
0x18000476d  mov     rcx, [rbp+arg_10]
0x180004771  mov     [rcx], ax
0x180004774  inc     word ptr [rdi+18h]
0x180004778  movzx   eax, word ptr [rdi+18h]
0x18000477c  mov     [r12], ax
0x180004781  add     rsp, 58h
0x180004785  pop     r15
0x180004787  pop     r14
0x180004789  pop     r13
0x18000478b  pop     r12
0x18000478d  pop     rdi
0x18000478e  pop     rsi
0x18000478f  pop     rbx
0x180004790  pop     rbp
0x180004791  retn
```
