# CLine::Measure(CMeasurer &,uint,long *,long,bool,CBreakRecLine const *)

- ea: `0x1800810d8`
- end: `0x180081654`
- name: `?Measure@CLine@@QEAAHAEAVCMeasurer@@IPEAJJ_NPEBUCBreakRecLine@@@Z`
- size: `1404`
- prototype: `__int64 __usercall@<rax>(CLine *__hidden this@<rcx>, struct CMeasurer *@<rdx>, unsigned int@<r8d>, int *@<r9>, int, bool, const struct CBreakRecLine *)`
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x18006e074`
- `0x18007d270`
- `0x18007f95c`
- `0x1800c35a0`

## callees

- `0x18001c800`
- `0x18002af88`
- `0x18002dd3c`
- `0x18003211c`
- `0x18006e7e0`
- `0x180081004`
- `0x1800810b8`
- `0x1800810d8`
- `0x1800824a8`
- `0x180082a5c`
- `0x18008c71c`
- `0x1800c34bc`
- `0x1800d9e48`
- `0x18013c8fe`
- `0x18013c916`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180081467`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180081467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008146d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008146d`

## pseudocode

```c
__int64 __fastcall CLine::Measure(
        CLine *this,
        struct CMeasurer *a2,
        unsigned int a3,
        int *a4,
        int a5,
        bool a6,
        const struct CBreakRecLine *a7)
{
  __int64 v7; // rax
  int v8; // edi
  __int64 v11; // rcx
  int v12; // edx
  char v13; // si
  _BYTE *v14; // rax
  int v15; // edx
  char v16; // cl
  int v17; // r13d
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 *v26; // rax
  __int64 v27; // rsi
  int v28; // edi
  _DWORD *LockTelemetry; // rax
  struct Ptls6::ols *Pols; // rax
  Ptls6::ols *v31; // rdi
  __int16 v32; // ax
  int *v33; // r15
  unsigned int v34; // esi
  int v35; // eax
  __int64 v36; // rcx
  int v37; // edi
  __int64 v38; // rax
  __int64 *v39; // rdi
  __int64 v40; // rax
  __int64 v41; // rcx
  const struct CParaFormat *PF; // rax
  __int64 v43; // rax
  RTL_SRWLOCK *Lock; // rax
  __int64 v46; // rax
  __int64 v47; // rcx
  const struct CParaFormat *v48; // rax
  const struct CParaFormat *v49; // rax
  const struct CParaFormat *v50; // rax
  int v51; // eax
  int Height; // eax
  _QWORD v53[2]; // [rsp+58h] [rbp-41h] BYREF
  bool v54; // [rsp+68h] [rbp-31h]
  char v55; // [rsp+69h] [rbp-30h]
  int v56; // [rsp+70h] [rbp-29h] BYREF
  char v57; // [rsp+74h] [rbp-25h]
  int v58; // [rsp+78h] [rbp-21h]
  __int64 v59; // [rsp+80h] [rbp-19h]
  __int128 v60; // [rsp+88h] [rbp-11h]
  __int16 v61; // [rsp+98h] [rbp-1h]
  int v62; // [rsp+9Ah] [rbp+1h]
  __int16 v63; // [rsp+9Eh] [rbp+5h]

  v7 = *((_QWORD *)a2 + 19);
  v8 = a3 & 1;
  if ( (*(_DWORD *)(v7 + 116) & 0x10000) != 0
    && (*(_DWORD *)(*(_QWORD *)(v7 + 16) + 288LL) & 0x200000) == 0
    && (a3 & 1) != 0
    && *((_DWORD *)a2 + 8)
    && CRchTxtPtr::GetPrevUnhiddenChar(a2) == 11 )
  {
    v8 = 0;
  }
  v11 = *((_QWORD *)a2 + 2);
  if ( v11 )
    v11 = *(_QWORD *)(v11 + 40);
  v12 = *(_DWORD *)(v11 + 184);
  if ( (v12 & 0x40000000) != 0 )
  {
    v13 = 0x80;
  }
  else if ( (v12 & 0x400000) != 0 || (*(_BYTE *)(v11 + 276) & 0xC0) == 0xC0 )
  {
    v13 = 64;
  }
  else
  {
    v13 = 0;
  }
  *((_BYTE *)a2 + 111) &= 0x1Fu;
  *((_BYTE *)a2 + 111) |= v13;
  memset_0(
    (char *)a2 + 96,
    0,
    4LL * *((unsigned __int8 *)&dword_1802A326C + ((unsigned __int64)*((unsigned __int8 *)a2 + 111) >> 5)) + 32);
  *((_BYTE *)a2 + 111) &= 0x1Fu;
  v14 = (char *)a2 + 110;
  *((_BYTE *)a2 + 111) |= v13;
  if ( v8 )
    *v14 |= 2u;
  v15 = *((_DWORD *)a2 + 8);
  v16 = *((_BYTE *)a2 + 277) & 0xBF;
  *(_QWORD *)((char *)a2 + 204) = 0;
  *((_DWORD *)a2 + 58) = -1;
  *((_DWORD *)a2 + 42) = v15;
  if ( v8 )
    *v14 |= 2u;
  *((_BYTE *)a2 + 277) = v16 | 0x20;
  v17 = 0;
  if ( a7 )
  {
    v51 = *((_DWORD *)a7 + 2);
    if ( v51 > 0 )
      v17 = v51 + v15;
  }
  v18 = *((_QWORD *)a2 + 2);
  if ( v18 )
    v19 = *(_QWORD *)(v18 + 40);
  else
    v19 = 0;
  if ( (*(_BYTE *)(v19 + 358) & 1) == 0 )
  {
    v34 = a3;
    v33 = a4;
LABEL_60:
    v37 = CMeasurer::MeasureLine(a2, v34, v33);
    goto LABEL_36;
  }
  v53[0] = a2;
  if ( v18 )
    v20 = *(_QWORD *)(v18 + 40);
  else
    v20 = 0;
  v21 = *(_QWORD *)(v20 + 256);
  v54 = 0;
  if ( v21 && (v22 = *(__int64 **)(v21 + 80)) != 0 )
  {
    v54 = (v22[2] & 4) != 0;
    v23 = *v22;
  }
  else
  {
    v23 = 0;
  }
  v53[1] = v23;
  v55 = 0;
  if ( v18 )
    v24 = *(_QWORD *)(v18 + 40);
  else
    v24 = 0;
  v25 = *(_QWORD *)(v24 + 256);
  if ( v25 && (v26 = *(__int64 **)(v25 + 80)) != 0 )
    v27 = *v26;
  else
    v27 = 0;
  v28 = (int)CLockSharedData::LockOwner;
  v56 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v28 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v46 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v46 + 4);
  }
  ++CLSLock::_cOLSBusy;
  v57 = 1;
  v60 = 0;
  g_cFCLock += v27 == 0;
  v59 = 0;
  v61 = 0;
  v58 = v27 == 0;
  Pols = CMeasurerLS::GetPols((CMeasurerLS *)v53);
  v31 = Pols;
  if ( !Pols )
  {
    v34 = a3;
    v33 = a4;
LABEL_61:
    v47 = v59;
    if ( v59 )
    {
      *(_OWORD *)(v59 + 56) = v60;
      *(_WORD *)(v47 + 72) = v61;
      *(_DWORD *)(v47 + 74) = v62;
      *(_WORD *)(v47 + 78) = v63;
    }
    g_cFCLock -= v58;
    CLSLock::~CLSLock((CLSLock *)&v56);
    goto LABEL_60;
  }
  v32 = *((_WORD *)Pols + 526);
  if ( (v32 & 0x20) != 0 && !a7 )
  {
    *((_WORD *)v31 + 526) = v32 & 0xFFDF;
    Ptls6::ols::ClearRunCache(v31);
  }
  v33 = a4;
  v34 = a3;
  v35 = Ptls6::ols::MeasureLine(v31, a3, a4, v17, 1, 0, 0, 0, 0, a7);
  if ( v35 < 0 )
    goto LABEL_61;
  v36 = v59;
  v37 = v35 != 1;
  if ( v59 )
  {
    *(_OWORD *)(v59 + 56) = v60;
    *(_WORD *)(v36 + 72) = v61;
    *(_DWORD *)(v36 + 74) = v62;
    *(_WORD *)(v36 + 78) = v63;
  }
  g_cFCLock -= v58;
  CLSLock::~CLSLock((CLSLock *)&v56);
LABEL_36:
  if ( !v37 )
    return 0;
  memcpy_0(
    this,
    (char *)a2 + 96,
    4LL * *((unsigned __int8 *)&dword_1802A326C + ((unsigned __int64)*((unsigned __int8 *)a2 + 111) >> 5)) + 32);
  if ( (*((_BYTE *)a2 + 277) & 0x10) != 0 )
  {
    Height = CLine::GetHeight(this, 0, 0);
    CLineBasic::SetHeight(this, (Height + 4) & 0xFFFFFFF8);
  }
  v38 = *((_QWORD *)a2 + 19);
  if ( (*(_DWORD *)(v38 + 116) & 0x10000) != 0 && (*(_DWORD *)(*(_QWORD *)(v38 + 16) + 288LL) & 0x200000) == 0 )
  {
    v39 = (__int64 *)((char *)a2 + 16);
    v40 = *((_QWORD *)a2 + 2);
    v41 = v40 ? *(_QWORD *)(v40 + 40) : 0LL;
    if ( (*(_BYTE *)(v41 + 176) & 1) != 0 )
    {
      PF = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
      if ( !PF )
        PF = CRchTxtPtr::GetPF(a2);
      if ( *((__int16 *)PF + 16) <= -2 )
      {
        v48 = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
        if ( !v48 )
          v48 = CRchTxtPtr::GetPF(a2);
        if ( *((__int16 *)v48 + 16) >= -10 )
        {
          v49 = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
          if ( !v49 )
            v49 = CRchTxtPtr::GetPF(a2);
          *((_BYTE *)this + 13) ^= (*((_BYTE *)this + 13) ^ ~*((_BYTE *)v49 + 32)) & 0xF;
        }
      }
      v43 = *v39;
      if ( *v39 )
        v43 = *(_QWORD *)(v43 + 40);
      if ( *(__int16 *)(v43 + 276) < 0 )
      {
        v50 = (const struct CParaFormat *)*((_QWORD *)a2 + 37);
        if ( !v50 )
          v50 = CRchTxtPtr::GetPF(a2);
        if ( (*(_DWORD *)v50 & 0x100) != 0 )
          *((_BYTE *)this + 13) |= 0x10u;
      }
      if ( CTxtPtr::GetPrevChar((struct CMeasurer *)((char *)a2 + 16)) == 12 )
        *((_BYTE *)this + 13) |= 0x40u;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800810d8  mov     rax, rsp
0x1800810db  mov     [rax+8], rbx
0x1800810df  mov     [rax+20h], r9
0x1800810e3  mov     [rax+18h], r8d
0x1800810e7  push    rbp
0x1800810e8  push    rsi
0x1800810e9  push    rdi
0x1800810ea  push    r12
0x1800810ec  push    r13
0x1800810ee  push    r14
0x1800810f0  push    r15
0x1800810f2  lea     rbp, [rax-47h]
0x1800810f6  sub     rsp, 0A0h
0x1800810fd  mov     rax, [rdx+98h]
0x180081104  mov     edi, r8d
0x180081107  and     edi, 1
0x18008110a  mov     rbx, rdx
0x18008110d  mov     r14, rcx
0x180081110  test    dword ptr [rax+74h], 10000h
0x180081117  jz      short loc_18008112D
0x180081119  mov     rax, [rax+10h]
0x18008111d  test    dword ptr [rax+120h], 200000h
0x180081127  jz      loc_180081488
0x18008112d  mov     rcx, [rbx+10h]
0x180081131  test    rcx, rcx
0x180081134  jz      short loc_18008113A
0x180081136  mov     rcx, [rcx+28h]
0x18008113a  mov     edx, [rcx+0B8h]
0x180081140  mov     eax, edx
0x180081142  shr     eax, 1Eh
0x180081145  test    al, 1
0x180081147  jnz     loc_1800815B9
0x18008114d  bt      edx, 16h
0x180081151  jb      loc_1800815C1
0x180081157  mov     al, [rcx+114h]
0x18008115d  and     al, 0C0h
0x18008115f  cmp     al, 0C0h
0x180081161  jz      loc_1800815C1
0x180081167  xor     sil, sil
0x18008116a  and     byte ptr [rbx+6Fh], 1Fh
0x18008116e  lea     rcx, dword_1802A326C
0x180081175  or      [rbx+6Fh], sil
0x180081179  xor     edx, edx; Val
0x18008117b  movzx   eax, byte ptr [rbx+6Fh]
0x18008117f  shr     rax, 5
0x180081183  movzx   r8d, byte ptr [rax+rcx]
0x180081188  lea     rcx, [rbx+60h]; void *
0x18008118c  lea     r8, ds:20h[r8*4]; Size
0x180081194  call    memset_0
0x180081199  and     byte ptr [rbx+6Fh], 1Fh
0x18008119d  lea     rax, [rbx+6Eh]
0x1800811a1  or      [rbx+6Fh], sil
0x1800811a5  xor     r9d, r9d
0x1800811a8  test    edi, edi
0x1800811aa  jz      short loc_1800811AF
0x1800811ac  or      byte ptr [rax], 2
0x1800811af  mov     cl, [rbx+115h]
0x1800811b5  mov     edx, [rbx+20h]
0x1800811b8  and     cl, 0BFh
0x1800811bb  mov     [rbx+0CCh], r9
0x1800811c2  mov     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x1800811cc  mov     [rbx+0A8h], edx
0x1800811d2  test    edi, edi
0x1800811d4  jz      short loc_1800811D9
0x1800811d6  or      byte ptr [rax], 2
0x1800811d9  mov     r15, [rbp+3Fh+arg_30]
0x1800811dd  or      cl, 20h
0x1800811e0  mov     [rbx+115h], cl
0x1800811e6  mov     r13d, r9d
0x1800811e9  test    r15, r15
0x1800811ec  jnz     loc_1800815C9
0x1800811f2  mov     r8, [rbx+10h]
0x1800811f6  test    r8, r8
0x1800811f9  jz      loc_180081522
0x1800811ff  mov     rax, [r8+28h]
0x180081203  test    byte ptr [rax+166h], 1
0x18008120a  jz      loc_1800814B3
0x180081210  mov     [rbp+3Fh+var_80], rbx
0x180081214  test    r8, r8
0x180081217  jz      loc_18008152A
0x18008121d  mov     rax, [r8+28h]
0x180081221  mov     rdx, [rax+100h]
0x180081228  mov     [rbp+3Fh+var_70], r9b
0x18008122c  test    rdx, rdx
0x18008122f  jz      short loc_18008123E
0x180081231  mov     rdx, [rdx+50h]
0x180081235  test    rdx, rdx
0x180081238  jnz     loc_1800815DE
0x18008123e  mov     rax, r9
0x180081241  mov     [rbp+3Fh+var_78], rax
0x180081245  mov     [rbp+3Fh+var_6F], r9b
0x180081249  test    r8, r8
0x18008124c  jz      loc_180081532
0x180081252  mov     rax, [r8+28h]
0x180081256  mov     rcx, [rax+100h]
0x18008125d  test    rcx, rcx
0x180081260  jz      short loc_18008126F
0x180081262  mov     rax, [rcx+50h]
0x180081266  test    rax, rax
0x180081269  jnz     loc_1800815F1
0x18008126f  mov     rsi, r9
0x180081272  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180081278  mov     [rbp+3Fh+var_68], r9d
0x18008127c  test    edi, edi
0x18008127e  jz      loc_18008145D
0x180081284  call    cs:__imp_GetCurrentThreadId
0x18008128a  cmp     edi, eax
0x18008128c  jnz     loc_18008145D
0x180081292  xor     ecx, ecx
0x180081294  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180081299  inc     dword ptr [rax]
0x18008129b  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x1800812a1  lea     rcx, [rbp+3Fh+var_80]; this
0x1800812a5  xor     eax, eax
0x1800812a7  mov     [rbp+3Fh+var_64], 1
0x1800812ab  test    rsi, rsi
0x1800812ae  xorps   xmm0, xmm0
0x1800812b1  movdqa  [rbp+3Fh+var_50], xmm0
0x1800812b6  setz    al
0x1800812b9  xor     esi, esi
0x1800812bb  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x1800812c1  mov     [rbp+3Fh+var_58], rsi
0x1800812c5  mov     [rbp+3Fh+var_40], si
0x1800812c9  mov     [rbp+3Fh+var_60], eax
0x1800812cc  call    ?GetPols@CMeasurerLS@@QEAAPEAUols@Ptls6@@XZ; CMeasurerLS::GetPols(void)
0x1800812d1  mov     rdi, rax
0x1800812d4  test    rax, rax
0x1800812d7  jz      loc_18008161E
0x1800812dd  movzx   eax, word ptr [rax+41Ch]
0x1800812e4  test    al, 20h
0x1800812e6  jnz     loc_1800815F9
0x1800812ec  mov     [rsp+48h], r15; struct CBreakRecLine *
0x1800812f1  mov     r9d, r13d; int
0x1800812f4  mov     r15, [rbp+3Fh+arg_18]
0x1800812f8  mov     rcx, rdi; this
0x1800812fb  mov     [rsp+0D0h+var_90], rsi; int *
0x180081300  mov     r8, r15; int *
0x180081303  mov     [rsp+0D0h+var_98], rsi; int *
0x180081308  mov     [rsp+0D0h+var_A0], sil; bool
0x18008130d  mov     [rsp+0D0h+var_A8], sil; bool
0x180081312  mov     esi, [rbp+3Fh+arg_10]
0x180081315  mov     edx, esi; unsigned int
0x180081317  mov     [rsp+0D0h+var_B0], 1; bool
0x18008131c  call    ?MeasureLine@ols@Ptls6@@QEAAJIPEAJJ_N1100PEBUCBreakRecLine@@@Z; Ptls6::ols::MeasureLine(uint,long *,long,bool,bool,bool,long *,long *,CBreakRecLine const *)
0x180081321  test    eax, eax
0x180081323  js      loc_1800814CE
0x180081329  mov     rcx, [rbp+3Fh+var_58]
0x18008132d  xor     edi, edi
0x18008132f  cmp     eax, 1
0x180081332  setnz   dil
0x180081336  test    rcx, rcx
0x180081339  jz      short loc_180081365
0x18008133b  mov     rax, qword ptr [rbp+3Fh+var_50]
0x18008133f  mov     [rcx+38h], rax
0x180081343  mov     rax, qword ptr [rbp+3Fh+var_50+8]
0x180081347  mov     [rcx+40h], rax
0x18008134b  mov     al, byte ptr [rbp+3Fh+var_40]
0x18008134e  mov     [rcx+48h], al
0x180081351  mov     al, byte ptr [rbp+3Fh+var_40+1]
0x180081354  mov     [rcx+49h], al
0x180081357  mov     eax, [rbp+3Fh+var_3E]
0x18008135a  mov     [rcx+4Ah], eax
0x18008135d  movzx   eax, [rbp+3Fh+var_3A]
0x180081361  mov     [rcx+4Eh], ax
0x180081365  mov     eax, [rbp+3Fh+var_60]
0x180081368  lea     rcx, [rbp+3Fh+var_68]; this
0x18008136c  sub     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x180081372  call    ??1CLSLock@@QEAA@XZ; CLSLock::~CLSLock(void)
0x180081377  test    edi, edi
0x180081379  jz      loc_180081541
0x18008137f  movzx   eax, byte ptr [rbx+6Fh]
0x180081383  lea     rcx, dword_1802A326C
0x18008138a  shr     rax, 5
0x18008138e  lea     rdx, [rbx+60h]; Src
0x180081392  movzx   r8d, byte ptr [rax+rcx]
0x180081397  mov     rcx, r14; void *
0x18008139a  lea     r8, ds:20h[r8*4]; Size
0x1800813a2  call    memcpy_0
0x1800813a7  test    byte ptr [rbx+115h], 10h
0x1800813ae  jnz     loc_18008162A
0x1800813b4  mov     rax, [rbx+98h]
0x1800813bb  test    dword ptr [rax+74h], 10000h
0x1800813c2  jz      short loc_18008143D
0x1800813c4  mov     rax, [rax+10h]
0x1800813c8  test    dword ptr [rax+120h], 200000h
0x1800813d2  jnz     short loc_18008143D
0x1800813d4  lea     rdi, [rbx+10h]
0x1800813d8  mov     rax, [rdi]
0x1800813db  test    rax, rax
0x1800813de  jz      loc_18008153A
0x1800813e4  mov     rcx, [rax+28h]
0x1800813e8  test    byte ptr [rcx+0B0h], 1
0x1800813ef  jz      short loc_18008143D
0x1800813f1  mov     rax, [rbx+128h]
0x1800813f8  test    rax, rax
0x1800813fb  jz      loc_180081515
0x180081401  cmp     word ptr [rax+20h], 0FFFEh
0x180081406  jle     loc_180081548
0x18008140c  mov     rax, [rdi]
0x18008140f  test    rax, rax
0x180081412  jz      short loc_180081418
0x180081414  mov     rax, [rax+28h]
0x180081418  movzx   eax, word ptr [rax+114h]
0x18008141f  shr     ax, 0Fh
0x180081423  test    al, al
0x180081425  jnz     loc_18008158F
0x18008142b  mov     rcx, rdi; this
0x18008142e  call    ?GetPrevChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetPrevChar(void)
0x180081433  cmp     ax, 0Ch
0x180081437  jz      loc_18008164A
0x18008143d  mov     eax, 1
0x180081442  mov     rbx, [rsp+0D0h+arg_0]
0x18008144a  add     rsp, 0A0h
0x180081451  pop     r15
0x180081453  pop     r14
0x180081455  pop     r13
0x180081457  pop     r12
0x180081459  pop     rdi
0x18008145a  pop     rsi
0x18008145b  pop     rbp
0x18008145c  retn
0x18008145d  xor     ecx, ecx
0x18008145f  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180081464  mov     rcx, rax; SRWLock
0x180081467  call    cs:__imp_AcquireSRWLockExclusive
0x18008146d  call    cs:__imp_GetCurrentThreadId
0x180081473  xor     ecx, ecx
0x180081475  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18008147b  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180081480  inc     dword ptr [rax+4]
0x180081483  jmp     loc_18008129B
0x180081488  test    edi, edi
0x18008148a  jz      loc_18008112D
0x180081490  cmp     dword ptr [rdx+20h], 0
0x180081494  jz      loc_18008112D
0x18008149a  mov     rcx, rbx; this
0x18008149d  call    ?GetPrevUnhiddenChar@CRchTxtPtr@@QEAAGXZ; CRchTxtPtr::GetPrevUnhiddenChar(void)
0x1800814a2  movzx   ecx, ax
0x1800814a5  xor     eax, eax
0x1800814a7  cmp     cx, 0Bh
0x1800814ab  cmovz   edi, eax
0x1800814ae  jmp     loc_18008112D
0x1800814b3  mov     esi, [rbp+3Fh+arg_10]
0x1800814b6  mov     r15, [rbp+3Fh+arg_18]
0x1800814ba  mov     r8, r15; int *
0x1800814bd  mov     edx, esi; unsigned int
0x1800814bf  mov     rcx, rbx; this
0x1800814c2  call    ?MeasureLine@CMeasurer@@QEAAHIPEAJ@Z; CMeasurer::MeasureLine(uint,long *)
0x1800814c7  mov     edi, eax
0x1800814c9  jmp     loc_180081377
0x1800814ce  mov     rcx, [rbp+3Fh+var_58]
0x1800814d2  test    rcx, rcx
0x1800814d5  jz      short loc_180081501
0x1800814d7  mov     rax, qword ptr [rbp+3Fh+var_50]
0x1800814db  mov     [rcx+38h], rax
0x1800814df  mov     rax, qword ptr [rbp+3Fh+var_50+8]
0x1800814e3  mov     [rcx+40h], rax
0x1800814e7  mov     al, byte ptr [rbp+3Fh+var_40]
0x1800814ea  mov     [rcx+48h], al
0x1800814ed  mov     al, byte ptr [rbp+3Fh+var_40+1]
0x1800814f0  mov     [rcx+49h], al
0x1800814f3  mov     eax, [rbp+3Fh+var_3E]
0x1800814f6  mov     [rcx+4Ah], eax
0x1800814f9  movzx   eax, [rbp+3Fh+var_3A]
0x1800814fd  mov     [rcx+4Eh], ax
0x180081501  mov     eax, [rbp+3Fh+var_60]
0x180081504  lea     rcx, [rbp+3Fh+var_68]; this
0x180081508  sub     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x18008150e  call    ??1CLSLock@@QEAA@XZ; CLSLock::~CLSLock(void)
0x180081513  jmp     short loc_1800814BA
0x180081515  mov     rcx, rbx; this
0x180081518  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18008151d  jmp     loc_180081401
0x180081522  mov     rax, r9
0x180081525  jmp     loc_180081203
0x18008152a  mov     rax, r9
0x18008152d  jmp     loc_180081221
0x180081532  mov     rax, r9
0x180081535  jmp     loc_180081256
0x18008153a  xor     ecx, ecx
0x18008153c  jmp     loc_1800813E8
0x180081541  xor     eax, eax
0x180081543  jmp     loc_180081442
0x180081548  mov     rax, [rbx+128h]
0x18008154f  test    rax, rax
0x180081552  jnz     short loc_18008155C
0x180081554  mov     rcx, rbx; this
0x180081557  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18008155c  cmp     word ptr [rax+20h], 0FFF6h
0x180081561  jl      loc_18008140C
0x180081567  mov     rax, [rbx+128h]
0x18008156e  test    rax, rax
0x180081571  jnz     short loc_18008157B
0x180081573  mov     rcx, rbx; this
0x180081576  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18008157b  mov     al, [rax+20h]
0x18008157e  not     al
0x180081580  xor     al, [r14+0Dh]
0x180081584  and     al, 0Fh
0x180081586  xor     [r14+0Dh], al
  ... truncated ...
```
