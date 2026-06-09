# Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::OnEtwEvent(_EVENT_RECORD const *,ulong,bool *)

- ea: `0x180019f70`
- end: `0x18001a2b7`
- name: `?OnEtwEvent@RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEBU_EVENT_RECORD@@KPEA_N@Z`
- size: `839`
- prototype: `int(Microsoft::DiagnosticsHub::StandardCollector::RundownAgent *__hidden this, const struct _EVENT_RECORD *, unsigned int, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180017dc4`
- `0x1800186a4`
- `0x180019f70`
- `0x18001a2b8`
- `0x18003d864`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180019fbf`
- `VCRUNTIME140!memcmp` at `0x18001a106`
- `VCRUNTIME140!memcmp` at `0x18001a158`
- `VCRUNTIME140!memcmp` at `0x18001a1e3`
- `VCRUNTIME140!memcmp` at `0x180019fbf`
- `VCRUNTIME140!memcmp` at `0x18001a106`
- `VCRUNTIME140!memcmp` at `0x18001a158`
- `VCRUNTIME140!memcmp` at `0x18001a1e3`
- `KERNEL32!SetEvent` at `0x18001a297`
- `KERNEL32!SetEvent` at `0x18001a297`
- `KERNEL32!LeaveCriticalSection` at `0x18001a0e7`
- `KERNEL32!LeaveCriticalSection` at `0x18001a0e7`
- `KERNEL32!EnterCriticalSection` at `0x180019ff1`
- `KERNEL32!EnterCriticalSection` at `0x180019ff1`

## string_xrefs

- `0x18001a00f`: `System trace rundown for target processes complete`
- `0x18001a269`: `Rundown complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::OnEtwEvent(
        Microsoft::DiagnosticsHub::StandardCollector::RundownAgent *this,
        const struct _EVENT_RECORD *a2,
        int a3,
        bool *a4)
{
  GUID *p_ProviderId; // r15
  unsigned int ProcessIdFromSystemEventRecord; // esi
  __int64 *v9; // rdx
  __int64 *v10; // rcx
  __int64 *v11; // rax
  __int64 **v12; // rdx
  __int64 *v13; // r8
  __int64 *i; // rcx
  __int64 *j; // rdx
  void *v16; // rax
  bool v17; // zf
  __int64 v18; // rcx
  __int64 ProcessId; // r9
  __int64 v20; // rcx
  __int64 v21; // r9
  char *k; // rax
  __int64 v23; // rcx

  p_ProviderId = &a2->EventHeader.ProviderId;
  *a4 = 0;
  if ( *((_BYTE *)this + 24) && a3 == *((_DWORD *)this + 56) )
  {
    if ( !memcmp(p_ProviderId, qword_1800569F8, 0x10u) && a2->EventHeader.EventDescriptor.Opcode == 3 )
    {
      ProcessIdFromSystemEventRecord = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetProcessIdFromSystemEventRecord(a2);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
      if ( *((_QWORD *)this + 10) )
      {
        v9 = (__int64 *)*((_QWORD *)this + 9);
        v10 = (__int64 *)v9[1];
        v11 = v9;
        while ( !*((_BYTE *)v10 + 25) )
        {
          if ( *((_DWORD *)v10 + 7) >= ProcessIdFromSystemEventRecord )
            v11 = v10;
          else
            v10 += 2;
          v10 = (__int64 *)*v10;
        }
        if ( !*((_BYTE *)v11 + 25) && ProcessIdFromSystemEventRecord >= *((_DWORD *)v11 + 7) && v11 != v9 )
        {
          *((_BYTE *)this + 25) = 1;
          v12 = (__int64 **)v11[2];
          v13 = v11;
          if ( *((_BYTE *)v12 + 25) )
          {
            for ( i = (__int64 *)v11[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v11 = i;
          }
          else
          {
            for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              ;
          }
          v16 = (void *)std::_Tree_val<std::_Tree_simple_types<unsigned int>>::_Extract((char *)this + 72, v13);
          operator delete(v16);
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
            L"System trace rundown for process %d started",
            ProcessIdFromSystemEventRecord);
        }
      }
      else
      {
        if ( *((_BYTE *)this + 25) )
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
            L"System trace rundown for target processes complete");
        *((_WORD *)this + 12) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    }
    else
    {
      if ( !*((_BYTE *)this + 25) )
        goto LABEL_50;
      if ( !memcmp(p_ProviderId, &EventTraceGuid, 0x10u) && a2->EventHeader.EventDescriptor.Opcode == 8 )
      {
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
          L"System trace rundown has ended");
        *((_WORD *)this + 12) = 0;
      }
    }
    v17 = *((_BYTE *)this + 25) == 0;
LABEL_40:
    if ( v17 )
      goto LABEL_50;
LABEL_49:
    *a4 = 1;
    goto LABEL_50;
  }
  if ( *((_BYTE *)this + 88) && !memcmp(p_ProviderId, &stru_1800569D8, 0x10u) )
  {
    ProcessId = a2->EventHeader.ProcessId;
    if ( a2->EventHeader.EventDescriptor.Id == 147 )
    {
      *((_BYTE *)this + 89) = 1;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
        L"Rundown '%d' for process %d started",
        1,
        ProcessId);
    }
    else if ( a2->EventHeader.EventDescriptor.Id == 145 )
    {
      Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::HandleEndOfRundown(
        v18,
        1,
        (char *)this + 88,
        ProcessId);
    }
    v17 = *((_BYTE *)this + 89) == 0;
    goto LABEL_40;
  }
  if ( !*((_BYTE *)this + 152) || memcmp(p_ProviderId, qword_1800569C8, 0x10u) )
    return 0;
  v21 = a2->EventHeader.ProcessId;
  if ( a2->EventHeader.EventDescriptor.Id == 1 )
  {
    *((_BYTE *)this + 153) = 1;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
      L"Rundown '%d' for process %d started",
      2,
      v21);
  }
  else if ( a2->EventHeader.EventDescriptor.Id == 2 )
  {
    Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::HandleEndOfRundown(v20, 2, (char *)this + 152, v21);
  }
  if ( *((_BYTE *)this + 153) )
    goto LABEL_49;
LABEL_50:
  for ( k = (char *)this + 24; k != (char *)this + 216; k += 64 )
  {
    if ( *k || k[1] )
      return 0;
  }
  DiagHubCommon::LogStream::Write(
    _logger,
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
    L"Rundown complete");
  v23 = *((_QWORD *)this + 27);
  if ( *(int *)(v23 + 8) >= 0 )
    SetEvent(*(HANDLE *)v23);
  return 0;
}

```

## disassembly

```asm
0x180019f70  mov     [rsp+arg_10], rbx
0x180019f75  push    rbp
0x180019f76  push    rsi
0x180019f77  push    rdi
0x180019f78  push    r12
0x180019f7a  push    r13
0x180019f7c  push    r14
0x180019f7e  push    r15
0x180019f80  sub     rsp, 40h
0x180019f84  mov     r12, r9
0x180019f87  mov     rbx, rdx
0x180019f8a  mov     rdi, rcx
0x180019f8d  lea     r15, [rdx+18h]
0x180019f91  xor     r13d, r13d
0x180019f94  mov     [r9], r13b
0x180019f97  cmp     [rcx+18h], r13b
0x180019f9b  jz      loc_18001A13F
0x180019fa1  cmp     r8d, [rcx+0E0h]
0x180019fa8  jnz     loc_18001A13F
0x180019fae  lea     r14d, [r13+10h]
0x180019fb2  mov     r8d, r14d; Size
0x180019fb5  lea     rdx, qword_1800569F8; Buf2
0x180019fbc  mov     rcx, r15; Buf1
0x180019fbf  call    cs:__imp_memcmp
0x180019fc5  lea     ebp, [r13+1]
0x180019fc9  test    eax, eax
0x180019fcb  jnz     loc_18001A0EF
0x180019fd1  cmp     byte ptr [rbx+2Dh], 3
0x180019fd5  jnz     loc_18001A0EF
0x180019fdb  mov     rcx, rbx; this
0x180019fde  call    ?GetProcessIdFromSystemEventRecord@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@SAIAEBU_EVENT_RECORD@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::GetProcessIdFromSystemEventRecord(_EVENT_RECORD const &)
0x180019fe3  mov     esi, eax
0x180019fe5  lea     rbx, [rdi+20h]
0x180019fe9  mov     [rsp+78h+var_48], rbx
0x180019fee  mov     rcx, rbx; lpCriticalSection
0x180019ff1  call    cs:__imp_EnterCriticalSection
0x180019ff7  nop
0x180019ff8  cmp     [rdi+50h], r13
0x180019ffc  jnz     short loc_18001A02C
0x180019ffe  cmp     [rdi+19h], r13b
0x18001a002  jz      short loc_18001A022
0x18001a004  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001a00b  add     rcx, 38h ; '8'; this
0x18001a00f  lea     r8, aSystemTraceRun; "System trace rundown for target process"...
0x18001a016  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001a01d  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001a022  mov     [rdi+18h], r13w
0x18001a027  jmp     loc_18001A0E4
0x18001a02c  mov     rdx, [rdi+48h]
0x18001a030  mov     rcx, [rdx+8]
0x18001a034  mov     rax, rdx
0x18001a037  jmp     short loc_18001A04A
0x18001a039  cmp     [rcx+1Ch], esi
0x18001a03c  jnb     short loc_18001A044
0x18001a03e  add     rcx, 10h
0x18001a042  jmp     short loc_18001A047
0x18001a044  mov     rax, rcx
0x18001a047  mov     rcx, [rcx]
0x18001a04a  cmp     [rcx+19h], r13b
0x18001a04e  jz      short loc_18001A039
0x18001a050  cmp     [rax+19h], r13b
0x18001a054  jnz     loc_18001A0E4
0x18001a05a  cmp     esi, [rax+1Ch]
0x18001a05d  jb      loc_18001A0E4
0x18001a063  cmp     rax, rdx
0x18001a066  jz      short loc_18001A0E4
0x18001a068  mov     [rdi+19h], bpl
0x18001a06c  mov     rdx, [rax+10h]
0x18001a070  mov     r8, rax
0x18001a073  cmp     [rdx+19h], r13b
0x18001a077  jz      short loc_18001A094
0x18001a079  mov     rcx, [rax+8]
0x18001a07d  jmp     short loc_18001A08C
0x18001a07f  cmp     rax, [rcx+10h]
0x18001a083  jnz     short loc_18001A0A9
0x18001a085  mov     rax, rcx
0x18001a088  mov     rcx, [rcx+8]
0x18001a08c  cmp     [rcx+19h], r13b
0x18001a090  jz      short loc_18001A07F
0x18001a092  jmp     short loc_18001A0A9
0x18001a094  mov     rdx, [rdx]
0x18001a097  cmp     [rdx+19h], r13b
0x18001a09b  jnz     short loc_18001A0A9
0x18001a09d  mov     rax, [rdx]
0x18001a0a0  mov     rdx, rax
0x18001a0a3  cmp     [rax+19h], r13b
0x18001a0a7  jz      short loc_18001A09D
0x18001a0a9  mov     rdx, r8
0x18001a0ac  lea     rcx, [rdi+48h]
0x18001a0b0  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@QEAAPEAU?$_Tree_node@IPEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<uint>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<uint>>,std::_Iterator_base0>)
0x18001a0b5  mov     edx, 20h ; ' '
0x18001a0ba  mov     rcx, rax; Block
0x18001a0bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a0c2  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001a0c9  add     rcx, 38h ; '8'; this
0x18001a0cd  mov     r9d, esi
0x18001a0d0  lea     r8, aSystemTraceRun_0; "System trace rundown for process %d sta"...
0x18001a0d7  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001a0de  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001a0e3  nop
0x18001a0e4  mov     rcx, rbx; lpCriticalSection
0x18001a0e7  call    cs:__imp_LeaveCriticalSection
0x18001a0ed  jmp     short loc_18001A139
0x18001a0ef  cmp     [rdi+19h], r13b
0x18001a0f3  jz      loc_18001A248
0x18001a0f9  mov     r8, r14; Size
0x18001a0fc  lea     rdx, EventTraceGuid; Buf2
0x18001a103  mov     rcx, r15; Buf1
0x18001a106  call    cs:__imp_memcmp
0x18001a10c  test    eax, eax
0x18001a10e  jnz     short loc_18001A139
0x18001a110  cmp     byte ptr [rbx+2Dh], 8
0x18001a114  jnz     short loc_18001A139
0x18001a116  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001a11d  add     rcx, 38h ; '8'; this
0x18001a121  lea     r8, aSystemTraceRun_1; "System trace rundown has ended"
0x18001a128  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001a12f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001a134  mov     [rdi+18h], r13w
0x18001a139  cmp     [rdi+19h], r13b
0x18001a13d  jmp     short loc_18001A1BB
0x18001a13f  mov     r14d, 10h
0x18001a145  cmp     [rcx+58h], r13b
0x18001a149  jz      short loc_18001A1C6
0x18001a14b  mov     r8d, r14d; Size
0x18001a14e  lea     rdx, stru_1800569D8; Buf2
0x18001a155  mov     rcx, r15; Buf1
0x18001a158  call    cs:__imp_memcmp
0x18001a15e  test    eax, eax
0x18001a160  jnz     short loc_18001A1C6
0x18001a162  mov     r9d, [rbx+0Ch]
0x18001a166  mov     eax, 93h
0x18001a16b  lea     ebp, [r14-0Fh]
0x18001a16f  cmp     [rbx+28h], ax
0x18001a173  jnz     short loc_18001A1A1
0x18001a175  mov     [rdi+59h], bpl
0x18001a179  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001a180  add     rcx, 38h ; '8'; this
0x18001a184  mov     [rsp+78h+var_58], r9d
0x18001a189  mov     r9d, ebp
0x18001a18c  lea     r8, aRundownDForPro; "Rundown '%d' for process %d started"
0x18001a193  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001a19a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001a19f  jmp     short loc_18001A1B7
0x18001a1a1  mov     eax, 91h
0x18001a1a6  cmp     [rbx+28h], ax
0x18001a1aa  jnz     short loc_18001A1B7
0x18001a1ac  lea     r8, [rdi+58h]
0x18001a1b0  mov     edx, ebp
0x18001a1b2  call    ?HandleEndOfRundown@RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXW4RundownProvider@234@AEAURundownInstance@1234@I@Z; Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::HandleEndOfRundown(Microsoft::DiagnosticsHub::StandardCollector::RundownProvider,Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::RundownInstance &,uint)
0x18001a1b7  cmp     [rdi+59h], r13b
0x18001a1bb  jnz     loc_18001A244
0x18001a1c1  jmp     loc_18001A248
0x18001a1c6  lea     rsi, [rdi+98h]
0x18001a1cd  cmp     [rsi], r13b
0x18001a1d0  jz      loc_18001A29D
0x18001a1d6  mov     r8, r14; Size
0x18001a1d9  lea     rdx, qword_1800569C8; Buf2
0x18001a1e0  mov     rcx, r15; Buf1
0x18001a1e3  call    cs:__imp_memcmp
0x18001a1e9  test    eax, eax
0x18001a1eb  jnz     loc_18001A29D
0x18001a1f1  mov     r9d, [rbx+0Ch]
0x18001a1f5  lea     ebp, [rax+1]
0x18001a1f8  cmp     [rbx+28h], bp
0x18001a1fc  jnz     short loc_18001A22B
0x18001a1fe  mov     [rsi+1], bpl
0x18001a202  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001a209  add     rcx, 38h ; '8'; this
0x18001a20d  mov     [rsp+78h+var_58], r9d
0x18001a212  lea     r9d, [rax+2]
0x18001a216  lea     r8, aRundownDForPro; "Rundown '%d' for process %d started"
0x18001a21d  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001a224  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001a229  jmp     short loc_18001A23E
0x18001a22b  mov     edx, 2
0x18001a230  cmp     [rbx+28h], dx
0x18001a234  jnz     short loc_18001A23E
0x18001a236  mov     r8, rsi
0x18001a239  call    ?HandleEndOfRundown@RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXW4RundownProvider@234@AEAURundownInstance@1234@I@Z; Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::HandleEndOfRundown(Microsoft::DiagnosticsHub::StandardCollector::RundownProvider,Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::RundownInstance &,uint)
0x18001a23e  cmp     [rsi+1], r13b
0x18001a242  jz      short loc_18001A248
0x18001a244  mov     [r12], bpl
0x18001a248  lea     rax, [rdi+18h]
0x18001a24c  lea     rcx, [rax+0C0h]
0x18001a253  jmp     short loc_18001A264
0x18001a255  cmp     [rax], r13b
0x18001a258  jnz     short loc_18001A29D
0x18001a25a  cmp     [rax+1], r13b
0x18001a25e  jnz     short loc_18001A29D
0x18001a260  add     rax, 40h ; '@'
0x18001a264  cmp     rax, rcx
0x18001a267  jnz     short loc_18001A255
0x18001a269  lea     r8, aRundownComplet; "Rundown complete"
0x18001a270  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001a277  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x18001a27e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001a283  mov     rcx, [rdi+0D8h]
0x18001a28a  mov     eax, [rcx+8]
0x18001a28d  shr     eax, 1Fh
0x18001a290  test    al, al
0x18001a292  jnz     short loc_18001A29D
0x18001a294  mov     rcx, [rcx]; hEvent
0x18001a297  call    cs:__imp_SetEvent
0x18001a29d  xor     eax, eax
0x18001a29f  mov     rbx, [rsp+78h+arg_10]
0x18001a2a7  add     rsp, 40h
0x18001a2ab  pop     r15
0x18001a2ad  pop     r14
0x18001a2af  pop     r13
0x18001a2b1  pop     r12
0x18001a2b3  pop     rdi
0x18001a2b4  pop     rsi
0x18001a2b5  pop     rbp
0x18001a2b6  retn
```
