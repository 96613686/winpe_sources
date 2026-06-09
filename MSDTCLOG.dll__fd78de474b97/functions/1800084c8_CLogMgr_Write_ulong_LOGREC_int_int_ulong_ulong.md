# CLogMgr::_Write(ulong,_LOGREC *,int,int,ulong *,ulong)

- ea: `0x1800084c8`
- end: `0x18000875f`
- name: `?_Write@CLogMgr@@AEAA?AT_ULARGE_INTEGER@@KPEAU_LOGREC@@HHPEAKK@Z`
- size: `663`
- prototype: `union _ULARGE_INTEGER(CLogMgr *__hidden this, unsigned int, struct _LOGREC *, int, int, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004d80`
- `0x1800052e0`

## callees

- `0x1800084c8`
- `0x180009298`
- `0x18000d3ec`
- `0x18000d620`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800086ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008726`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800086ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008726`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
union _ULARGE_INTEGER __fastcall CLogMgr::_Write(
        CLogMgr *this,
        _QWORD *a2,
        struct _LOGREC *a3,
        __int64 a4,
        int a5,
        unsigned int *a6,
        _DWORD *a7,
        unsigned int a8)
{
  char *v11; // rbx
  __int64 v12; // rcx
  unsigned int v13; // r9d
  int v14; // eax
  unsigned int v15; // r9d
  int v17; // eax
  ulong v18; // ebx
  ulong v19; // ebx
  int v20; // eax
  struct _WRITELISTELEMENT *v21; // [rsp+20h] [rbp-98h]
  int v22; // [rsp+20h] [rbp-98h]
  unsigned int v23; // [rsp+30h] [rbp-88h]
  int v24; // [rsp+50h] [rbp-68h] BYREF
  ulong v25; // [rsp+54h] [rbp-64h] BYREF
  ulong v26; // [rsp+58h] [rbp-60h] BYREF
  ulong v27; // [rsp+5Ch] [rbp-5Ch] BYREF
  ulong v28; // [rsp+60h] [rbp-58h] BYREF
  ulong v29; // [rsp+64h] [rbp-54h] BYREF
  __int128 v30; // [rsp+68h] [rbp-50h] BYREF
  __int64 v31; // [rsp+78h] [rbp-40h]
  int v32; // [rsp+80h] [rbp-38h] BYREF
  ulong v33; // [rsp+84h] [rbp-34h] BYREF
  int v34; // [rsp+88h] [rbp-30h]
  char *v35; // [rsp+90h] [rbp-28h]
  unsigned int v37; // [rsp+D0h] [rbp+18h] BYREF

  v37 = (unsigned int)a3;
  *a2 = 0;
  v34 = 1;
  v11 = (char *)this + 408;
  v35 = (char *)this + 408;
  try
  {
    (**((void (***)(void))this + 51))();
    if ( *((_DWORD *)this + 3) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
    }
    else
    {
      v12 = *((_QWORD *)this + 50);
      *(_DWORD *)(v12 + 160) = *(_DWORD *)v12;
      *(_DWORD *)(v12 + 164) = *(_DWORD *)(v12 + 4);
      *(_DWORD *)(v12 + 168) = *(_DWORD *)(v12 + 8);
      *(_DWORD *)(v12 + 172) = *(_DWORD *)(v12 + 12);
      *(_DWORD *)(v12 + 176) = *(_DWORD *)(v12 + 16);
      *(_DWORD *)(v12 + 180) = *(_DWORD *)(v12 + 20);
      *(_OWORD *)(v12 + 184) = *(_OWORD *)(v12 + 24);
      *(_OWORD *)(v12 + 200) = *(_OWORD *)(v12 + 40);
      *(_OWORD *)(v12 + 216) = *(_OWORD *)(v12 + 56);
      *(_OWORD *)(v12 + 232) = *(_OWORD *)(v12 + 72);
      *(_OWORD *)(v12 + 248) = *(_OWORD *)(v12 + 88);
      *(_DWORD *)(v12 + 264) = *(_DWORD *)(v12 + 104);
      *(_DWORD *)(v12 + 268) = *(_DWORD *)(v12 + 108);
      *(_DWORD *)(v12 + 272) = *(_DWORD *)(v12 + 112);
      *(_DWORD *)(v12 + 276) = *(_DWORD *)(v12 + 116);
      *(_DWORD *)(v12 + 280) = *(_DWORD *)(v12 + 120);
      *(_DWORD *)(v12 + 284) = *(_DWORD *)(v12 + 124);
      *(_DWORD *)(v12 + 288) = *(_DWORD *)(v12 + 128);
      *(_DWORD *)(v12 + 292) = *(_DWORD *)(v12 + 132);
      *(_DWORD *)(v12 + 296) = *(_DWORD *)(v12 + 136);
      *(_DWORD *)(v12 + 300) = *(_DWORD *)(v12 + 140);
      *(_DWORD *)(v12 + 304) = *(_DWORD *)(v12 + 144);
      v37 = 0;
      CWriteMap::Init(*((CWriteMap **)this + 78), *((struct CLogStorage **)this + 49), 1u, (struct _LOGREC *)a4, v21);
      v30 = 0;
      v31 = a8;
      HIDWORD(v30) = *(_DWORD *)(a4 + 12);
      try
      {
        v14 = CLogState::AttemptWrite(
                *((CLogState **)this + 50),
                (struct _LOGRECHEADER *)&v30,
                *((struct CWriteMap **)this + 78),
                v13,
                v22,
                0,
                v23,
                (union _ULARGE_INTEGER *)this + 77,
                &v37);
        *a2 = *((_QWORD *)this + 77);
        if ( a7 )
          *a7 = v14;
        CWriteMap::CopyRecord(*((CWriteMap **)this + 78), (struct _LOGRECHEADER *)&v30, 0, v15);
      }
      catch ( long v32 )
      {
        CLogState::_RestoreLogState(*((CLogState **)this + 50));
        v24 = v32;
        throw (long *)&v24;
      }
      catch ( ulong v33 )
      {
        CLogState::_RestoreLogState(*((CLogState **)this + 50));
        v25 = v33;
        throw &v25;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
      if ( a5 )
      {
        SetEvent(*((HANDLE *)this + 68));
      }
      else
      {
        v34 = 1;
        v35 = v11;
        (**(void (__fastcall ***)(char *))v11)(v11);
        if ( *((_DWORD *)this + 162) )
          SetEvent(*((HANDLE *)this + 71));
        else
          *((_DWORD *)this + 144) = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  catch ( long v26 )
  {
    v17 = -2147467259;
    v18 = v26;
    if ( !*((_QWORD *)this + 3)
      || v26 != -1073737699 && (!*((_QWORD *)this + 3) || v26 != -1073737670)
      || (v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 3) + 24LL))(
                  *((_QWORD *)this + 3),
                  4097,
                  4),
          v17 < 0) )
    {
      TraceFile(v17, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 1356);
    }
    v27 = v18;
    throw &v27;
  }
  catch ( ulong v28 )
  {
    v19 = v28;
    if ( *((_QWORD *)this + 3) && (v28 == -1073737699 || *((_QWORD *)this + 3) && v28 == -1073737670) )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 3) + 24LL))(
              *((_QWORD *)this + 3),
              4097,
              4);
      if ( v20 < 0 )
        TraceFile(v20, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 1386);
    }
    v29 = v19;
    throw &v29;
  }
  return (union _ULARGE_INTEGER)a2;
}

```

## disassembly

```asm
0x1800084c8  mov     rax, rsp
0x1800084cb  mov     [rax+10h], rbx
0x1800084cf  mov     [rax+18h], r8d
0x1800084d3  mov     [rax+8], rcx
0x1800084d7  push    rsi
0x1800084d8  push    rdi
0x1800084d9  push    r14
0x1800084db  sub     rsp, 0A0h
0x1800084e2  mov     r14, r9
0x1800084e5  mov     rsi, rdx
0x1800084e8  mov     rdi, rcx
0x1800084eb  mov     qword ptr [rdx], 0
0x1800084f2  mov     dword ptr [rax-30h], 1
0x1800084f9  lea     rbx, [rcx+198h]
0x180008500  mov     [rax-28h], rbx
0x180008504  mov     rax, [rbx]
0x180008507  mov     rcx, rbx
0x18000850a  mov     rax, [rax]
0x18000850d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008512  nop
0x180008513  cmp     dword ptr [rdi+0Ch], 0
0x180008517  jz      short loc_18000852E
0x180008519  mov     rax, [rbx]
0x18000851c  mov     rcx, rbx
0x18000851f  mov     rax, [rax+8]
0x180008523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008528  nop
0x180008529  jmp     loc_180008748
0x18000852e  mov     rcx, [rdi+190h]
0x180008535  mov     eax, [rcx]
0x180008537  mov     [rcx+0A0h], eax
0x18000853d  mov     eax, [rcx+4]
0x180008540  mov     [rcx+0A4h], eax
0x180008546  mov     eax, [rcx+8]
0x180008549  mov     [rcx+0A8h], eax
0x18000854f  mov     eax, [rcx+0Ch]
0x180008552  mov     [rcx+0ACh], eax
0x180008558  mov     eax, [rcx+10h]
0x18000855b  mov     [rcx+0B0h], eax
0x180008561  mov     eax, [rcx+14h]
0x180008564  mov     [rcx+0B4h], eax
0x18000856a  movups  xmm0, xmmword ptr [rcx+18h]
0x18000856e  movups  xmmword ptr [rcx+0B8h], xmm0
0x180008575  movups  xmm1, xmmword ptr [rcx+28h]
0x180008579  movups  xmmword ptr [rcx+0C8h], xmm1
0x180008580  movups  xmm0, xmmword ptr [rcx+38h]
0x180008584  movups  xmmword ptr [rcx+0D8h], xmm0
0x18000858b  movups  xmm1, xmmword ptr [rcx+48h]
0x18000858f  movups  xmmword ptr [rcx+0E8h], xmm1
0x180008596  movups  xmm0, xmmword ptr [rcx+58h]
0x18000859a  movups  xmmword ptr [rcx+0F8h], xmm0
0x1800085a1  mov     eax, [rcx+68h]
0x1800085a4  mov     [rcx+108h], eax
0x1800085aa  mov     eax, [rcx+6Ch]
0x1800085ad  mov     [rcx+10Ch], eax
0x1800085b3  mov     eax, [rcx+70h]
0x1800085b6  mov     [rcx+110h], eax
0x1800085bc  mov     eax, [rcx+74h]
0x1800085bf  mov     [rcx+114h], eax
0x1800085c5  mov     eax, [rcx+78h]
0x1800085c8  mov     [rcx+118h], eax
0x1800085ce  mov     eax, [rcx+7Ch]
0x1800085d1  mov     [rcx+11Ch], eax
0x1800085d7  mov     eax, [rcx+80h]
0x1800085dd  mov     [rcx+120h], eax
0x1800085e3  mov     eax, [rcx+84h]
0x1800085e9  mov     [rcx+124h], eax
0x1800085ef  mov     eax, [rcx+88h]
0x1800085f5  mov     [rcx+128h], eax
0x1800085fb  mov     eax, [rcx+8Ch]
0x180008601  mov     [rcx+12Ch], eax
0x180008607  mov     eax, [rcx+90h]
0x18000860d  mov     [rcx+130h], eax
0x180008613  mov     [rsp+0B8h+arg_10], 0
0x18000861e  mov     r9, r14; struct _LOGREC *
0x180008621  mov     r8d, 1; unsigned int
0x180008627  mov     rdx, [rdi+188h]; struct CLogStorage *
0x18000862e  mov     rcx, [rdi+270h]; this
0x180008635  call    ?Init@CWriteMap@@QEAAXPEAVCLogStorage@@KPEAU_LOGREC@@PEAU_WRITELISTELEMENT@@@Z; CWriteMap::Init(CLogStorage *,ulong,_LOGREC *,_WRITELISTELEMENT *)
0x18000863a  xorps   xmm0, xmm0
0x18000863d  xor     eax, eax
0x18000863f  movups  [rsp+0B8h+var_50], xmm0
0x180008644  mov     [rsp+0B8h+var_40], rax
0x180008649  mov     eax, [rsp+0B8h+arg_38]
0x180008650  mov     dword ptr [rsp+0B8h+var_40], eax
0x180008654  movzx   eax, word ptr [r14+0Ch]
0x180008659  mov     word ptr [rsp+0B8h+var_50+0Ch], ax
0x18000865e  movzx   eax, word ptr [r14+0Eh]
0x180008663  mov     word ptr [rsp+0B8h+var_50+0Eh], ax
0x180008668  lea     r14, [rdi+268h]
0x18000866f  lea     rax, [rsp+0B8h+arg_10]
0x180008677  mov     [rsp+0B8h+var_78], rax; unsigned int *
0x18000867c  mov     [rsp+0B8h+var_80], r14; union _ULARGE_INTEGER *
0x180008681  mov     [rsp+0B8h+var_90], 0; unsigned int
0x180008689  mov     r8, [rdi+270h]; struct CWriteMap *
0x180008690  lea     rdx, [rsp+0B8h+var_50]; struct _LOGRECHEADER *
0x180008695  mov     rcx, [rdi+190h]; this
0x18000869c  call    ?AttemptWrite@CLogState@@QEAAKPEAU_LOGRECHEADER@@AEAVCWriteMap@@HHKKPEAT_ULARGE_INTEGER@@PEAK@Z; CLogState::AttemptWrite(_LOGRECHEADER *,CWriteMap &,int,int,ulong,ulong,_ULARGE_INTEGER *,ulong *)
0x1800086a1  mov     rcx, [r14]
0x1800086a4  mov     [rsi], rcx
0x1800086a7  mov     rcx, [rsp+0B8h+arg_30]
0x1800086af  test    rcx, rcx
0x1800086b2  jz      short loc_1800086B6
0x1800086b4  mov     [rcx], eax
0x1800086b6  xor     r8d, r8d; unsigned int
0x1800086b9  lea     rdx, [rsp+0B8h+var_50]; struct _LOGRECHEADER *
0x1800086be  mov     rcx, [rdi+270h]; this
0x1800086c5  call    ?CopyRecord@CWriteMap@@QEAAXAEAU_LOGRECHEADER@@K@Z; CWriteMap::CopyRecord(_LOGRECHEADER &,ulong)
0x1800086ca  nop
0x1800086cb  mov     rax, [rbx]
0x1800086ce  mov     rcx, rbx
0x1800086d1  mov     rax, [rax+8]
0x1800086d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086da  nop
0x1800086db  cmp     [rsp+0B8h+arg_20], 0
0x1800086e3  jz      short loc_1800086F4
0x1800086e5  mov     rcx, [rdi+220h]; hEvent
0x1800086ec  call    cs:__imp_SetEvent
0x1800086f2  jmp     short loc_180008748
0x1800086f4  mov     [rsp+0B8h+var_30], 1
0x1800086ff  mov     [rsp+0B8h+var_28], rbx
0x180008707  mov     rax, [rbx]
0x18000870a  mov     rcx, rbx
0x18000870d  mov     rax, [rax]
0x180008710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008715  nop
0x180008716  cmp     dword ptr [rdi+288h], 0
0x18000871d  jz      short loc_18000872E
0x18000871f  mov     rcx, [rdi+238h]; hEvent
0x180008726  call    cs:__imp_SetEvent
0x18000872c  jmp     short loc_180008738
0x18000872e  mov     dword ptr [rdi+240h], 0
0x180008738  mov     rax, [rbx]
0x18000873b  mov     rcx, rbx
0x18000873e  mov     rax, [rax+8]
0x180008742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008747  nop
0x180008748  mov     rax, rsi
0x18000874b  mov     rbx, [rsp+0B8h+arg_8]
0x180008753  add     rsp, 0A0h
0x18000875a  pop     r14
0x18000875c  pop     rdi
0x18000875d  pop     rsi
0x18000875e  retn
```
