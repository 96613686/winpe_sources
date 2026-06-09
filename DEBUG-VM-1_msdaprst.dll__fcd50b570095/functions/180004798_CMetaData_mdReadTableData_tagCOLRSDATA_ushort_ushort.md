# CMetaData::mdReadTableData(tagCOLRSDATA *,ushort *,ushort *)

- ea: `0x180004798`
- end: `0x180004b27`
- name: `?mdReadTableData@CMetaData@@AEAAXPEAUtagCOLRSDATA@@PEAG1@Z`
- size: `911`
- prototype: `void(CMetaData *__hidden this, struct tagCOLRSDATA *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004238`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x180002650`
- `0x1800027c0`
- `0x1800027f0`
- `0x1800028b0`
- `0x180004798`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e012`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMetaData::mdReadTableData(
        CMetaData *this,
        struct tagCOLRSDATA *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // r12
  __int16 v8; // bx
  __int64 v9; // r14
  unsigned __int8 *v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned __int128 v13; // rax
  unsigned __int64 v14; // kr00_8
  int v15; // eax
  int v16; // ebx
  unsigned __int8 *v17; // r15
  __int64 v18; // rax
  unsigned int v19; // ebx
  unsigned __int128 v20; // rax
  unsigned __int64 v21; // kr10_8
  int v22; // eax
  int v23; // ebx
  unsigned __int8 *v24; // r14
  __int64 v25; // rax
  unsigned int v26; // ebx
  unsigned __int128 v27; // rax
  unsigned __int64 v28; // kr20_8
  int v29; // eax
  int v30; // ebx
  unsigned int v31; // r9d
  unsigned __int128 v32; // rax
  unsigned __int8 *v33; // rbx
  unsigned __int8 *v34; // rcx
  unsigned __int8 *v35; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int8 *v36; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *v37; // [rsp+40h] [rbp-18h]
  unsigned __int8 *v38; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int8 *v39; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 *v40; // [rsp+B0h] [rbp+58h]
  unsigned __int16 *v41; // [rsp+B8h] [rbp+60h]

  v41 = a4;
  v40 = a3;
  v4 = a4;
  v5 = a3;
  v8 = 0;
  if ( !*((_DWORD *)a2 + 1325) )
  {
    v9 = *((_QWORD *)this + 6);
    v10 = (unsigned __int8 *)v9;
    if ( v9 )
    {
      while ( !(unsigned int)fSameTable((struct tagTABLELIST *)v10, a2) )
      {
        v10 = (unsigned __int8 *)*((_QWORD *)v10 + 6);
        if ( !v10 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      v35 = 0;
      v39 = 0;
      v38 = 0;
      if ( v9 )
        v8 = *(_WORD *)(v9 + 40);
      v10 = MMMAlloc(0x38u, (unsigned int)a2);
      v36 = v10;
      OnNullThrowOOM(v10);
      *((_WORD *)v10 + 20) = v8 + 1;
      v11 = -1;
      do
        ++v11;
      while ( *((_WORD *)a2 + v11 + 2136) );
      v12 = v11 + 1;
      v14 = (unsigned int)(v11 + 1);
      v13 = (unsigned int)(v11 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v14, 2u) )
        LODWORD(v13) = -1;
      v37 = MMMAlloc(v13, DWORD2(v13));
      v35 = v37;
      OnNullThrowOOM(v37);
      v15 = StringCchCopyW((unsigned __int16 *)v37, v12, (const unsigned __int16 *)a2 + 2136);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180048408[0] )
            bidTraceW(off_1800481B8[0], 875520, off_180048408[0], (unsigned int)v15, 855);
        }
        ThrowHR(v16);
      }
      v17 = 0;
      if ( !*((_DWORD *)a2 + 804) )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)a2 + v18 + 1094) );
        v19 = v18 + 1;
        v21 = (unsigned int)(v18 + 1);
        v20 = (unsigned int)(v18 + 1) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v21, 2u) )
          LODWORD(v20) = -1;
        v17 = MMMAlloc(v20, DWORD2(v20));
        v39 = v17;
        OnNullThrowOOM(v17);
        v22 = StringCchCopyW((unsigned __int16 *)v17, v19, (const unsigned __int16 *)a2 + 1094);
        v23 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048400[0] )
            bidTraceW(off_1800481B8[0], 881664, off_180048400[0], (unsigned int)v22, 861);
          ThrowHR(v23);
        }
      }
      v24 = 0;
      if ( !*((_DWORD *)a2 + 1065) )
      {
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)a2 + v25 + 1616) );
        v26 = v25 + 1;
        v28 = (unsigned int)(v25 + 1);
        v27 = (unsigned int)(v25 + 1) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v28, 2u) )
          LODWORD(v27) = -1;
        v24 = MMMAlloc(v27, DWORD2(v27));
        v38 = v24;
        OnNullThrowOOM(v24);
        v29 = StringCchCopyW((unsigned __int16 *)v24, v26, (const unsigned __int16 *)a2 + 1616);
        v30 = v29;
        if ( v29 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800483F8[0] )
            bidTraceW(off_1800481B8[0], 888832, off_1800483F8[0], (unsigned int)v29, 868);
          ThrowHR(v30);
        }
        v5 = v40;
      }
      *((_DWORD *)v10 + 6) = 0;
      *((_QWORD *)v10 + 4) = 0;
      *((_QWORD *)v10 + 6) = *((_QWORD *)this + 6);
      v35 = 0;
      *(_QWORD *)v10 = v37;
      v39 = 0;
      *((_QWORD *)v10 + 1) = v17;
      v38 = 0;
      *((_QWORD *)v10 + 2) = v24;
      v36 = 0;
      *((_QWORD *)this + 6) = v10;
      CAutoP<_GUID>::~CAutoP<_GUID>(&v38);
      CAutoP<_GUID>::~CAutoP<_GUID>(&v39);
      CAutoP<_GUID>::~CAutoP<_GUID>(&v35);
      CAutoP<_GUID>::~CAutoP<_GUID>(&v36);
      v4 = v41;
    }
    if ( !*((_DWORD *)a2 + 2396) && *((_WORD *)a2 + 4790) == 0xFFFF )
    {
      v31 = *((unsigned __int16 *)v10 + 13);
      if ( v31 == 10 * (v31 / 0xA) )
      {
        v32 = (v31 + 10) * (unsigned __int128)2u;
        if ( !is_mul_ok(v31 + 10, 2u) )
          LODWORD(v32) = -1;
        v33 = MMMAlloc(v32, DWORD2(v32));
        OnNullThrowOOM(v33);
        memcpy_0(v33, *((const void **)v10 + 4), 2LL * *((unsigned __int16 *)v10 + 13));
        v34 = (unsigned __int8 *)*((_QWORD *)v10 + 4);
        if ( v34 )
          MMMFree(v34);
        *((_QWORD *)v10 + 4) = v33;
      }
      *(_WORD *)(*((_QWORD *)v10 + 4) + 2LL * (unsigned __int16)(*((_WORD *)v10 + 13))++) = *((_WORD *)a2 + 520);
    }
    *v5 = *((_WORD *)v10 + 20);
    *v4 = ++*((_WORD *)v10 + 12);
  }
}

```

## disassembly

```asm
0x180004798  mov     [rsp-40h+arg_18], r9
0x18000479d  mov     [rsp-40h+arg_10], r8
0x1800047a2  push    rbp
0x1800047a3  push    rbx
0x1800047a4  push    rsi
0x1800047a5  push    rdi
0x1800047a6  push    r12
0x1800047a8  push    r13
0x1800047aa  push    r14
0x1800047ac  push    r15
0x1800047ae  mov     rbp, rsp
0x1800047b1  sub     rsp, 58h
0x1800047b5  mov     r15, r9
0x1800047b8  mov     r12, r8
0x1800047bb  mov     rsi, rdx
0x1800047be  mov     r13, rcx
0x1800047c1  xor     ebx, ebx
0x1800047c3  cmp     [rdx+14B4h], ebx
0x1800047c9  jnz     loc_180004B16
0x1800047cf  mov     r14, [rcx+30h]
0x1800047d3  mov     rdi, r14
0x1800047d6  test    r14, r14
0x1800047d9  jz      short loc_1800047F7
0x1800047db  mov     rdx, rsi; struct tagCOLRSDATA *
0x1800047de  mov     rcx, rdi; struct tagTABLELIST *
0x1800047e1  call    ?fSameTable@@YAHPEAUtagTABLELIST@@PEAUtagCOLRSDATA@@@Z; fSameTable(tagTABLELIST *,tagCOLRSDATA *)
0x1800047e6  test    eax, eax
0x1800047e8  jnz     loc_180004A6D
0x1800047ee  mov     rdi, [rdi+30h]
0x1800047f2  test    rdi, rdi
0x1800047f5  jnz     short loc_1800047DB
0x1800047f7  xor     r15d, r15d
0x1800047fa  mov     [rbp+var_28], r15
0x1800047fe  mov     [rbp+arg_8], r15
0x180004802  mov     [rbp+arg_0], r15
0x180004806  test    r14, r14
0x180004809  jz      short loc_180004810
0x18000480b  movzx   ebx, word ptr [r14+28h]
0x180004810  mov     ecx, 38h ; '8'; unsigned int
0x180004815  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000481a  mov     rdi, rax
0x18000481d  mov     [rbp+var_20], rax
0x180004821  mov     rcx, rax; void *
0x180004824  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004829  inc     bx
0x18000482c  mov     [rdi+28h], bx
0x180004830  lea     r14, [rsi+10B0h]
0x180004837  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000483b  mov     rax, rcx
0x18000483e  inc     rax
0x180004841  cmp     [r14+rax*2], r15w
0x180004846  jnz     short loc_18000483E
0x180004848  lea     ebx, [rax+1]
0x18000484b  mov     eax, 2
0x180004850  mul     rbx
0x180004853  cmovb   rax, rcx
0x180004857  mov     ecx, eax; unsigned int
0x180004859  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000485e  mov     r15, rax
0x180004861  mov     [rbp+var_18], rax
0x180004865  mov     [rbp+var_28], rax
0x180004869  mov     rcx, rax; void *
0x18000486c  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004871  mov     r8, r14; unsigned __int16 *
0x180004874  mov     edx, ebx; unsigned __int64
0x180004876  mov     rcx, r15; unsigned __int16 *
0x180004879  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000487e  mov     ebx, eax
0x180004880  test    eax, eax
0x180004882  jns     short loc_1800048C4
0x180004884  test    byte ptr cs:_bidGblFlags, 2
0x18000488b  jz      short loc_1800048BC
0x18000488d  mov     rcx, cs:off_180048408; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004894  test    rcx, rcx
0x180004897  jz      short loc_1800048BC
0x180004899  mov     [rsp+58h+var_38], 357h
0x1800048a1  mov     r9d, eax
0x1800048a4  mov     r8, cs:off_180048408; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x1800048ab  mov     edx, 0D5C00h
0x1800048b0  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800048b7  call    _bidTraceW
0x1800048bc  mov     ecx, ebx; int
0x1800048be  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800048c4  xor     ebx, ebx
0x1800048c6  mov     r15d, ebx
0x1800048c9  cmp     [rsi+0C90h], ebx
0x1800048cf  jnz     loc_180004967
0x1800048d5  lea     r14, [rsi+88Ch]
0x1800048dc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800048e0  mov     rax, rcx
0x1800048e3  inc     rax
0x1800048e6  cmp     [r14+rax*2], bx
0x1800048eb  jnz     short loc_1800048E3
0x1800048ed  lea     ebx, [rax+1]
0x1800048f0  mov     eax, 2
0x1800048f5  mul     rbx
0x1800048f8  cmovb   rax, rcx
0x1800048fc  mov     ecx, eax; unsigned int
0x1800048fe  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004903  mov     r15, rax
0x180004906  mov     [rbp+arg_8], rax
0x18000490a  mov     rcx, rax; void *
0x18000490d  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004912  mov     r8, r14; unsigned __int16 *
0x180004915  mov     edx, ebx; unsigned __int64
0x180004917  mov     rcx, r15; unsigned __int16 *
0x18000491a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000491f  mov     ebx, eax
0x180004921  test    eax, eax
0x180004923  jns     short loc_180004965
0x180004925  test    byte ptr cs:_bidGblFlags, 2
0x18000492c  jz      short loc_18000495D
0x18000492e  mov     rcx, cs:off_180048400; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004935  test    rcx, rcx
0x180004938  jz      short loc_18000495D
0x18000493a  mov     [rsp+58h+var_38], 35Dh
0x180004942  mov     r9d, eax
0x180004945  mov     r8, cs:off_180048400; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x18000494c  mov     edx, 0D7400h
0x180004951  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180004958  call    _bidTraceW
0x18000495d  mov     ecx, ebx; int
0x18000495f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004965  xor     ebx, ebx
0x180004967  mov     r14, rbx
0x18000496a  cmp     [rsi+10A4h], ebx
0x180004970  jnz     loc_180004A0C
0x180004976  lea     r12, [rsi+0CA0h]
0x18000497d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004981  mov     rax, rcx
0x180004984  inc     rax
0x180004987  cmp     [r12+rax*2], bx
0x18000498c  jnz     short loc_180004984
0x18000498e  lea     ebx, [rax+1]
0x180004991  mov     eax, 2
0x180004996  mul     rbx
0x180004999  cmovb   rax, rcx
0x18000499d  mov     ecx, eax; unsigned int
0x18000499f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800049a4  mov     r14, rax
0x1800049a7  mov     [rbp+arg_0], rax
0x1800049ab  mov     rcx, rax; void *
0x1800049ae  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800049b3  mov     r8, r12; unsigned __int16 *
0x1800049b6  mov     edx, ebx; unsigned __int64
0x1800049b8  mov     rcx, r14; unsigned __int16 *
0x1800049bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800049c0  mov     ebx, eax
0x1800049c2  test    eax, eax
0x1800049c4  jns     short loc_180004A06
0x1800049c6  test    byte ptr cs:_bidGblFlags, 2
0x1800049cd  jz      short loc_1800049FE
0x1800049cf  mov     rcx, cs:off_1800483F8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x1800049d6  test    rcx, rcx
0x1800049d9  jz      short loc_1800049FE
0x1800049db  mov     [rsp+58h+var_38], 364h
0x1800049e3  mov     r9d, eax
0x1800049e6  mov     r8, cs:off_1800483F8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x1800049ed  mov     edx, 0D9000h
0x1800049f2  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800049f9  call    _bidTraceW
0x1800049fe  mov     ecx, ebx; int
0x180004a00  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004a06  mov     r12, [rbp+arg_10]
0x180004a0a  xor     ebx, ebx
0x180004a0c  mov     dword ptr [rdi+18h], 0
0x180004a13  mov     [rdi+20h], rbx
0x180004a17  mov     rax, [r13+30h]
0x180004a1b  mov     [rdi+30h], rax
0x180004a1f  mov     [rbp+var_28], rbx
0x180004a23  mov     rax, [rbp+var_18]
0x180004a27  mov     [rdi], rax
0x180004a2a  mov     [rbp+arg_8], rbx
0x180004a2e  mov     [rdi+8], r15
0x180004a32  mov     [rbp+arg_0], rbx
0x180004a36  mov     [rdi+10h], r14
0x180004a3a  mov     [rbp+var_20], rbx
0x180004a3e  mov     [r13+30h], rdi
0x180004a42  lea     rcx, [rbp+arg_0]
0x180004a46  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180004a4b  nop
0x180004a4c  lea     rcx, [rbp+arg_8]
0x180004a50  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180004a55  nop
0x180004a56  lea     rcx, [rbp+var_28]
0x180004a5a  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180004a5f  nop
0x180004a60  lea     rcx, [rbp+var_20]
0x180004a64  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180004a69  mov     r15, [rbp+arg_18]
0x180004a6d  cmp     [rsi+2570h], ebx
0x180004a73  jnz     loc_180004B01
0x180004a79  or      r10, 0FFFFFFFFFFFFFFFFh
0x180004a7d  cmp     [rsi+256Ch], r10w
0x180004a85  jnz     short loc_180004B01
0x180004a87  movzx   r9d, word ptr [rdi+1Ah]
0x180004a8c  mov     eax, 0CCCCCCCDh
0x180004a91  mul     r9d
0x180004a94  shr     edx, 3
0x180004a97  lea     r8d, [rdx+rdx*4]
0x180004a9b  add     r8d, r8d
0x180004a9e  cmp     r9d, r8d
0x180004aa1  jnz     short loc_180004AEA
0x180004aa3  lea     edx, [r9+0Ah]; unsigned int
0x180004aa7  lea     eax, [r10+3]
0x180004aab  mul     rdx
0x180004aae  cmovb   rax, r10
0x180004ab2  mov     ecx, eax; unsigned int
0x180004ab4  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004ab9  mov     rbx, rax
0x180004abc  mov     rcx, rax; void *
0x180004abf  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004ac4  movzx   r8d, word ptr [rdi+1Ah]
0x180004ac9  add     r8, r8; Size
0x180004acc  mov     rdx, [rdi+20h]; Src
0x180004ad0  mov     rcx, rbx; void *
0x180004ad3  call    memcpy_0
0x180004ad8  mov     rcx, [rdi+20h]; unsigned __int8 *
0x180004adc  test    rcx, rcx
0x180004adf  jz      short loc_180004AE6
0x180004ae1  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180004ae6  mov     [rdi+20h], rbx
0x180004aea  movzx   edx, word ptr [rdi+1Ah]
0x180004aee  mov     rcx, [rdi+20h]
0x180004af2  movzx   eax, word ptr [rsi+410h]
0x180004af9  mov     [rcx+rdx*2], ax
0x180004afd  inc     word ptr [rdi+1Ah]
0x180004b01  movzx   eax, word ptr [rdi+28h]
0x180004b05  mov     [r12], ax
0x180004b0a  inc     word ptr [rdi+18h]
0x180004b0e  movzx   eax, word ptr [rdi+18h]
0x180004b12  mov     [r15], ax
0x180004b16  add     rsp, 58h
0x180004b1a  pop     r15
0x180004b1c  pop     r14
0x180004b1e  pop     r13
0x180004b20  pop     r12
0x180004b22  pop     rdi
0x180004b23  pop     rsi
0x180004b24  pop     rbx
0x180004b25  pop     rbp
0x180004b26  retn
```
