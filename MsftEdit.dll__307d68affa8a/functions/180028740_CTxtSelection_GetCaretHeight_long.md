# CTxtSelection::GetCaretHeight(long *)

- ea: `0x180028740`
- end: `0x180028b8f`
- name: `?GetCaretHeight@CTxtSelection@@IEBAHPEAJ@Z`
- size: `1103`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800266f0`

## callees

- `0x18001bc08`
- `0x180022344`
- `0x180022934`
- `0x180024554`
- `0x1800245b0`
- `0x180028740`
- `0x180028b98`
- `0x18002ab44`
- `0x18002af88`
- `0x18006e770`
- `0x18006fc24`
- `0x1800714ac`
- `0x1800810b8`
- `0x18008fb4c`
- `0x1800b2e08`
- `0x1800e4d78`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028991`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028774`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028997`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028774`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028997`

## pseudocode

```c
__int64 __fastcall CTxtSelection::GetCaretHeight(CTxtSelection *this, int *a2)
{
  int v2; // ebx
  int v3; // r12d
  _DWORD *LockTelemetry; // rax
  __int64 v6; // r13
  __int64 v7; // r13
  __int64 v8; // rdx
  __int64 *v9; // r15
  char v10; // al
  __int64 v11; // rcx
  bool v12; // bl
  unsigned int ResolutionY; // r14d
  int ZoomDenominator; // ebx
  int ZoomNumerator; // eax
  unsigned int v16; // edi
  const struct CParaFormat *PF; // rax
  __int64 Ccs; // rbx
  int v19; // r11d
  __int64 v20; // rcx
  __int64 v21; // r13
  int v22; // r14d
  __int64 v23; // rsi
  int *v24; // rdi
  RTL_SRWLOCK *Lock; // rax
  __int64 v27; // rax
  HDC DC; // rax
  __int64 v29; // rax
  void ***v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // ecx
  struct IGraphicContext *GraphicContext; // [rsp+40h] [rbp-20h] BYREF
  char v37; // [rsp+48h] [rbp-18h]
  __int64 v38; // [rsp+4Ch] [rbp-14h]
  char v39; // [rsp+54h] [rbp-Ch]
  int v40; // [rsp+A0h] [rbp+40h] BYREF
  int *v41; // [rsp+A8h] [rbp+48h]
  __int64 *v42; // [rsp+B0h] [rbp+50h] BYREF

  v41 = a2;
  v2 = (int)CLockSharedData::LockOwner;
  v3 = 0;
  v40 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v2 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v27 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v27 + 4);
  }
  ++g_cFCLock;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
    v7 = *(_QWORD *)(v6 + 40);
  else
    v7 = 0;
  v8 = *((unsigned __int16 *)this + 56);
  v42 = 0;
  if ( (v8 & 0x8000u) != 0LL )
    v8 = *(unsigned __int16 *)(v7 + 352);
  if ( (*(int (__fastcall **)(CCharFormatArray *, __int64, __int64 **))(*(_QWORD *)qword_1802DF5C8 + 32LL))(
         qword_1802DF5C8,
         v8,
         &v42) >= 0 )
  {
    v9 = v42;
  }
  else
  {
    v9 = g_defaultCF;
    v42 = g_defaultCF;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 17) + 24LL) + 80LL))(*(_QWORD *)(*((_QWORD *)this + 17) + 24LL));
  v11 = *((_QWORD *)this + 17);
  v12 = v10;
  if ( *(_BYTE *)(v11 + 44)
    || (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 24) + 24LL))(*(_QWORD *)(v11 + 24)) )
  {
    ResolutionY = CHDC::GetResolutionY((CHDC *)(*((_QWORD *)this + 17) + 24LL));
  }
  else
  {
    DC = CTxtEdit::TxGetDC((CTxtEdit *)v7);
    GraphicContext = CreateGraphicContext(v12, *(const struct IDpiAccessor **)(v7 + 568), DC, 0);
    v37 = 0;
    v38 = 0;
    v39 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)GraphicContext + 24LL))(GraphicContext) )
    {
      CHDC::~CHDC((CHDC *)&GraphicContext);
      v16 = -1;
      goto LABEL_27;
    }
    ResolutionY = (*(__int64 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)GraphicContext + 104LL))(GraphicContext);
    v29 = (*(__int64 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)GraphicContext + 48LL))(GraphicContext);
    v30 = &CITextHost2Ref::s_dummyHost;
    if ( *(_QWORD *)(v7 + 112) )
      v30 = *(void ****)(v7 + 112);
    ((void (__fastcall *)(void ***, __int64))(*v30)[4])(v30, v29);
    CHDC::~CHDC((CHDC *)&GraphicContext);
  }
  if ( !v12 )
  {
    ZoomDenominator = CDisplay::GetZoomDenominator(*((CDisplay **)this + 17));
    ZoomNumerator = CDisplay::GetZoomNumerator(*((CDisplay **)this + 17));
    ResolutionY = CW32System::MulDivFunc(ResolutionY, ZoomNumerator, ZoomDenominator);
  }
  v16 = -1;
  PF = CTxtSelection::GetPF(this);
  Ccs = CTxtEdit::GetCcs(v7, v9, (*(_DWORD *)PF >> 26) & 7, ResolutionY, -1, 0, 0, 0);
  if ( Ccs )
  {
    v19 = 0;
    if ( *((_WORD *)v9 + 5) )
      v3 = CW32System::MulDivFunc(*((__int16 *)v9 + 5), ResolutionY, 1440);
    v20 = *((char *)v9 + 62);
    v21 = -50;
    if ( (_BYTE)v20 )
    {
      v32 = v20 * *(__int16 *)(Ccs + 18);
      v33 = -50;
      if ( v32 >= 0 )
        v33 = 50;
      v34 = (v32 + v33) / 100;
      if ( (unsigned __int64)(v34 + 0x80000000LL) > 0xFFFFFFFF )
        LODWORD(v34) = -1;
    }
    else
    {
      if ( (*(_DWORD *)v9 & 0x20000) != 0 )
      {
        v35 = 2 * *(__int16 *)(Ccs + 18);
      }
      else
      {
        v22 = v19;
        if ( (*(_DWORD *)v9 & 0x10000) == 0 )
          goto LABEL_21;
        v35 = 3 * (*(__int16 *)(Ccs + 22) - *(__int16 *)(Ccs + 18));
      }
      LODWORD(v34) = v35 / 5;
    }
    v22 = CCcs::ScaleMetric((CCcs *)Ccs, v34);
LABEL_21:
    if ( (unsigned int)CDisplay::FAdjustFELineHt(*((CDisplay **)this + 17)) && (*(_BYTE *)(Ccs + 361) & 0x10) != 0 )
    {
      v31 = 15LL * (int)CCcs::ScaleMetric((CCcs *)Ccs, *(__int16 *)(Ccs + 18));
      if ( v31 >= 0 )
        v21 = 50;
      v23 = (v31 + v21) / 100;
      if ( (unsigned __int64)(v23 + 0x80000000LL) > 0xFFFFFFFF )
        LODWORD(v23) = -1;
    }
    else
    {
      LODWORD(v23) = 0;
    }
    v24 = v41;
    if ( v41 )
      *v24 = v23 - v22 - v3 + CCcs::ScaleMetric((CCcs *)Ccs, *(__int16 *)(Ccs + 20));
    v16 = CCcs::ScaleMetric((CCcs *)Ccs, *(__int16 *)(Ccs + 18)) + 2 * v23;
    CCcs::Release((CCcs *)Ccs);
  }
LABEL_27:
  --g_cFCLock;
  CWriteLock::~CWriteLock((CWriteLock *)&v40);
  return v16;
}

```

## disassembly

```asm
0x180028740  mov     [rsp-38h+arg_18], rbx
0x180028745  mov     [rsp-38h+arg_8], rdx
0x18002874a  push    rbp
0x18002874b  push    rsi
0x18002874c  push    rdi
0x18002874d  push    r12
0x18002874f  push    r13
0x180028751  push    r14
0x180028753  push    r15
0x180028755  mov     rbp, rsp
0x180028758  sub     rsp, 60h
0x18002875c  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180028762  xor     r12d, r12d
0x180028765  mov     [rbp+arg_0], r12d
0x180028769  mov     rsi, rcx
0x18002876c  test    ebx, ebx
0x18002876e  jz      loc_180028987
0x180028774  call    cs:__imp_GetCurrentThreadId
0x18002877a  cmp     ebx, eax
0x18002877c  jnz     loc_180028987
0x180028782  xor     ecx, ecx
0x180028784  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180028789  inc     dword ptr [rax]
0x18002878b  inc     cs:?g_cFCLock@@3JA; long g_cFCLock
0x180028791  mov     r13, [rsi+18h]
0x180028795  test    r13, r13
0x180028798  jz      loc_180028AE3
0x18002879e  mov     r13, [r13+28h]
0x1800287a2  movzx   edx, word ptr [rsi+70h]
0x1800287a6  mov     [rbp+arg_10], r12
0x1800287aa  test    dx, dx
0x1800287ad  jns     short loc_1800287B7
0x1800287af  movzx   edx, word ptr [r13+160h]
0x1800287b7  mov     rcx, cs:qword_1802DF5C8
0x1800287be  lea     r8, [rbp+arg_10]
0x1800287c2  mov     rax, [rcx]
0x1800287c5  mov     rax, [rax+20h]
0x1800287c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287ce  test    eax, eax
0x1800287d0  jns     loc_18002897E
0x1800287d6  lea     r15, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x1800287dd  mov     [rbp+arg_10], r15
0x1800287e1  mov     rax, [rsi+88h]
0x1800287e8  mov     rcx, [rax+18h]
0x1800287ec  mov     rax, [rcx]
0x1800287ef  mov     rax, [rax+50h]
0x1800287f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287f8  mov     rcx, [rsi+88h]
0x1800287ff  mov     bl, al
0x180028801  cmp     [rcx+2Ch], r12b
0x180028805  jnz     short loc_18002881F
0x180028807  mov     rcx, [rcx+18h]
0x18002880b  mov     rdx, [rcx]
0x18002880e  mov     rax, [rdx+18h]
0x180028812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028817  test    al, al
0x180028819  jz      loc_1800289B2
0x18002881f  mov     rcx, [rsi+88h]
0x180028826  add     rcx, 18h; this
0x18002882a  call    ?GetResolutionY@CHDC@@QEBAJXZ; CHDC::GetResolutionY(void)
0x18002882f  mov     r14d, eax
0x180028832  test    bl, bl
0x180028834  jnz     short loc_180028860
0x180028836  mov     rcx, [rsi+88h]; this
0x18002883d  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x180028842  mov     rcx, [rsi+88h]; this
0x180028849  mov     ebx, eax
0x18002884b  call    ?GetZoomNumerator@CDisplay@@QEBAJXZ; CDisplay::GetZoomNumerator(void)
0x180028850  mov     edx, eax; int
0x180028852  mov     r8d, ebx; int
0x180028855  mov     ecx, r14d; int
0x180028858  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18002885d  mov     r14d, eax
0x180028860  mov     rcx, rsi; this
0x180028863  or      edi, 0FFFFFFFFh
0x180028866  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x18002886b  mov     [rsp+60h+var_28], r12d
0x180028870  mov     r9d, r14d
0x180028873  mov     [rsp+60h+var_30], r12
0x180028878  mov     rdx, r15
0x18002887b  mov     [rsp+60h+var_38], r12
0x180028880  mov     rcx, r13
0x180028883  mov     r8d, [rax]
0x180028886  shr     r8d, 1Ah
0x18002888a  and     r8d, 7
0x18002888e  mov     [rsp+60h+var_40], 0FFFFFFFFh
0x180028896  call    ?GetCcs@CTxtEdit@@QEAAPEAVCCcs@@QEBVCCharFormat@@W4FONTALIGNMENT@@JKPEAVCHDC@@PEBGJ@Z; CTxtEdit::GetCcs(CCharFormat const * const,FONTALIGNMENT,long,ulong,CHDC *,ushort const *,long)
0x18002889b  mov     rbx, rax
0x18002889e  test    rax, rax
0x1800288a1  jz      loc_180028955
0x1800288a7  xor     r11d, r11d
0x1800288aa  cmp     [r15+0Ah], r11w
0x1800288af  jnz     loc_180028B4D
0x1800288b5  movsx   rcx, byte ptr [r15+3Eh]
0x1800288ba  mov     r13, 0FFFFFFFFFFFFFFCEh
0x1800288c1  mov     r8, 0A3D70A3D70A3D70Bh
0x1800288cb  mov     r10d, 80000000h
0x1800288d1  lea     r9d, [r13+64h]
0x1800288d5  test    cl, cl
0x1800288d7  jnz     loc_180028AEB
0x1800288dd  test    dword ptr [r15], 20000h
0x1800288e4  jnz     loc_180028B68
0x1800288ea  test    dword ptr [r15], 10000h
0x1800288f1  mov     r14d, r11d
0x1800288f4  jnz     loc_180028B70
0x1800288fa  mov     rcx, [rsi+88h]; this
0x180028901  call    ?FAdjustFELineHt@CDisplay@@QEBAHXZ; CDisplay::FAdjustFELineHt(void)
0x180028906  xor     r15d, r15d
0x180028909  test    eax, eax
0x18002890b  jz      short loc_18002891A
0x18002890d  test    byte ptr [rbx+169h], 10h
0x180028914  jnz     loc_180028A5F
0x18002891a  mov     esi, r15d
0x18002891d  mov     rdi, [rbp+arg_8]
0x180028921  test    rdi, rdi
0x180028924  jz      short loc_18002893E
0x180028926  movsx   edx, word ptr [rbx+14h]; int
0x18002892a  mov     rcx, rbx; this
0x18002892d  call    ?ScaleMetric@CCcs@@QEBAJJ@Z; CCcs::ScaleMetric(long)
0x180028932  mov     ecx, esi
0x180028934  sub     ecx, r14d
0x180028937  sub     ecx, r12d
0x18002893a  add     eax, ecx
0x18002893c  mov     [rdi], eax
0x18002893e  movsx   edx, word ptr [rbx+12h]; int
0x180028942  mov     rcx, rbx; this
0x180028945  call    ?ScaleMetric@CCcs@@QEBAJJ@Z; CCcs::ScaleMetric(long)
0x18002894a  mov     rcx, rbx; this
0x18002894d  lea     edi, [rax+rsi*2]
0x180028950  call    ?Release@CCcs@@QEAAXXZ; CCcs::Release(void)
0x180028955  dec     cs:?g_cFCLock@@3JA; long g_cFCLock
0x18002895b  lea     rcx, [rbp+arg_0]; this
0x18002895f  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180028964  mov     rbx, [rsp+60h+arg_18]
0x18002896c  mov     eax, edi
0x18002896e  add     rsp, 60h
0x180028972  pop     r15
0x180028974  pop     r14
0x180028976  pop     r13
0x180028978  pop     r12
0x18002897a  pop     rdi
0x18002897b  pop     rsi
0x18002897c  pop     rbp
0x18002897d  retn
0x18002897e  mov     r15, [rbp+arg_10]
0x180028982  jmp     loc_1800287E1
0x180028987  xor     ecx, ecx
0x180028989  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002898e  mov     rcx, rax; SRWLock
0x180028991  call    cs:__imp_AcquireSRWLockExclusive
0x180028997  call    cs:__imp_GetCurrentThreadId
0x18002899d  xor     ecx, ecx
0x18002899f  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800289a5  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x1800289aa  inc     dword ptr [rax+4]
0x1800289ad  jmp     loc_18002878B
0x1800289b2  mov     rcx, r13; this
0x1800289b5  call    ?TxGetDC@CTxtEdit@@QEAAPEAUHDC__@@XZ; CTxtEdit::TxGetDC(void)
0x1800289ba  mov     rdx, [r13+238h]; struct IDpiAccessor *
0x1800289c1  xor     r9d, r9d; struct ITextRenderTarget *
0x1800289c4  mov     r8, rax; HDC
0x1800289c7  mov     cl, bl; bool
0x1800289c9  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x1800289ce  mov     [rbp+var_20], rax
0x1800289d2  mov     rdx, rax
0x1800289d5  mov     [rbp+var_18], r12b
0x1800289d9  mov     [rbp+var_14], r12
0x1800289dd  mov     [rbp+var_C], r12b
0x1800289e1  mov     rcx, [rax]
0x1800289e4  mov     rax, [rcx+18h]
0x1800289e8  mov     rcx, rdx
0x1800289eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f0  test    al, al
0x1800289f2  jz      loc_180028AC7
0x1800289f8  cmp     [rbp+var_18], r12b
0x1800289fc  jnz     loc_180028AD8
0x180028a02  cmp     [rbp+var_C], r12b
0x180028a06  jnz     loc_180028B40
0x180028a0c  mov     rcx, [rbp+var_20]
0x180028a10  mov     rax, [rcx]
0x180028a13  mov     rax, [rax+68h]
0x180028a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a1c  mov     r14d, eax
0x180028a1f  mov     rcx, [rbp+var_20]
0x180028a23  mov     rax, [rcx]
0x180028a26  mov     rax, [rax+30h]
0x180028a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a2f  cmp     [r13+70h], r12
0x180028a33  lea     rcx, ?s_dummyHost@CITextHost2Ref@@0VCDummyHost@@A; CDummyHost CITextHost2Ref::s_dummyHost
0x180028a3a  mov     r8, rax
0x180028a3d  cmovnz  rcx, [r13+70h]
0x180028a42  mov     rdx, [rcx]
0x180028a45  mov     rax, [rdx+20h]
0x180028a49  mov     rdx, r8
0x180028a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a51  lea     rcx, [rbp+var_20]; this
0x180028a55  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x180028a5a  jmp     loc_180028832
0x180028a5f  movsx   edx, word ptr [rbx+12h]; int
0x180028a63  mov     rcx, rbx; this
0x180028a66  call    ?ScaleMetric@CCcs@@QEBAJJ@Z; CCcs::ScaleMetric(long)
0x180028a6b  movsxd  rcx, eax
0x180028a6e  mov     eax, 32h ; '2'
0x180028a73  imul    rdx, rcx, 0Fh
0x180028a77  mov     rcx, rdx
0x180028a7a  shr     rcx, 3Fh
0x180028a7e  xor     ecx, 1
0x180028a81  cmp     ecx, 1
0x180028a84  mov     ecx, 0FFFFFFFFh
0x180028a89  cmovz   r13, rax
0x180028a8d  mov     rax, 0A3D70A3D70A3D70Bh
0x180028a97  add     r13, rdx
0x180028a9a  imul    r13
0x180028a9d  lea     rsi, [rdx+r13]
0x180028aa1  sar     rsi, 6
0x180028aa5  mov     rax, rsi
0x180028aa8  shr     rax, 3Fh
0x180028aac  add     rsi, rax
0x180028aaf  mov     eax, 80000000h
0x180028ab4  add     rax, rsi
0x180028ab7  cmp     rax, rcx
0x180028aba  jbe     loc_18002891D
0x180028ac0  mov     esi, edi
0x180028ac2  jmp     loc_18002891D
0x180028ac7  lea     rcx, [rbp+var_20]; this
0x180028acb  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x180028ad0  or      edi, 0FFFFFFFFh
0x180028ad3  jmp     loc_180028955
0x180028ad8  mov     r14d, 0DF3E0h
0x180028ade  jmp     loc_180028A1F
0x180028ae3  mov     r13, r12
0x180028ae6  jmp     loc_1800287A2
0x180028aeb  movsx   rdx, word ptr [rbx+12h]
0x180028af0  imul    rdx, rcx
0x180028af4  mov     rcx, r13
0x180028af7  mov     rax, rdx
0x180028afa  shr     rax, 3Fh
0x180028afe  xor     eax, 1
0x180028b01  cmp     eax, 1
0x180028b04  mov     rax, r8
0x180028b07  cmovz   rcx, r9
0x180028b0b  add     rcx, rdx
0x180028b0e  imul    rcx
0x180028b11  add     rdx, rcx
0x180028b14  mov     ecx, 0FFFFFFFFh
0x180028b19  sar     rdx, 6
0x180028b1d  mov     rax, rdx
0x180028b20  shr     rax, 3Fh
0x180028b24  add     rdx, rax; int
0x180028b27  lea     rax, [rdx+r10]
0x180028b2b  cmp     rax, rcx
0x180028b2e  ja      short loc_180028B49
0x180028b30  mov     rcx, rbx; this
0x180028b33  call    ?ScaleMetric@CCcs@@QEBAJJ@Z; CCcs::ScaleMetric(long)
0x180028b38  mov     r14d, eax
0x180028b3b  jmp     loc_1800288FA
0x180028b40  mov     r14d, dword ptr [rbp+var_14+4]
0x180028b44  jmp     loc_180028A1F
0x180028b49  mov     edx, edi
0x180028b4b  jmp     short loc_180028B30
0x180028b4d  movsx   ecx, word ptr [r15+0Ah]; int
0x180028b52  mov     r8d, 5A0h; int
0x180028b58  mov     edx, r14d; int
0x180028b5b  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180028b60  mov     r12d, eax
0x180028b63  jmp     loc_1800288B5
0x180028b68  movsx   ecx, word ptr [rbx+12h]
0x180028b6c  add     ecx, ecx
0x180028b6e  jmp     short loc_180028B7D
0x180028b70  movsx   ecx, word ptr [rbx+16h]
0x180028b74  movsx   eax, word ptr [rbx+12h]
0x180028b78  sub     ecx, eax
0x180028b7a  lea     ecx, [rcx+rcx*2]
0x180028b7d  mov     eax, 66666667h
0x180028b82  imul    ecx
0x180028b84  sar     edx, 1
0x180028b86  mov     eax, edx
0x180028b88  shr     eax, 1Fh
0x180028b8b  add     edx, eax
0x180028b8d  jmp     short loc_180028B30
```
