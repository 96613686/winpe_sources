# CAudioPump::InputPumpWorkRoutine(void *)

- ea: `0x140005240`
- end: `0x14000584e`
- name: `?InputPumpWorkRoutine@CAudioPump@@CAKPEAX@Z`
- size: `1550`
- prototype: `unsigned int __fastcall(CAudioPump *this)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400032f0`
- `0x140003c30`
- `0x140003ca0`
- `0x140003d00`
- `0x140004df0`
- `0x140004e50`
- `0x140005240`
- `0x140005860`
- `0x140005ac0`
- `0x140005b40`
- `0x140005b6c`
- `0x140005c6c`
- `0x140005d00`
- `0x140005d84`
- `0x14003a164`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400052f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400052f8`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x140005806`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x140005806`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400054c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400054c5`
- `ntdll!EtwEventActivityIdControl` at `0x140005299`
- `ntdll!EtwEventActivityIdControl` at `0x1400056c1`
- `ntdll!EtwEventActivityIdControl` at `0x140005299`
- `ntdll!EtwEventActivityIdControl` at `0x1400056c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioPump::InputPumpWorkRoutine(CAudioPump *this)
{
  __int64 v2; // rcx
  void *v3; // rdx
  __int64 v4; // rsi
  void (__fastcall *v5)(__int64, HANDLE, char *); // rbx
  HANDLE CurrentThread; // rax
  bool v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rsi
  bool v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned __int64 v19; // rcx
  double v20; // xmm0_8
  double v21; // xmm0_8
  unsigned __int64 v22; // rcx
  double v23; // xmm1_8
  double v24; // xmm0_8
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  bool v32; // cl
  __int64 v33; // [rsp+30h] [rbp-99h] BYREF
  CAudioPump *v34; // [rsp+38h] [rbp-91h] BYREF
  __int64 v35; // [rsp+40h] [rbp-89h] BYREF
  CAudioPump *v36; // [rsp+48h] [rbp-81h] BYREF
  __int64 v37; // [rsp+50h] [rbp-79h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-71h] BYREF
  __int64 v39; // [rsp+60h] [rbp-69h] BYREF
  __int128 v40; // [rsp+68h] [rbp-61h] BYREF
  __int128 v41; // [rsp+78h] [rbp-51h]
  __int64 v42; // [rsp+88h] [rbp-41h]
  __int128 v43; // [rsp+90h] [rbp-39h]
  _QWORD v44[2]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v45[16]; // [rsp+B0h] [rbp-19h] BYREF
  CAudioPump **v46; // [rsp+C0h] [rbp-9h]
  __int64 v47; // [rsp+C8h] [rbp-1h]
  CAudioPump **v48; // [rsp+D0h] [rbp+7h]
  __int64 v49; // [rsp+D8h] [rbp+Fh]
  CAudioPump **v50; // [rsp+E0h] [rbp+17h]
  __int64 v51; // [rsp+E8h] [rbp+1Fh]

  v43 = *((_OWORD *)this + 294);
  v44[0] = *((_QWORD *)this + 588);
  v44[1] = *((_QWORD *)this + 589);
  EtwEventActivityIdControl(4, v44);
  v33 = 0;
  v37 = 0;
  v35 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0pq_EtwEventWriteTransfer(v2, AudioCore_Pump_Process_Start, this, 0);
  CAudioPump::AttachToMMCSS(this);
  v4 = *((_QWORD *)this + 586);
  if ( v4 )
  {
    v5 = *(void (__fastcall **)(__int64, HANDLE, char *))(*(_QWORD *)v4 + 40LL);
    CurrentThread = GetCurrentThread();
    v5(v4, CurrentThread, (char *)this + 4696);
  }
  wil::details::SetEvent(*((wil::details **)this + 33), v3);
  v7 = (int)AERTLockCurrentThread() >= 0;
  v8 = *((_QWORD *)this + 584);
  v35 = v8;
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0p_EtwEventWriteTransfer(v8, AudioCore_Pump_Process_Stop, this);
  CAudioPump::Yield(this, &v35);
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0pq_EtwEventWriteTransfer(v9, AudioCore_Pump_Process_Start, this, 1);
  while ( !*((_BYTE *)this + 76) )
  {
    v10 = 0;
    v11 = *((_BYTE *)this + 4680) == 0;
    CAudioPump::CheckForPause(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 24LL))(*((_QWORD *)this + 10));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) )
    {
      (*(void (__fastcall **)(_QWORD, __int64 *, __int128 *))(**((_QWORD **)this + 26) + 24LL))(
        *((_QWORD *)this + 26),
        &v33,
        &v40);
      v14 = v33;
      if ( v33 <= 0 )
      {
        if ( (byte_1400E7E41 & 4) != 0 )
        {
          McTemplateU0pi_EtwEventWriteTransfer(v13, v12, this, v33);
          v14 = v33;
        }
      }
      else
      {
        CAudioPump::SignalWorkStarted(this);
        v14 = v33;
        v10 = v33;
      }
      if ( v14 > 0 )
      {
        while ( !*((_BYTE *)this + 76) )
        {
          v11 = 1;
          v15 = v33;
          if ( v33 > 0 )
          {
            while ( !*((_BYTE *)this + 76) )
            {
              v16 = v33;
              if ( v33 > *((_QWORD *)this + 13) )
                v16 = *((_QWORD *)this + 13);
              v37 = v16;
              (*(void (__fastcall **)(_QWORD, __int64 *, __int128 *))(**((_QWORD **)this + 10) + 32LL))(
                *((_QWORD *)this + 10),
                &v37,
                &v40);
              v17 = (unsigned int)(int)(*((float *)this + 28) * (double)(int)v37 / 10000000.0 + 0.5);
              *((_QWORD *)&v40 + 1) += v17;
              *(_QWORD *)&v41 = v41 - v17;
              v15 = v33 - v37;
              v33 = v15;
              if ( v15 < *((_QWORD *)this + 13) / 2LL )
              {
                v15 = 0;
                v33 = 0;
                goto LABEL_23;
              }
              if ( v15 <= 0 )
                goto LABEL_23;
            }
            v15 = v33;
          }
LABEL_23:
          if ( !*((_QWORD *)this + 39) )
          {
            (*(void (__fastcall **)(_QWORD, __int64 *, __int128 *))(**((_QWORD **)this + 26) + 24LL))(
              *((_QWORD *)this + 26),
              &v33,
              &v40);
            v15 = v33;
            if ( v33 < *((_QWORD *)this + 13) / 2LL )
            {
              v33 = 0;
              break;
            }
          }
          if ( v15 <= 0 )
            break;
        }
      }
    }
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v19 = PerformanceCount.QuadPart - v35;
    if ( PerformanceCount.QuadPart - v35 < 0 )
      v20 = (double)(int)(v19 & 1 | (v19 >> 1)) + (double)(int)(v19 & 1 | (v19 >> 1));
    else
      v20 = (double)(int)v19;
    v21 = v20 * 10000000.0;
    v22 = g_u64QPCFrequency;
    if ( (g_u64QPCFrequency & 0x8000000000000000uLL) != 0LL )
    {
      v22 = g_u64QPCFrequency & 1;
      v23 = (double)(int)(v22 | (g_u64QPCFrequency >> 1)) + (double)(int)(v22 | (g_u64QPCFrequency >> 1));
    }
    else
    {
      v23 = (double)(int)g_u64QPCFrequency;
    }
    v24 = v21 / v23;
    v25 = (unsigned int)(int)v24;
    *((_QWORD *)this + 45) = v25;
    *((_QWORD *)this + 49) += v25;
    ++*((_DWORD *)this + 100);
    if ( (byte_1400E7E41 & 8) != 0 )
    {
      v36 = (CAudioPump *)*((_QWORD *)this + 44);
      v39 = (unsigned int)(int)v24;
      v34 = this;
      v46 = &v34;
      v47 = 8;
      v48 = (CAudioPump **)&v39;
      v49 = 8;
      v50 = &v36;
      v51 = 8;
      McGenEventWrite_EtwEventWriteTransfer(v22, (__int64)AudioCore_Pump_ProcPassDuration, v18, 4, (__int64)v45);
    }
    if ( v25 > *((_QWORD *)this + 44) && _InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) )
      *((_QWORD *)this + 48) = _InterlockedIncrement64((volatile signed __int64 *)this + 48);
    else
      _InterlockedExchange64((volatile __int64 *)this + 48, 0);
    if ( v10 )
      CAudioPump::SignalWorkCompleted(this);
    if ( *((_BYTE *)this + 4680) )
    {
      if ( *((_BYTE *)this + 4760) )
      {
        _InterlockedExchange((volatile __int32 *)this + 1189, 2);
        WakeByAddressAll((char *)this + 4756);
        *((_BYTE *)this + 4760) = 0;
      }
      v32 = 0;
      if ( *((_DWORD *)this + 1189) == 1 )
        v32 = v11;
      *((_BYTE *)this + 4681) = v32;
    }
    (*(void (__fastcall **)(_QWORD, bool))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10), v11);
    if ( (byte_1400E7E41 & 8) != 0 )
    {
      v36 = this;
      v46 = &v36;
      v47 = 8;
      McGenEventWrite_EtwEventWriteTransfer(v26, (__int64)AudioCore_Pump_Process_Stop, v27, 2, (__int64)v45);
    }
    CAudioPump::Yield(this, &v35);
    v35 = *((_QWORD *)this + 584);
    if ( (byte_1400E7E41 & 8) != 0 )
    {
      LODWORD(v34) = 2;
      v36 = this;
      v46 = &v36;
      v47 = 8;
      v48 = &v34;
      v49 = 4;
      McGenEventWrite_EtwEventWriteTransfer(v28, (__int64)AudioCore_Pump_Process_Start, v29, 3, (__int64)v45);
    }
  }
  CAudioPump::CancelDeadline(this);
  ResetEngineThreadPriority((void **)this + 29, *((_DWORD *)this + 61));
  *((_DWORD *)this + 61) = 0;
  if ( v7 )
    AERTUnlockCurrentThread();
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0p_EtwEventWriteTransfer(v30, AudioCore_Pump_Process_Stop, this);
  EtwEventActivityIdControl(4, v44);
  return 0;
}

```

## disassembly

```asm
0x140005240  mov     [rsp-8+arg_8], rbx
0x140005245  mov     [rsp-8+arg_10], rsi
0x14000524a  push    rbp
0x14000524b  push    rdi
0x14000524c  push    r12
0x14000524e  push    r14
0x140005250  push    r15
0x140005252  lea     rbp, [rsp-37h]
0x140005257  sub     rsp, 100h
0x14000525e  mov     rax, cs:__security_cookie
0x140005265  xor     rax, rsp
0x140005268  mov     [rbp+57h+var_30], rax
0x14000526c  mov     rdi, rcx
0x14000526f  movups  xmm0, xmmword ptr [rcx+1260h]
0x140005276  movups  [rbp+57h+var_90], xmm0
0x14000527a  mov     rax, [rcx+1260h]
0x140005281  mov     [rbp+57h+var_80], rax
0x140005285  mov     rax, [rcx+1268h]
0x14000528c  mov     [rbp+57h+var_78], rax
0x140005290  lea     rdx, [rbp+57h+var_80]
0x140005294  mov     ecx, 4
0x140005299  call    cs:__imp_EtwEventActivityIdControl
0x14000529f  nop
0x1400052a0  xor     r12d, r12d
0x1400052a3  mov     [rsp+120h+var_F0], r12
0x1400052a8  mov     [rbp+57h+var_D0], r12
0x1400052ac  mov     [rsp+120h+var_E0], r12
0x1400052b1  xorps   xmm0, xmm0
0x1400052b4  xor     eax, eax
0x1400052b6  movups  [rbp+57h+var_B8], xmm0
0x1400052ba  movups  [rbp+57h+var_A8], xmm0
0x1400052be  mov     [rbp+57h+var_98], rax
0x1400052c2  test    cs:byte_1400E7E41, 8
0x1400052c9  jz      short loc_1400052DD
0x1400052cb  xor     r9d, r9d
0x1400052ce  mov     r8, rdi
0x1400052d1  lea     rdx, AudioCore_Pump_Process_Start
0x1400052d8  call    McTemplateU0pq_EtwEventWriteTransfer
0x1400052dd  mov     rcx, rdi; this
0x1400052e0  call    ?AttachToMMCSS@CAudioPump@@AEAAXXZ; CAudioPump::AttachToMMCSS(void)
0x1400052e5  mov     rsi, [rdi+1250h]
0x1400052ec  test    rsi, rsi
0x1400052ef  jz      short loc_140005313
0x1400052f1  mov     rax, [rsi]
0x1400052f4  mov     rbx, [rax+28h]
0x1400052f8  call    cs:__imp_GetCurrentThread
0x1400052fe  lea     r8, [rdi+1258h]
0x140005305  mov     rdx, rax
0x140005308  mov     rcx, rsi
0x14000530b  mov     rax, rbx
0x14000530e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005313  mov     rcx, [rdi+108h]; this
0x14000531a  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x14000531f  call    ?AERTLockCurrentThread@@YAJXZ; AERTLockCurrentThread(void)
0x140005324  mov     r15d, eax
0x140005327  shr     r15d, 1Fh
0x14000532b  xor     r15b, 1
0x14000532f  mov     rcx, [rdi+1240h]
0x140005336  mov     [rsp+120h+var_E0], rcx
0x14000533b  test    cs:byte_1400E7E41, 8
0x140005342  jnz     loc_1400057D1
0x140005348  lea     rdx, [rsp+120h+var_E0]
0x14000534d  mov     rcx, rdi
0x140005350  call    ?Yield@CAudioPump@@AEAA?AW4TEventType@1@PEA_K@Z; CAudioPump::Yield(unsigned __int64 *)
0x140005355  test    cs:byte_1400E7E41, 8
0x14000535c  jnz     loc_140005783
0x140005362  movzx   eax, byte ptr [rdi+4Ch]
0x140005366  test    al, al
0x140005368  jnz     loc_140005681
0x14000536e  xchg    ax, ax
0x140005370  mov     rsi, r12
0x140005373  cmp     [rdi+1248h], r12b
0x14000537a  setz    r14b
0x14000537e  mov     rcx, rdi; this
0x140005381  call    ?CheckForPause@CAudioPump@@AEAAXXZ; CAudioPump::CheckForPause(void)
0x140005386  mov     rcx, [rdi+50h]
0x14000538a  mov     rax, [rcx]
0x14000538d  mov     rax, [rax+18h]
0x140005391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005396  mov     ecx, r12d
0x140005399  xor     eax, eax
0x14000539b  lock cmpxchg [rdi+150h], ecx
0x1400053a3  jz      loc_1400054BD
0x1400053a9  mov     rcx, [rdi+0D0h]
0x1400053b0  mov     rax, [rcx]
0x1400053b3  lea     r8, [rbp+57h+var_B8]
0x1400053b7  lea     rdx, [rsp+120h+var_F0]
0x1400053bc  mov     rax, [rax+18h]
0x1400053c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053c5  mov     rax, [rsp+120h+var_F0]
0x1400053ca  test    rax, rax
0x1400053cd  jle     loc_140005731
0x1400053d3  mov     rcx, rdi; this
0x1400053d6  call    ?SignalWorkStarted@CAudioPump@@AEAAXXZ; CAudioPump::SignalWorkStarted(void)
0x1400053db  mov     rax, [rsp+120h+var_F0]
0x1400053e0  mov     rsi, rax
0x1400053e3  test    rax, rax
0x1400053e6  jle     loc_1400054BD
0x1400053ec  movzx   eax, byte ptr [rdi+4Ch]
0x1400053f0  test    al, al
0x1400053f2  jnz     loc_1400054BD
0x1400053f8  mov     r14b, 1
0x1400053fb  mov     rcx, [rsp+120h+var_F0]
0x140005400  test    rcx, rcx
0x140005403  jle     loc_1400054A7
0x140005409  movzx   eax, byte ptr [rdi+4Ch]
0x14000540d  test    al, al
0x14000540f  jnz     loc_1400057E5
0x140005415  mov     rax, [rsp+120h+var_F0]
0x14000541a  cmp     rax, [rdi+68h]
0x14000541e  cmovg   rax, [rdi+68h]
0x140005423  mov     [rbp+57h+var_D0], rax
0x140005427  mov     rcx, [rdi+50h]
0x14000542b  mov     rax, [rcx]
0x14000542e  lea     r8, [rbp+57h+var_B8]
0x140005432  lea     rdx, [rbp+57h+var_D0]
0x140005436  mov     rax, [rax+20h]
0x14000543a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000543f  movss   xmm1, dword ptr [rdi+70h]
0x140005444  cvtps2pd xmm1, xmm1
0x140005447  mov     rdx, [rbp+57h+var_D0]
0x14000544b  xorps   xmm0, xmm0
0x14000544e  cvtsi2sd xmm0, rdx
0x140005453  mulsd   xmm1, xmm0
0x140005457  divsd   xmm1, cs:__real@416312d000000000
0x14000545f  addsd   xmm1, cs:__real@3fe0000000000000
0x140005467  cvttsd2si rcx, xmm1
0x14000546c  mov     ecx, ecx
0x14000546e  add     qword ptr [rbp+57h+var_B8+8], rcx
0x140005472  sub     qword ptr [rbp+57h+var_A8], rcx
0x140005476  mov     rcx, [rsp+120h+var_F0]
0x14000547b  sub     rcx, rdx
0x14000547e  mov     [rsp+120h+var_F0], rcx
0x140005483  mov     rax, [rdi+68h]
0x140005487  cqo
0x140005489  sub     rax, rdx
0x14000548c  sar     rax, 1
0x14000548f  cmp     rcx, rax
0x140005492  jl      short loc_14000549F
0x140005494  test    rcx, rcx
0x140005497  jg      loc_140005409
0x14000549d  jmp     short loc_1400054A7
0x14000549f  mov     rcx, r12
0x1400054a2  mov     [rsp+120h+var_F0], rcx
0x1400054a7  cmp     [rdi+138h], r12
0x1400054ae  jz      loc_1400056F1
0x1400054b4  test    rcx, rcx
0x1400054b7  jg      loc_1400053EC
0x1400054bd  mov     qword ptr [rbp+57h+PerformanceCount], r12
0x1400054c1  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1400054c5  call    cs:__imp_QueryPerformanceCounter
0x1400054cb  mov     rcx, qword ptr [rbp+57h+PerformanceCount]
0x1400054cf  sub     rcx, [rsp+120h+var_E0]
0x1400054d4  xorps   xmm0, xmm0
0x1400054d7  js      loc_14000579D
0x1400054dd  cvtsi2sd xmm0, rcx
0x1400054e2  mulsd   xmm0, cs:__real@416312d000000000
0x1400054ea  mov     rcx, cs:?g_u64QPCFrequency@@3_KA; unsigned __int64 g_u64QPCFrequency
0x1400054f1  xorps   xmm1, xmm1
0x1400054f4  test    rcx, rcx
0x1400054f7  js      loc_1400057B7
0x1400054fd  cvtsi2sd xmm1, rcx
0x140005502  divsd   xmm0, xmm1
0x140005506  cvttsd2si rbx, xmm0
0x14000550b  mov     [rdi+168h], rbx
0x140005512  add     [rdi+188h], rbx
0x140005519  inc     dword ptr [rdi+190h]
0x14000551f  test    cs:byte_1400E7E41, 8
0x140005526  jz      short loc_14000558A
0x140005528  mov     rax, [rdi+160h]
0x14000552f  mov     [rsp+120h+var_D8], rax
0x140005534  mov     [rbp+57h+var_C0], rbx
0x140005538  mov     [rsp+120h+var_E8], rdi
0x14000553d  lea     rax, [rsp+120h+var_E8]
0x140005542  mov     [rbp+57h+var_60], rax
0x140005546  mov     [rbp+57h+var_58], 8
0x14000554e  lea     rax, [rbp+57h+var_C0]
0x140005552  mov     [rbp+57h+var_50], rax
0x140005556  mov     [rbp+57h+var_48], 8
0x14000555e  lea     rax, [rsp+120h+var_D8]
0x140005563  mov     [rbp+57h+var_40], rax
0x140005567  mov     [rbp+57h+var_38], 8
0x14000556f  lea     rax, [rbp+57h+var_70]
0x140005573  mov     [rsp+120h+var_100], rax
0x140005578  mov     r9d, 4
0x14000557e  lea     rdx, AudioCore_Pump_ProcPassDuration
0x140005585  call    McGenEventWrite_EtwEventWriteTransfer
0x14000558a  cmp     rbx, [rdi+160h]
0x140005591  jg      loc_140005753
0x140005597  mov     rax, r12
0x14000559a  xchg    rax, [rdi+180h]
0x1400055a1  test    rsi, rsi
0x1400055a4  jz      short loc_1400055AE
0x1400055a6  mov     rcx, rdi; this
0x1400055a9  call    ?SignalWorkCompleted@CAudioPump@@AEAAXXZ; CAudioPump::SignalWorkCompleted(void)
0x1400055ae  cmp     [rdi+1248h], r12b
0x1400055b5  jnz     loc_1400057EF
0x1400055bb  mov     rcx, [rdi+50h]
0x1400055bf  mov     rax, [rcx]
0x1400055c2  movzx   edx, r14b
0x1400055c6  mov     rax, [rax+30h]
0x1400055ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055cf  test    cs:byte_1400E7E41, 8
0x1400055d6  jz      short loc_140005609
0x1400055d8  mov     [rsp+120h+var_D8], rdi
0x1400055dd  lea     rax, [rsp+120h+var_D8]
0x1400055e2  mov     [rbp+57h+var_60], rax
0x1400055e6  mov     [rbp+57h+var_58], 8
0x1400055ee  lea     rax, [rbp+57h+var_70]
0x1400055f2  mov     [rsp+120h+var_100], rax
0x1400055f7  mov     r9d, 2
0x1400055fd  lea     rdx, AudioCore_Pump_Process_Stop
0x140005604  call    McGenEventWrite_EtwEventWriteTransfer
0x140005609  lea     rdx, [rsp+120h+var_E0]
0x14000560e  mov     rcx, rdi
0x140005611  call    ?Yield@CAudioPump@@AEAA?AW4TEventType@1@PEA_K@Z; CAudioPump::Yield(unsigned __int64 *)
0x140005616  mov     rax, [rdi+1240h]
0x14000561d  mov     [rsp+120h+var_E0], rax
0x140005622  test    cs:byte_1400E7E41, 8
0x140005629  jz      short loc_140005675
0x14000562b  mov     dword ptr [rsp+120h+var_E8], 2
0x140005633  mov     [rsp+120h+var_D8], rdi
0x140005638  lea     rax, [rsp+120h+var_D8]
0x14000563d  mov     [rbp+57h+var_60], rax
0x140005641  mov     [rbp+57h+var_58], 8
0x140005649  lea     rax, [rsp+120h+var_E8]
0x14000564e  mov     [rbp+57h+var_50], rax
0x140005652  mov     [rbp+57h+var_48], 4
0x14000565a  lea     rax, [rbp+57h+var_70]
0x14000565e  mov     [rsp+120h+var_100], rax
0x140005663  mov     r9d, 3
0x140005669  lea     rdx, AudioCore_Pump_Process_Start
0x140005670  call    McGenEventWrite_EtwEventWriteTransfer
0x140005675  movzx   eax, byte ptr [rdi+4Ch]
0x140005679  test    al, al
0x14000567b  jz      loc_140005370
0x140005681  mov     rcx, rdi; this
0x140005684  call    ?CancelDeadline@CAudioPump@@AEAAXXZ; CAudioPump::CancelDeadline(void)
0x140005689  lea     rcx, [rdi+0E8h]; void **
0x140005690  mov     edx, [rdi+0F4h]; unsigned int
0x140005696  call    ?ResetEngineThreadPriority@@YAJPEAPEAXK@Z; ResetEngineThreadPriority(void * *,ulong)
0x14000569b  mov     [rdi+0F4h], r12d
0x1400056a2  test    r15b, r15b
0x1400056a5  jnz     loc_14000582F
0x1400056ab  test    cs:byte_1400E7E41, 8
0x1400056b2  jnz     loc_140005839
0x1400056b8  lea     rdx, [rbp+57h+var_80]
0x1400056bc  mov     ecx, 4
0x1400056c1  call    cs:__imp_EtwEventActivityIdControl
0x1400056c7  xor     eax, eax
0x1400056c9  mov     rcx, [rbp+57h+var_30]
0x1400056cd  xor     rcx, rsp; StackCookie
0x1400056d0  call    __security_check_cookie
0x1400056d5  lea     r11, [rsp+120h+var_20]
0x1400056dd  mov     rbx, [r11+38h]
0x1400056e1  mov     rsi, [r11+40h]
0x1400056e5  mov     rsp, r11
0x1400056e8  pop     r15
0x1400056ea  pop     r14
0x1400056ec  pop     r12
0x1400056ee  pop     rdi
0x1400056ef  pop     rbp
0x1400056f0  retn
0x1400056f1  mov     rcx, [rdi+0D0h]
0x1400056f8  mov     rax, [rcx]
0x1400056fb  lea     r8, [rbp+57h+var_B8]
0x1400056ff  lea     rdx, [rsp+120h+var_F0]
0x140005704  mov     rax, [rax+18h]
0x140005708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000570d  mov     rax, [rdi+68h]
0x140005711  cqo
0x140005713  sub     rax, rdx
0x140005716  sar     rax, 1
0x140005719  mov     rcx, [rsp+120h+var_F0]
0x14000571e  cmp     rcx, rax
0x140005721  jge     loc_1400054B4
0x140005727  mov     [rsp+120h+var_F0], r12
0x14000572c  jmp     loc_1400054BD
0x140005731  test    cs:byte_1400E7E41, 4
0x140005738  jz      loc_1400053E3
0x14000573e  mov     r9, rax
0x140005741  mov     r8, rdi
0x140005744  call    McTemplateU0pi_EtwEventWriteTransfer
0x140005749  mov     rax, [rsp+120h+var_F0]
0x14000574e  jmp     loc_1400053E3
0x140005753  mov     ecx, r12d
0x140005756  xor     eax, eax
0x140005758  lock cmpxchg [rdi+150h], ecx
0x140005760  jz      loc_140005597
0x140005766  mov     eax, 1
0x14000576b  lock xadd [rdi+180h], rax
0x140005774  inc     rax
0x140005777  mov     [rdi+180h], rax
0x14000577e  jmp     loc_1400055A1
0x140005783  mov     r9d, 1
0x140005789  mov     r8, rdi
0x14000578c  lea     rdx, AudioCore_Pump_Process_Start
0x140005793  call    McTemplateU0pq_EtwEventWriteTransfer
0x140005798  jmp     loc_140005362
0x14000579d  mov     rax, rcx
  ... truncated ...
```
