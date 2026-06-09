# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendRdpData(std::span<uchar const,-1> const &)

- ea: `0x180019238`
- end: `0x180019355`
- name: `?SendRdpData@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXAEBV?$span@$$CBE$0?0@std@@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012430`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x1800156d0`
- `0x1800156dc`
- `0x180018108`
- `0x1800188e4`
- `0x180019238`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180082e90`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019299`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019299`

## string_xrefs

- `0x180019343`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019337`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed __int32 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendRdpData(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rbx
  int v6; // esi
  signed __int32 result; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v15; // rcx
  unsigned int v16; // eax
  char *v17; // [rsp+28h] [rbp-20h]
  __int64 v18; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v19; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<unsigned char>(
    a1,
    &v18,
    a3,
    *(_DWORD *)(a2 + 8));
  v5 = v18;
  memcpy_0(*(void **)(v18 + 16), *(const void **)a2, *(_QWORD *)(a2 + 8));
  v6 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
         *(unsigned __int8 **)(v5 + 16));
  if ( v6 < 0 )
  {
    v11 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v18);
    v12 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v11);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v13);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v15, Header);
    v16 = wil::verify_hresult<long>((unsigned int)v6);
    LODWORD(v17) = v12;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v16,
      (int)"Failed to commit event %d to shared memory",
      v17);
  }
  result = SetEvent(*(HANDLE *)(a1 + 112));
  if ( !result )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v8, v9);
  v10 = v19;
  if ( v19 )
  {
    result = _InterlockedDecrement(v19 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      result = _InterlockedDecrement(v10 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019238  mov     [rsp+arg_0], rbx
0x18001923d  mov     [rsp+arg_8], rsi
0x180019242  push    rdi
0x180019243  sub     rsp, 40h
0x180019247  mov     rsi, rdx
0x18001924a  mov     rdi, rcx
0x18001924d  cmp     byte ptr [rcx+90h], 0
0x180019254  jnz     short loc_18001925B
0x180019256  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001925b  mov     r9d, [rsi+8]
0x18001925f  lea     rdx, [rsp+48h+var_18]
0x180019264  mov     rcx, rdi
0x180019267  call    ??$AllocSharedBufEvent@E@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@E@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<uchar>(UMRDP_EVENT_TYPE,uint)
0x18001926c  nop
0x18001926d  mov     rbx, [rsp+48h+var_18]
0x180019272  mov     r8, [rsi+8]; Size
0x180019276  mov     rdx, [rsi]; Src
0x180019279  mov     rcx, [rbx+10h]; void *
0x18001927d  call    memcpy_0
0x180019282  mov     rdx, [rbx+10h]; unsigned __int8 *
0x180019286  mov     rcx, [rdi+68h]; this
0x18001928a  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x18001928f  mov     esi, eax
0x180019291  test    eax, eax
0x180019293  js      short loc_180019303
0x180019295  mov     rcx, [rdi+70h]; hEvent
0x180019299  call    cs:__imp_SetEvent
0x18001929f  mov     rcx, [rsp+48h]; this
0x1800192a4  test    eax, eax
0x1800192a6  jz      short loc_1800192F8
0x1800192a8  mov     rbx, [rsp+48h+var_10]
0x1800192ad  test    rbx, rbx
0x1800192b0  jz      short loc_1800192E8
0x1800192b2  or      edi, 0FFFFFFFFh
0x1800192b5  mov     eax, edi
0x1800192b7  lock xadd [rbx+8], eax
0x1800192bc  add     eax, edi
0x1800192be  jnz     short loc_1800192E8
0x1800192c0  mov     rax, [rbx]
0x1800192c3  mov     rcx, rbx
0x1800192c6  mov     rax, [rax]
0x1800192c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192ce  mov     eax, edi
0x1800192d0  lock xadd [rbx+0Ch], eax
0x1800192d5  add     eax, edi
0x1800192d7  jnz     short loc_1800192E8
0x1800192d9  mov     rax, [rbx]
0x1800192dc  mov     rcx, rbx
0x1800192df  mov     rax, [rax+8]
0x1800192e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192e8  mov     rbx, [rsp+48h+arg_0]
0x1800192ed  mov     rsi, [rsp+48h+arg_8]
0x1800192f2  add     rsp, 40h
0x1800192f6  pop     rdi
0x1800192f7  retn
0x1800192f8  mov     edx, 0A01h; void *
0x1800192fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019303  lea     rcx, [rsp+48h+var_18]
0x180019308  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x18001930d  mov     rcx, rax
0x180019310  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180019315  mov     ebx, [rax]
0x180019317  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x18001931c  mov     rdx, rax; unsigned __int8 *
0x18001931f  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180019324  mov     ecx, esi
0x180019326  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001932b  mov     r9d, eax; char *
0x18001932e  mov     rcx, [rsp+48h]; this
0x180019333  mov     dword ptr [rsp+48h+var_20], ebx; char *
0x180019337  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x18001933e  mov     qword ptr [rsp+48h+var_28], rax; int
0x180019343  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001934a  mov     edx, 14Dh; void *
0x18001934f  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
