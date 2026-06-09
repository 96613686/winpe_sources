# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::Start(ITraceEventCallback *)

- ea: `0x18002824c`
- end: `0x1800284f1`
- name: `?Start@EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAUITraceEventCallback@@@Z`
- size: `677`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *__hidden this, struct ITraceEventCallback *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020338`

## callees

- `0x18000334c`
- `0x1800082ec`
- `0x18002824c`
- `0x180028fc0`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180028289`
- `KERNEL32!WaitForSingleObject` at `0x180028453`
- `KERNEL32!WaitForSingleObject` at `0x180028484`
- `KERNEL32!WaitForSingleObject` at `0x180028289`
- `KERNEL32!WaitForSingleObject` at `0x180028453`
- `KERNEL32!WaitForSingleObject` at `0x180028484`
- `KERNEL32!WaitForMultipleObjects` at `0x180028419`
- `KERNEL32!WaitForMultipleObjects` at `0x180028419`
- `KERNEL32!GetLastError` at `0x18002845e`
- `KERNEL32!GetLastError` at `0x18002845e`
- `ole32!CoUninitialize` at `0x1800284c1`
- `ole32!CoUninitialize` at `0x1800284c1`
- `ole32!CoInitializeEx` at `0x1800282a4`
- `ole32!CoInitializeEx` at `0x1800282a4`
- `ole32!CoCreateInstance` at `0x180028320`
- `ole32!CoCreateInstance` at `0x180028320`

## string_xrefs

- `0x180028340`: `CoCreateInstance() for relogger failed. Error code: 0x%08x`
- `0x1800284a8`: `Relogger thread failed during start-up. HRESULT: %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::Start(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *this,
        struct ITraceEventCallback *a2)
{
  void *v4; // rcx
  char v6; // r15
  int v7; // edi
  __int64 v8; // rcx
  HRESULT Instance; // eax
  unsigned __int64 i; // rdx
  __int64 v11; // rcx
  DWORD v12; // ebx
  void *v13; // rcx
  signed int LastError; // eax
  void *v15; // rcx
  __int64 v16; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-39h]
  _QWORD v18[8]; // [rsp+50h] [rbp-29h] BYREF
  HANDLE *lpHandles[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+27h]

  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 && WaitForSingleObject(v4, 0) )
    return 2147942405LL;
  v6 = 0;
  v7 = CoInitializeEx(0, 0);
  if ( v7 >= 0 )
  {
    v6 = 1;
    if ( !a2 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
        L"Using relogger instance as event callback");
      a2 = this;
    }
    v8 = *((_QWORD *)this + 29);
    if ( v8 )
    {
      *((_QWORD *)this + 29) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    Instance = CoCreateInstance(
                 &CLSID_TraceRelogger,
                 0,
                 1u,
                 &GUID_f754ad43_3bcc_4286_8009_9c5da214e84e,
                 (LPVOID *)this + 29);
    v7 = Instance;
    _mm_lfence();
    if ( Instance >= 0 )
    {
      v18[0] = &std::_Func_impl_no_alloc<_lambda_e69fa4e628820368e55d60beaf7b68fa_,long,DiagHubCommon::AutoEvent const &,void *>::`vftable';
      v18[1] = a2;
      v18[7] = v18;
      v7 = DiagHubCommon::HubTask<long,0>::Start((char *)this + 24);
      if ( v7 >= 0 )
      {
        v17[0] = (char *)this + 240;
        v17[1] = (char *)this + 256;
        *(_OWORD *)lpHandles = 0;
        v20 = 0;
        v16 = -1;
        std::vector<void *>::vector<void *>(lpHandles, 2, &v16);
        for ( i = 0; i < 2; ++i )
        {
          v11 = v17[i];
          if ( !v11 || *(int *)(v11 + 8) < 0 )
          {
            std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(lpHandles);
            goto LABEL_20;
          }
          lpHandles[0][i] = *(HANDLE *)v11;
        }
        v12 = WaitForMultipleObjects(lpHandles[1] - lpHandles[0], lpHandles[0], 0, 0xFFFFFFFF);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(lpHandles);
        if ( !v12 )
          goto LABEL_29;
LABEL_20:
        _mm_lfence();
        v13 = (void *)*((_QWORD *)this + 4);
        if ( !v13 )
          goto LABEL_21;
        if ( WaitForSingleObject(v13, 0xFFFFFFFF) == -1 )
        {
          LastError = GetLastError();
          v7 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v7 = LastError;
          if ( v7 < 0 )
            goto LABEL_29;
        }
        _mm_lfence();
        v15 = (void *)*((_QWORD *)this + 4);
        if ( v15 && WaitForSingleObject(v15, 0) )
        {
LABEL_21:
          v7 = -2147024891;
        }
        else
        {
          _mm_lfence();
          v7 = *((_DWORD *)this + 32);
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 168),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
            L"Relogger thread failed during start-up. HRESULT: %#08x",
            (unsigned int)v7);
        }
      }
    }
    else
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
        L"CoCreateInstance() for relogger failed. Error code: 0x%08x",
        (unsigned int)Instance);
      if ( v7 == -2147221164 )
        v7 = -518979527;
    }
  }
LABEL_29:
  if ( v6 )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002824c  mov     [rsp-8+arg_8], rbx
0x180028251  mov     [rsp-8+arg_10], rsi
0x180028256  push    rbp
0x180028257  push    rdi
0x180028258  push    r13
0x18002825a  push    r14
0x18002825c  push    r15
0x18002825e  lea     rbp, [rsp-37h]
0x180028263  sub     rsp, 0B0h
0x18002826a  mov     rax, cs:__security_cookie
0x180028271  xor     rax, rsp
0x180028274  mov     [rbp+57h+var_28], rax
0x180028278  mov     r14, rdx
0x18002827b  mov     rsi, rcx
0x18002827e  mov     rcx, [rcx+20h]; hHandle
0x180028282  test    rcx, rcx
0x180028285  jz      short loc_18002829D
0x180028287  xor     edx, edx; dwMilliseconds
0x180028289  call    cs:__imp_WaitForSingleObject
0x18002828f  test    eax, eax
0x180028291  jz      short loc_18002829D
0x180028293  mov     eax, 80070005h
0x180028298  jmp     loc_1800284C9
0x18002829d  xor     r15b, r15b
0x1800282a0  xor     edx, edx; dwCoInit
0x1800282a2  xor     ecx, ecx; pvReserved
0x1800282a4  call    cs:__imp_CoInitializeEx
0x1800282aa  mov     edi, eax
0x1800282ac  test    eax, eax
0x1800282ae  js      loc_1800284BC
0x1800282b4  mov     r15d, 1
0x1800282ba  mov     [rbp+57h+var_A0], r15b
0x1800282be  test    r14, r14
0x1800282c1  jnz     short loc_1800282E4
0x1800282c3  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800282ca  add     rcx, 38h ; '8'; this
0x1800282ce  lea     r8, aUsingReloggerI; "Using relogger instance as event callba"...
0x1800282d5  lea     rdx, aDAWork1SSource; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800282dc  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800282e1  mov     r14, rsi
0x1800282e4  lea     rbx, [rsi+0E8h]
0x1800282eb  mov     rcx, [rbx]
0x1800282ee  test    rcx, rcx
0x1800282f1  jz      short loc_180028308
0x1800282f3  mov     qword ptr [rbx], 0
0x1800282fa  mov     rax, [rcx]
0x1800282fd  mov     rax, [rax+10h]
0x180028301  call    cs:__guard_dispatch_icall_fptr
0x180028307  nop
0x180028308  mov     [rsp+0D0h+ppv], rbx; ppv
0x18002830d  lea     r9, _GUID_f754ad43_3bcc_4286_8009_9c5da214e84e; riid
0x180028314  mov     r8d, r15d; dwClsContext
0x180028317  xor     edx, edx; pUnkOuter
0x180028319  lea     rcx, CLSID_TraceRelogger; rclsid
0x180028320  call    cs:__imp_CoCreateInstance
0x180028326  mov     edi, eax
0x180028328  lfence
0x18002832b  test    eax, eax
0x18002832d  jns     short loc_180028369
0x18002832f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180028336  add     rcx, 0A8h; this
0x18002833d  mov     r9d, eax
0x180028340  lea     r8, aCocreateinstan; "CoCreateInstance() for relogger failed."...
0x180028347  lea     rdx, aDAWork1SSource; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18002834e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180028353  cmp     edi, 80040154h
0x180028359  jnz     loc_1800284BC
0x18002835f  mov     edi, 0E1110039h
0x180028364  jmp     loc_1800284BC
0x180028369  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e69fa4e628820368e55d60beaf7b68fa_@@JAEBVAutoEvent@DiagHubCommon@@PEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e69fa4e628820368e55d60beaf7b68fa_,long,DiagHubCommon::AutoEvent const &,void *>::`vftable'
0x180028370  mov     [rbp+57h+var_80], rax
0x180028374  mov     [rbp+57h+var_78], r14
0x180028378  lea     rax, [rbp+57h+var_80]
0x18002837c  mov     [rbp+57h+var_48], rax
0x180028380  mov     r8, rsi
0x180028383  lea     rdx, [rbp+57h+var_80]
0x180028387  lea     rcx, [rsi+18h]; lpParameter
0x18002838b  call    ?Start@?$HubTask@J$0A@@DiagHubCommon@@QEAAJV?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@PEAX@Z; DiagHubCommon::HubTask<long,0>::Start(std::function<long (DiagHubCommon::AutoEvent const &,void *)>,void *)
0x180028390  mov     edi, eax
0x180028392  test    eax, eax
0x180028394  js      loc_1800284BC
0x18002839a  lea     rax, [rsi+0F0h]
0x1800283a1  mov     [rbp+57h+var_90], rax
0x1800283a5  lea     rax, [rsi+100h]
0x1800283ac  mov     [rbp+57h+var_88], rax
0x1800283b0  xorps   xmm0, xmm0
0x1800283b3  xor     eax, eax
0x1800283b5  movups  xmmword ptr [rbp+57h+lpHandles], xmm0
0x1800283b9  mov     [rbp+57h+var_30], rax
0x1800283bd  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x1800283c5  lea     r8, [rbp+57h+var_98]
0x1800283c9  lea     edx, [rax+2]
0x1800283cc  lea     rcx, [rbp+57h+lpHandles]
0x1800283d0  call    ??$?0V?$allocator@PEAX@std@@$0A@@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@_KAEBQEAXAEBV?$allocator@PEAX@1@@Z; std::vector<void *>::vector<void *>(unsigned __int64,void * const &,std::allocator<void *> const &)
0x1800283d5  xor     edx, edx
0x1800283d7  mov     rcx, [rbp+rdx+57h+var_90]
0x1800283dc  or      r14d, 0FFFFFFFFh
0x1800283e0  test    rcx, rcx
0x1800283e3  jz      short loc_180028434
0x1800283e5  mov     eax, [rcx+8]
0x1800283e8  shr     eax, 1Fh
0x1800283eb  test    al, al
0x1800283ed  jnz     short loc_180028434
0x1800283ef  mov     rcx, [rcx]
0x1800283f2  mov     rax, [rbp+57h+lpHandles]
0x1800283f6  mov     [rdx+rax], rcx
0x1800283fa  add     rdx, 8
0x1800283fe  cmp     rdx, 10h
0x180028402  jb      short loc_1800283D7
0x180028404  mov     rdx, [rbp+57h+lpHandles]; lpHandles
0x180028408  mov     rcx, [rbp+57h+lpHandles+8]
0x18002840c  sub     rcx, rdx
0x18002840f  sar     rcx, 3; nCount
0x180028413  mov     r9d, r14d; dwMilliseconds
0x180028416  xor     r8d, r8d; bWaitAll
0x180028419  call    cs:__imp_WaitForMultipleObjects
0x18002841f  mov     ebx, eax
0x180028421  lea     rcx, [rbp+57h+lpHandles]
0x180028425  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x18002842a  test    ebx, ebx
0x18002842c  jz      loc_1800284BC
0x180028432  jmp     short loc_18002843D
0x180028434  lea     rcx, [rbp+57h+lpHandles]
0x180028438  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x18002843d  lfence
0x180028440  mov     rcx, [rsi+20h]; hHandle
0x180028444  test    rcx, rcx
0x180028447  jnz     short loc_180028450
0x180028449  mov     edi, 80070005h
0x18002844e  jmp     short loc_1800284BC
0x180028450  mov     edx, r14d; dwMilliseconds
0x180028453  call    cs:__imp_WaitForSingleObject
0x180028459  cmp     eax, r14d
0x18002845c  jnz     short loc_180028476
0x18002845e  call    cs:__imp_GetLastError
0x180028464  movzx   edi, ax
0x180028467  or      edi, 80070000h
0x18002846d  test    eax, eax
0x18002846f  cmovle  edi, eax
0x180028472  test    edi, edi
0x180028474  js      short loc_1800284BC
0x180028476  lfence
0x180028479  mov     rcx, [rsi+20h]; hHandle
0x18002847d  test    rcx, rcx
0x180028480  jz      short loc_18002848E
0x180028482  xor     edx, edx; dwMilliseconds
0x180028484  call    cs:__imp_WaitForSingleObject
0x18002848a  test    eax, eax
0x18002848c  jnz     short loc_180028449
0x18002848e  lfence
0x180028491  mov     edi, [rsi+80h]
0x180028497  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002849e  add     rcx, 0A8h; this
0x1800284a5  mov     r9d, edi
0x1800284a8  lea     r8, aReloggerThread; "Relogger thread failed during start-up."...
0x1800284af  lea     rdx, aDAWork1SSource; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800284b6  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800284bb  nop
0x1800284bc  test    r15b, r15b
0x1800284bf  jz      short loc_1800284C7
0x1800284c1  call    cs:__imp_CoUninitialize
0x1800284c7  mov     eax, edi
0x1800284c9  mov     rcx, [rbp+57h+var_28]
0x1800284cd  xor     rcx, rsp; StackCookie
0x1800284d0  call    __security_check_cookie
0x1800284d5  lea     r11, [rsp+0D0h+var_20]
0x1800284dd  mov     rbx, [r11+38h]
0x1800284e1  mov     rsi, [r11+40h]
0x1800284e5  mov     rsp, r11
0x1800284e8  pop     r15
0x1800284ea  pop     r14
0x1800284ec  pop     r13
0x1800284ee  pop     rdi
0x1800284ef  pop     rbp
0x1800284f0  retn
```
