# CBufferSourceManager::Complete(CTStickyVal<int> *)

- ea: `0x180007f20`
- end: `0x1800084e3`
- name: `?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z`
- size: `1475`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001530`
- `0x1800036b0`
- `0x180006800`
- `0x1800098e0`
- `0x180009d98`
- `0x180029db0`
- `0x1800a2b70`
- `0x1800a8750`
- `0x1800a8cb0`
- `0x1800a8f30`
- `0x1800ae690`

## callees

- `0x180007f20`
- `0x1800084f0`
- `0x18002d514`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800876e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008041`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008041`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000812d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000812d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007f71`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008027`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800080c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008168`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007f71`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008027`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800080c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008168`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000832c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800083cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008445`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008494`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000832c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800083cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008445`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008494`

## string_xrefs

- `0x180007fa8`: `CBufferSourceManager::Complete`

## pseudocode

```c
__int64 __fastcall CBufferSourceManager::Complete(__int64 a1, __int64 a2)
{
  CallStackTracing *v4; // rbx
  char *v5; // rsi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // r14d
  CallStackTracing *v11; // rbx
  char *v12; // rsi
  DWORD v13; // ebp
  char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  CallStackTracing *v17; // rbx
  GUID *v18; // rdi
  DWORD v19; // esi
  GUID *v20; // rax
  int v21; // eax
  int v22; // eax
  CallStackTracing *v23; // rbx
  GUID *v24; // rdi
  DWORD v25; // esi
  GUID *v26; // rax
  int v27; // eax
  int v28; // eax
  CallStackTracing *v30; // rcx
  __int64 v31; // rax
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  CallStackTracing *v34; // rcx
  __int64 v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rax
  CallStackTracing *v41; // rax
  CallStackTracing *v42; // rax

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v5 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
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
        v5 = (char *)v31;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CBufferSourceManager::Complete";
      *(_DWORD *)&v5[8 * v9 + 8] = 663;
    }
    ++*((_DWORD *)v5 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x10u )
  {
    v39 = *(_QWORD *)(a1 + 96);
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      v39,
      (unsigned int)(*(_DWORD *)(a1 + 344) - v39),
      a1,
      *(_DWORD *)(a1 + 344) - v39,
      v39 + *(_DWORD *)(a1 + 336) - *(_DWORD *)(a1 + 344),
      v39 != 0);
  }
  if ( *(_QWORD *)(a1 + 96) )
  {
    v10 = CBufferSourceManager::CompleteCopyBuffer_((__int64 *)a1, a2);
    if ( v10 >= 0 )
    {
      *(_DWORD *)(a1 + 72) = 0;
      goto LABEL_14;
    }
  }
  else
  {
    v10 = -2147418113;
  }
  if ( byte_1800EACCB )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 28, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, a1, v10);
LABEL_14:
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v11 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v12 = (char *)CallStackTracing::s_wpInstance + 208;
    v13 = GetLastError();
    v14 = (char *)TlsGetValue(*((_DWORD *)v11 + 3));
    if ( v14 )
    {
      v12 = v14;
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
        v12 = (char *)v33;
    }
    SetLastError(v13);
    v15 = *((unsigned int *)v12 + 497);
    if ( (unsigned int)v15 < *((_DWORD *)v12 + 498) )
    {
      v16 = 2 * v15;
      *(_QWORD *)&v12[8 * v16] = "CBufferSourceManager::ResetForNext_";
      *(_DWORD *)&v12[8 * v16 + 8] = 146;
    }
    ++*((_DWORD *)v12 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, a1);
  v17 = CallStackTracing::s_wpInstance;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 28) = 0;
  *(_DWORD *)(a1 + 336) = 0;
  if ( *((_BYTE *)v17 + 8) )
  {
    v18 = (GUID *)((char *)v17 + 208);
    v19 = GetLastError();
    v20 = (GUID *)TlsGetValue(*((_DWORD *)v17 + 3));
    if ( v20 )
    {
      v18 = v20;
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
        v18 = (GUID *)v35;
    }
    SetLastError(v19);
    v21 = *(_DWORD *)&v18[124].Data2;
    if ( v21 )
    {
      v22 = v21 - 1;
      *(_DWORD *)&v18[124].Data2 = v22;
      if ( !v22 )
      {
        *(_DWORD *)&v18[124].Data2 = 0;
        *(_QWORD *)&v18[126].Data1 = 0;
        *(_DWORD *)&v18[124].Data4[4] = 0;
        v18[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v18[126].Data4 = 0;
        v18[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  v23 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v24 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v25 = GetLastError();
    v26 = (GUID *)TlsGetValue(*((_DWORD *)v23 + 3));
    if ( v26 )
    {
      v24 = v26;
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
        v24 = (GUID *)v37;
    }
    SetLastError(v25);
    v27 = *(_DWORD *)&v24[124].Data2;
    if ( v27 )
    {
      v28 = v27 - 1;
      *(_DWORD *)&v24[124].Data2 = v28;
      if ( !v28 )
      {
        *(_DWORD *)&v24[124].Data2 = 0;
        *(_QWORD *)&v24[126].Data1 = 0;
        *(_DWORD *)&v24[124].Data4[4] = 0;
        v24[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v24[126].Data4 = 0;
        v24[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007f20  mov     [rsp+arg_10], rbx
0x180007f25  push    rdi
0x180007f26  push    r14
0x180007f28  push    r15
0x180007f2a  sub     rsp, 40h
0x180007f2e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180007f36  mov     r14, rdx
0x180007f39  mov     rdi, rcx
0x180007f3c  jz      loc_180008322
0x180007f42  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180007f49  mov     [rsp+58h+arg_0], rbp
0x180007f4e  mov     [rsp+58h+arg_8], rsi
0x180007f53  cmp     byte ptr [rbx+8], 0
0x180007f57  jz      short loc_180007FC1
0x180007f59  lea     rsi, [rbx+0D0h]
0x180007f60  call    cs:__imp_GetLastError
0x180007f67  nop     dword ptr [rax+rax+00h]
0x180007f6c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180007f6f  mov     ebp, eax
0x180007f71  call    cs:__imp_TlsGetValue
0x180007f78  nop     dword ptr [rax+rax+00h]
0x180007f7d  test    rax, rax
0x180007f80  jz      loc_180008236
0x180007f86  mov     rsi, rax
0x180007f89  mov     ecx, ebp; dwErrCode
0x180007f8b  call    cs:__imp_SetLastError
0x180007f92  nop     dword ptr [rax+rax+00h]
0x180007f97  mov     eax, [rsi+7C4h]
0x180007f9d  cmp     eax, [rsi+7C8h]
0x180007fa3  jnb     short loc_180007FBB
0x180007fa5  add     rax, rax
0x180007fa8  lea     rcx, aCbuffersourcem_2; "CBufferSourceManager::Complete"
0x180007faf  mov     [rsi+rax*8], rcx
0x180007fb3  mov     dword ptr [rsi+rax*8+8], 297h
0x180007fbb  inc     dword ptr [rsi+7C4h]
0x180007fc1  xor     r15d, r15d
0x180007fc4  cmp     cs:byte_1800EACCB, 10h
0x180007fcb  jnb     loc_18000837B
0x180007fd1  cmp     [rdi+60h], r15
0x180007fd5  jz      loc_1800081F7
0x180007fdb  mov     rdx, r14
0x180007fde  mov     rcx, rdi
0x180007fe1  call    ?CompleteCopyBuffer_@CBufferSourceManager@@AEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::CompleteCopyBuffer_(CTStickyVal<int> *)
0x180007fe6  mov     r14d, eax
0x180007fe9  test    eax, eax
0x180007feb  js      loc_1800081FD
0x180007ff1  mov     [rdi+48h], r15d
0x180007ff5  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x180007ffc  jz      loc_1800083C5
0x180008002  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008009  cmp     [rbx+8], r15b
0x18000800d  jz      short loc_180008077
0x18000800f  lea     rsi, [rbx+0D0h]
0x180008016  call    cs:__imp_GetLastError
0x18000801d  nop     dword ptr [rax+rax+00h]
0x180008022  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180008025  mov     ebp, eax
0x180008027  call    cs:__imp_TlsGetValue
0x18000802e  nop     dword ptr [rax+rax+00h]
0x180008033  test    rax, rax
0x180008036  jz      loc_180008271
0x18000803c  mov     rsi, rax
0x18000803f  mov     ecx, ebp; dwErrCode
0x180008041  call    cs:__imp_SetLastError
0x180008048  nop     dword ptr [rax+rax+00h]
0x18000804d  mov     eax, [rsi+7C4h]
0x180008053  cmp     eax, [rsi+7C8h]
0x180008059  jnb     short loc_180008071
0x18000805b  add     rax, rax
0x18000805e  lea     rcx, aCbuffersourcem_0; "CBufferSourceManager::ResetForNext_"
0x180008065  mov     [rsi+rax*8], rcx
0x180008069  mov     dword ptr [rsi+rax*8+8], 92h
0x180008071  inc     dword ptr [rsi+7C4h]
0x180008077  mov     rbp, [rsp+58h+arg_0]
0x18000807c  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180008083  jnb     loc_18000841E
0x180008089  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008090  mov     [rdi+158h], r15
0x180008097  mov     [rdi+60h], r15
0x18000809b  mov     [rdi+1Ch], r15d
0x18000809f  mov     [rdi+150h], r15d
0x1800080a6  cmp     [rbx+8], r15b
0x1800080aa  jz      loc_18000813F
0x1800080b0  lea     rdi, [rbx+0D0h]
0x1800080b7  call    cs:__imp_GetLastError
0x1800080be  nop     dword ptr [rax+rax+00h]
0x1800080c3  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800080c6  mov     esi, eax
0x1800080c8  call    cs:__imp_TlsGetValue
0x1800080cf  nop     dword ptr [rax+rax+00h]
0x1800080d4  test    rax, rax
0x1800080d7  jz      loc_1800082AC
0x1800080dd  mov     rdi, rax
0x1800080e0  mov     ecx, esi; dwErrCode
0x1800080e2  call    cs:__imp_SetLastError
0x1800080e9  nop     dword ptr [rax+rax+00h]
0x1800080ee  mov     eax, [rdi+7C4h]
0x1800080f4  test    eax, eax
0x1800080f6  jz      short loc_18000813F
0x1800080f8  sub     eax, 1
0x1800080fb  mov     [rdi+7C4h], eax
0x180008101  jnz     short loc_18000813F
0x180008103  mov     [rdi+7C4h], r15d
0x18000810a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180008111  mov     [rdi+7E0h], r15
0x180008118  mov     [rdi+7CCh], r15d
0x18000811f  movups  xmmword ptr [rdi+7D0h], xmm0
0x180008126  mov     [rdi+7E8h], r15d
0x18000812d  call    cs:__imp_GetCurrentThreadId
0x180008134  nop     dword ptr [rax+rax+00h]
0x180008139  mov     [rdi+7C0h], eax
0x18000813f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008146  cmp     [rbx+8], r15b
0x18000814a  jz      loc_1800081DF
0x180008150  lea     rdi, [rbx+0D0h]
0x180008157  call    cs:__imp_GetLastError
0x18000815e  nop     dword ptr [rax+rax+00h]
0x180008163  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180008166  mov     esi, eax
0x180008168  call    cs:__imp_TlsGetValue
0x18000816f  nop     dword ptr [rax+rax+00h]
0x180008174  test    rax, rax
0x180008177  jz      loc_1800082E7
0x18000817d  mov     rdi, rax
0x180008180  mov     ecx, esi; dwErrCode
0x180008182  call    cs:__imp_SetLastError
0x180008189  nop     dword ptr [rax+rax+00h]
0x18000818e  mov     eax, [rdi+7C4h]
0x180008194  test    eax, eax
0x180008196  jz      short loc_1800081DF
0x180008198  sub     eax, 1
0x18000819b  mov     [rdi+7C4h], eax
0x1800081a1  jnz     short loc_1800081DF
0x1800081a3  mov     [rdi+7C4h], r15d
0x1800081aa  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800081b1  mov     [rdi+7E0h], r15
0x1800081b8  mov     [rdi+7CCh], r15d
0x1800081bf  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800081c6  mov     [rdi+7E8h], r15d
0x1800081cd  call    cs:__imp_GetCurrentThreadId
0x1800081d4  nop     dword ptr [rax+rax+00h]
0x1800081d9  mov     [rdi+7C0h], eax
0x1800081df  mov     rsi, [rsp+58h+arg_8]
0x1800081e4  mov     eax, r14d
0x1800081e7  mov     rbx, [rsp+58h+arg_10]
0x1800081ec  add     rsp, 40h
0x1800081f0  pop     r15
0x1800081f2  pop     r14
0x1800081f4  pop     rdi
0x1800081f5  retn
0x1800081f7  mov     r14d, 8000FFFFh
0x1800081fd  cmp     cs:byte_1800EACCB, 1
0x180008204  jb      loc_180007FF5
0x18000820a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008211  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x180008218  mov     edx, 1Ch
0x18000821d  mov     [rsp+58h+var_38], r14d
0x180008222  mov     r9, rdi
0x180008225  mov     rcx, [rcx+88h]
0x18000822c  call    WPP_SF_qD
0x180008231  jmp     loc_180007FF5
0x180008236  call    cs:__imp_GetLastError
0x18000823d  nop     dword ptr [rax+rax+00h]
0x180008242  test    eax, eax
0x180008244  jnz     loc_180007F89
0x18000824a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008251  test    rcx, rcx
0x180008254  jz      loc_18000832C
0x18000825a  mov     rax, [rcx]
0x18000825d  mov     rax, [rax]
0x180008260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008265  test    rax, rax
0x180008268  cmovnz  rsi, rax
0x18000826c  jmp     loc_180007F89
0x180008271  call    cs:__imp_GetLastError
0x180008278  nop     dword ptr [rax+rax+00h]
0x18000827d  test    eax, eax
0x18000827f  jnz     loc_18000803F
0x180008285  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000828c  test    rcx, rcx
0x18000828f  jz      loc_1800083CF
0x180008295  mov     rax, [rcx]
0x180008298  mov     rax, [rax]
0x18000829b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a0  test    rax, rax
0x1800082a3  cmovnz  rsi, rax
0x1800082a7  jmp     loc_18000803F
0x1800082ac  call    cs:__imp_GetLastError
0x1800082b3  nop     dword ptr [rax+rax+00h]
0x1800082b8  test    eax, eax
0x1800082ba  jnz     loc_1800080E0
0x1800082c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800082c7  test    rcx, rcx
0x1800082ca  jz      loc_180008445
0x1800082d0  mov     rax, [rcx]
0x1800082d3  mov     rax, [rax]
0x1800082d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082db  test    rax, rax
0x1800082de  cmovnz  rdi, rax
0x1800082e2  jmp     loc_1800080E0
0x1800082e7  call    cs:__imp_GetLastError
0x1800082ee  nop     dword ptr [rax+rax+00h]
0x1800082f3  test    eax, eax
0x1800082f5  jnz     loc_180008180
0x1800082fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008302  test    rcx, rcx
0x180008305  jz      loc_180008494
0x18000830b  mov     rax, [rcx]
0x18000830e  mov     rax, [rax]
0x180008311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008316  test    rax, rax
0x180008319  cmovnz  rdi, rax
0x18000831d  jmp     loc_180008180
0x180008322  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180008327  jmp     loc_180007F42
0x18000832c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180008333  nop     dword ptr [rax+rax+00h]
0x180008338  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000833f  mov     rcx, rax
0x180008342  test    rax, rax
0x180008345  jz      short loc_180008368
0x180008347  mov     rax, [rax]
0x18000834a  mov     edx, 7F0h
0x18000834f  mov     rax, [rax+8]
0x180008353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008358  test    eax, eax
0x18000835a  jz      short loc_180008368
0x18000835c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008363  jmp     loc_18000825A
0x180008368  lea     rcx, qword_1800EB130
0x18000836f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008376  jmp     loc_18000825A
0x18000837b  mov     rdx, [rdi+60h]
0x18000837f  mov     ecx, r15d
0x180008382  mov     r8d, [rdi+158h]
0x180008389  test    rdx, rdx
0x18000838c  mov     eax, [rdi+150h]
0x180008392  mov     r9, rdi
0x180008395  setnz   cl
0x180008398  sub     eax, r8d
0x18000839b  mov     [rsp+58h+var_28], ecx
0x18000839f  add     eax, edx
0x1800083a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083a8  sub     r8d, edx
0x1800083ab  mov     [rsp+58h+var_30], eax
0x1800083af  mov     [rsp+58h+var_38], r8d
0x1800083b4  mov     rcx, [rcx+88h]
0x1800083bb  call    WPP_SF_qddd
0x1800083c0  jmp     loc_180007FD1
0x1800083c5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800083ca  jmp     loc_180008002
0x1800083cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800083d6  nop     dword ptr [rax+rax+00h]
0x1800083db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800083e2  mov     rcx, rax
0x1800083e5  test    rax, rax
0x1800083e8  jz      short loc_18000840B
0x1800083ea  mov     rax, [rax]
0x1800083ed  mov     edx, 7F0h
0x1800083f2  mov     rax, [rax+8]
0x1800083f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083fb  test    eax, eax
0x1800083fd  jz      short loc_18000840B
0x1800083ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008406  jmp     loc_180008295
0x18000840b  lea     rcx, qword_1800EB130
0x180008412  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008419  jmp     loc_180008295
0x18000841e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008425  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18000842c  mov     edx, 0Ah
0x180008431  mov     r9, rdi
0x180008434  mov     rcx, [rcx+88h]
0x18000843b  call    WPP_SF_q
0x180008440  jmp     loc_180008089
0x180008445  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000844c  nop     dword ptr [rax+rax+00h]
0x180008451  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180008458  mov     rcx, rax
0x18000845b  test    rax, rax
0x18000845e  jz      short loc_180008481
0x180008460  mov     rax, [rax]
0x180008463  mov     edx, 7F0h
0x180008468  mov     rax, [rax+8]
0x18000846c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008471  test    eax, eax
0x180008473  jz      short loc_180008481
0x180008475  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000847c  jmp     loc_1800082D0
0x180008481  lea     rcx, qword_1800EB130
0x180008488  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000848f  jmp     loc_1800082D0
0x180008494  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000849b  nop     dword ptr [rax+rax+00h]
0x1800084a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800084a7  mov     rcx, rax
0x1800084aa  test    rax, rax
0x1800084ad  jz      short loc_1800084D0
0x1800084af  mov     rax, [rax]
0x1800084b2  mov     edx, 7F0h
  ... truncated ...
```
