# StartEtwListener(_GUID const &,ushort const *,ushort,void (*)(_EVENT_RECORD *),EtwListenerContext * *)

- ea: `0x180093984`
- end: `0x180093d17`
- name: `?StartEtwListener@@YAKAEBU_GUID@@PEBGGP6AXPEAU_EVENT_RECORD@@@ZPEAPEAUEtwListenerContext@@@Z`
- size: `915`
- prototype: `unsigned int __fastcall(const struct _GUID *, const unsigned __int16 *, unsigned __int16, void (*)(struct _EVENT_RECORD *), struct EtwListenerContext **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180092f68`

## callees

- `0x18000c018`
- `0x18007a6e8`
- `0x18007a810`
- `0x18007a9cf`
- `0x180093984`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180093b0a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093bae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093bd2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093cb4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093cf0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093b0a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093bae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093bd2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093cb4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180093cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c72`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180093c64`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180093c64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093cc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093cc8`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093a50`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093aff`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093bc9`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093c3a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093ce7`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093a50`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093aff`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093bc9`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093c3a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180093ce7`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180093ba2`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180093ba2`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180093ab1`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180093ab1`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180093cd1`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180093cd1`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180093c15`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180093c15`

## pseudocode

```c
__int64 __fastcall StartEtwListener(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        void (*a4)(struct _EVENT_RECORD *))
{
  char *v4; // rax
  char *v5; // rdi
  __int64 result; // rax
  LPCWSTR v7; // r11
  DWORD LastError; // esi
  LPCWSTR v9; // r11
  ULONG started; // ebx
  _WORD *v11; // rbx
  __int64 v12; // rcx
  ULONG v13; // r14d
  void *v14; // rax
  TRACEHANDLE v15; // r14
  HANDLE Thread; // r15
  ULONG64 *v17; // rbx
  ULONG64 TraceHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+240h] [rbp+140h] BYREF

  TraceHandle = 0;
  qword_18015C0A8 = 0;
  v4 = (char *)operator new[](0xA4u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( !v4 )
    return 8;
  memset_0(v4 + 4, 0, 0xA0u);
  *(_DWORD *)v5 = 164;
  *((_DWORD *)v5 + 10) = 1;
  *((_DWORD *)v5 + 11) = 0x20000;
  *((_DWORD *)v5 + 16) = 256;
  *((_DWORD *)v5 + 29) = 120;
  *((_DWORD *)v5 + 28) = 0;
  *(GUID *)(v5 + 24) = GUID_NULL;
  StringCchCopyW((unsigned __int16 *)v5 + 60, 0x16u, L"PcaRealtimeEtwSession");
  ControlTraceW(0, v7, (PEVENT_TRACE_PROPERTIES)v5, 1u);
  memset_0(v5, 0, 0xA4u);
  *((_DWORD *)v5 + 16) = 256;
  *((_DWORD *)v5 + 29) = 120;
  LastError = 8;
  *(_DWORD *)v5 = 164;
  *((_DWORD *)v5 + 14) = 8;
  *((_DWORD *)v5 + 10) = 1;
  *((_DWORD *)v5 + 11) = 0x20000;
  *((_DWORD *)v5 + 12) = 16;
  *((_DWORD *)v5 + 13) = 2;
  StringCchCopyW((unsigned __int16 *)v5 + 60, 0x16u, L"PcaRealtimeEtwSession");
  started = StartTraceW(&TraceHandle, v9, (PEVENT_TRACE_PROPERTIES)v5);
  if ( started )
    goto LABEL_6;
  memset(&EnableParameters, 0, sizeof(EnableParameters));
  EnableParameters.Version = 2;
  v21 = 0;
  v11 = operator new[](8u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v11 )
  {
    ControlTraceW(TraceHandle, 0, (PEVENT_TRACE_PROPERTIES)v5, 1u);
    started = 8;
LABEL_6:
    operator delete[](v5);
    return started;
  }
  *(_QWORD *)v11 = 0;
  v12 = 0;
  *(_BYTE *)v11 = 1;
  v11[1] = 2;
  do
  {
    v11[v12 + 2] = *((_WORD *)&qword_180117258 + v12);
    ++v12;
  }
  while ( v12 != 2 );
  EnableParameters.EnableFilterDesc = (PEVENT_FILTER_DESCRIPTOR)&v21;
  *(_QWORD *)&v21 = v11;
  *((_QWORD *)&v21 + 1) = 0x8000020000000008uLL;
  EnableParameters.FilterDescCount = 1;
  v13 = EnableTraceEx2(TraceHandle, &stru_180117260, 1u, 4u, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, &EnableParameters);
  operator delete[](v11);
  if ( v13 )
  {
    ControlTraceW(TraceHandle, 0, (PEVENT_TRACE_PROPERTIES)v5, 1u);
    operator delete[](v5);
    return v13;
  }
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileMode = 268435712;
  Logfile.LoggerName = (LPWSTR)L"PcaRealtimeEtwSession";
  Logfile.EventCallback = (PEVENT_CALLBACK)KernelProcessEventCallback;
  v14 = (void *)OpenTraceW(&Logfile);
  v15 = (TRACEHANDLE)v14;
  if ( v14 == (void *)-1LL )
  {
    started = GetLastError();
    ControlTraceW(TraceHandle, 0, (PEVENT_TRACE_PROPERTIES)v5, 1u);
    goto LABEL_6;
  }
  Thread = CreateThread(0, 0, EtwListenerThreadProc, v14, 0, 0);
  if ( Thread )
  {
    v17 = (ULONG64 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    if ( v17 )
    {
      *(_OWORD *)v17 = 0;
      v17[2] = 0;
      *v17 = TraceHandle;
      v17[1] = v15;
      v17[2] = (ULONG64)Thread;
      operator delete[](v5);
      result = 0;
      qword_18015C0A8 = (__int64)v17;
      return result;
    }
    CloseHandle(Thread);
  }
  else
  {
    LastError = GetLastError();
  }
  CloseTrace(v15);
  ControlTraceW(TraceHandle, 0, (PEVENT_TRACE_PROPERTIES)v5, 1u);
  operator delete[](v5);
  return LastError;
}

```

## disassembly

```asm
0x180093984  push    rbp
0x180093986  push    rbx
0x180093987  push    rsi
0x180093988  push    rdi
0x180093989  push    r14
0x18009398b  push    r15
0x18009398d  lea     rbp, [rsp-168h]
0x180093995  sub     rsp, 268h
0x18009399c  mov     rax, cs:__security_cookie
0x1800939a3  xor     rax, rsp
0x1800939a6  mov     [rbp+190h+var_40], rax
0x1800939ad  mov     ebx, 0A4h
0x1800939b2  mov     [rsp+290h+TraceHandle], 0
0x1800939bb  mov     ecx, ebx; unsigned __int64
0x1800939bd  mov     cs:qword_18015C0A8, 0
0x1800939c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800939cf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800939d4  mov     rdi, rax
0x1800939d7  test    rax, rax
0x1800939da  jnz     short loc_1800939E4
0x1800939dc  lea     eax, [rdi+8]
0x1800939df  jmp     loc_180093CF8
0x1800939e4  lea     rcx, [rax+4]; void *
0x1800939e8  xor     edx, edx; Val
0x1800939ea  mov     r8d, 0A0h; Size
0x1800939f0  call    memset_0
0x1800939f5  mov     esi, 78h ; 'x'
0x1800939fa  mov     [rdi], ebx
0x1800939fc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180093a03  lea     r11, aPcarealtimeetw; "PcaRealtimeEtwSession"
0x180093a0a  mov     dword ptr [rdi+28h], 1
0x180093a11  mov     r15d, 100h
0x180093a17  mov     dword ptr [rdi+2Ch], 20000h
0x180093a1e  lea     r14d, [rsi-62h]
0x180093a22  mov     [rdi+40h], r15d
0x180093a26  mov     edx, r14d; unsigned __int64
0x180093a29  mov     [rdi+74h], esi
0x180093a2c  mov     r8, r11; unsigned __int16 *
0x180093a2f  mov     dword ptr [rdi+70h], 0
0x180093a36  lea     rcx, [rdi+78h]; unsigned __int16 *
0x180093a3a  movdqu  xmmword ptr [rdi+18h], xmm0
0x180093a3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093a44  lea     r9d, [rsi-77h]; ControlCode
0x180093a48  mov     r8, rdi; Properties
0x180093a4b  mov     rdx, r11; InstanceName
0x180093a4e  xor     ecx, ecx; TraceHandle
0x180093a50  call    cs:__imp_ControlTraceW
0x180093a56  xor     edx, edx; Val
0x180093a58  mov     r8, rbx; Size
0x180093a5b  mov     rcx, rdi; void *
0x180093a5e  call    memset_0
0x180093a63  mov     [rdi+40h], r15d
0x180093a67  lea     r11, aPcarealtimeetw; "PcaRealtimeEtwSession"
0x180093a6e  lea     r15d, [rsi-76h]
0x180093a72  mov     [rdi+74h], esi
0x180093a75  lea     esi, [r14-0Eh]
0x180093a79  mov     [rdi], ebx
0x180093a7b  mov     r8, r11; unsigned __int16 *
0x180093a7e  mov     [rdi+38h], esi
0x180093a81  mov     edx, r14d; unsigned __int64
0x180093a84  mov     dword ptr [rdi+28h], 1
0x180093a8b  lea     rcx, [rdi+78h]; unsigned __int16 *
0x180093a8f  mov     dword ptr [rdi+2Ch], 20000h
0x180093a96  mov     dword ptr [rdi+30h], 10h
0x180093a9d  mov     [rdi+34h], r15d
0x180093aa1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093aa6  mov     r8, rdi; Properties
0x180093aa9  lea     rcx, [rsp+290h+TraceHandle]; TraceHandle
0x180093aae  mov     rdx, r11; InstanceName
0x180093ab1  call    cs:__imp_StartTraceW
0x180093ab7  mov     ebx, eax
0x180093ab9  test    eax, eax
0x180093abb  jnz     short loc_180093B07
0x180093abd  xorps   xmm0, xmm0
0x180093ac0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093ac7  movups  xmmword ptr [rsp+290h+var_248.Version], xmm0
0x180093acc  mov     ecx, esi; unsigned __int64
0x180093ace  mov     [rsp+290h+var_248.Version], r15d
0x180093ad3  movups  xmmword ptr [rsp+290h+var_248.SourceId.Data2], xmm0
0x180093ad8  movups  xmmword ptr [rsp+290h+var_248.EnableFilterDesc], xmm0
0x180093add  movups  [rbp+190h+var_50], xmm0
0x180093ae4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180093ae9  mov     rbx, rax
0x180093aec  test    rax, rax
0x180093aef  jnz     short loc_180093B17
0x180093af1  mov     rcx, [rsp+290h+TraceHandle]; TraceHandle
0x180093af6  lea     r9d, [r14-15h]; ControlCode
0x180093afa  mov     r8, rdi; Properties
0x180093afd  xor     edx, edx; InstanceName
0x180093aff  call    cs:__imp_ControlTraceW
0x180093b05  mov     ebx, esi
0x180093b07  mov     rcx, rdi
0x180093b0a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180093b10  mov     eax, ebx
0x180093b12  jmp     loc_180093CF8
0x180093b17  xor     eax, eax
0x180093b19  mov     [rbx], rax
0x180093b1c  xor     ecx, ecx
0x180093b1e  mov     byte ptr [rbx], 1
0x180093b21  mov     [rbx+2], r15w
0x180093b26  lea     rax, qword_180117258
0x180093b2d  movzx   eax, word ptr [rax+rcx*2]
0x180093b31  mov     [rbx+rcx*2+4], ax
0x180093b36  inc     rcx
0x180093b39  cmp     rcx, r15
0x180093b3c  jnz     short loc_180093B26
0x180093b3e  mov     rcx, [rsp+290h+TraceHandle]; TraceHandle
0x180093b43  lea     rax, [rbp+190h+var_50]
0x180093b4a  mov     [rsp+290h+var_248.EnableFilterDesc], rax
0x180093b4f  lea     rdx, stru_180117260; ProviderId
0x180093b56  lea     rax, [rsp+290h+var_248]
0x180093b5b  mov     qword ptr [rbp+190h+var_50], rbx
0x180093b62  mov     [rsp+290h+EnableParameters], rax; EnableParameters
0x180093b67  mov     r9b, 4; Level
0x180093b6a  mov     [rsp+290h+Timeout], 0; Timeout
0x180093b72  mov     r8d, 1; ControlCode
0x180093b78  mov     [rsp+290h+MatchAllKeyword], 0; MatchAllKeyword
0x180093b81  mov     [rsp+290h+MatchAnyKeyword], 0FFFFFFFFFFFFFFFFh; MatchAnyKeyword
0x180093b8a  mov     dword ptr [rbp+190h+var_50+8], esi
0x180093b90  mov     dword ptr [rbp+190h+var_50+0Ch], 80000200h
0x180093b9a  mov     [rsp+290h+var_248.FilterDescCount], 1
0x180093ba2  call    cs:__imp_EnableTraceEx2
0x180093ba8  mov     rcx, rbx
0x180093bab  mov     r14d, eax
0x180093bae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180093bb4  test    r14d, r14d
0x180093bb7  jz      short loc_180093BE0
0x180093bb9  mov     rcx, [rsp+290h+TraceHandle]; TraceHandle
0x180093bbe  mov     r9d, 1; ControlCode
0x180093bc4  mov     r8, rdi; Properties
0x180093bc7  xor     edx, edx; InstanceName
0x180093bc9  call    cs:__imp_ControlTraceW
0x180093bcf  mov     rcx, rdi
0x180093bd2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180093bd8  mov     eax, r14d
0x180093bdb  jmp     loc_180093CF8
0x180093be0  xor     edx, edx; Val
0x180093be2  lea     rcx, [rbp+190h+Logfile]; void *
0x180093be6  mov     r8d, 1C0h; Size
0x180093bec  call    memset_0
0x180093bf1  lea     rax, aPcarealtimeetw; "PcaRealtimeEtwSession"
0x180093bf8  mov     dword ptr [rbp+190h+Logfile.1Ch], 10000100h
0x180093bff  mov     [rbp+190h+Logfile.LoggerName], rax
0x180093c03  lea     rcx, [rbp+190h+Logfile]; Logfile
0x180093c07  lea     rax, KernelProcessEventCallback
0x180093c0e  mov     qword ptr [rbp+190h+Logfile.1A8h], rax
0x180093c15  call    cs:__imp_OpenTraceW
0x180093c1b  mov     r14, rax
0x180093c1e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180093c22  jnz     short loc_180093C45
0x180093c24  call    cs:__imp_GetLastError
0x180093c2a  mov     rcx, [rsp+290h+TraceHandle]; TraceHandle
0x180093c2f  lea     r9d, [r14+2]; ControlCode
0x180093c33  mov     r8, rdi; Properties
0x180093c36  xor     edx, edx; InstanceName
0x180093c38  mov     ebx, eax
0x180093c3a  call    cs:__imp_ControlTraceW
0x180093c40  jmp     loc_180093B07
0x180093c45  mov     [rsp+290h+MatchAllKeyword], 0; lpThreadId
0x180093c4e  lea     r8, EtwListenerThreadProc; lpStartAddress
0x180093c55  mov     r9, r14; lpParameter
0x180093c58  mov     dword ptr [rsp+290h+MatchAnyKeyword], 0; dwCreationFlags
0x180093c60  xor     edx, edx; dwStackSize
0x180093c62  xor     ecx, ecx; lpThreadAttributes
0x180093c64  call    cs:__imp_CreateThread
0x180093c6a  mov     r15, rax
0x180093c6d  test    rax, rax
0x180093c70  jnz     short loc_180093C7C
0x180093c72  call    cs:__imp_GetLastError
0x180093c78  mov     esi, eax
0x180093c7a  jmp     short loc_180093CCE
0x180093c7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093c83  mov     ecx, 18h; unsigned __int64
0x180093c88  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180093c8d  mov     rbx, rax
0x180093c90  test    rax, rax
0x180093c93  jz      short loc_180093CC5
0x180093c95  xorps   xmm0, xmm0
0x180093c98  xor     eax, eax
0x180093c9a  movups  xmmword ptr [rbx], xmm0
0x180093c9d  mov     [rbx+10h], rax
0x180093ca1  mov     rcx, [rsp+290h+TraceHandle]
0x180093ca6  mov     [rbx], rcx
0x180093ca9  mov     rcx, rdi
0x180093cac  mov     [rbx+8], r14
0x180093cb0  mov     [rbx+10h], r15
0x180093cb4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180093cba  xor     eax, eax
0x180093cbc  mov     cs:qword_18015C0A8, rbx
0x180093cc3  jmp     short loc_180093CF8
0x180093cc5  mov     rcx, r15; hObject
0x180093cc8  call    cs:__imp_CloseHandle
0x180093cce  mov     rcx, r14; TraceHandle
0x180093cd1  call    cs:__imp_CloseTrace
0x180093cd7  mov     rcx, [rsp+290h+TraceHandle]; TraceHandle
0x180093cdc  mov     r9d, 1; ControlCode
0x180093ce2  mov     r8, rdi; Properties
0x180093ce5  xor     edx, edx; InstanceName
0x180093ce7  call    cs:__imp_ControlTraceW
0x180093ced  mov     rcx, rdi
0x180093cf0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180093cf6  mov     eax, esi
0x180093cf8  mov     rcx, [rbp+190h+var_40]
0x180093cff  xor     rcx, rsp; StackCookie
0x180093d02  call    __security_check_cookie
0x180093d07  add     rsp, 268h
0x180093d0e  pop     r15
0x180093d10  pop     r14
0x180093d12  pop     rdi
0x180093d13  pop     rsi
0x180093d14  pop     rbx
0x180093d15  pop     rbp
0x180093d16  retn
```
