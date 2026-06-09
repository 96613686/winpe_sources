# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::OnEvent(ITraceEvent *,ITraceRelogger *)

- ea: `0x18001f2f0`
- end: `0x18001f729`
- name: `?OnEvent@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUITraceEvent@@PEAUITraceRelogger@@@Z`
- size: `1081`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this, struct ITraceEvent *, struct ITraceRelogger *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180010540`
- `0x180017dc4`
- `0x180018214`
- `0x18001f2f0`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18001f361`
- `VCRUNTIME140!memcmp` at `0x18001f361`
- `KERNEL32!SetEvent` at `0x18001f3b8`
- `KERNEL32!SetEvent` at `0x18001f448`
- `KERNEL32!SetEvent` at `0x18001f3b8`
- `KERNEL32!SetEvent` at `0x18001f448`
- `KERNEL32!GetCurrentProcessId` at `0x18001f583`
- `KERNEL32!GetCurrentProcessId` at `0x18001f583`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001f504`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001f67b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001f504`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001f67b`
- `KERNEL32!AcquireSRWLockShared` at `0x18001f491`
- `KERNEL32!AcquireSRWLockShared` at `0x18001f5e1`
- `KERNEL32!AcquireSRWLockShared` at `0x18001f491`
- `KERNEL32!AcquireSRWLockShared` at `0x18001f5e1`

## string_xrefs

- `0x18001f393`: `Unexpected remove target process signal result. Error code: 0x%08x`
- `0x18001f643`: `Removing IStandardCollectorEtwAgent - event callback failed with %#08x`
- `0x18001f6cb`: `Rundown agent - event callback failed with %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::OnEvent(
        RTL_SRWLOCK *this,
        struct ITraceEvent *a2,
        struct ITraceRelogger *a3)
{
  struct ITraceRelogger *v3; // r13
  struct ITraceEvent *v4; // r15
  _DWORD *v6; // rax
  __int64 v7; // rcx
  _DWORD *UserData; // rax
  __int64 v10; // rcx
  unsigned int v11; // r12d
  int v12; // r14d
  __m128i v13; // xmm6
  __m128i *v14; // rdx
  _QWORD *v15; // rax
  __m128i *v16; // rdx
  __int64 ProcessIdFromSystemEventRecord; // rbx
  int v18; // eax
  char v19; // si
  struct _EVENT_RECORD *v20; // rbx
  RTL_SRWLOCK *v21; // r15
  _BYTE *Ptr; // r12
  _BYTE *v23; // rbx
  int v24; // eax
  int v25; // eax
  unsigned int v26; // [rsp+38h] [rbp-49h]
  __m128i v27; // [rsp+48h] [rbp-39h] BYREF
  struct ITraceRelogger *v28; // [rsp+58h] [rbp-29h]
  struct ITraceEvent *v29; // [rsp+60h] [rbp-21h]
  _BYTE v30[8]; // [rsp+68h] [rbp-19h] BYREF
  struct _EVENT_RECORD *v31; // [rsp+70h] [rbp-11h] BYREF
  unsigned int *v32; // [rsp+78h] [rbp-9h] BYREF
  char v33; // [rsp+80h] [rbp-1h] BYREF
  _BYTE v34[7]; // [rsp+81h] [rbp+0h] BYREF

  v3 = a3;
  v28 = a3;
  v4 = a2;
  v29 = a2;
  if ( (*(int (__fastcall **)(struct ITraceEvent *, struct _EVENT_RECORD **))(*(_QWORD *)a2 + 40LL))(a2, &v31) < 0 )
    return 0;
  if ( memcmp(&v31->EventHeader.ProviderId, &this[201], 0x10u) )
  {
LABEL_17:
    _mm_lfence();
    v32 = 0;
    (*(void (__fastcall **)(struct ITraceEvent *, unsigned int **))(*(_QWORD *)v4 + 32LL))(v4, &v32);
    v11 = *v32;
    v26 = *v32;
    v12 = 0;
    v27.m128i_i64[0] = 0;
    v27.m128i_i32[2] = 0;
    v13 = v27;
    AcquireSRWLockShared(this + 226);
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v15 = *(_QWORD **)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                            &this[218],
                            v30);
        if ( v15 != this[219].Ptr )
          goto LABEL_23;
      }
      v14 = &v27;
    }
    else
    {
      v14 = (__m128i *)v30;
    }
    v15 = *(_QWORD **)std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
                        &this[218],
                        v14);
    if ( v15 == this[219].Ptr )
    {
LABEL_24:
      ReleaseSRWLockShared(this + 226);
      if ( !v11
        && Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::IsTargetedChildProcessCreate(
             (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter *)&this[1],
             v31) )
      {
        ProcessIdFromSystemEventRecord = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetProcessIdFromSystemEventRecord(v31);
        v18 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, __int64))this[-2].Ptr + 9))(
                this - 2,
                ProcessIdFromSystemEventRecord,
                4);
        if ( v18 < 0 )
        {
          _mm_lfence();
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 112),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
            L"Failed to add child process (ID: %d). %#08x",
            (unsigned int)ProcessIdFromSystemEventRecord,
            v18);
        }
      }
      v19 = 1;
      if ( (v12 & 1) != 0 )
      {
        if ( (v12 & 8) == 0 || (v20 = v31, GetCurrentProcessId() != v20->EventHeader.ProcessId) )
        {
          if ( !((__int64 (__fastcall *)(char *, struct _EVENT_RECORD *))v13.m128i_i64[0])(
                  (char *)&this[-130] + _mm_cvtsi128_si32(_mm_srli_si128(v13, 8)),
                  v31) )
            return 0;
        }
      }
      if ( (v12 & 2) != 0 )
      {
        v19 = 0;
        v21 = this - 63;
        v27.m128i_i64[0] = (__int64)&this[-63];
        v27.m128i_i32[2] = 0;
        AcquireSRWLockShared(this - 63);
        Ptr = this[-61].Ptr;
        v23 = this[-62].Ptr;
        if ( v23 != Ptr )
        {
          do
          {
            v33 = 0;
            if ( !v23[8] )
            {
              v24 = (*(__int64 (__fastcall **)(_QWORD, struct _EVENT_RECORD *, _QWORD, char *))(**(_QWORD **)v23 + 40LL))(
                      *(_QWORD *)v23,
                      v31,
                      v26,
                      &v33);
              if ( v24 >= 0 )
              {
                if ( v33 )
                  v19 = 1;
              }
              else
              {
                _mm_lfence();
                v23[8] = 1;
                DiagHubCommon::LogStream::Write(
                  (DiagHubCommon::LogStream *)((char *)_logger + 56),
                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
                  L"Removing IStandardCollectorEtwAgent - event callback failed with %#08x",
                  (unsigned int)v24);
              }
            }
            v23 += 16;
          }
          while ( v23 != Ptr );
          v21 = this - 63;
          v3 = v28;
        }
        ReleaseSRWLockShared(v21);
        v4 = v29;
        v11 = v26;
      }
      v34[0] = 0;
      if ( v12 < 0 )
      {
        v25 = (*(__int64 (__fastcall **)(PVOID, struct _EVENT_RECORD *, _QWORD, _BYTE *))(*(_QWORD *)this[215].Ptr + 40LL))(
                this[215].Ptr,
                v31,
                v11,
                v34);
        if ( v25 < 0 )
        {
          _mm_lfence();
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
            L"Rundown agent - event callback failed with %#08x",
            (unsigned int)v25);
        }
      }
      if ( !v19 && !v34[0] && (v12 & 4) == 0 )
        return 0;
LABEL_9:
      _mm_lfence();
      return (*(__int64 (__fastcall **)(struct ITraceRelogger *, struct ITraceEvent *))(*(_QWORD *)v3 + 48LL))(v3, v4);
    }
LABEL_23:
    v16 = (__m128i *)v15[4];
    v13 = v16[3];
    v12 = v16[1].m128i_i32[1];
    goto LABEL_24;
  }
  if ( v31->EventHeader.EventDescriptor.Id != 2 )
  {
    if ( BYTE4(this[206].Ptr) && v31->EventHeader.EventDescriptor.Id == 1 )
    {
      UserData = v31->UserData;
      v10 = 3 * ((*UserData & 0x1F) + 3LL);
      if ( LODWORD(this[3 * (*UserData & 0x1F) + 9].Ptr) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)&this[3 * (*UserData & 0x1F) + 9], 0xFFFFFFFF) == 1
          && SLODWORD(this[v10 + 2].Ptr) >= 0 )
        {
          SetEvent(this[v10 + 1].Ptr);
        }
      }
      else
      {
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
          L"Unexpected flush signal result. Error code: 0x%08x",
          1);
      }
      return 0;
    }
    goto LABEL_17;
  }
  v6 = v31->UserData;
  v7 = 3 * ((*v6 & 0x1F) + 35LL);
  if ( LODWORD(this[3 * (*v6 & 0x1F) + 105].Ptr) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&this[3 * (*v6 & 0x1F) + 105], 0xFFFFFFFF) == 1
      && SLODWORD(this[v7 + 2].Ptr) >= 0 )
    {
      SetEvent(this[v7 + 1].Ptr);
    }
    goto LABEL_9;
  }
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 56),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
    L"Unexpected remove target process signal result. Error code: 0x%08x",
    1);
  return 0;
}

```

## disassembly

```asm
0x18001f2f0  mov     rax, rsp
0x18001f2f3  mov     [rax+20h], rbx
0x18001f2f7  push    rbp
0x18001f2f8  push    rsi
0x18001f2f9  push    rdi
0x18001f2fa  push    r12
0x18001f2fc  push    r13
0x18001f2fe  push    r14
0x18001f300  push    r15
0x18001f302  lea     rbp, [rax-5Fh]
0x18001f306  sub     rsp, 0A0h
0x18001f30d  movaps  xmmword ptr [rax-48h], xmm6
0x18001f311  mov     rax, cs:__security_cookie
0x18001f318  xor     rax, rsp
0x18001f31b  mov     [rbp+57h+var_50], rax
0x18001f31f  mov     r13, r8
0x18001f322  mov     [rbp+57h+var_80], r8
0x18001f326  mov     r15, rdx
0x18001f329  mov     [rbp+57h+var_78], rdx
0x18001f32d  mov     rdi, rcx
0x18001f330  mov     rax, [rdx]
0x18001f333  lea     rdx, [rbp+57h+var_68]
0x18001f337  mov     rcx, r15
0x18001f33a  mov     rax, [rax+28h]
0x18001f33e  call    cs:__guard_dispatch_icall_fptr
0x18001f344  xor     ebx, ebx
0x18001f346  test    eax, eax
0x18001f348  js      loc_18001F6FB
0x18001f34e  lea     rdx, [rdi+648h]; Buf2
0x18001f355  mov     rcx, [rbp+57h+var_68]
0x18001f359  add     rcx, 18h; Buf1
0x18001f35d  lea     r8d, [rbx+10h]; Size
0x18001f361  call    cs:__imp_memcmp
0x18001f367  lea     edx, [rbx+1]
0x18001f36a  test    eax, eax
0x18001f36c  jnz     loc_18001F453
0x18001f372  mov     rax, [rbp+57h+var_68]
0x18001f376  cmp     word ptr [rax+28h], 2
0x18001f37b  jnz     short loc_18001F3DA
0x18001f37d  mov     rax, [rax+60h]
0x18001f381  mov     ecx, [rax]
0x18001f383  and     ecx, 1Fh
0x18001f386  add     rcx, 23h ; '#'
0x18001f38a  lea     rcx, [rcx+rcx*2]
0x18001f38e  cmp     [rdi+rcx*8], ebx
0x18001f391  jnz     short loc_18001F39C
0x18001f393  lea     r8, aUnexpectedRemo; "Unexpected remove target process signal"...
0x18001f39a  jmp     short loc_18001F405
0x18001f39c  or      eax, 0FFFFFFFFh
0x18001f39f  lock xadd [rdi+rcx*8], eax
0x18001f3a4  cmp     eax, edx
0x18001f3a6  jnz     short loc_18001F3BE
0x18001f3a8  mov     eax, [rdi+rcx*8+10h]
0x18001f3ac  shr     eax, 1Fh
0x18001f3af  test    al, al
0x18001f3b1  jnz     short loc_18001F3BE
0x18001f3b3  mov     rcx, [rdi+rcx*8+8]; hEvent
0x18001f3b8  call    cs:__imp_SetEvent
0x18001f3be  lfence
0x18001f3c1  mov     rax, [r13+0]
0x18001f3c5  mov     rdx, r15
0x18001f3c8  mov     rcx, r13
0x18001f3cb  mov     rax, [rax+30h]
0x18001f3cf  call    cs:__guard_dispatch_icall_fptr
0x18001f3d5  jmp     loc_18001F6FD
0x18001f3da  cmp     [rdi+674h], bl
0x18001f3e0  jz      short loc_18001F453
0x18001f3e2  cmp     [rax+28h], dx
0x18001f3e6  jnz     short loc_18001F453
0x18001f3e8  mov     rax, [rax+60h]
0x18001f3ec  mov     ecx, [rax]
0x18001f3ee  and     ecx, 1Fh
0x18001f3f1  add     rcx, 3
0x18001f3f5  lea     rcx, [rcx+rcx*2]
0x18001f3f9  cmp     [rdi+rcx*8], ebx
0x18001f3fc  jnz     short loc_18001F424
0x18001f3fe  lea     r8, aUnexpectedFlus; "Unexpected flush signal result. Error c"...
0x18001f405  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001f40c  mov     r9d, edx
0x18001f40f  add     rcx, 38h ; '8'; this
0x18001f413  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001f41a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001f41f  jmp     loc_18001F6FB
0x18001f424  or      eax, 0FFFFFFFFh
0x18001f427  lock xadd [rdi+rcx*8], eax
0x18001f42c  cmp     eax, edx
0x18001f42e  jnz     loc_18001F6FB
0x18001f434  mov     eax, [rdi+rcx*8+10h]
0x18001f438  shr     eax, 1Fh
0x18001f43b  test    al, al
0x18001f43d  jnz     loc_18001F6FB
0x18001f443  mov     rcx, [rdi+rcx*8+8]; hEvent
0x18001f448  call    cs:__imp_SetEvent
0x18001f44e  jmp     loc_18001F6FB
0x18001f453  lfence
0x18001f456  mov     [rbp+57h+var_60], rbx
0x18001f45a  mov     rax, [r15]
0x18001f45d  lea     rdx, [rbp+57h+var_60]
0x18001f461  mov     rcx, r15
0x18001f464  mov     rax, [rax+20h]
0x18001f468  call    cs:__guard_dispatch_icall_fptr
0x18001f46e  mov     rax, [rbp+57h+var_60]
0x18001f472  mov     r12d, [rax]
0x18001f475  mov     [rbp+57h+var_A0], r12d
0x18001f479  mov     r14d, ebx
0x18001f47c  mov     qword ptr [rbp+57h+var_90], rbx
0x18001f480  mov     dword ptr [rbp+57h+var_90+8], ebx
0x18001f483  movaps  xmm6, [rbp+57h+var_90]
0x18001f487  lea     rsi, [rdi+710h]
0x18001f48e  mov     rcx, rsi; SRWLock
0x18001f491  call    cs:__imp_AcquireSRWLockShared
0x18001f497  lea     rbx, [rdi+6D0h]
0x18001f49e  test    r12d, r12d
0x18001f4a1  jnz     short loc_18001F4B0
0x18001f4a3  lea     r8, SystemTraceControlGuid
0x18001f4aa  lea     rdx, [rbp+57h+var_70]
0x18001f4ae  jmp     short loc_18001F4E1
0x18001f4b0  mov     r8, [rbp+57h+var_68]
0x18001f4b4  add     r8, 18h
0x18001f4b8  cmp     r12d, 1
0x18001f4bc  jnz     short loc_18001F4DD
0x18001f4be  lea     rdx, [rbp+57h+var_70]
0x18001f4c2  mov     rcx, rbx
0x18001f4c5  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18001f4ca  mov     rax, [rax]
0x18001f4cd  cmp     rax, [rdi+6D8h]
0x18001f4d4  jnz     short loc_18001F4F5
0x18001f4d6  lea     r8, ?HeapTraceProviderGuid@HeapTraceSession@EventTrace@Microsoft@@2U_GUID@@B; _GUID const Microsoft::EventTrace::HeapTraceSession::HeapTraceProviderGuid
0x18001f4dd  lea     rdx, [rbp+57h+var_90]
0x18001f4e1  mov     rcx, rbx
0x18001f4e4  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x18001f4e9  mov     rax, [rax]
0x18001f4ec  cmp     rax, [rdi+6D8h]
0x18001f4f3  jz      short loc_18001F501
0x18001f4f5  mov     rdx, [rax+20h]
0x18001f4f9  movups  xmm6, xmmword ptr [rdx+30h]
0x18001f4fd  mov     r14d, [rdx+14h]
0x18001f501  mov     rcx, rsi; SRWLock
0x18001f504  call    cs:__imp_ReleaseSRWLockShared
0x18001f50a  test    r12d, r12d
0x18001f50d  jnz     short loc_18001F56F
0x18001f50f  lea     rcx, [rdi+8]; this
0x18001f513  mov     rdx, [rbp+57h+var_68]; struct _EVENT_RECORD *
0x18001f517  call    ?IsTargetedChildProcessCreate@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@IEAA_NAEBU_EVENT_RECORD@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::IsTargetedChildProcessCreate(_EVENT_RECORD const &)
0x18001f51c  test    al, al
0x18001f51e  jz      short loc_18001F56F
0x18001f520  mov     rcx, [rbp+57h+var_68]; this
0x18001f524  call    ?GetProcessIdFromSystemEventRecord@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@SAIAEBU_EVENT_RECORD@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetProcessIdFromSystemEventRecord(_EVENT_RECORD const &)
0x18001f529  mov     ebx, eax
0x18001f52b  lea     rcx, [rdi-10h]
0x18001f52f  mov     rdx, [rcx]
0x18001f532  mov     rax, [rdx+48h]
0x18001f536  lea     r8d, [r12+4]
0x18001f53b  mov     edx, ebx
0x18001f53d  call    cs:__guard_dispatch_icall_fptr
0x18001f543  test    eax, eax
0x18001f545  jns     short loc_18001F56F
0x18001f547  lfence
0x18001f54a  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001f551  add     rcx, 70h ; 'p'; this
0x18001f555  mov     [rsp+0D0h+var_B0], eax
0x18001f559  mov     r9d, ebx
0x18001f55c  lea     r8, aFailedToAddChi; "Failed to add child process (ID: %d). %"...
0x18001f563  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001f56a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001f56f  mov     esi, 1
0x18001f574  test    sil, r14b
0x18001f577  jz      short loc_18001F5BF
0x18001f579  test    r14b, 8
0x18001f57d  jz      short loc_18001F58E
0x18001f57f  mov     rbx, [rbp+57h+var_68]
0x18001f583  call    cs:__imp_GetCurrentProcessId
0x18001f589  cmp     eax, [rbx+0Ch]
0x18001f58c  jz      short loc_18001F5BF
0x18001f58e  movdqa  xmm0, xmm6
0x18001f592  psrldq  xmm0, 8
0x18001f597  movd    eax, xmm0
0x18001f59b  movsxd  rcx, eax
0x18001f59e  add     rcx, 0FFFFFFFFFFFFFBF0h
0x18001f5a5  add     rcx, rdi
0x18001f5a8  movq    rax, xmm6
0x18001f5ad  mov     rdx, [rbp+57h+var_68]
0x18001f5b1  call    cs:__guard_dispatch_icall_fptr
0x18001f5b7  test    al, al
0x18001f5b9  jz      loc_18001F6FB
0x18001f5bf  test    r14b, 2
0x18001f5c3  jz      loc_18001F689
0x18001f5c9  xor     sil, sil
0x18001f5cc  lea     r15, [rdi-1F8h]
0x18001f5d3  mov     qword ptr [rbp+57h+var_90], r15
0x18001f5d7  mov     dword ptr [rbp+57h+var_90+8], 0
0x18001f5de  mov     rcx, r15; SRWLock
0x18001f5e1  call    cs:__imp_AcquireSRWLockShared
0x18001f5e7  nop
0x18001f5e8  mov     r12, [rdi-1E8h]
0x18001f5ef  mov     rbx, [rdi-1F0h]
0x18001f5f6  cmp     rbx, r12
0x18001f5f9  jz      short loc_18001F678
0x18001f5fb  mov     r15d, [rbp+57h+var_A0]
0x18001f5ff  mov     r13d, 1
0x18001f605  mov     [rbp+57h+var_58], 0
0x18001f609  cmp     byte ptr [rbx+8], 0
0x18001f60d  jnz     short loc_18001F664
0x18001f60f  mov     rcx, [rbx]
0x18001f612  mov     rax, [rcx]
0x18001f615  lea     r9, [rbp+57h+var_58]
0x18001f619  mov     r8d, r15d
0x18001f61c  mov     rdx, [rbp+57h+var_68]
0x18001f620  mov     rax, [rax+28h]
0x18001f624  call    cs:__guard_dispatch_icall_fptr
0x18001f62a  test    eax, eax
0x18001f62c  jns     short loc_18001F658
0x18001f62e  lfence
0x18001f631  mov     [rbx+8], r13b
0x18001f635  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001f63c  add     rcx, 38h ; '8'; this
0x18001f640  mov     r9d, eax
0x18001f643  lea     r8, aRemovingIstand_4; "Removing IStandardCollectorEtwAgent - e"...
0x18001f64a  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001f651  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001f656  jmp     short loc_18001F664
0x18001f658  movzx   esi, sil
0x18001f65c  cmp     [rbp+57h+var_58], 0
0x18001f660  cmovnz  esi, r13d
0x18001f664  add     rbx, 10h
0x18001f668  cmp     rbx, r12
0x18001f66b  jnz     short loc_18001F605
0x18001f66d  lea     r15, [rdi-1F8h]
0x18001f674  mov     r13, [rbp+57h+var_80]
0x18001f678  mov     rcx, r15; SRWLock
0x18001f67b  call    cs:__imp_ReleaseSRWLockShared
0x18001f681  mov     r15, [rbp+57h+var_78]
0x18001f685  mov     r12d, [rbp+57h+var_A0]
0x18001f689  mov     [rbp+57h+var_57], 0
0x18001f68d  mov     eax, r14d
0x18001f690  shr     eax, 1Fh
0x18001f693  test    al, al
0x18001f695  jz      short loc_18001F6DE
0x18001f697  mov     rcx, [rdi+6B8h]
0x18001f69e  mov     rax, [rcx]
0x18001f6a1  lea     r9, [rbp+57h+var_57]
0x18001f6a5  mov     r8d, r12d
0x18001f6a8  mov     rdx, [rbp+57h+var_68]
0x18001f6ac  mov     rax, [rax+28h]
0x18001f6b0  call    cs:__guard_dispatch_icall_fptr
0x18001f6b6  test    eax, eax
0x18001f6b8  jns     short loc_18001F6DE
0x18001f6ba  lfence
0x18001f6bd  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001f6c4  add     rcx, 38h ; '8'; this
0x18001f6c8  mov     r9d, eax
0x18001f6cb  lea     r8, aRundownAgentEv; "Rundown agent - event callback failed w"...
0x18001f6d2  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001f6d9  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001f6de  test    sil, sil
0x18001f6e1  jnz     loc_18001F3BE
0x18001f6e7  cmp     [rbp+57h+var_57], sil
0x18001f6eb  jnz     loc_18001F3BE
0x18001f6f1  test    r14b, 4
0x18001f6f5  jnz     loc_18001F3BE
0x18001f6fb  xor     eax, eax
0x18001f6fd  mov     rcx, [rbp+57h+var_50]
0x18001f701  xor     rcx, rsp; StackCookie
0x18001f704  call    __security_check_cookie
0x18001f709  lea     r11, [rsp+0D0h+var_30]
0x18001f711  mov     rbx, [r11+58h]
0x18001f715  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f71a  mov     rsp, r11
0x18001f71d  pop     r15
0x18001f71f  pop     r14
0x18001f721  pop     r13
0x18001f723  pop     r12
0x18001f725  pop     rdi
0x18001f726  pop     rsi
0x18001f727  pop     rbp
0x18001f728  retn
```
