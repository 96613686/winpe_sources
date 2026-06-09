# CTransportStreamMapper::Process(IMediaSample *,uchar *,int,CRefCountedCritSec *)

- ea: `0x180017b70`
- end: `0x180018212`
- name: `?Process@CTransportStreamMapper@@UEAAJPEAUIMediaSample@@PEAEHPEAVCRefCountedCritSec@@@Z`
- size: `1698`
- prototype: `__int64 __fastcall(CTransportStreamMapper *this, struct IMediaSample *, unsigned __int8 *, int, struct _RTL_CRITICAL_SECTION *lpCriticalSection)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180002820`
- `0x1800052c0`
- `0x1800140b0`
- `0x180017b70`
- `0x180018220`
- `0x180019100`
- `0x180019140`
- `0x180051ce4`
- `0x180053b10`
- `0x180074a12`
- `0x18007c8e8`
- `0x1800b1780`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017ff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017ff0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001800c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001800c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017da6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017bef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001801d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001801d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018088`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017df1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017bd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017d8c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017bd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017d8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800180d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800181c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800180d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800181c3`

## pseudocode

```c
__int64 __fastcall CTransportStreamMapper::Process(
        CTransportStreamMapper *this,
        struct IMediaSample *a2,
        unsigned __int8 *a3,
        int a4,
        struct _RTL_CRITICAL_SECTION *lpCriticalSection)
{
  int v5; // edi
  unsigned __int8 *v6; // rsi
  CallStackTracing *v7; // r14
  int v8; // r12d
  char *v10; // rbp
  DWORD LastError; // r15d
  char *Value; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  _DWORD *v15; // r14
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  DWORD TickCount; // esi
  CallStackTracing *v24; // rdi
  GUID *v25; // rbx
  DWORD v26; // esi
  GUID *v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v31; // rcx
  char *v32; // rcx
  char *v33; // rdx
  int v34; // r15d
  __int64 v35; // r8
  int v36; // ecx
  CallStackTracing *v37; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  CTransportStreamMapper *v41; // rbp
  void *v42; // rcx
  CParserRef *v43; // rdi
  __int64 *v44; // rcx
  __int64 v45; // rax
  __int64 *v46; // rcx
  __int64 v47; // rax
  CallStackTracing *v48; // rax
  int v49; // eax
  CallStackTracing *v50; // rax
  unsigned __int8 *v51; // [rsp+80h] [rbp+18h] BYREF
  int v52; // [rsp+88h] [rbp+20h] BYREF

  v52 = a4;
  v51 = a3;
  v5 = a4;
  v6 = a3;
  v7 = CallStackTracing::s_wpInstance;
  v8 = (int)a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v7 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v7 + 8) )
  {
    v10 = (char *)v7 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
    if ( Value )
    {
      v10 = Value;
    }
    else if ( !GetLastError() )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v45 = (*(__int64 (__fastcall **)(__int64 *))*v44)(v44);
      if ( v45 )
        v10 = (char *)v45;
    }
    SetLastError(LastError);
    v13 = *((unsigned int *)v10 + 497);
    if ( (unsigned int)v13 < *((_DWORD *)v10 + 498) )
    {
      v14 = 2 * v13;
      *(_QWORD *)&v10[8 * v14] = "CTransportStreamMapper::Process";
      *(_DWORD *)&v10[8 * v14 + 8] = 448;
    }
    ++*((_DWORD *)v10 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 17), 24, &WPP_db22ba5164493dcbd331695ea6183974_Traceguids, this, v6, v5);
  v15 = (_DWORD *)((char *)this + 72);
  while ( v5 > 0 )
  {
    v16 = *((_DWORD *)this + 20);
    if ( v16 )
    {
      v36 = v16 - 1;
      if ( v36 )
      {
        if ( v36 != 1 )
          goto LABEL_26;
        goto LABEL_22;
      }
    }
    else
    {
      v17 = *((_DWORD *)this + 22);
      v18 = v17;
      if ( v5 < v17 )
        v18 = v5;
      v19 = v17 - v18;
      v5 -= v18;
      v6 += v18;
      *((_DWORD *)this + 22) = v19;
      v52 = v5;
      v51 = v6;
      if ( v19 > 0 )
        goto LABEL_26;
      *((_DWORD *)this + 20) = 1;
      if ( !v5 )
        goto LABEL_26;
    }
    if ( *((_QWORD *)this + 1552) != *((_QWORD *)this + 1551) )
    {
      v31 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL);
      if ( v31 )
        ++*(_QWORD *)(v31 + 280);
      v32 = (char *)*((_QWORD *)this + 1552);
      v33 = &v32[-*((_QWORD *)this + 1551)];
      v34 = 188 - (_DWORD)v33;
      if ( 188 - (__int64)v33 >= (unsigned __int64)v5 )
        v34 = v5;
      if ( v34 < (unsigned __int64)&v32[v34] && (unsigned __int64)v34 <= *((_QWORD *)this + 1553) - (_QWORD)v33 )
      {
        memcpy_0(v32, v6, v34);
        *((_QWORD *)this + 1552) += v34;
        v32 = (char *)*((_QWORD *)this + 1552);
      }
      v35 = *((_QWORD *)this + 1551);
      v6 += v34;
      v5 -= v34;
      v51 = v6;
      v52 = v5;
      if ( &v32[-v35] != (char *)188 )
        goto LABEL_26;
      *((_DWORD *)this + 19) = 0;
      CTransportStreamMapper::ProcessTSPacket_((_DWORD)this, v8, v35, -v5, (__int64)this + 72);
      *((_QWORD *)this + 1552) = *((_QWORD *)this + 1551);
      goto LABEL_21;
    }
    if ( *v6 == 71 )
      goto LABEL_19;
    v49 = CTransportStreamMapper::SeekSyncByte_(this, &v51, &v52);
    v6 = v51;
    if ( v49 )
    {
      v5 = v52;
LABEL_19:
      if ( v5 < 188 )
      {
        v42 = (void *)*((_QWORD *)this + 1552);
        if ( v5 < (unsigned __int64)v42 + v5
          && (unsigned __int64)v5 <= *((_QWORD *)this + 1551) + *((_QWORD *)this + 1553) - (_QWORD)v42 )
        {
          memcpy_0(v42, v6, v5);
          *((_QWORD *)this + 1552) += v5;
        }
        v6 += v5;
        v52 = 0;
        v51 = v6;
        v5 = 0;
        goto LABEL_26;
      }
      *((_DWORD *)this + 19) = 0;
      CTransportStreamMapper::ProcessTSPacket_((_DWORD)this, v8, (_DWORD)v6, 188 - v5, (__int64)this + 72);
      v6 += 188;
      v5 -= 188;
LABEL_21:
      *((_DWORD *)this + 20) = 2;
LABEL_22:
      v20 = *((_DWORD *)this + 24);
      v21 = v20;
      if ( v5 < v20 )
        v21 = v5;
      v22 = v20 - v21;
      v5 -= v21;
      v6 += v21;
      *((_DWORD *)this + 24) = v22;
      v52 = v5;
      v51 = v6;
      if ( v22 )
        goto LABEL_26;
      goto LABEL_25;
    }
    v5 = 0;
    v6 = &v51[v52];
    v52 = 0;
    v51 = v6;
LABEL_25:
    *((_DWORD *)this + 22) = *((_DWORD *)this + 21);
    *((_DWORD *)this + 24) = *((_DWORD *)this + 23);
    *((_DWORD *)this + 20) = 0;
LABEL_26:
    if ( *((_DWORD *)this + 19) == *v15 )
    {
      LeaveCriticalSection(lpCriticalSection);
      CStreamMapper::ParserInstructedReset_(this);
      EnterCriticalSection(lpCriticalSection);
    }
  }
  TickCount = GetTickCount();
  if ( TickCount - *((_DWORD *)this + 10) > *((_DWORD *)this + 9) )
  {
    v37 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v37 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v37);
      v39 = *((unsigned int *)ThreadRelativeContext + 497);
      if ( (unsigned int)v39 < *((_DWORD *)ThreadRelativeContext + 498) )
      {
        v40 = 2 * v39;
        *((_QWORD *)ThreadRelativeContext + v40) = "CStreamMapper::CheckForTimeouts_";
        *((_DWORD *)ThreadRelativeContext + 2 * v40 + 2) = 182;
      }
      ++*((_DWORD *)ThreadRelativeContext + 497);
    }
    if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        16,
        &WPP_db22ba5164493dcbd331695ea6183974_Traceguids,
        this,
        TickCount - *((_DWORD *)this + 10));
    v41 = (CTransportStreamMapper *)*((_QWORD *)this + 2);
    while ( v41 != (CTransportStreamMapper *)((char *)this + 16) )
    {
      if ( *((_DWORD *)this + 19) == *v15 )
        break;
      v43 = (CTransportStreamMapper *)((char *)v41 - 16);
      _InterlockedIncrement((volatile signed __int32 *)v41 - 4);
      CDemuxBaseParser::CheckTimeout(*((_QWORD *)v41 - 1), TickCount, (char *)this + 72);
      v41 = *(CTransportStreamMapper **)v41;
      CParserRef::Release(v43);
    }
    *((_DWORD *)this + 10) = TickCount;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v52);
  }
  v24 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v25 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v26 = GetLastError();
    v27 = (GUID *)TlsGetValue(*((_DWORD *)v24 + 3));
    if ( v27 )
    {
      v25 = v27;
    }
    else if ( !GetLastError() )
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v47 = (*(__int64 (__fastcall **)(__int64 *))*v46)(v46);
      if ( v47 )
        v25 = (GUID *)v47;
    }
    SetLastError(v26);
    v28 = *(_DWORD *)&v25[124].Data2;
    if ( v28 )
    {
      v29 = v28 - 1;
      *(_DWORD *)&v25[124].Data2 = v29;
      if ( !v29 )
      {
        *(_DWORD *)&v25[124].Data2 = 0;
        *(_QWORD *)&v25[126].Data1 = 0;
        *(_DWORD *)&v25[124].Data4[4] = 0;
        v25[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v25[126].Data4 = 0;
        v25[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017b70  mov     [rsp+arg_18], r9d
0x180017b75  mov     [rsp+arg_10], r8
0x180017b7a  push    rbx
0x180017b7b  push    rsi
0x180017b7c  push    rdi
0x180017b7d  push    r13
0x180017b7f  sub     rsp, 48h
0x180017b83  mov     [rsp+68h+var_28], r12
0x180017b88  mov     edi, r9d
0x180017b8b  mov     [rsp+68h+var_30], r14
0x180017b90  mov     rsi, r8
0x180017b93  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017b9a  mov     r12, rdx
0x180017b9d  mov     rbx, rcx
0x180017ba0  test    r14, r14
0x180017ba3  jz      loc_1800180C3
0x180017ba9  cmp     byte ptr [r14+8], 0
0x180017bae  mov     [rsp+68h+arg_0], rbp
0x180017bb3  mov     [rsp+68h+var_38], r15
0x180017bb8  jz      short loc_180017C26
0x180017bba  lea     rbp, [r14+0D0h]
0x180017bc1  call    cs:__imp_GetLastError
0x180017bc8  nop     dword ptr [rax+rax+00h]
0x180017bcd  mov     ecx, [r14+0Ch]; dwTlsIndex
0x180017bd1  mov     r15d, eax
0x180017bd4  call    cs:__imp_TlsGetValue
0x180017bdb  nop     dword ptr [rax+rax+00h]
0x180017be0  test    rax, rax
0x180017be3  jz      loc_18001801D
0x180017be9  mov     rbp, rax
0x180017bec  mov     ecx, r15d; dwErrCode
0x180017bef  call    cs:__imp_SetLastError
0x180017bf6  nop     dword ptr [rax+rax+00h]
0x180017bfb  mov     eax, [rbp+7C4h]
0x180017c01  cmp     eax, [rbp+7C8h]
0x180017c07  jnb     short loc_180017C20
0x180017c09  add     rax, rax
0x180017c0c  lea     rcx, aCtransportstre_2; "CTransportStreamMapper::Process"
0x180017c13  mov     [rbp+rax*8+0], rcx
0x180017c18  mov     dword ptr [rbp+rax*8+8], 1C0h
0x180017c20  inc     dword ptr [rbp+7C4h]
0x180017c26  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180017c2d  jnb     loc_180018058
0x180017c33  xor     r13d, r13d
0x180017c36  lea     r14, [rbx+48h]
0x180017c3a  test    edi, edi
0x180017c3c  jle     loc_180017D33
0x180017c42  mov     ecx, [rbx+50h]
0x180017c45  test    ecx, ecx
0x180017c47  jnz     loc_180017ED2
0x180017c4d  mov     ecx, [rbx+58h]
0x180017c50  cmp     edi, ecx
0x180017c52  mov     eax, ecx
0x180017c54  cmovl   eax, edi
0x180017c57  sub     ecx, eax
0x180017c59  sub     edi, eax
0x180017c5b  cdqe
0x180017c5d  add     rsi, rax
0x180017c60  mov     [rbx+58h], ecx
0x180017c63  mov     [rsp+68h+arg_18], edi
0x180017c6a  mov     [rsp+68h+arg_10], rsi
0x180017c72  test    ecx, ecx
0x180017c74  jg      loc_180017D1F
0x180017c7a  mov     dword ptr [rbx+50h], 1
0x180017c81  test    edi, edi
0x180017c83  jz      loc_180017D1F
0x180017c89  mov     rax, [rbx+3080h]
0x180017c90  cmp     rax, [rbx+3078h]
0x180017c97  jnz     loc_180017E10
0x180017c9d  cmp     byte ptr [rsi], 47h ; 'G'
0x180017ca0  jnz     loc_180018123
0x180017ca6  cmp     edi, 0BCh
0x180017cac  jl      loc_180017F5D
0x180017cb2  mov     r9d, 0BCh
0x180017cb8  mov     [rbx+4Ch], r13d
0x180017cbc  sub     r9d, edi
0x180017cbf  mov     [rsp+68h+var_48], r14
0x180017cc4  mov     r8, rsi
0x180017cc7  mov     rdx, r12
0x180017cca  mov     rcx, rbx
0x180017ccd  call    ?ProcessTSPacket_@CTransportStreamMapper@@AEAAXPEAUIMediaSample@@PEAEHPEAV?$CTStickyVal@H@@@Z; CTransportStreamMapper::ProcessTSPacket_(IMediaSample *,uchar *,int,CTStickyVal<int> *)
0x180017cd2  add     rsi, 0BCh
0x180017cd9  sub     edi, 0BCh
0x180017cdf  mov     dword ptr [rbx+50h], 2
0x180017ce6  mov     ecx, [rbx+60h]
0x180017ce9  cmp     edi, ecx
0x180017ceb  mov     eax, ecx
0x180017ced  cmovl   eax, edi
0x180017cf0  sub     ecx, eax
0x180017cf2  sub     edi, eax
0x180017cf4  cdqe
0x180017cf6  add     rsi, rax
0x180017cf9  mov     [rbx+60h], ecx
0x180017cfc  mov     [rsp+68h+arg_18], edi
0x180017d03  mov     [rsp+68h+arg_10], rsi
0x180017d0b  test    ecx, ecx
0x180017d0d  jnz     short loc_180017D1F
0x180017d0f  mov     eax, [rbx+54h]
0x180017d12  mov     [rbx+58h], eax
0x180017d15  mov     eax, [rbx+5Ch]
0x180017d18  mov     [rbx+60h], eax
0x180017d1b  mov     [rbx+50h], r13d
0x180017d1f  mov     eax, [r14]
0x180017d22  cmp     [rbx+4Ch], eax
0x180017d25  jz      loc_180017FE8
0x180017d2b  test    edi, edi
0x180017d2d  jg      loc_180017C42
0x180017d33  call    cs:__imp_GetTickCount
0x180017d3a  nop     dword ptr [rax+rax+00h]
0x180017d3f  mov     r12, [rsp+68h+var_28]
0x180017d44  mov     ecx, eax
0x180017d46  sub     ecx, [rbx+28h]
0x180017d49  mov     esi, eax
0x180017d4b  cmp     ecx, [rbx+24h]
0x180017d4e  ja      loc_180017EE9
0x180017d54  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017d5b  mov     r15, [rsp+68h+var_38]
0x180017d60  mov     r14, [rsp+68h+var_30]
0x180017d65  mov     rbp, [rsp+68h+arg_0]
0x180017d6a  cmp     [rdi+8], r13b
0x180017d6e  jz      loc_180017E03
0x180017d74  lea     rbx, [rdi+0D0h]
0x180017d7b  call    cs:__imp_GetLastError
0x180017d82  nop     dword ptr [rax+rax+00h]
0x180017d87  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180017d8a  mov     esi, eax
0x180017d8c  call    cs:__imp_TlsGetValue
0x180017d93  nop     dword ptr [rax+rax+00h]
0x180017d98  test    rax, rax
0x180017d9b  jz      loc_180018088
0x180017da1  mov     rbx, rax
0x180017da4  mov     ecx, esi; dwErrCode
0x180017da6  call    cs:__imp_SetLastError
0x180017dad  nop     dword ptr [rax+rax+00h]
0x180017db2  mov     eax, [rbx+7C4h]
0x180017db8  test    eax, eax
0x180017dba  jz      short loc_180017E03
0x180017dbc  sub     eax, 1
0x180017dbf  mov     [rbx+7C4h], eax
0x180017dc5  jnz     short loc_180017E03
0x180017dc7  mov     [rbx+7C4h], r13d
0x180017dce  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180017dd5  mov     [rbx+7E0h], r13
0x180017ddc  mov     [rbx+7CCh], r13d
0x180017de3  movups  xmmword ptr [rbx+7D0h], xmm0
0x180017dea  mov     [rbx+7E8h], r13d
0x180017df1  call    cs:__imp_GetCurrentThreadId
0x180017df8  nop     dword ptr [rax+rax+00h]
0x180017dfd  mov     [rbx+7C0h], eax
0x180017e03  xor     eax, eax
0x180017e05  add     rsp, 48h
0x180017e09  pop     r13
0x180017e0b  pop     rdi
0x180017e0c  pop     rsi
0x180017e0d  pop     rbx
0x180017e0e  retn
0x180017e10  mov     rax, [rbx+38h]
0x180017e14  mov     rcx, [rax+8]
0x180017e18  test    rcx, rcx
0x180017e1b  jnz     loc_180018176
0x180017e21  mov     rcx, [rbx+3080h]; void *
0x180017e28  mov     r15d, 0BCh
0x180017e2e  movsxd  rax, edi
0x180017e31  mov     rdx, rcx
0x180017e34  sub     rdx, [rbx+3078h]
0x180017e3b  sub     r15, rdx
0x180017e3e  cmp     r15, rax
0x180017e41  cmovnb  r15d, eax
0x180017e45  movsxd  rbp, r15d
0x180017e48  lea     rax, [rcx+rbp]
0x180017e4c  cmp     rbp, rax
0x180017e4f  jnb     short loc_180017E79
0x180017e51  mov     rax, [rbx+3088h]
0x180017e58  sub     rax, rdx
0x180017e5b  cmp     rbp, rax
0x180017e5e  ja      short loc_180017E79
0x180017e60  mov     r8, rbp; Size
0x180017e63  mov     rdx, rsi; Src
0x180017e66  call    memcpy_0
0x180017e6b  add     [rbx+3080h], rbp
0x180017e72  mov     rcx, [rbx+3080h]
0x180017e79  mov     r8, [rbx+3078h]
0x180017e80  add     rsi, rbp
0x180017e83  sub     edi, r15d
0x180017e86  mov     [rsp+68h+arg_10], rsi
0x180017e8e  sub     rcx, r8
0x180017e91  mov     [rsp+68h+arg_18], edi
0x180017e98  cmp     rcx, 0BCh
0x180017e9f  jnz     loc_180017D1F
0x180017ea5  mov     r9d, edi
0x180017ea8  mov     [rbx+4Ch], r13d
0x180017eac  neg     r9d
0x180017eaf  mov     [rsp+68h+var_48], r14
0x180017eb4  mov     rdx, r12
0x180017eb7  mov     rcx, rbx
0x180017eba  call    ?ProcessTSPacket_@CTransportStreamMapper@@AEAAXPEAUIMediaSample@@PEAEHPEAV?$CTStickyVal@H@@@Z; CTransportStreamMapper::ProcessTSPacket_(IMediaSample *,uchar *,int,CTStickyVal<int> *)
0x180017ebf  mov     rax, [rbx+3078h]
0x180017ec6  mov     [rbx+3080h], rax
0x180017ecd  jmp     loc_180017CDF
0x180017ed2  sub     ecx, 1
0x180017ed5  jz      loc_180017C89
0x180017edb  cmp     ecx, 1
0x180017ede  jz      loc_180017CE6
0x180017ee4  jmp     loc_180017D1F
0x180017ee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180017ef0  test    rcx, rcx
0x180017ef3  jz      loc_180018182
0x180017ef9  cmp     [rcx+8], r13b
0x180017efd  jz      short loc_180017F2E
0x180017eff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017f04  mov     ecx, [rax+7C4h]
0x180017f0a  cmp     ecx, [rax+7C8h]
0x180017f10  jnb     short loc_180017F28
0x180017f12  add     rcx, rcx
0x180017f15  lea     rdx, aCstreammapperC_0; "CStreamMapper::CheckForTimeouts_"
0x180017f1c  mov     [rax+rcx*8], rdx
0x180017f20  mov     dword ptr [rax+rcx*8+8], 0B6h
0x180017f28  inc     dword ptr [rax+7C4h]
0x180017f2e  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180017f35  jnb     loc_180018193
0x180017f3b  mov     rbp, [rbx+10h]
0x180017f3f  lea     r15, [rbx+10h]
0x180017f43  cmp     rbp, r15
0x180017f46  jnz     short loc_180017FB3
0x180017f48  lea     rcx, [rsp+68h+arg_18]; this
0x180017f50  mov     [rbx+28h], esi
0x180017f53  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017f58  jmp     loc_180017D54
0x180017f5d  mov     rcx, [rbx+3080h]; void *
0x180017f64  movsxd  rdi, edi
0x180017f67  lea     rax, [rcx+rdi]
0x180017f6b  cmp     rdi, rax
0x180017f6e  jnb     short loc_180017F98
0x180017f70  mov     rax, [rbx+3088h]
0x180017f77  sub     rax, rcx
0x180017f7a  add     rax, [rbx+3078h]
0x180017f81  cmp     rdi, rax
0x180017f84  ja      short loc_180017F98
0x180017f86  mov     r8, rdi; Size
0x180017f89  mov     rdx, rsi; Src
0x180017f8c  call    memcpy_0
0x180017f91  add     [rbx+3080h], rdi
0x180017f98  add     rsi, rdi
0x180017f9b  mov     [rsp+68h+arg_18], r13d
0x180017fa3  mov     [rsp+68h+arg_10], rsi
0x180017fab  mov     edi, r13d
0x180017fae  jmp     loc_180017D1F
0x180017fb3  mov     eax, [r14]
0x180017fb6  cmp     [r14+4], eax
0x180017fba  jz      short loc_180017F48
0x180017fbc  lea     rdi, [rbp-10h]
0x180017fc0  lock inc dword ptr [rdi]
0x180017fc3  mov     rcx, [rdi+8]
0x180017fc7  mov     r8, r14
0x180017fca  mov     edx, esi
0x180017fcc  call    ?CheckTimeout@CDemuxBaseParser@@QEAAXKPEAV?$CTStickyVal@H@@@Z; CDemuxBaseParser::CheckTimeout(ulong,CTStickyVal<int> *)
0x180017fd1  mov     rbp, [rbp+0]
0x180017fd5  mov     rcx, rdi; this
0x180017fd8  call    ?Release@CParserRef@@QEAAKXZ; CParserRef::Release(void)
0x180017fdd  cmp     rbp, r15
0x180017fe0  jz      loc_180017F48
0x180017fe6  jmp     short loc_180017FB3
0x180017fe8  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180017ff0  call    cs:__imp_LeaveCriticalSection
0x180017ff7  nop     dword ptr [rax+rax+00h]
0x180017ffc  mov     rcx, rbx; this
0x180017fff  call    ?ParserInstructedReset_@CStreamMapper@@IEAAXXZ; CStreamMapper::ParserInstructedReset_(void)
0x180018004  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18001800c  call    cs:__imp_EnterCriticalSection
0x180018013  nop     dword ptr [rax+rax+00h]
0x180018018  jmp     loc_180017D2B
0x18001801d  call    cs:__imp_GetLastError
0x180018024  nop     dword ptr [rax+rax+00h]
0x180018029  test    eax, eax
0x18001802b  jnz     loc_180017BEC
0x180018031  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018038  test    rcx, rcx
0x18001803b  jz      loc_1800180D4
0x180018041  mov     rax, [rcx]
0x180018044  mov     rax, [rax]
0x180018047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001804c  test    rax, rax
0x18001804f  cmovnz  rbp, rax
0x180018053  jmp     loc_180017BEC
0x180018058  mov     rcx, cs:WPP_GLOBAL_Control
0x18001805f  lea     r8, WPP_db22ba5164493dcbd331695ea6183974_Traceguids
0x180018066  mov     edx, 18h
0x18001806b  mov     [rsp+68h+var_40], edi
0x18001806f  mov     r9, rbx
0x180018072  mov     [rsp+68h+var_48], rsi
0x180018077  mov     rcx, [rcx+88h]
0x18001807e  call    WPP_SF_qqD
0x180018083  jmp     loc_180017C33
0x180018088  call    cs:__imp_GetLastError
0x18001808f  nop     dword ptr [rax+rax+00h]
0x180018094  test    eax, eax
0x180018096  jnz     loc_180017DA4
0x18001809c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800180a3  test    rcx, rcx
0x1800180a6  jz      loc_1800181C3
  ... truncated ...
```
