# CTransportStreamMapper::ProcessTSPacket_(IMediaSample *,uchar *,int,CTStickyVal<int> *)

- ea: `0x180018220`
- end: `0x180018aa1`
- name: `?ProcessTSPacket_@CTransportStreamMapper@@AEAAXPEAUIMediaSample@@PEAEHPEAV?$CTStickyVal@H@@@Z`
- size: `2177`
- prototype: `void __fastcall(__int64, __int64, unsigned __int8 *, int, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180017b70`

## callees

- `0x180016e30`
- `0x180018220`
- `0x180018ab0`
- `0x180018e30`
- `0x1800190ac`
- `0x18001a29c`
- `0x180073d4c`
- `0x180074160`
- `0x180074a06`
- `0x18007c8e8`
- `0x1800b18cc`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800185d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800185d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001839d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001839d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018872`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018625`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800183ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800185bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800183ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800185bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001895d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018a52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001895d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018a52`

## pseudocode

```c
void __fastcall CTransportStreamMapper::ProcessTSPacket_(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        int a4,
        _DWORD *a5)
{
  unsigned int v7; // ecx
  char v8; // r8
  __int64 v9; // r8
  unsigned int v10; // ecx
  int v11; // edx
  unsigned int v12; // r9d
  unsigned __int8 *v13; // rax
  __int64 v14; // r14
  CallStackTracing *v15; // rdi
  char *v16; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdi
  unsigned int v23; // ecx
  BOOL v24; // r8d
  volatile signed __int32 *v25; // r15
  int v26; // r8d
  _DWORD *v27; // r9
  CParserRef *v28; // r14
  BOOL v29; // edx
  CallStackTracing *v30; // rdi
  GUID *v31; // rbx
  DWORD v32; // esi
  GUID *v33; // rax
  int v34; // eax
  int v35; // eax
  __int64 v36; // r14
  volatile signed __int32 *v37; // rdi
  volatile signed __int32 *v38; // r14
  CParserRef *v39; // rsi
  __int64 v40; // rcx
  __int64 *v41; // rcx
  __int64 v42; // rax
  __int64 *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rcx
  CallStackTracing *v46; // rax
  __int64 v47; // rcx
  CallStackTracing *v48; // rax
  __int128 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h]
  BOOL v51; // [rsp+68h] [rbp-98h]
  BOOL v52; // [rsp+6Ch] [rbp-94h]
  int i; // [rsp+70h] [rbp-90h]
  int v54; // [rsp+74h] [rbp-8Ch]
  unsigned int v55; // [rsp+78h] [rbp-88h]
  _DWORD *v56; // [rsp+80h] [rbp-80h]
  __int64 v57; // [rsp+88h] [rbp-78h]
  _DWORD v58[2]; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  unsigned int v62; // [rsp+ACh] [rbp-54h]
  int v63; // [rsp+B0h] [rbp-50h]
  int v64; // [rsp+B4h] [rbp-4Ch]
  int v65; // [rsp+B8h] [rbp-48h]
  int v66; // [rsp+BCh] [rbp-44h]
  unsigned int v67; // [rsp+C0h] [rbp-40h]
  unsigned int v68; // [rsp+C4h] [rbp-3Ch]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  unsigned int v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  unsigned int v74; // [rsp+100h] [rbp+0h]
  unsigned int v75; // [rsp+160h] [rbp+60h]
  __int64 v76; // [rsp+168h] [rbp+68h]
  unsigned int v77; // [rsp+170h] [rbp+70h]

  v57 = a2;
  v56 = a5;
  *(_QWORD *)&v49 = a3;
  v54 = a4;
  memset_0(v58, 0, 0xE8u);
  v7 = *(unsigned __int16 *)(a3 + 1);
  v8 = *(_WORD *)(a3 + 1);
  v63 = *a3;
  v64 = (v7 >> 7) & 1;
  v65 = (v7 >> 6) & 1;
  v9 = (v7 >> 8) | ((v8 & 0x1F) << 8);
  v66 = (v7 >> 5) & 1;
  v10 = a3[3];
  v67 = v9;
  v11 = (v10 >> 4) & 3;
  v68 = v10 >> 6;
  v69 = v11;
  v70 = v10 & 0xF;
  if ( (unsigned int)(v11 - 2) <= 1 )
  {
    if ( (unsigned int)MPEG2_TRANSPORT_PACKET::ParseAdaptationField((MPEG2_TRANSPORT_PACKET *)v58, a3 + 4) != 1 )
      return;
    v11 = v69;
    if ( v69 == 3 )
    {
      v12 = v71;
      if ( v71 > 0xB6 )
        return;
    }
    else
    {
      if ( v69 != 2 )
        return;
      v12 = v71;
      if ( v71 != 183 )
        return;
    }
    v9 = v67;
  }
  else
  {
    v12 = 0;
    v71 = 0;
  }
  v58[1] = DWORD1(v49);
  v58[0] = (_DWORD)a3;
  v59 = 188;
  if ( ((v11 - 1) & 0xFFFFFFFD) != 0 )
  {
    v60 = 0;
    v61 = 0;
  }
  else
  {
    if ( (unsigned int)(v11 - 2) <= 1 )
    {
      if ( v12 )
        v13 = (unsigned __int8 *)(v75 + v76);
      else
        v13 = a3 + 5;
    }
    else
    {
      v13 = a3 + 4;
    }
    v60 = v13;
    v61 = (_DWORD)a3 - (_DWORD)v13 + 188;
  }
  v62 = v9 & 0x1FFF | v62 & 0xFFFFE000 | 0x8000;
  v49 = 0;
  if ( (unsigned int)(v11 - 2) <= 1 && v12 && v72 )
    v14 = v74 + 300 * v73;
  else
    v14 = v49;
  v15 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v11 = v69;
    v9 = v67;
    v15 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v16 = (char *)v15 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v15 + 3));
    if ( Value )
    {
      v16 = Value;
    }
    else if ( !GetLastError() )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v42 = (*(__int64 (__fastcall **)(__int64 *))*v41)(v41);
      if ( v42 )
        v16 = (char *)v42;
    }
    SetLastError(LastError);
    v19 = *((unsigned int *)v16 + 497);
    if ( (unsigned int)v19 < *((_DWORD *)v16 + 498) )
    {
      v20 = 2 * v19;
      *(_QWORD *)&v16[8 * v20] = "CTransportStreamMapper::ProcessTSPacket_";
      *(_DWORD *)&v16[8 * v20 + 8] = 708;
    }
    ++*((_DWORD *)v16 + 497);
    v11 = v69;
    v9 = v67;
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qDidd(*((_QWORD *)WPP_GLOBAL_Control + 17), v14 / 27000, v9, a1, v9, v14 / 27000, v65, v59);
    v11 = v69;
    LODWORD(v9) = v67;
  }
  v21 = *(_DWORD *)(a1 + 100);
  if ( v21 != (_DWORD)v9 )
  {
    if ( v21 != -1 )
    {
      if ( *(_BYTE *)(*(unsigned int *)(a1 + 100) + *(_QWORD *)(a1 + 104)) )
      {
        v36 = *(_QWORD *)(*(_QWORD *)(a1 + 112)
                        + 16LL * *(unsigned __int8 *)(*(unsigned int *)(a1 + 100) + *(_QWORD *)(a1 + 104))
                        - 8);
        if ( v36 )
        {
          v37 = *(volatile signed __int32 **)(v36 + 8);
          v38 = (volatile signed __int32 *)(v36 + 8);
          if ( v37 != v38 )
          {
            do
            {
              if ( a5[1] == *a5 )
                break;
              v39 = (CParserRef *)(v37 - 4);
              _InterlockedIncrement(v37 - 4);
              (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v37 - 1) + 16LL))(*((_QWORD *)v37 - 1), a5);
              v37 = *(volatile signed __int32 **)v37;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v39, 0xFFFFFFFF) == 1 )
              {
                CParserRef::~CParserRef(v39);
                operator delete(v39);
              }
            }
            while ( v37 != v38 );
            v11 = v69;
            LODWORD(v9) = v67;
          }
        }
      }
    }
    *(_DWORD *)(a1 + 100) = v9;
  }
  if ( *(_BYTE *)((unsigned int)v9 + *(_QWORD *)(a1 + 104)) )
  {
    v22 = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL * *(unsigned __int8 *)((unsigned int)v9 + *(_QWORD *)(a1 + 104)) - 8);
    if ( v22 )
    {
      v23 = *(unsigned __int8 *)(v22 + 48);
      v77 = v23;
      v55 = v64;
      v24 = (_DWORD)v9 != 0x1FFF && (v11 & 0xFFFFFFFD) != 0 && v70 != v23;
      v51 = v24;
      v52 = ((v11 - 1) & 0xFFFFFFFD) == 0 && v23 == (((_BYTE)v70 + 1) & 0xF);
      if ( v24 )
      {
        v45 = *(_QWORD *)(a1 + 64);
        *(_QWORD *)(v45 + 424) = 0;
        *(_QWORD *)(v45 + 408) = -1;
        CTClockSubordinate<__int64,__int64>::Reset(v45 + 32);
        *(_QWORD *)&v49 = 1;
        v50 = 0;
        *((_QWORD *)&v49 + 1) = v67 & 0x1FFF | ((v77 | ((unsigned __int64)(v70 & 0xF) << 32)) << 13);
        Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(*(_QWORD *)(a1 + 56) + 8504LL, &v49);
        v11 = v69;
      }
      if ( v64 )
      {
        v40 = *(_QWORD *)(a1 + 56);
        v49 = 0;
        LODWORD(v49) = 5;
        v50 = 0;
        Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(v40 + 8504, &v49);
        v11 = v69;
      }
      if ( !v11 )
      {
        v47 = *(_QWORD *)(a1 + 56) + 8504LL;
        *((_QWORD *)&v49 + 1) = v67 & 0x1FFF;
        *(_QWORD *)&v49 = 6;
        v50 = 0;
        Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(v47, &v49);
      }
      v62 = v62 & 0xFFFF9FFF | 0x4000;
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 40));
      v25 = *(volatile signed __int32 **)(v22 + 8);
      v26 = v65;
      for ( i = v65; v25 != (volatile signed __int32 *)(v22 + 8); v26 = i )
      {
        v27 = v56;
        if ( v56[1] == *v56 )
          break;
        v28 = (CParserRef *)(v25 - 4);
        _InterlockedIncrement(v25 - 4);
        v29 = v51 || *(_DWORD *)(v22 + 44);
        (*(void (__fastcall **)(_QWORD, __int64, _DWORD *, _QWORD, BOOL, BOOL, int, int, _DWORD *))(**((_QWORD **)v25 - 1)
                                                                                                  + 8LL))(
          *((_QWORD *)v25 - 1),
          v57,
          v58,
          v55,
          v29,
          v52,
          v26,
          v54,
          v27);
        v25 = *(volatile signed __int32 **)v25;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28, 0xFFFFFFFF) == 1 )
        {
          CParserRef::~CParserRef(v28);
          operator delete(v28);
        }
      }
      *(_DWORD *)(v22 + 44) = 0;
      if ( v67 != 0x1FFF && (v69 & 0xFFFFFFFD) != 0 )
        *(_BYTE *)(v22 + 48) = (v70 + 1) & 0xF;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 40), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v22)(v22, 1);
    }
  }
  else
  {
    v62 = v62 & 0xFFFF9FFF | 0x2000;
  }
  CMpeg2Stats::OnPacket(*(CMpeg2Stats **)(a1 + 56), (struct MPEG2_SYS_BUFFER *)v58);
  v30 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v31 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v32 = GetLastError();
    v33 = (GUID *)TlsGetValue(*((_DWORD *)v30 + 3));
    if ( v33 )
    {
      v31 = v33;
    }
    else if ( !GetLastError() )
    {
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v44 = (*(__int64 (__fastcall **)(__int64 *))*v43)(v43);
      if ( v44 )
        v31 = (GUID *)v44;
    }
    SetLastError(v32);
    v34 = *(_DWORD *)&v31[124].Data2;
    if ( v34 )
    {
      v35 = v34 - 1;
      *(_DWORD *)&v31[124].Data2 = v35;
      if ( !v35 )
      {
        *(_DWORD *)&v31[124].Data2 = 0;
        *(_QWORD *)&v31[126].Data1 = 0;
        *(_DWORD *)&v31[124].Data4[4] = 0;
        v31[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v31[126].Data4 = 0;
        v31[124].Data1 = GetCurrentThreadId();
      }
    }
  }
}

```

## disassembly

```asm
0x180018220  push    rbp
0x180018222  push    rbx
0x180018223  push    r12
0x180018225  push    r13
0x180018227  push    r15
0x180018229  lea     rbp, [rsp-0B0h]
0x180018231  sub     rsp, 1B0h
0x180018238  mov     rax, cs:__security_cookie
0x18001823f  xor     rax, rsp
0x180018242  mov     [rbp+0D0h+var_50], rax
0x180018249  mov     r15, [rbp+0D0h+arg_20]
0x180018250  mov     rbx, r8
0x180018253  mov     [rbp+0D0h+var_148], rdx
0x180018257  mov     r13, rcx
0x18001825a  xor     edx, edx; Val
0x18001825c  mov     [rbp+0D0h+var_150], r15
0x180018260  mov     r8d, 0E8h; Size
0x180018266  mov     qword ptr [rsp+1D0h+var_180], rbx
0x18001826b  lea     rcx, [rbp+0D0h+var_140]; void *
0x18001826f  mov     [rsp+1D0h+var_15C], r9d
0x180018274  call    memset_0
0x180018279  movzx   ecx, word ptr [rbx+1]
0x18001827d  xor     r12d, r12d
0x180018280  movzx   eax, byte ptr [rbx]
0x180018283  mov     r8d, ecx
0x180018286  mov     [rbp+0D0h+var_120], eax
0x180018289  and     r8d, 1Fh
0x18001828d  mov     eax, ecx
0x18001828f  shl     r8d, 8
0x180018293  shr     eax, 7
0x180018296  and     eax, 1
0x180018299  mov     [rbp+0D0h+var_11C], eax
0x18001829c  mov     eax, ecx
0x18001829e  shr     eax, 6
0x1800182a1  and     eax, 1
0x1800182a4  mov     [rbp+0D0h+var_118], eax
0x1800182a7  mov     eax, ecx
0x1800182a9  shr     eax, 5
0x1800182ac  and     eax, 1
0x1800182af  shr     ecx, 8
0x1800182b2  or      r8d, ecx
0x1800182b5  mov     [rbp+0D0h+var_114], eax
0x1800182b8  movzx   ecx, byte ptr [rbx+3]
0x1800182bc  mov     edx, ecx
0x1800182be  mov     dword ptr [rbp+0D0h+var_110], r8d
0x1800182c2  shr     edx, 4
0x1800182c5  mov     eax, ecx
0x1800182c7  and     edx, 3
0x1800182ca  shr     eax, 6
0x1800182cd  and     ecx, 0Fh
0x1800182d0  mov     dword ptr [rbp+0D0h+var_110+4], eax
0x1800182d3  mov     [rbp+0D0h+var_108], edx
0x1800182d6  mov     [rbp+0D0h+var_104], ecx
0x1800182d9  lea     eax, [rdx-2]
0x1800182dc  cmp     eax, 1
0x1800182df  jbe     loc_1800186DF
0x1800182e5  mov     r9d, r12d
0x1800182e8  mov     [rbp+0D0h+var_100], r12d
0x1800182ec  mov     eax, dword ptr [rsp+1D0h+var_180+4]
0x1800182f0  mov     [rbp+0D0h+var_13C], eax
0x1800182f3  lea     eax, [rdx-1]
0x1800182f6  mov     [rsp+1D0h+var_30], rdi
0x1800182fe  mov     [rbp+0D0h+var_140], ebx
0x180018301  mov     [rbp+0D0h+var_138], 0BCh
0x180018308  test    eax, 0FFFFFFFDh
0x18001830d  jnz     loc_1800187BD
0x180018313  lea     eax, [rdx-2]
0x180018316  cmp     eax, 1
0x180018319  jbe     loc_18001871B
0x18001831f  lea     rax, [rbx+4]
0x180018323  sub     ebx, eax
0x180018325  mov     [rbp+0D0h+var_130], rax
0x180018329  add     ebx, 0BCh
0x18001832f  mov     [rbp+0D0h+var_128], ebx
0x180018332  mov     ecx, [rbp+0D0h+var_124]
0x180018335  mov     eax, r8d
0x180018338  and     ecx, 0FFFFE000h
0x18001833e  mov     [rsp+1D0h+var_38], r14
0x180018346  and     eax, 1FFFh
0x18001834b  xorps   xmm0, xmm0
0x18001834e  or      ecx, eax
0x180018350  lea     eax, [rdx-2]
0x180018353  bts     ecx, 0Fh
0x180018357  mov     [rbp+0D0h+var_124], ecx
0x18001835a  movups  [rsp+1D0h+var_180], xmm0
0x18001835f  cmp     eax, 1
0x180018362  ja      short loc_180018373
0x180018364  test    r9d, r9d
0x180018367  jz      short loc_180018373
0x180018369  cmp     [rbp+0D0h+var_F0], r12d
0x18001836d  jnz     loc_180018932
0x180018373  mov     r14, qword ptr [rsp+1D0h+var_180]
0x180018378  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001837f  test    rdi, rdi
0x180018382  jz      loc_180018945
0x180018388  mov     [rsp+1D0h+var_28], rsi
0x180018390  cmp     [rdi+8], r12b
0x180018394  jz      short loc_180018405
0x180018396  lea     rbx, [rdi+0D0h]
0x18001839d  call    cs:__imp_GetLastError
0x1800183a4  nop     dword ptr [rax+rax+00h]
0x1800183a9  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800183ac  mov     esi, eax
0x1800183ae  call    cs:__imp_TlsGetValue
0x1800183b5  nop     dword ptr [rax+rax+00h]
0x1800183ba  test    rax, rax
0x1800183bd  jz      loc_180018837
0x1800183c3  mov     rbx, rax
0x1800183c6  mov     ecx, esi; dwErrCode
0x1800183c8  call    cs:__imp_SetLastError
0x1800183cf  nop     dword ptr [rax+rax+00h]
0x1800183d4  mov     eax, [rbx+7C4h]
0x1800183da  cmp     eax, [rbx+7C8h]
0x1800183e0  jnb     short loc_1800183F8
0x1800183e2  add     rax, rax
0x1800183e5  lea     rcx, aCtransportstre_1; "CTransportStreamMapper::ProcessTSPacket"...
0x1800183ec  mov     [rbx+rax*8], rcx
0x1800183f0  mov     dword ptr [rbx+rax*8+8], 2C4h
0x1800183f8  inc     dword ptr [rbx+7C4h]
0x1800183fe  mov     edx, [rbp+0D0h+var_108]
0x180018401  mov     r8d, dword ptr [rbp+0D0h+var_110]
0x180018405  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18001840c  jnb     loc_1800189AC
0x180018412  mov     eax, [r13+64h]
0x180018416  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001841d  cmp     eax, r8d
0x180018420  jnz     loc_180018733
0x180018426  mov     rax, [r13+68h]
0x18001842a  mov     ecx, r8d
0x18001842d  movzx   r9d, byte ptr [rcx+rax]
0x180018432  test    r9b, r9b
0x180018435  jz      loc_180018667
0x18001843b  mov     rax, [r13+70h]
0x18001843f  mov     ecx, r9d
0x180018442  add     rcx, rcx
0x180018445  mov     rdi, [rax+rcx*8-8]
0x18001844a  test    rdi, rdi
0x18001844d  jz      loc_18001857E
0x180018453  movzx   ecx, byte ptr [rdi+30h]
0x180018457  mov     eax, [rbp+0D0h+var_11C]
0x18001845a  mov     [rbp+0D0h+var_60], ecx
0x18001845d  mov     [rsp+1D0h+var_158], eax
0x180018461  cmp     r8d, 1FFFh
0x180018468  jnz     loc_18001867A
0x18001846e  mov     r8d, r12d
0x180018471  lea     eax, [rdx-1]
0x180018474  mov     [rsp+1D0h+var_168], r8d
0x180018479  test    eax, 0FFFFFFFDh
0x18001847e  jz      loc_18001869A
0x180018484  mov     [rsp+1D0h+var_164], r12d
0x180018489  test    r8d, r8d
0x18001848c  jnz     loc_1800188AD
0x180018492  cmp     [rbp+0D0h+var_11C], r12d
0x180018496  jnz     loc_180018803
0x18001849c  test    edx, edx
0x18001849e  jz      loc_180018A04
0x1800184a4  mov     eax, [rbp+0D0h+var_124]
0x1800184a7  btr     eax, 0Dh
0x1800184ab  bts     eax, 0Eh
0x1800184af  mov     [rbp+0D0h+var_124], eax
0x1800184b2  lock inc dword ptr [rdi+28h]
0x1800184b6  mov     r15, [rdi+8]
0x1800184ba  lea     r12, [rdi+8]
0x1800184be  mov     r8d, [rbp+0D0h+var_118]
0x1800184c2  mov     [rsp+1D0h+var_160], r8d
0x1800184c7  cmp     r15, r12
0x1800184ca  jz      loc_18001855C
0x1800184d0  mov     r9, [rbp+0D0h+var_150]
0x1800184d4  mov     eax, [r9]
0x1800184d7  cmp     [r9+4], eax
0x1800184db  jz      short loc_18001855C
0x1800184dd  lea     r14, [r15-10h]
0x1800184e1  lock inc dword ptr [r14]
0x1800184e5  cmp     [rsp+1D0h+var_168], 0
0x1800184ea  mov     rcx, [r14+8]
0x1800184ee  mov     rax, [rcx]
0x1800184f1  jnz     loc_1800186D5
0x1800184f7  cmp     dword ptr [rdi+2Ch], 0
0x1800184fb  jnz     loc_1800186D5
0x180018501  xor     edx, edx
0x180018503  mov     rax, [rax+8]
0x180018507  mov     [rsp+1D0h+var_190], r9
0x18001850c  mov     r9d, [rsp+1D0h+var_15C]
0x180018511  mov     [rsp+1D0h+var_198], r9d
0x180018516  mov     r9d, [rsp+1D0h+var_158]
0x18001851b  mov     [rsp+1D0h+var_1A0], r8d
0x180018520  mov     r8d, [rsp+1D0h+var_164]
0x180018525  mov     dword ptr [rsp+1D0h+var_1A8], r8d
0x18001852a  lea     r8, [rbp+0D0h+var_140]
0x18001852e  mov     [rsp+1D0h+var_1B0], edx
0x180018532  mov     rdx, [rbp+0D0h+var_148]
0x180018536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001853b  mov     r15, [r15]
0x18001853e  mov     eax, ebx
0x180018540  lock xadd [r14], eax
0x180018545  cmp     eax, 1
0x180018548  jz      loc_1800187E9
0x18001854e  mov     r8d, [rsp+1D0h+var_160]
0x180018553  cmp     r15, r12
0x180018556  jnz     loc_1800184D0
0x18001855c  xor     r12d, r12d
0x18001855f  mov     [rdi+2Ch], r12d
0x180018563  cmp     dword ptr [rbp+0D0h+var_110], 1FFFh
0x18001856a  jnz     loc_1800186B8
0x180018570  lock xadd [rdi+28h], ebx
0x180018575  cmp     ebx, 1
0x180018578  jz      loc_180018A3A
0x18001857e  mov     rcx, [r13+38h]; this
0x180018582  lea     rdx, [rbp+0D0h+var_140]; struct MPEG2_SYS_BUFFER *
0x180018586  call    ?OnPacket@CMpeg2Stats@@QEAAXPEAUMPEG2_SYS_BUFFER@@@Z; CMpeg2Stats::OnPacket(MPEG2_SYS_BUFFER *)
0x18001858b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018592  mov     r14, [rsp+1D0h+var_38]
0x18001859a  cmp     byte ptr [rdi+8], 0
0x18001859e  jz      loc_180018637
0x1800185a4  lea     rbx, [rdi+0D0h]
0x1800185ab  call    cs:__imp_GetLastError
0x1800185b2  nop     dword ptr [rax+rax+00h]
0x1800185b7  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800185ba  mov     esi, eax
0x1800185bc  call    cs:__imp_TlsGetValue
0x1800185c3  nop     dword ptr [rax+rax+00h]
0x1800185c8  test    rax, rax
0x1800185cb  jz      loc_180018872
0x1800185d1  mov     rbx, rax
0x1800185d4  mov     ecx, esi; dwErrCode
0x1800185d6  call    cs:__imp_SetLastError
0x1800185dd  nop     dword ptr [rax+rax+00h]
0x1800185e2  mov     eax, [rbx+7C4h]
0x1800185e8  test    eax, eax
0x1800185ea  jz      short loc_180018637
0x1800185ec  sub     eax, 1
0x1800185ef  mov     [rbx+7C4h], eax
0x1800185f5  jnz     short loc_180018637
0x1800185f7  mov     [rbx+7C4h], r12d
0x1800185fe  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180018605  mov     qword ptr [rbx+7E0h], 0
0x180018610  mov     [rbx+7CCh], r12d
0x180018617  movups  xmmword ptr [rbx+7D0h], xmm0
0x18001861e  mov     [rbx+7E8h], r12d
0x180018625  call    cs:__imp_GetCurrentThreadId
0x18001862c  nop     dword ptr [rax+rax+00h]
0x180018631  mov     [rbx+7C0h], eax
0x180018637  mov     rsi, [rsp+1D0h+var_28]
0x18001863f  mov     rdi, [rsp+1D0h+var_30]
0x180018647  mov     rcx, [rbp+0D0h+var_50]
0x18001864e  xor     rcx, rsp; StackCookie
0x180018651  call    __security_check_cookie
0x180018656  add     rsp, 1B0h
0x18001865d  pop     r15
0x18001865f  pop     r13
0x180018661  pop     r12
0x180018663  pop     rbx
0x180018664  pop     rbp
0x180018665  retn
0x180018667  mov     eax, [rbp+0D0h+var_124]
0x18001866a  btr     eax, 0Eh
0x18001866e  bts     eax, 0Dh
0x180018672  mov     [rbp+0D0h+var_124], eax
0x180018675  jmp     loc_18001857E
0x18001867a  test    edx, 0FFFFFFFDh
0x180018680  jz      loc_18001846E
0x180018686  cmp     [rbp+0D0h+var_104], ecx
0x180018689  jz      loc_18001846E
0x18001868f  mov     r8d, 1
0x180018695  jmp     loc_180018471
0x18001869a  movzx   eax, byte ptr [rbp+0D0h+var_104]
0x18001869e  inc     al
0x1800186a0  and     eax, 0Fh
0x1800186a3  cmp     ecx, eax
0x1800186a5  jnz     loc_180018484
0x1800186ab  mov     [rsp+1D0h+var_164], 1
0x1800186b3  jmp     loc_180018489
0x1800186b8  test    [rbp+0D0h+var_108], 0FFFFFFFDh
0x1800186bf  jz      loc_180018570
0x1800186c5  movzx   eax, byte ptr [rbp+0D0h+var_104]
0x1800186c9  inc     al
0x1800186cb  and     al, 0Fh
0x1800186cd  mov     [rdi+30h], al
0x1800186d0  jmp     loc_180018570
0x1800186d5  mov     edx, 1
0x1800186da  jmp     loc_180018503
0x1800186df  lea     rdx, [rbx+4]; unsigned __int8 *
0x1800186e3  lea     rcx, [rbp+0D0h+var_140]; this
0x1800186e7  call    ?ParseAdaptationField@MPEG2_TRANSPORT_PACKET@@QEAAHPEAE@Z; MPEG2_TRANSPORT_PACKET::ParseAdaptationField(uchar *)
0x1800186ec  cmp     eax, 1
0x1800186ef  jnz     loc_180018647
0x1800186f5  mov     edx, [rbp+0D0h+var_108]
0x1800186f8  cmp     edx, 3
0x1800186fb  jnz     loc_1800187CA
0x180018701  mov     r9d, [rbp+0D0h+var_100]
0x180018705  cmp     r9d, 0B6h
0x18001870c  ja      loc_180018647
0x180018712  mov     r8d, dword ptr [rbp+0D0h+var_110]
0x180018716  jmp     loc_1800182EC
0x18001871b  test    r9d, r9d
0x18001871e  jz      loc_1800187B4
0x180018724  mov     ecx, [rbp+0D0h+var_70]
0x180018727  mov     rax, [rbp+0D0h+var_68]
0x18001872b  add     rax, rcx
0x18001872e  jmp     loc_180018323
  ... truncated ...
```
