# CMidiEndpointProtocolManager::DiscoverAndNegotiate(_GUID,ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001)

- ea: `0x140036a90`
- end: `0x14003706a`
- name: `?DiscoverAndNegotiate@CMidiEndpointProtocolManager@@UEAAJU_GUID@@PEBGU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@Z`
- size: `1498`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001ce8`
- `0x140001f28`
- `0x1400054c0`
- `0x1400054e4`
- `0x1400060f8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000e154`
- `0x140013a38`
- `0x14001dccc`
- `0x14001f95c`
- `0x140035e6c`
- `0x1400360c8`
- `0x1400363d0`
- `0x140036868`
- `0x140036a90`
- `0x14005a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x140036dd4`
- `msvcp_win!_Mtx_unlock` at `0x140037051`
- `msvcp_win!_Mtx_unlock` at `0x140036dd4`
- `msvcp_win!_Mtx_unlock` at `0x140037051`
- `msvcp_win!_Thrd_detach` at `0x140036f85`
- `msvcp_win!_Thrd_detach` at `0x140036f85`
- `msvcp_win!_Mtx_lock` at `0x140036b7e`
- `msvcp_win!_Mtx_lock` at `0x140036b7e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140036b8d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140036baa`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140037063`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140036b8d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140036baa`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140037063`

## string_xrefs

- `0x140036cdf`: `avcore\midi2\service\exe\midiendpointprotocolmanager.cpp`
- `0x140036d78`: `avcore\midi2\service\exe\midiendpointprotocolmanager.cpp`
- `0x140036ad3`: `CMidiEndpointProtocolManager::DiscoverAndNegotiate`
- `0x140036fc5`: `CMidiEndpointProtocolManager::DiscoverAndNegotiate`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolManager::DiscoverAndNegotiate(__int64 a1, __int64 a2, _WORD *a3, void *a4)
{
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rsi
  const wchar_t *v13; // rdx
  size_t v14; // rbx
  const wchar_t *v15; // rcx
  size_t v16; // rdi
  size_t v17; // r8
  int v18; // eax
  char v19; // al
  __int64 v20; // rax
  __int64 v21; // rcx
  volatile signed __int32 *v22; // r15
  volatile signed __int32 *v23; // rbx
  unsigned int v24; // edi
  bool v25; // zf
  wchar_t **v26; // r9
  __int128 v27; // xmm1
  __int64 (__fastcall *v28)(volatile signed __int32 *, int *, __int128 *, wchar_t **); // rax
  int v29; // eax
  _DWORD *v30; // rax
  void *Hnd; // r9
  _DWORD *v32; // r14
  volatile signed __int32 *v33; // rdi
  _QWORD *v34; // rsi
  volatile signed __int32 *v35; // rdi
  volatile signed __int32 *v36; // rdi
  __int64 v37; // rax
  _Thrd_t *v38; // rdi
  _DWORD *v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+60h] [rbp-A0h]
  _Thrd_t v45; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v46; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+8Ch] [rbp-74h]
  int v48[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h]
  _WORD *v50; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v54; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *S1[2]; // [rsp+E8h] [rbp-18h] BYREF
  size_t v56; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v57; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v45._Hnd = a4;
  v46 = a3;
  *(_QWORD *)&v43 = a2;
  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v44 = *(unsigned __int8 *)(a1 + 16);
    v51 = L"Enter";
    *(_QWORD *)v48 = "CMidiEndpointProtocolManager::DiscoverAndNegotiate";
    v50 = a3;
    v52 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v6,
      (__int64)&byte_14008A8CF,
      v7,
      v8,
      v48,
      (__int64)&v52,
      &v51,
      &v50);
  }
  if ( !*(_BYTE *)(a1 + 16) )
    return 2147500036LL;
  if ( _Mtx_lock((_Mtx_t)(a1 + 88)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(a1 + 164) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 164) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v54 = 0u;
  v53 = 0;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v53, a3, v10);
  v11 = std::wstring::wstring((__int64)v48, (__int64)&v53);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v11);
  std::wstring::~wstring((char **)&v53);
  std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(
    a1 + 168,
    v48,
    S1);
  v12 = v49;
  if ( *(_BYTE *)(v49 + 25) )
    goto LABEL_29;
  v13 = (const wchar_t *)(v49 + 32);
  v14 = *(_QWORD *)(v49 + 48);
  if ( *(_QWORD *)(v49 + 56) > 7u )
    v13 = *(const wchar_t **)v13;
  v15 = (const wchar_t *)S1;
  v16 = v56;
  if ( v57 > 7 )
    v15 = S1[0];
  v17 = v56;
  if ( v14 < v56 )
    v17 = *(_QWORD *)(v49 + 48);
  v18 = wmemcmp(v15, v13, v17);
  if ( v18 )
  {
    if ( v18 >= 0 )
    {
LABEL_21:
      v19 = 1;
      goto LABEL_22;
    }
  }
  else if ( v16 >= v14 )
  {
    if ( v16 <= v14 )
      goto LABEL_23;
    goto LABEL_21;
  }
  v19 = -1;
LABEL_22:
  if ( v19 < 0 )
  {
LABEL_29:
    v23 = (volatile signed __int32 *)operator new(0x158u);
    *((_DWORD *)v23 + 2) = 1;
    *((_DWORD *)v23 + 3) = 1;
    v22 = v23 + 4;
    *(_QWORD *)v23 = &std::_Ref_count_obj2<CMidiEndpointProtocolWorker>::`vftable';
    memset_0((void *)(v23 + 4), 0, 0x148u);
    CMidiEndpointProtocolWorker::CMidiEndpointProtocolWorker((CMidiEndpointProtocolWorker *)(v23 + 4));
    goto LABEL_30;
  }
LABEL_23:
  if ( v12 == *(_QWORD *)(a1 + 168) )
    goto LABEL_29;
  v20 = std::map<std::wstring,ProtocolNegotiationWorkerThreadEntry>::operator[](
          (__int64 *)(a1 + 168),
          (const wchar_t *)S1);
  v21 = *(_QWORD *)(v20 + 24);
  if ( v21 )
    _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
  v22 = *(volatile signed __int32 **)(v20 + 16);
  v23 = *(volatile signed __int32 **)(v20 + 24);
LABEL_30:
  if ( !v22 )
  {
    v24 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolmanager.cpp",
      (const char *)0x80004003LL,
      v42);
    if ( v23 )
    {
      v25 = _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1;
      goto LABEL_38;
    }
    goto LABEL_41;
  }
  v26 = S1;
  v27 = *(_OWORD *)(a1 + 20);
  if ( v57 > 7 )
    v26 = (wchar_t **)S1[0];
  v28 = *(__int64 (__fastcall **)(volatile signed __int32 *, int *, __int128 *, wchar_t **))(*(_QWORD *)v22 + 40LL);
  v43 = *(_OWORD *)v43;
  *(_OWORD *)v48 = v27;
  v29 = v28(v22, v48, &v43, v26);
  v24 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolmanager.cpp",
      (const char *)(unsigned int)v29,
      a1 + 40);
    if ( v23 )
    {
      v25 = _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1;
LABEL_38:
      if ( v25 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
LABEL_41:
    std::wstring::~wstring((char **)S1);
    _Mtx_unlock((_Mtx_t)(a1 + 88));
    return v24;
  }
  v53 = 0;
  v54 = 0;
  if ( v23 )
    _InterlockedIncrement(v23 + 2);
  *(_QWORD *)&v54 = v22;
  *(_QWORD *)&v43 =  CMidiEndpointProtocolWorker::`vcall'{48,{flat}};
  HIDWORD(v43) = v47;
  *((_QWORD *)&v54 + 1) = v23;
  DWORD2(v43) = 0;
  v30 = operator new(0x20u);
  Hnd = v45._Hnd;
  v32 = v30;
  v30[2] = 1;
  v30[3] = 1;
  *(_QWORD *)v30 = &std::_Ref_count_obj2<std::thread>::`vftable';
  ____0P8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EAEAV__shared_ptr_VCMidiEndpointProtocolWorker___std__AEAU1__0A__thread_std__QEAA___QEAP8CMidiEndpointProtocolWorker__EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001____EAEAV__shared_ptr_VCMidiEndpointProtocolWorker___1_AEAU3__Z(
    (__int64)(v30 + 4),
    &v43,
    &v54,
    (__int64)Hnd);
  *(_QWORD *)&v53 = v32 + 4;
  v33 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
  *((_QWORD *)&v53 + 1) = v32;
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  v34 = (_QWORD *)std::map<std::wstring,ProtocolNegotiationWorkerThreadEntry>::operator[](
                    (__int64 *)(a1 + 168),
                    (const wchar_t *)S1);
  _InterlockedIncrement(v32 + 2);
  v35 = (volatile signed __int32 *)v34[1];
  v34[1] = v32;
  *v34 = v32 + 4;
  if ( v35 )
  {
    if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
      if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    }
  }
  if ( v23 )
    _InterlockedIncrement(v23 + 2);
  v36 = (volatile signed __int32 *)v34[3];
  v34[2] = v22;
  v34[3] = v23;
  if ( v36 )
  {
    if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  v37 = std::map<std::wstring,ProtocolNegotiationWorkerThreadEntry>::operator[](
          (__int64 *)(a1 + 168),
          (const wchar_t *)S1);
  v38 = *(_Thrd_t **)v37;
  if ( !*(_DWORD *)(*(_QWORD *)v37 + 8LL) || (v45 = *v38, _Thrd_detach(&v45)) )
  {
    std::_Throw_Cpp_error(1);
    JUMPOUT(0x140037069LL);
  }
  *v38 = 0;
  v39 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v39 > 4u )
  {
    v45._Hnd = L"Exit success";
    *(_QWORD *)v48 = "CMidiEndpointProtocolManager::DiscoverAndNegotiate";
    *(_QWORD *)&v43 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v39,
      (__int64)&dword_14008A7BC,
      v40,
      v41,
      v48,
      (__int64)&v43,
      &v45,
      &v46);
  }
  ProtocolNegotiationWorkerThreadEntry::~ProtocolNegotiationWorkerThreadEntry((ProtocolNegotiationWorkerThreadEntry *)&v53);
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  std::wstring::~wstring((char **)S1);
  _Mtx_unlock((_Mtx_t)(a1 + 88));
  return 0;
}

```

## disassembly

```asm
0x140036a90  mov     [rsp-8+arg_18], rbx
0x140036a95  push    rbp
0x140036a96  push    rsi
0x140036a97  push    rdi
0x140036a98  push    r12
0x140036a9a  push    r13
0x140036a9c  push    r14
0x140036a9e  push    r15
0x140036aa0  lea     rbp, [rsp-10h]
0x140036aa5  sub     rsp, 110h
0x140036aac  mov     rax, cs:__security_cookie
0x140036ab3  xor     rax, rsp
0x140036ab6  mov     [rbp+40h+var_38], rax
0x140036aba  mov     [rsp+140h+var_D0._Hnd], r9
0x140036abf  mov     rdi, r8
0x140036ac2  mov     [rbp+40h+var_C0], r8
0x140036ac6  mov     r12, rcx
0x140036ac9  mov     qword ptr [rsp+140h+var_F0], rdx
0x140036ace  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140036ad3  lea     rdx, aCmidiendpointp_0; "CMidiEndpointProtocolManager::DiscoverA"...
0x140036ada  mov     rcx, [rax+8]
0x140036ade  mov     eax, [rcx]
0x140036ae0  cmp     eax, 4
0x140036ae3  jbe     short loc_140036B40
0x140036ae5  movzx   eax, byte ptr [r12+10h]
0x140036aeb  mov     [rsp+140h+var_E0], eax
0x140036aef  lea     rax, aEnter; "Enter"
0x140036af6  mov     [rbp+40h+var_88], rax
0x140036afa  lea     rax, [rsp+140h+var_E0]
0x140036aff  mov     [rsp+140h+var_100], rax
0x140036b04  lea     rax, [rbp+40h+var_90]
0x140036b08  mov     [rsp+140h+var_108], rax
0x140036b0d  lea     rax, [rbp+40h+var_88]
0x140036b11  mov     [rsp+140h+var_110], rax
0x140036b16  lea     rax, [rbp+40h+var_80]
0x140036b1a  mov     [rsp+140h+var_118], rax
0x140036b1f  lea     rax, [rbp+40h+var_B0]
0x140036b23  mov     qword ptr [rbp+40h+var_B0], rdx
0x140036b27  lea     rdx, byte_14008A8CF
0x140036b2e  mov     qword ptr [rsp+140h+var_120], rax; int
0x140036b33  mov     [rbp+40h+var_90], rdi
0x140036b37  mov     [rbp+40h+var_80], r12
0x140036b3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140036b40  xor     r15d, r15d
0x140036b43  cmp     [r12+10h], r15b
0x140036b48  jnz     short loc_140036B76
0x140036b4a  mov     eax, 80004004h
0x140036b4f  mov     rcx, [rbp+40h+var_38]
0x140036b53  xor     rcx, rsp; StackCookie
0x140036b56  call    __security_check_cookie
0x140036b5b  mov     rbx, [rsp+140h+arg_18]
0x140036b63  add     rsp, 110h
0x140036b6a  pop     r15
0x140036b6c  pop     r14
0x140036b6e  pop     r13
0x140036b70  pop     r12
0x140036b72  pop     rdi
0x140036b73  pop     rsi
0x140036b74  pop     rbp
0x140036b75  retn
0x140036b76  lea     r13, [r12+58h]
0x140036b7b  mov     rcx, r13; _Mtx_t
0x140036b7e  call    cs:__imp__Mtx_lock
0x140036b84  test    eax, eax
0x140036b86  jz      short loc_140036B94
0x140036b88  mov     ecx, 5
0x140036b8d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140036b93  int     3; Trap to Debugger
0x140036b94  mov     eax, [r13+4Ch]
0x140036b98  cmp     eax, 7FFFFFFFh
0x140036b9d  jnz     short loc_140036BB1
0x140036b9f  dec     eax
0x140036ba1  mov     ecx, 6
0x140036ba6  mov     [r13+4Ch], eax
0x140036baa  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140036bb0  int     3; Trap to Debugger
0x140036bb1  xorps   xmm0, xmm0
0x140036bb4  mov     qword ptr [rbp+40h+var_68], r15
0x140036bb8  movups  [rbp+40h+var_78], xmm0
0x140036bbc  mov     qword ptr [rbp+40h+var_68+8], r15
0x140036bc0  or      r8, 0FFFFFFFFFFFFFFFFh
0x140036bc4  inc     r8
0x140036bc7  cmp     [rdi+r8*2], r15w
0x140036bcc  jnz     short loc_140036BC4
0x140036bce  mov     rdx, rdi
0x140036bd1  lea     rcx, [rbp+40h+var_78]
0x140036bd5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140036bda  lea     rdx, [rbp+40h+var_78]
0x140036bde  lea     rcx, [rbp+40h+var_B0]
0x140036be2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140036be7  mov     rdx, rax
0x140036bea  lea     rcx, [rbp+40h+S1]
0x140036bee  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x140036bf3  lea     rcx, [rbp+40h+var_78]; void *
0x140036bf7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036bfc  lea     r14, [r12+0A8h]
0x140036c04  mov     rcx, r14
0x140036c07  lea     r8, [rbp+40h+S1]
0x140036c0b  lea     rdx, [rbp+40h+var_B0]
0x140036c0f  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiSessionConnectionEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiSessionConnectionEntry>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140036c14  mov     rsi, [rbp+40h+var_A0]
0x140036c18  cmp     [rsi+19h], r15b
0x140036c1c  jnz     short loc_140036C95
0x140036c1e  lea     rdx, [rsi+20h]
0x140036c22  cmp     qword ptr [rdx+18h], 7
0x140036c27  mov     rbx, [rdx+10h]
0x140036c2b  jbe     short loc_140036C30
0x140036c2d  mov     rdx, [rdx]; S2
0x140036c30  cmp     [rbp+40h+var_40], 7
0x140036c35  lea     rcx, [rbp+40h+S1]
0x140036c39  mov     rdi, [rbp+40h+var_48]
0x140036c3d  cmova   rcx, [rbp+40h+S1]; S1
0x140036c42  mov     r8, rdi
0x140036c45  cmp     rbx, rdi
0x140036c48  cmovb   r8, rbx; N
0x140036c4c  call    wmemcmp
0x140036c51  test    eax, eax
0x140036c53  jnz     short loc_140036C8F
0x140036c55  cmp     rdi, rbx
0x140036c58  jb      short loc_140036C91
0x140036c5a  jbe     short loc_140036C62
0x140036c5c  mov     al, 1
0x140036c5e  test    al, al
0x140036c60  js      short loc_140036C95
0x140036c62  cmp     rsi, [r12+0A8h]
0x140036c6a  jz      short loc_140036C95
0x140036c6c  lea     rdx, [rbp+40h+S1]
0x140036c70  mov     rcx, r14
0x140036c73  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@@2@@std@@QEAAAEAUProtocolNegotiationWorkerThreadEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ProtocolNegotiationWorkerThreadEntry>::operator[](std::wstring const &)
0x140036c78  mov     rcx, [rax+18h]
0x140036c7c  test    rcx, rcx
0x140036c7f  jz      short loc_140036C85
0x140036c81  lock inc dword ptr [rcx+8]
0x140036c85  mov     r15, [rax+10h]
0x140036c89  mov     rbx, [rax+18h]
0x140036c8d  jmp     short loc_140036CD6
0x140036c8f  jns     short loc_140036C5C
0x140036c91  mov     al, 0FFh
0x140036c93  jmp     short loc_140036C5E
0x140036c95  mov     ecx, 158h; Size
0x140036c9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140036c9f  mov     rbx, rax
0x140036ca2  xor     edx, edx; Val
0x140036ca4  mov     r8d, 148h; Size
0x140036caa  mov     dword ptr [rax+8], 1
0x140036cb1  mov     dword ptr [rax+0Ch], 1
0x140036cb8  lea     r15, [rbx+10h]
0x140036cbc  lea     rax, ??_7?$_Ref_count_obj2@VCMidiEndpointProtocolWorker@@@std@@6B@; const std::_Ref_count_obj2<CMidiEndpointProtocolWorker>::`vftable'
0x140036cc3  mov     rcx, r15; void *
0x140036cc6  mov     [rbx], rax
0x140036cc9  call    memset_0
0x140036cce  mov     rcx, r15; this
0x140036cd1  call    ??0CMidiEndpointProtocolWorker@@QEAA@XZ; CMidiEndpointProtocolWorker::CMidiEndpointProtocolWorker(void)
0x140036cd6  test    r15, r15
0x140036cd9  jnz     short loc_140036D11
0x140036cdb  mov     rcx, [rbp+48h]; this
0x140036cdf  lea     r8, aAvcoreMidi2Ser_12; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140036ce6  mov     edi, 80004003h
0x140036ceb  mov     edx, 0D3h; void *
0x140036cf0  mov     r9d, edi; char *
0x140036cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140036cf8  test    rbx, rbx
0x140036cfb  jz      loc_140036DC8
0x140036d01  or      eax, 0FFFFFFFFh
0x140036d04  lock xadd [rbx+8], eax
0x140036d09  cmp     eax, 1
0x140036d0c  jmp     loc_140036D9C
0x140036d11  mov     rcx, qword ptr [rsp+140h+var_F0]
0x140036d16  lea     rdx, [r12+38h]
0x140036d1b  mov     rax, [r15]
0x140036d1e  lea     r8, [r12+28h]
0x140036d23  cmp     [rbp+40h+var_40], 7
0x140036d28  lea     r9, [rbp+40h+S1]
0x140036d2c  movups  xmm1, xmmword ptr [r12+14h]
0x140036d32  cmova   r9, [rbp+40h+S1]
0x140036d37  movups  xmm0, xmmword ptr [rcx]
0x140036d3a  mov     rax, [rax+28h]
0x140036d3e  lea     rcx, [r12+48h]
0x140036d43  mov     [rsp+140h+var_110], rcx
0x140036d48  mov     rcx, r15
0x140036d4b  mov     [rsp+140h+var_118], rdx
0x140036d50  lea     rdx, [rbp+40h+var_B0]
0x140036d54  mov     qword ptr [rsp+140h+var_120], r8; int
0x140036d59  lea     r8, [rsp+140h+var_F0]
0x140036d5e  movdqu  [rsp+140h+var_F0], xmm0
0x140036d64  movdqu  xmmword ptr [rbp+40h+var_B0], xmm1
0x140036d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036d6e  mov     edi, eax
0x140036d70  test    eax, eax
0x140036d72  jns     short loc_140036DE1
0x140036d74  mov     rcx, [rbp+48h]; this
0x140036d78  lea     r8, aAvcoreMidi2Ser_12; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140036d7f  mov     r9d, eax; char *
0x140036d82  mov     edx, 0DEh; void *
0x140036d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140036d8c  test    rbx, rbx
0x140036d8f  jz      short loc_140036DC8
0x140036d91  or      ecx, 0FFFFFFFFh
0x140036d94  lock xadd [rbx+8], ecx
0x140036d99  cmp     ecx, 1
0x140036d9c  jnz     short loc_140036DC8
0x140036d9e  mov     rax, [rbx]
0x140036da1  mov     rcx, rbx
0x140036da4  mov     rax, [rax]
0x140036da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036dac  or      eax, 0FFFFFFFFh
0x140036daf  lock xadd [rbx+0Ch], eax
0x140036db4  cmp     eax, 1
0x140036db7  jnz     short loc_140036DC8
0x140036db9  mov     rax, [rbx]
0x140036dbc  mov     rcx, rbx
0x140036dbf  mov     rax, [rax+8]
0x140036dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036dc8  lea     rcx, [rbp+40h+S1]; void *
0x140036dcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036dd1  mov     rcx, r13; _Mtx_t
0x140036dd4  call    cs:__imp__Mtx_unlock
0x140036dda  mov     eax, edi
0x140036ddc  jmp     loc_140036B4F
0x140036de1  xorps   xmm0, xmm0
0x140036de4  movdqu  [rbp+40h+var_78], xmm0
0x140036de9  movups  [rbp+40h+var_68], xmm0
0x140036ded  test    rbx, rbx
0x140036df0  jz      short loc_140036DF6
0x140036df2  lock inc dword ptr [rbx+8]
0x140036df6  lea     rax, ??_9CMidiEndpointProtocolWorker@@$BDA@AA; [thunk]: CMidiEndpointProtocolWorker::`vcall'{48,{flat}}
0x140036dfd  mov     qword ptr [rbp+40h+var_68], r15
0x140036e01  mov     qword ptr [rsp+140h+var_F0], rax
0x140036e06  mov     ecx, 20h ; ' '; Size
0x140036e0b  mov     eax, [rbp+40h+var_B4]
0x140036e0e  mov     dword ptr [rsp+140h+var_F0+0Ch], eax
0x140036e12  mov     qword ptr [rbp+40h+var_68+8], rbx
0x140036e16  mov     dword ptr [rsp+140h+var_F0+8], 0
0x140036e1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140036e23  mov     r9, [rsp+140h+var_D0._Hnd]
0x140036e28  lea     r8, [rbp+40h+var_68]
0x140036e2c  mov     r14, rax
0x140036e2f  lea     rdx, [rsp+140h+var_F0]
0x140036e34  mov     dword ptr [rax+8], 1
0x140036e3b  mov     dword ptr [rax+0Ch], 1
0x140036e42  lea     rax, ??_7?$_Ref_count_obj2@Vthread@std@@@std@@6B@; const std::_Ref_count_obj2<std::thread>::`vftable'
0x140036e49  lea     rdi, [r14+10h]
0x140036e4d  mov     [r14], rax
0x140036e50  mov     rcx, rdi
0x140036e53  call    ??$?0P8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EAEAV?$shared_ptr@VCMidiEndpointProtocolWorker@@@std@@AEAU1@$0A@@thread@std@@QEAA@$$QEAP8CMidiEndpointProtocolWorker@@EAAJU__MIDL___MIDL_itf_windowsmidiservices_0000_0010_0001@@@_EAEAV?$shared_ptr@VCMidiEndpointProtocolWorker@@@1@AEAU3@@Z
0x140036e58  mov     qword ptr [rbp+40h+var_78], rdi
0x140036e5c  mov     rdi, qword ptr [rbp+40h+var_78+8]
0x140036e60  mov     qword ptr [rbp+40h+var_78+8], r14
0x140036e64  test    rdi, rdi
0x140036e67  jz      short loc_140036EA0
0x140036e69  or      eax, 0FFFFFFFFh
0x140036e6c  lock xadd [rdi+8], eax
0x140036e71  cmp     eax, 1
0x140036e74  jnz     short loc_140036EA0
0x140036e76  mov     rax, [rdi]
0x140036e79  mov     rcx, rdi
0x140036e7c  mov     rax, [rax]
0x140036e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e84  or      eax, 0FFFFFFFFh
0x140036e87  lock xadd [rdi+0Ch], eax
0x140036e8c  cmp     eax, 1
0x140036e8f  jnz     short loc_140036EA0
0x140036e91  mov     rax, [rdi]
0x140036e94  mov     rcx, rdi
0x140036e97  mov     rax, [rax+8]
0x140036e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ea0  lea     rdx, [rbp+40h+S1]
0x140036ea4  lea     rcx, [r12+0A8h]
0x140036eac  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@@2@@std@@QEAAAEAUProtocolNegotiationWorkerThreadEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ProtocolNegotiationWorkerThreadEntry>::operator[](std::wstring const &)
0x140036eb1  mov     rsi, rax
0x140036eb4  lock inc dword ptr [r14+8]
0x140036eb9  mov     rdi, [rsi+8]
0x140036ebd  lea     rax, [r14+10h]
0x140036ec1  mov     [rsi+8], r14
0x140036ec5  or      r14, 0FFFFFFFFFFFFFFFFh
0x140036ec9  mov     [rsi], rax
0x140036ecc  test    rdi, rdi
0x140036ecf  jz      short loc_140036F08
0x140036ed1  mov     ecx, r14d
0x140036ed4  lock xadd [rdi+8], ecx
0x140036ed9  add     ecx, r14d
0x140036edc  jnz     short loc_140036F08
0x140036ede  mov     rax, [rdi]
0x140036ee1  mov     rcx, rdi
0x140036ee4  mov     rax, [rax]
0x140036ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036eec  mov     eax, r14d
0x140036eef  lock xadd [rdi+0Ch], eax
0x140036ef4  add     eax, r14d
0x140036ef7  jnz     short loc_140036F08
0x140036ef9  mov     rax, [rdi]
0x140036efc  mov     rcx, rdi
0x140036eff  mov     rax, [rax+8]
0x140036f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f08  test    rbx, rbx
0x140036f0b  jz      short loc_140036F11
0x140036f0d  lock inc dword ptr [rbx+8]
0x140036f11  mov     rdi, [rsi+18h]
0x140036f15  mov     [rsi+10h], r15
0x140036f19  mov     [rsi+18h], rbx
  ... truncated ...
```
