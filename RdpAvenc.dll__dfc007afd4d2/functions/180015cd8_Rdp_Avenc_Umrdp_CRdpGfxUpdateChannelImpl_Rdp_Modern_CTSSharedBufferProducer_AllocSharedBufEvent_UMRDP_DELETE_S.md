# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_DELETE_SURFACE_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x180015cd8`
- end: `0x180015ebf`
- name: `??$AllocSharedBufEvent@UUMRDP_DELETE_SURFACE_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_DELETE_SURFACE_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180020a08`

## callees

- `0x1800065a4`
- `0x18000b07c`
- `0x1800146bc`
- `0x180015cd8`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015d1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015d7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015d7c`

## string_xrefs

- `0x180015d3b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180015d9f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_DELETE_SURFACE_EVENT>(
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
           0x18u,
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
  *((_QWORD *)v6 + 2) = 0;
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 11;
  *((_DWORD *)v6 + 1) = 24;
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
0x180015cd8  push    rbx
0x180015cda  push    rbp
0x180015cdb  push    rsi
0x180015cdc  push    rdi
0x180015cdd  sub     rsp, 48h
0x180015ce1  xor     ebx, ebx
0x180015ce3  mov     rsi, rdx
0x180015ce6  mov     [rsp+68h+arg_0], rbx
0x180015ceb  mov     rbp, rcx
0x180015cee  mov     rcx, [rbp+68h]; this
0x180015cf2  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x180015cf7  mov     edx, 18h; unsigned int
0x180015cfc  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x180015d01  mov     rdi, [rsp+68h+arg_0]
0x180015d06  test    eax, eax
0x180015d08  jns     short loc_180015D36
0x180015d0a  mov     rcx, rbp
0x180015d0d  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x180015d12  test    al, al
0x180015d14  jnz     short loc_180015D2D
0x180015d16  mov     rcx, [rbp+70h]; hEvent
0x180015d1a  call    cs:__imp_SetEvent
0x180015d20  mov     rcx, [rsp+68h]; this
0x180015d25  test    eax, eax
0x180015d27  jz      loc_180015EB4
0x180015d2d  inc     ebx
0x180015d2f  cmp     ebx, 8
0x180015d32  jb      short loc_180015CEE
0x180015d34  jmp     short loc_180015D8E
0x180015d36  mov     rcx, [rsp+68h]; this
0x180015d3b  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015d42  xor     eax, eax
0x180015d44  xorps   xmm0, xmm0
0x180015d47  movups  xmmword ptr [rdi], xmm0
0x180015d4a  mov     [rdi+10h], rax
0x180015d4e  mov     r9d, 80004005h; char *
0x180015d54  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180015d5b  mov     edx, 130h; void *
0x180015d60  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180015d65  mov     byte ptr [rsp+68h+var_48], 0; int
0x180015d6a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015d6f  mov     dword ptr [rdi], 0Bh
0x180015d75  mov     dword ptr [rdi+4], 18h
0x180015d7c  call    cs:__imp_GetCurrentProcessId
0x180015d82  mov     [rdi+0Ch], eax
0x180015d85  call    cs:__imp_GetCurrentThreadId
0x180015d8b  mov     [rdi+8], eax
0x180015d8e  mov     rcx, [rsp+68h]; this
0x180015d93  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180015d9a  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180015d9f  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015da6  cmp     ebx, 8
0x180015da9  mov     r9d, 800705B4h; char *
0x180015daf  mov     edx, 138h; void *
0x180015db4  setz    al
0x180015db7  mov     byte ptr [rsp+68h+var_48], al; int
0x180015dbb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015dc0  mov     ecx, 28h ; '('; Size
0x180015dc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015dca  mov     [rsp+68h+arg_0], rax
0x180015dcf  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x180015dd6  xorps   xmm0, xmm0
0x180015dd9  movups  xmmword ptr [rax], xmm0
0x180015ddc  mov     [rax], rcx
0x180015ddf  lea     rcx, [rax+10h]
0x180015de3  mov     dword ptr [rax+8], 1
0x180015dea  mov     dword ptr [rax+0Ch], 1
0x180015df1  mov     qword ptr [rcx], 0
0x180015df8  mov     qword ptr [rcx+8], 0
0x180015e00  mov     [rcx+10h], rdi
0x180015e04  mov     [rsi], rcx
0x180015e07  mov     [rsi+8], rax
0x180015e0b  test    rcx, rcx
0x180015e0e  jz      loc_180015EA8
0x180015e14  mov     rdx, [rcx+8]
0x180015e18  test    rdx, rdx
0x180015e1b  jz      short loc_180015E27
0x180015e1d  cmp     dword ptr [rdx+8], 0
0x180015e21  jnz     loc_180015EA8
0x180015e27  lock inc dword ptr [rax+8]
0x180015e2b  mov     rbx, [rsi+8]
0x180015e2f  xor     eax, eax
0x180015e31  xor     r8d, r8d
0x180015e34  test    rbx, rbx
0x180015e37  jz      short loc_180015E43
0x180015e39  mov     rax, rcx
0x180015e3c  mov     r8, rbx
0x180015e3f  lock inc dword ptr [rbx+0Ch]
0x180015e43  mov     rdx, [rcx+8]
0x180015e47  or      ebp, 0FFFFFFFFh
0x180015e4a  mov     [rcx], rax
0x180015e4d  mov     [rcx+8], r8
0x180015e51  test    rdx, rdx
0x180015e54  jz      short loc_180015E70
0x180015e56  mov     eax, ebp
0x180015e58  lock xadd [rdx+0Ch], eax
0x180015e5d  add     eax, ebp
0x180015e5f  jnz     short loc_180015E70
0x180015e61  mov     rax, [rdx]
0x180015e64  mov     rcx, rdx
0x180015e67  mov     rax, [rax+8]
0x180015e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e70  test    rbx, rbx
0x180015e73  jz      short loc_180015EA8
0x180015e75  mov     eax, ebp
0x180015e77  lock xadd [rbx+8], eax
0x180015e7c  add     eax, ebp
0x180015e7e  jnz     short loc_180015EA8
0x180015e80  mov     rax, [rbx]
0x180015e83  mov     rcx, rbx
0x180015e86  mov     rax, [rax]
0x180015e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8e  mov     eax, ebp
0x180015e90  lock xadd [rbx+0Ch], eax
0x180015e95  add     eax, ebp
0x180015e97  jnz     short loc_180015EA8
0x180015e99  mov     rax, [rbx]
0x180015e9c  mov     rcx, rbx
0x180015e9f  mov     rax, [rax+8]
0x180015ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ea8  mov     rax, rsi
0x180015eab  add     rsp, 48h
0x180015eaf  pop     rdi
0x180015eb0  pop     rsi
0x180015eb1  pop     rbp
0x180015eb2  pop     rbx
0x180015eb3  retn
0x180015eb4  mov     edx, 0A01h; void *
0x180015eb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
