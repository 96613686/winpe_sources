# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_VIDEO_HINT_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x18001689c`
- end: `0x180016a94`
- name: `??$AllocSharedBufEvent@UUMRDP_VIDEO_HINT_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_VIDEO_HINT_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `504`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180019020`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x18001689c`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800168df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800168df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016947`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016947`

## string_xrefs

- `0x18001691c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x18001696c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_VIDEO_HINT_EVENT>(
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
           0x45Cu,
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
  memset_0(v20, 0, 0x45Cu);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 23;
  *((_DWORD *)v6 + 1) = 1116;
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
0x18001689c  push    rbx
0x18001689e  push    rsi
0x18001689f  push    rdi
0x1800168a0  push    r14
0x1800168a2  sub     rsp, 48h
0x1800168a6  xor     ebx, ebx
0x1800168a8  mov     rsi, rdx
0x1800168ab  mov     [rsp+68h+arg_0], rbx
0x1800168b0  mov     rdi, rcx
0x1800168b3  mov     rcx, [rdi+68h]; this
0x1800168b7  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x1800168bc  mov     edx, 45Ch; unsigned int
0x1800168c1  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x1800168c6  mov     r14, [rsp+68h+arg_0]
0x1800168cb  test    eax, eax
0x1800168cd  jns     short loc_1800168FB
0x1800168cf  mov     rcx, rdi
0x1800168d2  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x1800168d7  test    al, al
0x1800168d9  jnz     short loc_1800168F2
0x1800168db  mov     rcx, [rdi+70h]; hEvent
0x1800168df  call    cs:__imp_SetEvent
0x1800168e5  mov     rcx, [rsp+68h]; this
0x1800168ea  test    eax, eax
0x1800168ec  jz      loc_180016A89
0x1800168f2  inc     ebx
0x1800168f4  cmp     ebx, 8
0x1800168f7  jb      short loc_1800168B3
0x1800168f9  jmp     short loc_18001695B
0x1800168fb  xor     edx, edx; Val
0x1800168fd  mov     r8d, 45Ch; Size
0x180016903  mov     rcx, r14; void *
0x180016906  call    memset_0
0x18001690b  mov     rcx, [rsp+68h]; this
0x180016910  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180016917  mov     qword ptr [rsp+68h+var_40], rax; bool
0x18001691c  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016923  mov     r9d, 80004005h; char *
0x180016929  mov     byte ptr [rsp+68h+var_48], 0; int
0x18001692e  mov     edx, 130h; void *
0x180016933  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016938  mov     dword ptr [r14], 17h
0x18001693f  mov     dword ptr [r14+4], 45Ch
0x180016947  call    cs:__imp_GetCurrentProcessId
0x18001694d  mov     [r14+0Ch], eax
0x180016951  call    cs:__imp_GetCurrentThreadId
0x180016957  mov     [r14+8], eax
0x18001695b  mov     rcx, [rsp+68h]; this
0x180016960  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016967  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x18001696c  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016973  cmp     ebx, 8
0x180016976  mov     r9d, 800705B4h; char *
0x18001697c  mov     edx, 138h; void *
0x180016981  setz    al
0x180016984  mov     byte ptr [rsp+68h+var_48], al; int
0x180016988  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001698d  mov     ecx, 28h ; '('; Size
0x180016992  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016997  mov     [rsp+68h+arg_0], rax
0x18001699c  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800169a3  xorps   xmm0, xmm0
0x1800169a6  movups  xmmword ptr [rax], xmm0
0x1800169a9  mov     [rax], rcx
0x1800169ac  lea     rcx, [rax+10h]
0x1800169b0  mov     dword ptr [rax+8], 1
0x1800169b7  mov     dword ptr [rax+0Ch], 1
0x1800169be  mov     qword ptr [rcx], 0
0x1800169c5  mov     qword ptr [rcx+8], 0
0x1800169cd  mov     [rcx+10h], r14
0x1800169d1  mov     [rsi], rcx
0x1800169d4  mov     [rsi+8], rax
0x1800169d8  test    rcx, rcx
0x1800169db  jz      loc_180016A7C
0x1800169e1  mov     rdx, [rcx+8]
0x1800169e5  test    rdx, rdx
0x1800169e8  jz      short loc_1800169F4
0x1800169ea  cmp     dword ptr [rdx+8], 0
0x1800169ee  jnz     loc_180016A7C
0x1800169f4  lock inc dword ptr [rax+8]
0x1800169f8  mov     rbx, [rsi+8]
0x1800169fc  xor     eax, eax
0x1800169fe  xor     r8d, r8d
0x180016a01  test    rbx, rbx
0x180016a04  jz      short loc_180016A10
0x180016a06  mov     rax, rcx
0x180016a09  mov     r8, rbx
0x180016a0c  lock inc dword ptr [rbx+0Ch]
0x180016a10  mov     rdx, [rcx+8]
0x180016a14  or      r14d, 0FFFFFFFFh
0x180016a18  mov     [rcx], rax
0x180016a1b  mov     [rcx+8], r8
0x180016a1f  test    rdx, rdx
0x180016a22  jz      short loc_180016A40
0x180016a24  mov     eax, r14d
0x180016a27  lock xadd [rdx+0Ch], eax
0x180016a2c  add     eax, r14d
0x180016a2f  jnz     short loc_180016A40
0x180016a31  mov     rax, [rdx]
0x180016a34  mov     rcx, rdx
0x180016a37  mov     rax, [rax+8]
0x180016a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a40  test    rbx, rbx
0x180016a43  jz      short loc_180016A7C
0x180016a45  mov     eax, r14d
0x180016a48  lock xadd [rbx+8], eax
0x180016a4d  add     eax, r14d
0x180016a50  jnz     short loc_180016A7C
0x180016a52  mov     rax, [rbx]
0x180016a55  mov     rcx, rbx
0x180016a58  mov     rax, [rax]
0x180016a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a60  mov     eax, r14d
0x180016a63  lock xadd [rbx+0Ch], eax
0x180016a68  add     eax, r14d
0x180016a6b  jnz     short loc_180016A7C
0x180016a6d  mov     rax, [rbx]
0x180016a70  mov     rcx, rbx
0x180016a73  mov     rax, [rax+8]
0x180016a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a7c  mov     rax, rsi
0x180016a7f  add     rsp, 48h
0x180016a83  pop     r14
0x180016a85  pop     rdi
0x180016a86  pop     rsi
0x180016a87  pop     rbx
0x180016a88  retn
0x180016a89  mov     edx, 0A01h; void *
0x180016a8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
