# StandardCollectorService::SessionLifetimeMonitor::LifetimeMonitorMain(void *,uchar)

- ea: `0x180034eb0`
- end: `0x1800351f6`
- name: `?LifetimeMonitorMain@SessionLifetimeMonitor@StandardCollectorService@@CAXPEAXE@Z`
- size: `838`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800186a4`
- `0x180034ab0`
- `0x180034eb0`
- `0x1800357fc`
- `0x18003d864`
- `0x180041c24`
- `0x180049b50`
- `0x18004a078`
- `0x18004ad58`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180034fce`
- `KERNEL32!LeaveCriticalSection` at `0x1800350a4`
- `KERNEL32!LeaveCriticalSection` at `0x1800350b7`
- `KERNEL32!LeaveCriticalSection` at `0x180034fce`
- `KERNEL32!LeaveCriticalSection` at `0x1800350a4`
- `KERNEL32!LeaveCriticalSection` at `0x1800350b7`
- `KERNEL32!EnterCriticalSection` at `0x180034f43`
- `KERNEL32!EnterCriticalSection` at `0x180034f43`
- `KERNEL32!CloseHandle` at `0x180034f7d`
- `KERNEL32!CloseHandle` at `0x180034fc0`
- `KERNEL32!CloseHandle` at `0x180035009`
- `KERNEL32!CloseHandle` at `0x180035096`
- `KERNEL32!CloseHandle` at `0x180034f7d`
- `KERNEL32!CloseHandle` at `0x180034fc0`
- `KERNEL32!CloseHandle` at `0x180035009`
- `KERNEL32!CloseHandle` at `0x180035096`
- `ole32!StringFromGUID2` at `0x180034eee`
- `ole32!StringFromGUID2` at `0x180034eee`

## string_xrefs

- `0x180034f28`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180034f21`: `Monitor thread for session '%s' has been triggered`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StandardCollectorService::SessionLifetimeMonitor::LifetimeMonitorMain(char *a1)
{
  __int64 v2; // rdi
  int v3; // eax
  DWORD v4; // r14d
  void *v5; // rax
  void **v6; // r8
  void *v7; // rcx
  int v8; // eax
  _WORD *v9; // rcx
  __int16 v10; // ax
  _WORD *v11; // rax
  __int64 v12; // rdx
  _WORD *v13; // rcx
  __int16 v14; // ax
  _WORD *v15; // rax
  DiagHubCommon::LogStream *v16; // rcx
  _WORD *v17; // rdx
  __int16 v18; // ax
  _WORD *v19; // rax
  int pExceptionObject; // [rsp+30h] [rbp-128h] BYREF
  char *v21; // [rsp+38h] [rbp-120h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-118h] BYREF
  OLECHAR sz[39]; // [rsp+50h] [rbp-108h] BYREF
  _WORD v24[73]; // [rsp+9Eh] [rbp-BAh] BYREF

  v2 = 39;
  v3 = StringFromGUID2((const GUID *const)a1, sz, 39);
  try
  {
    if ( !v3 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v24[0] = 0;
    v24[39] = 0;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Monitor thread for session '%s' has been triggered",
      sz);
    v21 = a1 + 56;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
    while ( *((_QWORD *)a1 + 6) )
    {
      v4 = *(_DWORD *)(**((_QWORD **)a1 + 5) + 28LL);
      v5 = (void *)std::_Tree_val<std::_Tree_simple_types<unsigned int>>::_Extract();
      operator delete(v5);
      v7 = (void *)*((_QWORD *)a1 + 13);
      if ( v7 )
      {
        CloseHandle(v7);
        *((_QWORD *)a1 + 13) = 0;
      }
      hObject[0] = 0;
      Microsoft::DiagnosticsHub::UnifiedPlatform::OpenProcessForQuery(v4, hObject, v6);
      if ( hObject[0] )
      {
        v8 = StandardCollectorService::SessionLifetimeMonitor::MonitorHandle(a1, (struct ATL::CHandle *)hObject);
        if ( v8 == 1 )
        {
          if ( hObject[0] )
          {
            CloseHandle(hObject[0]);
            hObject[0] = 0;
          }
LABEL_11:
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
          return;
        }
        if ( !v8 )
        {
          if ( !v24[0] )
          {
            v9 = v24;
            do
            {
              if ( v2 == 3 )
                break;
              v10 = *(v9 - 38);
              if ( !v10 )
                break;
              *v9++ = v10;
              --v2;
            }
            while ( v2 );
            v11 = v9 - 1;
            if ( v2 )
              v11 = v9;
            *v11 = 0;
            if ( !v2 )
              v24[0] = 0;
          }
          DiagHubCommon::LogStream::Write(
            _logger,
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
            L"Monitoring process %d for session '%s' lifetime.",
            v4,
            v24);
          if ( hObject[0] )
          {
            CloseHandle(hObject[0]);
            hObject[0] = 0;
          }
          goto LABEL_11;
        }
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 112),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
          L"Failed to schedule monitor of process %d for session lifetime.",
          v4);
        if ( hObject[0] )
        {
          CloseHandle(hObject[0]);
          hObject[0] = 0;
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
    if ( !v24[0] )
    {
      v12 = 39;
      v13 = v24;
      do
      {
        if ( v12 == 3 )
          break;
        v14 = *(v13 - 38);
        if ( !v14 )
          break;
        *v13++ = v14;
        --v12;
      }
      while ( v12 );
      v15 = v13 - 1;
      if ( v12 )
        v15 = v13;
      *v15 = 0;
      if ( !v12 )
        v24[0] = 0;
    }
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Session lifetime has been terminated. Session '%s' is being destroyed",
      v24);
    if ( (unsigned int)StandardCollectorService::DestroySessionEx(*((RTL_SRWLOCK **)a1 + 4), (const struct _GUID *)a1) )
    {
      v16 = (DiagHubCommon::LogStream *)((char *)_logger + 168);
      if ( !v24[0] )
      {
        v17 = v24;
        do
        {
          if ( v2 == 3 )
            break;
          v18 = *(v17 - 38);
          if ( !v18 )
            break;
          *v17++ = v18;
          --v2;
        }
        while ( v2 );
        v19 = v17 - 1;
        if ( v2 )
          v19 = v17;
        *v19 = 0;
        if ( !v2 )
          v24[0] = 0;
      }
      DiagHubCommon::LogStream::Write(
        v16,
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Failed to destroy session '%s'",
        v24);
    }
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x180034eb0  mov     [rsp+arg_8], rbx
0x180034eb5  mov     [rsp+arg_10], rsi
0x180034eba  mov     [rsp+arg_18], rdi
0x180034ebf  push    r12
0x180034ec1  push    r14
0x180034ec3  push    r15
0x180034ec5  sub     rsp, 140h
0x180034ecc  mov     rax, cs:__security_cookie
0x180034ed3  xor     rax, rsp
0x180034ed6  mov     [rsp+158h+var_28], rax
0x180034ede  mov     rsi, rcx
0x180034ee1  mov     edi, 27h ; '''
0x180034ee6  mov     r8d, edi; cchMax
0x180034ee9  lea     rdx, [rsp+158h+sz]; lpsz
0x180034eee  call    cs:__imp_StringFromGUID2
0x180034ef4  xor     r15d, r15d
0x180034ef7  test    eax, eax
0x180034ef9  jz      loc_1800351DB
0x180034eff  mov     [rsp+158h+var_BA], r15w
0x180034f08  mov     [rsp+158h+var_6C], r15w
0x180034f11  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180034f18  add     rcx, 38h ; '8'; this
0x180034f1c  lea     r9, [rsp+158h+sz]
0x180034f21  lea     r8, aMonitorThreadF; "Monitor thread for session '%s' has bee"...
0x180034f28  lea     r12, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180034f2f  mov     rdx, r12; unsigned __int16 *
0x180034f32  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180034f37  lea     rbx, [rsi+38h]
0x180034f3b  mov     [rsp+158h+var_120], rbx
0x180034f40  mov     rcx, rbx; lpCriticalSection
0x180034f43  call    cs:__imp_EnterCriticalSection
0x180034f49  nop
0x180034f4a  lea     rcx, [rsi+28h]
0x180034f4e  cmp     [rcx+8], r15
0x180034f52  jz      loc_1800350B4
0x180034f58  mov     rdx, [rcx]
0x180034f5b  mov     rdx, [rdx]
0x180034f5e  mov     r14d, [rdx+1Ch]
0x180034f62  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@QEAAPEAU?$_Tree_node@IPEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<uint>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<uint>>,std::_Iterator_base0>)
0x180034f67  mov     edx, 20h ; ' '
0x180034f6c  mov     rcx, rax; Block
0x180034f6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034f74  mov     rcx, [rsi+68h]; hObject
0x180034f78  test    rcx, rcx
0x180034f7b  jz      short loc_180034F87
0x180034f7d  call    cs:__imp_CloseHandle
0x180034f83  mov     [rsi+68h], r15
0x180034f87  mov     [rsp+158h+hObject], r15
0x180034f8c  lea     rdx, [rsp+158h+hObject]; unsigned int
0x180034f91  mov     ecx, r14d; dwProcessId
0x180034f94  call    ?OpenProcessForQuery@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJKPEAPEAX@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::OpenProcessForQuery(ulong,void * *)
0x180034f99  cmp     [rsp+158h+hObject], r15
0x180034f9e  jz      loc_1800350AF
0x180034fa4  lea     rdx, [rsp+158h+hObject]; struct ATL::CHandle *
0x180034fa9  mov     rcx, rsi; Context
0x180034fac  call    ?MonitorHandle@SessionLifetimeMonitor@StandardCollectorService@@AEAAJAEAVCHandle@ATL@@@Z; StandardCollectorService::SessionLifetimeMonitor::MonitorHandle(ATL::CHandle &)
0x180034fb1  cmp     eax, 1
0x180034fb4  jnz     short loc_180034FD9
0x180034fb6  mov     rcx, [rsp+158h+hObject]; hObject
0x180034fbb  test    rcx, rcx
0x180034fbe  jz      short loc_180034FCB
0x180034fc0  call    cs:__imp_CloseHandle
0x180034fc6  mov     [rsp+158h+hObject], r15
0x180034fcb  mov     rcx, rbx; lpCriticalSection
0x180034fce  call    cs:__imp_LeaveCriticalSection
0x180034fd4  jmp     loc_1800351AD
0x180034fd9  test    eax, eax
0x180034fdb  jz      short loc_180035019
0x180034fdd  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180034fe4  add     rcx, 70h ; 'p'; this
0x180034fe8  mov     r9d, r14d
0x180034feb  lea     r8, aFailedToSchedu; "Failed to schedule monitor of process %"...
0x180034ff2  mov     rdx, r12; unsigned __int16 *
0x180034ff5  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180034ffa  nop
0x180034ffb  mov     rcx, [rsp+158h+hObject]; hObject
0x180035000  test    rcx, rcx
0x180035003  jz      loc_180034F4A
0x180035009  call    cs:__imp_CloseHandle
0x18003500f  mov     [rsp+158h+hObject], r15
0x180035014  jmp     loc_180034F4A
0x180035019  cmp     [rsp+158h+var_BA], r15w
0x180035022  jnz     short loc_180035065
0x180035024  lea     rcx, [rsp+158h+var_BA]
0x18003502c  lea     rax, [rdi-3]
0x180035030  test    rax, rax
0x180035033  jz      short loc_18003504B
0x180035035  movzx   eax, word ptr [rcx-4Ch]
0x180035039  test    ax, ax
0x18003503c  jz      short loc_18003504B
0x18003503e  mov     [rcx], ax
0x180035041  add     rcx, 2
0x180035045  sub     rdi, 1
0x180035049  jnz     short loc_18003502C
0x18003504b  lea     rax, [rcx-2]
0x18003504f  test    rdi, rdi
0x180035052  cmovnz  rax, rcx
0x180035056  mov     [rax], r15w
0x18003505a  jnz     short loc_180035065
0x18003505c  mov     [rsp+158h+var_BA], r15w
0x180035065  lea     rax, [rsp+158h+var_BA]
0x18003506d  mov     [rsp+158h+var_138], rax
0x180035072  mov     r9d, r14d
0x180035075  lea     r8, aMonitoringProc; "Monitoring process %d for session '%s' "...
0x18003507c  mov     rdx, r12; unsigned __int16 *
0x18003507f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x180035086  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003508b  nop
0x18003508c  mov     rcx, [rsp+158h+hObject]; hObject
0x180035091  test    rcx, rcx
0x180035094  jz      short loc_1800350A1
0x180035096  call    cs:__imp_CloseHandle
0x18003509c  mov     [rsp+158h+hObject], r15
0x1800350a1  mov     rcx, rbx; lpCriticalSection
0x1800350a4  call    cs:__imp_LeaveCriticalSection
0x1800350aa  jmp     loc_1800351AD
0x1800350af  jmp     loc_180034F4A
0x1800350b4  mov     rcx, rbx; lpCriticalSection
0x1800350b7  call    cs:__imp_LeaveCriticalSection
0x1800350bd  cmp     [rsp+158h+var_BA], r15w
0x1800350c6  jnz     short loc_18003510C
0x1800350c8  mov     rdx, rdi
0x1800350cb  lea     rcx, [rsp+158h+var_BA]
0x1800350d3  lea     rax, [rdx-3]
0x1800350d7  test    rax, rax
0x1800350da  jz      short loc_1800350F2
0x1800350dc  movzx   eax, word ptr [rcx-4Ch]
0x1800350e0  test    ax, ax
0x1800350e3  jz      short loc_1800350F2
0x1800350e5  mov     [rcx], ax
0x1800350e8  add     rcx, 2
0x1800350ec  sub     rdx, 1
0x1800350f0  jnz     short loc_1800350D3
0x1800350f2  lea     rax, [rcx-2]
0x1800350f6  test    rdx, rdx
0x1800350f9  cmovnz  rax, rcx
0x1800350fd  mov     [rax], r15w
0x180035101  jnz     short loc_18003510C
0x180035103  mov     [rsp+158h+var_BA], r15w
0x18003510c  lea     r9, [rsp+158h+var_BA]
0x180035114  lea     r8, aSessionLifetim_0; "Session lifetime has been terminated. S"...
0x18003511b  mov     rdx, r12; unsigned __int16 *
0x18003511e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x180035125  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003512a  mov     rdx, rsi; struct _GUID *
0x18003512d  mov     rcx, [rsi+20h]; this
0x180035131  call    ?DestroySessionEx@StandardCollectorService@@QEAAJAEBU_GUID@@@Z; StandardCollectorService::DestroySessionEx(_GUID const &)
0x180035136  test    eax, eax
0x180035138  jz      short loc_1800351AB
0x18003513a  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180035141  add     rcx, 0A8h; this
0x180035148  cmp     [rsp+158h+var_BA], r15w
0x180035151  jnz     short loc_180035194
0x180035153  lea     rdx, [rsp+158h+var_BA]
0x18003515b  lea     rax, [rdi-3]
0x18003515f  test    rax, rax
0x180035162  jz      short loc_18003517A
0x180035164  movzx   eax, word ptr [rdx-4Ch]
0x180035168  test    ax, ax
0x18003516b  jz      short loc_18003517A
0x18003516d  mov     [rdx], ax
0x180035170  add     rdx, 2
0x180035174  sub     rdi, 1
0x180035178  jnz     short loc_18003515B
0x18003517a  lea     rax, [rdx-2]
0x18003517e  test    rdi, rdi
0x180035181  cmovnz  rax, rdx
0x180035185  mov     [rax], r15w
0x180035189  jnz     short loc_180035194
0x18003518b  mov     [rsp+158h+var_BA], r15w
0x180035194  lea     r9, [rsp+158h+var_BA]
0x18003519c  lea     r8, aFailedToDestro; "Failed to destroy session '%s'"
0x1800351a3  mov     rdx, r12; unsigned __int16 *
0x1800351a6  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800351ab  jmp     short $+2
0x1800351ad  mov     rcx, [rsp+158h+var_28]
0x1800351b5  xor     rcx, rsp; StackCookie
0x1800351b8  call    __security_check_cookie
0x1800351bd  lea     r11, [rsp+158h+var_18]
0x1800351c5  mov     rbx, [r11+28h]
0x1800351c9  mov     rsi, [r11+30h]
0x1800351cd  mov     rdi, [r11+38h]
0x1800351d1  mov     rsp, r11
0x1800351d4  pop     r15
0x1800351d6  pop     r14
0x1800351d8  pop     r12
0x1800351da  retn
0x1800351db  mov     [rsp+158h+pExceptionObject], 8007000Eh
0x1800351e3  lea     rdx, _TI1J; pThrowInfo
0x1800351ea  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x1800351ef  call    _CxxThrowException_0
```
