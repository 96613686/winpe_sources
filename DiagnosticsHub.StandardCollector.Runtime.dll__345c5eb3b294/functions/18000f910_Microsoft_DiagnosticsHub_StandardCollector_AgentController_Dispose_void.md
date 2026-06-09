# Microsoft::DiagnosticsHub::StandardCollector::AgentController::Dispose(void)

- ea: `0x18000f910`
- end: `0x18000fc68`
- name: `?Dispose@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAXXZ`
- size: `856`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::AgentController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d180`

## callees

- `0x18000f910`
- `0x1800105c4`
- `0x18003d864`
- `0x18004b640`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fa84`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fa84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fa3b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fa3b`
- `KERNEL32!LeaveCriticalSection` at `0x18000f98e`
- `KERNEL32!LeaveCriticalSection` at `0x18000f9b0`
- `KERNEL32!LeaveCriticalSection` at `0x18000f9d2`
- `KERNEL32!LeaveCriticalSection` at `0x18000fa2b`
- `KERNEL32!LeaveCriticalSection` at `0x18000fadd`
- `KERNEL32!LeaveCriticalSection` at `0x18000fb36`
- `KERNEL32!LeaveCriticalSection` at `0x18000fb8f`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc27`
- `KERNEL32!LeaveCriticalSection` at `0x18000f98e`
- `KERNEL32!LeaveCriticalSection` at `0x18000f9b0`
- `KERNEL32!LeaveCriticalSection` at `0x18000f9d2`
- `KERNEL32!LeaveCriticalSection` at `0x18000fa2b`
- `KERNEL32!LeaveCriticalSection` at `0x18000fadd`
- `KERNEL32!LeaveCriticalSection` at `0x18000fb36`
- `KERNEL32!LeaveCriticalSection` at `0x18000fb8f`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc27`
- `KERNEL32!EnterCriticalSection` at `0x18000f944`
- `KERNEL32!EnterCriticalSection` at `0x18000f99e`
- `KERNEL32!EnterCriticalSection` at `0x18000f9c0`
- `KERNEL32!EnterCriticalSection` at `0x18000f9e2`
- `KERNEL32!EnterCriticalSection` at `0x18000fa94`
- `KERNEL32!EnterCriticalSection` at `0x18000faed`
- `KERNEL32!EnterCriticalSection` at `0x18000fb46`
- `KERNEL32!EnterCriticalSection` at `0x18000fba1`
- `KERNEL32!EnterCriticalSection` at `0x18000f944`
- `KERNEL32!EnterCriticalSection` at `0x18000f99e`
- `KERNEL32!EnterCriticalSection` at `0x18000f9c0`
- `KERNEL32!EnterCriticalSection` at `0x18000f9e2`
- `KERNEL32!EnterCriticalSection` at `0x18000fa94`
- `KERNEL32!EnterCriticalSection` at `0x18000faed`
- `KERNEL32!EnterCriticalSection` at `0x18000fb46`
- `KERNEL32!EnterCriticalSection` at `0x18000fba1`

## string_xrefs

- `0x18000fbdb`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000fbd4`: `Agent shutdown failed. HRESULT: %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentController::Dispose(
        Microsoft::DiagnosticsHub::StandardCollector::AgentController *this)
{
  _QWORD *v2; // rbp
  _QWORD *v3; // rsi
  _QWORD *v4; // rbp
  _QWORD *v5; // rsi
  _QWORD *v6; // rsi
  _QWORD *v7; // rbx
  _QWORD *v8; // rbp
  _QWORD *v9; // rsi
  _QWORD *v10; // rbp
  _QWORD *v11; // rsi
  _QWORD *v12; // rbp
  _QWORD *v13; // rsi
  _QWORD *v14; // rbp
  _QWORD *i; // rsi
  unsigned int v16; // eax
  _QWORD *v17; // rbp
  _QWORD *v18; // rsi
  __int64 v19; // rcx
  char *v20; // [rsp+20h] [rbp-18h]

  if ( !*((_BYTE *)this + 689) )
  {
    *((_BYTE *)this + 689) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    v2 = (_QWORD *)*((_QWORD *)this + 20);
    v3 = (_QWORD *)*((_QWORD *)this + 19);
    if ( v3 != v2 )
    {
      do
      {
        if ( *v3 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
        v3 += 2;
      }
      while ( v3 != v2 );
      *((_QWORD *)this + 20) = *((_QWORD *)this + 19);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::clear((char *)this + 216);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
    EnterCriticalSection((LPCRITICAL_SECTION)this + 7);
    std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::clear((char *)this + 320);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 7);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
    v4 = (_QWORD *)*((_QWORD *)this + 54);
    v5 = (_QWORD *)*((_QWORD *)this + 53);
    if ( v5 != v4 )
    {
      do
      {
        if ( *v5 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
        v5 += 2;
      }
      while ( v5 != v4 );
      *((_QWORD *)this + 54) = *((_QWORD *)this + 53);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
    AcquireSRWLockExclusive((PSRWLOCK)this + 64);
    v6 = (_QWORD *)*((_QWORD *)this + 66);
    v7 = (_QWORD *)*((_QWORD *)this + 65);
    if ( v7 != v6 )
    {
      do
      {
        if ( *v7 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
        v7 += 2;
      }
      while ( v7 != v6 );
      *((_QWORD *)this + 66) = *((_QWORD *)this + 65);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
    v8 = (_QWORD *)*((_QWORD *)this + 62);
    v9 = (_QWORD *)*((_QWORD *)this + 61);
    if ( v9 != v8 )
    {
      do
      {
        if ( *v9 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
        v9 += 2;
      }
      while ( v9 != v8 );
      *((_QWORD *)this + 62) = *((_QWORD *)this + 61);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
    v10 = (_QWORD *)*((_QWORD *)this + 74);
    v11 = (_QWORD *)*((_QWORD *)this + 73);
    if ( v11 != v10 )
    {
      do
      {
        if ( *v11 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
        v11 += 2;
      }
      while ( v11 != v10 );
      *((_QWORD *)this + 74) = *((_QWORD *)this + 73);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
    v12 = (_QWORD *)*((_QWORD *)this + 82);
    v13 = (_QWORD *)*((_QWORD *)this + 81);
    if ( v13 != v12 )
    {
      do
      {
        if ( *v13 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
        v13 += 2;
      }
      while ( v13 != v12 );
      *((_QWORD *)this + 82) = *((_QWORD *)this + 81);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
    v20 = (char *)this + 48;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v14 = (_QWORD *)*((_QWORD *)this + 12);
    for ( i = (_QWORD *)*((_QWORD *)this + 11); i != v14; i += 2 )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 32LL))(*i);
      if ( v16 )
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
          L"Agent shutdown failed. HRESULT: %#08x",
          v16,
          v20);
    }
    v17 = (_QWORD *)*((_QWORD *)this + 12);
    v18 = (_QWORD *)*((_QWORD *)this + 11);
    if ( v18 != v17 )
    {
      do
      {
        if ( *v18 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 16LL))(*v18);
        v18 += 2;
      }
      while ( v18 != v17 );
      *((_QWORD *)this + 12) = *((_QWORD *)this + 11);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v19 = *((_QWORD *)this + 85);
    if ( v19 )
    {
      *((_QWORD *)this + 85) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
}

```

## disassembly

```asm
0x18000f910  mov     [rsp+arg_8], rbx
0x18000f915  mov     [rsp+arg_10], rbp
0x18000f91a  mov     [rsp+arg_18], rsi
0x18000f91f  push    rdi
0x18000f920  sub     rsp, 30h
0x18000f924  mov     rdi, rcx
0x18000f927  mov     al, [rcx+2B1h]
0x18000f92d  test    al, al
0x18000f92f  jnz     loc_18000FC53
0x18000f935  mov     eax, 1
0x18000f93a  xchg    al, [rcx+2B1h]
0x18000f940  add     rcx, 70h ; 'p'; lpCriticalSection
0x18000f944  call    cs:__imp_EnterCriticalSection
0x18000f94a  mov     rbp, [rdi+0A0h]
0x18000f951  mov     rsi, [rdi+98h]
0x18000f958  cmp     rsi, rbp
0x18000f95b  jz      short loc_18000F98A
0x18000f95d  mov     rcx, [rsi]
0x18000f960  test    rcx, rcx
0x18000f963  jz      short loc_18000F973
0x18000f965  mov     rax, [rcx]
0x18000f968  mov     rax, [rax+10h]
0x18000f96c  call    cs:__guard_dispatch_icall_fptr
0x18000f972  nop
0x18000f973  add     rsi, 10h
0x18000f977  cmp     rsi, rbp
0x18000f97a  jnz     short loc_18000F95D
0x18000f97c  mov     rax, [rdi+98h]
0x18000f983  mov     [rdi+0A0h], rax
0x18000f98a  lea     rcx, [rdi+70h]; lpCriticalSection
0x18000f98e  call    cs:__imp_LeaveCriticalSection
0x18000f994  lea     rbx, [rdi+0B0h]
0x18000f99b  mov     rcx, rbx; lpCriticalSection
0x18000f99e  call    cs:__imp_EnterCriticalSection
0x18000f9a4  lea     rcx, [rbx+28h]
0x18000f9a8  call    ?clear@?$_Hash@V?$_Umap_traits@U_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@8@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::clear(void)
0x18000f9ad  mov     rcx, rbx; lpCriticalSection
0x18000f9b0  call    cs:__imp_LeaveCriticalSection
0x18000f9b6  lea     rbx, [rdi+118h]
0x18000f9bd  mov     rcx, rbx; lpCriticalSection
0x18000f9c0  call    cs:__imp_EnterCriticalSection
0x18000f9c6  lea     rcx, [rbx+28h]
0x18000f9ca  call    ?clear@?$_Hash@V?$_Umap_traits@U_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@8@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<_GUID,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>,0>>::clear(void)
0x18000f9cf  mov     rcx, rbx; lpCriticalSection
0x18000f9d2  call    cs:__imp_LeaveCriticalSection
0x18000f9d8  lea     rbx, [rdi+180h]
0x18000f9df  mov     rcx, rbx; lpCriticalSection
0x18000f9e2  call    cs:__imp_EnterCriticalSection
0x18000f9e8  mov     rbp, [rdi+1B0h]
0x18000f9ef  mov     rsi, [rdi+1A8h]
0x18000f9f6  cmp     rsi, rbp
0x18000f9f9  jz      short loc_18000FA28
0x18000f9fb  mov     rcx, [rsi]
0x18000f9fe  test    rcx, rcx
0x18000fa01  jz      short loc_18000FA11
0x18000fa03  mov     rax, [rcx]
0x18000fa06  mov     rax, [rax+10h]
0x18000fa0a  call    cs:__guard_dispatch_icall_fptr
0x18000fa10  nop
0x18000fa11  add     rsi, 10h
0x18000fa15  cmp     rsi, rbp
0x18000fa18  jnz     short loc_18000F9FB
0x18000fa1a  mov     rax, [rdi+1A8h]
0x18000fa21  mov     [rdi+1B0h], rax
0x18000fa28  mov     rcx, rbx; lpCriticalSection
0x18000fa2b  call    cs:__imp_LeaveCriticalSection
0x18000fa31  lea     rbp, [rdi+200h]
0x18000fa38  mov     rcx, rbp; SRWLock
0x18000fa3b  call    cs:__imp_AcquireSRWLockExclusive
0x18000fa41  mov     rsi, [rdi+210h]
0x18000fa48  mov     rbx, [rdi+208h]
0x18000fa4f  cmp     rbx, rsi
0x18000fa52  jz      short loc_18000FA81
0x18000fa54  mov     rcx, [rbx]
0x18000fa57  test    rcx, rcx
0x18000fa5a  jz      short loc_18000FA6A
0x18000fa5c  mov     rax, [rcx]
0x18000fa5f  mov     rax, [rax+10h]
0x18000fa63  call    cs:__guard_dispatch_icall_fptr
0x18000fa69  nop
0x18000fa6a  add     rbx, 10h
0x18000fa6e  cmp     rbx, rsi
0x18000fa71  jnz     short loc_18000FA54
0x18000fa73  mov     rax, [rdi+208h]
0x18000fa7a  mov     [rdi+210h], rax
0x18000fa81  mov     rcx, rbp; SRWLock
0x18000fa84  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fa8a  lea     rbx, [rdi+1C0h]
0x18000fa91  mov     rcx, rbx; lpCriticalSection
0x18000fa94  call    cs:__imp_EnterCriticalSection
0x18000fa9a  mov     rbp, [rdi+1F0h]
0x18000faa1  mov     rsi, [rdi+1E8h]
0x18000faa8  cmp     rsi, rbp
0x18000faab  jz      short loc_18000FADA
0x18000faad  mov     rcx, [rsi]
0x18000fab0  test    rcx, rcx
0x18000fab3  jz      short loc_18000FAC3
0x18000fab5  mov     rax, [rcx]
0x18000fab8  mov     rax, [rax+10h]
0x18000fabc  call    cs:__guard_dispatch_icall_fptr
0x18000fac2  nop
0x18000fac3  add     rsi, 10h
0x18000fac7  cmp     rsi, rbp
0x18000faca  jnz     short loc_18000FAAD
0x18000facc  mov     rax, [rdi+1E8h]
0x18000fad3  mov     [rdi+1F0h], rax
0x18000fada  mov     rcx, rbx; lpCriticalSection
0x18000fadd  call    cs:__imp_LeaveCriticalSection
0x18000fae3  lea     rbx, [rdi+220h]
0x18000faea  mov     rcx, rbx; lpCriticalSection
0x18000faed  call    cs:__imp_EnterCriticalSection
0x18000faf3  mov     rbp, [rdi+250h]
0x18000fafa  mov     rsi, [rdi+248h]
0x18000fb01  cmp     rsi, rbp
0x18000fb04  jz      short loc_18000FB33
0x18000fb06  mov     rcx, [rsi]
0x18000fb09  test    rcx, rcx
0x18000fb0c  jz      short loc_18000FB1C
0x18000fb0e  mov     rax, [rcx]
0x18000fb11  mov     rax, [rax+10h]
0x18000fb15  call    cs:__guard_dispatch_icall_fptr
0x18000fb1b  nop
0x18000fb1c  add     rsi, 10h
0x18000fb20  cmp     rsi, rbp
0x18000fb23  jnz     short loc_18000FB06
0x18000fb25  mov     rax, [rdi+248h]
0x18000fb2c  mov     [rdi+250h], rax
0x18000fb33  mov     rcx, rbx; lpCriticalSection
0x18000fb36  call    cs:__imp_LeaveCriticalSection
0x18000fb3c  lea     rbx, [rdi+260h]
0x18000fb43  mov     rcx, rbx; lpCriticalSection
0x18000fb46  call    cs:__imp_EnterCriticalSection
0x18000fb4c  mov     rbp, [rdi+290h]
0x18000fb53  mov     rsi, [rdi+288h]
0x18000fb5a  cmp     rsi, rbp
0x18000fb5d  jz      short loc_18000FB8C
0x18000fb5f  mov     rcx, [rsi]
0x18000fb62  test    rcx, rcx
0x18000fb65  jz      short loc_18000FB75
0x18000fb67  mov     rax, [rcx]
0x18000fb6a  mov     rax, [rax+10h]
0x18000fb6e  call    cs:__guard_dispatch_icall_fptr
0x18000fb74  nop
0x18000fb75  add     rsi, 10h
0x18000fb79  cmp     rsi, rbp
0x18000fb7c  jnz     short loc_18000FB5F
0x18000fb7e  mov     rax, [rdi+288h]
0x18000fb85  mov     [rdi+290h], rax
0x18000fb8c  mov     rcx, rbx; lpCriticalSection
0x18000fb8f  call    cs:__imp_LeaveCriticalSection
0x18000fb95  lea     rbx, [rdi+30h]
0x18000fb99  mov     [rsp+38h+var_18], rbx
0x18000fb9e  mov     rcx, rbx; lpCriticalSection
0x18000fba1  call    cs:__imp_EnterCriticalSection
0x18000fba7  nop
0x18000fba8  mov     rbp, [rdi+60h]
0x18000fbac  mov     rsi, [rdi+58h]
0x18000fbb0  jmp     short loc_18000FBEB
0x18000fbb2  mov     rcx, [rsi]
0x18000fbb5  mov     rax, [rcx]
0x18000fbb8  mov     rax, [rax+20h]
0x18000fbbc  call    cs:__guard_dispatch_icall_fptr
0x18000fbc2  test    eax, eax
0x18000fbc4  jz      short loc_18000FBE7
0x18000fbc6  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000fbcd  add     rcx, 38h ; '8'; this
0x18000fbd1  mov     r9d, eax
0x18000fbd4  lea     r8, aAgentShutdownF; "Agent shutdown failed. HRESULT: %#08x"
0x18000fbdb  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000fbe2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000fbe7  add     rsi, 10h
0x18000fbeb  cmp     rsi, rbp
0x18000fbee  jnz     short loc_18000FBB2
0x18000fbf0  mov     rbp, [rdi+60h]
0x18000fbf4  mov     rsi, [rdi+58h]
0x18000fbf8  cmp     rsi, rbp
0x18000fbfb  jz      short loc_18000FC24
0x18000fbfd  mov     rcx, [rsi]
0x18000fc00  test    rcx, rcx
0x18000fc03  jz      short loc_18000FC13
0x18000fc05  mov     rax, [rcx]
0x18000fc08  mov     rax, [rax+10h]
0x18000fc0c  call    cs:__guard_dispatch_icall_fptr
0x18000fc12  nop
0x18000fc13  add     rsi, 10h
0x18000fc17  cmp     rsi, rbp
0x18000fc1a  jnz     short loc_18000FBFD
0x18000fc1c  mov     rax, [rdi+58h]
0x18000fc20  mov     [rdi+60h], rax
0x18000fc24  mov     rcx, rbx; lpCriticalSection
0x18000fc27  call    cs:__imp_LeaveCriticalSection
0x18000fc2d  nop
0x18000fc2e  mov     rcx, [rdi+2A8h]
0x18000fc35  test    rcx, rcx
0x18000fc38  jz      short loc_18000FC53
0x18000fc3a  mov     qword ptr [rdi+2A8h], 0
0x18000fc45  mov     rax, [rcx]
0x18000fc48  mov     rax, [rax+10h]
0x18000fc4c  call    cs:__guard_dispatch_icall_fptr
0x18000fc52  nop
0x18000fc53  mov     rbx, [rsp+38h+arg_8]
0x18000fc58  mov     rbp, [rsp+38h+arg_10]
0x18000fc5d  mov     rsi, [rsp+38h+arg_18]
0x18000fc62  add     rsp, 30h
0x18000fc66  pop     rdi
0x18000fc67  retn
```
