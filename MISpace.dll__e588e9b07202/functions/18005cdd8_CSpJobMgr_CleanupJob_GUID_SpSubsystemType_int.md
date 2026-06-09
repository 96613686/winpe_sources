# CSpJobMgr::CleanupJob(_GUID,SpSubsystemType,int)

- ea: `0x18005cdd8`
- end: `0x18005cfa1`
- name: `?CleanupJob@CSpJobMgr@@QEAAHU_GUID@@W4SpSubsystemType@@H@Z`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180014be8`
- `0x180024bb0`

## callees

- `0x1800011b0`
- `0x18005cdd8`
- `0x18005e8d0`
- `0x18005f07c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cefe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cefe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005cf13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005cf13`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005cf84`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005cf84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ce4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005cf4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ce4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005cf4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ce59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cf8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ce59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cf8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ce6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ce6e`

## pseudocode

```c
__int64 __fastcall CSpJobMgr::CleanupJob(__int64 a1, __int128 *a2, unsigned int a3, int a4)
{
  LPCRITICAL_SECTION v7; // rbx
  _DWORD *v8; // rsi
  unsigned int v9; // edi
  int DebugInfo_high; // r12d
  __int128 *v11; // r13
  int v12; // r8d
  int v13; // r9d
  HANDLE CurrentThread; // rax
  int v16; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  __int128 v18; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+A8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v20 = 603;
    *(_QWORD *)&v18 = "CSpJobMgr::CleanupJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CSpJobMgr::CleanupJob",
      (unsigned int)&dword_18030A3A4,
      a3,
      a4,
      (__int64)&v18,
      (__int64)&v20);
  }
  v7 = MISpaceHandle::g_MISpaceHandle;
  v8 = 0;
  TokenHandle = 0;
  v9 = 1;
  EnterCriticalSection(MISpaceHandle::g_MISpaceHandle);
  DebugInfo_high = HIDWORD(v7[1].DebugInfo);
  LeaveCriticalSection(v7);
  if ( a4 || DebugInfo_high )
    goto LABEL_7;
  v8 = LocalAlloc(0, 0x20u);
  if ( !v8
    || a3 != -1
    && (CurrentThread = GetCurrentThread(), !OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle))
    && GetLastError() != 1008 )
  {
    v9 = 0;
LABEL_7:
    v11 = a2;
LABEL_8:
    v18 = *v11;
    CSpJobMgr::_RemoveJob(a1, &v18, a3);
    goto LABEL_9;
  }
  v11 = a2;
  v8[6] = a3;
  *(_OWORD *)v8 = *a2;
  *((_QWORD *)v8 + 2) = TokenHandle;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( (*(unsigned __int8 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)(a1 + 368) + 8LL))(a1 + 368, v8) )
  {
    if ( a3 != -1 )
      _InterlockedAdd((volatile signed __int32 *)(a1 + 48), 1u);
    v8 = 0;
    v16 = 0;
    SetEvent(*(HANDLE *)(a1 + 64));
  }
  else
  {
    v16 = 1;
    v9 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( v16 )
    goto LABEL_8;
LABEL_9:
  SuFreeTpContext(v8);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v20 = 683;
    *(_QWORD *)&v18 = "CSpJobMgr::CleanupJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_180397B68,
      (unsigned int)&dword_18030A55C,
      v12,
      v13,
      (__int64)&v18,
      (__int64)&v20);
  }
  return v9;
}

```

## disassembly

```asm
0x18005cdd8  mov     r11, rsp
0x18005cddb  mov     [r11+8], rbx
0x18005cddf  mov     [r11+10h], rdx
0x18005cde3  push    rbp
0x18005cde4  push    rsi
0x18005cde5  push    rdi
0x18005cde6  push    r12
0x18005cde8  push    r13
0x18005cdea  push    r14
0x18005cdec  push    r15
0x18005cdee  mov     rbp, rsp
0x18005cdf1  sub     rsp, 50h
0x18005cdf5  mov     eax, cs:dword_180397B68
0x18005cdfb  mov     r14, rcx
0x18005cdfe  lea     rcx, aCspjobmgrClean; "CSpJobMgr::CleanupJob"
0x18005ce05  mov     r13d, r9d
0x18005ce08  mov     r15d, r8d
0x18005ce0b  cmp     eax, 5
0x18005ce0e  jbe     short loc_18005CE37
0x18005ce10  lea     rax, [rbp+arg_18]
0x18005ce14  mov     [rbp+arg_18], 25Bh
0x18005ce1b  mov     [r11-60h], rax
0x18005ce1f  lea     rdx, dword_18030A3A4
0x18005ce26  lea     rax, [rbp+var_10]
0x18005ce2a  mov     qword ptr [rbp+var_10], rcx
0x18005ce2e  mov     [r11-68h], rax
0x18005ce32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005ce37  mov     rbx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; MISpaceHandle * MISpaceHandle::g_MISpaceHandle
0x18005ce3e  xor     esi, esi
0x18005ce40  mov     rcx, rbx; lpCriticalSection
0x18005ce43  mov     [rbp+TokenHandle], rsi
0x18005ce47  mov     edi, 1
0x18005ce4c  call    cs:__imp_EnterCriticalSection
0x18005ce52  mov     r12d, [rbx+2Ch]
0x18005ce56  mov     rcx, rbx; lpCriticalSection
0x18005ce59  call    cs:__imp_LeaveCriticalSection
0x18005ce5f  test    r13d, r13d
0x18005ce62  jnz     short loc_18005CE7E
0x18005ce64  test    r12d, r12d
0x18005ce67  jnz     short loc_18005CE7E
0x18005ce69  lea     edx, [rdi+1Fh]; uBytes
0x18005ce6c  xor     ecx, ecx; uFlags
0x18005ce6e  call    cs:__imp_LocalAlloc
0x18005ce74  mov     rsi, rax
0x18005ce77  test    rax, rax
0x18005ce7a  jnz     short loc_18005CEF8
0x18005ce7c  xor     edi, edi
0x18005ce7e  mov     r13, [rbp+arg_8]
0x18005ce82  movups  xmm0, xmmword ptr [r13+0]
0x18005ce87  mov     r8d, r15d
0x18005ce8a  lea     rdx, [rbp+var_10]
0x18005ce8e  mov     rcx, r14
0x18005ce91  movdqu  [rbp+var_10], xmm0
0x18005ce96  call    ?_RemoveJob@CSpJobMgr@@AEAAHU_GUID@@W4SpSubsystemType@@@Z; CSpJobMgr::_RemoveJob(_GUID,SpSubsystemType)
0x18005ce9b  mov     rcx, rsi; hMem
0x18005ce9e  call    ?SuFreeTpContext@@YAXPEAU_SU_TP_CONTEXT@@@Z; SuFreeTpContext(_SU_TP_CONTEXT *)
0x18005cea3  mov     ecx, cs:dword_180397B68
0x18005cea9  cmp     ecx, 5
0x18005ceac  jbe     short loc_18005CEDE
0x18005ceae  lea     rax, aCspjobmgrClean; "CSpJobMgr::CleanupJob"
0x18005ceb5  mov     [rbp+arg_18], 2ABh
0x18005cebc  mov     qword ptr [rbp+var_10], rax
0x18005cec0  lea     rdx, dword_18030A55C
0x18005cec7  lea     rax, [rbp+arg_18]
0x18005cecb  mov     [rsp+50h+var_28], rax
0x18005ced0  lea     rax, [rbp+var_10]
0x18005ced4  mov     [rsp+50h+var_30], rax
0x18005ced9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005cede  mov     rbx, [rsp+50h+arg_0]
0x18005cee6  mov     eax, edi
0x18005cee8  add     rsp, 50h
0x18005ceec  pop     r15
0x18005ceee  pop     r14
0x18005cef0  pop     r13
0x18005cef2  pop     r12
0x18005cef4  pop     rdi
0x18005cef5  pop     rsi
0x18005cef6  pop     rbp
0x18005cef7  retn
0x18005cef8  cmp     r15d, 0FFFFFFFFh
0x18005cefc  jz      short loc_18005CF2E
0x18005cefe  call    cs:__imp_GetCurrentThread
0x18005cf04  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005cf08  xor     r8d, r8d; OpenAsSelf
0x18005cf0b  mov     rcx, rax; ThreadHandle
0x18005cf0e  mov     edx, 2000Ch; DesiredAccess
0x18005cf13  call    cs:__imp_OpenThreadToken
0x18005cf19  test    eax, eax
0x18005cf1b  jnz     short loc_18005CF2E
0x18005cf1d  call    cs:__imp_GetLastError
0x18005cf23  cmp     eax, 3F0h
0x18005cf28  jnz     loc_18005CE7C
0x18005cf2e  mov     r13, [rbp+arg_8]
0x18005cf32  lea     rcx, [r14+8]; lpCriticalSection
0x18005cf36  mov     [rsi+18h], r15d
0x18005cf3a  movups  xmm0, xmmword ptr [r13+0]
0x18005cf3f  movdqu  xmmword ptr [rsi], xmm0
0x18005cf43  mov     rax, [rbp+TokenHandle]
0x18005cf47  mov     [rsi+10h], rax
0x18005cf4b  call    cs:__imp_EnterCriticalSection
0x18005cf51  lea     rcx, [r14+170h]
0x18005cf58  mov     rdx, rsi
0x18005cf5b  mov     rax, [rcx]
0x18005cf5e  mov     rax, [rax+8]
0x18005cf62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf67  test    al, al
0x18005cf69  jnz     short loc_18005CF71
0x18005cf6b  mov     ebx, edi
0x18005cf6d  xor     edi, edi
0x18005cf6f  jmp     short loc_18005CF8A
0x18005cf71  cmp     r15d, 0FFFFFFFFh
0x18005cf75  jz      short loc_18005CF7C
0x18005cf77  lock add [r14+30h], edi
0x18005cf7c  mov     rcx, [r14+40h]; hEvent
0x18005cf80  xor     esi, esi
0x18005cf82  xor     ebx, ebx
0x18005cf84  call    cs:__imp_SetEvent
0x18005cf8a  lea     rcx, [r14+8]; lpCriticalSection
0x18005cf8e  call    cs:__imp_LeaveCriticalSection
0x18005cf94  test    ebx, ebx
0x18005cf96  jz      loc_18005CE9B
0x18005cf9c  jmp     loc_18005CE82
```
