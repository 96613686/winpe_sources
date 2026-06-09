# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x1800162b4`
- end: `0x180016499`
- name: `??$AllocSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001935c`
- `0x1800195a0`

## callees

- `0x1800065a4`
- `0x18000b07c`
- `0x1800146bc`
- `0x1800162b4`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800162f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800162f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001635f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001635f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016356`

## string_xrefs

- `0x180016334`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180016379`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(
        __int64 a1,
        _QWORD *a2)
{
  int v2; // ebx
  int v5; // eax
  unsigned __int8 *v6; // rdi
  unsigned int v7; // r8d
  const char *v8; // r9
  char *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // r8
  volatile signed __int32 *v15; // rdx
  int v17; // [rsp+20h] [rbp-48h]
  const char *v18; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int8 *v20; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  v20 = 0;
  while ( 1 )
  {
    v5 = Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(
           *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
           0x1Cu,
           &v20);
    v6 = v20;
    if ( v5 >= 0 )
      break;
    if ( !(unsigned __int8)Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(a1)
      && !SetEvent(*(HANDLE *)(a1 + 112)) )
    {
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
    }
    if ( (unsigned int)++v2 >= 8 )
      goto LABEL_8;
  }
  *(_OWORD *)v20 = 0;
  LOBYTE(v17) = 0;
  *(_OWORD *)(v6 + 12) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 15;
  *((_DWORD *)v6 + 1) = 28;
  *((_DWORD *)v6 + 3) = GetCurrentProcessId();
  *((_DWORD *)v6 + 2) = GetCurrentThreadId();
LABEL_8:
  LOBYTE(v17) = v2 == 8;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x138,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x800705B4LL,
    v17,
    (bool)"Failed to allocate shared buffer event",
    v18);
  v9 = (char *)operator new(0x28u);
  v20 = (unsigned __int8 *)v9;
  *(_OWORD *)v9 = 0;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable';
  v10 = v9 + 16;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 4) = v6;
  *a2 = v9 + 16;
  a2[1] = v9;
  if ( v9 != (char *)-16LL )
  {
    v11 = *((_QWORD *)v9 + 3);
    if ( !v11 || !*(_DWORD *)(v11 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
      v12 = (volatile signed __int32 *)a2[1];
      v13 = 0;
      v14 = 0;
      if ( v12 )
      {
        v13 = v10;
        v14 = a2[1];
        _InterlockedIncrement(v12 + 3);
      }
      v15 = (volatile signed __int32 *)v10[1];
      *v10 = v13;
      v10[1] = v14;
      if ( v15 && _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800162b4  push    rbx
0x1800162b6  push    rbp
0x1800162b7  push    rsi
0x1800162b8  push    rdi
0x1800162b9  sub     rsp, 48h
0x1800162bd  xor     ebx, ebx
0x1800162bf  mov     rsi, rdx
0x1800162c2  mov     [rsp+68h+arg_0], rbx
0x1800162c7  mov     rbp, rcx
0x1800162ca  mov     rcx, [rbp+68h]; this
0x1800162ce  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x1800162d3  mov     edx, 1Ch; unsigned int
0x1800162d8  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x1800162dd  mov     rdi, [rsp+68h+arg_0]
0x1800162e2  test    eax, eax
0x1800162e4  jns     short loc_180016312
0x1800162e6  mov     rcx, rbp
0x1800162e9  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x1800162ee  test    al, al
0x1800162f0  jnz     short loc_180016309
0x1800162f2  mov     rcx, [rbp+70h]; hEvent
0x1800162f6  call    cs:__imp_SetEvent
0x1800162fc  mov     rcx, [rsp+68h]; this
0x180016301  test    eax, eax
0x180016303  jz      loc_18001648E
0x180016309  inc     ebx
0x18001630b  cmp     ebx, 8
0x18001630e  jb      short loc_1800162CA
0x180016310  jmp     short loc_180016368
0x180016312  mov     rcx, [rsp+68h]; this
0x180016317  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x18001631e  xorps   xmm0, xmm0
0x180016321  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180016326  movups  xmmword ptr [rdi], xmm0
0x180016329  mov     r9d, 80004005h; char *
0x18001632f  mov     byte ptr [rsp+68h+var_48], 0; int
0x180016334  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001633b  mov     edx, 130h; void *
0x180016340  movups  xmmword ptr [rdi+0Ch], xmm0
0x180016344  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016349  mov     dword ptr [rdi], 0Fh
0x18001634f  mov     dword ptr [rdi+4], 1Ch
0x180016356  call    cs:__imp_GetCurrentProcessId
0x18001635c  mov     [rdi+0Ch], eax
0x18001635f  call    cs:__imp_GetCurrentThreadId
0x180016365  mov     [rdi+8], eax
0x180016368  mov     rcx, [rsp+68h]; this
0x18001636d  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016374  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180016379  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016380  cmp     ebx, 8
0x180016383  mov     r9d, 800705B4h; char *
0x180016389  mov     edx, 138h; void *
0x18001638e  setz    al
0x180016391  mov     byte ptr [rsp+68h+var_48], al; int
0x180016395  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001639a  mov     ecx, 28h ; '('; Size
0x18001639f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800163a4  mov     [rsp+68h+arg_0], rax
0x1800163a9  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800163b0  xorps   xmm0, xmm0
0x1800163b3  movups  xmmword ptr [rax], xmm0
0x1800163b6  mov     [rax], rcx
0x1800163b9  lea     rcx, [rax+10h]
0x1800163bd  mov     dword ptr [rax+8], 1
0x1800163c4  mov     dword ptr [rax+0Ch], 1
0x1800163cb  mov     qword ptr [rcx], 0
0x1800163d2  mov     qword ptr [rcx+8], 0
0x1800163da  mov     [rcx+10h], rdi
0x1800163de  mov     [rsi], rcx
0x1800163e1  mov     [rsi+8], rax
0x1800163e5  test    rcx, rcx
0x1800163e8  jz      loc_180016482
0x1800163ee  mov     rdx, [rcx+8]
0x1800163f2  test    rdx, rdx
0x1800163f5  jz      short loc_180016401
0x1800163f7  cmp     dword ptr [rdx+8], 0
0x1800163fb  jnz     loc_180016482
0x180016401  lock inc dword ptr [rax+8]
0x180016405  mov     rbx, [rsi+8]
0x180016409  xor     eax, eax
0x18001640b  xor     r8d, r8d
0x18001640e  test    rbx, rbx
0x180016411  jz      short loc_18001641D
0x180016413  mov     rax, rcx
0x180016416  mov     r8, rbx
0x180016419  lock inc dword ptr [rbx+0Ch]
0x18001641d  mov     rdx, [rcx+8]
0x180016421  or      ebp, 0FFFFFFFFh
0x180016424  mov     [rcx], rax
0x180016427  mov     [rcx+8], r8
0x18001642b  test    rdx, rdx
0x18001642e  jz      short loc_18001644A
0x180016430  mov     eax, ebp
0x180016432  lock xadd [rdx+0Ch], eax
0x180016437  add     eax, ebp
0x180016439  jnz     short loc_18001644A
0x18001643b  mov     rax, [rdx]
0x18001643e  mov     rcx, rdx
0x180016441  mov     rax, [rax+8]
0x180016445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001644a  test    rbx, rbx
0x18001644d  jz      short loc_180016482
0x18001644f  mov     eax, ebp
0x180016451  lock xadd [rbx+8], eax
0x180016456  add     eax, ebp
0x180016458  jnz     short loc_180016482
0x18001645a  mov     rax, [rbx]
0x18001645d  mov     rcx, rbx
0x180016460  mov     rax, [rax]
0x180016463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016468  mov     eax, ebp
0x18001646a  lock xadd [rbx+0Ch], eax
0x18001646f  add     eax, ebp
0x180016471  jnz     short loc_180016482
0x180016473  mov     rax, [rbx]
0x180016476  mov     rcx, rbx
0x180016479  mov     rax, [rax+8]
0x18001647d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016482  mov     rax, rsi
0x180016485  add     rsp, 48h
0x180016489  pop     rdi
0x18001648a  pop     rsi
0x18001648b  pop     rbp
0x18001648c  pop     rbx
0x18001648d  retn
0x18001648e  mov     edx, 0A01h; void *
0x180016493  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
