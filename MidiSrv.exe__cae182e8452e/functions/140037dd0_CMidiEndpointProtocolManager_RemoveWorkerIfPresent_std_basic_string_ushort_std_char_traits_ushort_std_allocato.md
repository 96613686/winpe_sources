# CMidiEndpointProtocolManager::RemoveWorkerIfPresent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140037dd0`
- end: `0x14003815f`
- name: `?RemoveWorkerIfPresent@CMidiEndpointProtocolManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `911`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140037b20`
- `0x140038168`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000c598`
- `0x140013a38`
- `0x14001dccc`
- `0x14001f95c`
- `0x1400360c8`
- `0x140037070`
- `0x140037dd0`
- `0x14003846c`
- `0x14005a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x140037f9e`
- `msvcp_win!_Mtx_unlock` at `0x140037f9e`
- `msvcp_win!_Thrd_join` at `0x14003802d`
- `msvcp_win!_Thrd_join` at `0x14003802d`
- `msvcp_win!_Thrd_id` at `0x140038008`
- `msvcp_win!_Thrd_id` at `0x140038008`
- `msvcp_win!_Mtx_lock` at `0x140037e95`
- `msvcp_win!_Mtx_lock` at `0x140037e95`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140037ea4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140037ec2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140038017`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14003803c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140037ea4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140037ec2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140038017`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14003803c`

## string_xrefs

- `0x140038069`: `avcore\midi2\service\exe\midiendpointprotocolmanager.cpp`
- `0x14003813c`: `Worker removed`
- `0x140037e0f`: `CMidiEndpointProtocolManager::RemoveWorkerIfPresent`
- `0x140037f2e`: `CMidiEndpointProtocolManager::RemoveWorkerIfPresent`
- `0x140038147`: `CMidiEndpointProtocolManager::RemoveWorkerIfPresent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidiEndpointProtocolManager::RemoveWorkerIfPresent(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  const wchar_t *v10; // rdx
  size_t v11; // rbx
  size_t v12; // r14
  const wchar_t *v13; // rcx
  size_t v14; // r8
  int v15; // eax
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t **v19; // rax
  __int16 *v20; // rdx
  _Thrd_t *v22; // r14
  _Thrd_id_t Id; // ebx
  int v24; // eax
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rbx
  wchar_t **v27; // rax
  int v28[2]; // [rsp+40h] [rbp-49h] BYREF
  const char *v29; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-39h] BYREF
  _Thrd_t v31; // [rsp+60h] [rbp-29h] BYREF
  __int64 v32; // [rsp+70h] [rbp-19h]
  __int64 v33; // [rsp+80h] [rbp-9h]
  wchar_t *S1[2]; // [rsp+88h] [rbp-1h] BYREF
  size_t N; // [rsp+98h] [rbp+Fh]
  unsigned __int64 v36; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v33 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v7 = (char *)a2;
    else
      v7 = *(char **)a2;
    v29 = v7;
    v30[0] = L"Exit success";
    v31._Hnd = (void *)a1;
    *(_QWORD *)v28 = "CMidiEndpointProtocolManager::RemoveWorkerIfPresent";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_14008A879,
      v5,
      v6,
      v28,
      (__int64)&v31,
      v30,
      &v29);
  }
  v8 = std::wstring::wstring((__int64)&v31, a2);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v8);
  *(_QWORD *)v28 = a1 + 88;
  if ( _Mtx_lock((_Mtx_t)(a1 + 88)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(a1 + 164) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 164) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(
    a1 + 168,
    &v31,
    S1);
  v9 = v32;
  if ( *(_BYTE *)(v32 + 25) )
    goto LABEL_19;
  v10 = (const wchar_t *)(v32 + 32);
  v11 = *(_QWORD *)(v32 + 48);
  if ( *(_QWORD *)(v32 + 56) > 7u )
    v10 = *(const wchar_t **)v10;
  v12 = N;
  v13 = (const wchar_t *)S1;
  if ( v36 > 7 )
    v13 = S1[0];
  v14 = *(_QWORD *)(v32 + 48);
  if ( v11 >= N )
    v14 = N;
  v15 = wmemcmp(v13, v10, v14);
  if ( v15 )
  {
    if ( v15 < 0 )
      goto LABEL_19;
  }
  else if ( v12 < v11 )
  {
    goto LABEL_19;
  }
  if ( v9 == *(_QWORD *)(a1 + 168) )
  {
LABEL_19:
    v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v16 > 3u )
    {
      v19 = S1;
      if ( v36 > 7 )
        v19 = (wchar_t **)S1[0];
      *(_QWORD *)v28 = v19;
      v31._Hnd = L"No matching worker present";
      v29 = "CMidiEndpointProtocolManager::RemoveWorkerIfPresent";
      v20 = (__int16 *)qword_14008A710;
LABEL_23:
      v30[0] = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v16,
        (__int64)v20,
        v17,
        v18,
        &v29,
        (__int64)v30,
        &v31,
        v28);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  CMidiEndpointProtocolWorker::EndProcessing(*(CMidiEndpointProtocolWorker **)(v9 + 80));
  v22 = *(_Thrd_t **)(v9 + 64);
  if ( v22->_Id )
  {
    Id = v22->_Id;
    if ( Id == _Thrd_id() )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    v31 = *v22;
    if ( _Thrd_join(&v31, 0) )
    {
      std::_Throw_Cpp_error(2);
      __debugbreak();
    }
    *v22 = 0;
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 80) + 56LL))(*(_QWORD *)(v9 + 80));
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x118,
      (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolmanager.cpp",
      (const char *)(unsigned int)v24);
  *(_QWORD *)(v9 + 80) = 0;
  v25 = *(volatile signed __int32 **)(v9 + 88);
  *(_QWORD *)(v9 + 88) = 0;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  *(_QWORD *)(v9 + 64) = 0;
  v26 = *(volatile signed __int32 **)(v9 + 72);
  *(_QWORD *)(v9 + 72) = 0;
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,ProtocolNegotiationWorkerThreadEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>>,0>>::erase(
    a1 + 168,
    S1);
  v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v16 > 4u )
  {
    v27 = S1;
    if ( v36 > 7 )
      v27 = (wchar_t **)S1[0];
    *(_QWORD *)v28 = v27;
    v31._Hnd = L"Worker removed";
    v29 = "CMidiEndpointProtocolManager::RemoveWorkerIfPresent";
    v20 = &word_14008A766;
    goto LABEL_23;
  }
LABEL_24:
  _Mtx_unlock((_Mtx_t)(a1 + 88));
  std::wstring::~wstring((char **)S1);
  std::wstring::~wstring((char **)a2);
  return 0;
}

```

## disassembly

```asm
0x140037dd0  mov     [rsp-8+arg_10], rbx
0x140037dd5  push    rbp
0x140037dd6  push    rsi
0x140037dd7  push    rdi
0x140037dd8  push    r12
0x140037dda  push    r13
0x140037ddc  push    r14
0x140037dde  push    r15
0x140037de0  lea     rbp, [rsp-27h]
0x140037de5  sub     rsp, 0B0h
0x140037dec  mov     rax, cs:__security_cookie
0x140037df3  xor     rax, rsp
0x140037df6  mov     [rbp+57h+var_38], rax
0x140037dfa  mov     rsi, rdx
0x140037dfd  mov     r13, rcx
0x140037e00  mov     [rbp+57h+var_60], rdx
0x140037e04  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140037e09  mov     rcx, [rax+8]
0x140037e0d  mov     eax, [rcx]
0x140037e0f  lea     rbx, aCmidiendpointp_12; "CMidiEndpointProtocolManager::RemoveWor"...
0x140037e16  cmp     eax, 4
0x140037e19  jbe     short loc_140037E71
0x140037e1b  cmp     qword ptr [rsi+18h], 7
0x140037e20  jbe     short loc_140037E27
0x140037e22  mov     rax, [rsi]
0x140037e25  jmp     short loc_140037E2A
0x140037e27  mov     rax, rsi
0x140037e2a  mov     [rbp+57h+var_98], rax
0x140037e2e  lea     rax, aExitSuccess_0; "Exit success"
0x140037e35  mov     [rbp+57h+var_90], rax
0x140037e39  mov     [rbp+57h+var_80._Hnd], r13
0x140037e3d  mov     qword ptr [rbp+57h+var_A0], rbx
0x140037e41  lea     rax, [rbp+57h+var_98]
0x140037e45  mov     [rsp+0E0h+var_A8], rax
0x140037e4a  lea     rax, [rbp+57h+var_90]
0x140037e4e  mov     [rsp+0E0h+var_B0], rax
0x140037e53  lea     rax, [rbp+57h+var_80]
0x140037e57  mov     [rsp+0E0h+var_B8], rax
0x140037e5c  lea     rax, [rbp+57h+var_A0]
0x140037e60  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x140037e65  lea     rdx, byte_14008A879
0x140037e6c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140037e71  mov     rdx, rsi
0x140037e74  lea     rcx, [rbp+57h+var_80]
0x140037e78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140037e7d  mov     rdx, rax
0x140037e80  lea     rcx, [rbp+57h+S1]
0x140037e84  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140037e89  nop
0x140037e8a  lea     r15, [r13+58h]
0x140037e8e  mov     qword ptr [rbp+57h+var_A0], r15
0x140037e92  mov     rcx, r15; _Mtx_t
0x140037e95  call    cs:__imp__Mtx_lock
0x140037e9b  test    eax, eax
0x140037e9d  jz      short loc_140037EAB
0x140037e9f  mov     ecx, 5
0x140037ea4  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140037eaa  int     3; Trap to Debugger
0x140037eab  cmp     dword ptr [r15+4Ch], 7FFFFFFFh
0x140037eb3  jnz     short loc_140037EC9
0x140037eb5  mov     dword ptr [r15+4Ch], 7FFFFFFEh
0x140037ebd  mov     ecx, 6
0x140037ec2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140037ec8  nop
0x140037ec9  lea     r12, [r13+0A8h]
0x140037ed0  lea     r8, [rbp+57h+S1]
0x140037ed4  lea     rdx, [rbp+57h+var_80]
0x140037ed8  mov     rcx, r12
0x140037edb  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140037ee0  mov     rdi, [rbp+57h+var_70]
0x140037ee4  cmp     byte ptr [rdi+19h], 0
0x140037ee8  jnz     short loc_140037F35
0x140037eea  lea     rdx, [rdi+20h]
0x140037eee  mov     rbx, [rdx+10h]
0x140037ef2  cmp     qword ptr [rdx+18h], 7
0x140037ef7  jbe     short loc_140037EFC
0x140037ef9  mov     rdx, [rdx]; S2
0x140037efc  mov     r14, [rbp+57h+N]
0x140037f00  lea     rcx, [rbp+57h+S1]
0x140037f04  cmp     [rbp+57h+var_40], 7
0x140037f09  cmova   rcx, [rbp+57h+S1]; S1
0x140037f0e  mov     r8, rbx
0x140037f11  cmp     rbx, r14
0x140037f14  cmovnb  r8, r14; N
0x140037f18  call    wmemcmp
0x140037f1d  test    eax, eax
0x140037f1f  jnz     loc_140037FE0
0x140037f25  cmp     r14, rbx
0x140037f28  jnb     loc_140037FE6
0x140037f2e  lea     rbx, aCmidiendpointp_12; "CMidiEndpointProtocolManager::RemoveWor"...
0x140037f35  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140037f3a  mov     rcx, [rax+8]
0x140037f3e  mov     eax, [rcx]
0x140037f40  cmp     eax, 3
0x140037f43  jbe     short loc_140037F9B
0x140037f45  lea     rax, [rbp+57h+S1]
0x140037f49  cmp     [rbp+57h+var_40], 7
0x140037f4e  cmova   rax, [rbp+57h+S1]
0x140037f53  mov     qword ptr [rbp+57h+var_A0], rax
0x140037f57  lea     rax, aNoMatchingWork; "No matching worker present"
0x140037f5e  mov     [rbp+57h+var_80._Hnd], rax
0x140037f62  mov     [rbp+57h+var_98], rbx
0x140037f66  lea     rdx, qword_14008A710
0x140037f6d  lea     rax, [rbp+57h+var_A0]
0x140037f71  mov     [rsp+0E0h+var_A8], rax
0x140037f76  lea     rax, [rbp+57h+var_80]
0x140037f7a  mov     [rsp+0E0h+var_B0], rax
0x140037f7f  lea     rax, [rbp+57h+var_90]
0x140037f83  mov     [rsp+0E0h+var_B8], rax
0x140037f88  lea     rax, [rbp+57h+var_98]
0x140037f8c  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140037f91  mov     [rbp+57h+var_90], r13
0x140037f95  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140037f9a  nop
0x140037f9b  mov     rcx, r15; _Mtx_t
0x140037f9e  call    cs:__imp__Mtx_unlock
0x140037fa4  nop
0x140037fa5  lea     rcx, [rbp+57h+S1]; void *
0x140037fa9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140037fae  nop
0x140037faf  mov     rcx, rsi; void *
0x140037fb2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140037fb7  xor     eax, eax
0x140037fb9  mov     rcx, [rbp+57h+var_38]
0x140037fbd  xor     rcx, rsp; StackCookie
0x140037fc0  call    __security_check_cookie
0x140037fc5  mov     rbx, [rsp+0E0h+arg_10]
0x140037fcd  add     rsp, 0B0h
0x140037fd4  pop     r15
0x140037fd6  pop     r14
0x140037fd8  pop     r13
0x140037fda  pop     r12
0x140037fdc  pop     rdi
0x140037fdd  pop     rsi
0x140037fde  pop     rbp
0x140037fdf  retn
0x140037fe0  js      loc_140037F2E
0x140037fe6  cmp     rdi, [r12]
0x140037fea  jz      loc_140037F2E
0x140037ff0  mov     rcx, [rdi+50h]; this
0x140037ff4  call    ?EndProcessing@CMidiEndpointProtocolWorker@@QEAAXXZ; CMidiEndpointProtocolWorker::EndProcessing(void)
0x140037ff9  mov     r14, [rdi+40h]
0x140037ffd  cmp     dword ptr [r14+8], 0
0x140038002  jz      short loc_14003804B
0x140038004  mov     ebx, [r14+8]
0x140038008  call    cs:__imp__Thrd_id
0x14003800e  cmp     ebx, eax
0x140038010  jnz     short loc_14003801E
0x140038012  mov     ecx, 5
0x140038017  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14003801d  int     3; Trap to Debugger
0x14003801e  movups  xmm0, xmmword ptr [r14]
0x140038022  movdqu  xmmword ptr [rbp+57h+var_80._Hnd], xmm0
0x140038027  xor     edx, edx; int *
0x140038029  lea     rcx, [rbp+57h+var_80]; _Thrd_t
0x14003802d  call    cs:__imp__Thrd_join
0x140038033  test    eax, eax
0x140038035  jz      short loc_140038043
0x140038037  mov     ecx, 2
0x14003803c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140038042  int     3; Trap to Debugger
0x140038043  xorps   xmm0, xmm0
0x140038046  movdqu  xmmword ptr [r14], xmm0
0x14003804b  mov     rcx, [rdi+50h]
0x14003804f  mov     rax, [rcx]
0x140038052  mov     rax, [rax+38h]
0x140038056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003805b  mov     rcx, [rbp+5Fh]; this
0x14003805f  xor     r14d, r14d
0x140038062  test    eax, eax
0x140038064  jns     short loc_14003807A
0x140038066  mov     r9d, eax; char *
0x140038069  lea     r8, aAvcoreMidi2Ser_12; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140038070  mov     edx, 118h; void *
0x140038075  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003807a  mov     [rdi+50h], r14
0x14003807e  mov     rbx, [rdi+58h]
0x140038082  mov     [rdi+58h], r14
0x140038086  test    rbx, rbx
0x140038089  jz      short loc_1400380C2
0x14003808b  or      eax, 0FFFFFFFFh
0x14003808e  lock xadd [rbx+8], eax
0x140038093  cmp     eax, 1
0x140038096  jnz     short loc_1400380C2
0x140038098  mov     rax, [rbx]
0x14003809b  mov     rcx, rbx
0x14003809e  mov     rax, [rax]
0x1400380a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400380a6  or      eax, 0FFFFFFFFh
0x1400380a9  lock xadd [rbx+0Ch], eax
0x1400380ae  cmp     eax, 1
0x1400380b1  jnz     short loc_1400380C2
0x1400380b3  mov     rax, [rbx]
0x1400380b6  mov     rcx, rbx
0x1400380b9  mov     rax, [rax+8]
0x1400380bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400380c2  mov     [rdi+40h], r14
0x1400380c6  mov     rbx, [rdi+48h]
0x1400380ca  mov     [rdi+48h], r14
0x1400380ce  test    rbx, rbx
0x1400380d1  jz      short loc_14003810A
0x1400380d3  or      eax, 0FFFFFFFFh
0x1400380d6  lock xadd [rbx+8], eax
0x1400380db  cmp     eax, 1
0x1400380de  jnz     short loc_14003810A
0x1400380e0  mov     rax, [rbx]
0x1400380e3  mov     rcx, rbx
0x1400380e6  mov     rax, [rax]
0x1400380e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400380ee  or      eax, 0FFFFFFFFh
0x1400380f1  lock xadd [rbx+0Ch], eax
0x1400380f6  cmp     eax, 1
0x1400380f9  jnz     short loc_14003810A
0x1400380fb  mov     rax, [rbx]
0x1400380fe  mov     rcx, rbx
0x140038101  mov     rax, [rax+8]
0x140038105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003810a  lea     rdx, [rbp+57h+S1]
0x14003810e  mov     rcx, r12
0x140038111  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ProtocolNegotiationWorkerThreadEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>>,0>>::erase(std::wstring const &)
0x140038116  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003811b  mov     rcx, [rax+8]
0x14003811f  mov     eax, [rcx]
0x140038121  cmp     eax, 4
0x140038124  jbe     loc_140037F9B
0x14003812a  lea     rax, [rbp+57h+S1]
0x14003812e  cmp     [rbp+57h+var_40], 7
0x140038133  cmova   rax, [rbp+57h+S1]
0x140038138  mov     qword ptr [rbp+57h+var_A0], rax
0x14003813c  lea     rax, aWorkerRemoved; "Worker removed"
0x140038143  mov     [rbp+57h+var_80._Hnd], rax
0x140038147  lea     rax, aCmidiendpointp_12; "CMidiEndpointProtocolManager::RemoveWor"...
0x14003814e  mov     [rbp+57h+var_98], rax
0x140038152  lea     rdx, word_14008A766
0x140038159  jmp     loc_140037F6D
```
