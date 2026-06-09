# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_DXTEXTURE_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x1800158e4`
- end: `0x180015ad2`
- name: `??$AllocSharedBufEvent@UUMRDP_CREATE_SURFACE_DXTEXTURE_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_DXTEXTURE_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800195a0`

## callees

- `0x1800065a4`
- `0x18000b07c`
- `0x1800146bc`
- `0x1800158e4`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015926`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015926`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001598f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001598f`

## string_xrefs

- `0x180015947`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x1800159b2`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_DXTEXTURE_EVENT>(
        __int64 a1,
        _QWORD *a2)
{
  int v2; // edi
  int v5; // eax
  unsigned __int8 *v6; // rbx
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
           0x34u,
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
  *((_OWORD *)v6 + 1) = 0;
  *((_OWORD *)v6 + 2) = 0;
  *((_DWORD *)v6 + 12) = 0;
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 21;
  *((_DWORD *)v6 + 1) = 52;
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
0x1800158e4  push    rbx
0x1800158e6  push    rbp
0x1800158e7  push    rsi
0x1800158e8  push    rdi
0x1800158e9  sub     rsp, 48h
0x1800158ed  xor     edi, edi
0x1800158ef  mov     rsi, rdx
0x1800158f2  mov     [rsp+68h+arg_0], rdi
0x1800158f7  mov     rbp, rcx
0x1800158fa  mov     rcx, [rbp+68h]; this
0x1800158fe  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x180015903  mov     edx, 34h ; '4'; unsigned int
0x180015908  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x18001590d  mov     rbx, [rsp+68h+arg_0]
0x180015912  test    eax, eax
0x180015914  jns     short loc_180015942
0x180015916  mov     rcx, rbp
0x180015919  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x18001591e  test    al, al
0x180015920  jnz     short loc_180015939
0x180015922  mov     rcx, [rbp+70h]; hEvent
0x180015926  call    cs:__imp_SetEvent
0x18001592c  mov     rcx, [rsp+68h]; this
0x180015931  test    eax, eax
0x180015933  jz      loc_180015AC7
0x180015939  inc     edi
0x18001593b  cmp     edi, 8
0x18001593e  jb      short loc_1800158FA
0x180015940  jmp     short loc_1800159A1
0x180015942  mov     rcx, [rsp+68h]; this
0x180015947  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001594e  xorps   xmm0, xmm0
0x180015951  xor     eax, eax
0x180015953  movups  xmmword ptr [rbx], xmm0
0x180015956  mov     r9d, 80004005h; char *
0x18001595c  mov     edx, 130h; void *
0x180015961  movups  xmmword ptr [rbx+10h], xmm0
0x180015965  movups  xmmword ptr [rbx+20h], xmm0
0x180015969  mov     [rbx+30h], eax
0x18001596c  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180015973  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180015978  mov     byte ptr [rsp+68h+var_48], 0; int
0x18001597d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015982  mov     dword ptr [rbx], 15h
0x180015988  mov     dword ptr [rbx+4], 34h ; '4'
0x18001598f  call    cs:__imp_GetCurrentProcessId
0x180015995  mov     [rbx+0Ch], eax
0x180015998  call    cs:__imp_GetCurrentThreadId
0x18001599e  mov     [rbx+8], eax
0x1800159a1  mov     rcx, [rsp+68h]; this
0x1800159a6  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x1800159ad  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x1800159b2  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800159b9  cmp     edi, 8
0x1800159bc  mov     r9d, 800705B4h; char *
0x1800159c2  mov     edx, 138h; void *
0x1800159c7  setz    al
0x1800159ca  mov     byte ptr [rsp+68h+var_48], al; int
0x1800159ce  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800159d3  mov     ecx, 28h ; '('; Size
0x1800159d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800159dd  mov     [rsp+68h+arg_0], rax
0x1800159e2  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800159e9  xorps   xmm0, xmm0
0x1800159ec  movups  xmmword ptr [rax], xmm0
0x1800159ef  mov     [rax], rcx
0x1800159f2  lea     rcx, [rax+10h]
0x1800159f6  mov     dword ptr [rax+8], 1
0x1800159fd  mov     dword ptr [rax+0Ch], 1
0x180015a04  mov     qword ptr [rcx], 0
0x180015a0b  mov     qword ptr [rcx+8], 0
0x180015a13  mov     [rcx+10h], rbx
0x180015a17  mov     [rsi], rcx
0x180015a1a  mov     [rsi+8], rax
0x180015a1e  test    rcx, rcx
0x180015a21  jz      loc_180015ABB
0x180015a27  mov     rdx, [rcx+8]
0x180015a2b  test    rdx, rdx
0x180015a2e  jz      short loc_180015A3A
0x180015a30  cmp     dword ptr [rdx+8], 0
0x180015a34  jnz     loc_180015ABB
0x180015a3a  lock inc dword ptr [rax+8]
0x180015a3e  mov     rbx, [rsi+8]
0x180015a42  xor     eax, eax
0x180015a44  xor     r8d, r8d
0x180015a47  test    rbx, rbx
0x180015a4a  jz      short loc_180015A56
0x180015a4c  mov     rax, rcx
0x180015a4f  mov     r8, rbx
0x180015a52  lock inc dword ptr [rbx+0Ch]
0x180015a56  mov     rdx, [rcx+8]
0x180015a5a  or      ebp, 0FFFFFFFFh
0x180015a5d  mov     [rcx], rax
0x180015a60  mov     [rcx+8], r8
0x180015a64  test    rdx, rdx
0x180015a67  jz      short loc_180015A83
0x180015a69  mov     eax, ebp
0x180015a6b  lock xadd [rdx+0Ch], eax
0x180015a70  add     eax, ebp
0x180015a72  jnz     short loc_180015A83
0x180015a74  mov     rax, [rdx]
0x180015a77  mov     rcx, rdx
0x180015a7a  mov     rax, [rax+8]
0x180015a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a83  test    rbx, rbx
0x180015a86  jz      short loc_180015ABB
0x180015a88  mov     eax, ebp
0x180015a8a  lock xadd [rbx+8], eax
0x180015a8f  add     eax, ebp
0x180015a91  jnz     short loc_180015ABB
0x180015a93  mov     rax, [rbx]
0x180015a96  mov     rcx, rbx
0x180015a99  mov     rax, [rax]
0x180015a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aa1  mov     eax, ebp
0x180015aa3  lock xadd [rbx+0Ch], eax
0x180015aa8  add     eax, ebp
0x180015aaa  jnz     short loc_180015ABB
0x180015aac  mov     rax, [rbx]
0x180015aaf  mov     rcx, rbx
0x180015ab2  mov     rax, [rax+8]
0x180015ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015abb  mov     rax, rsi
0x180015abe  add     rsp, 48h
0x180015ac2  pop     rdi
0x180015ac3  pop     rsi
0x180015ac4  pop     rbp
0x180015ac5  pop     rbx
0x180015ac6  retn
0x180015ac7  mov     edx, 0A01h; void *
0x180015acc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
