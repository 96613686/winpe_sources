# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_SURF_TO_SURF_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x180016c9c`
- end: `0x180016e92`
- name: `??$AllocSharedBufEvent@UtagUMRDP_SURF_TO_SURF_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UtagUMRDP_SURF_TO_SURF_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180020b44`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x180016c9c`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016cdf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016d45`

## string_xrefs

- `0x180016d1a`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180016d6a`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_SURF_TO_SURF_EVENT>(
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
           0x78u,
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
  memset_0(v20, 0, 0x78u);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 0;
  *((_DWORD *)v6 + 1) = 120;
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
0x180016c9c  push    rbx
0x180016c9e  push    rsi
0x180016c9f  push    rdi
0x180016ca0  push    r14
0x180016ca2  sub     rsp, 48h
0x180016ca6  xor     ebx, ebx
0x180016ca8  mov     rsi, rdx
0x180016cab  mov     [rsp+68h+arg_0], rbx
0x180016cb0  mov     rdi, rcx
0x180016cb3  mov     rcx, [rdi+68h]; this
0x180016cb7  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x180016cbc  mov     edx, 78h ; 'x'; unsigned int
0x180016cc1  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x180016cc6  mov     r14, [rsp+68h+arg_0]
0x180016ccb  test    eax, eax
0x180016ccd  jns     short loc_180016CFB
0x180016ccf  mov     rcx, rdi
0x180016cd2  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x180016cd7  test    al, al
0x180016cd9  jnz     short loc_180016CF2
0x180016cdb  mov     rcx, [rdi+70h]; hEvent
0x180016cdf  call    cs:__imp_SetEvent
0x180016ce5  mov     rcx, [rsp+68h]; this
0x180016cea  test    eax, eax
0x180016cec  jz      loc_180016E87
0x180016cf2  inc     ebx
0x180016cf4  cmp     ebx, 8
0x180016cf7  jb      short loc_180016CB3
0x180016cf9  jmp     short loc_180016D59
0x180016cfb  xor     edx, edx; Val
0x180016cfd  mov     rcx, r14; void *
0x180016d00  lea     r8d, [rdx+78h]; Size
0x180016d04  call    memset_0
0x180016d09  mov     rcx, [rsp+68h]; this
0x180016d0e  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180016d15  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180016d1a  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016d21  mov     r9d, 80004005h; char *
0x180016d27  mov     byte ptr [rsp+68h+var_48], 0; int
0x180016d2c  mov     edx, 130h; void *
0x180016d31  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016d36  mov     dword ptr [r14], 0
0x180016d3d  mov     dword ptr [r14+4], 78h ; 'x'
0x180016d45  call    cs:__imp_GetCurrentProcessId
0x180016d4b  mov     [r14+0Ch], eax
0x180016d4f  call    cs:__imp_GetCurrentThreadId
0x180016d55  mov     [r14+8], eax
0x180016d59  mov     rcx, [rsp+68h]; this
0x180016d5e  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016d65  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180016d6a  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016d71  cmp     ebx, 8
0x180016d74  mov     r9d, 800705B4h; char *
0x180016d7a  mov     edx, 138h; void *
0x180016d7f  setz    al
0x180016d82  mov     byte ptr [rsp+68h+var_48], al; int
0x180016d86  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016d8b  mov     ecx, 28h ; '('; Size
0x180016d90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016d95  mov     [rsp+68h+arg_0], rax
0x180016d9a  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x180016da1  xorps   xmm0, xmm0
0x180016da4  movups  xmmword ptr [rax], xmm0
0x180016da7  mov     [rax], rcx
0x180016daa  lea     rcx, [rax+10h]
0x180016dae  mov     dword ptr [rax+8], 1
0x180016db5  mov     dword ptr [rax+0Ch], 1
0x180016dbc  mov     qword ptr [rcx], 0
0x180016dc3  mov     qword ptr [rcx+8], 0
0x180016dcb  mov     [rcx+10h], r14
0x180016dcf  mov     [rsi], rcx
0x180016dd2  mov     [rsi+8], rax
0x180016dd6  test    rcx, rcx
0x180016dd9  jz      loc_180016E7A
0x180016ddf  mov     rdx, [rcx+8]
0x180016de3  test    rdx, rdx
0x180016de6  jz      short loc_180016DF2
0x180016de8  cmp     dword ptr [rdx+8], 0
0x180016dec  jnz     loc_180016E7A
0x180016df2  lock inc dword ptr [rax+8]
0x180016df6  mov     rbx, [rsi+8]
0x180016dfa  xor     eax, eax
0x180016dfc  xor     r8d, r8d
0x180016dff  test    rbx, rbx
0x180016e02  jz      short loc_180016E0E
0x180016e04  mov     rax, rcx
0x180016e07  mov     r8, rbx
0x180016e0a  lock inc dword ptr [rbx+0Ch]
0x180016e0e  mov     rdx, [rcx+8]
0x180016e12  or      r14d, 0FFFFFFFFh
0x180016e16  mov     [rcx], rax
0x180016e19  mov     [rcx+8], r8
0x180016e1d  test    rdx, rdx
0x180016e20  jz      short loc_180016E3E
0x180016e22  mov     eax, r14d
0x180016e25  lock xadd [rdx+0Ch], eax
0x180016e2a  add     eax, r14d
0x180016e2d  jnz     short loc_180016E3E
0x180016e2f  mov     rax, [rdx]
0x180016e32  mov     rcx, rdx
0x180016e35  mov     rax, [rax+8]
0x180016e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e3e  test    rbx, rbx
0x180016e41  jz      short loc_180016E7A
0x180016e43  mov     eax, r14d
0x180016e46  lock xadd [rbx+8], eax
0x180016e4b  add     eax, r14d
0x180016e4e  jnz     short loc_180016E7A
0x180016e50  mov     rax, [rbx]
0x180016e53  mov     rcx, rbx
0x180016e56  mov     rax, [rax]
0x180016e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5e  mov     eax, r14d
0x180016e61  lock xadd [rbx+0Ch], eax
0x180016e66  add     eax, r14d
0x180016e69  jnz     short loc_180016E7A
0x180016e6b  mov     rax, [rbx]
0x180016e6e  mov     rcx, rbx
0x180016e71  mov     rax, [rax+8]
0x180016e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e7a  mov     rax, rsi
0x180016e7d  add     rsp, 48h
0x180016e81  pop     r14
0x180016e83  pop     rdi
0x180016e84  pop     rsi
0x180016e85  pop     rbx
0x180016e86  retn
0x180016e87  mov     edx, 0A01h; void *
0x180016e8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
