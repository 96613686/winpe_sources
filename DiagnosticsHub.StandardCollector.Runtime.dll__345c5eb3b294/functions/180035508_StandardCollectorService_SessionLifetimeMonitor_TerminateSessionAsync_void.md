# StandardCollectorService::SessionLifetimeMonitor::TerminateSessionAsync(void)

- ea: `0x180035508`
- end: `0x1800357f9`
- name: `?TerminateSessionAsync@SessionLifetimeMonitor@StandardCollectorService@@QEAAJXZ`
- size: `753`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180034078`

## callees

- `0x180017274`
- `0x180035508`
- `0x1800357fc`
- `0x18003d864`
- `0x18004a078`
- `0x18004ad58`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180035554`
- `KERNEL32!WaitForSingleObject` at `0x1800355f4`
- `KERNEL32!WaitForSingleObject` at `0x180035554`
- `KERNEL32!WaitForSingleObject` at `0x1800355f4`
- `KERNEL32!SetEvent` at `0x1800356d2`
- `KERNEL32!SetEvent` at `0x1800356d2`
- `KERNEL32!UnregisterWaitEx` at `0x1800355a1`
- `KERNEL32!UnregisterWaitEx` at `0x1800355a1`
- `KERNEL32!CreateEventW` at `0x1800356ac`
- `KERNEL32!CreateEventW` at `0x1800356ac`
- `KERNEL32!LeaveCriticalSection` at `0x180035706`
- `KERNEL32!LeaveCriticalSection` at `0x180035727`
- `KERNEL32!LeaveCriticalSection` at `0x180035782`
- `KERNEL32!LeaveCriticalSection` at `0x180035706`
- `KERNEL32!LeaveCriticalSection` at `0x180035727`
- `KERNEL32!LeaveCriticalSection` at `0x180035782`
- `KERNEL32!EnterCriticalSection` at `0x18003553a`
- `KERNEL32!EnterCriticalSection` at `0x180035642`
- `KERNEL32!EnterCriticalSection` at `0x18003553a`
- `KERNEL32!EnterCriticalSection` at `0x180035642`
- `KERNEL32!CloseHandle` at `0x180035696`
- `KERNEL32!CloseHandle` at `0x1800356fd`
- `KERNEL32!CloseHandle` at `0x18003571e`
- `KERNEL32!CloseHandle` at `0x180035696`
- `KERNEL32!CloseHandle` at `0x1800356fd`
- `KERNEL32!CloseHandle` at `0x18003571e`
- `KERNEL32!GetLastError` at `0x1800355af`
- `KERNEL32!GetLastError` at `0x1800356dc`
- `KERNEL32!GetLastError` at `0x1800355af`
- `KERNEL32!GetLastError` at `0x1800356dc`
- `ole32!StringFromGUID2` at `0x18003557f`
- `ole32!StringFromGUID2` at `0x180035621`
- `ole32!StringFromGUID2` at `0x18003574f`
- `ole32!StringFromGUID2` at `0x18003557f`
- `ole32!StringFromGUID2` at `0x180035621`
- `ole32!StringFromGUID2` at `0x18003574f`

## string_xrefs

- `0x1800355cd`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x18003576e`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StandardCollectorService::SessionLifetimeMonitor::TerminateSessionAsync(char *Context)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v3; // esi
  DiagHubCommon::LogStream *v4; // rbx
  const unsigned __int16 *v5; // r8
  BOOL v6; // eax
  DWORD LastError; // eax
  _QWORD *v8; // r15
  _QWORD *v9; // r12
  void *v10; // rcx
  void *v11; // rcx
  signed int v12; // r15d
  signed int v13; // eax
  HANDLE hObject[2]; // [rsp+28h] [rbp-E0h] BYREF
  OLECHAR sz[112]; // [rsp+38h] [rbp-D0h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(Context + 112);
  hObject[1] = Context + 112;
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 112));
  v3 = 0;
  if ( *((int *)Context + 6) < 0 || WaitForSingleObject(*((HANDLE *)Context + 2), 0) )
  {
    v6 = UnregisterWaitEx(*((HANDLE *)Context + 12), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)Context + 12) = 0;
    if ( !v6 )
    {
      LastError = GetLastError();
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Failed to cancel lifetime monitor. (ErrorCode: %#08x)",
        LastError);
      v3 = -2147418113;
      goto LABEL_31;
    }
    if ( *((int *)Context + 6) < 0 || WaitForSingleObject(*((HANDLE *)Context + 2), 0) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(Context + 56));
      v8 = (_QWORD *)*((_QWORD *)Context + 5);
      v9 = (_QWORD *)v8[1];
      while ( !*((_BYTE *)v9 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<unsigned int>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned int,void *>>>(
          Context + 40,
          Context + 40,
          v9[2]);
        v10 = v9;
        v9 = (_QWORD *)*v9;
        operator delete(v10);
      }
      v8[1] = v8;
      *v8 = v8;
      v8[2] = v8;
      *((_QWORD *)Context + 6) = 0;
      v11 = (void *)*((_QWORD *)Context + 13);
      if ( v11 )
      {
        CloseHandle(v11);
        *((_QWORD *)Context + 13) = 0;
      }
      hObject[0] = CreateEventW(0, 1, 0, 0);
      v12 = StandardCollectorService::SessionLifetimeMonitor::MonitorHandle(Context, (struct ATL::CHandle *)hObject);
      if ( v12 >= 0 )
      {
        _mm_lfence();
        if ( SetEvent(*((HANDLE *)Context + 13)) )
        {
          _mm_lfence();
          if ( hObject[0] )
            CloseHandle(hObject[0]);
          LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 56));
          v4 = _logger;
          if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
          {
            _mm_lfence();
            if ( !StringFromGUID2((const GUID *const)Context, sz, 39) )
            {
              LODWORD(hObject[0]) = -2147024882;
              throw (long *)hObject;
            }
            v5 = L"Destroy session for '%s' has been triggered";
            goto LABEL_30;
          }
          goto LABEL_31;
        }
        v13 = GetLastError();
        v12 = (unsigned __int16)v13 | 0x80070000;
        if ( v13 <= 0 )
          v12 = v13;
      }
      if ( hObject[0] )
        CloseHandle(hObject[0]);
      LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 56));
      v3 = v12;
      goto LABEL_31;
    }
    v4 = _logger;
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
    {
      if ( !StringFromGUID2((const GUID *const)Context, sz, 39) )
      {
        LODWORD(hObject[0]) = -2147024882;
        throw (long *)hObject;
      }
      v5 = L"(2) SessionTerminated event for '%s' has been signaled";
      goto LABEL_30;
    }
  }
  else
  {
    v4 = _logger;
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
    {
      if ( !StringFromGUID2((const GUID *const)Context, sz, 39) )
      {
        LODWORD(hObject[0]) = -2147024882;
        throw (long *)hObject;
      }
      v5 = L"(1) SessionTerminated event for '%s' has been signaled";
LABEL_30:
      sz[39] = 0;
      sz[78] = 0;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)v4 + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        v5,
        sz);
    }
  }
LABEL_31:
  LeaveCriticalSection(v2);
  return v3;
}

```

## disassembly

```asm
0x180035508  mov     rax, rsp
0x18003550b  mov     [rax+10h], rbx
0x18003550f  mov     [rax+18h], rsi
0x180035513  mov     [rax+20h], rdi
0x180035517  push    rbp
0x180035518  push    r12
0x18003551a  push    r13
0x18003551c  push    r14
0x18003551e  push    r15
0x180035520  lea     rbp, [rax-38h]
0x180035524  sub     rsp, 110h
0x18003552b  mov     r14, rcx
0x18003552e  lea     rdi, [rcx+70h]
0x180035532  mov     qword ptr [rsp+130h+var_108], rdi
0x180035537  mov     rcx, rdi; lpCriticalSection
0x18003553a  call    cs:__imp_EnterCriticalSection
0x180035540  nop
0x180035541  mov     eax, [r14+18h]
0x180035545  shr     eax, 1Fh
0x180035548  xor     esi, esi
0x18003554a  test    al, al
0x18003554c  jnz     short loc_180035599
0x18003554e  xor     edx, edx; dwMilliseconds
0x180035550  mov     rcx, [r14+10h]; hHandle
0x180035554  call    cs:__imp_WaitForSingleObject
0x18003555a  test    eax, eax
0x18003555c  jnz     short loc_180035599
0x18003555e  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180035565  mov     rax, [rbx+40h]
0x180035569  cmp     [rbx+38h], rax
0x18003556d  jz      loc_18003577F
0x180035573  lea     r8d, [rsi+27h]; cchMax
0x180035577  lea     rdx, [rsp+130h+sz]; lpsz
0x18003557c  mov     rcx, r14; rguid
0x18003557f  call    cs:__imp_StringFromGUID2
0x180035585  test    eax, eax
0x180035587  jz      loc_1800357C5
0x18003558d  lea     r8, a1Sessiontermin; "(1) SessionTerminated event for '%s' ha"...
0x180035594  jmp     loc_180035760
0x180035599  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003559d  mov     rcx, [r14+60h]; WaitHandle
0x1800355a1  call    cs:__imp_UnregisterWaitEx
0x1800355a7  mov     [r14+60h], rsi
0x1800355ab  test    eax, eax
0x1800355ad  jnz     short loc_1800355E3
0x1800355af  call    cs:__imp_GetLastError
0x1800355b5  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800355bc  add     rcx, 0A8h; this
0x1800355c3  mov     r9d, eax
0x1800355c6  lea     r8, aFailedToCancel; "Failed to cancel lifetime monitor. (Err"...
0x1800355cd  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800355d4  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800355d9  mov     esi, 8000FFFFh
0x1800355de  jmp     loc_18003577F
0x1800355e3  mov     eax, [r14+18h]
0x1800355e7  shr     eax, 1Fh
0x1800355ea  test    al, al
0x1800355ec  jnz     short loc_18003563B
0x1800355ee  xor     edx, edx; dwMilliseconds
0x1800355f0  mov     rcx, [r14+10h]; hHandle
0x1800355f4  call    cs:__imp_WaitForSingleObject
0x1800355fa  test    eax, eax
0x1800355fc  jnz     short loc_18003563B
0x1800355fe  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180035605  mov     rax, [rbx+40h]
0x180035609  cmp     [rbx+38h], rax
0x18003560d  jz      loc_18003577F
0x180035613  mov     r8d, 27h ; '''; cchMax
0x180035619  lea     rdx, [rsp+130h+sz]; lpsz
0x18003561e  mov     rcx, r14; rguid
0x180035621  call    cs:__imp_StringFromGUID2
0x180035627  test    eax, eax
0x180035629  jz      loc_1800357DF
0x18003562f  lea     r8, a2Sessiontermin; "(2) SessionTerminated event for '%s' ha"...
0x180035636  jmp     loc_180035760
0x18003563b  lea     rbx, [r14+38h]
0x18003563f  mov     rcx, rbx; lpCriticalSection
0x180035642  call    cs:__imp_EnterCriticalSection
0x180035648  lea     r13, [r14+28h]
0x18003564c  mov     r15, [r13+0]
0x180035650  mov     r12, [r15+8]
0x180035654  jmp     short loc_180035677
0x180035656  mov     r8, [r12+10h]
0x18003565b  mov     rdx, r13
0x18003565e  mov     rcx, r13
0x180035661  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@IPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@IPEAX@std@@@1@PEAU?$_Tree_node@IPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<uint>>::_Erase_tree<std::allocator<std::_Tree_node<uint,void *>>>(std::allocator<std::_Tree_node<uint,void *>> &,std::_Tree_node<uint,void *> *)
0x180035666  mov     rcx, r12; Block
0x180035669  mov     r12, [r12]
0x18003566d  mov     edx, 20h ; ' '
0x180035672  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035677  cmp     [r12+19h], sil
0x18003567c  jz      short loc_180035656
0x18003567e  mov     [r15+8], r15
0x180035682  mov     [r15], r15
0x180035685  mov     [r15+10h], r15
0x180035689  mov     [r13+8], rsi
0x18003568d  mov     rcx, [r14+68h]; hObject
0x180035691  test    rcx, rcx
0x180035694  jz      short loc_1800356A0
0x180035696  call    cs:__imp_CloseHandle
0x18003569c  mov     [r14+68h], rsi
0x1800356a0  xor     r9d, r9d; lpName
0x1800356a3  xor     r8d, r8d; bInitialState
0x1800356a6  lea     edx, [r9+1]; bManualReset
0x1800356aa  xor     ecx, ecx; lpEventAttributes
0x1800356ac  call    cs:__imp_CreateEventW
0x1800356b2  mov     [rsp+130h+hObject], rax
0x1800356b7  lea     rdx, [rsp+130h+hObject]; struct ATL::CHandle *
0x1800356bc  mov     rcx, r14; Context
0x1800356bf  call    ?MonitorHandle@SessionLifetimeMonitor@StandardCollectorService@@AEAAJAEAVCHandle@ATL@@@Z; StandardCollectorService::SessionLifetimeMonitor::MonitorHandle(ATL::CHandle &)
0x1800356c4  mov     r15d, eax
0x1800356c7  test    eax, eax
0x1800356c9  js      short loc_1800356F3
0x1800356cb  lfence
0x1800356ce  mov     rcx, [r14+68h]; hEvent
0x1800356d2  call    cs:__imp_SetEvent
0x1800356d8  test    eax, eax
0x1800356da  jnz     short loc_180035711
0x1800356dc  call    cs:__imp_GetLastError
0x1800356e2  movzx   r15d, ax
0x1800356e6  or      r15d, 80070000h
0x1800356ed  test    eax, eax
0x1800356ef  cmovle  r15d, eax
0x1800356f3  mov     rcx, [rsp+130h+hObject]; hObject
0x1800356f8  test    rcx, rcx
0x1800356fb  jz      short loc_180035703
0x1800356fd  call    cs:__imp_CloseHandle
0x180035703  mov     rcx, rbx; lpCriticalSection
0x180035706  call    cs:__imp_LeaveCriticalSection
0x18003570c  mov     esi, r15d
0x18003570f  jmp     short loc_18003577F
0x180035711  lfence
0x180035714  mov     rcx, [rsp+130h+hObject]; hObject
0x180035719  test    rcx, rcx
0x18003571c  jz      short loc_180035724
0x18003571e  call    cs:__imp_CloseHandle
0x180035724  mov     rcx, rbx; lpCriticalSection
0x180035727  call    cs:__imp_LeaveCriticalSection
0x18003572d  mov     rbx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180035734  mov     rax, [rbx+40h]
0x180035738  cmp     [rbx+38h], rax
0x18003573c  jz      short loc_18003577F
0x18003573e  lfence
0x180035741  mov     r8d, 27h ; '''; cchMax
0x180035747  lea     rdx, [rsp+130h+sz]; lpsz
0x18003574c  mov     rcx, r14; rguid
0x18003574f  call    cs:__imp_StringFromGUID2
0x180035755  test    eax, eax
0x180035757  jz      short loc_1800357AB
0x180035759  lea     r8, aDestroySession_0; "Destroy session for '%s' has been trigg"...
0x180035760  mov     [rsp+130h+var_B2], si
0x180035765  mov     [rbp+30h+var_64], si
0x180035769  lea     r9, [rsp+130h+sz]
0x18003576e  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180035775  lea     rcx, [rbx+38h]; this
0x180035779  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003577e  nop
0x18003577f  mov     rcx, rdi; lpCriticalSection
0x180035782  call    cs:__imp_LeaveCriticalSection
0x180035788  mov     eax, esi
0x18003578a  lea     r11, [rsp+130h+var_20]
0x180035792  mov     rbx, [r11+38h]
0x180035796  mov     rsi, [r11+40h]
0x18003579a  mov     rdi, [r11+48h]
0x18003579e  mov     rsp, r11
0x1800357a1  pop     r15
0x1800357a3  pop     r14
0x1800357a5  pop     r13
0x1800357a7  pop     r12
0x1800357a9  pop     rbp
0x1800357aa  retn
0x1800357ab  mov     dword ptr [rsp+130h+hObject], 8007000Eh
0x1800357b3  lea     rdx, _TI1J; pThrowInfo
0x1800357ba  lea     rcx, [rsp+130h+hObject]; pExceptionObject
0x1800357bf  call    _CxxThrowException_0
0x1800357c5  mov     dword ptr [rsp+130h+hObject], 8007000Eh
0x1800357cd  lea     rdx, _TI1J; pThrowInfo
0x1800357d4  lea     rcx, [rsp+130h+hObject]; pExceptionObject
0x1800357d9  call    _CxxThrowException_0
0x1800357df  mov     dword ptr [rsp+130h+hObject], 8007000Eh
0x1800357e7  lea     rdx, _TI1J; pThrowInfo
0x1800357ee  lea     rcx, [rsp+130h+hObject]; pExceptionObject
0x1800357f3  call    _CxxThrowException_0
```
