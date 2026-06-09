# CStreamAggregator::CStreamAggregator(long *)

- ea: `0x180035484`
- end: `0x180035761`
- name: `??0CStreamAggregator@@QEAA@PEAJ@Z`
- size: `733`
- prototype: `CStreamAggregator *__fastcall(CStreamAggregator *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180034274`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180035484`
- `0x180051ce4`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035499`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035499`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003557e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003565b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003557e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003565b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035674`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800354e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800355c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800356a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800354e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800355c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800356a3`

## pseudocode

```c
CStreamAggregator *__fastcall CStreamAggregator::CStreamAggregator(CStreamAggregator *this, int *a2)
{
  signed int v4; // ebx
  CallStackTracing *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  HANDLE v14; // rax
  signed int v15; // eax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v20; // [rsp+40h] [rbp+8h] BYREF

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  v4 = *a2;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v20, "CStreamAggregator::CStreamAggregator", 2483);
  if ( v4 >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 6) = EventW;
    if ( EventW )
      goto LABEL_26;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_26:
      v14 = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 5) = v14;
      if ( !v14 )
      {
        v15 = GetLastError();
        v4 = v15;
        if ( v15 > 0 )
          v4 = (unsigned __int16)v15 | 0x80070000;
        if ( v4 < 0 )
        {
          v16 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v17;
            if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
            {
              v16 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v16);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamAggregator::CStreamAggregator", 2504, v4);
          }
          if ( g_wppLevels )
          {
            v8 = 228;
            goto LABEL_40;
          }
        }
      }
    }
    else
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)v13 + 499) != v4 )
          CallStackContext::TraceFailure(v13, "CStreamAggregator::CStreamAggregator", 2493, v4);
      }
      if ( g_wppLevels )
      {
        v8 = 227;
        goto LABEL_40;
      }
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CStreamAggregator::CStreamAggregator", 2483, v4);
    }
    if ( g_wppLevels )
    {
      v8 = 226;
LABEL_40:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v4);
    }
  }
  *a2 = v4;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
  return this;
}

```

## disassembly

```asm
0x180035484  mov     [rsp+arg_8], rbx
0x180035489  mov     [rsp+arg_10], rsi
0x18003548e  push    rdi
0x18003548f  sub     rsp, 30h
0x180035493  mov     rsi, rdx
0x180035496  mov     rdi, rcx
0x180035499  call    cs:__imp_InitializeCriticalSection
0x1800354a0  nop     dword ptr [rax+rax+00h]
0x1800354a5  mov     ebx, [rsi]
0x1800354a7  lea     rdx, aCstreamaggrega_2; "CStreamAggregator::CStreamAggregator"
0x1800354ae  mov     r8d, 9B3h; int
0x1800354b4  mov     qword ptr [rdi+28h], 0
0x1800354bc  lea     rcx, [rsp+38h+arg_0]; this
0x1800354c1  mov     qword ptr [rdi+30h], 0
0x1800354c9  mov     dword ptr [rdi+38h], 0
0x1800354d0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800354d5  test    ebx, ebx
0x1800354d7  jns     loc_180035572
0x1800354dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800354e4  test    rcx, rcx
0x1800354e7  jnz     short loc_180035530
0x1800354e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800354f0  nop     dword ptr [rax+rax+00h]
0x1800354f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800354fc  mov     rcx, rax
0x1800354ff  test    rax, rax
0x180035502  jz      short loc_180035522
0x180035504  mov     rax, [rax]
0x180035507  mov     edx, 7F0h
0x18003550c  mov     rax, [rax+8]
0x180035510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035515  test    eax, eax
0x180035517  jz      short loc_180035522
0x180035519  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035520  jmp     short loc_180035530
0x180035522  lea     rcx, qword_1800EB130; this
0x180035529  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035530  cmp     byte ptr [rcx+8], 0
0x180035534  jz      short loc_18003555B
0x180035536  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003553b  cmp     [rax+7CCh], ebx
0x180035541  jz      short loc_18003555B
0x180035543  mov     r9d, ebx; int
0x180035546  lea     rdx, aCstreamaggrega_2; "CStreamAggregator::CStreamAggregator"
0x18003554d  mov     r8d, 9B3h; int
0x180035553  mov     rcx, rax; this
0x180035556  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003555b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035562  jb      loc_180035741
0x180035568  mov     edx, 0E2h
0x18003556d  jmp     loc_180035723
0x180035572  xor     r9d, r9d; lpName
0x180035575  xor     r8d, r8d; bInitialState
0x180035578  xor     ecx, ecx; lpEventAttributes
0x18003557a  lea     edx, [r9+1]; bManualReset
0x18003557e  call    cs:__imp_CreateEventW
0x180035585  nop     dword ptr [rax+rax+00h]
0x18003558a  mov     [rdi+30h], rax
0x18003558e  test    rax, rax
0x180035591  jnz     loc_18003564F
0x180035597  call    cs:__imp_GetLastError
0x18003559e  nop     dword ptr [rax+rax+00h]
0x1800355a3  mov     ebx, eax
0x1800355a5  test    eax, eax
0x1800355a7  jle     short loc_1800355B2
0x1800355a9  movzx   ebx, ax
0x1800355ac  or      ebx, 80070000h
0x1800355b2  test    ebx, ebx
0x1800355b4  jns     loc_18003564F
0x1800355ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800355c1  test    rcx, rcx
0x1800355c4  jnz     short loc_18003560D
0x1800355c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800355cd  nop     dword ptr [rax+rax+00h]
0x1800355d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800355d9  mov     rcx, rax
0x1800355dc  test    rax, rax
0x1800355df  jz      short loc_1800355FF
0x1800355e1  mov     rax, [rax]
0x1800355e4  mov     edx, 7F0h
0x1800355e9  mov     rax, [rax+8]
0x1800355ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355f2  test    eax, eax
0x1800355f4  jz      short loc_1800355FF
0x1800355f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800355fd  jmp     short loc_18003560D
0x1800355ff  lea     rcx, qword_1800EB130; this
0x180035606  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003560d  cmp     byte ptr [rcx+8], 0
0x180035611  jz      short loc_180035638
0x180035613  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035618  cmp     [rax+7CCh], ebx
0x18003561e  jz      short loc_180035638
0x180035620  mov     r9d, ebx; int
0x180035623  lea     rdx, aCstreamaggrega_2; "CStreamAggregator::CStreamAggregator"
0x18003562a  mov     r8d, 9BDh; int
0x180035630  mov     rcx, rax; this
0x180035633  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035638  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003563f  jb      loc_180035741
0x180035645  mov     edx, 0E3h
0x18003564a  jmp     loc_180035723
0x18003564f  xor     r9d, r9d; lpName
0x180035652  xor     r8d, r8d; bInitialState
0x180035655  xor     ecx, ecx; lpEventAttributes
0x180035657  lea     edx, [r9+1]; bManualReset
0x18003565b  call    cs:__imp_CreateEventW
0x180035662  nop     dword ptr [rax+rax+00h]
0x180035667  mov     [rdi+28h], rax
0x18003566b  test    rax, rax
0x18003566e  jnz     loc_180035741
0x180035674  call    cs:__imp_GetLastError
0x18003567b  nop     dword ptr [rax+rax+00h]
0x180035680  mov     ebx, eax
0x180035682  test    eax, eax
0x180035684  jle     short loc_18003568F
0x180035686  movzx   ebx, ax
0x180035689  or      ebx, 80070000h
0x18003568f  test    ebx, ebx
0x180035691  jns     loc_180035741
0x180035697  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003569e  test    rcx, rcx
0x1800356a1  jnz     short loc_1800356EA
0x1800356a3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800356aa  nop     dword ptr [rax+rax+00h]
0x1800356af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800356b6  mov     rcx, rax
0x1800356b9  test    rax, rax
0x1800356bc  jz      short loc_1800356DC
0x1800356be  mov     rax, [rax]
0x1800356c1  mov     edx, 7F0h
0x1800356c6  mov     rax, [rax+8]
0x1800356ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356cf  test    eax, eax
0x1800356d1  jz      short loc_1800356DC
0x1800356d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800356da  jmp     short loc_1800356EA
0x1800356dc  lea     rcx, qword_1800EB130; this
0x1800356e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800356ea  cmp     byte ptr [rcx+8], 0
0x1800356ee  jz      short loc_180035715
0x1800356f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800356f5  cmp     [rax+7CCh], ebx
0x1800356fb  jz      short loc_180035715
0x1800356fd  mov     r9d, ebx; int
0x180035700  lea     rdx, aCstreamaggrega_2; "CStreamAggregator::CStreamAggregator"
0x180035707  mov     r8d, 9C8h; int
0x18003570d  mov     rcx, rax; this
0x180035710  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035715  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003571c  jb      short loc_180035741
0x18003571e  mov     edx, 0E4h
0x180035723  mov     rcx, cs:WPP_GLOBAL_Control
0x18003572a  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180035731  mov     r9, rdi
0x180035734  mov     [rsp+38h+var_18], ebx
0x180035738  mov     rcx, [rcx+10h]
0x18003573c  call    WPP_SF_qD
0x180035741  lea     rcx, [rsp+38h+arg_0]; this
0x180035746  mov     [rsi], ebx
0x180035748  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003574d  mov     rbx, [rsp+38h+arg_8]
0x180035752  mov     rax, rdi
0x180035755  mov     rsi, [rsp+38h+arg_10]
0x18003575a  add     rsp, 30h
0x18003575e  pop     rdi
0x18003575f  retn
```
