# Rdp::Avenc::Umrdp::CRdpSurface::SendDelete(void)

- ea: `0x180020a08`
- end: `0x180020b3d`
- name: `?SendDelete@CRdpSurface@Umrdp@Avenc@Rdp@@QEAAXXZ`
- size: `309`
- prototype: `void __fastcall(Rdp::Avenc::Umrdp::CRdpSurface *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d290`
- `0x18001d494`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x1800156d0`
- `0x180015cd8`
- `0x180018108`
- `0x1800188e4`
- `0x1800199cc`
- `0x180019c04`
- `0x180019c10`
- `0x180019df0`
- `0x180020a08`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020a79`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020a79`

## string_xrefs

- `0x180020b2b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180020b1f`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Rdp::Avenc::Umrdp::CRdpSurface::SendDelete(Rdp::Avenc::Umrdp::CRdpSurface *this)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // rdx
  int v6; // edi
  unsigned int v7; // r8d
  const char *v8; // r9
  volatile signed __int32 *v9; // rdi
  __int64 v10; // rax
  int v11; // ebx
  __int64 v12; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v14; // rcx
  unsigned int v15; // eax
  char *v16; // [rsp+28h] [rbp-20h]
  __int64 v17; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v18; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)this + 4);
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(v2, 0x5DCu);
  v3 = *((_QWORD *)this + 4);
  v4 = *((_QWORD *)this + 8);
  if ( !*(_BYTE *)(v3 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_DELETE_SURFACE_EVENT>(
    v3,
    &v17);
  v5 = v17;
  *(_QWORD *)(*(_QWORD *)(v17 + 16) + 16LL) = v4;
  v6 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(v3 + 104),
         *(unsigned __int8 **)(v5 + 16));
  if ( v6 < 0 )
  {
    v10 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v17);
    v11 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v10);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v12);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v14, Header);
    v15 = wil::verify_hresult<long>((unsigned int)v6);
    LODWORD(v16) = v11;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v15,
      (int)"Failed to commit event %d to shared memory",
      v16);
  }
  if ( !SetEvent(*(HANDLE *)(v3 + 112)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
  v9 = v18;
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(v2);
}

```

## disassembly

```asm
0x180020a08  mov     [rsp+arg_8], rbx
0x180020a0d  mov     [rsp+arg_10], rsi
0x180020a12  push    rdi
0x180020a13  sub     rsp, 40h
0x180020a17  mov     rdi, rcx
0x180020a1a  mov     rbx, [rcx+20h]
0x180020a1e  mov     [rsp+48h+arg_0], rbx
0x180020a23  mov     edx, 5DCh
0x180020a28  mov     rcx, rbx
0x180020a2b  call    ?lock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(uint)
0x180020a30  nop
0x180020a31  mov     rsi, [rdi+20h]
0x180020a35  mov     rdi, [rdi+40h]
0x180020a39  cmp     byte ptr [rsi+90h], 0
0x180020a40  jnz     short loc_180020A47
0x180020a42  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020a47  lea     rdx, [rsp+48h+var_18]
0x180020a4c  mov     rcx, rsi
0x180020a4f  call    ??$AllocSharedBufEvent@UUMRDP_DELETE_SURFACE_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_DELETE_SURFACE_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_DELETE_SURFACE_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180020a54  nop
0x180020a55  mov     rdx, [rsp+48h+var_18]
0x180020a5a  mov     rax, [rdx+10h]
0x180020a5e  mov     [rax+10h], rdi
0x180020a62  mov     rdx, [rdx+10h]; unsigned __int8 *
0x180020a66  mov     rcx, [rsi+68h]; this
0x180020a6a  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180020a6f  mov     edi, eax
0x180020a71  test    eax, eax
0x180020a73  js      short loc_180020AEB
0x180020a75  mov     rcx, [rsi+70h]; hEvent
0x180020a79  call    cs:__imp_SetEvent
0x180020a7f  mov     rcx, [rsp+48h]; this
0x180020a84  test    eax, eax
0x180020a86  jz      short loc_180020AE0
0x180020a88  mov     rdi, [rsp+48h+var_10]
0x180020a8d  test    rdi, rdi
0x180020a90  jz      short loc_180020AC9
0x180020a92  or      esi, 0FFFFFFFFh
0x180020a95  mov     eax, esi
0x180020a97  lock xadd [rdi+8], eax
0x180020a9c  add     eax, esi
0x180020a9e  jnz     short loc_180020AC9
0x180020aa0  mov     rax, [rdi]
0x180020aa3  mov     rcx, rdi
0x180020aa6  mov     rax, [rax]
0x180020aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aae  mov     eax, esi
0x180020ab0  lock xadd [rdi+0Ch], eax
0x180020ab5  add     eax, esi
0x180020ab7  jnz     short loc_180020AC9
0x180020ab9  mov     rax, [rdi]
0x180020abc  mov     rcx, rdi
0x180020abf  mov     rax, [rax+8]
0x180020ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ac8  nop
0x180020ac9  mov     rcx, rbx
0x180020acc  mov     rbx, [rsp+48h+arg_8]
0x180020ad1  mov     rsi, [rsp+48h+arg_10]
0x180020ad6  add     rsp, 40h
0x180020ada  pop     rdi
0x180020adb  jmp     ?unlock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(void)
0x180020ae0  mov     edx, 0A01h; void *
0x180020ae5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020aeb  lea     rcx, [rsp+48h+var_18]
0x180020af0  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x180020af5  mov     rcx, rax
0x180020af8  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180020afd  mov     ebx, [rax]
0x180020aff  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180020b04  mov     rdx, rax; unsigned __int8 *
0x180020b07  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180020b0c  mov     ecx, edi
0x180020b0e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180020b13  mov     r9d, eax; char *
0x180020b16  mov     rcx, [rsp+48h]; this
0x180020b1b  mov     dword ptr [rsp+48h+var_20], ebx; char *
0x180020b1f  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x180020b26  mov     qword ptr [rsp+48h+var_28], rax; int
0x180020b2b  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180020b32  mov     edx, 14Dh; void *
0x180020b37  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
