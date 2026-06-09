# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_UPDATE_MONITORLAYOUT_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x18001669c`
- end: `0x180016894`
- name: `??$AllocSharedBufEvent@UUMRDP_UPDATE_MONITORLAYOUT_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_UPDATE_MONITORLAYOUT_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001709c`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x18001669c`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800166df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800166df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016747`

## string_xrefs

- `0x18001671c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x18001676c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_UPDATE_MONITORLAYOUT_EVENT>(
        __int64 a1,
        _QWORD *a2)
{
  int v2; // ebx
  int v5; // eax
  unsigned __int8 *v6; // r14
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
           0x294u,
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
  memset_0(v20, 0, 0x294u);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 17;
  *((_DWORD *)v6 + 1) = 660;
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
0x18001669c  push    rbx
0x18001669e  push    rsi
0x18001669f  push    rdi
0x1800166a0  push    r14
0x1800166a2  sub     rsp, 48h
0x1800166a6  xor     ebx, ebx
0x1800166a8  mov     rsi, rdx
0x1800166ab  mov     [rsp+68h+arg_0], rbx
0x1800166b0  mov     rdi, rcx
0x1800166b3  mov     rcx, [rdi+68h]; this
0x1800166b7  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x1800166bc  mov     edx, 294h; unsigned int
0x1800166c1  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x1800166c6  mov     r14, [rsp+68h+arg_0]
0x1800166cb  test    eax, eax
0x1800166cd  jns     short loc_1800166FB
0x1800166cf  mov     rcx, rdi
0x1800166d2  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x1800166d7  test    al, al
0x1800166d9  jnz     short loc_1800166F2
0x1800166db  mov     rcx, [rdi+70h]; hEvent
0x1800166df  call    cs:__imp_SetEvent
0x1800166e5  mov     rcx, [rsp+68h]; this
0x1800166ea  test    eax, eax
0x1800166ec  jz      loc_180016889
0x1800166f2  inc     ebx
0x1800166f4  cmp     ebx, 8
0x1800166f7  jb      short loc_1800166B3
0x1800166f9  jmp     short loc_18001675B
0x1800166fb  xor     edx, edx; Val
0x1800166fd  mov     r8d, 294h; Size
0x180016703  mov     rcx, r14; void *
0x180016706  call    memset_0
0x18001670b  mov     rcx, [rsp+68h]; this
0x180016710  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180016717  mov     qword ptr [rsp+68h+var_40], rax; bool
0x18001671c  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016723  mov     r9d, 80004005h; char *
0x180016729  mov     byte ptr [rsp+68h+var_48], 0; int
0x18001672e  mov     edx, 130h; void *
0x180016733  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016738  mov     dword ptr [r14], 11h
0x18001673f  mov     dword ptr [r14+4], 294h
0x180016747  call    cs:__imp_GetCurrentProcessId
0x18001674d  mov     [r14+0Ch], eax
0x180016751  call    cs:__imp_GetCurrentThreadId
0x180016757  mov     [r14+8], eax
0x18001675b  mov     rcx, [rsp+68h]; this
0x180016760  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016767  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x18001676c  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016773  cmp     ebx, 8
0x180016776  mov     r9d, 800705B4h; char *
0x18001677c  mov     edx, 138h; void *
0x180016781  setz    al
0x180016784  mov     byte ptr [rsp+68h+var_48], al; int
0x180016788  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001678d  mov     ecx, 28h ; '('; Size
0x180016792  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016797  mov     [rsp+68h+arg_0], rax
0x18001679c  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800167a3  xorps   xmm0, xmm0
0x1800167a6  movups  xmmword ptr [rax], xmm0
0x1800167a9  mov     [rax], rcx
0x1800167ac  lea     rcx, [rax+10h]
0x1800167b0  mov     dword ptr [rax+8], 1
0x1800167b7  mov     dword ptr [rax+0Ch], 1
0x1800167be  mov     qword ptr [rcx], 0
0x1800167c5  mov     qword ptr [rcx+8], 0
0x1800167cd  mov     [rcx+10h], r14
0x1800167d1  mov     [rsi], rcx
0x1800167d4  mov     [rsi+8], rax
0x1800167d8  test    rcx, rcx
0x1800167db  jz      loc_18001687C
0x1800167e1  mov     rdx, [rcx+8]
0x1800167e5  test    rdx, rdx
0x1800167e8  jz      short loc_1800167F4
0x1800167ea  cmp     dword ptr [rdx+8], 0
0x1800167ee  jnz     loc_18001687C
0x1800167f4  lock inc dword ptr [rax+8]
0x1800167f8  mov     rbx, [rsi+8]
0x1800167fc  xor     eax, eax
0x1800167fe  xor     r8d, r8d
0x180016801  test    rbx, rbx
0x180016804  jz      short loc_180016810
0x180016806  mov     rax, rcx
0x180016809  mov     r8, rbx
0x18001680c  lock inc dword ptr [rbx+0Ch]
0x180016810  mov     rdx, [rcx+8]
0x180016814  or      r14d, 0FFFFFFFFh
0x180016818  mov     [rcx], rax
0x18001681b  mov     [rcx+8], r8
0x18001681f  test    rdx, rdx
0x180016822  jz      short loc_180016840
0x180016824  mov     eax, r14d
0x180016827  lock xadd [rdx+0Ch], eax
0x18001682c  add     eax, r14d
0x18001682f  jnz     short loc_180016840
0x180016831  mov     rax, [rdx]
0x180016834  mov     rcx, rdx
0x180016837  mov     rax, [rax+8]
0x18001683b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016840  test    rbx, rbx
0x180016843  jz      short loc_18001687C
0x180016845  mov     eax, r14d
0x180016848  lock xadd [rbx+8], eax
0x18001684d  add     eax, r14d
0x180016850  jnz     short loc_18001687C
0x180016852  mov     rax, [rbx]
0x180016855  mov     rcx, rbx
0x180016858  mov     rax, [rax]
0x18001685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016860  mov     eax, r14d
0x180016863  lock xadd [rbx+0Ch], eax
0x180016868  add     eax, r14d
0x18001686b  jnz     short loc_18001687C
0x18001686d  mov     rax, [rbx]
0x180016870  mov     rcx, rbx
0x180016873  mov     rax, [rax+8]
0x180016877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001687c  mov     rax, rsi
0x18001687f  add     rsp, 48h
0x180016883  pop     r14
0x180016885  pop     rdi
0x180016886  pop     rsi
0x180016887  pop     rbx
0x180016888  retn
0x180016889  mov     edx, 0A01h; void *
0x18001688e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
