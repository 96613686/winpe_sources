# CAudioClient::InitializeInternalHelper(_AUDCLNT_SHAREMODE,ulong &,__int64,__int64,tWAVEFORMATEX const *,_GUID const *,SYSTEM_AUDIO_STREAM_TYPE &,SYSTEM_AUDIO_STREAM *)

- ea: `0x180047344`
- end: `0x18004779a`
- name: `?InitializeInternalHelper@CAudioClient@@IEAAJW4_AUDCLNT_SHAREMODE@@AEAK_J2PEBUtWAVEFORMATEX@@PEBU_GUID@@AEAW4SYSTEM_AUDIO_STREAM_TYPE@@PEAUSYSTEM_AUDIO_STREAM@@@Z`
- size: `1110`
- prototype: `__int64 __fastcall(CAudioClient *__hidden this, enum _AUDCLNT_SHAREMODE, unsigned int *, __int64, __int64, const struct tWAVEFORMATEX *, const struct _GUID *, enum SYSTEM_AUDIO_STREAM_TYPE *, struct SYSTEM_AUDIO_STREAM *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180047178`

## callees

- `0x18000cae4`
- `0x180010a90`
- `0x1800165ac`
- `0x1800469e8`
- `0x180046a14`
- `0x180047344`
- `0x180049300`
- `0x18006a838`
- `0x18006a9bc`
- `0x180087e80`
- `0x180088ce8`
- `0x180094d20`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004754e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004776f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004754e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004776f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047401`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800475a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047401`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800475a5`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800473fb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004759f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800473fb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004759f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAudioClient::InitializeInternalHelper(
        CAudioClient *this,
        enum _AUDCLNT_SHAREMODE a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        const struct tWAVEFORMATEX *a6,
        const struct _GUID *a7,
        enum SYSTEM_AUDIO_STREAM_TYPE *a8,
        struct SYSTEM_AUDIO_STREAM *a9)
{
  CInProcLogger *v11; // rcx
  CAudioClient *v12; // rdi
  int v13; // ebx
  __int64 *v14; // rdx
  CInProcLogger *v16; // rcx
  int v17; // eax
  int v18; // eax
  int *v19; // rax
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-E0h]
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  STRSAFE_LPWSTR v25; // [rsp+60h] [rbp-A0h] BYREF
  STRSAFE_LPWSTR v26; // [rsp+68h] [rbp-98h] BYREF
  char *v27; // [rsp+70h] [rbp-90h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-88h]
  CAudioClient *v29; // [rsp+80h] [rbp-80h]
  char v30; // [rsp+88h] [rbp-78h]
  __int64 v31[7]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v32; // [rsp+C8h] [rbp-38h]
  int v33[316]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID BackTrace[2]; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int128 v35; // [rsp+5D0h] [rbp+4D0h]
  wchar_t pszDest[1024]; // [rsp+5E0h] [rbp+4E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E38h] [rbp+D38h]

  v29 = this;
  v27 = (char *)this + 440;
  lpCriticalSection = 0;
  CPrivCritSecLock::Lock((CPrivCritSecLock *)&v27);
  v32 = 0;
  *(_OWORD *)BackTrace = 0;
  v35 = 0;
  v26 = pszDest;
  v25 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  CurrentThreadId = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v26, (unsigned __int64 *)&v25, 0, L"[%d]:", CurrentThreadId);
  StringCchPrintfExW(v26, (unsigned __int64)v25, &v26, (unsigned __int64 *)&v25, 0, L"E1: %p", v29);
  StringCchPrintfW(v26, (unsigned __int64)v25, L"[%p %p %p %p]", BackTrace[0], BackTrace[1], v35);
  CInProcLogger::AddLog(v11, pszDest);
  memset_0(v33, 0, 0x4E8u);
  v12 = v29;
  v13 = CAudioClient::SetupAudioStreamWithAudioSrv(
          v29,
          a4,
          a5,
          (__int64)a6,
          (__int64)a7,
          (__int64)a8,
          (int)v33,
          (__int64)v31);
  if ( v13 < 0 )
  {
    if ( v32 )
    {
      v14 = v31;
      LOBYTE(v14) = v32 != v31;
      (*(void (__fastcall **)(__int64 *, __int64 *))(*v32 + 32))(v32, v14);
      v32 = 0;
    }
    goto LABEL_4;
  }
  v29 = (CAudioClient *)v31;
  v30 = 1;
  *(_OWORD *)BackTrace = 0;
  v35 = 0;
  v25 = pszDest;
  v26 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  LODWORD(v23) = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v25, (unsigned __int64 *)&v26, 0, L"[%d]:", v23);
  LODWORD(v24) = v33[0];
  StringCchPrintfExW(v25, (unsigned __int64)v26, &v25, (unsigned __int64 *)&v26, 0, L"E2: %p (%x)", v12, v24);
  v21 = (int)BackTrace[1];
  StringCchPrintfW(v25, (unsigned __int64)v26, L"[%p %p %p %p]", BackTrace[0]);
  CInProcLogger::AddLog(v16, pszDest);
  v17 = *((_DWORD *)v12 + 209);
  if ( v17 )
  {
    if ( v17 == 1 )
    {
      v19 = v33;
      v20 = 9;
      do
      {
        *(_OWORD *)a9 = *(_OWORD *)v19;
        *((_OWORD *)a9 + 1) = *((_OWORD *)v19 + 1);
        *((_OWORD *)a9 + 2) = *((_OWORD *)v19 + 2);
        *((_OWORD *)a9 + 3) = *((_OWORD *)v19 + 3);
        *((_OWORD *)a9 + 4) = *((_OWORD *)v19 + 4);
        *((_OWORD *)a9 + 5) = *((_OWORD *)v19 + 5);
        *((_OWORD *)a9 + 6) = *((_OWORD *)v19 + 6);
        *((_OWORD *)a9 + 7) = *((_OWORD *)v19 + 7);
        a9 = (struct SYSTEM_AUDIO_STREAM *)((char *)a9 + 128);
        v19 += 32;
        --v20;
      }
      while ( v20 );
      *(_OWORD *)a9 = *(_OWORD *)v19;
      *((_OWORD *)a9 + 1) = *((_OWORD *)v19 + 1);
      *((_OWORD *)a9 + 2) = *((_OWORD *)v19 + 2);
      *((_OWORD *)a9 + 3) = *((_OWORD *)v19 + 3);
      *((_OWORD *)a9 + 4) = *((_OWORD *)v19 + 4);
      *((_OWORD *)a9 + 5) = *((_OWORD *)v19 + 5);
      *((_QWORD *)a9 + 12) = *((_QWORD *)v19 + 12);
    }
  }
  else
  {
    v18 = CAudioClient::SetupStreamingEndpoint(v12, (struct SYSTEM_AUDIO_STREAM *)v33);
    v13 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A9,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)(unsigned int)v18,
        v21);
      std::_Func_class<void,>::operator()(v31);
      std::_Func_class<void,>::_Tidy(v31);
LABEL_4:
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return (unsigned int)v13;
    }
  }
  *((_BYTE *)v12 + 832) = 1;
  std::_Func_class<void,>::_Tidy(v31);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180047344  push    rbp
0x180047346  push    rbx
0x180047347  push    rsi
0x180047348  push    rdi
0x180047349  push    r12
0x18004734b  push    r13
0x18004734d  push    r14
0x18004734f  push    r15
0x180047351  lea     rbp, [rsp-0CF8h]
0x180047359  sub     rsp, 0DF8h
0x180047360  mov     rax, cs:__security_cookie
0x180047367  xor     rax, rsp
0x18004736a  mov     [rbp+0D30h+var_50], rax
0x180047371  mov     r12, r9
0x180047374  mov     r15, r8
0x180047377  mov     r14d, edx
0x18004737a  mov     rax, rcx
0x18004737d  mov     [rbp+0D30h+var_DB0], rcx
0x180047381  mov     rsi, [rbp+0D30h+arg_28]
0x180047388  mov     rdi, [rbp+0D30h+arg_30]
0x18004738f  mov     rbx, [rbp+0D30h+arg_38]
0x180047396  mov     r13, [rbp+0D30h+arg_40]
0x18004739d  add     rax, 1B8h
0x1800473a3  mov     [rsp+0E30h+var_DC0], rax
0x1800473a8  mov     [rsp+0E30h+lpCriticalSection], 0
0x1800473b1  lea     rcx, [rsp+0E30h+var_DC0]; this
0x1800473b6  call    ?Lock@CPrivCritSecLock@@QEAAXXZ; CPrivCritSecLock::Lock(void)
0x1800473bb  nop
0x1800473bc  mov     [rbp+0D30h+var_D68], 0
0x1800473c4  xorps   xmm0, xmm0
0x1800473c7  movups  xmmword ptr [rbp+0D30h+BackTrace], xmm0
0x1800473ce  movups  [rbp+0D30h+var_860], xmm0
0x1800473d5  lea     rax, [rbp+0D30h+pszDest]
0x1800473dc  mov     [rsp+0E30h+var_DC8], rax
0x1800473e1  mov     [rsp+0E30h+var_DD0], 400h
0x1800473ea  xor     r9d, r9d; BackTraceHash
0x1800473ed  lea     r8, [rbp+0D30h+BackTrace]; BackTrace
0x1800473f4  lea     edx, [r9+4]; FramesToCapture
0x1800473f8  lea     ecx, [rdx-2]; FramesToSkip
0x1800473fb  call    cs:__imp_RtlCaptureStackBackTrace
0x180047401  call    cs:__imp_GetCurrentThreadId
0x180047407  mov     dword ptr [rsp+0E30h+var_E08+8], eax
0x18004740b  lea     rax, aD; "[%d]:"
0x180047412  mov     qword ptr [rsp+0E30h+var_E08], rax; unsigned __int16 *
0x180047417  mov     qword ptr [rsp+0E30h+var_E10], 0; unsigned int
0x180047420  lea     r9, [rsp+0E30h+var_DD0]; unsigned __int64 *
0x180047425  lea     r8, [rsp+0E30h+var_DC8]; unsigned __int16 **
0x18004742a  mov     edx, 400h; unsigned __int64
0x18004742f  lea     rcx, [rbp+0D30h+pszDest]; pszDest
0x180047436  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004743b  mov     rax, [rbp+0D30h+var_DB0]
0x18004743f  mov     qword ptr [rsp+0E30h+var_E08+8], rax
0x180047444  lea     rax, aE1P; "E1: %p"
0x18004744b  mov     qword ptr [rsp+0E30h+var_E08], rax; unsigned __int16 *
0x180047450  mov     qword ptr [rsp+0E30h+var_E10], 0; unsigned int
0x180047459  lea     r9, [rsp+0E30h+var_DD0]; unsigned __int64 *
0x18004745e  lea     r8, [rsp+0E30h+var_DC8]; unsigned __int16 **
0x180047463  mov     rdx, [rsp+0E30h+var_DD0]; unsigned __int64
0x180047468  mov     rcx, [rsp+0E30h+var_DC8]; pszDest
0x18004746d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180047472  mov     rax, qword ptr [rbp+0D30h+var_860+8]
0x180047479  mov     qword ptr [rsp+0E30h+var_E08+8], rax
0x18004747e  mov     rax, qword ptr [rbp+0D30h+var_860]
0x180047485  mov     qword ptr [rsp+0E30h+var_E08], rax
0x18004748a  mov     rax, [rbp+0D30h+BackTrace+8]
0x180047491  mov     qword ptr [rsp+0E30h+var_E10], rax
0x180047496  mov     r9, [rbp+0D30h+BackTrace]
0x18004749d  lea     r8, aPPPP; "[%p %p %p %p]"
0x1800474a4  mov     rdx, [rsp+0E30h+var_DD0]; unsigned __int64
0x1800474a9  mov     rcx, [rsp+0E30h+var_DC8]; unsigned __int16 *
0x1800474ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800474b3  lea     rdx, [rbp+0D30h+pszDest]; unsigned __int16 *
0x1800474ba  call    ?AddLog@CInProcLogger@@QEAAXPEBG@Z; CInProcLogger::AddLog(ushort const *)
0x1800474bf  xor     edx, edx; Val
0x1800474c1  mov     r8d, 4E8h; Size
0x1800474c7  lea     rcx, [rbp+0D30h+var_D60]; void *
0x1800474cb  call    memset_0
0x1800474d0  lea     rax, [rbp+0D30h+var_DA0]
0x1800474d4  mov     [rsp+0E30h+var_DE0], rax; __int64
0x1800474d9  lea     rax, [rbp+0D30h+var_D60]
0x1800474dd  mov     qword ptr [rsp+0E30h+var_DE8], rax; int
0x1800474e2  mov     [rsp+0E30h+var_DF0], rbx; __int64
0x1800474e7  mov     [rsp+0E30h+var_DF8], rdi; __int64
0x1800474ec  mov     qword ptr [rsp+0E30h+var_E08+8], rsi; __int64
0x1800474f1  mov     rax, [rbp+0D30h+arg_20]
0x1800474f8  mov     qword ptr [rsp+0E30h+var_E08], rax; __int64
0x1800474fd  mov     qword ptr [rsp+0E30h+var_E10], r12; __int64
0x180047502  mov     r9, r15
0x180047505  mov     r8d, r14d
0x180047508  lea     rdx, [rsp+0E30h+var_DC0]
0x18004750d  mov     rdi, [rbp+0D30h+var_DB0]
0x180047511  mov     rcx, rdi; this
0x180047514  call    ?SetupAudioStreamWithAudioSrv@CAudioClient@@AEAAJAEAVCPrivCritSecLock@@W4_AUDCLNT_SHAREMODE@@AEAK_J3PEBUtWAVEFORMATEX@@PEBU_GUID@@AEAW4SYSTEM_AUDIO_STREAM_TYPE@@AEAUSYSTEM_AUDIO_STREAM@@AEAV?$function@$$A6AXXZ@std@@@Z; CAudioClient::SetupAudioStreamWithAudioSrv(CPrivCritSecLock &,_AUDCLNT_SHAREMODE,ulong &,__int64,__int64,tWAVEFORMATEX const *,_GUID const *,SYSTEM_AUDIO_STREAM_TYPE &,SYSTEM_AUDIO_STREAM &,std::function<void (void)> &)
0x180047519  mov     ebx, eax
0x18004751b  xor     esi, esi
0x18004751d  test    eax, eax
0x18004751f  jns     short loc_18004755B
0x180047521  mov     rcx, [rbp+0D30h+var_D68]
0x180047525  test    rcx, rcx
0x180047528  jz      short loc_180047544
0x18004752a  mov     rax, [rcx]
0x18004752d  lea     rdx, [rbp+0D30h+var_DA0]
0x180047531  cmp     rcx, rdx
0x180047534  setnz   dl
0x180047537  mov     rax, [rax+20h]
0x18004753b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047540  mov     [rbp+0D30h+var_D68], rsi
0x180047544  mov     rcx, [rsp+0E30h+lpCriticalSection]; lpCriticalSection
0x180047549  test    rcx, rcx
0x18004754c  jz      short loc_180047554
0x18004754e  call    cs:__imp_LeaveCriticalSection
0x180047554  mov     eax, ebx
0x180047556  jmp     loc_180047777
0x18004755b  lea     rax, [rbp+0D30h+var_DA0]
0x18004755f  mov     [rbp+0D30h+var_DB0], rax
0x180047563  mov     [rbp+0D30h+var_DA8], 1
0x180047567  xorps   xmm0, xmm0
0x18004756a  movups  xmmword ptr [rbp+0D30h+BackTrace], xmm0
0x180047571  movups  [rbp+0D30h+var_860], xmm0
0x180047578  lea     rax, [rbp+0D30h+pszDest]
0x18004757f  mov     [rsp+0E30h+var_DD0], rax
0x180047584  mov     ebx, 400h
0x180047589  mov     [rsp+0E30h+var_DC8], rbx
0x18004758e  xor     r9d, r9d; BackTraceHash
0x180047591  lea     r8, [rbp+0D30h+BackTrace]; BackTrace
0x180047598  lea     edx, [r9+4]; FramesToCapture
0x18004759c  lea     ecx, [rdx-2]; FramesToSkip
0x18004759f  call    cs:__imp_RtlCaptureStackBackTrace
0x1800475a5  call    cs:__imp_GetCurrentThreadId
0x1800475ab  mov     dword ptr [rsp+0E30h+var_E08+8], eax
0x1800475af  lea     rax, aD; "[%d]:"
0x1800475b6  mov     qword ptr [rsp+0E30h+var_E08], rax; unsigned __int16 *
0x1800475bb  mov     qword ptr [rsp+0E30h+var_E10], rsi; unsigned int
0x1800475c0  lea     r9, [rsp+0E30h+var_DC8]; unsigned __int64 *
0x1800475c5  lea     r8, [rsp+0E30h+var_DD0]; unsigned __int16 **
0x1800475ca  mov     edx, ebx; unsigned __int64
0x1800475cc  lea     rcx, [rbp+0D30h+pszDest]; pszDest
0x1800475d3  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800475d8  mov     eax, [rbp+0D30h+var_D60]
0x1800475db  mov     dword ptr [rsp+0E30h+var_DF8], eax
0x1800475df  mov     qword ptr [rsp+0E30h+var_E08+8], rdi
0x1800475e4  lea     rax, aE2PX; "E2: %p (%x)"
0x1800475eb  mov     qword ptr [rsp+0E30h+var_E08], rax; unsigned __int16 *
0x1800475f0  mov     qword ptr [rsp+0E30h+var_E10], rsi; unsigned int
0x1800475f5  lea     r9, [rsp+0E30h+var_DC8]; unsigned __int64 *
0x1800475fa  lea     r8, [rsp+0E30h+var_DD0]; unsigned __int16 **
0x1800475ff  mov     rdx, [rsp+0E30h+var_DC8]; unsigned __int64
0x180047604  mov     rcx, [rsp+0E30h+var_DD0]; pszDest
0x180047609  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004760e  mov     rax, qword ptr [rbp+0D30h+var_860+8]
0x180047615  mov     qword ptr [rsp+0E30h+var_E08+8], rax
0x18004761a  mov     rax, qword ptr [rbp+0D30h+var_860]
0x180047621  mov     qword ptr [rsp+0E30h+var_E08], rax
0x180047626  mov     rax, [rbp+0D30h+BackTrace+8]
0x18004762d  mov     qword ptr [rsp+0E30h+var_E10], rax; int
0x180047632  mov     r9, [rbp+0D30h+BackTrace]
0x180047639  lea     r8, aPPPP; "[%p %p %p %p]"
0x180047640  mov     rdx, [rsp+0E30h+var_DC8]; unsigned __int64
0x180047645  mov     rcx, [rsp+0E30h+var_DD0]; unsigned __int16 *
0x18004764a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004764f  lea     rdx, [rbp+0D30h+pszDest]; unsigned __int16 *
0x180047656  call    ?AddLog@CInProcLogger@@QEAAXPEBG@Z; CInProcLogger::AddLog(ushort const *)
0x18004765b  mov     eax, [rdi+344h]
0x180047661  test    eax, eax
0x180047663  jnz     short loc_1800476AF
0x180047665  lea     rdx, [rbp+0D30h+var_D60]; struct SYSTEM_AUDIO_STREAM *
0x180047669  mov     rcx, rdi; this
0x18004766c  call    ?SetupStreamingEndpoint@CAudioClient@@AEAAJAEAUSYSTEM_AUDIO_STREAM@@@Z; CAudioClient::SetupStreamingEndpoint(SYSTEM_AUDIO_STREAM &)
0x180047671  mov     ebx, eax
0x180047673  test    eax, eax
0x180047675  jns     loc_180047754
0x18004767b  mov     rcx, [rbp+0D38h]; this
0x180047682  mov     r9d, eax; char *
0x180047685  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x18004768c  mov     edx, 4A9h; void *
0x180047691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047696  nop
0x180047697  lea     rcx, [rbp+0D30h+var_DA0]
0x18004769b  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1800476a0  nop
0x1800476a1  lea     rcx, [rbp+0D30h+var_DA0]
0x1800476a5  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800476aa  jmp     loc_180047544
0x1800476af  cmp     eax, 1
0x1800476b2  jnz     loc_180047754
0x1800476b8  lea     rax, [rbp+0D30h+var_D60]
0x1800476bc  mov     ecx, 9
0x1800476c1  lea     edx, [rcx+77h]
0x1800476c4  movups  xmm0, xmmword ptr [rax]
0x1800476c7  movups  xmmword ptr [r13+0], xmm0
0x1800476cc  movups  xmm1, xmmword ptr [rax+10h]
0x1800476d0  movups  xmmword ptr [r13+10h], xmm1
0x1800476d5  movups  xmm0, xmmword ptr [rax+20h]
0x1800476d9  movups  xmmword ptr [r13+20h], xmm0
0x1800476de  movups  xmm1, xmmword ptr [rax+30h]
0x1800476e2  movups  xmmword ptr [r13+30h], xmm1
0x1800476e7  movups  xmm0, xmmword ptr [rax+40h]
0x1800476eb  movups  xmmword ptr [r13+40h], xmm0
0x1800476f0  movups  xmm1, xmmword ptr [rax+50h]
0x1800476f4  movups  xmmword ptr [r13+50h], xmm1
0x1800476f9  movups  xmm0, xmmword ptr [rax+60h]
0x1800476fd  movups  xmmword ptr [r13+60h], xmm0
0x180047702  movups  xmm1, xmmword ptr [rax+70h]
0x180047706  movups  xmmword ptr [r13+70h], xmm1
0x18004770b  add     r13, rdx
0x18004770e  add     rax, rdx
0x180047711  sub     rcx, 1
0x180047715  jnz     short loc_1800476C4
0x180047717  movups  xmm0, xmmword ptr [rax]
0x18004771a  movups  xmmword ptr [r13+0], xmm0
0x18004771f  movups  xmm1, xmmword ptr [rax+10h]
0x180047723  movups  xmmword ptr [r13+10h], xmm1
0x180047728  movups  xmm0, xmmword ptr [rax+20h]
0x18004772c  movups  xmmword ptr [r13+20h], xmm0
0x180047731  movups  xmm1, xmmword ptr [rax+30h]
0x180047735  movups  xmmword ptr [r13+30h], xmm1
0x18004773a  movups  xmm0, xmmword ptr [rax+40h]
0x18004773e  movups  xmmword ptr [r13+40h], xmm0
0x180047743  movups  xmm1, xmmword ptr [rax+50h]
0x180047747  movups  xmmword ptr [r13+50h], xmm1
0x18004774c  mov     rax, [rax+60h]
0x180047750  mov     [r13+60h], rax
0x180047754  mov     byte ptr [rdi+340h], 1
0x18004775b  lea     rcx, [rbp+0D30h+var_DA0]
0x18004775f  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180047764  nop
0x180047765  mov     rcx, [rsp+0E30h+lpCriticalSection]; lpCriticalSection
0x18004776a  test    rcx, rcx
0x18004776d  jz      short loc_180047775
0x18004776f  call    cs:__imp_LeaveCriticalSection
0x180047775  xor     eax, eax
0x180047777  mov     rcx, [rbp+0D30h+var_50]
0x18004777e  xor     rcx, rsp; StackCookie
0x180047781  call    __security_check_cookie
0x180047786  add     rsp, 0DF8h
0x18004778d  pop     r15
0x18004778f  pop     r14
0x180047791  pop     r13
0x180047793  pop     r12
0x180047795  pop     rdi
0x180047796  pop     rsi
0x180047797  pop     rbx
0x180047798  pop     rbp
0x180047799  retn
```
