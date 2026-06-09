# CMFMediaEventGenerator::QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)

- ea: `0x18009b9e0`
- end: `0x18009bd96`
- name: `?QueueEvent@CMFMediaEventGenerator@@QEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(CMFMediaEventGenerator *__hidden this, unsigned int, GUID *guidExtendedType, HRESULT hrStatus, PROPVARIANT *pvValue)`
- caller_count: `28`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18002a42c`
- `0x180083180`
- `0x1800840e0`
- `0x18009b038`
- `0x18009ce18`
- `0x18009f2f0`
- `0x18014d690`
- `0x180163ab0`
- `0x1801779a0`
- `0x1801b01e0`
- `0x1801bd740`
- `0x1801d6658`
- `0x1801fd430`
- `0x180238344`
- `0x18024f95c`
- `0x180298070`
- `0x180299d20`
- `0x180299d30`
- `0x18029ef0c`
- `0x1802a0920`
- `0x1802ace70`
- `0x1802ad4c0`
- `0x1802ad4e0`
- `0x1802b4050`
- `0x1802b6be0`
- `0x1802cf370`
- `0x18031bc78`
- `0x18032f0e0`

## callees

- `0x18001616c`
- `0x18001b9b0`
- `0x180039ad8`
- `0x1800402c0`
- `0x180050d6c`
- `0x18009b9e0`
- `0x18009c830`
- `0x1800b9118`
- `0x1800ec0e0`
- `0x18014b764`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bbe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bbe0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bb7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bb7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ba58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ba58`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009ba3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009ba3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bce7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bce7`
- `MFPlat!MFCreateMediaEventResult` at `0x18009bba0`
- `MFPlat!MFCreateMediaEventResult` at `0x18009bba0`
- `MFPlat!MFCreateMediaEvent` at `0x18009bac2`
- `MFPlat!MFCreateMediaEvent` at `0x18009bac2`

## pseudocode

```c
__int64 __fastcall CMFMediaEventGenerator::QueueEvent(
        CMFMediaEventGenerator *this,
        unsigned int a2,
        GUID *guidExtendedType,
        HRESULT hrStatus,
        PROPVARIANT *pvValue)
{
  CallStackTracing *v9; // rdi
  char *v10; // rbx
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  HRESULT v15; // ebx
  void (*Release)(void); // rax
  struct CallStackContext *v17; // rax
  int v18; // ecx
  int v19; // ecx
  struct IMFMediaEvent *v21; // rbx
  unsigned int v22; // edx
  __int64 *v23; // rax
  __int64 v24; // rdx
  const char *v25; // rax
  int v26; // edx
  int v27; // r8d
  CallStackTracing *v28; // rcx
  __int64 v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // [rsp+30h] [rbp-28h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v37[3]; // [rsp+40h] [rbp-18h] BYREF
  int v38; // [rsp+A0h] [rbp+48h] BYREF

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v9 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v10 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v9 + 3));
    if ( Value )
    {
      v10 = Value;
    }
    else if ( !GetLastError() )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v28 = CallStackTracing::s_wpInstance;
      }
      v29 = (**(__int64 (__fastcall ***)(CallStackTracing *))v28)(v28);
      if ( v29 )
        v10 = (char *)v29;
    }
    SetLastError(LastError);
    v13 = *((unsigned int *)v10 + 497);
    if ( (unsigned int)v13 < *((_DWORD *)v10 + 498) )
    {
      v14 = 2 * v13;
      *(_QWORD *)&v10[8 * v14] = "CMFMediaEventGenerator::QueueEvent";
      *(_DWORD *)&v10[8 * v14 + 8] = 366;
    }
    ++*((_DWORD *)v10 + 497);
  }
  if ( (unsigned __int8)byte_1803CECEB >= 0x10u )
  {
    v25 = MFTRACE_STRING_FROM_MET(a2);
    WPP_SF_qsL(*((_QWORD *)WPP_GLOBAL_Control + 17), v26, v27, (_DWORD)this, (__int64)v25, hrStatus);
  }
  if ( *((_DWORD *)this + 12) )
  {
    v15 = -1072873851;
  }
  else
  {
    ppEvent = 0;
    v15 = MFCreateMediaEvent(a2, guidExtendedType, hrStatus, pvValue, &ppEvent);
    if ( v15 < 0 )
    {
      if ( !ppEvent )
        goto LABEL_16;
      Release = (void (*)(void))ppEvent->lpVtbl->Release;
      goto LABEL_15;
    }
    v21 = ppEvent;
    v37[0] = 0;
    v38 = 0;
    v35 = 0;
    if ( ppEvent
      && ((int (__fastcall *)(IMFMediaEvent *, int *))ppEvent->lpVtbl->GetType)(ppEvent, &v38) >= 0
      && v38 == 1
      && ((int (__fastcall *)(struct IMFMediaEvent *, int *))v21->lpVtbl->GetStatus)(v21, &v35) >= 0 )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( v35 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v35 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMediaEventGenerator::QueueEvent", 458, v35);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((_DWORD *)this + 12) )
    {
      v15 = -1072873851;
    }
    else
    {
      if ( (unsigned __int8)byte_1803CECEB >= 0x10u )
        MFTRACE_MEDIA_EVENT_IMPL(0x30001u, v22, v21);
      v15 = MFCreateMediaEventResult(v21, v37);
      if ( v15 >= 0 )
      {
        v23 = (__int64 *)*((_QWORD *)this + 9);
        v24 = v37[0] + 128LL;
        *(_QWORD *)(v37[0] + 128LL) = (char *)this + 64;
        *(_QWORD *)(v24 + 8) = v23;
        *v23 = v24;
        ++*((_DWORD *)this + 14);
        *((_QWORD *)this + 9) = v24;
        v15 = CMFMediaEventGenerator::CheckDispatchEvent(this);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( ppEvent )
    {
      Release = (void (*)(void))ppEvent->lpVtbl->Release;
LABEL_15:
      Release();
    }
  }
LABEL_16:
  if ( (unsigned __int8)byte_1803CECEB >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 20, &WPP_5850d8474d1a3657fe88c51c9f643822_Traceguids, this, v15);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v18 = *((_DWORD *)v17 + 497);
    if ( v18 )
    {
      v19 = v18 - 1;
      *((_DWORD *)v17 + 497) = v19;
      if ( !v19 )
        CallStackContext::ClearState(v17);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18009b9e0  push    rbp
0x18009b9e2  push    rbx
0x18009b9e3  push    rsi
0x18009b9e4  push    rdi
0x18009b9e5  push    r12
0x18009b9e7  push    r13
0x18009b9e9  push    r14
0x18009b9eb  push    r15
0x18009b9ed  mov     rbp, rsp
0x18009b9f0  sub     rsp, 58h
0x18009b9f4  xor     r14d, r14d
0x18009b9f7  mov     r15d, r9d
0x18009b9fa  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ba01  mov     r13, r8
0x18009ba04  mov     r12d, edx
0x18009ba07  mov     rsi, rcx
0x18009ba0a  jz      loc_18009BC8D
0x18009ba10  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ba17  lea     rcx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x18009ba1e  cmp     [rdi+8], r14b
0x18009ba22  jz      short loc_18009BA91
0x18009ba24  lea     rbx, [rdi+0D0h]
0x18009ba2b  call    cs:__imp_GetLastError
0x18009ba32  nop     dword ptr [rax+rax+00h]
0x18009ba37  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18009ba3a  mov     r14d, eax
0x18009ba3d  call    cs:__imp_TlsGetValue
0x18009ba44  nop     dword ptr [rax+rax+00h]
0x18009ba49  test    rax, rax
0x18009ba4c  jz      loc_18009BC97
0x18009ba52  mov     rbx, rax
0x18009ba55  mov     ecx, r14d; dwErrCode
0x18009ba58  call    cs:__imp_SetLastError
0x18009ba5f  nop     dword ptr [rax+rax+00h]
0x18009ba64  mov     eax, [rbx+7C4h]
0x18009ba6a  lea     rcx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x18009ba71  xor     r14d, r14d
0x18009ba74  cmp     eax, [rbx+7C8h]
0x18009ba7a  jnb     short loc_18009BA8B
0x18009ba7c  add     rax, rax
0x18009ba7f  mov     [rbx+rax*8], rcx
0x18009ba83  mov     dword ptr [rbx+rax*8+8], 16Eh
0x18009ba8b  inc     dword ptr [rbx+7C4h]
0x18009ba91  cmp     cs:byte_1803CECEB, 10h
0x18009ba98  jnb     loc_18009BC19
0x18009ba9e  cmp     [rsi+30h], r14d
0x18009baa2  jnz     loc_18009BC71
0x18009baa8  mov     r9, [rbp+pvValue]; pvValue
0x18009baac  lea     rax, [rbp+var_20]
0x18009bab0  mov     r8d, r15d; hrStatus
0x18009bab3  mov     [rsp+58h+ppEvent], rax; ppEvent
0x18009bab8  mov     rdx, r13; guidExtendedType
0x18009babb  mov     [rbp+var_20], r14
0x18009babf  mov     ecx, r12d; met
0x18009bac2  call    cs:__imp_MFCreateMediaEvent
0x18009bac9  nop     dword ptr [rax+rax+00h]
0x18009bace  mov     ebx, eax
0x18009bad0  test    eax, eax
0x18009bad2  jns     short loc_18009BB39
0x18009bad4  mov     rcx, [rbp+var_20]
0x18009bad8  test    rcx, rcx
0x18009badb  jz      short loc_18009BAEA
0x18009badd  mov     rdx, [rcx]
0x18009bae0  mov     rax, [rdx+10h]
0x18009bae4  call    cs:__guard_dispatch_icall_fptr
0x18009baea  cmp     cs:byte_1803CECEB, 20h ; ' '
0x18009baf1  jnb     loc_18009BC46
0x18009baf7  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bafe  cmp     [rdi+8], r14b
0x18009bb02  jz      short loc_18009BB25
0x18009bb04  mov     rcx, rdi; this
0x18009bb07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bb0c  mov     ecx, [rax+7C4h]
0x18009bb12  test    ecx, ecx
0x18009bb14  jz      short loc_18009BB25
0x18009bb16  sub     ecx, 1
0x18009bb19  mov     [rax+7C4h], ecx
0x18009bb1f  jz      loc_18009BC0C
0x18009bb25  mov     eax, ebx
0x18009bb27  add     rsp, 58h
0x18009bb2b  pop     r15
0x18009bb2d  pop     r14
0x18009bb2f  pop     r13
0x18009bb31  pop     r12
0x18009bb33  pop     rdi
0x18009bb34  pop     rsi
0x18009bb35  pop     rbx
0x18009bb36  pop     rbp
0x18009bb37  retn
0x18009bb39  mov     rbx, [rbp+var_20]
0x18009bb3d  mov     [rbp+var_18], r14
0x18009bb41  mov     [rbp+arg_0], r14d
0x18009bb45  mov     [rbp+var_28], r14d
0x18009bb49  test    rbx, rbx
0x18009bb4c  jz      short loc_18009BB73
0x18009bb4e  mov     rax, [rbx]
0x18009bb51  lea     rdx, [rbp+arg_0]
0x18009bb55  mov     rcx, rbx
0x18009bb58  mov     rax, [rax+108h]
0x18009bb5f  call    cs:__guard_dispatch_icall_fptr
0x18009bb65  test    eax, eax
0x18009bb67  js      short loc_18009BB73
0x18009bb69  cmp     [rbp+arg_0], 1
0x18009bb6d  jz      loc_18009BD72
0x18009bb73  lea     rdi, [rsi+8]
0x18009bb77  mov     rcx, rdi; lpCriticalSection
0x18009bb7a  call    cs:__imp_EnterCriticalSection
0x18009bb81  nop     dword ptr [rax+rax+00h]
0x18009bb86  cmp     [rsi+30h], r14d
0x18009bb8a  jnz     short loc_18009BC05
0x18009bb8c  cmp     cs:byte_1803CECEB, 10h
0x18009bb93  jnb     loc_18009BC7B
0x18009bb99  lea     rdx, [rbp+var_18]
0x18009bb9d  mov     rcx, rbx
0x18009bba0  call    cs:__imp_MFCreateMediaEventResult
0x18009bba7  nop     dword ptr [rax+rax+00h]
0x18009bbac  mov     ebx, eax
0x18009bbae  test    eax, eax
0x18009bbb0  js      short loc_18009BBDD
0x18009bbb2  mov     rdx, [rbp+var_18]
0x18009bbb6  lea     rcx, [rsi+40h]
0x18009bbba  mov     rax, [rcx+8]
0x18009bbbe  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18009bbc2  mov     [rdx], rcx
0x18009bbc5  mov     [rdx+8], rax
0x18009bbc9  mov     [rax], rdx
0x18009bbcc  inc     dword ptr [rsi+38h]
0x18009bbcf  mov     [rcx+8], rdx
0x18009bbd3  mov     rcx, rsi; this
0x18009bbd6  call    ?CheckDispatchEvent@CMFMediaEventGenerator@@IEAAJXZ; CMFMediaEventGenerator::CheckDispatchEvent(void)
0x18009bbdb  mov     ebx, eax
0x18009bbdd  mov     rcx, rdi; lpCriticalSection
0x18009bbe0  call    cs:__imp_LeaveCriticalSection
0x18009bbe7  nop     dword ptr [rax+rax+00h]
0x18009bbec  mov     rcx, [rbp+var_20]
0x18009bbf0  test    rcx, rcx
0x18009bbf3  jz      loc_18009BAEA
0x18009bbf9  mov     rax, [rcx]
0x18009bbfc  mov     rax, [rax+10h]
0x18009bc00  jmp     loc_18009BAE4
0x18009bc05  mov     ebx, 0C00D3E85h
0x18009bc0a  jmp     short loc_18009BBDD
0x18009bc0c  mov     rcx, rax; this
0x18009bc0f  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18009bc14  jmp     loc_18009BB25
0x18009bc19  mov     ecx, r12d; unsigned int
0x18009bc1c  call    ?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z; MFTRACE_STRING_FROM_MET(ulong)
0x18009bc21  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc28  mov     r9, rsi
0x18009bc2b  mov     [rsp+58h+var_30], r15d
0x18009bc30  mov     [rsp+58h+ppEvent], rax
0x18009bc35  mov     rcx, [rcx+88h]
0x18009bc3c  call    WPP_SF_qsL
0x18009bc41  jmp     loc_18009BA9E
0x18009bc46  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc4d  lea     r8, WPP_5850d8474d1a3657fe88c51c9f643822_Traceguids
0x18009bc54  mov     edx, 14h
0x18009bc59  mov     dword ptr [rsp+58h+ppEvent], ebx
0x18009bc5d  mov     r9, rsi
0x18009bc60  mov     rcx, [rcx+88h]
0x18009bc67  call    WPP_SF_qD
0x18009bc6c  jmp     loc_18009BAF7
0x18009bc71  mov     ebx, 0C00D3E85h
0x18009bc76  jmp     loc_18009BAEA
0x18009bc7b  mov     r8, rbx; struct IMFMediaEvent *
0x18009bc7e  mov     ecx, 30001h; unsigned int
0x18009bc83  call    ?MFTRACE_MEDIA_EVENT_IMPL@@YAXKKPEAUIMFMediaEvent@@@Z; MFTRACE_MEDIA_EVENT_IMPL(ulong,ulong,IMFMediaEvent *)
0x18009bc88  jmp     loc_18009BB99
0x18009bc8d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009bc92  jmp     loc_18009BA10
0x18009bc97  call    cs:__imp_GetLastError
0x18009bc9e  nop     dword ptr [rax+rax+00h]
0x18009bca3  test    eax, eax
0x18009bca5  jnz     loc_18009BA55
0x18009bcab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bcb2  test    rcx, rcx
0x18009bcb5  jnz     short loc_18009BCC3
0x18009bcb7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009bcbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bcc3  mov     rax, [rcx]
0x18009bcc6  mov     rax, [rax]
0x18009bcc9  call    cs:__guard_dispatch_icall_fptr
0x18009bccf  test    rax, rax
0x18009bcd2  cmovnz  rbx, rax
0x18009bcd6  jmp     loc_18009BA55
0x18009bcdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bce2  test    rcx, rcx
0x18009bce5  jnz     short loc_18009BD1F
0x18009bce7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009bcee  nop     dword ptr [rax+rax+00h]
0x18009bcf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bcfa  mov     rcx, rax
0x18009bcfd  test    rax, rax
0x18009bd00  jz      short loc_18009BD62
0x18009bd02  mov     rax, [rax]
0x18009bd05  mov     edx, 7F0h
0x18009bd0a  mov     rax, [rax+8]
0x18009bd0e  call    cs:__guard_dispatch_icall_fptr
0x18009bd14  test    eax, eax
0x18009bd16  jz      short loc_18009BD62
0x18009bd18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009bd1f  cmp     [rcx+8], r14b
0x18009bd23  jz      loc_18009BB73
0x18009bd29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bd2e  mov     r9d, [rbp+var_28]; int
0x18009bd32  test    r9d, r9d
0x18009bd35  jns     loc_18009BB73
0x18009bd3b  cmp     [rax+7CCh], r9d
0x18009bd42  jz      loc_18009BB73
0x18009bd48  mov     r8d, 1CAh; int
0x18009bd4e  lea     rdx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x18009bd55  mov     rcx, rax; this
0x18009bd58  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009bd5d  jmp     loc_18009BB73
0x18009bd62  lea     rcx, qword_1803CE250
0x18009bd69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bd70  jmp     short loc_18009BD1F
0x18009bd72  mov     rax, [rbx]
0x18009bd75  lea     rdx, [rbp+var_28]
0x18009bd79  mov     rcx, rbx
0x18009bd7c  mov     rax, [rax+118h]
0x18009bd83  call    cs:__guard_dispatch_icall_fptr
0x18009bd89  test    eax, eax
0x18009bd8b  js      loc_18009BB73
0x18009bd91  jmp     loc_18009BCDB
```
