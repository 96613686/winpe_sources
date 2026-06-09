# EquationManager::CreateEquation(GameInputForceFeedbackEffectKind,Equation * *)

- ea: `0x180013628`
- end: `0x180013bd0`
- name: `?CreateEquation@EquationManager@@AEAAJW4GameInputForceFeedbackEffectKind@@PEAPEAVEquation@@@Z`
- size: `1448`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001800c`

## callees

- `0x180001304`
- `0x18000ea00`
- `0x18000f514`
- `0x180013548`
- `0x180013628`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001368a`
- `ntdll!RtlAllocateHeap` at `0x1800136cb`
- `ntdll!RtlAllocateHeap` at `0x18001370c`
- `ntdll!RtlAllocateHeap` at `0x18001374d`
- `ntdll!RtlAllocateHeap` at `0x1800137fb`
- `ntdll!RtlAllocateHeap` at `0x1800138ab`
- `ntdll!RtlAllocateHeap` at `0x180013987`
- `ntdll!RtlAllocateHeap` at `0x1800139c8`
- `ntdll!RtlAllocateHeap` at `0x180013a09`
- `ntdll!RtlAllocateHeap` at `0x180013a47`
- `ntdll!RtlAllocateHeap` at `0x180013a89`
- `ntdll!RtlAllocateHeap` at `0x18001368a`
- `ntdll!RtlAllocateHeap` at `0x1800136cb`
- `ntdll!RtlAllocateHeap` at `0x18001370c`
- `ntdll!RtlAllocateHeap` at `0x18001374d`
- `ntdll!RtlAllocateHeap` at `0x1800137fb`
- `ntdll!RtlAllocateHeap` at `0x1800138ab`
- `ntdll!RtlAllocateHeap` at `0x180013987`
- `ntdll!RtlAllocateHeap` at `0x1800139c8`
- `ntdll!RtlAllocateHeap` at `0x180013a09`
- `ntdll!RtlAllocateHeap` at `0x180013a47`
- `ntdll!RtlAllocateHeap` at `0x180013a89`

## pseudocode

```c
__int64 __fastcall EquationManager::CreateEquation(
        const struct Equation::VendorParameters **a1,
        int a2,
        PeriodicEquation **a3,
        __int64 a4)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  PeriodicEquation *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  PeriodicEquation *v12; // rbx
  void **v13; // rcx
  PeriodicEquation *v14; // rax
  PeriodicEquation *v15; // rax
  char *v16; // rax
  _QWORD *v17; // rax
  char *v18; // rax
  _QWORD *v19; // rax
  PeriodicEquation *v20; // rax
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  ConditionEquation *v26; // rax
  ConditionEquation *v27; // rax
  ConditionEquation *v28; // rax
  ConditionEquation *v29; // rax
  PeriodicEquation *Heap; // rax
  int Equation; // esi
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34[2]; // [rsp+40h] [rbp-10h] BYREF
  int v35; // [rsp+78h] [rbp+28h] BYREF
  int v36; // [rsp+88h] [rbp+38h] BYREF

  if ( a2 > 5 )
  {
    v21 = a2 - 6;
    if ( !v21 )
    {
      Heap = (PeriodicEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
      v12 = Heap;
      if ( Heap )
      {
        PeriodicEquation::PeriodicEquation(Heap);
        v13 = &SawtoothDownEquation::`vftable';
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      v29 = (ConditionEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x98u);
      v12 = v29;
      if ( v29 )
      {
        ConditionEquation::ConditionEquation(v29);
        v13 = &SpringEquation::`vftable';
        *((_DWORD *)v12 + 36) = 0;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v28 = (ConditionEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x90u);
      v12 = v28;
      if ( v28 )
      {
        ConditionEquation::ConditionEquation(v28);
        v13 = &FrictionEquation::`vftable';
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v24 = v23 - 1;
    if ( !v24 )
    {
      v27 = (ConditionEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x90u);
      v12 = v27;
      if ( v27 )
      {
        ConditionEquation::ConditionEquation(v27);
        v13 = &DamperEquation::`vftable';
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    if ( v24 == 1 )
    {
      v26 = (ConditionEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x90u);
      v12 = v26;
      if ( v26 )
      {
        ConditionEquation::ConditionEquation(v26);
        v13 = &InertiaEquation::`vftable';
        goto LABEL_40;
      }
      goto LABEL_41;
    }
  }
  else
  {
    if ( a2 == 5 )
    {
      v20 = (PeriodicEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
      v12 = v20;
      if ( v20 )
      {
        PeriodicEquation::PeriodicEquation(v20);
        v13 = &SawtoothUpEquation::`vftable';
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    if ( !a2 )
    {
      v18 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x98u);
      v12 = (PeriodicEquation *)v18;
      if ( v18 )
      {
        v19 = v18 + 8;
        *v19 = v19;
        v19[1] = v19;
        v19[2] = v19;
        v19[3] = 0;
        *((_QWORD *)v12 + 9) = 0;
        *((_OWORD *)v12 + 7) = 0;
        *(_QWORD *)v12 = &ConstantEquation::`vftable';
        *((_OWORD *)v12 + 8) = 0;
        *((_QWORD *)v12 + 18) = 0;
        *((_QWORD *)v12 + 5) = 0;
        *((_QWORD *)v12 + 6) = 0;
        *((_DWORD *)v12 + 14) = 0;
        *((_QWORD *)v12 + 8) = -1;
        *((_QWORD *)v12 + 10) = 0;
        *((_DWORD *)v12 + 22) = 2;
        *((_QWORD *)v12 + 12) = 0;
        *((_QWORD *)v12 + 13) = 0;
        goto LABEL_42;
      }
      goto LABEL_41;
    }
    v6 = a2 - 1;
    if ( !v6 )
    {
      v16 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA0u);
      v12 = (PeriodicEquation *)v16;
      if ( v16 )
      {
        v17 = v16 + 8;
        *v17 = v17;
        v17[1] = v17;
        v17[2] = v17;
        v17[3] = 0;
        *((_QWORD *)v12 + 9) = 0;
        *((_OWORD *)v12 + 7) = 0;
        *(_QWORD *)v12 = &RampEquation::`vftable';
        *((_OWORD *)v12 + 8) = 0;
        *((_QWORD *)v12 + 5) = 0;
        *((_OWORD *)v12 + 9) = 0;
        *((_QWORD *)v12 + 6) = 0;
        *((_DWORD *)v12 + 14) = 0;
        *((_QWORD *)v12 + 8) = -1;
        *((_QWORD *)v12 + 10) = 0;
        *((_DWORD *)v12 + 22) = 2;
        *((_QWORD *)v12 + 12) = 0;
        *((_QWORD *)v12 + 13) = 0;
        goto LABEL_42;
      }
      goto LABEL_41;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      v15 = (PeriodicEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
      v12 = v15;
      if ( v15 )
      {
        PeriodicEquation::PeriodicEquation(v15);
        v13 = &SineEquation::`vftable';
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      v14 = (PeriodicEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
      v12 = v14;
      if ( v14 )
      {
        PeriodicEquation::PeriodicEquation(v14);
        v13 = &SquareEquation::`vftable';
        goto LABEL_40;
      }
LABEL_41:
      v12 = 0;
LABEL_42:
      if ( v12 )
      {
        Equation = Equation::CreateEquation(v12, (struct ApplicationMemory *)a1, a1[558]);
        if ( Equation >= 0 )
        {
          *a3 = v12;
          return 0;
        }
        else
        {
          if ( (unsigned int)dword_180069000 > 2
            && (qword_180069010 & 8) != 0
            && (qword_180069018 & 8) == qword_180069018 )
          {
            v35 = Equation;
            v34[0] = (__int64 *)"onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\EquationManager.cpp";
            v36 = 248;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              qword_180069010,
              (unsigned __int8 *)&word_18005C916,
              v32,
              v33,
              v34,
              (__int64)&v36,
              (__int64)&v35);
          }
          (**(void (__fastcall ***)(PeriodicEquation *, __int64))v12)(v12, 1);
          return (unsigned int)Equation;
        }
      }
      else
      {
        if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
        {
          v35 = -2147024882;
          v36 = 246;
          v34[0] = (__int64 *)"onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\EquationManager.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)v34,
            (unsigned __int8 *)byte_18005BE93,
            v10,
            v11,
            v34,
            (__int64)&v36,
            (__int64)&v35);
        }
        return 2147942414LL;
      }
    }
    if ( v8 == 1 )
    {
      v9 = (PeriodicEquation *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA8u);
      v12 = v9;
      if ( v9 )
      {
        PeriodicEquation::PeriodicEquation(v9);
        v13 = &TriangleEquation::`vftable';
LABEL_40:
        *(_QWORD *)v12 = v13;
        goto LABEL_42;
      }
      goto LABEL_41;
    }
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v35 = -2147024809;
    v34[0] = (__int64 *)"onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\EquationManager.cpp";
    v36 = 241;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)&dword_18005CB04,
      (__int64)a3,
      a4,
      v34,
      (__int64)&v36,
      (__int64)&v35);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180013628  mov     [rsp-18h+arg_0], rbx
0x18001362d  push    rbp
0x18001362e  push    rsi
0x18001362f  push    r14
0x180013631  mov     rbp, rsp
0x180013634  sub     rsp, 50h
0x180013638  mov     r14, r8
0x18001363b  mov     rsi, rcx
0x18001363e  cmp     edx, 5
0x180013641  jg      loc_1800138D7
0x180013647  jz      loc_180013896
0x18001364d  test    edx, edx
0x18001364f  jz      loc_1800137E6
0x180013655  sub     edx, 1
0x180013658  jz      loc_180013738
0x18001365e  sub     edx, 1
0x180013661  jz      loc_1800136F7
0x180013667  sub     edx, 1
0x18001366a  jz      short loc_1800136B6
0x18001366c  cmp     edx, 1
0x18001366f  jnz     loc_180013900
0x180013675  mov     rcx, gs:60h
0x18001367e  xor     edx, edx; Flags
0x180013680  mov     r8d, 0A8h; Size
0x180013686  mov     rcx, [rcx+30h]; HeapHandle
0x18001368a  call    cs:__imp_RtlAllocateHeap
0x180013691  nop     dword ptr [rax+rax+00h]
0x180013696  mov     rbx, rax
0x180013699  test    rax, rax
0x18001369c  jz      loc_180013AB1
0x1800136a2  mov     rcx, rax; this
0x1800136a5  call    ??0PeriodicEquation@@QEAA@XZ; PeriodicEquation::PeriodicEquation(void)
0x1800136aa  lea     rcx, ??_7TriangleEquation@@6B@; const TriangleEquation::`vftable'
0x1800136b1  jmp     loc_180013AAC
0x1800136b6  mov     rcx, gs:60h
0x1800136bf  xor     edx, edx; Flags
0x1800136c1  mov     r8d, 0A8h; Size
0x1800136c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800136cb  call    cs:__imp_RtlAllocateHeap
0x1800136d2  nop     dword ptr [rax+rax+00h]
0x1800136d7  mov     rbx, rax
0x1800136da  test    rax, rax
0x1800136dd  jz      loc_180013AB1
0x1800136e3  mov     rcx, rax; this
0x1800136e6  call    ??0PeriodicEquation@@QEAA@XZ; PeriodicEquation::PeriodicEquation(void)
0x1800136eb  lea     rcx, ??_7SquareEquation@@6B@; const SquareEquation::`vftable'
0x1800136f2  jmp     loc_180013AAC
0x1800136f7  mov     rcx, gs:60h
0x180013700  xor     edx, edx; Flags
0x180013702  mov     r8d, 0A8h; Size
0x180013708  mov     rcx, [rcx+30h]; HeapHandle
0x18001370c  call    cs:__imp_RtlAllocateHeap
0x180013713  nop     dword ptr [rax+rax+00h]
0x180013718  mov     rbx, rax
0x18001371b  test    rax, rax
0x18001371e  jz      loc_180013AB1
0x180013724  mov     rcx, rax; this
0x180013727  call    ??0PeriodicEquation@@QEAA@XZ; PeriodicEquation::PeriodicEquation(void)
0x18001372c  lea     rcx, ??_7SineEquation@@6B@; const SineEquation::`vftable'
0x180013733  jmp     loc_180013AAC
0x180013738  mov     rcx, gs:60h
0x180013741  xor     edx, edx; Flags
0x180013743  mov     r8d, 0A0h; Size
0x180013749  mov     rcx, [rcx+30h]; HeapHandle
0x18001374d  call    cs:__imp_RtlAllocateHeap
0x180013754  nop     dword ptr [rax+rax+00h]
0x180013759  mov     rbx, rax
0x18001375c  test    rax, rax
0x18001375f  jz      loc_180013AB1
0x180013765  add     rax, 8
0x180013769  xorps   xmm0, xmm0
0x18001376c  mov     [rax], rax
0x18001376f  mov     [rax+8], rax
0x180013773  mov     [rax+10h], rax
0x180013777  mov     qword ptr [rax+18h], 0
0x18001377f  lea     rax, ??_7RampEquation@@6B@; const RampEquation::`vftable'
0x180013786  mov     qword ptr [rbx+48h], 0
0x18001378e  movups  xmmword ptr [rbx+70h], xmm0
0x180013792  mov     [rbx], rax
0x180013795  movups  xmmword ptr [rbx+80h], xmm0
0x18001379c  mov     qword ptr [rbx+28h], 0
0x1800137a4  movups  xmmword ptr [rbx+90h], xmm0
0x1800137ab  mov     qword ptr [rbx+30h], 0
0x1800137b3  mov     dword ptr [rbx+38h], 0
0x1800137ba  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x1800137c2  mov     qword ptr [rbx+50h], 0
0x1800137ca  mov     dword ptr [rbx+58h], 2
0x1800137d1  mov     qword ptr [rbx+60h], 0
0x1800137d9  mov     qword ptr [rbx+68h], 0
0x1800137e1  jmp     loc_180013AB3
0x1800137e6  mov     rcx, gs:60h
0x1800137ef  xor     edx, edx; Flags
0x1800137f1  mov     r8d, 98h; Size
0x1800137f7  mov     rcx, [rcx+30h]; HeapHandle
0x1800137fb  call    cs:__imp_RtlAllocateHeap
0x180013802  nop     dword ptr [rax+rax+00h]
0x180013807  mov     rbx, rax
0x18001380a  test    rax, rax
0x18001380d  jz      loc_180013AB1
0x180013813  add     rax, 8
0x180013817  xorps   xmm0, xmm0
0x18001381a  mov     [rax], rax
0x18001381d  mov     [rax+8], rax
0x180013821  mov     [rax+10h], rax
0x180013825  mov     qword ptr [rax+18h], 0
0x18001382d  lea     rax, ??_7ConstantEquation@@6B@; const ConstantEquation::`vftable'
0x180013834  mov     qword ptr [rbx+48h], 0
0x18001383c  movups  xmmword ptr [rbx+70h], xmm0
0x180013840  mov     [rbx], rax
0x180013843  xor     eax, eax
0x180013845  movups  xmmword ptr [rbx+80h], xmm0
0x18001384c  mov     [rbx+90h], rax
0x180013853  mov     qword ptr [rbx+28h], 0
0x18001385b  mov     qword ptr [rbx+30h], 0
0x180013863  mov     dword ptr [rbx+38h], 0
0x18001386a  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180013872  mov     qword ptr [rbx+50h], 0
0x18001387a  mov     dword ptr [rbx+58h], 2
0x180013881  mov     qword ptr [rbx+60h], 0
0x180013889  mov     qword ptr [rbx+68h], 0
0x180013891  jmp     loc_180013AB3
0x180013896  mov     rcx, gs:60h
0x18001389f  xor     edx, edx; Flags
0x1800138a1  mov     r8d, 0A8h; Size
0x1800138a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800138ab  call    cs:__imp_RtlAllocateHeap
0x1800138b2  nop     dword ptr [rax+rax+00h]
0x1800138b7  mov     rbx, rax
0x1800138ba  test    rax, rax
0x1800138bd  jz      loc_180013AB1
0x1800138c3  mov     rcx, rax; this
0x1800138c6  call    ??0PeriodicEquation@@QEAA@XZ; PeriodicEquation::PeriodicEquation(void)
0x1800138cb  lea     rcx, ??_7SawtoothUpEquation@@6B@; const SawtoothUpEquation::`vftable'
0x1800138d2  jmp     loc_180013AAC
0x1800138d7  sub     edx, 6
0x1800138da  jz      loc_180013A74
0x1800138e0  sub     edx, 1
0x1800138e3  jz      loc_180013A32
0x1800138e9  sub     edx, 1
0x1800138ec  jz      loc_1800139F4
0x1800138f2  sub     edx, 1
0x1800138f5  jz      loc_1800139B3
0x1800138fb  cmp     edx, 1
0x1800138fe  jz      short loc_180013972
0x180013900  mov     eax, cs:dword_180069000
0x180013906  cmp     eax, 2
0x180013909  jbe     short loc_180013968
0x18001390b  mov     rcx, cs:qword_180069018
0x180013912  mov     rax, cs:qword_180069010
0x180013919  test    al, 8
0x18001391b  jz      short loc_180013968
0x18001391d  mov     rax, rcx
0x180013920  and     eax, 8
0x180013923  cmp     rax, rcx
0x180013926  jnz     short loc_180013968
0x180013928  lea     rax, aOnecoreXboxGam_27; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x18001392f  mov     [rbp+arg_8], 80070057h
0x180013936  mov     [rbp+var_10], rax
0x18001393a  lea     rdx, dword_18005CB04
0x180013941  lea     rax, [rbp+arg_8]
0x180013945  mov     [rbp+arg_18], 0F1h
0x18001394c  mov     [rsp+50h+var_20], rax
0x180013951  lea     rax, [rbp+arg_18]
0x180013955  mov     [rsp+50h+var_28], rax
0x18001395a  lea     rax, [rbp+var_10]
0x18001395e  mov     [rsp+50h+var_30], rax
0x180013963  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013968  mov     eax, 80070057h
0x18001396d  jmp     loc_180013BC1
0x180013972  mov     rcx, gs:60h
0x18001397b  xor     edx, edx; Flags
0x18001397d  mov     r8d, 90h; Size
0x180013983  mov     rcx, [rcx+30h]; HeapHandle
0x180013987  call    cs:__imp_RtlAllocateHeap
0x18001398e  nop     dword ptr [rax+rax+00h]
0x180013993  mov     rbx, rax
0x180013996  test    rax, rax
0x180013999  jz      loc_180013AB1
0x18001399f  mov     rcx, rax; this
0x1800139a2  call    ??0ConditionEquation@@QEAA@XZ; ConditionEquation::ConditionEquation(void)
0x1800139a7  lea     rcx, ??_7InertiaEquation@@6B@; const InertiaEquation::`vftable'
0x1800139ae  jmp     loc_180013AAC
0x1800139b3  mov     rcx, gs:60h
0x1800139bc  xor     edx, edx; Flags
0x1800139be  mov     r8d, 90h; Size
0x1800139c4  mov     rcx, [rcx+30h]; HeapHandle
0x1800139c8  call    cs:__imp_RtlAllocateHeap
0x1800139cf  nop     dword ptr [rax+rax+00h]
0x1800139d4  mov     rbx, rax
0x1800139d7  test    rax, rax
0x1800139da  jz      loc_180013AB1
0x1800139e0  mov     rcx, rax; this
0x1800139e3  call    ??0ConditionEquation@@QEAA@XZ; ConditionEquation::ConditionEquation(void)
0x1800139e8  lea     rcx, ??_7DamperEquation@@6B@; const DamperEquation::`vftable'
0x1800139ef  jmp     loc_180013AAC
0x1800139f4  mov     rcx, gs:60h
0x1800139fd  xor     edx, edx; Flags
0x1800139ff  mov     r8d, 90h; Size
0x180013a05  mov     rcx, [rcx+30h]; HeapHandle
0x180013a09  call    cs:__imp_RtlAllocateHeap
0x180013a10  nop     dword ptr [rax+rax+00h]
0x180013a15  mov     rbx, rax
0x180013a18  test    rax, rax
0x180013a1b  jz      loc_180013AB1
0x180013a21  mov     rcx, rax; this
0x180013a24  call    ??0ConditionEquation@@QEAA@XZ; ConditionEquation::ConditionEquation(void)
0x180013a29  lea     rcx, ??_7FrictionEquation@@6B@; const FrictionEquation::`vftable'
0x180013a30  jmp     short loc_180013AAC
0x180013a32  mov     rcx, gs:60h
0x180013a3b  xor     edx, edx; Flags
0x180013a3d  mov     r8d, 98h; Size
0x180013a43  mov     rcx, [rcx+30h]; HeapHandle
0x180013a47  call    cs:__imp_RtlAllocateHeap
0x180013a4e  nop     dword ptr [rax+rax+00h]
0x180013a53  mov     rbx, rax
0x180013a56  test    rax, rax
0x180013a59  jz      short loc_180013AB1
0x180013a5b  mov     rcx, rax; this
0x180013a5e  call    ??0ConditionEquation@@QEAA@XZ; ConditionEquation::ConditionEquation(void)
0x180013a63  xor     eax, eax
0x180013a65  lea     rcx, ??_7SpringEquation@@6B@; const SpringEquation::`vftable'
0x180013a6c  mov     [rbx+90h], eax
0x180013a72  jmp     short loc_180013AAC
0x180013a74  mov     rcx, gs:60h
0x180013a7d  xor     edx, edx; Flags
0x180013a7f  mov     r8d, 0A8h; Size
0x180013a85  mov     rcx, [rcx+30h]; HeapHandle
0x180013a89  call    cs:__imp_RtlAllocateHeap
0x180013a90  nop     dword ptr [rax+rax+00h]
0x180013a95  mov     rbx, rax
0x180013a98  test    rax, rax
0x180013a9b  jz      short loc_180013AB1
0x180013a9d  mov     rcx, rax; this
0x180013aa0  call    ??0PeriodicEquation@@QEAA@XZ; PeriodicEquation::PeriodicEquation(void)
0x180013aa5  lea     rcx, ??_7SawtoothDownEquation@@6B@; const SawtoothDownEquation::`vftable'
0x180013aac  mov     [rbx], rcx
0x180013aaf  jmp     short loc_180013AB3
0x180013ab1  xor     ebx, ebx
0x180013ab3  test    rbx, rbx
0x180013ab6  jnz     short loc_180013B28
0x180013ab8  mov     eax, cs:dword_180069000
0x180013abe  mov     ebx, 8007000Eh
0x180013ac3  cmp     eax, 2
0x180013ac6  jbe     short loc_180013B21
0x180013ac8  mov     rcx, cs:qword_180069018
0x180013acf  mov     rax, cs:qword_180069010
0x180013ad6  test    al, 8
0x180013ad8  jz      short loc_180013B21
0x180013ada  mov     rax, rcx
0x180013add  and     eax, 8
0x180013ae0  cmp     rax, rcx
0x180013ae3  jnz     short loc_180013B21
0x180013ae5  lea     rcx, [rbp+arg_8]
0x180013ae9  mov     [rbp+arg_8], ebx
0x180013aec  mov     [rsp+50h+var_20], rcx
0x180013af1  lea     rax, aOnecoreXboxGam_27; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180013af8  lea     rcx, [rbp+arg_18]
0x180013afc  mov     [rbp+arg_18], 0F6h
0x180013b03  mov     [rsp+50h+var_28], rcx
0x180013b08  lea     rdx, byte_18005BE93
0x180013b0f  lea     rcx, [rbp+var_10]
0x180013b13  mov     [rbp+var_10], rax
0x180013b17  mov     [rsp+50h+var_30], rcx
0x180013b1c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013b21  mov     eax, ebx
0x180013b23  jmp     loc_180013BC1
0x180013b28  mov     r8, [rsi+1170h]; struct Equation::VendorParameters *
0x180013b2f  mov     rdx, rsi; struct ApplicationMemory *
0x180013b32  mov     rcx, rbx; this
0x180013b35  call    ?CreateEquation@Equation@@QEAAJAEAVApplicationMemory@@PEBUVendorParameters@1@@Z; Equation::CreateEquation(ApplicationMemory &,Equation::VendorParameters const *)
0x180013b3a  mov     esi, eax
0x180013b3c  test    eax, eax
0x180013b3e  jns     short loc_180013BBC
0x180013b40  mov     ecx, cs:dword_180069000
0x180013b46  cmp     ecx, 2
0x180013b49  jbe     short loc_180013BA5
0x180013b4b  mov     rdx, cs:qword_180069018
0x180013b52  mov     rcx, cs:qword_180069010
0x180013b59  test    cl, 8
0x180013b5c  jz      short loc_180013BA5
0x180013b5e  mov     rax, rdx
0x180013b61  and     eax, 8
0x180013b64  cmp     rax, rdx
0x180013b67  jnz     short loc_180013BA5
0x180013b69  lea     rax, aOnecoreXboxGam_27; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x180013b70  mov     [rbp+arg_8], esi
0x180013b73  mov     [rbp+var_10], rax
0x180013b77  lea     rdx, word_18005C916
0x180013b7e  lea     rax, [rbp+arg_8]
0x180013b82  mov     [rbp+arg_18], 0F8h
0x180013b89  mov     [rsp+50h+var_20], rax
0x180013b8e  lea     rax, [rbp+arg_18]
0x180013b92  mov     [rsp+50h+var_28], rax
0x180013b97  lea     rax, [rbp+var_10]
0x180013b9b  mov     [rsp+50h+var_30], rax
0x180013ba0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013ba5  mov     rax, [rbx]
0x180013ba8  mov     edx, 1
0x180013bad  mov     rcx, rbx
0x180013bb0  mov     rax, [rax]
  ... truncated ...
```
