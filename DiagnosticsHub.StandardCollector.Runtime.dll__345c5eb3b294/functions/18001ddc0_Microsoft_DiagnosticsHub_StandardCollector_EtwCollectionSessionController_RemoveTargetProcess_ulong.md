# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::RemoveTargetProcess(ulong)

- ea: `0x18001ddc0`
- end: `0x18001e0c6`
- name: `?RemoveTargetProcess@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJK@Z`
- size: `774`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18001ddc0`
- `0x180024494`
- `0x18003d864`
- `0x180041834`
- `0x180041938`
- `0x180041a18`
- `0x180049b50`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001dea4`
- `KERNEL32!WaitForSingleObject` at `0x18001dfc6`
- `KERNEL32!WaitForSingleObject` at `0x18001dea4`
- `KERNEL32!WaitForSingleObject` at `0x18001dfc6`
- `KERNEL32!SetEvent` at `0x18001df8f`
- `KERNEL32!SetEvent` at `0x18001df8f`
- `KERNEL32!ResetEvent` at `0x18001df6e`
- `KERNEL32!ResetEvent` at `0x18001df6e`
- `KERNEL32!LeaveCriticalSection` at `0x18001df9c`
- `KERNEL32!LeaveCriticalSection` at `0x18001e071`
- `KERNEL32!LeaveCriticalSection` at `0x18001df9c`
- `KERNEL32!LeaveCriticalSection` at `0x18001e071`
- `KERNEL32!EnterCriticalSection` at `0x18001de6b`
- `KERNEL32!EnterCriticalSection` at `0x18001de6b`
- `ADVAPI32!EventWrite` at `0x18001e00d`
- `ADVAPI32!EventWrite` at `0x18001e00d`

## string_xrefs

- `0x18001df02`: `Remove target process event creation failed. HRESULT: %#08x`
- `0x18001df37`: `Remove target process event consumption has exceeded expected usage velocity.`
- `0x18001e030`: `Failed to emit remove target process event for ID: %llu`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::RemoveTargetProcess(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        unsigned int a2)
{
  const unsigned __int16 *v5; // r8
  const struct _GUID *v6; // rdx
  unsigned int v7; // ebx
  int v8; // r14d
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  unsigned __int64 i; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  void *v13; // rcx
  signed __int64 v14; // rax
  __int64 v15; // rsi
  int v16; // r9d
  unsigned int v17; // esi
  char v18; // r14
  __int64 v19; // r14
  signed int v20; // r15d
  struct _GUID *v21[2]; // [rsp+20h] [rbp-30h] BYREF
  signed __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-18h] BYREF

  if ( *((_BYTE *)this + 2552) )
    return 3775987731LL;
  if ( !*((_BYTE *)this - 160) )
  {
    *(_OWORD *)v21 = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)v21,
      -518979564,
      *((_WORD *)this - 164));
    v6 = (const struct _GUID *)L"<unknown error>";
    if ( v21[0] )
      v6 = v21[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v6, v5);
    v7 = (unsigned int)v21[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v21);
    return v7;
  }
  v8 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2472);
  v21[0] = (struct _GUID *)((char *)this + 2472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2472));
  for ( i = 0; i < 0x280; i += 128LL )
  {
    v11 = *(_QWORD *)((char *)this + i + 1832);
    if ( v11 )
    {
      v12 = *(_QWORD *)((char *)this + i + 1840);
      if ( v12 )
      {
        if ( *(_QWORD *)(v11 + 16) )
        {
          v13 = *(void **)(v12 + 32);
          if ( v13 )
          {
            if ( WaitForSingleObject(v13, 0) && *((_BYTE *)this + i + 1936) )
              ++v8;
          }
        }
      }
    }
  }
  v14 = _InterlockedExchangeAdd64(
          &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::s_RemoveTargetProcessIdCounter,
          1u);
  v22 = v14 + 1;
  v15 = 3LL * (((_DWORD)v14 + 1) & 0x1F);
  v16 = *((_DWORD *)this + 6 * (((int)v14 + 1) & 0x1F) + 218);
  if ( v16 < 0 )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
      L"Remove target process event creation failed. HRESULT: %#08x");
    v17 = -2147418113;
LABEL_31:
    _mm_lfence();
    LeaveCriticalSection(v9);
    return v17;
  }
  if ( *((_DWORD *)this + 6 * (((int)v14 + 1) & 0x1F) + 214) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
      L"Remove target process event consumption has exceeded expected usage velocity.");
    v17 = -518922223;
    goto LABEL_31;
  }
  *((_DWORD *)this + 6 * (((int)v14 + 1) & 0x1F) + 214) = v8;
  if ( v16 >= 0 )
    ResetEvent(*((HANDLE *)this + 3 * (((int)v14 + 1) & 0x1F) + 108));
  if ( v8 )
  {
    UserData.Ptr = (ULONGLONG)&v22;
    *(_QWORD *)&UserData.Size = 8;
    v20 = EventWrite(
            *((_QWORD *)this + 205),
            &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::RemoveProcessEventDescriptor,
            1u,
            &UserData);
    if ( v20 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
        L"Failed to emit remove target process event for ID: %llu",
        v22,
        v21[0]);
      *((_DWORD *)this + 2 * v15 + 214) = 0;
      v17 = (unsigned __int16)v20 | 0x80070000;
      if ( v20 <= 0 )
        v17 = v20;
      goto LABEL_31;
    }
  }
  else if ( *((int *)this + 2 * v15 + 218) >= 0 )
  {
    SetEvent(*((HANDLE *)this + v15 + 108));
  }
  v18 = v22;
  LeaveCriticalSection(v9);
  v19 = (v18 & 0x1F) + 36LL;
  if ( *((int *)this + 6 * v19 + 2) >= 0 && !WaitForSingleObject(*((HANDLE *)this + 3 * v19), 0x2710u) )
    return Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::RemoveTargetProcessInternal(
             (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)this - 1024),
             a2);
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 168),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSyncController.cpp",
    L"Removing the target process timed out");
  return 1;
}

```

## disassembly

```asm
0x18001ddc0  mov     [rsp-28h+arg_10], rbx
0x18001ddc5  mov     [rsp-28h+arg_18], rsi
0x18001ddca  push    rbp
0x18001ddcb  push    rdi
0x18001ddcc  push    r12
0x18001ddce  push    r14
0x18001ddd0  push    r15
0x18001ddd2  mov     rbp, rsp
0x18001ddd5  sub     rsp, 50h
0x18001ddd9  mov     rax, cs:__security_cookie
0x18001dde0  xor     rax, rsp
0x18001dde3  mov     [rbp+var_8], rax
0x18001dde7  mov     r12d, edx
0x18001ddea  mov     rdi, rcx
0x18001dded  mov     al, [rcx+9F8h]
0x18001ddf3  test    al, al
0x18001ddf5  jz      short loc_18001DE01
0x18001ddf7  mov     eax, 0E1110013h
0x18001ddfc  jmp     loc_18001E0A1
0x18001de01  mov     al, [rcx-0A0h]
0x18001de07  test    al, al
0x18001de09  jnz     short loc_18001DE5A
0x18001de0b  xorps   xmm0, xmm0
0x18001de0e  movups  xmmword ptr [rbp+var_30], xmm0
0x18001de12  movzx   r8d, word ptr [rcx-148h]; unsigned __int16
0x18001de1a  mov     edx, 0E1110014h; int
0x18001de1f  lea     rcx, [rbp+var_30]; this
0x18001de23  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x18001de28  nop
0x18001de29  lea     rdx, aUnknownError; "<unknown error>"
0x18001de30  mov     rax, [rbp+var_30]
0x18001de34  test    rax, rax
0x18001de37  cmovnz  rdx, rax; struct _GUID *
0x18001de3b  lea     rcx, IID_ICollectionSession; this
0x18001de42  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18001de47  mov     ebx, dword ptr [rbp+var_30+8]
0x18001de4a  lea     rcx, [rbp+var_30]; this
0x18001de4e  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18001de53  mov     eax, ebx
0x18001de55  jmp     loc_18001E0A1
0x18001de5a  xor     r14d, r14d
0x18001de5d  lea     rbx, [rcx+9A8h]
0x18001de64  mov     [rbp+var_30], rbx
0x18001de68  mov     rcx, rbx; lpCriticalSection
0x18001de6b  call    cs:__imp_EnterCriticalSection
0x18001de71  nop
0x18001de72  xor     esi, esi
0x18001de74  lea     r15d, [r14+1]
0x18001de78  mov     rax, [rsi+rdi+728h]
0x18001de80  test    rax, rax
0x18001de83  jz      short loc_18001DEBB
0x18001de85  mov     rcx, [rsi+rdi+730h]
0x18001de8d  test    rcx, rcx
0x18001de90  jz      short loc_18001DEBB
0x18001de92  cmp     qword ptr [rax+10h], 0
0x18001de97  jz      short loc_18001DEBB
0x18001de99  mov     rcx, [rcx+20h]; hHandle
0x18001de9d  test    rcx, rcx
0x18001dea0  jz      short loc_18001DEBB
0x18001dea2  xor     edx, edx; dwMilliseconds
0x18001dea4  call    cs:__imp_WaitForSingleObject
0x18001deaa  test    eax, eax
0x18001deac  jz      short loc_18001DEBB
0x18001deae  cmp     byte ptr [rsi+rdi+790h], 0
0x18001deb6  jz      short loc_18001DEBB
0x18001deb8  add     r14d, r15d
0x18001debb  sub     rsi, 0FFFFFFFFFFFFFF80h
0x18001debf  cmp     rsi, 280h
0x18001dec6  jb      short loc_18001DE78
0x18001dec8  mov     rax, r15
0x18001decb  lock xadd cs:?s_RemoveTargetProcessIdCounter@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@0_JA, rax; __int64 Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::s_RemoveTargetProcessIdCounter
0x18001ded4  add     rax, r15
0x18001ded7  mov     [rbp+var_20], rax
0x18001dedb  and     eax, 1Fh
0x18001dede  lea     rsi, [rax+rax*2]
0x18001dee2  mov     r9d, [rdi+rsi*8+368h]
0x18001deea  mov     eax, r9d
0x18001deed  shr     eax, 1Fh
0x18001def0  test    al, al
0x18001def2  jz      short loc_18001DF1F
0x18001def4  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001defb  add     rcx, 0A8h; this
0x18001df02  lea     r8, aRemoveTargetPr; "Remove target process event creation fa"...
0x18001df09  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001df10  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001df15  mov     esi, 8000FFFFh
0x18001df1a  jmp     loc_18001E06B
0x18001df1f  cmp     dword ptr [rdi+rsi*8+358h], 0
0x18001df27  jz      short loc_18001DF54
0x18001df29  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001df30  add     rcx, 0A8h; this
0x18001df37  lea     r8, aRemoveTargetPr_0; "Remove target process event consumption"...
0x18001df3e  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001df45  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001df4a  mov     esi, 0E111E011h
0x18001df4f  jmp     loc_18001E06B
0x18001df54  mov     [rdi+rsi*8+358h], r14d
0x18001df5c  mov     eax, r9d
0x18001df5f  shr     eax, 1Fh
0x18001df62  test    al, al
0x18001df64  jnz     short loc_18001DF74
0x18001df66  mov     rcx, [rdi+rsi*8+360h]; hEvent
0x18001df6e  call    cs:__imp_ResetEvent
0x18001df74  test    r14d, r14d
0x18001df77  jnz     short loc_18001DFE8
0x18001df79  mov     eax, [rdi+rsi*8+368h]
0x18001df80  shr     eax, 1Fh
0x18001df83  test    al, al
0x18001df85  jnz     short loc_18001DF95
0x18001df87  mov     rcx, [rdi+rsi*8+360h]; hEvent
0x18001df8f  call    cs:__imp_SetEvent
0x18001df95  mov     r14, [rbp+var_20]
0x18001df99  mov     rcx, rbx; lpCriticalSection
0x18001df9c  call    cs:__imp_LeaveCriticalSection
0x18001dfa2  and     r14d, 1Fh
0x18001dfa6  add     r14, 24h ; '$'
0x18001dfaa  lea     rcx, [r14+r14*2]
0x18001dfae  mov     eax, [rdi+rcx*8+8]
0x18001dfb2  shr     eax, 1Fh
0x18001dfb5  test    al, al
0x18001dfb7  jnz     loc_18001E07B
0x18001dfbd  mov     edx, 2710h; dwMilliseconds
0x18001dfc2  mov     rcx, [rdi+rcx*8]; hHandle
0x18001dfc6  call    cs:__imp_WaitForSingleObject
0x18001dfcc  test    eax, eax
0x18001dfce  jnz     loc_18001E07B
0x18001dfd4  lea     rcx, [rdi-400h]; this
0x18001dfdb  mov     edx, r12d; unsigned int
0x18001dfde  call    ?RemoveTargetProcessInternal@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJK@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::RemoveTargetProcessInternal(ulong)
0x18001dfe3  jmp     loc_18001E0A1
0x18001dfe8  lea     rax, [rbp+var_20]
0x18001dfec  mov     [rbp+UserData.Ptr], rax
0x18001dff0  mov     qword ptr [rbp+UserData.Size], 8
0x18001dff8  lea     r9, [rbp+UserData]; UserData
0x18001dffc  mov     r8d, r15d; UserDataCount
0x18001dfff  lea     rdx, ?RemoveProcessEventDescriptor@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@1U_EVENT_DESCRIPTOR@@B; EventDescriptor
0x18001e006  mov     rcx, [rdi+668h]; RegHandle
0x18001e00d  call    cs:__imp_EventWrite
0x18001e013  mov     r15d, eax
0x18001e016  test    eax, eax
0x18001e018  jz      loc_18001DF95
0x18001e01e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001e025  add     rcx, 0A8h; this
0x18001e02c  mov     r9, [rbp+var_20]
0x18001e030  lea     r8, aFailedToEmitRe; "Failed to emit remove target process ev"...
0x18001e037  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001e03e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001e043  mov     r14, [rbp+var_20]
0x18001e047  mov     dword ptr [rdi+rsi*8+358h], 0
0x18001e052  movzx   esi, r15w
0x18001e056  or      esi, 80070000h
0x18001e05c  test    r15d, r15d
0x18001e05f  cmovle  esi, r15d
0x18001e063  test    esi, esi
0x18001e065  jns     loc_18001DF99
0x18001e06b  lfence
0x18001e06e  mov     rcx, rbx; lpCriticalSection
0x18001e071  call    cs:__imp_LeaveCriticalSection
0x18001e077  mov     eax, esi
0x18001e079  jmp     short loc_18001E0A1
0x18001e07b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001e082  add     rcx, 0A8h; this
0x18001e089  lea     r8, aRemovingTheTar; "Removing the target process timed out"
0x18001e090  lea     rdx, aDAWork1SSource_13; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001e097  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001e09c  mov     eax, 1
0x18001e0a1  mov     rcx, [rbp+var_8]
0x18001e0a5  xor     rcx, rsp; StackCookie
0x18001e0a8  call    __security_check_cookie
0x18001e0ad  lea     r11, [rsp+50h+var_s0]
0x18001e0b2  mov     rbx, [r11+40h]
0x18001e0b6  mov     rsi, [r11+48h]
0x18001e0ba  mov     rsp, r11
0x18001e0bd  pop     r15
0x18001e0bf  pop     r14
0x18001e0c1  pop     r12
0x18001e0c3  pop     rdi
0x18001e0c4  pop     rbp
0x18001e0c5  retn
```
