# Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessTagFrame(Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TAG_FRAME_REQ * const)

- ea: `0x180013878`
- end: `0x180013a05`
- name: `?ProcessTagFrame@CUmrdpProcessor@Umrdp@Avenc@Rdp@@AEAAXQEAU_RDPAVENC_OPCODE_TAG_FRAME_REQ@234@@Z`
- size: `397`
- prototype: `void __fastcall(Rdp::Avenc::Umrdp::CUmrdpProcessor *__hidden this, struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TAG_FRAME_REQ *const)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012950`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x180013878`
- `0x1800146bc`
- `0x1800156d0`
- `0x1800164a0`
- `0x180018108`
- `0x1800188e4`
- `0x1800199cc`
- `0x180019c04`
- `0x180019c10`
- `0x180019df0`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013941`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013941`

## string_xrefs

- `0x18001389d`: `Gfx update channel is not initialized`
- `0x1800139f3`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x1800139e7`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessTagFrame(
        Rdp::Avenc::Umrdp::CUmrdpProcessor *this,
        struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TAG_FRAME_REQ *const a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  const char *v6; // rdx
  _OWORD *v7; // rax
  int v8; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  volatile signed __int32 *v11; // rdi
  __int64 v12; // rax
  int v13; // ebx
  __int64 v14; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v16; // rcx
  unsigned int v17; // eax
  int v18; // [rsp+20h] [rbp-28h]
  char *v19; // [rsp+28h] [rbp-20h]
  const char *v20; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v21; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LOBYTE(v18) = *((_QWORD *)this + 17) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x313,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
    (const char *)0x80070057LL,
    v18,
    (bool)"Gfx update channel is not initialized",
    v20);
  v4 = *((_QWORD *)this + 17);
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(v4, 1500);
  v5 = *((_QWORD *)this + 17);
  if ( !*(_BYTE *)(v5 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_TAG_FRAME_EVENT>(
    v5,
    &v20);
  v6 = v20;
  v7 = (_OWORD *)*((_QWORD *)v20 + 2);
  v7[1] = *(_OWORD *)((char *)a2 + 12);
  v7[2] = *(_OWORD *)((char *)a2 + 28);
  v7[3] = *(_OWORD *)((char *)a2 + 44);
  v7[4] = *(_OWORD *)((char *)a2 + 60);
  v8 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(v5 + 104),
         *((unsigned __int8 **)v6 + 2));
  if ( v8 < 0 )
  {
    v12 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v20);
    v13 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v12);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v14);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v16, Header);
    v17 = wil::verify_hresult<long>((unsigned int)v8);
    LODWORD(v19) = v13;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v17,
      (int)"Failed to commit event %d to shared memory",
      v19);
  }
  if ( !SetEvent(*(HANDLE *)(v5 + 112)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
  v11 = v21;
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(v4);
}

```

## disassembly

```asm
0x180013878  mov     [rsp+arg_8], rbx
0x18001387d  mov     [rsp+arg_10], rsi
0x180013882  push    rdi
0x180013883  sub     rsp, 40h
0x180013887  mov     rsi, rdx
0x18001388a  mov     rdi, rcx
0x18001388d  cmp     qword ptr [rcx+88h], 0
0x180013895  setz    al
0x180013898  mov     rcx, [rsp+48h]; this
0x18001389d  lea     rdx, aGfxUpdateChann; "Gfx update channel is not initialized"
0x1800138a4  mov     [rsp+48h+var_20], rdx; bool
0x1800138a9  mov     byte ptr [rsp+48h+var_28], al; int
0x1800138ad  mov     r9d, 80070057h; char *
0x1800138b3  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800138ba  mov     edx, 313h; void *
0x1800138bf  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800138c4  mov     rbx, [rdi+88h]
0x1800138cb  mov     [rsp+48h+arg_0], rbx
0x1800138d0  mov     edx, 5DCh
0x1800138d5  mov     rcx, rbx
0x1800138d8  call    ?lock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(uint)
0x1800138dd  nop
0x1800138de  mov     rdi, [rdi+88h]
0x1800138e5  cmp     byte ptr [rdi+90h], 0
0x1800138ec  jnz     short loc_1800138F3
0x1800138ee  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800138f3  lea     rdx, [rsp+48h+var_18]
0x1800138f8  mov     rcx, rdi
0x1800138fb  call    ??$AllocSharedBufEvent@UUMRDP_TAG_FRAME_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_TAG_FRAME_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_TAG_FRAME_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180013900  nop
0x180013901  mov     rdx, [rsp+48h+var_18]
0x180013906  mov     rax, [rdx+10h]
0x18001390a  movups  xmm0, xmmword ptr [rsi+0Ch]
0x18001390e  movups  xmmword ptr [rax+10h], xmm0
0x180013912  movups  xmm1, xmmword ptr [rsi+1Ch]
0x180013916  movups  xmmword ptr [rax+20h], xmm1
0x18001391a  movups  xmm0, xmmword ptr [rsi+2Ch]
0x18001391e  movups  xmmword ptr [rax+30h], xmm0
0x180013922  movups  xmm1, xmmword ptr [rsi+3Ch]
0x180013926  movups  xmmword ptr [rax+40h], xmm1
0x18001392a  mov     rdx, [rdx+10h]; unsigned __int8 *
0x18001392e  mov     rcx, [rdi+68h]; this
0x180013932  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180013937  mov     esi, eax
0x180013939  test    eax, eax
0x18001393b  js      short loc_1800139B3
0x18001393d  mov     rcx, [rdi+70h]; hEvent
0x180013941  call    cs:__imp_SetEvent
0x180013947  mov     rcx, [rsp+48h]; this
0x18001394c  test    eax, eax
0x18001394e  jz      short loc_1800139A8
0x180013950  mov     rdi, [rsp+48h+var_10]
0x180013955  test    rdi, rdi
0x180013958  jz      short loc_180013991
0x18001395a  or      esi, 0FFFFFFFFh
0x18001395d  mov     eax, esi
0x18001395f  lock xadd [rdi+8], eax
0x180013964  add     eax, esi
0x180013966  jnz     short loc_180013991
0x180013968  mov     rax, [rdi]
0x18001396b  mov     rcx, rdi
0x18001396e  mov     rax, [rax]
0x180013971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013976  mov     eax, esi
0x180013978  lock xadd [rdi+0Ch], eax
0x18001397d  add     eax, esi
0x18001397f  jnz     short loc_180013991
0x180013981  mov     rax, [rdi]
0x180013984  mov     rcx, rdi
0x180013987  mov     rax, [rax+8]
0x18001398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013990  nop
0x180013991  mov     rcx, rbx
0x180013994  mov     rbx, [rsp+48h+arg_8]
0x180013999  mov     rsi, [rsp+48h+arg_10]
0x18001399e  add     rsp, 40h
0x1800139a2  pop     rdi
0x1800139a3  jmp     ?unlock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(void)
0x1800139a8  mov     edx, 0A01h; void *
0x1800139ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800139b3  lea     rcx, [rsp+48h+var_18]
0x1800139b8  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x1800139bd  mov     rcx, rax
0x1800139c0  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800139c5  mov     ebx, [rax]
0x1800139c7  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800139cc  mov     rdx, rax; unsigned __int8 *
0x1800139cf  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x1800139d4  mov     ecx, esi
0x1800139d6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800139db  mov     r9d, eax; char *
0x1800139de  mov     rcx, [rsp+48h]; this
0x1800139e3  mov     dword ptr [rsp+48h+var_20], ebx; char *
0x1800139e7  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x1800139ee  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800139f3  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800139fa  mov     edx, 14Dh; void *
0x1800139ff  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
