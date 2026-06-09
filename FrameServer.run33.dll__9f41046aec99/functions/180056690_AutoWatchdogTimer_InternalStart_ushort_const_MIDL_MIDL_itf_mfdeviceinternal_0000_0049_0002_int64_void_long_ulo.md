# AutoWatchdogTimer::InternalStart(ushort const *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0049_0002,__int64,void *,long,ulong,unsigned __int64 *)

- ea: `0x180056690`
- end: `0x1800568bd`
- name: `?InternalStart@AutoWatchdogTimer@@MEAAXPEBGW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0049_0002@@_JPEAXJKPEA_K@Z`
- size: `557`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800b46f0`
- `0x1800b4860`
- `0x1800b49a0`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180007bcc`
- `0x1800564f0`
- `0x18005654c`
- `0x18005659c`
- `0x180056690`
- `0x180061944`
- `0x180061b98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005686a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005686a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005681f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005681f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180056848`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180056848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056700`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056700`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180056890`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180056890`
- `MFPlat!MFGetSystemTime` at `0x180056773`
- `MFPlat!MFGetSystemTime` at `0x180056773`

## pseudocode

```c
void __fastcall AutoWatchdogTimer::InternalStart(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        __int64 a8)
{
  __int64 v8; // rbp
  unsigned __int16 *v11; // rcx
  const unsigned __int16 *v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  char AdjustedWatchdogDuration; // si
  MFTIME v17; // rax
  int v18; // edx
  int v19; // ecx
  bool v20; // zf
  __int64 v21; // rax
  __int64 ScopeString; // rax
  __int64 OpString; // rax
  __int64 v24; // rdx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  int LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp-E8h] BYREF
  _EXCEPTION_RECORD pExceptionRecord; // [rsp+60h] [rbp-D8h] BYREF

  pftDueTime = (struct _FILETIME)a4;
  v8 = a1 + 216;
  v11 = (unsigned __int16 *)(a1 + 216);
  v13 = a2;
  if ( !a2 )
    v13 = L"<none>";
  StringCchCopyW(v11, 0x104u, v13);
  *(_QWORD *)(a1 + 72) = a5;
  *(_DWORD *)(a1 + 80) = a6;
  *(_DWORD *)(a1 + 52) = a3;
  *(_DWORD *)(a1 + 740) = GetCurrentThreadId();
  if ( a7 )
  {
    memset_0((void *)(a1 + 88), 0, 0x78u);
    v14 = 15;
    if ( a7 < 0xF )
      v14 = a7;
    v15 = 0;
    *(_DWORD *)(a1 + 84) = v14;
    do
    {
      *(_QWORD *)(a1 + 8 * v15 + 88) = *(_QWORD *)(a8 + 8 * v15);
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < *(_DWORD *)(a1 + 84) );
  }
  if ( !*(_BYTE *)(a1 + 48) )
  {
    AdjustedWatchdogDuration = a4;
    if ( !*(_BYTE *)(a1 + 737) )
      AdjustedWatchdogDuration = GetAdjustedWatchdogDuration(a4);
    v17 = MFGetSystemTime();
    v20 = *(_BYTE *)(a1 + 736) == 0;
    *(_QWORD *)(a1 + 208) = v17;
    if ( v20 )
    {
      if ( (Microsoft_Windows_MF_FrameServerEnableBits & 1) != 0 )
      {
        v21 = -a4;
        if ( a4 > 0 )
          LOBYTE(v21) = a4;
        McTemplateU0qxqxz_EventWriteTransfer(v19, v18, *(_DWORD *)(a1 + 56), *(_QWORD *)(a1 + 72), a3, v21, v8);
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        ScopeString = GetScopeString(*(unsigned int *)(a1 + 56));
        OpString = GetOpString(*(unsigned int *)(a1 + 52), ScopeString);
        WPP_SF_qssiqDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          OpString,
          v24,
          AdjustedWatchdogDuration,
          *(_QWORD *)(a1 + 72),
          *(_DWORD *)(a1 + 80),
          v8);
      }
    }
    ThreadpoolTimer = CreateThreadpoolTimer(AutoWatchdogTimer::WatchdogTimerCallback, (PVOID)a1, 0);
    *(_QWORD *)(a1 + 64) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime.dwLowDateTime = a4;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    }
    else
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionFlags = 1;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      pExceptionRecord.ExceptionCode = LastError;
      pExceptionRecord.ExceptionAddress = (PVOID)a1;
      RaiseFailFastException(&pExceptionRecord, 0, 1u);
    }
  }
}

```

## disassembly

```asm
0x180056690  mov     [rsp+arg_10], rbx
0x180056695  push    rbp
0x180056696  push    rsi
0x180056697  push    rdi
0x180056698  push    r14
0x18005669a  push    r15
0x18005669c  sub     rsp, 110h
0x1800566a3  mov     rax, cs:__security_cookie
0x1800566aa  xor     rax, rsp
0x1800566ad  mov     [rsp+138h+var_38], rax
0x1800566b5  mov     qword ptr [rsp+138h+pftDueTime.dwLowDateTime], r9
0x1800566ba  lea     rbp, [rcx+0D8h]
0x1800566c1  mov     r15d, r8d
0x1800566c4  mov     rbx, rcx
0x1800566c7  mov     rcx, rbp; unsigned __int16 *
0x1800566ca  mov     rdi, r9
0x1800566cd  mov     r8, rdx
0x1800566d0  test    rdx, rdx
0x1800566d3  jnz     short loc_1800566DC
0x1800566d5  lea     r8, aNone; "<none>"
0x1800566dc  mov     edx, 104h; unsigned __int64
0x1800566e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800566e6  mov     rax, [rsp+138h+arg_20]
0x1800566ee  mov     [rbx+48h], rax
0x1800566f2  mov     eax, [rsp+138h+arg_28]
0x1800566f9  mov     [rbx+50h], eax
0x1800566fc  mov     [rbx+34h], r15d
0x180056700  call    cs:__imp_GetCurrentThreadId
0x180056706  mov     esi, [rsp+138h+arg_30]
0x18005670d  mov     [rbx+2E4h], eax
0x180056713  test    esi, esi
0x180056715  jz      short loc_180056752
0x180056717  mov     r14, [rsp+138h+arg_38]
0x18005671f  lea     rcx, [rbx+58h]; void *
0x180056723  xor     edx, edx; Val
0x180056725  lea     r8d, [rdx+78h]; Size
0x180056729  call    memset_0
0x18005672e  mov     eax, 0Fh
0x180056733  cmp     esi, eax
0x180056735  jnb     short loc_180056739
0x180056737  mov     eax, esi
0x180056739  xor     edx, edx
0x18005673b  mov     [rbx+54h], eax
0x18005673e  test    eax, eax
0x180056740  jz      short loc_180056752
0x180056742  mov     rax, [r14+rdx*8]
0x180056746  mov     [rbx+rdx*8+58h], rax
0x18005674b  inc     edx
0x18005674d  cmp     edx, [rbx+54h]
0x180056750  jb      short loc_180056742
0x180056752  cmp     byte ptr [rbx+30h], 0
0x180056756  jnz     loc_180056896
0x18005675c  cmp     byte ptr [rbx+2E1h], 0
0x180056763  mov     rsi, rdi
0x180056766  jnz     short loc_180056773
0x180056768  mov     rcx, rdi; __int64
0x18005676b  call    ?GetAdjustedWatchdogDuration@@YA_J_J@Z; GetAdjustedWatchdogDuration(__int64)
0x180056770  mov     rsi, rax
0x180056773  call    cs:__imp_MFGetSystemTime
0x180056779  cmp     byte ptr [rbx+2E0h], 0
0x180056780  mov     [rbx+0D0h], rax
0x180056787  jnz     loc_180056812
0x18005678d  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, 1
0x180056794  jz      short loc_1800567BC
0x180056796  mov     r9, [rbx+48h]
0x18005679a  mov     rax, rdi
0x18005679d  mov     r8d, [rbx+38h]
0x1800567a1  neg     rax
0x1800567a4  mov     qword ptr [rsp+138h+var_108], rbp
0x1800567a9  cmovs   rax, rdi
0x1800567ad  mov     [rsp+138h+var_110], rax
0x1800567b2  mov     dword ptr [rsp+138h+var_118], r15d
0x1800567b7  call    McTemplateU0qxqxz_EventWriteTransfer
0x1800567bc  cmp     cs:byte_18010EC4D, 8
0x1800567c3  jb      short loc_180056812
0x1800567c5  mov     ecx, [rbx+38h]
0x1800567c8  call    GetScopeString
0x1800567cd  mov     ecx, [rbx+34h]
0x1800567d0  mov     rdx, rax
0x1800567d3  call    GetOpString
0x1800567d8  mov     ecx, [rbx+50h]
0x1800567db  mov     r9, rbx
0x1800567de  mov     [rsp+138h+var_F0], rbp; __int64
0x1800567e3  mov     dword ptr [rsp+138h+var_F8], ecx; char
0x1800567e7  mov     rcx, [rbx+48h]
0x1800567eb  mov     qword ptr [rsp+138h+var_100], rcx; char
0x1800567f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567f7  mov     qword ptr [rsp+138h+var_108], rsi; char
0x1800567fc  mov     [rsp+138h+var_110], rdx; __int64
0x180056801  mov     [rsp+138h+var_118], rax; __int64
0x180056806  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18005680d  call    WPP_SF_qssiqDS
0x180056812  xor     r8d, r8d; pcbe
0x180056815  lea     rcx, ?WatchdogTimerCallback@AutoWatchdogTimer@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005681c  mov     rdx, rbx; pv
0x18005681f  call    cs:__imp_CreateThreadpoolTimer
0x180056825  mov     [rbx+40h], rax
0x180056829  test    rax, rax
0x18005682c  jz      short loc_180056850
0x18005682e  mov     ecx, [rsp+138h+pftDueTime.dwHighDateTime]
0x180056832  lea     rdx, [rsp+138h+pftDueTime]; pftDueTime
0x180056837  mov     [rsp+138h+pftDueTime.dwHighDateTime], ecx
0x18005683b  xor     r9d, r9d; msWindowLength
0x18005683e  mov     rcx, rax; pti
0x180056841  mov     [rsp+138h+pftDueTime.dwLowDateTime], edi
0x180056845  xor     r8d, r8d; msPeriod
0x180056848  call    cs:__imp_SetThreadpoolTimer
0x18005684e  jmp     short loc_180056896
0x180056850  xor     edx, edx; Val
0x180056852  lea     rcx, [rsp+138h+pExceptionRecord]; void *
0x180056857  mov     r8d, 98h; Size
0x18005685d  call    memset_0
0x180056862  mov     [rsp+138h+pExceptionRecord.ExceptionFlags], 1
0x18005686a  call    cs:__imp_GetLastError
0x180056870  test    eax, eax
0x180056872  jle     short loc_18005687C
0x180056874  movzx   eax, ax
0x180056877  or      eax, 80070000h
0x18005687c  xor     edx, edx; pContextRecord
0x18005687e  mov     [rsp+138h+pExceptionRecord.ExceptionCode], eax
0x180056882  lea     rcx, [rsp+138h+pExceptionRecord]; pExceptionRecord
0x180056887  mov     [rsp+138h+pExceptionRecord.ExceptionAddress], rbx
0x18005688c  lea     r8d, [rdx+1]; dwFlags
0x180056890  call    cs:__imp_RaiseFailFastException
0x180056896  mov     rcx, [rsp+138h+var_38]
0x18005689e  xor     rcx, rsp; StackCookie
0x1800568a1  call    __security_check_cookie
0x1800568a6  mov     rbx, [rsp+138h+arg_10]
0x1800568ae  add     rsp, 110h
0x1800568b5  pop     r15
0x1800568b7  pop     r14
0x1800568b9  pop     rdi
0x1800568ba  pop     rsi
0x1800568bb  pop     rbp
0x1800568bc  retn
```
