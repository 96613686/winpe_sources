# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_FRAME_MARKER_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x180015ec8`
- end: `0x1800160b2`
- name: `??$AllocSharedBufEvent@UUMRDP_FRAME_MARKER_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_FRAME_MARKER_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180018f00`

## callees

- `0x1800065a4`
- `0x18000b07c`
- `0x1800146bc`
- `0x180015ec8`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015f0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015f78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015f78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015f6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015f6f`

## string_xrefs

- `0x180015f2b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180015f92`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_FRAME_MARKER_EVENT>(
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
           0x24u,
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
  *((_DWORD *)v6 + 8) = 0;
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 16;
  *((_DWORD *)v6 + 1) = 36;
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
0x180015ec8  push    rbx
0x180015eca  push    rbp
0x180015ecb  push    rsi
0x180015ecc  push    rdi
0x180015ecd  sub     rsp, 48h
0x180015ed1  xor     edi, edi
0x180015ed3  mov     rsi, rdx
0x180015ed6  mov     [rsp+68h+arg_0], rdi
0x180015edb  mov     rbp, rcx
0x180015ede  mov     rcx, [rbp+68h]; this
0x180015ee2  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x180015ee7  mov     edx, 24h ; '$'; unsigned int
0x180015eec  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x180015ef1  mov     rbx, [rsp+68h+arg_0]
0x180015ef6  test    eax, eax
0x180015ef8  jns     short loc_180015F26
0x180015efa  mov     rcx, rbp
0x180015efd  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x180015f02  test    al, al
0x180015f04  jnz     short loc_180015F1D
0x180015f06  mov     rcx, [rbp+70h]; hEvent
0x180015f0a  call    cs:__imp_SetEvent
0x180015f10  mov     rcx, [rsp+68h]; this
0x180015f15  test    eax, eax
0x180015f17  jz      loc_1800160A7
0x180015f1d  inc     edi
0x180015f1f  cmp     edi, 8
0x180015f22  jb      short loc_180015EDE
0x180015f24  jmp     short loc_180015F81
0x180015f26  mov     rcx, [rsp+68h]; this
0x180015f2b  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015f32  xorps   xmm0, xmm0
0x180015f35  xor     eax, eax
0x180015f37  movups  xmmword ptr [rbx], xmm0
0x180015f3a  mov     r9d, 80004005h; char *
0x180015f40  mov     edx, 130h; void *
0x180015f45  movups  xmmword ptr [rbx+10h], xmm0
0x180015f49  mov     [rbx+20h], eax
0x180015f4c  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180015f53  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180015f58  mov     byte ptr [rsp+68h+var_48], 0; int
0x180015f5d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015f62  mov     dword ptr [rbx], 10h
0x180015f68  mov     dword ptr [rbx+4], 24h ; '$'
0x180015f6f  call    cs:__imp_GetCurrentProcessId
0x180015f75  mov     [rbx+0Ch], eax
0x180015f78  call    cs:__imp_GetCurrentThreadId
0x180015f7e  mov     [rbx+8], eax
0x180015f81  mov     rcx, [rsp+68h]; this
0x180015f86  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180015f8d  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180015f92  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015f99  cmp     edi, 8
0x180015f9c  mov     r9d, 800705B4h; char *
0x180015fa2  mov     edx, 138h; void *
0x180015fa7  setz    al
0x180015faa  mov     byte ptr [rsp+68h+var_48], al; int
0x180015fae  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015fb3  mov     ecx, 28h ; '('; Size
0x180015fb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015fbd  mov     [rsp+68h+arg_0], rax
0x180015fc2  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x180015fc9  xorps   xmm0, xmm0
0x180015fcc  movups  xmmword ptr [rax], xmm0
0x180015fcf  mov     [rax], rcx
0x180015fd2  lea     rcx, [rax+10h]
0x180015fd6  mov     dword ptr [rax+8], 1
0x180015fdd  mov     dword ptr [rax+0Ch], 1
0x180015fe4  mov     qword ptr [rcx], 0
0x180015feb  mov     qword ptr [rcx+8], 0
0x180015ff3  mov     [rcx+10h], rbx
0x180015ff7  mov     [rsi], rcx
0x180015ffa  mov     [rsi+8], rax
0x180015ffe  test    rcx, rcx
0x180016001  jz      loc_18001609B
0x180016007  mov     rdx, [rcx+8]
0x18001600b  test    rdx, rdx
0x18001600e  jz      short loc_18001601A
0x180016010  cmp     dword ptr [rdx+8], 0
0x180016014  jnz     loc_18001609B
0x18001601a  lock inc dword ptr [rax+8]
0x18001601e  mov     rbx, [rsi+8]
0x180016022  xor     eax, eax
0x180016024  xor     r8d, r8d
0x180016027  test    rbx, rbx
0x18001602a  jz      short loc_180016036
0x18001602c  mov     rax, rcx
0x18001602f  mov     r8, rbx
0x180016032  lock inc dword ptr [rbx+0Ch]
0x180016036  mov     rdx, [rcx+8]
0x18001603a  or      ebp, 0FFFFFFFFh
0x18001603d  mov     [rcx], rax
0x180016040  mov     [rcx+8], r8
0x180016044  test    rdx, rdx
0x180016047  jz      short loc_180016063
0x180016049  mov     eax, ebp
0x18001604b  lock xadd [rdx+0Ch], eax
0x180016050  add     eax, ebp
0x180016052  jnz     short loc_180016063
0x180016054  mov     rax, [rdx]
0x180016057  mov     rcx, rdx
0x18001605a  mov     rax, [rax+8]
0x18001605e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016063  test    rbx, rbx
0x180016066  jz      short loc_18001609B
0x180016068  mov     eax, ebp
0x18001606a  lock xadd [rbx+8], eax
0x18001606f  add     eax, ebp
0x180016071  jnz     short loc_18001609B
0x180016073  mov     rax, [rbx]
0x180016076  mov     rcx, rbx
0x180016079  mov     rax, [rax]
0x18001607c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016081  mov     eax, ebp
0x180016083  lock xadd [rbx+0Ch], eax
0x180016088  add     eax, ebp
0x18001608a  jnz     short loc_18001609B
0x18001608c  mov     rax, [rbx]
0x18001608f  mov     rcx, rbx
0x180016092  mov     rax, [rax+8]
0x180016096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001609b  mov     rax, rsi
0x18001609e  add     rsp, 48h
0x1800160a2  pop     rdi
0x1800160a3  pop     rsi
0x1800160a4  pop     rbp
0x1800160a5  pop     rbx
0x1800160a6  retn
0x1800160a7  mov     edx, 0A01h; void *
0x1800160ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
