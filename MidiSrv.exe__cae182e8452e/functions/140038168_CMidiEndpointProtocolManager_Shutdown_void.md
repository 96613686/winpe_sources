# CMidiEndpointProtocolManager::Shutdown(void)

- ea: `0x140038168`
- end: `0x140038427`
- name: `?Shutdown@CMidiEndpointProtocolManager@@QEAAJXZ`
- size: `703`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400113b8`

## callees

- `0x1400018e4`
- `0x140005868`
- `0x140007c20`
- `0x14000984c`
- `0x14000c598`
- `0x14000d15c`
- `0x14000e154`
- `0x140013a38`
- `0x140037dd0`
- `0x140038168`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400381eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400381eb`

## string_xrefs

- `0x140038240`: `avcore\midi2\service\exe\midiendpointprotocolmanager.cpp`
- `0x140038187`: `CMidiEndpointProtocolManager::Shutdown`
- `0x1400382e8`: `CMidiEndpointProtocolManager::Shutdown`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolManager::Shutdown(CMidiEndpointProtocolManager *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, _OWORD *, _QWORD); // rbx
  DWORD CurrentProcessId; // eax
  char *v8; // r12
  __int64 *v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  __int64 **v12; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v15; // r14
  char *v16; // r15
  char **v17; // rdi
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  _DWORD *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  _OWORD v25[2]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  const wchar_t *v27; // [rsp+A0h] [rbp+40h] BYREF
  CMidiEndpointProtocolManager *v28; // [rsp+A8h] [rbp+48h] BYREF
  const char *v29; // [rsp+B0h] [rbp+50h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v28 = this;
    v27 = L"Enter";
    v29 = "CMidiEndpointProtocolManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)word_14008A812,
      v3,
      v4,
      &v29,
      (__int64)&v28,
      &v27);
  }
  if ( *((_BYTE *)this + 16) )
  {
    v5 = *((_QWORD *)this + 9);
    v6 = *(void (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v5 + 40LL);
    CurrentProcessId = GetCurrentProcessId();
    v25[0] = *(_OWORD *)((char *)this + 20);
    v6(v5, v25, CurrentProcessId);
    v8 = (char *)this + 168;
    v9 = (__int64 *)**((_QWORD **)this + 21);
    while ( !*((_BYTE *)v9 + 25) )
    {
      v10 = std::wstring::wstring((__int64)v25, (__int64)(v9 + 4));
      v11 = CMidiEndpointProtocolManager::RemoveWorkerIfPresent(this, v10);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14F,
          (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolmanager.cpp",
          (const char *)(unsigned int)v11);
      v12 = (__int64 **)v9[2];
      if ( *((_BYTE *)v12 + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
        v9 = i;
      }
      else
      {
        v9 = (__int64 *)v9[2];
        for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v9 = j;
      }
    }
    v15 = *(_QWORD **)v8;
    v16 = *(char **)(*(_QWORD *)v8 + 8LL);
    while ( !v16[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>,void *>>>(
        (__int64)this + 168,
        (__int64)this + 168,
        *((__int64 **)v16 + 2));
      v17 = (char **)v16;
      v16 = *(char **)v16;
      ProtocolNegotiationWorkerThreadEntry::~ProtocolNegotiationWorkerThreadEntry((ProtocolNegotiationWorkerThreadEntry *)(v17 + 8));
      std::wstring::~wstring(v17 + 4);
      operator delete(v17);
    }
    v15[1] = v15;
    *v15 = v15;
    v15[2] = v15;
    *((_QWORD *)this + 22) = 0;
  }
  v18 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  v19 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  v20 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v21 > 4u )
  {
    v28 = this;
    v27 = L"Exit";
    v29 = "CMidiEndpointProtocolManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v21,
      (__int64)byte_14008A69D,
      v22,
      v23,
      &v29,
      (__int64)&v28,
      &v27);
  }
  return 0;
}

```

## disassembly

```asm
0x140038168  mov     [rsp-38h+arg_18], rbx
0x14003816d  push    rbp
0x14003816e  push    rsi
0x14003816f  push    rdi
0x140038170  push    r12
0x140038172  push    r13
0x140038174  push    r14
0x140038176  push    r15
0x140038178  mov     rbp, rsp
0x14003817b  sub     rsp, 60h
0x14003817f  mov     rsi, rcx
0x140038182  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140038187  lea     r14, aCmidiendpointp_3; "CMidiEndpointProtocolManager::Shutdown"
0x14003818e  mov     rcx, [rax+8]
0x140038192  mov     eax, [rcx]
0x140038194  cmp     eax, 4
0x140038197  jbe     short loc_1400381D3
0x140038199  lea     rax, aEnter; "Enter"
0x1400381a0  mov     [rbp+arg_8], rsi
0x1400381a4  mov     [rbp+arg_0], rax
0x1400381a8  lea     rdx, word_14008A812
0x1400381af  lea     rax, [rbp+arg_0]
0x1400381b3  mov     [rbp+arg_10], r14
0x1400381b7  mov     [rsp+60h+var_30], rax
0x1400381bc  lea     rax, [rbp+arg_8]
0x1400381c0  mov     [rsp+60h+var_38], rax
0x1400381c5  lea     rax, [rbp+arg_10]
0x1400381c9  mov     qword ptr [rsp+60h+var_40], rax; int
0x1400381ce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1400381d3  xor     r13d, r13d
0x1400381d6  cmp     [rsi+10h], r13b
0x1400381da  jz      loc_1400382F4
0x1400381e0  mov     rdi, [rsi+48h]
0x1400381e4  mov     rax, [rdi]
0x1400381e7  mov     rbx, [rax+28h]
0x1400381eb  call    cs:__imp_GetCurrentProcessId
0x1400381f1  movups  xmm0, xmmword ptr [rsi+14h]
0x1400381f5  mov     r8d, eax
0x1400381f8  lea     rdx, [rbp+var_20]
0x1400381fc  mov     rcx, rdi
0x1400381ff  mov     rax, rbx
0x140038202  movdqu  [rbp+var_20], xmm0
0x140038207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003820c  lea     r12, [rsi+0A8h]
0x140038213  mov     rbx, [r12]
0x140038217  mov     rbx, [rbx]
0x14003821a  cmp     [rbx+19h], r13b
0x14003821e  jnz     short loc_140038299
0x140038220  lea     rdx, [rbx+20h]
0x140038224  lea     rcx, [rbp+var_20]
0x140038228  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003822d  mov     rdx, rax
0x140038230  mov     rcx, rsi
0x140038233  call    ?RemoveWorkerIfPresent@CMidiEndpointProtocolManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMidiEndpointProtocolManager::RemoveWorkerIfPresent(std::wstring)
0x140038238  test    eax, eax
0x14003823a  jns     short loc_140038254
0x14003823c  mov     rcx, [rbp+38h]; this
0x140038240  lea     r8, aAvcoreMidi2Ser_12; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140038247  mov     r9d, eax; char *
0x14003824a  mov     edx, 14Fh; void *
0x14003824f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140038254  mov     rcx, [rbx+10h]
0x140038258  cmp     [rcx+19h], r13b
0x14003825c  jz      short loc_14003827C
0x14003825e  mov     rax, [rbx+8]
0x140038262  jmp     short loc_140038271
0x140038264  cmp     rbx, [rax+10h]
0x140038268  jnz     short loc_140038277
0x14003826a  mov     rbx, rax
0x14003826d  mov     rax, [rax+8]
0x140038271  cmp     [rax+19h], r13b
0x140038275  jz      short loc_140038264
0x140038277  mov     rbx, rax
0x14003827a  jmp     short loc_14003821A
0x14003827c  mov     rbx, rcx
0x14003827f  mov     rcx, [rcx]
0x140038282  cmp     [rcx+19h], r13b
0x140038286  jnz     short loc_14003821A
0x140038288  mov     rax, [rcx]
0x14003828b  mov     rbx, rcx
0x14003828e  mov     rcx, rax
0x140038291  cmp     [rax+19h], r13b
0x140038295  jz      short loc_140038288
0x140038297  jmp     short loc_14003821A
0x140038299  mov     r14, [r12]
0x14003829d  mov     r15, [r14+8]
0x1400382a1  jmp     short loc_1400382D7
0x1400382a3  mov     r8, [r15+10h]
0x1400382a7  mov     rdx, r12
0x1400382aa  mov     rcx, r12
0x1400382ad  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UProtocolNegotiationWorkerThreadEntry@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>,void *>> &,std::_Tree_node<std::pair<std::wstring const,ProtocolNegotiationWorkerThreadEntry>,void *> *)
0x1400382b2  mov     rdi, r15
0x1400382b5  mov     r15, [r15]
0x1400382b8  lea     rcx, [rdi+40h]; this
0x1400382bc  call    ??1ProtocolNegotiationWorkerThreadEntry@@QEAA@XZ; ProtocolNegotiationWorkerThreadEntry::~ProtocolNegotiationWorkerThreadEntry(void)
0x1400382c1  lea     rcx, [rdi+20h]; void *
0x1400382c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400382ca  mov     edx, 60h ; '`'
0x1400382cf  mov     rcx, rdi; Block
0x1400382d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400382d7  cmp     [r15+19h], r13b
0x1400382db  jz      short loc_1400382A3
0x1400382dd  mov     [r14+8], r14
0x1400382e1  mov     [r14], r14
0x1400382e4  mov     [r14+10h], r14
0x1400382e8  lea     r14, aCmidiendpointp_3; "CMidiEndpointProtocolManager::Shutdown"
0x1400382ef  mov     [r12+8], r13
0x1400382f4  mov     rbx, [rsi+30h]
0x1400382f8  or      edi, 0FFFFFFFFh
0x1400382fb  mov     [rsi+28h], r13
0x1400382ff  mov     [rsi+30h], r13
0x140038303  test    rbx, rbx
0x140038306  jz      short loc_14003833B
0x140038308  mov     eax, edi
0x14003830a  lock xadd [rbx+8], eax
0x14003830f  add     eax, edi
0x140038311  jnz     short loc_14003833B
0x140038313  mov     rax, [rbx]
0x140038316  mov     rcx, rbx
0x140038319  mov     rax, [rax]
0x14003831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038321  mov     eax, edi
0x140038323  lock xadd [rbx+0Ch], eax
0x140038328  add     eax, edi
0x14003832a  jnz     short loc_14003833B
0x14003832c  mov     rax, [rbx]
0x14003832f  mov     rcx, rbx
0x140038332  mov     rax, [rax+8]
0x140038336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003833b  mov     rbx, [rsi+40h]
0x14003833f  mov     [rsi+38h], r13
0x140038343  mov     [rsi+40h], r13
0x140038347  test    rbx, rbx
0x14003834a  jz      short loc_14003837F
0x14003834c  mov     eax, edi
0x14003834e  lock xadd [rbx+8], eax
0x140038353  add     eax, edi
0x140038355  jnz     short loc_14003837F
0x140038357  mov     rax, [rbx]
0x14003835a  mov     rcx, rbx
0x14003835d  mov     rax, [rax]
0x140038360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038365  mov     eax, edi
0x140038367  lock xadd [rbx+0Ch], eax
0x14003836c  add     eax, edi
0x14003836e  jnz     short loc_14003837F
0x140038370  mov     rax, [rbx]
0x140038373  mov     rcx, rbx
0x140038376  mov     rax, [rax+8]
0x14003837a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003837f  mov     rbx, [rsi+50h]
0x140038383  mov     [rsi+48h], r13
0x140038387  mov     [rsi+50h], r13
0x14003838b  test    rbx, rbx
0x14003838e  jz      short loc_1400383C3
0x140038390  mov     eax, edi
0x140038392  lock xadd [rbx+8], eax
0x140038397  add     eax, edi
0x140038399  jnz     short loc_1400383C3
0x14003839b  mov     rax, [rbx]
0x14003839e  mov     rcx, rbx
0x1400383a1  mov     rax, [rax]
0x1400383a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400383a9  mov     eax, edi
0x1400383ab  lock xadd [rbx+0Ch], eax
0x1400383b0  add     eax, edi
0x1400383b2  jnz     short loc_1400383C3
0x1400383b4  mov     rax, [rbx]
0x1400383b7  mov     rcx, rbx
0x1400383ba  mov     rax, [rax+8]
0x1400383be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400383c3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400383c8  mov     rcx, [rax+8]
0x1400383cc  mov     eax, [rcx]
0x1400383ce  cmp     eax, 4
0x1400383d1  jbe     short loc_14003840D
0x1400383d3  lea     rax, aExit; "Exit"
0x1400383da  mov     [rbp+arg_8], rsi
0x1400383de  mov     [rbp+arg_0], rax
0x1400383e2  lea     rdx, byte_14008A69D
0x1400383e9  lea     rax, [rbp+arg_0]
0x1400383ed  mov     [rbp+arg_10], r14
0x1400383f1  mov     [rsp+60h+var_30], rax
0x1400383f6  lea     rax, [rbp+arg_8]
0x1400383fa  mov     [rsp+60h+var_38], rax
0x1400383ff  lea     rax, [rbp+arg_10]
0x140038403  mov     qword ptr [rsp+60h+var_40], rax
0x140038408  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003840d  mov     rbx, [rsp+60h+arg_18]
0x140038415  xor     eax, eax
0x140038417  add     rsp, 60h
0x14003841b  pop     r15
0x14003841d  pop     r14
0x14003841f  pop     r13
0x140038421  pop     r12
0x140038423  pop     rdi
0x140038424  pop     rsi
0x140038425  pop     rbp
0x140038426  retn
```
