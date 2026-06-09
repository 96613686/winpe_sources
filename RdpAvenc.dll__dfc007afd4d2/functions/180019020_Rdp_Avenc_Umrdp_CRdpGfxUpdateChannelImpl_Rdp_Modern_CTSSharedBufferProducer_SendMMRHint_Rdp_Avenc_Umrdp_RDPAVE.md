# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMMRHint(Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_MMR_DATA * const)

- ea: `0x180019020`
- end: `0x180019230`
- name: `?SendMMRHint@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXQEAU_RDPAVENC_OPCODE_MMR_DATA@234@@Z`
- size: `528`
- prototype: `signed __int32 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012950`

## callees

- `0x180001008`
- `0x1800080cc`
- `0x18000b07c`
- `0x1800156d0`
- `0x18001689c`
- `0x180018108`
- `0x1800188e4`
- `0x180019020`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019181`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019181`

## string_xrefs

- `0x180019106`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x18001911d`: `Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::SendMMRHint`
- `0x180019216`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
signed __int32 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMMRHint(
        __int64 a1,
        __int64 a2)
{
  int v4; // r9d
  __int64 v5; // rsi
  __int64 v6; // rcx
  _OWORD *v7; // rcx
  _OWORD *v8; // rax
  __int64 v9; // rdx
  int v10; // edi
  signed __int32 result; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  int v16; // ebx
  __int64 v17; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v19; // rcx
  unsigned int v20; // eax
  char *v21; // [rsp+28h] [rbp-28h]
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF
  volatile signed __int32 *v23; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v25; // [rsp+80h] [rbp+30h] BYREF
  const char *v26; // [rsp+88h] [rbp+38h] BYREF
  const char *v27; // [rsp+90h] [rbp+40h] BYREF
  const char *v28; // [rsp+98h] [rbp+48h] BYREF

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_VIDEO_HINT_EVENT>(
    a1,
    &v22);
  v5 = v22;
  v6 = *(_QWORD *)(v22 + 16);
  *(_QWORD *)(v6 + 20) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(v6 + 28) = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(v6 + 36) = *(_DWORD *)(a2 + 32);
  *(_DWORD *)(v6 + 40) = *(_DWORD *)(a2 + 36);
  *(_DWORD *)(v6 + 44) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(v6 + 48) = *(_DWORD *)(a2 + 44);
  *(_DWORD *)(v6 + 52) = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(v6 + 56) = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(v6 + 60) = *(_DWORD *)(a2 + 56);
  *(_DWORD *)(v6 + 64) = *(_DWORD *)(a2 + 60);
  v7 = (_OWORD *)(v6 + 68);
  v8 = (_OWORD *)(a2 + 64);
  v9 = 8;
  do
  {
    *v7 = *v8;
    v7[1] = v8[1];
    v7[2] = v8[2];
    v7[3] = v8[3];
    v7[4] = v8[4];
    v7[5] = v8[5];
    v7[6] = v8[6];
    v7[7] = v8[7];
    v7 += 8;
    v8 += 8;
    --v9;
  }
  while ( v9 );
  *v7 = *v8;
  *((_QWORD *)v7 + 2) = *((_QWORD *)v8 + 2);
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v26 = "Send UMRDP_MMR_DATA";
    v27 = "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::SendMMRHint";
    v25 = 766;
    v28 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800ACACA,
      128,
      v4,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)&v27,
      (__int64)&v26);
  }
  v10 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
          *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
          *(unsigned __int8 **)(v5 + 16));
  if ( v10 < 0 )
  {
    v15 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v22);
    v16 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v15);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v17);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v19, Header);
    v20 = wil::verify_hresult<long>((unsigned int)v10);
    LODWORD(v21) = v16;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v20,
      (int)"Failed to commit event %d to shared memory",
      v21);
  }
  result = SetEvent(*(HANDLE *)(a1 + 112));
  if ( !result )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v12, v13);
  v14 = v23;
  if ( v23 )
  {
    result = _InterlockedDecrement(v23 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      result = _InterlockedDecrement(v14 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019020  push    rbp
0x180019022  push    rbx
0x180019023  push    rsi
0x180019024  push    rdi
0x180019025  push    r14
0x180019027  mov     rbp, rsp
0x18001902a  sub     rsp, 50h
0x18001902e  mov     rdi, rdx
0x180019031  mov     rbx, rcx
0x180019034  cmp     byte ptr [rcx+90h], 0
0x18001903b  jnz     short loc_180019042
0x18001903d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019042  lea     rdx, [rbp+var_10]
0x180019046  mov     rcx, rbx
0x180019049  call    ??$AllocSharedBufEvent@UUMRDP_VIDEO_HINT_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_VIDEO_HINT_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_VIDEO_HINT_EVENT>(UMRDP_EVENT_TYPE,uint)
0x18001904e  nop
0x18001904f  mov     rsi, [rbp+var_10]
0x180019053  mov     rcx, [rsi+10h]
0x180019057  mov     rax, [rdi+10h]
0x18001905b  mov     [rcx+14h], rax
0x18001905f  mov     rax, [rdi+18h]
0x180019063  mov     [rcx+1Ch], rax
0x180019067  mov     eax, [rdi+20h]
0x18001906a  mov     [rcx+24h], eax
0x18001906d  mov     eax, [rdi+24h]
0x180019070  mov     [rcx+28h], eax
0x180019073  mov     eax, [rdi+28h]
0x180019076  mov     [rcx+2Ch], eax
0x180019079  mov     eax, [rdi+2Ch]
0x18001907c  mov     [rcx+30h], eax
0x18001907f  mov     eax, [rdi+30h]
0x180019082  mov     [rcx+34h], eax
0x180019085  mov     eax, [rdi+34h]
0x180019088  mov     [rcx+38h], eax
0x18001908b  mov     eax, [rdi+38h]
0x18001908e  mov     [rcx+3Ch], eax
0x180019091  mov     eax, [rdi+3Ch]
0x180019094  mov     [rcx+40h], eax
0x180019097  add     rcx, 44h ; 'D'
0x18001909b  lea     rax, [rdi+40h]
0x18001909f  mov     edx, 8
0x1800190a4  lea     r8d, [rdx+78h]
0x1800190a8  movups  xmm0, xmmword ptr [rax]
0x1800190ab  movups  xmmword ptr [rcx], xmm0
0x1800190ae  movups  xmm1, xmmword ptr [rax+10h]
0x1800190b2  movups  xmmword ptr [rcx+10h], xmm1
0x1800190b6  movups  xmm0, xmmword ptr [rax+20h]
0x1800190ba  movups  xmmword ptr [rcx+20h], xmm0
0x1800190be  movups  xmm1, xmmword ptr [rax+30h]
0x1800190c2  movups  xmmword ptr [rcx+30h], xmm1
0x1800190c6  movups  xmm0, xmmword ptr [rax+40h]
0x1800190ca  movups  xmmword ptr [rcx+40h], xmm0
0x1800190ce  movups  xmm1, xmmword ptr [rax+50h]
0x1800190d2  movups  xmmword ptr [rcx+50h], xmm1
0x1800190d6  movups  xmm0, xmmword ptr [rax+60h]
0x1800190da  movups  xmmword ptr [rcx+60h], xmm0
0x1800190de  movups  xmm1, xmmword ptr [rax+70h]
0x1800190e2  movups  xmmword ptr [rcx+70h], xmm1
0x1800190e6  add     rcx, r8
0x1800190e9  add     rax, r8
0x1800190ec  sub     rdx, 1
0x1800190f0  jnz     short loc_1800190A8
0x1800190f2  movups  xmm0, xmmword ptr [rax]
0x1800190f5  movups  xmmword ptr [rcx], xmm0
0x1800190f8  mov     rax, [rax+10h]
0x1800190fc  mov     [rcx+10h], rax
0x180019100  mov     eax, cs:dword_1800C1058
0x180019106  lea     r14, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001910d  cmp     eax, 5
0x180019110  jbe     short loc_18001916A
0x180019112  lea     rax, aSendUmrdpMmrDa; "Send UMRDP_MMR_DATA"
0x180019119  mov     [rbp+arg_8], rax
0x18001911d  lea     rax, aRdpAvencUmrdpC_34; "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannel"...
0x180019124  mov     [rbp+arg_10], rax
0x180019128  mov     [rbp+arg_0], 2FEh
0x18001912f  mov     [rbp+arg_18], r14
0x180019133  lea     rax, [rbp+arg_8]
0x180019137  mov     [rsp+50h+var_18], rax
0x18001913c  lea     rax, [rbp+arg_10]
0x180019140  mov     [rsp+50h+var_20], rax
0x180019145  lea     rax, [rbp+arg_0]
0x180019149  mov     [rsp+50h+var_28], rax
0x18001914e  lea     rax, [rbp+arg_18]
0x180019152  mov     qword ptr [rsp+50h+var_30], rax
0x180019157  lea     rdx, word_1800ACACA
0x18001915e  lea     rcx, dword_1800C1058
0x180019165  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001916a  mov     rdx, [rsi+10h]; unsigned __int8 *
0x18001916e  mov     rcx, [rbx+68h]; this
0x180019172  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180019177  mov     edi, eax
0x180019179  test    eax, eax
0x18001917b  js      short loc_1800191E4
0x18001917d  mov     rcx, [rbx+70h]; hEvent
0x180019181  call    cs:__imp_SetEvent
0x180019187  mov     rcx, [rbp+28h]; this
0x18001918b  test    eax, eax
0x18001918d  jz      short loc_1800191D9
0x18001918f  mov     rbx, [rbp+var_8]
0x180019193  test    rbx, rbx
0x180019196  jz      short loc_1800191CE
0x180019198  or      edi, 0FFFFFFFFh
0x18001919b  mov     eax, edi
0x18001919d  lock xadd [rbx+8], eax
0x1800191a2  add     eax, edi
0x1800191a4  jnz     short loc_1800191CE
0x1800191a6  mov     rax, [rbx]
0x1800191a9  mov     rcx, rbx
0x1800191ac  mov     rax, [rax]
0x1800191af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191b4  mov     eax, edi
0x1800191b6  lock xadd [rbx+0Ch], eax
0x1800191bb  add     eax, edi
0x1800191bd  jnz     short loc_1800191CE
0x1800191bf  mov     rax, [rbx]
0x1800191c2  mov     rcx, rbx
0x1800191c5  mov     rax, [rax+8]
0x1800191c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191ce  add     rsp, 50h
0x1800191d2  pop     r14
0x1800191d4  pop     rdi
0x1800191d5  pop     rsi
0x1800191d6  pop     rbx
0x1800191d7  pop     rbp
0x1800191d8  retn
0x1800191d9  mov     edx, 0A01h; void *
0x1800191de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800191e4  lea     rcx, [rbp+var_10]
0x1800191e8  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x1800191ed  mov     rcx, rax
0x1800191f0  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800191f5  mov     ebx, [rax]
0x1800191f7  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800191fc  mov     rdx, rax; unsigned __int8 *
0x1800191ff  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180019204  mov     ecx, edi
0x180019206  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001920b  mov     r9d, eax; char *
0x18001920e  mov     rcx, [rbp+28h]; this
0x180019212  mov     dword ptr [rsp+50h+var_28], ebx; char *
0x180019216  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x18001921d  mov     qword ptr [rsp+50h+var_30], rax; int
0x180019222  mov     r8, r14; unsigned int
0x180019225  mov     edx, 14Dh; void *
0x18001922a  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
