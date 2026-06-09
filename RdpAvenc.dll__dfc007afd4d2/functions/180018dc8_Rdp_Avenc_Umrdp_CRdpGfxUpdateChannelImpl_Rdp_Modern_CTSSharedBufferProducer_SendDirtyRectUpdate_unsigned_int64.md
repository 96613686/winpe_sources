# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendDirtyRectUpdate(unsigned __int64,tagRECT const *)

- ea: `0x180018dc8`
- end: `0x180018ef8`
- name: `?SendDirtyRectUpdate@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAX_KPEBUtagRECT@@@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d9d0`
- `0x180020b44`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x1800156d0`
- `0x1800160b8`
- `0x180018108`
- `0x1800188e4`
- `0x18001893c`
- `0x180018dc8`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018e41`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018e41`

## string_xrefs

- `0x180018ee6`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180018eda`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed __int32 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendDirtyRectUpdate(
        __int64 a1,
        __int64 a2,
        _OWORD *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rbx
  int v8; // edi
  signed __int32 result; // eax
  unsigned int v10; // r8d
  const char *v11; // r9
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rax
  int v14; // ebx
  __int64 v15; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v17; // rcx
  unsigned int v18; // eax
  char *v19; // [rsp+28h] [rbp-40h]
  __int64 v20; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v21; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_INVALIDATE_RECT_EVENT>(
    a1,
    &v20);
  v6 = v20;
  v7 = *(_QWORD *)(v20 + 16);
  *(_DWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 20) = a2;
  *(_QWORD *)(v7 + 28) = a2;
  *(_QWORD *)(v7 + 52) = 0;
  *(_QWORD *)(v7 + 60) = Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::GetTimeHNS();
  *(_OWORD *)(v7 + 36) = *a3;
  v8 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
         *(unsigned __int8 **)(v6 + 16));
  if ( v8 < 0 )
  {
    v13 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v20);
    v14 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v13);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v15);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v17, Header);
    v18 = wil::verify_hresult<long>((unsigned int)v8);
    LODWORD(v19) = v14;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v18,
      (int)"Failed to commit event %d to shared memory",
      v19);
  }
  result = SetEvent(*(HANDLE *)(a1 + 112));
  if ( !result )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v10, v11);
  v12 = v21;
  if ( v21 )
  {
    result = _InterlockedDecrement(v21 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      result = _InterlockedDecrement(v12 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018dc8  push    rbx
0x180018dca  push    rbp
0x180018dcb  push    rsi
0x180018dcc  push    rdi
0x180018dcd  push    r14
0x180018dcf  sub     rsp, 40h
0x180018dd3  mov     r14, r8
0x180018dd6  mov     rbp, rdx
0x180018dd9  mov     rsi, rcx
0x180018ddc  cmp     byte ptr [rcx+90h], 0
0x180018de3  jnz     short loc_180018DEA
0x180018de5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018dea  lea     rdx, [rsp+68h+var_38]
0x180018def  mov     rcx, rsi
0x180018df2  call    ??$AllocSharedBufEvent@UUMRDP_INVALIDATE_RECT_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_INVALIDATE_RECT_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_INVALIDATE_RECT_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180018df7  nop
0x180018df8  mov     rdi, [rsp+68h+var_38]
0x180018dfd  mov     rbx, [rdi+10h]
0x180018e01  mov     dword ptr [rbx+10h], 0
0x180018e08  mov     [rbx+14h], rbp
0x180018e0c  mov     [rbx+1Ch], rbp
0x180018e10  mov     qword ptr [rbx+34h], 0
0x180018e18  call    ?GetTimeHNS@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_JXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::GetTimeHNS(void)
0x180018e1d  mov     [rbx+3Ch], rax
0x180018e21  movups  xmm0, xmmword ptr [r14]
0x180018e25  movdqu  xmmword ptr [rbx+24h], xmm0
0x180018e2a  mov     rdx, [rdi+10h]; unsigned __int8 *
0x180018e2e  mov     rcx, [rsi+68h]; this
0x180018e32  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180018e37  mov     edi, eax
0x180018e39  test    eax, eax
0x180018e3b  js      short loc_180018EA6
0x180018e3d  mov     rcx, [rsi+70h]; hEvent
0x180018e41  call    cs:__imp_SetEvent
0x180018e47  mov     rcx, [rsp+68h]; this
0x180018e4c  test    eax, eax
0x180018e4e  jz      short loc_180018E9B
0x180018e50  mov     rbx, [rsp+68h+var_30]
0x180018e55  test    rbx, rbx
0x180018e58  jz      short loc_180018E90
0x180018e5a  or      edi, 0FFFFFFFFh
0x180018e5d  mov     eax, edi
0x180018e5f  lock xadd [rbx+8], eax
0x180018e64  add     eax, edi
0x180018e66  jnz     short loc_180018E90
0x180018e68  mov     rax, [rbx]
0x180018e6b  mov     rcx, rbx
0x180018e6e  mov     rax, [rax]
0x180018e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e76  mov     eax, edi
0x180018e78  lock xadd [rbx+0Ch], eax
0x180018e7d  add     eax, edi
0x180018e7f  jnz     short loc_180018E90
0x180018e81  mov     rax, [rbx]
0x180018e84  mov     rcx, rbx
0x180018e87  mov     rax, [rax+8]
0x180018e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e90  add     rsp, 40h
0x180018e94  pop     r14
0x180018e96  pop     rdi
0x180018e97  pop     rsi
0x180018e98  pop     rbp
0x180018e99  pop     rbx
0x180018e9a  retn
0x180018e9b  mov     edx, 0A01h; void *
0x180018ea0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018ea6  lea     rcx, [rsp+68h+var_38]
0x180018eab  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x180018eb0  mov     rcx, rax
0x180018eb3  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180018eb8  mov     ebx, [rax]
0x180018eba  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180018ebf  mov     rdx, rax; unsigned __int8 *
0x180018ec2  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180018ec7  mov     ecx, edi
0x180018ec9  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180018ece  mov     r9d, eax; char *
0x180018ed1  mov     rcx, [rsp+68h]; this
0x180018ed6  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x180018eda  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x180018ee1  mov     qword ptr [rsp+68h+var_48], rax; int
0x180018ee6  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180018eed  mov     edx, 14Dh; void *
0x180018ef2  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
