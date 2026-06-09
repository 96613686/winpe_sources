# CCopyFrameParser::CopyFrameBytes(uchar *,int)

- ea: `0x18000a4e0`
- end: `0x18000aa6c`
- name: `?CopyFrameBytes@CCopyFrameParser@@IEAAHPEAEH@Z`
- size: `1420`
- prototype: `__int64 __fastcall(CCopyFrameParser *this, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180009d98`
- `0x180029db0`
- `0x1800a8cb0`

## callees

- `0x180002820`
- `0x1800052c0`
- `0x18000a4e0`
- `0x18002d514`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a552`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a68c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a73d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a552`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a68c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a73d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a874`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a788`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a538`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a5c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a672`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a723`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a538`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a5c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a672`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a8c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a958`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a9ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000aa1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a8c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a958`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a9ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000aa1d`

## string_xrefs

- `0x18000a5fe`: `CBufferSourceManager::CopyBlock`
- `0x18000a576`: `CCopyFrameParser::CopyFrameBytes`

## pseudocode

```c
__int64 __fastcall CCopyFrameParser::CopyFrameBytes(CCopyFrameParser *this, unsigned __int8 *a2, unsigned int a3)
{
  CallStackTracing *v3; // rbx
  char *v7; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  char *v12; // rsi
  char *v13; // rdi
  DWORD v14; // ebp
  char *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // eax
  CallStackTracing *v19; // rbx
  unsigned int v20; // ebp
  GUID *v21; // rdi
  DWORD v22; // esi
  GUID *v23; // rax
  int v24; // eax
  int v25; // eax
  GUID *v26; // rdi
  DWORD v27; // esi
  GUID *v28; // rax
  int v29; // eax
  int v30; // eax
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  CallStackTracing *v34; // rcx
  __int64 v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  CallStackTracing *v40; // rax
  CallStackTracing *v41; // rax
  CallStackTracing *v42; // rax
  CallStackTracing *v43; // rax
  char v44; // [rsp+60h] [rbp+8h] BYREF
  int v45; // [rsp+78h] [rbp+20h] BYREF

  v3 = CallStackTracing::s_wpInstance;
  v45 = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v7 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
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
        v7 = (char *)v33;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    v3 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CCopyFrameParser::CopyFrameBytes";
      *(_DWORD *)&v7[8 * v11 + 8] = 1092;
    }
    ++*((_DWORD *)v7 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 17), 42, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, this, a2, a3);
    v3 = CallStackTracing::s_wpInstance;
  }
  v12 = (char *)this + 48;
  if ( !v3 )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v13 = (char *)v3 + 208;
    v14 = GetLastError();
    v15 = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( v15 )
    {
      v13 = v15;
    }
    else if ( !GetLastError() )
    {
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v35 = (**(__int64 (__fastcall ***)(CallStackTracing *))v34)(v34);
      if ( v35 )
        v13 = (char *)v35;
    }
    SetLastError(v14);
    v16 = *((unsigned int *)v13 + 497);
    if ( (unsigned int)v16 < *((_DWORD *)v13 + 498) )
    {
      v17 = 2 * v16;
      *(_QWORD *)&v13[8 * v17] = "CBufferSourceManager::CopyBlock";
      *(_DWORD *)&v13[8 * v17 + 8] = 695;
    }
    ++*((_DWORD *)v13 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 29, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, v12);
  if ( !*((_QWORD *)v12 + 12) )
  {
    v45 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
    v20 = 0;
    goto LABEL_28;
  }
  v18 = (**(__int64 (__fastcall ***)(char *, unsigned __int8 *, _QWORD, int *))v12)(v12, a2, a3, &v45);
  v19 = CallStackTracing::s_wpInstance;
  v20 = v18;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v21 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v22 = GetLastError();
    v23 = (GUID *)TlsGetValue(*((_DWORD *)v19 + 3));
    if ( v23 )
    {
      v21 = v23;
    }
    else if ( !GetLastError() )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v36 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v37 = (**(__int64 (__fastcall ***)(CallStackTracing *))v36)(v36);
      if ( v37 )
        v21 = (GUID *)v37;
    }
    SetLastError(v22);
    v24 = *(_DWORD *)&v21[124].Data2;
    v19 = CallStackTracing::s_wpInstance;
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
LABEL_28:
        v19 = CallStackTracing::s_wpInstance;
      }
    }
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    v26 = (GUID *)((char *)v19 + 208);
    v27 = GetLastError();
    v28 = (GUID *)TlsGetValue(*((_DWORD *)v19 + 3));
    if ( v28 )
    {
      v26 = v28;
    }
    else if ( !GetLastError() )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v38)(v38);
      if ( v39 )
        v26 = (GUID *)v39;
    }
    SetLastError(v27);
    v29 = *(_DWORD *)&v26[124].Data2;
    if ( v29 )
    {
      v30 = v29 - 1;
      *(_DWORD *)&v26[124].Data2 = v30;
      if ( !v30 )
      {
        *(_DWORD *)&v26[124].Data2 = 0;
        *(_QWORD *)&v26[126].Data1 = 0;
        *(_DWORD *)&v26[124].Data4[4] = 0;
        v26[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v26[126].Data4 = 0;
        v26[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v20;
}

```

## disassembly

```asm
0x18000a4e0  push    rbx
0x18000a4e2  push    rbp
0x18000a4e3  push    rsi
0x18000a4e4  push    r12
0x18000a4e6  sub     rsp, 38h
0x18000a4ea  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a4f1  xor     r12d, r12d
0x18000a4f4  mov     [rsp+58h+arg_10], r14
0x18000a4f9  mov     r14d, r8d
0x18000a4fc  mov     [rsp+58h+var_28], r15
0x18000a501  mov     r15, rdx
0x18000a504  mov     [rsp+58h+arg_18], r12d
0x18000a509  mov     rbp, rcx
0x18000a50c  test    rbx, rbx
0x18000a50f  jz      loc_18000A8AF
0x18000a515  mov     [rsp+58h+arg_8], rdi
0x18000a51a  cmp     [rbx+8], r12b
0x18000a51e  jz      short loc_18000A58F
0x18000a520  lea     rdi, [rbx+0D0h]
0x18000a527  call    cs:__imp_GetLastError
0x18000a52e  nop     dword ptr [rax+rax+00h]
0x18000a533  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18000a536  mov     esi, eax
0x18000a538  call    cs:__imp_TlsGetValue
0x18000a53f  nop     dword ptr [rax+rax+00h]
0x18000a544  test    rax, rax
0x18000a547  jz      loc_18000A7C3
0x18000a54d  mov     rdi, rax
0x18000a550  mov     ecx, esi; dwErrCode
0x18000a552  call    cs:__imp_SetLastError
0x18000a559  nop     dword ptr [rax+rax+00h]
0x18000a55e  mov     eax, [rdi+7C4h]
0x18000a564  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a56b  cmp     eax, [rdi+7C8h]
0x18000a571  jnb     short loc_18000A589
0x18000a573  add     rax, rax
0x18000a576  lea     rcx, aCcopyframepars_2; "CCopyFrameParser::CopyFrameBytes"
0x18000a57d  mov     [rdi+rax*8], rcx
0x18000a581  mov     dword ptr [rdi+rax*8+8], 444h
0x18000a589  inc     dword ptr [rdi+7C4h]
0x18000a58f  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000a596  jnb     loc_18000A90F
0x18000a59c  lea     rsi, [rbp+30h]
0x18000a5a0  test    rbx, rbx
0x18000a5a3  jz      loc_18000A947
0x18000a5a9  cmp     [rbx+8], r12b
0x18000a5ad  jz      short loc_18000A617
0x18000a5af  lea     rdi, [rbx+0D0h]
0x18000a5b6  call    cs:__imp_GetLastError
0x18000a5bd  nop     dword ptr [rax+rax+00h]
0x18000a5c2  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18000a5c5  mov     ebp, eax
0x18000a5c7  call    cs:__imp_TlsGetValue
0x18000a5ce  nop     dword ptr [rax+rax+00h]
0x18000a5d3  test    rax, rax
0x18000a5d6  jz      loc_18000A7FE
0x18000a5dc  mov     rdi, rax
0x18000a5df  mov     ecx, ebp; dwErrCode
0x18000a5e1  call    cs:__imp_SetLastError
0x18000a5e8  nop     dword ptr [rax+rax+00h]
0x18000a5ed  mov     eax, [rdi+7C4h]
0x18000a5f3  cmp     eax, [rdi+7C8h]
0x18000a5f9  jnb     short loc_18000A611
0x18000a5fb  add     rax, rax
0x18000a5fe  lea     rcx, aCbuffersourcem_1; "CBufferSourceManager::CopyBlock"
0x18000a605  mov     [rdi+rax*8], rcx
0x18000a609  mov     dword ptr [rdi+rax*8+8], 2B7h
0x18000a611  inc     dword ptr [rdi+7C4h]
0x18000a617  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18000a61e  jnb     loc_18000A9A7
0x18000a624  cmp     [rsi+60h], r12
0x18000a628  jz      loc_18000A7AC
0x18000a62e  mov     rax, [rsi]
0x18000a631  lea     r9, [rsp+58h+arg_18]
0x18000a636  mov     r8d, r14d
0x18000a639  mov     rdx, r15
0x18000a63c  mov     rcx, rsi
0x18000a63f  mov     rax, [rax]
0x18000a642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a647  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a64e  mov     ebp, eax
0x18000a650  cmp     [rbx+8], r12b
0x18000a654  jz      loc_18000A6F7
0x18000a65a  lea     rdi, [rbx+0D0h]
0x18000a661  call    cs:__imp_GetLastError
0x18000a668  nop     dword ptr [rax+rax+00h]
0x18000a66d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18000a670  mov     esi, eax
0x18000a672  call    cs:__imp_TlsGetValue
0x18000a679  nop     dword ptr [rax+rax+00h]
0x18000a67e  test    rax, rax
0x18000a681  jz      loc_18000A839
0x18000a687  mov     rdi, rax
0x18000a68a  mov     ecx, esi; dwErrCode
0x18000a68c  call    cs:__imp_SetLastError
0x18000a693  nop     dword ptr [rax+rax+00h]
0x18000a698  mov     eax, [rdi+7C4h]
0x18000a69e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a6a5  test    eax, eax
0x18000a6a7  jz      short loc_18000A6F7
0x18000a6a9  sub     eax, 1
0x18000a6ac  mov     [rdi+7C4h], eax
0x18000a6b2  jnz     short loc_18000A6F7
0x18000a6b4  mov     [rdi+7C4h], r12d
0x18000a6bb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000a6c2  mov     [rdi+7E0h], r12
0x18000a6c9  mov     [rdi+7CCh], r12d
0x18000a6d0  movups  xmmword ptr [rdi+7D0h], xmm0
0x18000a6d7  mov     [rdi+7E8h], r12d
0x18000a6de  call    cs:__imp_GetCurrentThreadId
0x18000a6e5  nop     dword ptr [rax+rax+00h]
0x18000a6ea  mov     [rdi+7C0h], eax
0x18000a6f0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a6f7  mov     r15, [rsp+58h+var_28]
0x18000a6fc  mov     r14, [rsp+58h+arg_10]
0x18000a701  cmp     [rbx+8], r12b
0x18000a705  jz      loc_18000A79A
0x18000a70b  lea     rdi, [rbx+0D0h]
0x18000a712  call    cs:__imp_GetLastError
0x18000a719  nop     dword ptr [rax+rax+00h]
0x18000a71e  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18000a721  mov     esi, eax
0x18000a723  call    cs:__imp_TlsGetValue
0x18000a72a  nop     dword ptr [rax+rax+00h]
0x18000a72f  test    rax, rax
0x18000a732  jz      loc_18000A874
0x18000a738  mov     rdi, rax
0x18000a73b  mov     ecx, esi; dwErrCode
0x18000a73d  call    cs:__imp_SetLastError
0x18000a744  nop     dword ptr [rax+rax+00h]
0x18000a749  mov     eax, [rdi+7C4h]
0x18000a74f  test    eax, eax
0x18000a751  jz      short loc_18000A79A
0x18000a753  sub     eax, 1
0x18000a756  mov     [rdi+7C4h], eax
0x18000a75c  jnz     short loc_18000A79A
0x18000a75e  mov     [rdi+7C4h], r12d
0x18000a765  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000a76c  mov     [rdi+7E0h], r12
0x18000a773  mov     [rdi+7CCh], r12d
0x18000a77a  movups  xmmword ptr [rdi+7D0h], xmm0
0x18000a781  mov     [rdi+7E8h], r12d
0x18000a788  call    cs:__imp_GetCurrentThreadId
0x18000a78f  nop     dword ptr [rax+rax+00h]
0x18000a794  mov     [rdi+7C0h], eax
0x18000a79a  mov     rdi, [rsp+58h+arg_8]
0x18000a79f  mov     eax, ebp
0x18000a7a1  add     rsp, 38h
0x18000a7a5  pop     r12
0x18000a7a7  pop     rsi
0x18000a7a8  pop     rbp
0x18000a7a9  pop     rbx
0x18000a7aa  retn
0x18000a7ac  lea     rcx, [rsp+58h+arg_0]; this
0x18000a7b1  mov     [rsp+58h+arg_18], r12d
0x18000a7b6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000a7bb  mov     ebp, r12d
0x18000a7be  jmp     loc_18000A6F0
0x18000a7c3  call    cs:__imp_GetLastError
0x18000a7ca  nop     dword ptr [rax+rax+00h]
0x18000a7cf  test    eax, eax
0x18000a7d1  jnz     loc_18000A550
0x18000a7d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a7de  test    rcx, rcx
0x18000a7e1  jz      loc_18000A8C0
0x18000a7e7  mov     rax, [rcx]
0x18000a7ea  mov     rax, [rax]
0x18000a7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f2  test    rax, rax
0x18000a7f5  cmovnz  rdi, rax
0x18000a7f9  jmp     loc_18000A550
0x18000a7fe  call    cs:__imp_GetLastError
0x18000a805  nop     dword ptr [rax+rax+00h]
0x18000a80a  test    eax, eax
0x18000a80c  jnz     loc_18000A5DF
0x18000a812  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a819  test    rcx, rcx
0x18000a81c  jz      loc_18000A958
0x18000a822  mov     rax, [rcx]
0x18000a825  mov     rax, [rax]
0x18000a828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a82d  test    rax, rax
0x18000a830  cmovnz  rdi, rax
0x18000a834  jmp     loc_18000A5DF
0x18000a839  call    cs:__imp_GetLastError
0x18000a840  nop     dword ptr [rax+rax+00h]
0x18000a845  test    eax, eax
0x18000a847  jnz     loc_18000A68A
0x18000a84d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a854  test    rcx, rcx
0x18000a857  jz      loc_18000A9CE
0x18000a85d  mov     rax, [rcx]
0x18000a860  mov     rax, [rax]
0x18000a863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a868  test    rax, rax
0x18000a86b  cmovnz  rdi, rax
0x18000a86f  jmp     loc_18000A68A
0x18000a874  call    cs:__imp_GetLastError
0x18000a87b  nop     dword ptr [rax+rax+00h]
0x18000a880  test    eax, eax
0x18000a882  jnz     loc_18000A73B
0x18000a888  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a88f  test    rcx, rcx
0x18000a892  jz      loc_18000AA1D
0x18000a898  mov     rax, [rcx]
0x18000a89b  mov     rax, [rax]
0x18000a89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8a3  test    rax, rax
0x18000a8a6  cmovnz  rdi, rax
0x18000a8aa  jmp     loc_18000A73B
0x18000a8af  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000a8b4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a8bb  jmp     loc_18000A515
0x18000a8c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a8c7  nop     dword ptr [rax+rax+00h]
0x18000a8cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a8d3  mov     rcx, rax
0x18000a8d6  test    rax, rax
0x18000a8d9  jz      short loc_18000A8FC
0x18000a8db  mov     rax, [rax]
0x18000a8de  mov     edx, 7F0h
0x18000a8e3  mov     rax, [rax+8]
0x18000a8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ec  test    eax, eax
0x18000a8ee  jz      short loc_18000A8FC
0x18000a8f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a8f7  jmp     loc_18000A7E7
0x18000a8fc  lea     rcx, qword_1800EB130
0x18000a903  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a90a  jmp     loc_18000A7E7
0x18000a90f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a916  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18000a91d  mov     edx, 2Ah ; '*'
0x18000a922  mov     [rsp+58h+var_30], r14d
0x18000a927  mov     r9, rbp
0x18000a92a  mov     [rsp+58h+var_38], r15
0x18000a92f  mov     rcx, [rcx+88h]
0x18000a936  call    WPP_SF_qqD
0x18000a93b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a942  jmp     loc_18000A59C
0x18000a947  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000a94c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a953  jmp     loc_18000A5A9
0x18000a958  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a95f  nop     dword ptr [rax+rax+00h]
0x18000a964  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a96b  mov     rcx, rax
0x18000a96e  test    rax, rax
0x18000a971  jz      short loc_18000A994
0x18000a973  mov     rax, [rax]
0x18000a976  mov     edx, 7F0h
0x18000a97b  mov     rax, [rax+8]
0x18000a97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a984  test    eax, eax
0x18000a986  jz      short loc_18000A994
0x18000a988  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a98f  jmp     loc_18000A822
0x18000a994  lea     rcx, qword_1800EB130
0x18000a99b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a9a2  jmp     loc_18000A822
0x18000a9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9ae  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18000a9b5  mov     edx, 1Dh
0x18000a9ba  mov     r9, rsi
0x18000a9bd  mov     rcx, [rcx+88h]
0x18000a9c4  call    WPP_SF_q
0x18000a9c9  jmp     loc_18000A624
0x18000a9ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a9d5  nop     dword ptr [rax+rax+00h]
0x18000a9da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a9e1  mov     rcx, rax
0x18000a9e4  test    rax, rax
0x18000a9e7  jz      short loc_18000AA0A
0x18000a9e9  mov     rax, [rax]
0x18000a9ec  mov     edx, 7F0h
0x18000a9f1  mov     rax, [rax+8]
0x18000a9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9fa  test    eax, eax
0x18000a9fc  jz      short loc_18000AA0A
0x18000a9fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa05  jmp     loc_18000A85D
0x18000aa0a  lea     rcx, qword_1800EB130
0x18000aa11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa18  jmp     loc_18000A85D
0x18000aa1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000aa24  nop     dword ptr [rax+rax+00h]
0x18000aa29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa30  mov     rcx, rax
0x18000aa33  test    rax, rax
0x18000aa36  jz      short loc_18000AA59
0x18000aa38  mov     rax, [rax]
0x18000aa3b  mov     edx, 7F0h
0x18000aa40  mov     rax, [rax+8]
0x18000aa44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa49  test    eax, eax
0x18000aa4b  jz      short loc_18000AA59
0x18000aa4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000aa54  jmp     loc_18000A898
0x18000aa59  lea     rcx, qword_1800EB130
0x18000aa60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
