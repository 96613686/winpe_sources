# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendSurfaceCreate(std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedSurface> const &)

- ea: `0x18001935c`
- end: `0x180019599`
- name: `?SendSurfaceCreate@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXAEBV?$shared_ptr@VCRdpSharedSurface@Umrdp@Avenc@Rdp@@@std@@@Z`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001e620`
- `0x180020850`

## callees

- `0x1800080cc`
- `0x18000abb8`
- `0x18000b07c`
- `0x18000e848`
- `0x1800156d0`
- `0x180015ad8`
- `0x1800162b4`
- `0x180016e98`
- `0x180018108`
- `0x1800188e4`
- `0x18001935c`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019462`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019462`

## string_xrefs

- `0x180019436`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019587`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019427`: `Failed to copy pszSurfaceName`
- `0x18001957b`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendSurfaceCreate(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdx
  _QWORD *v6; // rax
  unsigned int v7; // eax
  int v8; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rdx
  __int64 result; // rax
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  int v16; // ebx
  __int64 v17; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v19; // rcx
  unsigned int v20; // eax
  char *v21; // [rsp+28h] [rbp-30h]
  char *v22; // [rsp+28h] [rbp-30h]
  __int64 v23; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v24; // [rsp+38h] [rbp-20h]
  __int64 v25; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>(
    a1,
    &v25);
  v4 = v25;
  v5 = *(_QWORD *)(v25 + 16);
  *(_DWORD *)(v5 + 144) = *(_DWORD *)(*(_QWORD *)a2 + 184LL);
  *(_DWORD *)(v5 + 148) = *(_DWORD *)(*(_QWORD *)a2 + 76LL);
  *(_DWORD *)(v5 + 152) = *(_DWORD *)(*(_QWORD *)a2 + 72LL);
  *(_DWORD *)(v5 + 156) = *(_DWORD *)(*(_QWORD *)a2 + 80LL);
  *(_QWORD *)(v5 + 160) = *(_QWORD *)(*(_QWORD *)a2 + 64LL);
  *(_QWORD *)(v5 + 168) = 0;
  *(_DWORD *)(v5 + 176) = *(_DWORD *)(*(_QWORD *)a2 + 84LL);
  v6 = (_QWORD *)(*(_QWORD *)a2 + 152LL);
  if ( *(_QWORD *)(*(_QWORD *)a2 + 176LL) > 7u )
    v6 = (_QWORD *)*v6;
  v7 = StringCchPrintfW((unsigned __int16 *)(v5 + 16), 0x40u, L"%s%s", L"Global\\", v6);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x196,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)v7,
    (int)"Failed to copy pszSurfaceName",
    v21);
  v8 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
         *(unsigned __int8 **)(v4 + 16));
  if ( v8 < 0 )
  {
    v15 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v25);
    v16 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v15);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v17);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v19, Header);
    v20 = wil::verify_hresult<long>((unsigned int)v8);
    LODWORD(v22) = v16;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v20,
      (int)"Failed to commit event %d to shared memory",
      v22);
  }
  if ( !SetEvent(*(HANDLE *)(a1 + 112)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(
    a1,
    &v23);
  v11 = *(_QWORD *)(v23 + 16);
  *(_DWORD *)(v11 + 16) = *(_DWORD *)(*(_QWORD *)a2 + 56LL);
  *(_QWORD *)(v11 + 20) = *(_QWORD *)(*(_QWORD *)a2 + 64LL);
  result = Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::CommitSharedBufferEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(
             a1,
             &v23);
  v13 = v24;
  if ( v24 )
  {
    result = (unsigned int)_InterlockedDecrement(v24 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      result = (unsigned int)_InterlockedDecrement(v13 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = v26;
  if ( v26 )
  {
    result = (unsigned int)_InterlockedDecrement(v26 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      result = (unsigned int)_InterlockedDecrement(v14 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001935c  mov     [rsp+arg_0], rbx
0x180019361  mov     [rsp+arg_8], rsi
0x180019366  push    rdi
0x180019367  sub     rsp, 50h
0x18001936b  mov     rdi, rdx
0x18001936e  mov     rbx, rcx
0x180019371  cmp     byte ptr [rcx+90h], 0
0x180019378  jnz     short loc_18001937F
0x18001937a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001937f  lea     rdx, [rsp+58h+var_18]
0x180019384  mov     rcx, rbx
0x180019387  call    ??$AllocSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>(UMRDP_EVENT_TYPE,uint)
0x18001938c  nop
0x18001938d  mov     rsi, [rsp+58h+var_18]
0x180019392  mov     rdx, [rsi+10h]
0x180019396  mov     rax, [rdi]
0x180019399  mov     ecx, [rax+0B8h]
0x18001939f  mov     [rdx+90h], ecx
0x1800193a5  mov     rax, [rdi]
0x1800193a8  mov     ecx, [rax+4Ch]
0x1800193ab  mov     [rdx+94h], ecx
0x1800193b1  mov     rax, [rdi]
0x1800193b4  mov     ecx, [rax+48h]
0x1800193b7  mov     [rdx+98h], ecx
0x1800193bd  mov     rax, [rdi]
0x1800193c0  mov     ecx, [rax+50h]
0x1800193c3  mov     [rdx+9Ch], ecx
0x1800193c9  mov     rax, [rdi]
0x1800193cc  mov     rcx, [rax+40h]
0x1800193d0  mov     [rdx+0A0h], rcx
0x1800193d7  mov     qword ptr [rdx+0A8h], 0
0x1800193e2  mov     rax, [rdi]
0x1800193e5  mov     ecx, [rax+54h]
0x1800193e8  mov     [rdx+0B0h], ecx
0x1800193ee  mov     rax, [rdi]
0x1800193f1  add     rax, 98h
0x1800193f7  cmp     qword ptr [rax+18h], 7
0x1800193fc  jbe     short loc_180019401
0x1800193fe  mov     rax, [rax]
0x180019401  lea     rcx, [rdx+10h]; unsigned __int16 *
0x180019405  mov     qword ptr [rsp+58h+var_38], rax
0x18001940a  lea     r9, aGlobal; "Global\\"
0x180019411  lea     r8, aSS; "%s%s"
0x180019418  mov     edx, 40h ; '@'; unsigned __int64
0x18001941d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019422  mov     rcx, [rsp+58h]; this
0x180019427  lea     rdx, aFailedToCopyPs; "Failed to copy pszSurfaceName"
0x18001942e  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180019433  mov     r9d, eax; char *
0x180019436  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001943d  mov     edx, 196h; void *
0x180019442  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180019447  mov     rdx, [rsi+10h]; unsigned __int8 *
0x18001944b  mov     rcx, [rbx+68h]; this
0x18001944f  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180019454  mov     esi, eax
0x180019456  test    eax, eax
0x180019458  js      loc_180019547
0x18001945e  mov     rcx, [rbx+70h]; hEvent
0x180019462  call    cs:__imp_SetEvent
0x180019468  mov     rcx, [rsp+58h]; this
0x18001946d  test    eax, eax
0x18001946f  jz      loc_18001953C
0x180019475  lea     rdx, [rsp+58h+var_28]
0x18001947a  mov     rcx, rbx
0x18001947d  call    ??$AllocSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180019482  nop
0x180019483  mov     rax, [rsp+58h+var_28]
0x180019488  mov     rdx, [rax+10h]
0x18001948c  mov     rax, [rdi]
0x18001948f  mov     ecx, [rax+38h]
0x180019492  mov     [rdx+10h], ecx
0x180019495  mov     rax, [rdi]
0x180019498  mov     rcx, [rax+40h]
0x18001949c  mov     [rdx+14h], rcx
0x1800194a0  lea     rdx, [rsp+58h+var_28]
0x1800194a5  mov     rcx, rbx
0x1800194a8  call    ??$CommitSharedBufferEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAAXAEBV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@Umrdp@Avenc@Rdp@@@std@@@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::CommitSharedBufferEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>> const &)
0x1800194ad  nop
0x1800194ae  or      edi, 0FFFFFFFFh
0x1800194b1  mov     rbx, [rsp+58h+var_20]
0x1800194b6  test    rbx, rbx
0x1800194b9  jz      short loc_1800194EF
0x1800194bb  mov     eax, edi
0x1800194bd  lock xadd [rbx+8], eax
0x1800194c2  add     eax, edi
0x1800194c4  jnz     short loc_1800194EF
0x1800194c6  mov     rax, [rbx]
0x1800194c9  mov     rcx, rbx
0x1800194cc  mov     rax, [rax]
0x1800194cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194d4  mov     eax, edi
0x1800194d6  lock xadd [rbx+0Ch], eax
0x1800194db  add     eax, edi
0x1800194dd  jnz     short loc_1800194EF
0x1800194df  mov     rax, [rbx]
0x1800194e2  mov     rcx, rbx
0x1800194e5  mov     rax, [rax+8]
0x1800194e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194ee  nop
0x1800194ef  mov     rbx, [rsp+58h+var_10]
0x1800194f4  test    rbx, rbx
0x1800194f7  jz      short loc_18001952C
0x1800194f9  mov     eax, edi
0x1800194fb  lock xadd [rbx+8], eax
0x180019500  add     eax, edi
0x180019502  jnz     short loc_18001952C
0x180019504  mov     rax, [rbx]
0x180019507  mov     rcx, rbx
0x18001950a  mov     rax, [rax]
0x18001950d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019512  mov     eax, edi
0x180019514  lock xadd [rbx+0Ch], eax
0x180019519  add     eax, edi
0x18001951b  jnz     short loc_18001952C
0x18001951d  mov     rax, [rbx]
0x180019520  mov     rcx, rbx
0x180019523  mov     rax, [rax+8]
0x180019527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001952c  mov     rbx, [rsp+58h+arg_0]
0x180019531  mov     rsi, [rsp+58h+arg_8]
0x180019536  add     rsp, 50h
0x18001953a  pop     rdi
0x18001953b  retn
0x18001953c  mov     edx, 0A01h; void *
0x180019541  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019547  lea     rcx, [rsp+58h+var_18]
0x18001954c  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x180019551  mov     rcx, rax
0x180019554  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180019559  mov     ebx, [rax]
0x18001955b  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180019560  mov     rdx, rax; unsigned __int8 *
0x180019563  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180019568  mov     ecx, esi
0x18001956a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001956f  mov     r9d, eax; char *
0x180019572  mov     rcx, [rsp+58h]; this
0x180019577  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18001957b  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x180019582  mov     qword ptr [rsp+58h+var_38], rax; int
0x180019587  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001958e  mov     edx, 14Dh; void *
0x180019593  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
