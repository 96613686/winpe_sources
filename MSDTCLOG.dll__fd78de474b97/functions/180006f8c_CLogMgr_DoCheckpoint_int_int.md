# CLogMgr::_DoCheckpoint(int,int)

- ea: `0x180006f8c`
- end: `0x1800073ab`
- name: `?_DoCheckpoint@CLogMgr@@AEAAXHH@Z`
- size: `1055`
- prototype: `void __fastcall(CLogMgr *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x1800044c8`
- `0x180005ff0`
- `0x180006328`
- `0x18000699c`

## callees

- `0x180006f8c`
- `0x1800073b4`
- `0x180008768`
- `0x18000955c`
- `0x18000a1a8`
- `0x18001266c`
- `0x18001280a`
- `0x180015010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CLogMgr::_DoCheckpoint(CLogMgr *this, int a2, int a3)
{
  char *v6; // r14
  _DWORD *v7; // r8
  __int64 v8; // r13
  unsigned int v9; // eax
  unsigned int v10; // r9d
  __int64 v11; // rbx
  unsigned int v12; // esi
  unsigned int v13; // esi
  unsigned int v14; // r12d
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-E8h] BYREF
  int v19; // [rsp+28h] [rbp-E0h]
  int v20; // [rsp+2Ch] [rbp-DCh]
  ulong pExceptionObject; // [rsp+30h] [rbp-D8h] BYREF
  ulong v22; // [rsp+34h] [rbp-D4h] BYREF
  int v23; // [rsp+38h] [rbp-D0h] BYREF
  ulong v24; // [rsp+3Ch] [rbp-CCh] BYREF
  ulong v25; // [rsp+40h] [rbp-C8h] BYREF
  int v26; // [rsp+48h] [rbp-C0h]
  char *v27; // [rsp+50h] [rbp-B8h]
  __int128 v28; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-A0h]
  ulong v30; // [rsp+70h] [rbp-98h] BYREF
  ulong v31; // [rsp+74h] [rbp-94h] BYREF
  char v32[8]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-80h]
  unsigned int v34; // [rsp+110h] [rbp+8h] BYREF
  __int64 v35; // [rsp+128h] [rbp+20h]

  memset_0(v32, 0, 0x54u);
  v28 = 0;
  v29 = 0;
  v26 = 1;
  v6 = (char *)this + 408;
  v27 = (char *)this + 408;
  (**((void (__fastcall ***)(char *))this + 51))((char *)this + 408);
  v7 = (_DWORD *)*((_QWORD *)this + 50);
  v8 = 0;
  if ( v7[34] )
  {
    if ( !a3 )
    {
      pExceptionObject = -1073737699;
      throw &pExceptionObject;
    }
  }
  else
  {
    v9 = 0;
    v10 = v7[29];
    if ( v10 < 0x84 )
      v9 = 8160 * ((132 - v10) / 0x1FE0 + 1);
    if ( v10 + v9 + 8028 > v7[4] )
    {
      v7[34] = 1;
      v22 = -1073737699;
      throw &v22;
    }
  }
  LODWORD(v29) = -1;
  HIDWORD(v28) = 196608;
  CLogMgr::_WriteChkPt(this, (struct _LOGRECHEADER *)&v28, 0, 0);
  v18 = *((_QWORD *)this + 50) + 24LL;
  v19 = 84;
  v20 = 393216;
  HIWORD(v28) = 6;
  CLogMgr::_WriteChkPt(this, (struct _LOGRECHEADER *)&v28, (struct _LOGREC *)&v18, 0x54u);
  if ( *(_WORD *)(*((_QWORD *)this + 50) + 88LL) )
  {
    v11 = *((_QWORD *)this + 37);
    v12 = 0;
    do
    {
      v18 = v11;
      v19 = 44;
      v20 = 327680;
      HIWORD(v28) = 5;
      CLogMgr::_WriteChkPt(this, (struct _LOGRECHEADER *)&v28, (struct _LOGREC *)&v18, 0x2Cu);
      v11 += 44;
      ++v12;
    }
    while ( v12 < *(unsigned __int16 *)(*((_QWORD *)this + 50) + 88LL) );
    v6 = (char *)this + 408;
  }
  HIWORD(v28) = 4;
  CLogMgr::_WriteChkPt(this, (struct _LOGRECHEADER *)&v28, 0, 0);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  CLogMgr::_Flush(this, 0, 0, a2);
  v26 = 1;
  v27 = v6;
  (**(void (__fastcall ***)(char *))v6)(v6);
  CLogState::GetRestartArea(*((CLogState **)this + 50), (struct _RESTARTLOG *)v32, &v34, 0);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( !*((_DWORD *)this + 95) )
  {
    if ( !*((_QWORD *)this + 46) )
    {
      v23 = -2147418113;
      throw (long *)&v23;
    }
    v13 = 1;
    v34 = 1;
    v14 = 0;
    v35 = v33;
    while ( v13 )
    {
      v15 = 0;
      v26 = 1;
      v27 = (char *)this + 304;
      (**((void (__fastcall ***)(char *))this + 38))((char *)this + 304);
      v16 = *(_QWORD *)(*((_QWORD *)this + 46) + 16LL * v14);
      if ( v16
        && (*(unsigned int (__fastcall **)(char *, __int64, __int64))(*((_QWORD *)this + 18) + 24LL))(
             (char *)this + 144,
             v16,
             v35) != 2 )
      {
        v17 = *((_QWORD *)this + 46);
        if ( *(_QWORD *)(v17 + 16LL * v14 + 8) )
        {
          v8 = *(_QWORD *)(v17 + 16LL * v14 + 8);
          v15 = *(_QWORD *)(v17 + 16LL * v14);
        }
        *(_QWORD *)(v17 + 16LL * v14 + 8) = 0;
        *(_QWORD *)(*((_QWORD *)this + 46) + 16LL * v14) = 0;
        --*((_DWORD *)this + 90);
      }
      if ( v14 == *((_DWORD *)this + 94) )
      {
        v13 = 0;
        v34 = 0;
        if ( !*((_DWORD *)this + 90) )
        {
          *((_DWORD *)this + 94) = 0;
          *((_DWORD *)this + 95) = 1;
        }
      }
      else
      {
        ++v14;
        v13 = v34;
      }
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 38) + 8LL))((char *)this + 304);
      if ( v8 )
      {
        try
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v8 + 16LL))(v8, 0, v15);
        }
        catch ( long v30 )
        {
          v24 = v30;
          throw &v24;
        }
        catch ( ulong v31 )
        {
          v25 = v31;
          throw &v25;
        }
      }
      v8 = 0;
    }
  }
  v26 = 1;
  v27 = v6;
  (**(void (__fastcall ***)(char *))v6)(v6);
  CLogStorage::ForceRestart(*((CLogStorage **)this + 49), (struct _RESTARTLOG *)v32, *((struct _STRMTBL **)this + 37));
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
}

```

## disassembly

```asm
0x180006f8c  mov     [rsp+arg_8], rbx
0x180006f91  mov     [rsp+arg_10], rsi
0x180006f96  push    rdi
0x180006f97  push    r12
0x180006f99  push    r13
0x180006f9b  push    r14
0x180006f9d  push    r15
0x180006f9f  sub     rsp, 0E0h
0x180006fa6  mov     ebx, r8d
0x180006fa9  mov     r15d, edx
0x180006fac  mov     rdi, rcx
0x180006faf  mov     esi, 54h ; 'T'
0x180006fb4  mov     r8d, esi; Size
0x180006fb7  xor     edx, edx; Val
0x180006fb9  lea     rcx, [rsp+108h+var_88]; void *
0x180006fc1  call    memset_0
0x180006fc6  xorps   xmm0, xmm0
0x180006fc9  xor     eax, eax
0x180006fcb  movups  [rsp+108h+var_B0], xmm0
0x180006fd0  mov     [rsp+108h+var_A0], rax
0x180006fd5  lea     r12d, [rsi-53h]
0x180006fd9  mov     [rsp+108h+var_C0], r12d
0x180006fde  lea     r14, [rdi+198h]
0x180006fe5  mov     [rsp+108h+var_B8], r14
0x180006fea  mov     rax, [r14]
0x180006fed  mov     rcx, r14
0x180006ff0  mov     rax, [rax]
0x180006ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff8  nop
0x180006ff9  mov     r8, [rdi+190h]
0x180007000  xor     r13d, r13d
0x180007003  cmp     [r8+88h], r13d
0x18000700a  jz      short loc_180007016
0x18000700c  test    ebx, ebx
0x18000700e  jz      loc_180007356
0x180007014  jmp     short loc_18000704F
0x180007016  mov     eax, r13d
0x180007019  mov     r9d, [r8+74h]
0x18000701d  mov     ecx, 84h
0x180007022  cmp     r9d, ecx
0x180007025  jnb     short loc_18000703D
0x180007027  sub     ecx, r9d
0x18000702a  mov     eax, 80808081h
0x18000702f  mul     ecx
0x180007031  shr     edx, 0Ch
0x180007034  add     edx, r12d
0x180007037  imul    eax, edx, 1FE0h
0x18000703d  add     eax, 1F5Ch
0x180007042  add     eax, r9d
0x180007045  cmp     eax, [r8+10h]
0x180007049  ja      loc_180007370
0x18000704f  mov     dword ptr [rsp+108h+var_A0], 0FFFFFFFFh
0x180007057  mov     dword ptr [rsp+108h+var_B0+0Ch], 30000h
0x18000705f  xor     r9d, r9d; unsigned int
0x180007062  xor     r8d, r8d; struct _LOGREC *
0x180007065  lea     rdx, [rsp+108h+var_B0]; struct _LOGRECHEADER *
0x18000706a  mov     rcx, rdi; this
0x18000706d  call    ?_WriteChkPt@CLogMgr@@AEAAKPEAU_LOGRECHEADER@@PEAU_LOGREC@@K@Z; CLogMgr::_WriteChkPt(_LOGRECHEADER *,_LOGREC *,ulong)
0x180007072  mov     rax, [rdi+190h]
0x180007079  add     rax, 18h
0x18000707d  mov     [rsp+108h+var_E8], rax
0x180007082  mov     [rsp+108h+var_E0], esi
0x180007086  mov     [rsp+108h+var_DC], 60000h
0x18000708e  mov     eax, 6
0x180007093  mov     word ptr [rsp+108h+var_B0+0Eh], ax
0x180007098  mov     r9d, esi; unsigned int
0x18000709b  lea     r8, [rsp+108h+var_E8]; struct _LOGREC *
0x1800070a0  lea     rdx, [rsp+108h+var_B0]; struct _LOGRECHEADER *
0x1800070a5  mov     rcx, rdi; this
0x1800070a8  call    ?_WriteChkPt@CLogMgr@@AEAAKPEAU_LOGRECHEADER@@PEAU_LOGREC@@K@Z; CLogMgr::_WriteChkPt(_LOGRECHEADER *,_LOGREC *,ulong)
0x1800070ad  mov     rax, [rdi+190h]
0x1800070b4  cmp     [rax+58h], r13w
0x1800070b9  jbe     short loc_18000711B
0x1800070bb  mov     rbx, [rdi+128h]
0x1800070c2  mov     esi, r13d
0x1800070c5  mov     r14d, 5
0x1800070cb  mov     [rsp+108h+var_E8], rbx
0x1800070d0  mov     [rsp+108h+var_E0], 2Ch ; ','
0x1800070d8  mov     [rsp+108h+var_DC], 50000h
0x1800070e0  mov     word ptr [rsp+108h+var_B0+0Eh], r14w
0x1800070e6  mov     r9d, 2Ch ; ','; unsigned int
0x1800070ec  lea     r8, [rsp+108h+var_E8]; struct _LOGREC *
0x1800070f1  lea     rdx, [rsp+108h+var_B0]; struct _LOGRECHEADER *
0x1800070f6  mov     rcx, rdi; this
0x1800070f9  call    ?_WriteChkPt@CLogMgr@@AEAAKPEAU_LOGRECHEADER@@PEAU_LOGREC@@K@Z; CLogMgr::_WriteChkPt(_LOGRECHEADER *,_LOGREC *,ulong)
0x1800070fe  add     rbx, 2Ch ; ','
0x180007102  add     esi, r12d
0x180007105  mov     rax, [rdi+190h]
0x18000710c  movzx   ecx, word ptr [rax+58h]
0x180007110  cmp     esi, ecx
0x180007112  jb      short loc_1800070CB
0x180007114  lea     r14, [rdi+198h]
0x18000711b  mov     eax, 4
0x180007120  mov     word ptr [rsp+108h+var_B0+0Eh], ax
0x180007125  xor     r9d, r9d; unsigned int
0x180007128  xor     r8d, r8d; struct _LOGREC *
0x18000712b  lea     rdx, [rsp+108h+var_B0]; struct _LOGRECHEADER *
0x180007130  mov     rcx, rdi; this
0x180007133  call    ?_WriteChkPt@CLogMgr@@AEAAKPEAU_LOGRECHEADER@@PEAU_LOGREC@@K@Z; CLogMgr::_WriteChkPt(_LOGRECHEADER *,_LOGREC *,ulong)
0x180007138  nop
0x180007139  mov     rax, [r14]
0x18000713c  mov     rcx, r14
0x18000713f  mov     rax, [rax+8]
0x180007143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007148  nop
0x180007149  mov     r9d, r15d; int
0x18000714c  xor     r8d, r8d; unsigned int
0x18000714f  xor     edx, edx; unsigned int
0x180007151  mov     rcx, rdi; this
0x180007154  call    ?_Flush@CLogMgr@@QEAAXKKH@Z; CLogMgr::_Flush(ulong,ulong,int)
0x180007159  mov     [rsp+108h+var_C0], r12d
0x18000715e  mov     [rsp+108h+var_B8], r14
0x180007163  mov     rax, [r14]
0x180007166  mov     rcx, r14
0x180007169  mov     rax, [rax]
0x18000716c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007171  nop
0x180007172  xor     r9d, r9d; int
0x180007175  lea     r8, [rsp+108h+arg_0]; unsigned int *
0x18000717d  lea     rdx, [rsp+108h+var_88]; struct _RESTARTLOG *
0x180007185  mov     rcx, [rdi+190h]; this
0x18000718c  call    ?GetRestartArea@CLogState@@QEAAXPEAU_RESTARTLOG@@PEAKH@Z; CLogState::GetRestartArea(_RESTARTLOG *,ulong *,int)
0x180007191  nop
0x180007192  mov     rax, [r14]
0x180007195  mov     rcx, r14
0x180007198  mov     rax, [rax+8]
0x18000719c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a1  nop
0x1800071a2  cmp     [rdi+17Ch], r13d
0x1800071a9  jnz     loc_1800072F4
0x1800071af  cmp     [rdi+170h], r13
0x1800071b6  jz      loc_180007391
0x1800071bc  mov     esi, r12d
0x1800071bf  mov     [rsp+108h+arg_0], r12d
0x1800071c7  mov     r12d, r13d
0x1800071ca  mov     eax, dword ptr [rsp+108h+var_80+4]
0x1800071d1  mov     dword ptr [rsp+108h+arg_18+4], eax
0x1800071d8  mov     eax, dword ptr [rsp+108h+var_80]
0x1800071df  mov     dword ptr [rsp+108h+arg_18], eax
0x1800071e6  jmp     short loc_1800071EB
0x1800071e8  xor     r13d, r13d
0x1800071eb  test    esi, esi
0x1800071ed  jz      loc_1800072EE
0x1800071f3  xor     ebx, ebx
0x1800071f5  mov     [rsp+108h+var_C0], 1
0x1800071fd  lea     r15, [rdi+130h]
0x180007204  mov     [rsp+108h+var_B8], r15
0x180007209  mov     rax, [r15]
0x18000720c  mov     rcx, r15
0x18000720f  mov     rax, [rax]
0x180007212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007217  nop
0x180007218  mov     esi, r12d
0x18000721b  add     rsi, rsi
0x18000721e  mov     rax, [rdi+170h]
0x180007225  mov     rdx, [rax+rsi*8]
0x180007229  test    rdx, rdx
0x18000722c  jz      short loc_180007284
0x18000722e  lea     rcx, [rdi+90h]
0x180007235  mov     rax, [rcx]
0x180007238  mov     r8, [rsp+108h+arg_18]
0x180007240  mov     rax, [rax+18h]
0x180007244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007249  cmp     eax, 2
0x18000724c  jz      short loc_180007284
0x18000724e  mov     rax, [rdi+170h]
0x180007255  mov     rcx, [rax+rsi*8+8]
0x18000725a  test    rcx, rcx
0x18000725d  jz      short loc_180007266
0x18000725f  mov     r13, rcx
0x180007262  mov     rbx, [rax+rsi*8]
0x180007266  mov     qword ptr [rax+rsi*8+8], 0
0x18000726f  mov     rax, [rdi+170h]
0x180007276  mov     qword ptr [rax+rsi*8], 0
0x18000727e  dec     dword ptr [rdi+168h]
0x180007284  cmp     r12d, [rdi+178h]
0x18000728b  jnz     short loc_1800072B0
0x18000728d  xor     esi, esi
0x18000728f  mov     [rsp+108h+arg_0], esi
0x180007296  cmp     [rdi+168h], esi
0x18000729c  jnz     short loc_1800072BA
0x18000729e  mov     [rdi+178h], esi
0x1800072a4  mov     dword ptr [rdi+17Ch], 1
0x1800072ae  jmp     short loc_1800072BA
0x1800072b0  inc     r12d
0x1800072b3  mov     esi, [rsp+108h+arg_0]
0x1800072ba  mov     rax, [r15]
0x1800072bd  mov     rcx, r15
0x1800072c0  mov     rax, [rax+8]
0x1800072c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072c9  nop
0x1800072ca  test    r13, r13
0x1800072cd  jz      loc_1800071E8
0x1800072d3  mov     rax, [r13+0]
0x1800072d7  mov     r8, rbx
0x1800072da  xor     edx, edx
0x1800072dc  mov     rcx, r13
0x1800072df  mov     rax, [rax+10h]
0x1800072e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e8  nop
0x1800072e9  jmp     loc_1800071E8
0x1800072ee  mov     r12d, 1
0x1800072f4  mov     [rsp+108h+var_C0], r12d
0x1800072f9  mov     [rsp+108h+var_B8], r14
0x1800072fe  mov     rax, [r14]
0x180007301  mov     rcx, r14
0x180007304  mov     rax, [rax]
0x180007307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730c  nop
0x18000730d  mov     r8, [rdi+128h]; struct _STRMTBL *
0x180007314  lea     rdx, [rsp+108h+var_88]; struct _RESTARTLOG *
0x18000731c  mov     rcx, [rdi+188h]; this
0x180007323  call    ?ForceRestart@CLogStorage@@QEAAXPEAU_RESTARTLOG@@PEAU_STRMTBL@@@Z; CLogStorage::ForceRestart(_RESTARTLOG *,_STRMTBL *)
0x180007328  nop
0x180007329  mov     rax, [r14]
0x18000732c  mov     rcx, r14
0x18000732f  mov     rax, [rax+8]
0x180007333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007338  nop
0x180007339  lea     r11, [rsp+108h+var_28]
0x180007341  mov     rbx, [r11+38h]
0x180007345  mov     rsi, [r11+40h]
0x180007349  mov     rsp, r11
0x18000734c  pop     r15
0x18000734e  pop     r14
0x180007350  pop     r13
0x180007352  pop     r12
0x180007354  pop     rdi
0x180007355  retn
0x180007356  mov     [rsp+108h+pExceptionObject], 0C000101Dh
0x18000735e  lea     rdx, _TI1K; pThrowInfo
0x180007365  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18000736a  call    _CxxThrowException_0
0x180007370  mov     [r8+88h], r12d
0x180007377  mov     [rsp+108h+var_D4], 0C000101Dh
0x18000737f  lea     rdx, _TI1K; pThrowInfo
0x180007386  lea     rcx, [rsp+108h+var_D4]; pExceptionObject
0x18000738b  call    _CxxThrowException_0
0x180007391  mov     [rsp+108h+var_D0], 8000FFFFh
0x180007399  lea     rdx, _TI1J; pThrowInfo
0x1800073a0  lea     rcx, [rsp+108h+var_D0]; pExceptionObject
0x1800073a5  call    _CxxThrowException_0
```
