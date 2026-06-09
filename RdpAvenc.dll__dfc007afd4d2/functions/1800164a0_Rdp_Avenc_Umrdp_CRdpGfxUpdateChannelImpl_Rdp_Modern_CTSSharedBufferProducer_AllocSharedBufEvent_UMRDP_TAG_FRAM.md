# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_TAG_FRAME_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x1800164a0`
- end: `0x180016696`
- name: `??$AllocSharedBufEvent@UUMRDP_TAG_FRAME_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_TAG_FRAME_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180013878`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x1800164a0`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800164e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800164e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016549`

## string_xrefs

- `0x18001651e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x18001656e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_TAG_FRAME_EVENT>(
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
           0x50u,
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
  memset_0(v20, 0, 0x50u);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 12;
  *((_DWORD *)v6 + 1) = 80;
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
0x1800164a0  push    rbx
0x1800164a2  push    rsi
0x1800164a3  push    rdi
0x1800164a4  push    r14
0x1800164a6  sub     rsp, 48h
0x1800164aa  xor     ebx, ebx
0x1800164ac  mov     rsi, rdx
0x1800164af  mov     [rsp+68h+arg_0], rbx
0x1800164b4  mov     rdi, rcx
0x1800164b7  mov     rcx, [rdi+68h]; this
0x1800164bb  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x1800164c0  mov     edx, 50h ; 'P'; unsigned int
0x1800164c5  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x1800164ca  mov     r14, [rsp+68h+arg_0]
0x1800164cf  test    eax, eax
0x1800164d1  jns     short loc_1800164FF
0x1800164d3  mov     rcx, rdi
0x1800164d6  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x1800164db  test    al, al
0x1800164dd  jnz     short loc_1800164F6
0x1800164df  mov     rcx, [rdi+70h]; hEvent
0x1800164e3  call    cs:__imp_SetEvent
0x1800164e9  mov     rcx, [rsp+68h]; this
0x1800164ee  test    eax, eax
0x1800164f0  jz      loc_18001668B
0x1800164f6  inc     ebx
0x1800164f8  cmp     ebx, 8
0x1800164fb  jb      short loc_1800164B7
0x1800164fd  jmp     short loc_18001655D
0x1800164ff  xor     edx, edx; Val
0x180016501  mov     rcx, r14; void *
0x180016504  lea     r8d, [rdx+50h]; Size
0x180016508  call    memset_0
0x18001650d  mov     rcx, [rsp+68h]; this
0x180016512  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180016519  mov     qword ptr [rsp+68h+var_40], rax; bool
0x18001651e  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016525  mov     r9d, 80004005h; char *
0x18001652b  mov     byte ptr [rsp+68h+var_48], 0; int
0x180016530  mov     edx, 130h; void *
0x180016535  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001653a  mov     dword ptr [r14], 0Ch
0x180016541  mov     dword ptr [r14+4], 50h ; 'P'
0x180016549  call    cs:__imp_GetCurrentProcessId
0x18001654f  mov     [r14+0Ch], eax
0x180016553  call    cs:__imp_GetCurrentThreadId
0x180016559  mov     [r14+8], eax
0x18001655d  mov     rcx, [rsp+68h]; this
0x180016562  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016569  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x18001656e  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016575  cmp     ebx, 8
0x180016578  mov     r9d, 800705B4h; char *
0x18001657e  mov     edx, 138h; void *
0x180016583  setz    al
0x180016586  mov     byte ptr [rsp+68h+var_48], al; int
0x18001658a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001658f  mov     ecx, 28h ; '('; Size
0x180016594  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016599  mov     [rsp+68h+arg_0], rax
0x18001659e  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800165a5  xorps   xmm0, xmm0
0x1800165a8  movups  xmmword ptr [rax], xmm0
0x1800165ab  mov     [rax], rcx
0x1800165ae  lea     rcx, [rax+10h]
0x1800165b2  mov     dword ptr [rax+8], 1
0x1800165b9  mov     dword ptr [rax+0Ch], 1
0x1800165c0  mov     qword ptr [rcx], 0
0x1800165c7  mov     qword ptr [rcx+8], 0
0x1800165cf  mov     [rcx+10h], r14
0x1800165d3  mov     [rsi], rcx
0x1800165d6  mov     [rsi+8], rax
0x1800165da  test    rcx, rcx
0x1800165dd  jz      loc_18001667E
0x1800165e3  mov     rdx, [rcx+8]
0x1800165e7  test    rdx, rdx
0x1800165ea  jz      short loc_1800165F6
0x1800165ec  cmp     dword ptr [rdx+8], 0
0x1800165f0  jnz     loc_18001667E
0x1800165f6  lock inc dword ptr [rax+8]
0x1800165fa  mov     rbx, [rsi+8]
0x1800165fe  xor     eax, eax
0x180016600  xor     r8d, r8d
0x180016603  test    rbx, rbx
0x180016606  jz      short loc_180016612
0x180016608  mov     rax, rcx
0x18001660b  mov     r8, rbx
0x18001660e  lock inc dword ptr [rbx+0Ch]
0x180016612  mov     rdx, [rcx+8]
0x180016616  or      r14d, 0FFFFFFFFh
0x18001661a  mov     [rcx], rax
0x18001661d  mov     [rcx+8], r8
0x180016621  test    rdx, rdx
0x180016624  jz      short loc_180016642
0x180016626  mov     eax, r14d
0x180016629  lock xadd [rdx+0Ch], eax
0x18001662e  add     eax, r14d
0x180016631  jnz     short loc_180016642
0x180016633  mov     rax, [rdx]
0x180016636  mov     rcx, rdx
0x180016639  mov     rax, [rax+8]
0x18001663d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016642  test    rbx, rbx
0x180016645  jz      short loc_18001667E
0x180016647  mov     eax, r14d
0x18001664a  lock xadd [rbx+8], eax
0x18001664f  add     eax, r14d
0x180016652  jnz     short loc_18001667E
0x180016654  mov     rax, [rbx]
0x180016657  mov     rcx, rbx
0x18001665a  mov     rax, [rax]
0x18001665d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016662  mov     eax, r14d
0x180016665  lock xadd [rbx+0Ch], eax
0x18001666a  add     eax, r14d
0x18001666d  jnz     short loc_18001667E
0x18001666f  mov     rax, [rbx]
0x180016672  mov     rcx, rbx
0x180016675  mov     rax, [rax+8]
0x180016679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001667e  mov     rax, rsi
0x180016681  add     rsp, 48h
0x180016685  pop     r14
0x180016687  pop     rdi
0x180016688  pop     rsi
0x180016689  pop     rbx
0x18001668a  retn
0x18001668b  mov     edx, 0A01h; void *
0x180016690  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
