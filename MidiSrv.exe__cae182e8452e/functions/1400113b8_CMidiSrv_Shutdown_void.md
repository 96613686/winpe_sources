# CMidiSrv::Shutdown(void)

- ea: `0x1400113b8`
- end: `0x1400117a5`
- name: `?Shutdown@CMidiSrv@@QEAAJXZ`
- size: `1005`
- prototype: `__int64 __fastcall(CMidiSrv *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000b2b8`
- `0x14000da78`
- `0x140010068`

## callees

- `0x14000183c`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400113b8`
- `0x1400118bc`
- `0x1400118e0`
- `0x14001d7c8`
- `0x140026018`
- `0x140038168`
- `0x1400387bc`
- `0x14003886c`
- `0x14005a010`

## import_xrefs

- `RPCRT4!RpcEpUnregister` at `0x140011424`
- `RPCRT4!RpcEpUnregister` at `0x140011424`
- `RPCRT4!RpcBindingVectorFree` at `0x14001149e`
- `RPCRT4!RpcBindingVectorFree` at `0x14001149e`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x14001145d`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x14001145d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400114a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400114a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001148c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001148c`

## string_xrefs

- `0x1400114d4`: `avcore\midi2\service\exe\midisrv.cpp`

## pseudocode

```c
__int64 __fastcall CMidiSrv::Shutdown(CMidiSrv *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // eax
  unsigned int v8; // r8d
  RPC_BINDING_VECTOR *v9; // rsi
  DWORD LastError; // eax
  DWORD v11; // ebx
  RTL_SRWLOCK *v12; // rcx
  int v13; // ebx
  __int64 v14; // rdx
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  CMidiProcessManager *v20; // rcx
  volatile signed __int32 *v21; // rbx
  CMidiConfigurationManager *v22; // rcx
  volatile signed __int32 *v23; // rbx
  CMidiEndpointProtocolManager *v24; // rcx
  volatile signed __int32 *v25; // rbx
  __int64 v26; // rcx
  volatile signed __int32 *v27; // rbx
  unsigned int v28; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+50h] [rbp+8h] BYREF
  const char *v31; // [rsp+58h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    BindingVector = (RPC_BINDING_VECTOR *)this;
    v31 = "CMidiSrv::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v2,
      (__int64)byte_140087209,
      v3,
      v4,
      &v31);
  }
  if ( *((_BYTE *)this + 129) )
  {
    v5 = RpcEpUnregister(qword_14005C0B0, *((RPC_BINDING_VECTOR **)this + 17), 0);
    if ( v5 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0xC8, v6, (const char *)v5, v28);
    *((_BYTE *)this + 129) = 0;
  }
  if ( *((_BYTE *)this + 128) )
  {
    v7 = RpcServerUnregisterIfEx(qword_14005C0B0, 0, 1);
    if ( v7 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0xCE, v8, (const char *)v7, v28);
    *((_BYTE *)this + 128) = 0;
  }
  v9 = (RPC_BINDING_VECTOR *)*((_QWORD *)this + 17);
  if ( v9 )
  {
    LastError = GetLastError();
    BindingVector = v9;
    v11 = LastError;
    RpcBindingVectorFree(&BindingVector);
    SetLastError(v11);
    *((_QWORD *)this + 17) = 0;
  }
  v12 = (RTL_SRWLOCK *)*((_QWORD *)this + 6);
  if ( v12 )
  {
    v13 = CMidiClientManager::Shutdown(v12);
    if ( v13 < 0 )
    {
      v14 = 217;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"avcore\\midi2\\service\\exe\\midisrv.cpp",
        (const char *)(unsigned int)v13,
        v28);
      return (unsigned int)v13;
    }
    v16 = (volatile signed __int32 *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    if ( v16 )
    {
      if ( !_InterlockedDecrement(v16 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( !_InterlockedDecrement(v16 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  v17 = *((_QWORD *)this + 4);
  if ( v17 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 112LL))(v17);
    if ( v13 < 0 )
    {
      v14 = 223;
      goto LABEL_16;
    }
    v18 = (volatile signed __int32 *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    if ( v18 )
    {
      if ( !_InterlockedDecrement(v18 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( !_InterlockedDecrement(v18 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  if ( *(_QWORD *)this )
  {
    v13 = CMidiPerformanceManager::Shutdown(*(CMidiPerformanceManager **)this);
    if ( v13 < 0 )
    {
      v14 = 229;
      goto LABEL_16;
    }
    v19 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    if ( v19 )
    {
      if ( !_InterlockedDecrement(v19 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( !_InterlockedDecrement(v19 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
  v20 = (CMidiProcessManager *)*((_QWORD *)this + 2);
  if ( v20 )
  {
    v13 = CMidiProcessManager::Shutdown(v20);
    if ( v13 < 0 )
    {
      v14 = 235;
      goto LABEL_16;
    }
    v21 = (volatile signed __int32 *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    if ( v21 )
    {
      if ( !_InterlockedDecrement(v21 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( !_InterlockedDecrement(v21 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
  }
  v22 = (CMidiConfigurationManager *)*((_QWORD *)this + 8);
  if ( v22 )
  {
    v13 = CMidiConfigurationManager::Shutdown(v22);
    if ( v13 < 0 )
    {
      v14 = 241;
      goto LABEL_16;
    }
    v23 = (volatile signed __int32 *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    if ( v23 )
    {
      if ( !_InterlockedDecrement(v23 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( !_InterlockedDecrement(v23 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
  {
    v24 = (CMidiEndpointProtocolManager *)*((_QWORD *)this + 10);
    if ( v24 )
    {
      v13 = CMidiEndpointProtocolManager::Shutdown(v24);
      if ( v13 < 0 )
      {
        v14 = 249;
        goto LABEL_16;
      }
      v25 = (volatile signed __int32 *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 11) = 0;
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
  }
  v26 = *((_QWORD *)this + 12);
  if ( v26 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 72LL))(v26);
    if ( v13 < 0 )
    {
      v14 = 256;
      goto LABEL_16;
    }
    v27 = (volatile signed __int32 *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    if ( v27 && _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400113b8  mov     [rsp+arg_10], rbx
0x1400113bd  push    rbp
0x1400113be  push    rsi
0x1400113bf  push    rdi
0x1400113c0  sub     rsp, 30h
0x1400113c4  mov     rdi, rcx
0x1400113c7  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400113cc  mov     rcx, [rax+8]
0x1400113d0  mov     eax, [rcx]
0x1400113d2  cmp     eax, 4
0x1400113d5  jbe     short loc_140011408
0x1400113d7  lea     rax, aCmidisrvShutdo; "CMidiSrv::Shutdown"
0x1400113de  mov     [rsp+48h+BindingVector], rdi
0x1400113e3  mov     [rsp+48h+arg_8], rax
0x1400113e8  lea     rdx, byte_140087209
0x1400113ef  lea     rax, [rsp+48h+BindingVector]
0x1400113f4  mov     [rsp+48h+var_20], rax
0x1400113f9  lea     rax, [rsp+48h+arg_8]
0x1400113fe  mov     qword ptr [rsp+48h+var_28], rax; int
0x140011403  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x140011408  xor     ebp, ebp
0x14001140a  cmp     [rdi+81h], bpl
0x140011411  jz      short loc_140011447
0x140011413  mov     rdx, [rdi+88h]; BindingVector
0x14001141a  lea     rcx, qword_14005C0B0; IfSpec
0x140011421  xor     r8d, r8d; UuidVector
0x140011424  call    cs:__imp_RpcEpUnregister
0x14001142a  test    eax, eax
0x14001142c  jz      short loc_140011440
0x14001142e  mov     rcx, [rsp+48h]; this
0x140011433  mov     r9d, eax; char *
0x140011436  mov     edx, 0C8h; void *
0x14001143b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140011440  mov     [rdi+81h], bpl
0x140011447  cmp     [rdi+80h], bpl
0x14001144e  jz      short loc_140011480
0x140011450  xor     edx, edx; MgrTypeUuid
0x140011452  lea     rcx, qword_14005C0B0; IfSpec
0x140011459  lea     r8d, [rdx+1]; RundownContextHandles
0x14001145d  call    cs:__imp_RpcServerUnregisterIfEx
0x140011463  test    eax, eax
0x140011465  jz      short loc_140011479
0x140011467  mov     rcx, [rsp+48h]; this
0x14001146c  mov     r9d, eax; char *
0x14001146f  mov     edx, 0CEh; void *
0x140011474  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140011479  mov     [rdi+80h], bpl
0x140011480  mov     rsi, [rdi+88h]
0x140011487  test    rsi, rsi
0x14001148a  jz      short loc_1400114B3
0x14001148c  call    cs:__imp_GetLastError
0x140011492  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x140011497  mov     [rsp+48h+BindingVector], rsi
0x14001149c  mov     ebx, eax
0x14001149e  call    cs:__imp_RpcBindingVectorFree
0x1400114a4  mov     ecx, ebx; dwErrCode
0x1400114a6  call    cs:__imp_SetLastError
0x1400114ac  mov     [rdi+88h], rbp
0x1400114b3  mov     rcx, [rdi+30h]; SRWLock
0x1400114b7  or      esi, 0FFFFFFFFh
0x1400114ba  test    rcx, rcx
0x1400114bd  jz      short loc_14001152E
0x1400114bf  call    ?Shutdown@CMidiClientManager@@QEAAJXZ; CMidiClientManager::Shutdown(void)
0x1400114c4  mov     ebx, eax
0x1400114c6  test    eax, eax
0x1400114c8  jns     short loc_1400114EA
0x1400114ca  mov     edx, 0D9h; void *
0x1400114cf  mov     rcx, [rsp+48h]; this
0x1400114d4  lea     r8, aAvcoreMidi2Ser_4; "avcore\\midi2\\service\\exe\\midisrv.cp"...
0x1400114db  mov     r9d, ebx; char *
0x1400114de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400114e3  mov     eax, ebx
0x1400114e5  jmp     loc_140011798
0x1400114ea  mov     rbx, [rdi+38h]
0x1400114ee  mov     [rdi+30h], rbp
0x1400114f2  mov     [rdi+38h], rbp
0x1400114f6  test    rbx, rbx
0x1400114f9  jz      short loc_14001152E
0x1400114fb  mov     eax, esi
0x1400114fd  lock xadd [rbx+8], eax
0x140011502  add     eax, esi
0x140011504  jnz     short loc_14001152E
0x140011506  mov     rax, [rbx]
0x140011509  mov     rcx, rbx
0x14001150c  mov     rax, [rax]
0x14001150f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011514  mov     eax, esi
0x140011516  lock xadd [rbx+0Ch], eax
0x14001151b  add     eax, esi
0x14001151d  jnz     short loc_14001152E
0x14001151f  mov     rax, [rbx]
0x140011522  mov     rcx, rbx
0x140011525  mov     rax, [rax+8]
0x140011529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001152e  mov     rcx, [rdi+20h]
0x140011532  test    rcx, rcx
0x140011535  jz      short loc_140011597
0x140011537  mov     rax, [rcx]
0x14001153a  mov     rax, [rax+70h]
0x14001153e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011543  mov     ebx, eax
0x140011545  test    eax, eax
0x140011547  jns     short loc_140011553
0x140011549  mov     edx, 0DFh
0x14001154e  jmp     loc_1400114CF
0x140011553  mov     rbx, [rdi+28h]
0x140011557  mov     [rdi+20h], rbp
0x14001155b  mov     [rdi+28h], rbp
0x14001155f  test    rbx, rbx
0x140011562  jz      short loc_140011597
0x140011564  mov     eax, esi
0x140011566  lock xadd [rbx+8], eax
0x14001156b  add     eax, esi
0x14001156d  jnz     short loc_140011597
0x14001156f  mov     rax, [rbx]
0x140011572  mov     rcx, rbx
0x140011575  mov     rax, [rax]
0x140011578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001157d  mov     eax, esi
0x14001157f  lock xadd [rbx+0Ch], eax
0x140011584  add     eax, esi
0x140011586  jnz     short loc_140011597
0x140011588  mov     rax, [rbx]
0x14001158b  mov     rcx, rbx
0x14001158e  mov     rax, [rax+8]
0x140011592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011597  mov     rcx, [rdi]; this
0x14001159a  test    rcx, rcx
0x14001159d  jz      short loc_1400115F7
0x14001159f  call    ?Shutdown@CMidiPerformanceManager@@QEAAJXZ; CMidiPerformanceManager::Shutdown(void)
0x1400115a4  mov     ebx, eax
0x1400115a6  test    eax, eax
0x1400115a8  jns     short loc_1400115B4
0x1400115aa  mov     edx, 0E5h
0x1400115af  jmp     loc_1400114CF
0x1400115b4  mov     rbx, [rdi+8]
0x1400115b8  mov     [rdi], rbp
0x1400115bb  mov     [rdi+8], rbp
0x1400115bf  test    rbx, rbx
0x1400115c2  jz      short loc_1400115F7
0x1400115c4  mov     eax, esi
0x1400115c6  lock xadd [rbx+8], eax
0x1400115cb  add     eax, esi
0x1400115cd  jnz     short loc_1400115F7
0x1400115cf  mov     rax, [rbx]
0x1400115d2  mov     rcx, rbx
0x1400115d5  mov     rax, [rax]
0x1400115d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115dd  mov     eax, esi
0x1400115df  lock xadd [rbx+0Ch], eax
0x1400115e4  add     eax, esi
0x1400115e6  jnz     short loc_1400115F7
0x1400115e8  mov     rax, [rbx]
0x1400115eb  mov     rcx, rbx
0x1400115ee  mov     rax, [rax+8]
0x1400115f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115f7  mov     rcx, [rdi+10h]; this
0x1400115fb  test    rcx, rcx
0x1400115fe  jz      short loc_140011659
0x140011600  call    ?Shutdown@CMidiProcessManager@@QEAAJXZ; CMidiProcessManager::Shutdown(void)
0x140011605  mov     ebx, eax
0x140011607  test    eax, eax
0x140011609  jns     short loc_140011615
0x14001160b  mov     edx, 0EBh
0x140011610  jmp     loc_1400114CF
0x140011615  mov     rbx, [rdi+18h]
0x140011619  mov     [rdi+10h], rbp
0x14001161d  mov     [rdi+18h], rbp
0x140011621  test    rbx, rbx
0x140011624  jz      short loc_140011659
0x140011626  mov     eax, esi
0x140011628  lock xadd [rbx+8], eax
0x14001162d  add     eax, esi
0x14001162f  jnz     short loc_140011659
0x140011631  mov     rax, [rbx]
0x140011634  mov     rcx, rbx
0x140011637  mov     rax, [rax]
0x14001163a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001163f  mov     eax, esi
0x140011641  lock xadd [rbx+0Ch], eax
0x140011646  add     eax, esi
0x140011648  jnz     short loc_140011659
0x14001164a  mov     rax, [rbx]
0x14001164d  mov     rcx, rbx
0x140011650  mov     rax, [rax+8]
0x140011654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011659  mov     rcx, [rdi+40h]; this
0x14001165d  test    rcx, rcx
0x140011660  jz      short loc_1400116BB
0x140011662  call    ?Shutdown@CMidiConfigurationManager@@QEAAJXZ; CMidiConfigurationManager::Shutdown(void)
0x140011667  mov     ebx, eax
0x140011669  test    eax, eax
0x14001166b  jns     short loc_140011677
0x14001166d  mov     edx, 0F1h
0x140011672  jmp     loc_1400114CF
0x140011677  mov     rbx, [rdi+48h]
0x14001167b  mov     [rdi+40h], rbp
0x14001167f  mov     [rdi+48h], rbp
0x140011683  test    rbx, rbx
0x140011686  jz      short loc_1400116BB
0x140011688  mov     eax, esi
0x14001168a  lock xadd [rbx+8], eax
0x14001168f  add     eax, esi
0x140011691  jnz     short loc_1400116BB
0x140011693  mov     rax, [rbx]
0x140011696  mov     rcx, rbx
0x140011699  mov     rax, [rax]
0x14001169c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400116a1  mov     eax, esi
0x1400116a3  lock xadd [rbx+0Ch], eax
0x1400116a8  add     eax, esi
0x1400116aa  jnz     short loc_1400116BB
0x1400116ac  mov     rax, [rbx]
0x1400116af  mov     rcx, rbx
0x1400116b2  mov     rax, [rax+8]
0x1400116b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400116bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x1400116c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x1400116c7  test    al, al
0x1400116c9  jz      short loc_14001172D
0x1400116cb  mov     rcx, [rdi+50h]; this
0x1400116cf  test    rcx, rcx
0x1400116d2  jz      short loc_14001172D
0x1400116d4  call    ?Shutdown@CMidiEndpointProtocolManager@@QEAAJXZ; CMidiEndpointProtocolManager::Shutdown(void)
0x1400116d9  mov     ebx, eax
0x1400116db  test    eax, eax
0x1400116dd  jns     short loc_1400116E9
0x1400116df  mov     edx, 0F9h
0x1400116e4  jmp     loc_1400114CF
0x1400116e9  mov     rbx, [rdi+58h]
0x1400116ed  mov     [rdi+50h], rbp
0x1400116f1  mov     [rdi+58h], rbp
0x1400116f5  test    rbx, rbx
0x1400116f8  jz      short loc_14001172D
0x1400116fa  mov     eax, esi
0x1400116fc  lock xadd [rbx+8], eax
0x140011701  add     eax, esi
0x140011703  jnz     short loc_14001172D
0x140011705  mov     rax, [rbx]
0x140011708  mov     rcx, rbx
0x14001170b  mov     rax, [rax]
0x14001170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011713  mov     eax, esi
0x140011715  lock xadd [rbx+0Ch], eax
0x14001171a  add     eax, esi
0x14001171c  jnz     short loc_14001172D
0x14001171e  mov     rax, [rbx]
0x140011721  mov     rcx, rbx
0x140011724  mov     rax, [rax+8]
0x140011728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001172d  mov     rcx, [rdi+60h]
0x140011731  test    rcx, rcx
0x140011734  jz      short loc_140011796
0x140011736  mov     rax, [rcx]
0x140011739  mov     rax, [rax+48h]
0x14001173d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011742  mov     ebx, eax
0x140011744  test    eax, eax
0x140011746  jns     short loc_140011752
0x140011748  mov     edx, 100h
0x14001174d  jmp     loc_1400114CF
0x140011752  mov     rbx, [rdi+68h]
0x140011756  mov     [rdi+60h], rbp
0x14001175a  mov     [rdi+68h], rbp
0x14001175e  test    rbx, rbx
0x140011761  jz      short loc_140011796
0x140011763  mov     eax, esi
0x140011765  lock xadd [rbx+8], eax
0x14001176a  add     eax, esi
0x14001176c  jnz     short loc_140011796
0x14001176e  mov     rax, [rbx]
0x140011771  mov     rcx, rbx
0x140011774  mov     rax, [rax]
0x140011777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001177c  mov     eax, esi
0x14001177e  lock xadd [rbx+0Ch], eax
0x140011783  add     eax, esi
0x140011785  jnz     short loc_140011796
0x140011787  mov     rax, [rbx]
0x14001178a  mov     rcx, rbx
0x14001178d  mov     rax, [rax+8]
0x140011791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011796  xor     eax, eax
0x140011798  mov     rbx, [rsp+48h+arg_10]
0x14001179d  add     rsp, 30h
0x1400117a1  pop     rdi
0x1400117a2  pop     rsi
0x1400117a3  pop     rbp
0x1400117a4  retn
```
