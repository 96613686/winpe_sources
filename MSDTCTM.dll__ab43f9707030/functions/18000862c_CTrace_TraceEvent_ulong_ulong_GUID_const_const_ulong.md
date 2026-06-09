# CTrace::TraceEvent(ulong,ulong,_GUID const * const,ulong,...)

- ea: `0x18000862c`
- end: `0x180008a3f`
- name: `?TraceEvent@CTrace@@QEAAJKKQEBU_GUID@@KZZ`
- size: `1043`
- prototype: `__int64(CTrace *__hidden this, unsigned int, unsigned int, const struct _GUID *const, unsigned int, ...)`
- caller_count: `15`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006750`
- `0x180007d90`
- `0x1800160c4`
- `0x180018608`
- `0x180031d00`
- `0x180032050`
- `0x1800352d0`
- `0x1800358a0`
- `0x1800370c0`
- `0x1800374e0`
- `0x1800606f0`
- `0x180060970`
- `0x18006ec7c`
- `0x1800720c0`
- `0x1800755f0`

## callees

- `0x1800063b0`
- `0x180007d08`
- `0x18000862c`
- `0x18001554c`
- `0x180085624`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008740`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a14`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008917`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008917`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18000887f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180008928`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x18000887f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180008928`

## string_xrefs

- `0x180008796`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180008983`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180008720`: `MSDTC Service`

## pseudocode

```c
__int64 CTrace::TraceEvent(
        CTrace *this,
        unsigned int a2,
        unsigned int a3,
        union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *a4,
        ULONG a5,
        ...)
{
  unsigned int v9; // ebx
  signed __int32 v10; // r14d
  const wchar_t *v11; // r12
  __int64 v12; // rsi
  DWORD v13; // eax
  __int64 v14; // r9
  char *v15; // rdi
  union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F v16; // xmm0
  va_list v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  TRACEHANDLE v20; // rcx
  signed int v21; // eax
  unsigned int v22; // r9d
  signed __int32 v23; // r14d
  void *v24; // r9
  signed __int32 v25; // edi
  void *v26; // r9
  unsigned int v28[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v29; // [rsp+28h] [rbp-D8h]
  const wchar_t *v30; // [rsp+30h] [rbp-D0h]
  void *v31; // [rsp+38h] [rbp-C8h]
  int v32; // [rsp+40h] [rbp-C0h]
  int TraceContext; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+60h] [rbp-A0h]
  signed __int32 v36; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  char *v38; // [rsp+78h] [rbp-88h] BYREF
  _EVENT_TRACE_HEADER EventTrace; // [rsp+80h] [rbp-80h] BYREF
  signed __int32 *v40; // [rsp+B0h] [rbp-50h]
  int v41; // [rsp+B8h] [rbp-48h]
  char v42; // [rsp+C0h] [rbp-40h] BYREF
  char v43[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v44; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v45[111]; // [rsp+1C1h] [rbp+C1h] BYREF
  va_list va; // [rsp+2B8h] [rbp+1B8h] BYREF

  va_start(va, a5);
  v36 = _InterlockedIncrement(&dword_18016810C);
  memset_0(&EventTrace, 0, 0x140u);
  v34 = 0;
  v35 = 0;
  v44 = 0;
  memset_0(v45, 0, 0x63u);
  pv = 0;
  v38 = &v44;
  if ( (unsigned int)(*((_DWORD *)this + 2) - 1) > 2 )
  {
    v9 = -2147467263;
    goto LABEL_40;
  }
  if ( a5 - 10 > 0xF4 )
  {
    v9 = -2147024809;
    goto LABEL_40;
  }
  TraceContext = CTrace::GetTraceContext(this, a2, (struct _TRACE_CONTEXT *)&v34);
  v9 = TraceContext;
  if ( TraceContext >= 0 && (_DWORD)v34 && HIDWORD(v34) >= a3 )
  {
    v10 = 0;
    v11 = L"MSDTC Service";
    v12 = -1;
    if ( *((_DWORD *)this + 2) != 1 )
      goto LABEL_13;
    v13 = WaitForSingleObject(*((HANDLE *)this + 210), 0x1388u);
    if ( v13 == -1 )
    {
      v9 = -1;
      v30 = L"WaitForSingleObjectEx for m_hSessionEvent Failed";
      v14 = 1728;
      v28[0] = -1;
      TraceContext = -1;
    }
    else
    {
      if ( v13 != 258 )
        goto LABEL_13;
      v14 = 1734;
      v30 = L"WaitForSingleObjectEx for m_hSessionEvent timed out";
      *(_QWORD *)v28 = 0;
    }
    *((_DWORD *)this + 2) = 2;
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
      v14,
      L"CTrace::TraceEvent",
      *(_QWORD *)v28,
      v30);
LABEL_13:
    memset_0(&EventTrace, 0, 0x140u);
    v15 = &v42;
    v16 = *a4;
    EventTrace.Version = a5;
    va_copy(v17, va);
    EventTrace.UserTime = 1179648;
    EventTrace.24 = v16;
    v40 = &v36;
    v41 = 4;
    do
    {
      v18 = *(_DWORD *)v17;
      *((_DWORD *)v15 + 2) = *(_DWORD *)v17;
      if ( !v18 )
        break;
      v19 = *((_QWORD *)v17 + 1);
      v17 += 16;
      *(_QWORD *)v15 = v19;
      v15 += 16;
    }
    while ( v15 < v43 );
    if ( g_pCoreTmInstance )
    {
      (*(void (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)g_pCoreTmInstance + 56LL))(
        g_pCoreTmInstance,
        &pv);
      if ( pv )
        v11 = (const wchar_t *)pv;
    }
    if ( v15 < v43 )
    {
      do
        ++v12;
      while ( v11[v12] );
      *(_QWORD *)v15 = v11;
      *((_DWORD *)v15 + 2) = 2 * v12 + 2;
      LODWORD(v15) = (_DWORD)v15 + 16;
    }
    v20 = *((_QWORD *)this + 202);
    *(_DWORD *)&EventTrace.Size = (_DWORD)v15 - (unsigned int)&EventTrace;
    v21 = TraceEvent(v20, &EventTrace);
    if ( v21 == 8 )
    {
      do
      {
        v22 = g_dwNumTraceSleepIntervals;
        if ( g_dwNumTraceSleepIntervals <= 0xF424A )
        {
          v23 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwNumTraceSleepIntervals, 1u);
          v22 = g_dwNumTraceSleepIntervals;
          v10 = v23 + 1;
        }
        if ( v10 == g_dwTraceSleepIntervalsLimit )
        {
          StringCchPrintfA(&v44, 0x64u, "%d", v22);
          DtcWriteToEventLoggerExUnFilteredA(2u, 0xDu, 0xC0001149, v24, 1u, v28[0], (const char **)&v38, v31, v32);
          if ( 10 * g_dwTraceSleepIntervalsLimit <= 0xF424A )
            g_dwTraceSleepIntervalsLimit *= 10;
        }
        Sleep(0x7D0u);
        v21 = TraceEvent(*((_QWORD *)this + 202), &EventTrace);
      }
      while ( v21 == 8 );
      v9 = TraceContext;
    }
    if ( v21 )
    {
      v25 = 0;
      if ( g_dwNumTraceEventsLost <= 0xF424A )
        v25 = _InterlockedIncrement((volatile signed __int32 *)&g_dwNumTraceEventsLost);
      if ( v21 > 0 )
        v9 = (unsigned __int16)v21 | 0x80070000;
      else
        v9 = v21;
      v28[0] = v9;
      TraceStringInline(
        14,
        1,
        L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
        1860,
        L"CTrace::TraceEvent",
        *(_QWORD *)v28,
        L"::TraceEvent Failed");
      if ( v25 == g_dwTraceEventsLossLimit )
      {
        StringCchPrintfA(&v44, 0x64u, "%d, Internal Information : latest hr = 0x%x", g_dwNumTraceEventsLost, v9);
        DtcWriteToEventLoggerExUnFilteredA(1u, 0xDu, 0xC0001139, v26, 1u, v29, (const char **)&v38, v31, v32);
        if ( 10 * g_dwTraceEventsLossLimit <= 0xF424A )
          g_dwTraceEventsLossLimit *= 10;
      }
    }
  }
LABEL_40:
  CoTaskMemFree(pv);
  return v9;
}

```

## disassembly

```asm
0x18000862c  push    rbp
0x18000862e  push    rbx
0x18000862f  push    rsi
0x180008630  push    rdi
0x180008631  push    r12
0x180008633  push    r13
0x180008635  push    r14
0x180008637  push    r15
0x180008639  lea     rbp, [rsp-148h]
0x180008641  sub     rsp, 248h
0x180008648  mov     rax, cs:__security_cookie
0x18000864f  xor     rax, rsp
0x180008652  mov     [rbp+180h+var_50], rax
0x180008659  mov     r14d, 1
0x18000865f  mov     r13, r9
0x180008662  mov     eax, r14d
0x180008665  mov     edi, r8d
0x180008668  mov     ebx, edx
0x18000866a  mov     r15, rcx
0x18000866d  lock xadd cs:dword_18016810C, eax
0x180008675  add     eax, r14d
0x180008678  lea     rcx, [rbp+180h+EventTrace]; void *
0x18000867c  xor     edx, edx; Val
0x18000867e  mov     [rsp+280h+var_218], eax
0x180008682  mov     r8d, 140h; Size
0x180008688  call    memset_0
0x18000868d  xor     esi, esi
0x18000868f  lea     r8d, [r14+62h]; Size
0x180008693  xor     edx, edx; Val
0x180008695  mov     [rsp+280h+var_228], rsi
0x18000869a  lea     rcx, [rbp+180h+var_BF]; void *
0x1800086a1  mov     [rsp+280h+var_220], esi
0x1800086a5  mov     [rbp+180h+var_C0], sil
0x1800086ac  call    memset_0
0x1800086b1  lea     rax, [rbp+180h+var_C0]
0x1800086b8  mov     [rsp+280h+pv], rsi
0x1800086bd  mov     [rsp+280h+var_208], rax
0x1800086c2  mov     eax, [r15+8]
0x1800086c6  sub     eax, r14d
0x1800086c9  cmp     eax, 2
0x1800086cc  jbe     short loc_1800086D8
0x1800086ce  mov     ebx, 80004001h
0x1800086d3  jmp     loc_180008A0F
0x1800086d8  mov     eax, [rbp+180h+arg_20]
0x1800086de  add     eax, 0FFFFFFF6h
0x1800086e1  cmp     eax, 0F4h
0x1800086e6  ja      loc_180008A0A
0x1800086ec  lea     r8, [rsp+280h+var_228]; struct _TRACE_CONTEXT *
0x1800086f1  mov     edx, ebx; unsigned int
0x1800086f3  mov     rcx, r15; this
0x1800086f6  call    ?GetTraceContext@CTrace@@QEAAJKPEAU_TRACE_CONTEXT@@@Z
0x1800086fb  mov     [rsp+280h+var_230], eax
0x1800086ff  mov     ebx, eax
0x180008701  test    eax, eax
0x180008703  js      loc_180008A0F
0x180008709  cmp     dword ptr [rsp+280h+var_228], esi
0x18000870d  jz      loc_180008A0F
0x180008713  cmp     dword ptr [rsp+280h+var_228+4], edi
0x180008717  jb      loc_180008A0F
0x18000871d  mov     r14d, esi
0x180008720  lea     r12, aMsdtcService
0x180008727  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000872b  lea     edi, [rsi+2]
0x18000872e  cmp     [r15+8], edi
0x180008732  jnz     short loc_1800087AE
0x180008734  mov     rcx, [r15+690h]; hHandle
0x18000873b  mov     edx, 1388h; dwMilliseconds
0x180008740  call    cs:__imp_WaitForSingleObject
0x180008746  cmp     eax, 0FFFFFFFFh
0x180008749  jnz     short loc_180008769
0x18000874b  lea     rax, aWaitforsingleo_2
0x180008752  mov     ebx, esi
0x180008754  mov     [rsp+280h+var_250], rax
0x180008759  mov     r9d, 6C0h
0x18000875f  mov     [rsp+280h+var_258], esi
0x180008763  mov     [rsp+280h+var_230], ebx
0x180008767  jmp     short loc_180008787
0x180008769  cmp     eax, 102h
0x18000876e  jnz     short loc_1800087AE
0x180008770  lea     rax, aWaitforsingleo
0x180008777  mov     r9d, 6C6h
0x18000877d  mov     [rsp+280h+var_250], rax
0x180008782  mov     qword ptr [rsp+280h+var_258], r14; unsigned int
0x180008787  lea     rax, aCtraceTraceeve
0x18000878e  mov     dword ptr [r15+8], 2
0x180008796  lea     r8, aComComplusDtcD_22
0x18000879d  mov     qword ptr [rsp+280h+var_260], rax
0x1800087a2  mov     edx, edi
0x1800087a4  mov     ecx, 0Eh
0x1800087a9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ
0x1800087ae  xor     edx, edx; Val
0x1800087b0  lea     rcx, [rbp+180h+EventTrace]; void *
0x1800087b4  mov     r8d, 140h; Size
0x1800087ba  call    memset_0
0x1800087bf  mov     eax, [rbp+180h+arg_20]
0x1800087c5  lea     rdi, [rbp+180h+var_1C0]
0x1800087c9  movups  xmm0, xmmword ptr [r13+0]
0x1800087ce  mov     dword ptr [rbp+180h+EventTrace.4], eax
0x1800087d1  lea     rcx, [rbp+180h+arg_28]
0x1800087d8  lea     rax, [rsp+280h+var_218]
0x1800087dd  mov     dword ptr [rbp+180h+EventTrace.28h+4], 120000h
0x1800087e4  movdqu  xmmword ptr [rbp+180h+EventTrace.18h], xmm0
0x1800087e9  mov     [rbp+180h+var_1D0], rax
0x1800087ed  xor     r13d, r13d
0x1800087f0  mov     [rbp+180h+var_1C8], 4
0x1800087f7  mov     eax, [rcx]
0x1800087f9  mov     [rdi+8], eax
0x1800087fc  test    eax, eax
0x1800087fe  jz      short loc_18000881B
0x180008800  mov     rax, [rcx+8]
0x180008804  add     rcx, 10h
0x180008808  mov     [rdi], rax
0x18000880b  add     rdi, 10h
0x18000880f  lea     rax, [rbp+180h+var_D0]
0x180008816  cmp     rdi, rax
0x180008819  jb      short loc_1800087F7
0x18000881b  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA
0x180008822  test    rcx, rcx
0x180008825  jz      short loc_180008844
0x180008827  mov     rax, [rcx]
0x18000882a  lea     rdx, [rsp+280h+pv]
0x18000882f  mov     rax, [rax+38h]
0x180008833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008838  mov     rax, [rsp+280h+pv]
0x18000883d  test    rax, rax
0x180008840  cmovnz  r12, rax
0x180008844  lea     rax, [rbp+180h+var_D0]
0x18000884b  cmp     rdi, rax
0x18000884e  jnb     short loc_18000886B
0x180008850  inc     rsi
0x180008853  cmp     [r12+rsi*2], r13w
0x180008858  jnz     short loc_180008850
0x18000885a  lea     eax, ds:2[rsi*2]
0x180008861  mov     [rdi], r12
0x180008864  mov     [rdi+8], eax
0x180008867  add     rdi, 10h
0x18000886b  mov     rcx, [r15+650h]; TraceHandle
0x180008872  lea     rax, [rbp+180h+EventTrace]
0x180008876  sub     edi, eax
0x180008878  lea     rdx, [rbp+180h+EventTrace]; EventTrace
0x18000887c  mov     dword ptr [rbp+180h+EventTrace.Size], edi
0x18000887f  call    cs:__imp_TraceEvent
0x180008885  mov     r12d, 0F424Ah
0x18000888b  cmp     eax, 8
0x18000888e  jnz     loc_18000893B
0x180008894  lea     ebx, [rax-7]
0x180008897  mov     r9d, cs:?g_dwNumTraceSleepIntervals@@3KA
0x18000889e  cmp     r9d, r12d
0x1800088a1  ja      short loc_1800088B9
0x1800088a3  mov     r14d, ebx
0x1800088a6  lock xadd cs:?g_dwNumTraceSleepIntervals@@3KA, r14d
0x1800088af  mov     r9d, cs:?g_dwNumTraceSleepIntervals@@3KA
0x1800088b6  add     r14d, ebx
0x1800088b9  cmp     r14d, cs:?g_dwTraceSleepIntervalsLimit@@3KA
0x1800088c0  jnz     short loc_180008912
0x1800088c2  lea     r8, aD
0x1800088c9  mov     edx, 64h ; 'd'; unsigned __int64
0x1800088ce  lea     rcx, [rbp+180h+var_C0]; char *
0x1800088d5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ
0x1800088da  mov     edx, 0Dh; unsigned __int16
0x1800088df  lea     rax, [rsp+280h+var_208]
0x1800088e4  mov     [rsp+280h+var_250], rax; char **
0x1800088e9  mov     r8d, 0C0001149h; unsigned int
0x1800088ef  mov     [rsp+280h+var_260], bx; unsigned __int16
0x1800088f4  lea     ecx, [rdx-0Bh]; unsigned __int16
0x1800088f7  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z
0x1800088fc  mov     eax, cs:?g_dwTraceSleepIntervalsLimit@@3KA
0x180008902  lea     ecx, [rax+rax*4]
0x180008905  add     ecx, ecx
0x180008907  cmp     ecx, r12d
0x18000890a  ja      short loc_180008912
0x18000890c  mov     cs:?g_dwTraceSleepIntervalsLimit@@3KA, ecx
0x180008912  mov     ecx, 7D0h; dwMilliseconds
0x180008917  call    cs:__imp_Sleep
0x18000891d  mov     rcx, [r15+650h]; TraceHandle
0x180008924  lea     rdx, [rbp+180h+EventTrace]; EventTrace
0x180008928  call    cs:__imp_TraceEvent
0x18000892e  cmp     eax, 8
0x180008931  jz      loc_180008897
0x180008937  mov     ebx, [rsp+280h+var_230]
0x18000893b  test    eax, eax
0x18000893d  jz      loc_180008A0F
0x180008943  cmp     cs:?g_dwNumTraceEventsLost@@3KA, r12d
0x18000894a  mov     edi, r13d
0x18000894d  mov     esi, 1
0x180008952  ja      short loc_180008960
0x180008954  mov     edi, esi
0x180008956  lock xadd cs:?g_dwNumTraceEventsLost@@3KA, edi
0x18000895e  add     edi, esi
0x180008960  test    eax, eax
0x180008962  jg      short loc_180008968
0x180008964  mov     ebx, eax
0x180008966  jmp     short loc_180008971
0x180008968  movzx   ebx, ax
0x18000896b  or      ebx, 80070000h
0x180008971  lea     rax, aTraceeventFail
0x180008978  mov     r9d, 744h
0x18000897e  mov     [rsp+280h+var_250], rax
0x180008983  lea     r8, aComComplusDtcD_22
0x18000898a  lea     rax, aCtraceTraceeve
0x180008991  mov     [rsp+280h+var_258], ebx; unsigned int
0x180008995  mov     edx, esi
0x180008997  mov     qword ptr [rsp+280h+var_260], rax
0x18000899c  mov     ecx, 0Eh
0x1800089a1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ
0x1800089a6  cmp     edi, cs:?g_dwTraceEventsLossLimit@@3KA
0x1800089ac  jnz     short loc_180008A0F
0x1800089ae  mov     r9d, cs:?g_dwNumTraceEventsLost@@3KA
0x1800089b5  lea     r8, aDInternalInfor
0x1800089bc  mov     edx, 64h ; 'd'; unsigned __int64
0x1800089c1  mov     dword ptr [rsp+280h+var_260], ebx
0x1800089c5  lea     rcx, [rbp+180h+var_C0]; char *
0x1800089cc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ
0x1800089d1  lea     rax, [rsp+280h+var_208]
0x1800089d6  mov     edx, 0Dh; unsigned __int16
0x1800089db  mov     [rsp+280h+var_250], rax; char **
0x1800089e0  mov     ecx, esi; unsigned __int16
0x1800089e2  mov     r8d, 0C0001139h; unsigned int
0x1800089e8  mov     [rsp+280h+var_260], si; unsigned __int16
0x1800089ed  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z
0x1800089f2  mov     eax, cs:?g_dwTraceEventsLossLimit@@3KA
0x1800089f8  lea     ecx, [rax+rax*4]
0x1800089fb  add     ecx, ecx
0x1800089fd  cmp     ecx, r12d
0x180008a00  ja      short loc_180008A0F
0x180008a02  mov     cs:?g_dwTraceEventsLossLimit@@3KA, ecx
0x180008a08  jmp     short loc_180008A0F
0x180008a0a  mov     ebx, 80070057h
0x180008a0f  mov     rcx, [rsp+280h+pv]; pv
0x180008a14  call    cs:__imp_CoTaskMemFree
0x180008a1a  mov     eax, ebx
0x180008a1c  mov     rcx, [rbp+180h+var_50]
0x180008a23  xor     rcx, rsp; StackCookie
0x180008a26  call    __security_check_cookie
0x180008a2b  add     rsp, 248h
0x180008a32  pop     r15
0x180008a34  pop     r14
0x180008a36  pop     r13
0x180008a38  pop     r12
0x180008a3a  pop     rdi
0x180008a3b  pop     rsi
0x180008a3c  pop     rbx
0x180008a3d  pop     rbp
0x180008a3e  retn
```
