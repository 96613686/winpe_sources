# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<uchar>(UMRDP_EVENT_TYPE,uint)

- ea: `0x1800156dc`
- end: `0x1800158dc`
- name: `??$AllocSharedBufEvent@E@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@E@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180019238`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x1800156dc`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015727`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001578d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001578d`

## string_xrefs

- `0x180015761`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x1800157b2`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<unsigned char>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4)
{
  int v4; // ebx
  size_t v5; // rbp
  int v8; // eax
  unsigned __int8 *v9; // r14
  unsigned int v10; // r8d
  const char *v11; // r9
  char *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // r8
  volatile signed __int32 *v18; // rdx
  int v20; // [rsp+20h] [rbp-38h]
  const char *v21; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int8 *v23; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  v5 = a4;
  v23 = 0;
  while ( 1 )
  {
    v8 = Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(
           *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
           v5,
           &v23);
    v9 = v23;
    if ( v8 >= 0 )
      break;
    if ( !(unsigned __int8)Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(a1)
      && !SetEvent(*(HANDLE *)(a1 + 112)) )
    {
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v10, v11);
    }
    if ( (unsigned int)++v4 >= 8 )
      goto LABEL_8;
  }
  memset_0(v23, 0, v5);
  LOBYTE(v20) = (unsigned int)v5 < 0x10;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v20,
    (bool)"Event buffer size is smaller than event header",
    v21);
  *(_DWORD *)v9 = 0;
  *((_DWORD *)v9 + 1) = v5;
  *((_DWORD *)v9 + 3) = GetCurrentProcessId();
  *((_DWORD *)v9 + 2) = GetCurrentThreadId();
LABEL_8:
  LOBYTE(v20) = v4 == 8;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x138,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x800705B4LL,
    v20,
    (bool)"Failed to allocate shared buffer event",
    v21);
  v12 = (char *)operator new(0x28u);
  v23 = (unsigned __int8 *)v12;
  *(_OWORD *)v12 = 0;
  *(_QWORD *)v12 = &std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable';
  v13 = v12 + 16;
  *((_DWORD *)v12 + 2) = 1;
  *((_DWORD *)v12 + 3) = 1;
  *((_QWORD *)v12 + 2) = 0;
  *((_QWORD *)v12 + 3) = 0;
  *((_QWORD *)v12 + 4) = v9;
  *a2 = v12 + 16;
  a2[1] = v12;
  if ( v12 != (char *)-16LL )
  {
    v14 = *((_QWORD *)v12 + 3);
    if ( !v14 || !*(_DWORD *)(v14 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v12 + 2);
      v15 = (volatile signed __int32 *)a2[1];
      v16 = 0;
      v17 = 0;
      if ( v15 )
      {
        v16 = v13;
        v17 = a2[1];
        _InterlockedIncrement(v15 + 3);
      }
      v18 = (volatile signed __int32 *)v13[1];
      *v13 = v16;
      v13[1] = v17;
      if ( v18 && _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800156dc  mov     [rsp+arg_8], rbx
0x1800156e1  mov     [rsp+arg_10], rbp
0x1800156e6  push    rsi
0x1800156e7  push    rdi
0x1800156e8  push    r14
0x1800156ea  sub     rsp, 40h
0x1800156ee  xor     ebx, ebx
0x1800156f0  mov     ebp, r9d
0x1800156f3  mov     [rsp+58h+arg_0], rbx
0x1800156f8  mov     rsi, rdx
0x1800156fb  mov     rdi, rcx
0x1800156fe  mov     rcx, [rdi+68h]; this
0x180015702  lea     r8, [rsp+58h+arg_0]; unsigned __int8 **
0x180015707  mov     edx, ebp; unsigned int
0x180015709  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x18001570e  mov     r14, [rsp+58h+arg_0]
0x180015713  test    eax, eax
0x180015715  jns     short loc_180015743
0x180015717  mov     rcx, rdi
0x18001571a  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x18001571f  test    al, al
0x180015721  jnz     short loc_18001573A
0x180015723  mov     rcx, [rdi+70h]; hEvent
0x180015727  call    cs:__imp_SetEvent
0x18001572d  mov     rcx, [rsp+58h]; this
0x180015732  test    eax, eax
0x180015734  jz      loc_1800158D1
0x18001573a  inc     ebx
0x18001573c  cmp     ebx, 8
0x18001573f  jb      short loc_1800156FE
0x180015741  jmp     short loc_1800157A1
0x180015743  mov     r8, rbp; Size
0x180015746  xor     edx, edx; Val
0x180015748  mov     rcx, r14; void *
0x18001574b  call    memset_0
0x180015750  mov     rcx, [rsp+58h]; this
0x180015755  lea     rdx, aEventBufferSiz; "Event buffer size is smaller than event"...
0x18001575c  mov     qword ptr [rsp+58h+var_30], rdx; bool
0x180015761  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015768  cmp     ebp, 10h
0x18001576b  mov     r9d, 80004005h; char *
0x180015771  mov     edx, 130h; void *
0x180015776  setb    al
0x180015779  mov     byte ptr [rsp+58h+var_38], al; int
0x18001577d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015782  mov     dword ptr [r14], 0
0x180015789  mov     [r14+4], ebp
0x18001578d  call    cs:__imp_GetCurrentProcessId
0x180015793  mov     [r14+0Ch], eax
0x180015797  call    cs:__imp_GetCurrentThreadId
0x18001579d  mov     [r14+8], eax
0x1800157a1  mov     rcx, [rsp+58h]; this
0x1800157a6  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x1800157ad  mov     qword ptr [rsp+58h+var_30], rdx; bool
0x1800157b2  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800157b9  cmp     ebx, 8
0x1800157bc  mov     r9d, 800705B4h; char *
0x1800157c2  mov     edx, 138h; void *
0x1800157c7  setz    al
0x1800157ca  mov     byte ptr [rsp+58h+var_38], al; int
0x1800157ce  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800157d3  mov     ecx, 28h ; '('; Size
0x1800157d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800157dd  mov     [rsp+58h+arg_0], rax
0x1800157e2  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800157e9  xorps   xmm0, xmm0
0x1800157ec  movups  xmmword ptr [rax], xmm0
0x1800157ef  mov     [rax], rcx
0x1800157f2  lea     rcx, [rax+10h]
0x1800157f6  mov     dword ptr [rax+8], 1
0x1800157fd  mov     dword ptr [rax+0Ch], 1
0x180015804  mov     qword ptr [rcx], 0
0x18001580b  mov     qword ptr [rcx+8], 0
0x180015813  mov     [rcx+10h], r14
0x180015817  mov     [rsi], rcx
0x18001581a  mov     [rsi+8], rax
0x18001581e  test    rcx, rcx
0x180015821  jz      loc_1800158BB
0x180015827  mov     rdx, [rcx+8]
0x18001582b  test    rdx, rdx
0x18001582e  jz      short loc_18001583A
0x180015830  cmp     dword ptr [rdx+8], 0
0x180015834  jnz     loc_1800158BB
0x18001583a  lock inc dword ptr [rax+8]
0x18001583e  mov     rbx, [rsi+8]
0x180015842  xor     eax, eax
0x180015844  xor     r8d, r8d
0x180015847  test    rbx, rbx
0x18001584a  jz      short loc_180015856
0x18001584c  mov     rax, rcx
0x18001584f  mov     r8, rbx
0x180015852  lock inc dword ptr [rbx+0Ch]
0x180015856  mov     rdx, [rcx+8]
0x18001585a  or      ebp, 0FFFFFFFFh
0x18001585d  mov     [rcx], rax
0x180015860  mov     [rcx+8], r8
0x180015864  test    rdx, rdx
0x180015867  jz      short loc_180015883
0x180015869  mov     eax, ebp
0x18001586b  lock xadd [rdx+0Ch], eax
0x180015870  add     eax, ebp
0x180015872  jnz     short loc_180015883
0x180015874  mov     rax, [rdx]
0x180015877  mov     rcx, rdx
0x18001587a  mov     rax, [rax+8]
0x18001587e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015883  test    rbx, rbx
0x180015886  jz      short loc_1800158BB
0x180015888  mov     eax, ebp
0x18001588a  lock xadd [rbx+8], eax
0x18001588f  add     eax, ebp
0x180015891  jnz     short loc_1800158BB
0x180015893  mov     rax, [rbx]
0x180015896  mov     rcx, rbx
0x180015899  mov     rax, [rax]
0x18001589c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158a1  mov     eax, ebp
0x1800158a3  lock xadd [rbx+0Ch], eax
0x1800158a8  add     eax, ebp
0x1800158aa  jnz     short loc_1800158BB
0x1800158ac  mov     rax, [rbx]
0x1800158af  mov     rcx, rbx
0x1800158b2  mov     rax, [rax+8]
0x1800158b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158bb  mov     rbx, [rsp+58h+arg_8]
0x1800158c0  mov     rax, rsi
0x1800158c3  mov     rbp, [rsp+58h+arg_10]
0x1800158c8  add     rsp, 40h
0x1800158cc  pop     r14
0x1800158ce  pop     rdi
0x1800158cf  pop     rsi
0x1800158d0  retn
0x1800158d1  mov     edx, 0A01h; void *
0x1800158d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
