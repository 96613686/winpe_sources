# TerminateRecallComponentRelatedProcesses(void)

- ea: `0x18002bc5c`
- end: `0x18002bf48`
- name: `?TerminateRecallComponentRelatedProcesses@@YAXXZ`
- size: `748`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d050`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18002189c`
- `0x1800248a0`
- `0x180025f28`
- `0x180027d0c`
- `0x180027f88`
- `0x180028268`
- `0x18002bc5c`
- `0x18002e708`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd66`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002bd66`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002bd49`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002be2e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002bd49`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002be2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bedc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bedc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bdd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002beb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bdd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002be7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002beb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bef0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf27`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002bd32`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002be17`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002bd32`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002be17`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002bcbd`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18002bcbd`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18002bda1`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x18002bda1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void TerminateRecallComponentRelatedProcesses(void)
{
  _QWORD *v0; // rax
  char *Toolhelp32Snapshot; // rdi
  char *v2; // rbx
  __int64 v3; // rbx
  unsigned __int64 v4; // rsi
  __int64 i; // rcx
  DWORD v6; // r8d
  char *v7; // rbx
  __int64 v8; // rbx
  char *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  void *v11; // rbx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h]
  _QWORD v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  PROCESSENTRY32W pe; // [rsp+50h] [rbp-B0h] BYREF

  pv = 0;
  v0 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v0 + 8LL, v15);
  v13 = 0;
  v14 = 0;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  v15[0] = Toolhelp32Snapshot;
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset_0(&pe.cntUsage, 0, 0x234u);
    pe.dwSize = 568;
    while ( Process32NextW(Toolhelp32Snapshot, &pe) )
    {
      if ( (unsigned int)_o__wcsicmp(pe.szExeFile, L"aihost.exe")
        && (unsigned int)_o__wcsicmp(pe.szExeFile, L"aixhost.exe") )
      {
        if ( !(unsigned int)_o__wcsicmp(pe.szExeFile, L"aicontext.exe") )
        {
          if ( *((_QWORD *)&v13 + 1) == v14 )
          {
            std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(
              &v13,
              *((_QWORD *)&v13 + 1),
              &pe.th32ProcessID);
          }
          else
          {
            **((_DWORD **)&v13 + 1) = pe.th32ProcessID;
            *((_QWORD *)&v13 + 1) += 4LL;
          }
        }
      }
      else if ( pe.th32ProcessID )
      {
        v2 = (char *)OpenProcess(1u, 0, pe.th32ProcessID);
        if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          TerminateProcess(v2, 0);
          CloseHandle(v2);
        }
      }
    }
  }
  v3 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(&pv);
  v15[0] = v3;
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 280));
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 200));
  ++*(_DWORD *)(v3 + 240);
  *(_BYTE *)(v3 + 272) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(v15);
  v4 = 0;
  for ( i = v13; v4 < (*((_QWORD *)&v13 + 1) - i) >> 2; ++v4 )
  {
    v6 = *(_DWORD *)(i + 4 * v4);
    if ( v6 )
    {
      v7 = (char *)OpenProcess(1u, 0, v6);
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        TerminateProcess(v7, 0);
        CloseHandle(v7);
      }
      i = v13;
    }
  }
  v8 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(&pv);
  v15[0] = v8;
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 280));
  EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 200));
  ++*(_DWORD *)(v8 + 240);
  *(_BYTE *)(v8 + 273) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(v15);
  if ( pv )
  {
    v9 = (char *)pv + 8;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    *((_DWORD *)v9 + 16) |= 0x300u;
    if ( *((_QWORD *)v9 + 30) )
      tip2::details::shared_data<0,0,0>::complete_helper(v9, 2);
    if ( v10 )
      LeaveCriticalSection(v10);
  }
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Toolhelp32Snapshot);
  std::vector<unsigned long>::~vector<unsigned long>(&v13);
  v11 = pv;
  if ( pv )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(v11);
      CoTaskMemFree(v11);
    }
  }
}

```

## disassembly

```asm
0x18002bc5c  push    rbp
0x18002bc5e  push    rbx
0x18002bc5f  push    rsi
0x18002bc60  push    rdi
0x18002bc61  lea     rbp, [rsp-1A8h]
0x18002bc69  sub     rsp, 2A8h
0x18002bc70  mov     rax, cs:__security_cookie
0x18002bc77  xor     rax, rsp
0x18002bc7a  mov     [rbp+1C0h+var_30], rax
0x18002bc81  mov     [rsp+2C0h+pv], 0
0x18002bc8a  lea     rcx, [rsp+2C0h+pv]
0x18002bc8f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(void)
0x18002bc94  mov     rcx, [rax]
0x18002bc97  add     rcx, 8
0x18002bc9b  lea     rdx, [rsp+2C0h+var_280]
0x18002bca0  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18002bca5  nop
0x18002bca6  xorps   xmm0, xmm0
0x18002bca9  movdqu  [rsp+2C0h+var_298], xmm0
0x18002bcaf  mov     [rsp+2C0h+var_288], 0
0x18002bcb8  xor     edx, edx; th32ProcessID
0x18002bcba  lea     ecx, [rdx+2]; dwFlags
0x18002bcbd  call    cs:__imp_CreateToolhelp32Snapshot
0x18002bcc3  mov     rdi, rax
0x18002bcc6  mov     [rsp+2C0h+var_280], rax
0x18002bccb  dec     rax
0x18002bcce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bcd2  ja      loc_18002BDAF
0x18002bcd8  xor     edx, edx; Val
0x18002bcda  mov     r8d, 234h; Size
0x18002bce0  lea     rcx, [rsp+2C0h+pe.cntUsage]; void *
0x18002bce5  call    memset_0
0x18002bcea  mov     [rsp+2C0h+pe.dwSize], 238h
0x18002bcf2  jmp     loc_18002BD99
0x18002bcf7  lea     rdx, aAihostExe; "aihost.exe"
0x18002bcfe  lea     rcx, [rsp+2C0h+pe.szExeFile]
0x18002bd03  call    cs:__imp__o__wcsicmp
0x18002bd09  test    eax, eax
0x18002bd0b  jz      short loc_18002BD23
0x18002bd0d  lea     rdx, aAixhostExe; "aixhost.exe"
0x18002bd14  lea     rcx, [rsp+2C0h+pe.szExeFile]
0x18002bd19  call    cs:__imp__o__wcsicmp
0x18002bd1f  test    eax, eax
0x18002bd21  jnz     short loc_18002BD5A
0x18002bd23  mov     r8d, [rsp+2C0h+pe.th32ProcessID]; dwProcessId
0x18002bd28  test    r8d, r8d
0x18002bd2b  jz      short loc_18002BD99
0x18002bd2d  xor     edx, edx; bInheritHandle
0x18002bd2f  lea     ecx, [rdx+1]; dwDesiredAccess
0x18002bd32  call    cs:__imp_OpenProcess
0x18002bd38  mov     rbx, rax
0x18002bd3b  dec     rax
0x18002bd3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bd42  ja      short loc_18002BD99
0x18002bd44  xor     edx, edx; uExitCode
0x18002bd46  mov     rcx, rbx; hProcess
0x18002bd49  call    cs:__imp_TerminateProcess
0x18002bd4f  mov     rcx, rbx; hObject
0x18002bd52  call    cs:__imp_CloseHandle
0x18002bd58  jmp     short loc_18002BD99
0x18002bd5a  lea     rdx, aAicontextExe; "aicontext.exe"
0x18002bd61  lea     rcx, [rsp+2C0h+pe.szExeFile]
0x18002bd66  call    cs:__imp__o__wcsicmp
0x18002bd6c  test    eax, eax
0x18002bd6e  jnz     short loc_18002BD99
0x18002bd70  mov     rdx, qword ptr [rsp+2C0h+var_298+8]
0x18002bd75  cmp     rdx, [rsp+2C0h+var_288]
0x18002bd7a  jz      short loc_18002BD8A
0x18002bd7c  mov     eax, [rsp+2C0h+pe.th32ProcessID]
0x18002bd80  mov     [rdx], eax
0x18002bd82  add     qword ptr [rsp+2C0h+var_298+8], 4
0x18002bd88  jmp     short loc_18002BD99
0x18002bd8a  lea     r8, [rsp+2C0h+pe.th32ProcessID]
0x18002bd8f  lea     rcx, [rsp+2C0h+var_298]
0x18002bd94  call    ??$_Emplace_reallocate@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAKAEBK@Z; std::vector<ulong>::_Emplace_reallocate<ulong const &>(ulong * const,ulong const &)
0x18002bd99  lea     rdx, [rsp+2C0h+pe]; lppe
0x18002bd9e  mov     rcx, rdi; hSnapshot
0x18002bda1  call    cs:__imp_Process32NextW
0x18002bda7  test    eax, eax
0x18002bda9  jnz     loc_18002BCF7
0x18002bdaf  lea     rcx, [rsp+2C0h+pv]
0x18002bdb4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(void)
0x18002bdb9  mov     rbx, [rax]
0x18002bdbc  mov     [rsp+2C0h+var_280], rbx
0x18002bdc1  test    rbx, rbx
0x18002bdc4  jz      short loc_18002BDCD
0x18002bdc6  lock inc dword ptr [rbx+118h]
0x18002bdcd  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002bdd4  call    cs:__imp_EnterCriticalSection
0x18002bdda  inc     dword ptr [rbx+0F0h]
0x18002bde0  mov     byte ptr [rbx+110h], 1
0x18002bde7  lea     rcx, [rsp+2C0h+var_280]
0x18002bdec  call    ??1?$test_data_control@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(void)
0x18002bdf1  xor     esi, esi
0x18002bdf3  mov     rax, qword ptr [rsp+2C0h+var_298+8]
0x18002bdf8  mov     rcx, qword ptr [rsp+2C0h+var_298]
0x18002bdfd  sub     rax, rcx
0x18002be00  sar     rax, 2
0x18002be04  test    rax, rax
0x18002be07  jz      short loc_18002BE56
0x18002be09  mov     r8d, [rcx+rsi*4]; dwProcessId
0x18002be0d  test    r8d, r8d
0x18002be10  jz      short loc_18002BE42
0x18002be12  xor     edx, edx; bInheritHandle
0x18002be14  lea     ecx, [rdx+1]; dwDesiredAccess
0x18002be17  call    cs:__imp_OpenProcess
0x18002be1d  mov     rbx, rax
0x18002be20  dec     rax
0x18002be23  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002be27  ja      short loc_18002BE3D
0x18002be29  xor     edx, edx; uExitCode
0x18002be2b  mov     rcx, rbx; hProcess
0x18002be2e  call    cs:__imp_TerminateProcess
0x18002be34  mov     rcx, rbx; hObject
0x18002be37  call    cs:__imp_CloseHandle
0x18002be3d  mov     rcx, qword ptr [rsp+2C0h+var_298]
0x18002be42  inc     rsi
0x18002be45  mov     rax, qword ptr [rsp+2C0h+var_298+8]
0x18002be4a  sub     rax, rcx
0x18002be4d  sar     rax, 2
0x18002be51  cmp     rsi, rax
0x18002be54  jb      short loc_18002BE09
0x18002be56  lea     rcx, [rsp+2C0h+pv]
0x18002be5b  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::ensure_data(void)
0x18002be60  mov     rbx, [rax]
0x18002be63  mov     [rsp+2C0h+var_280], rbx
0x18002be68  test    rbx, rbx
0x18002be6b  jz      short loc_18002BE74
0x18002be6d  lock inc dword ptr [rbx+118h]
0x18002be74  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002be7b  call    cs:__imp_EnterCriticalSection
0x18002be81  inc     dword ptr [rbx+0F0h]
0x18002be87  mov     byte ptr [rbx+111h], 1
0x18002be8e  lea     rcx, [rsp+2C0h+var_280]
0x18002be93  call    ??1?$test_data_control@V?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>>(void)
0x18002be98  mov     rax, [rsp+2C0h+pv]
0x18002be9d  test    rax, rax
0x18002bea0  jz      short loc_18002BEE3
0x18002bea2  lea     rbx, [rax+8]
0x18002bea6  lea     rsi, [rbx+0C0h]
0x18002bead  mov     rcx, rsi; lpCriticalSection
0x18002beb0  call    cs:__imp_EnterCriticalSection
0x18002beb6  or      dword ptr [rbx+40h], 300h
0x18002bebd  cmp     qword ptr [rbx+0F0h], 0
0x18002bec5  jz      short loc_18002BED4
0x18002bec7  mov     edx, 2
0x18002becc  mov     rcx, rbx
0x18002becf  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18002bed4  test    rsi, rsi
0x18002bed7  jz      short loc_18002BEE3
0x18002bed9  mov     rcx, rsi; lpCriticalSection
0x18002bedc  call    cs:__imp_LeaveCriticalSection
0x18002bee2  nop
0x18002bee3  lea     rax, [rdi-1]
0x18002bee7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002beeb  ja      short loc_18002BEF7
0x18002beed  mov     rcx, rdi; hObject
0x18002bef0  call    cs:__imp_CloseHandle
0x18002bef6  nop
0x18002bef7  lea     rcx, [rsp+2C0h+var_298]
0x18002befc  call    ??1?$vector@KV?$allocator@K@std@@@std@@QEAA@XZ; std::vector<ulong>::~vector<ulong>(void)
0x18002bf01  nop
0x18002bf02  mov     rbx, [rsp+2C0h+pv]
0x18002bf07  test    rbx, rbx
0x18002bf0a  jz      short loc_18002BF2D
0x18002bf0c  or      eax, 0FFFFFFFFh
0x18002bf0f  lock xadd [rbx+118h], eax
0x18002bf17  cmp     eax, 1
0x18002bf1a  jnz     short loc_18002BF2D
0x18002bf1c  mov     rcx, rbx
0x18002bf1f  call    ??1?$merged_data@U_tip_ProcessTerminationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>::~merged_data<_tip_ProcessTerminationTipTest,_tip_ProcessTerminationTipTest>(void)
0x18002bf24  mov     rcx, rbx; pv
0x18002bf27  call    cs:__imp_CoTaskMemFree
0x18002bf2d  mov     rcx, [rbp+1C0h+var_30]
0x18002bf34  xor     rcx, rsp; StackCookie
0x18002bf37  call    __security_check_cookie
0x18002bf3c  add     rsp, 2A8h
0x18002bf43  pop     rdi
0x18002bf44  pop     rsi
0x18002bf45  pop     rbx
0x18002bf46  pop     rbp
0x18002bf47  retn
```
