# CMediaSampleCopyBuffer::GetCopyBuffer(unsigned __int64 *,uchar * *,int *)

- ea: `0x18002a170`
- end: `0x18002a773`
- name: `?GetCopyBuffer@CMediaSampleCopyBuffer@@UEAAJPEA_KPEAPEAEPEAH@Z`
- size: `1539`
- prototype: `__int64 __fastcall(CMediaSampleCopyBuffer *__hidden this, unsigned __int64 *, unsigned __int8 **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002820`
- `0x18002a170`
- `0x18002d514`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800aa560`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a20c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a315`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a20c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a35f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a35f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a1f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a2fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a1f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a2fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a5b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a724`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a5b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a724`

## string_xrefs

- `0x18002a22c`: `CMediaSampleCopyBuffer::GetCopyBuffer`

## pseudocode

```c
__int64 __fastcall CMediaSampleCopyBuffer::GetCopyBuffer(
        CMediaSampleCopyBuffer *this,
        unsigned __int64 *a2,
        unsigned __int8 **a3,
        int *a4)
{
  CallStackTracing *v4; // rdi
  char *v9; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // dl
  __int64 v15; // rcx
  int v16; // eax
  int v17; // esi
  unsigned __int64 v18; // rcx
  int v19; // eax
  CallStackTracing *v20; // rdi
  GUID *v21; // rbx
  DWORD v22; // r14d
  GUID *v23; // rax
  int v24; // eax
  int v25; // eax
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // eax
  CallStackTracing *v30; // rcx
  __int64 v31; // rax
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  CallStackTracing *v34; // rax
  CallStackTracing *v35; // rax
  unsigned __int64 v36; // [rsp+40h] [rbp-19h] BYREF
  __int64 v37; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v38[6]; // [rsp+50h] [rbp-9h] BYREF
  char v39; // [rsp+C0h] [rbp+67h] BYREF

  v4 = CallStackTracing::s_wpInstance;
  v36 = 0;
  v37 = 0;
  memset(v38, 0, 64);
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v9 = (char *)v4 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v30 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v30)(v30);
      if ( v31 )
        v9 = (char *)v31;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "CMediaSampleCopyBuffer::GetCopyBuffer";
      *(_DWORD *)&v9[8 * v13 + 8] = 93;
    }
    ++*((_DWORD *)v9 + 497);
  }
  v14 = byte_1800EACCB;
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qqqD(*((_QWORD *)WPP_GLOBAL_Control + 17), (unsigned __int8)byte_1800EACCB, 0, this, a2, a3, *a4);
    v14 = byte_1800EACCB;
  }
  v15 = *(_QWORD *)(*((_QWORD *)this + 4) + 216LL);
  if ( v15 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v15 + 56LL))(
            v15,
            &v36,
            0,
            0,
            0);
    v17 = v16;
    if ( v16 )
    {
      if ( byte_1800EACCB )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 14, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this, v16);
      if ( v17 < 0 )
        goto LABEL_16;
    }
    if ( !*((_DWORD *)this + 21) )
    {
LABEL_14:
      v18 = v36;
      *a2 = v36;
      (*(void (__fastcall **)(unsigned __int64, unsigned __int8 **))(*(_QWORD *)v18 + 24LL))(v18, a3);
      v19 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v36 + 32LL))(v36);
      *a4 = v19;
      if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 19, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this, v19);
LABEL_16:
      v20 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v21 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
        v22 = GetLastError();
        v23 = (GUID *)TlsGetValue(*((_DWORD *)v20 + 3));
        if ( v23 )
        {
          v21 = v23;
        }
        else if ( !GetLastError() )
        {
          v32 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
            {
              v32 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
          if ( v33 )
            v21 = (GUID *)v33;
        }
        SetLastError(v22);
        v24 = *(_DWORD *)&v21[124].Data2;
        if ( v24 )
        {
          v25 = v24 - 1;
          *(_DWORD *)&v21[124].Data2 = v25;
          if ( !v25 )
          {
            *(_DWORD *)&v21[124].Data2 = 0;
            *(_QWORD *)&v21[126].Data1 = 0;
            *(_DWORD *)&v21[124].Data4[4] = 0;
            v21[125] = GUID_00000000_0000_0000_0000_000000000000;
            *(_DWORD *)v21[126].Data4 = 0;
            v21[124].Data1 = GetCurrentThreadId();
          }
        }
      }
      return (unsigned int)v17;
    }
    v27 = (**(__int64 (__fastcall ***)(unsigned __int64, GUID *, __int64 *))v36)(v36, &IID_IMediaSample2, &v37);
    v28 = v27;
    if ( v27 >= 0 )
    {
      v29 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *))(*(_QWORD *)v37 + 152LL))(v37, 64, v38);
      v17 = v29;
      if ( !v29 )
        goto LABEL_28;
      if ( byte_1800EACCB )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this, v29);
      if ( v17 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      else
      {
LABEL_28:
        DWORD1(v38[0]) = *((_DWORD *)this + 20) & 0x1FFF | DWORD1(v38[0]) & 0xFFFFE;
        v17 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *))(*(_QWORD *)v37 + 160LL))(v37, 64, v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        if ( v17 >= 0 )
        {
          if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              18,
              &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids,
              this,
              *((_DWORD *)this + 20));
          goto LABEL_14;
        }
      }
      if ( byte_1800EACCB )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 17, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this, v17);
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v36 + 16LL))(v36);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v39);
      return (unsigned int)v17;
    }
    if ( byte_1800EACCB )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 15, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this, v27);
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v36 + 16LL))(v36);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v39);
    return v28;
  }
  else
  {
    if ( v14 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 13, &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids, this);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v39);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18002a170  mov     [rsp-8+arg_18], rdi
0x18002a175  push    rbp
0x18002a176  push    r12
0x18002a178  push    r13
0x18002a17a  push    r14
0x18002a17c  push    r15
0x18002a17e  lea     rbp, [rsp-37h]
0x18002a183  sub     rsp, 90h
0x18002a18a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a191  xorps   xmm0, xmm0
0x18002a194  mov     r12, r8
0x18002a197  mov     r15, r9
0x18002a19a  xor     r8d, r8d
0x18002a19d  mov     r13, rdx
0x18002a1a0  mov     [rbp+57h+var_70], r8
0x18002a1a4  mov     r14, rcx
0x18002a1a7  mov     [rbp+57h+var_68], r8
0x18002a1ab  movups  [rbp+57h+var_60], xmm0
0x18002a1af  movups  [rbp+57h+var_50], xmm0
0x18002a1b3  movups  [rbp+57h+var_40], xmm0
0x18002a1b7  movups  [rbp+57h+var_30], xmm0
0x18002a1bb  test    rdi, rdi
0x18002a1be  jz      loc_18002A59E
0x18002a1c4  cmp     byte ptr [rdi+8], 0
0x18002a1c8  mov     [rsp+0B0h+arg_8], rbx
0x18002a1d0  mov     [rsp+0B0h+arg_10], rsi
0x18002a1d8  jz      short loc_18002A245
0x18002a1da  lea     rbx, [rdi+0D0h]
0x18002a1e1  call    cs:__imp_GetLastError
0x18002a1e8  nop     dword ptr [rax+rax+00h]
0x18002a1ed  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002a1f0  mov     esi, eax
0x18002a1f2  call    cs:__imp_TlsGetValue
0x18002a1f9  nop     dword ptr [rax+rax+00h]
0x18002a1fe  test    rax, rax
0x18002a201  jz      loc_18002A4B6
0x18002a207  mov     rbx, rax
0x18002a20a  mov     ecx, esi; dwErrCode
0x18002a20c  call    cs:__imp_SetLastError
0x18002a213  nop     dword ptr [rax+rax+00h]
0x18002a218  mov     eax, [rbx+7C4h]
0x18002a21e  xor     r8d, r8d
0x18002a221  cmp     eax, [rbx+7C8h]
0x18002a227  jnb     short loc_18002A23F
0x18002a229  add     rax, rax
0x18002a22c  lea     rcx, aCmediasampleco; "CMediaSampleCopyBuffer::GetCopyBuffer"
0x18002a233  mov     [rbx+rax*8], rcx
0x18002a237  mov     dword ptr [rbx+rax*8+8], 5Dh ; ']'
0x18002a23f  inc     dword ptr [rbx+7C4h]
0x18002a245  movzx   edx, cs:byte_1800EACCB
0x18002a24c  cmp     dl, 20h ; ' '
0x18002a24f  jnb     loc_18002A601
0x18002a255  mov     rax, [r14+20h]
0x18002a259  mov     rcx, [rax+0D8h]
0x18002a260  test    rcx, rcx
0x18002a263  jz      loc_18002A39D
0x18002a269  mov     rax, [rcx]
0x18002a26c  lea     rdx, [rbp+57h+var_70]
0x18002a270  mov     dword ptr [rsp+0B0h+var_90], r8d
0x18002a275  xor     r9d, r9d
0x18002a278  xor     r8d, r8d
0x18002a27b  mov     rax, [rax+38h]
0x18002a27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a284  mov     esi, eax
0x18002a286  test    eax, eax
0x18002a288  jnz     loc_18002A65E
0x18002a28e  cmp     dword ptr [r14+54h], 0
0x18002a293  jnz     loc_18002A3B6
0x18002a299  mov     rcx, [rbp+57h+var_70]
0x18002a29d  mov     rdx, r12
0x18002a2a0  mov     [r13+0], rcx
0x18002a2a4  mov     rax, [rcx]
0x18002a2a7  mov     rax, [rax+18h]
0x18002a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2b0  mov     rcx, [rbp+57h+var_70]
0x18002a2b4  mov     rax, [rcx]
0x18002a2b7  mov     rax, [rax+20h]
0x18002a2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2c0  mov     [r15], eax
0x18002a2c3  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18002a2ca  jnb     loc_18002A6F9
0x18002a2d0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a2d7  cmp     byte ptr [rdi+8], 0
0x18002a2db  jz      loc_18002A371
0x18002a2e1  lea     rbx, [rdi+0D0h]
0x18002a2e8  call    cs:__imp_GetLastError
0x18002a2ef  nop     dword ptr [rax+rax+00h]
0x18002a2f4  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002a2f7  mov     r14d, eax
0x18002a2fa  call    cs:__imp_TlsGetValue
0x18002a301  nop     dword ptr [rax+rax+00h]
0x18002a306  test    rax, rax
0x18002a309  jz      loc_18002A4F1
0x18002a30f  mov     rbx, rax
0x18002a312  mov     ecx, r14d; dwErrCode
0x18002a315  call    cs:__imp_SetLastError
0x18002a31c  nop     dword ptr [rax+rax+00h]
0x18002a321  mov     eax, [rbx+7C4h]
0x18002a327  test    eax, eax
0x18002a329  jz      short loc_18002A371
0x18002a32b  sub     eax, 1
0x18002a32e  mov     [rbx+7C4h], eax
0x18002a334  jnz     short loc_18002A371
0x18002a336  xor     eax, eax
0x18002a338  mov     [rbx+7C4h], eax
0x18002a33e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002a345  mov     [rbx+7E0h], rax
0x18002a34c  mov     [rbx+7CCh], eax
0x18002a352  movups  xmmword ptr [rbx+7D0h], xmm0
0x18002a359  mov     [rbx+7E8h], eax
0x18002a35f  call    cs:__imp_GetCurrentThreadId
0x18002a366  nop     dword ptr [rax+rax+00h]
0x18002a36b  mov     [rbx+7C0h], eax
0x18002a371  mov     eax, esi
0x18002a373  mov     rsi, [rsp+0B0h+arg_10]
0x18002a37b  mov     rbx, [rsp+0B0h+arg_8]
0x18002a383  mov     rdi, [rsp+0B0h+arg_18]
0x18002a38b  add     rsp, 90h
0x18002a392  pop     r15
0x18002a394  pop     r14
0x18002a396  pop     r13
0x18002a398  pop     r12
0x18002a39a  pop     rbp
0x18002a39b  retn
0x18002a39d  cmp     dl, 1
0x18002a3a0  jnb     loc_18002A637
0x18002a3a6  lea     rcx, [rbp+57h+arg_0]; this
0x18002a3aa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002a3af  mov     eax, 80004005h
0x18002a3b4  jmp     short loc_18002A373
0x18002a3b6  mov     rcx, [rbp+57h+var_70]
0x18002a3ba  lea     r8, [rbp+57h+var_68]
0x18002a3be  lea     rdx, IID_IMediaSample2
0x18002a3c5  mov     rax, [rcx]
0x18002a3c8  mov     rax, [rax]
0x18002a3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3d0  mov     ebx, eax
0x18002a3d2  test    eax, eax
0x18002a3d4  js      loc_18002A489
0x18002a3da  mov     rcx, [rbp+57h+var_68]
0x18002a3de  lea     r8, [rbp+57h+var_60]
0x18002a3e2  mov     edx, 40h ; '@'
0x18002a3e7  mov     rax, [rcx]
0x18002a3ea  mov     rax, [rax+98h]
0x18002a3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3f6  mov     esi, eax
0x18002a3f8  test    eax, eax
0x18002a3fa  jnz     loc_18002A6C1
0x18002a400  mov     ecx, dword ptr [rbp+57h+var_60+4]
0x18002a403  lea     r8, [rbp+57h+var_60]
0x18002a407  mov     eax, [r14+50h]
0x18002a40b  and     ecx, 0FFFFEh
0x18002a411  and     eax, 1FFFh
0x18002a416  mov     edx, 40h ; '@'
0x18002a41b  or      ecx, eax
0x18002a41d  mov     dword ptr [rbp+57h+var_60+4], ecx
0x18002a420  mov     rcx, [rbp+57h+var_68]
0x18002a424  mov     rax, [rcx]
0x18002a427  mov     rax, [rax+0A0h]
0x18002a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a433  mov     rcx, [rbp+57h+var_68]
0x18002a437  mov     esi, eax
0x18002a439  mov     rax, [rcx]
0x18002a43c  mov     rax, [rax+10h]
0x18002a440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a445  test    esi, esi
0x18002a447  js      loc_18002A551
0x18002a44d  cmp     cs:byte_1800EACCB, 10h
0x18002a454  jb      loc_18002A299
0x18002a45a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a461  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
0x18002a468  mov     eax, [r14+50h]
0x18002a46c  mov     edx, 12h
0x18002a471  mov     r9, r14
0x18002a474  mov     dword ptr [rsp+0B0h+var_90], eax
0x18002a478  mov     rcx, [rcx+88h]
0x18002a47f  call    WPP_SF_qD
0x18002a484  jmp     loc_18002A299
0x18002a489  cmp     cs:byte_1800EACCB, 1
0x18002a490  jnb     loc_18002A696
0x18002a496  mov     rcx, [rbp+57h+var_70]
0x18002a49a  mov     rax, [rcx]
0x18002a49d  mov     rax, [rax+10h]
0x18002a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4a6  lea     rcx, [rbp+57h+arg_0]; this
0x18002a4aa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002a4af  mov     eax, ebx
0x18002a4b1  jmp     loc_18002A373
0x18002a4b6  call    cs:__imp_GetLastError
0x18002a4bd  nop     dword ptr [rax+rax+00h]
0x18002a4c2  test    eax, eax
0x18002a4c4  jnz     loc_18002A20A
0x18002a4ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a4d1  test    rcx, rcx
0x18002a4d4  jz      loc_18002A5B2
0x18002a4da  mov     rax, [rcx]
0x18002a4dd  mov     rax, [rax]
0x18002a4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4e5  test    rax, rax
0x18002a4e8  cmovnz  rbx, rax
0x18002a4ec  jmp     loc_18002A20A
0x18002a4f1  call    cs:__imp_GetLastError
0x18002a4f8  nop     dword ptr [rax+rax+00h]
0x18002a4fd  test    eax, eax
0x18002a4ff  jnz     loc_18002A312
0x18002a505  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a50c  test    rcx, rcx
0x18002a50f  jz      loc_18002A724
0x18002a515  mov     rax, [rcx]
0x18002a518  mov     rax, [rax]
0x18002a51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a520  test    rax, rax
0x18002a523  cmovnz  rbx, rax
0x18002a527  jmp     loc_18002A312
0x18002a52c  test    esi, esi
0x18002a52e  jns     loc_18002A28E
0x18002a534  jmp     loc_18002A2D0
0x18002a539  test    esi, esi
0x18002a53b  jns     loc_18002A400
0x18002a541  mov     rcx, [rbp+57h+var_68]
0x18002a545  mov     rax, [rcx]
0x18002a548  mov     rax, [rax+10h]
0x18002a54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a551  cmp     cs:byte_1800EACCB, 1
0x18002a558  jb      short loc_18002A580
0x18002a55a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a561  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
0x18002a568  mov     edx, 11h
0x18002a56d  mov     dword ptr [rsp+0B0h+var_90], esi
0x18002a571  mov     r9, r14
0x18002a574  mov     rcx, [rcx+88h]
0x18002a57b  call    WPP_SF_qD
0x18002a580  mov     rcx, [rbp+57h+var_70]
0x18002a584  mov     rax, [rcx]
0x18002a587  mov     rax, [rax+10h]
0x18002a58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a590  lea     rcx, [rbp+57h+arg_0]; this
0x18002a594  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002a599  jmp     loc_18002A371
0x18002a59e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002a5a3  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5aa  xor     r8d, r8d
0x18002a5ad  jmp     loc_18002A1C4
0x18002a5b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a5b9  nop     dword ptr [rax+rax+00h]
0x18002a5be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5c5  mov     rcx, rax
0x18002a5c8  test    rax, rax
0x18002a5cb  jz      short loc_18002A5EE
0x18002a5cd  mov     rax, [rax]
0x18002a5d0  mov     edx, 7F0h
0x18002a5d5  mov     rax, [rax+8]
0x18002a5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5de  test    eax, eax
0x18002a5e0  jz      short loc_18002A5EE
0x18002a5e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5e9  jmp     loc_18002A4DA
0x18002a5ee  lea     rcx, qword_1800EB130
0x18002a5f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5fc  jmp     loc_18002A4DA
0x18002a601  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a608  mov     r9, r14
0x18002a60b  mov     eax, [r15]
0x18002a60e  mov     [rsp+0B0h+var_80], eax
0x18002a612  mov     [rsp+0B0h+var_88], r12
0x18002a617  mov     rcx, [rcx+88h]
0x18002a61e  mov     [rsp+0B0h+var_90], r13
0x18002a623  call    WPP_SF_qqqD
0x18002a628  movzx   edx, cs:byte_1800EACCB
0x18002a62f  xor     r8d, r8d
0x18002a632  jmp     loc_18002A255
0x18002a637  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a63e  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
0x18002a645  mov     edx, 0Dh
0x18002a64a  mov     r9, r14
0x18002a64d  mov     rcx, [rcx+88h]
0x18002a654  call    WPP_SF_q
0x18002a659  jmp     loc_18002A3A6
0x18002a65e  cmp     cs:byte_1800EACCB, 1
0x18002a665  jb      loc_18002A52C
0x18002a66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a672  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
0x18002a679  mov     edx, 0Eh
0x18002a67e  mov     dword ptr [rsp+0B0h+var_90], esi
0x18002a682  mov     r9, r14
0x18002a685  mov     rcx, [rcx+88h]
0x18002a68c  call    WPP_SF_qD
0x18002a691  jmp     loc_18002A52C
0x18002a696  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a69d  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
0x18002a6a4  mov     edx, 0Fh
0x18002a6a9  mov     dword ptr [rsp+0B0h+var_90], ebx
0x18002a6ad  mov     r9, r14
0x18002a6b0  mov     rcx, [rcx+88h]
0x18002a6b7  call    WPP_SF_qD
0x18002a6bc  jmp     loc_18002A496
0x18002a6c1  cmp     cs:byte_1800EACCB, 1
0x18002a6c8  jb      loc_18002A539
0x18002a6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6d5  lea     r8, WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids
  ... truncated ...
```
