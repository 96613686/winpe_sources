# GameInputServer::BufferListEntry::Create(GameInputServerDevice *,ISIPCEndpoint *,SIPC_CLIENT_INFO const *,HKL__ *,GameInputServer::BufferListEntry * *)

- ea: `0x18002f774`
- end: `0x18002fc9b`
- name: `?Create@BufferListEntry@GameInputServer@@SAJPEAVGameInputServerDevice@@PEAUISIPCEndpoint@@PEBUSIPC_CLIENT_INFO@@PEAUHKL__@@PEAPEAU12@@Z`
- size: `1319`
- prototype: `__int64 __fastcall(struct GameInputServerDevice *this, struct ISIPCEndpoint *, const struct SIPC_CLIENT_INFO *, HKL, struct GameInputServer::BufferListEntry **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003dc00`
- `0x18003ee94`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18000d414`
- `0x1800239a4`
- `0x180023e1c`
- `0x18002d50c`
- `0x18002eef4`
- `0x18002f774`
- `0x18003c208`
- `0x1800401cc`
- `0x18004c8a5`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002f7c1`
- `ntdll!RtlAllocateHeap` at `0x18002f7c1`

## pseudocode

```c
__int64 __fastcall GameInputServer::BufferListEntry::Create(
        struct GameInputServerDevice *this,
        struct ISIPCEndpoint *a2,
        const struct SIPC_CLIENT_INFO *a3,
        HKL a4,
        struct GameInputServer::BufferListEntry **a5)
{
  struct _PEB *v6; // rcx
  char *Heap; // rax
  int v10; // r8d
  int v11; // r9d
  char *v12; // rbx
  unsigned int *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r9
  int v16; // edi
  int v17; // r9d
  int v18; // r8d
  int v19; // ecx
  int *v20; // rdx
  struct SharedBufferLayout *v21; // rsi
  TimestampConverter *v22; // rcx
  __int64 v23; // r11
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rax
  __int64 v26; // r11
  unsigned int v27; // edi
  char v28; // al
  unsigned int *v29; // r12
  const struct std::nothrow_t *v30; // rdx
  int v31; // esi
  int v32; // r9d
  const struct std::nothrow_t *v33; // rdx
  struct ReadingPool *v35; // r15
  _QWORD **v36; // r14
  _QWORD *v37; // rsi
  void *v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // rcx
  __int64 v41; // rax
  KeyboardLookupTable *v42; // rsi
  unsigned int *v43; // rax
  unsigned int i; // ecx
  unsigned int j; // edx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  _DWORD *v49; // rdx
  char v50; // si
  unsigned __int64 v51; // rdx
  const struct std::nothrow_t *v52; // rdx
  _QWORD *v53; // rdi
  void *v54; // rcx
  struct ReadingPool *v55; // [rsp+40h] [rbp-20h] BYREF
  void *v56; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v57[2]; // [rsp+50h] [rbp-10h] BYREF

  v6 = NtCurrentPeb();
  *a5 = 0;
  Heap = (char *)RtlAllocateHeap(v6->ProcessHeap, 0, 0xA8u);
  v12 = Heap;
  if ( Heap )
  {
    *((_QWORD *)Heap + 3) = 0;
    *((_QWORD *)Heap + 2) = 0;
    *((_QWORD *)Heap + 4) = 0;
    *((_QWORD *)Heap + 5) = 0;
    *((_QWORD *)Heap + 6) = 0;
    *((_QWORD *)Heap + 7) = 0;
    *((_QWORD *)Heap + 8) = 0;
    *((_QWORD *)Heap + 9) = 21;
    *((_QWORD *)Heap + 10) = 0;
    *((_OWORD *)Heap + 6) = 0;
    *((_OWORD *)Heap + 7) = 0;
    *((_QWORD *)Heap + 16) = 0;
    *(_OWORD *)(Heap + 136) = 0;
    Heap[152] = 0;
    *((_DWORD *)Heap + 39) = 0;
    *((_WORD *)Heap + 80) = 0;
    v13 = (unsigned int *)*((_QWORD *)this + 18);
    v14 = *(_QWORD *)a2;
    v15 = *((_QWORD *)this + 11);
    v56 = 0;
    v16 = (*(__int64 (__fastcall **)(struct ISIPCEndpoint *, _QWORD, __int64, __int64, void **))(v14 + 24))(
            a2,
            *v13,
            32,
            v15 + 32,
            &v56);
    if ( v16 < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_23;
      v18 = qword_180069018;
      v19 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_23;
      LODWORD(v55) = 2226;
      v20 = (int *)byte_18006281B;
LABEL_7:
      v57[0] = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
      LODWORD(a5) = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v19,
        (_DWORD)v20,
        v18,
        v17,
        (__int64)v57,
        (__int64)&v55,
        (__int64)&a5);
LABEL_23:
      GameInputServer::BufferListEntry::~BufferListEntry((GameInputServer::BufferListEntry *)v12);
      operator delete(v12, v33);
      return (unsigned int)v16;
    }
    (*(void (__fastcall **)(struct ISIPCEndpoint *))(*(_QWORD *)a2 + 8LL))(a2);
    *((_QWORD *)v12 + 2) = this;
    *((_QWORD *)v12 + 6) = a2;
    v21 = GameInputServerDevice::InitializeBuffer(this, v56, a3);
    *((_QWORD *)v12 + 7) = v21;
    v22 = (TimestampConverter *)*((unsigned int *)a3 + 8);
    *((_DWORD *)v12 + 19) = (_DWORD)v22;
    v23 = *((_QWORD *)a3 + 5);
    v57[0] = v12 + 56;
    if ( v23 < 0 )
    {
      if ( v23 == 0x8000000000000000uLL )
        v24 = 0x8000000000000000uLL;
      else
        v24 = -v23;
    }
    else
    {
      v24 = v23;
    }
    v25 = TimestampConverter::PerformanceCountToMicroseconds(v22, v24);
    if ( v26 < 0 )
    {
      if ( v25 > 0x7FFFFFFFFFFFFFFFLL )
        v25 = 0x8000000000000000uLL;
      else
        v25 = -(__int64)v25;
    }
    *((_QWORD *)v12 + 10) = v25;
    v27 = 1;
    v12[88] = *((_BYTE *)a3 + 48);
    v28 = *((_BYTE *)a3 + 49) & 1;
    v55 = 0;
    v12[161] = v28;
    v29 = (unsigned int *)(((unsigned __int64)v21 + *((unsigned int *)v21 + 4)) & -(__int64)(*((_DWORD *)v21 + 4) != 0));
    v31 = ReadingPool::Create(v29, (const struct InputDataLayout *)v29, &v55);
    if ( v31 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        LODWORD(a5) = v31;
        v57[0] = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
        LODWORD(v55) = 2241;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)&dword_180061AF4,
          qword_180069018,
          v32,
          (__int64)v57,
          (__int64)&v55,
          (__int64)&a5);
      }
      v16 = v31;
      goto LABEL_23;
    }
    v35 = v55;
    v36 = (_QWORD **)(v12 + 24);
    v37 = (_QWORD *)*((_QWORD *)v12 + 3);
    *((_QWORD *)v12 + 3) = v55;
    if ( v37 )
    {
      v38 = (void *)v37[6];
      if ( v38 )
        operator delete(v38, v30);
      operator delete(v37, v30);
    }
    GameInputServerDevice::AddRestReadingToBuffer(
      this,
      v35,
      *((_QWORD *)v12 + 10),
      (struct GameInputMouseState *)(v12 + 96));
    v39 = v29[5];
    v40 = (unsigned __int64)v29 + v39;
    v41 = -v39;
    v42 = (KeyboardLookupTable *)(v40 & -(__int64)(v41 != 0));
    if ( v42 )
    {
      *(_QWORD *)((v40 & -(__int64)(v41 != 0)) + 0xC00) = 0;
      memset_0((void *)(v40 & -(__int64)(v41 != 0)), 0, 0xC00u);
      v43 = (unsigned int *)((char *)v42 + 12);
      for ( i = 1; i <= 0x7F; ++i )
      {
        *v43 = i;
        v43 += 3;
      }
      for ( j = 57345; j <= 0xE07F; ++j )
      {
        *v43 = j;
        v43 += 3;
      }
      *v43 = 57629;
      KeyboardLookupTable::Initialize(v42, a4);
    }
    v46 = *(unsigned int *)(*(_QWORD *)v57[0] + 12LL);
    v47 = v46 + *(_QWORD *)v57[0];
    v48 = -v46;
    if ( (v47 & -(__int64)(v48 != 0)) != 0 )
      *((_QWORD *)v12 + 4) = ((v47 & -(__int64)(v48 != 0)) + *(unsigned int *)((v47 & -(__int64)(v48 != 0)) + 8))
                           & ((unsigned __int128)-(__int128)*(unsigned int *)((v47 & -(__int64)(v48 != 0)) + 8) >> 64);
    v49 = (_DWORD *)(((unsigned __int64)v29 + v29[10]) & ((unsigned __int128)-(__int128)v29[10] >> 64));
    *((_QWORD *)v12 + 5) = v49;
    *v49 = *((_DWORD *)v12 + 18);
    _mm_mfence();
    v50 = *((_BYTE *)a3 + 49);
    if ( !(*(unsigned __int8 (__fastcall **)(struct ISIPCEndpoint *))(*(_QWORD *)a2 + 80LL))(a2)
      || !*((_BYTE *)this + 227)
      || (v50 & 1) != 0 )
    {
      v27 = 0;
    }
    v16 = (*(__int64 (__fastcall **)(struct ISIPCEndpoint *, void *, _QWORD, char *))(*(_QWORD *)a2 + 40LL))(
            a2,
            v56,
            v27,
            v12 + 64);
    if ( v16 < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_23;
      v18 = qword_180069018;
      v19 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_23;
      LODWORD(v55) = 2278;
      v20 = &dword_18005F8DC;
      goto LABEL_7;
    }
    v51 = *((_QWORD *)v12 + 8);
    if ( v51 )
    {
      if ( (int)GameInputServerDevice::SendDriverOffloadRequest(this, v51, *((_DWORD *)a3 + 8), 0) >= 0 )
      {
        v53 = *v36;
        *v36 = 0;
        if ( v53 )
        {
          v54 = (void *)v53[6];
          if ( v54 )
            operator delete(v54, v52);
          operator delete(v53, v52);
        }
      }
    }
    *a5 = (struct GameInputServer::BufferListEntry *)v12;
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      LODWORD(a5) = -2147024882;
      LODWORD(v55) = 2217;
      v57[0] = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)v57,
        (unsigned int)&byte_180062447,
        v10,
        v11,
        (__int64)v57,
        (__int64)&v55,
        (__int64)&a5);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002f774  mov     rax, rsp
0x18002f777  mov     [rax+8], rbx
0x18002f77b  mov     [rax+20h], r9
0x18002f77f  mov     [rax+18h], r8
0x18002f783  mov     [rax+10h], rdx
0x18002f787  push    rbp
0x18002f788  push    rsi
0x18002f789  push    rdi
0x18002f78a  push    r12
0x18002f78c  push    r13
0x18002f78e  push    r14
0x18002f790  push    r15
0x18002f792  mov     rbp, rsp
0x18002f795  sub     rsp, 60h
0x18002f799  mov     rax, [rbp+arg_20]
0x18002f79d  mov     r13, rcx
0x18002f7a0  mov     rcx, gs:60h
0x18002f7a9  mov     r14, r8
0x18002f7ac  mov     rsi, rdx
0x18002f7af  xor     r15d, r15d
0x18002f7b2  xor     edx, edx; Flags
0x18002f7b4  mov     r8d, 0A8h; Size
0x18002f7ba  mov     [rax], r15
0x18002f7bd  mov     rcx, [rcx+30h]; HeapHandle
0x18002f7c1  call    cs:__imp_RtlAllocateHeap
0x18002f7c8  nop     dword ptr [rax+rax+00h]
0x18002f7cd  mov     rbx, rax
0x18002f7d0  test    rax, rax
0x18002f7d3  jz      loc_18002FC11
0x18002f7d9  mov     [rax+18h], r15
0x18002f7dd  lea     r8d, [r15+20h]
0x18002f7e1  mov     [rax+10h], r15
0x18002f7e5  xorps   xmm0, xmm0
0x18002f7e8  mov     [rax+20h], r15
0x18002f7ec  mov     [rax+28h], r15
0x18002f7f0  mov     [rax+30h], r15
0x18002f7f4  mov     [rax+38h], r15
0x18002f7f8  mov     [rax+40h], r15
0x18002f7fc  mov     qword ptr [rax+48h], 15h
0x18002f804  mov     [rax+50h], r15
0x18002f808  xor     eax, eax
0x18002f80a  movups  xmmword ptr [rbx+60h], xmm0
0x18002f80e  movups  xmmword ptr [rbx+70h], xmm0
0x18002f812  mov     [rbx+80h], rax
0x18002f819  movups  xmmword ptr [rbx+88h], xmm0
0x18002f820  mov     [rbx+98h], r15b
0x18002f827  mov     [rbx+9Ch], r15d
0x18002f82e  mov     [rbx+0A0h], r15w
0x18002f836  mov     rax, [r13+90h]
0x18002f83d  mov     rcx, [rsi]
0x18002f840  mov     r9, [r13+58h]
0x18002f844  mov     [rbp+var_18], r15
0x18002f848  add     r9, r8
0x18002f84b  mov     edx, [rax]
0x18002f84d  mov     rax, [rcx+18h]
0x18002f851  lea     rcx, [rbp+var_18]
0x18002f855  mov     [rsp+60h+var_40], rcx
0x18002f85a  mov     rcx, rsi
0x18002f85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f862  mov     edi, eax
0x18002f864  test    eax, eax
0x18002f866  jns     short loc_18002F8E3
0x18002f868  mov     ecx, cs:dword_180069000
0x18002f86e  cmp     ecx, 2
0x18002f871  jbe     loc_18002FA1D
0x18002f877  mov     r8, cs:qword_180069018
0x18002f87e  mov     edx, 400h
0x18002f883  mov     rcx, cs:qword_180069010
0x18002f88a  test    rdx, rcx
0x18002f88d  jz      loc_18002FA1D
0x18002f893  mov     rax, r8
0x18002f896  and     rax, rdx
0x18002f899  cmp     rax, r8
0x18002f89c  jnz     loc_18002FA1D
0x18002f8a2  mov     dword ptr [rbp+var_20], 8B2h
0x18002f8a9  lea     rdx, byte_18006281B
0x18002f8b0  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18002f8b7  mov     [rbp+var_10], rax
0x18002f8bb  lea     rax, [rbp+arg_20]
0x18002f8bf  mov     [rsp+60h+var_30], rax
0x18002f8c4  lea     rax, [rbp+var_20]
0x18002f8c8  mov     [rsp+60h+var_38], rax
0x18002f8cd  lea     rax, [rbp+var_10]
0x18002f8d1  mov     [rsp+60h+var_40], rax
0x18002f8d6  mov     dword ptr [rbp+arg_20], edi
0x18002f8d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002f8de  jmp     loc_18002FA1D
0x18002f8e3  mov     rax, [rsi]
0x18002f8e6  mov     rcx, rsi
0x18002f8e9  mov     rax, [rax+8]
0x18002f8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8f2  mov     [rbx+10h], r13
0x18002f8f6  mov     r8, r14; struct SIPC_CLIENT_INFO *
0x18002f8f9  mov     [rbx+30h], rsi
0x18002f8fd  mov     rcx, r13; this
0x18002f900  mov     rdx, [rbp+var_18]; void *
0x18002f904  call    ?InitializeBuffer@GameInputServerDevice@@QEAAPEAVSharedBufferLayout@@PEAXPEBUSIPC_CLIENT_INFO@@@Z; GameInputServerDevice::InitializeBuffer(void *,SIPC_CLIENT_INFO const *)
0x18002f909  mov     rsi, rax
0x18002f90c  mov     rdi, 8000000000000000h
0x18002f916  lea     rax, [rbx+38h]
0x18002f91a  mov     [rax], rsi
0x18002f91d  mov     ecx, [r14+20h]; this
0x18002f921  mov     [rbx+4Ch], ecx
0x18002f924  mov     r11, [r14+28h]
0x18002f928  mov     [rbp+var_10], rax
0x18002f92c  test    r11, r11
0x18002f92f  js      short loc_18002F936
0x18002f931  mov     rdx, r11
0x18002f934  jmp     short loc_18002F946
0x18002f936  cmp     r11, rdi
0x18002f939  jle     short loc_18002F943
0x18002f93b  mov     rdx, r11
0x18002f93e  neg     rdx
0x18002f941  jmp     short loc_18002F946
0x18002f943  mov     rdx, rdi; unsigned __int64
0x18002f946  call    ?PerformanceCountToMicroseconds@TimestampConverter@@QEBA_K_K@Z; TimestampConverter::PerformanceCountToMicroseconds(unsigned __int64)
0x18002f94b  test    r11, r11
0x18002f94e  jns     short loc_18002F967
0x18002f950  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18002f95a  cmp     rax, rcx
0x18002f95d  ja      short loc_18002F964
0x18002f95f  neg     rax
0x18002f962  jmp     short loc_18002F967
0x18002f964  mov     rax, rdi
0x18002f967  mov     [rbx+50h], rax
0x18002f96b  lea     r8, [rbp+var_20]; struct ReadingPool **
0x18002f96f  mov     al, [r14+30h]
0x18002f973  mov     edi, 1
0x18002f978  mov     [rbx+58h], al
0x18002f97b  mov     al, [r14+31h]
0x18002f97f  and     al, dil
0x18002f982  mov     [rbp+var_20], r15
0x18002f986  mov     [rbx+0A1h], al
0x18002f98c  mov     eax, [rsi+10h]
0x18002f98f  lea     rcx, [rsi+rax]
0x18002f993  neg     rax
0x18002f996  sbb     r12, r12
0x18002f999  and     r12, rcx
0x18002f99c  mov     rdx, r12; struct InputDataLayout *
0x18002f99f  mov     rcx, r12; void *
0x18002f9a2  call    ?Create@ReadingPool@@SAJPEAXPEBVInputDataLayout@@PEAPEAV1@@Z; ReadingPool::Create(void *,InputDataLayout const *,ReadingPool * *)
0x18002f9a7  mov     esi, eax
0x18002f9a9  test    eax, eax
0x18002f9ab  jns     loc_18002FA34
0x18002f9b1  mov     ecx, cs:dword_180069000
0x18002f9b7  cmp     ecx, 2
0x18002f9ba  jbe     short loc_18002FA1B
0x18002f9bc  mov     r8, cs:qword_180069018
0x18002f9c3  mov     edx, 400h
0x18002f9c8  mov     rcx, cs:qword_180069010
0x18002f9cf  test    rdx, rcx
0x18002f9d2  jz      short loc_18002FA1B
0x18002f9d4  mov     rax, r8
0x18002f9d7  and     rax, rdx
0x18002f9da  cmp     rax, r8
0x18002f9dd  jnz     short loc_18002FA1B
0x18002f9df  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18002f9e6  mov     dword ptr [rbp+arg_20], esi
0x18002f9e9  mov     [rbp+var_10], rax
0x18002f9ed  lea     rdx, dword_180061AF4
0x18002f9f4  lea     rax, [rbp+arg_20]
0x18002f9f8  mov     dword ptr [rbp+var_20], 8C1h
0x18002f9ff  mov     [rsp+60h+var_30], rax
0x18002fa04  lea     rax, [rbp+var_20]
0x18002fa08  mov     [rsp+60h+var_38], rax
0x18002fa0d  lea     rax, [rbp+var_10]
0x18002fa11  mov     [rsp+60h+var_40], rax
0x18002fa16  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002fa1b  mov     edi, esi
0x18002fa1d  mov     rcx, rbx; this
0x18002fa20  call    ??1BufferListEntry@GameInputServer@@QEAA@XZ; GameInputServer::BufferListEntry::~BufferListEntry(void)
0x18002fa25  mov     rcx, rbx; P
0x18002fa28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002fa2d  mov     eax, edi
0x18002fa2f  jmp     loc_18002FC82
0x18002fa34  mov     r15, [rbp+var_20]
0x18002fa38  lea     r14, [rbx+18h]
0x18002fa3c  mov     rsi, [r14]
0x18002fa3f  mov     [r14], r15
0x18002fa42  test    rsi, rsi
0x18002fa45  jz      short loc_18002FA5D
0x18002fa47  mov     rcx, [rsi+30h]; P
0x18002fa4b  test    rcx, rcx
0x18002fa4e  jz      short loc_18002FA55
0x18002fa50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002fa55  mov     rcx, rsi; P
0x18002fa58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002fa5d  mov     r8, [rbx+50h]; unsigned __int64
0x18002fa61  lea     r9, [rbx+60h]; struct GameInputMouseState *
0x18002fa65  mov     rdx, r15; struct ReadingPool *
0x18002fa68  mov     rcx, r13; this
0x18002fa6b  call    ?AddRestReadingToBuffer@GameInputServerDevice@@QEAAXPEAVReadingPool@@_KAEAUGameInputMouseState@@@Z; GameInputServerDevice::AddRestReadingToBuffer(ReadingPool *,unsigned __int64,GameInputMouseState &)
0x18002fa70  mov     eax, [r12+14h]
0x18002fa75  lea     rcx, [rax+r12]
0x18002fa79  neg     rax
0x18002fa7c  sbb     rsi, rsi
0x18002fa7f  and     rsi, rcx
0x18002fa82  jz      short loc_18002FAD9
0x18002fa84  xor     edx, edx; Val
0x18002fa86  mov     qword ptr [rsi+0C00h], 0
0x18002fa91  mov     r8d, 0C00h; Size
0x18002fa97  mov     rcx, rsi; void *
0x18002fa9a  call    memset_0
0x18002fa9f  lea     rax, [rsi+0Ch]
0x18002faa3  mov     ecx, edi
0x18002faa5  mov     [rax], ecx
0x18002faa7  add     rax, 0Ch
0x18002faab  add     ecx, edi
0x18002faad  cmp     ecx, 7Fh
0x18002fab0  jbe     short loc_18002FAA5
0x18002fab2  mov     edx, 0E001h
0x18002fab7  mov     [rax], edx
0x18002fab9  add     edx, edi
0x18002fabb  lea     rax, [rax+0Ch]
0x18002fabf  cmp     edx, 0E07Fh
0x18002fac5  jbe     short loc_18002FAB7
0x18002fac7  mov     rdx, [rbp+arg_18]; HKL
0x18002facb  mov     rcx, rsi; this
0x18002face  mov     dword ptr [rax], 0E11Dh
0x18002fad4  call    ?Initialize@KeyboardLookupTable@@QEAAXPEAUHKL__@@@Z; KeyboardLookupTable::Initialize(HKL__ *)
0x18002fad9  mov     rax, [rbp+var_10]
0x18002fadd  mov     rax, [rax]
0x18002fae0  mov     ecx, [rax+0Ch]
0x18002fae3  lea     rdx, [rcx+rax]
0x18002fae7  neg     rcx
0x18002faea  sbb     r8, r8
0x18002faed  and     r8, rdx
0x18002faf0  jz      short loc_18002FB07
0x18002faf2  mov     eax, [r8+8]
0x18002faf6  lea     rcx, [r8+rax]
0x18002fafa  neg     rax
0x18002fafd  sbb     rdx, rdx
0x18002fb00  and     rdx, rcx
0x18002fb03  mov     [rbx+20h], rdx
0x18002fb07  mov     eax, [r12+28h]
0x18002fb0c  lea     rcx, [rax+r12]
0x18002fb10  neg     rax
0x18002fb13  sbb     rdx, rdx
0x18002fb16  and     rdx, rcx
0x18002fb19  mov     [rbx+28h], rdx
0x18002fb1d  mov     eax, [rbx+48h]
0x18002fb20  nop
0x18002fb21  mov     [rdx], eax
0x18002fb23  mfence
0x18002fb26  mov     r15, [rbp+arg_8]
0x18002fb2a  mov     r12, [rbp+arg_10]
0x18002fb2e  mov     rcx, r15
0x18002fb31  mov     rax, [r15]
0x18002fb34  mov     sil, [r12+31h]
0x18002fb39  mov     rax, [rax+50h]
0x18002fb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb42  test    al, al
0x18002fb44  jz      short loc_18002FB55
0x18002fb46  cmp     byte ptr [r13+0E3h], 0
0x18002fb4e  jz      short loc_18002FB55
0x18002fb50  test    dil, sil
0x18002fb53  jz      short loc_18002FB57
0x18002fb55  xor     edi, edi
0x18002fb57  mov     rax, [r15]
0x18002fb5a  lea     r9, [rbx+40h]
0x18002fb5e  mov     rdx, [rbp+var_18]
0x18002fb62  mov     r8d, edi
0x18002fb65  mov     rcx, r15
0x18002fb68  mov     rax, [rax+28h]
0x18002fb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb71  mov     edi, eax
0x18002fb73  test    eax, eax
0x18002fb75  jns     short loc_18002FBC4
0x18002fb77  mov     ecx, cs:dword_180069000
0x18002fb7d  cmp     ecx, 2
0x18002fb80  jbe     loc_18002FA1D
0x18002fb86  mov     r8, cs:qword_180069018
0x18002fb8d  mov     edx, 400h
0x18002fb92  mov     rcx, cs:qword_180069010
0x18002fb99  test    rdx, rcx
0x18002fb9c  jz      loc_18002FA1D
0x18002fba2  mov     rax, r8
0x18002fba5  and     rax, rdx
0x18002fba8  cmp     rax, r8
0x18002fbab  jnz     loc_18002FA1D
0x18002fbb1  mov     dword ptr [rbp+var_20], 8E6h
0x18002fbb8  lea     rdx, dword_18005F8DC
0x18002fbbf  jmp     loc_18002F8B0
0x18002fbc4  mov     rdx, [rbx+40h]; unsigned __int64
0x18002fbc8  test    rdx, rdx
0x18002fbcb  jz      short loc_18002FC06
0x18002fbcd  mov     r8d, [r12+20h]; unsigned int
0x18002fbd2  xor     r9d, r9d; bool
0x18002fbd5  mov     rcx, r13; this
0x18002fbd8  call    ?SendDriverOffloadRequest@GameInputServerDevice@@QEAAJ_KK_N@Z; GameInputServerDevice::SendDriverOffloadRequest(unsigned __int64,ulong,bool)
0x18002fbdd  test    eax, eax
0x18002fbdf  js      short loc_18002FC06
0x18002fbe1  mov     rdi, [r14]
0x18002fbe4  mov     qword ptr [r14], 0
0x18002fbeb  test    rdi, rdi
0x18002fbee  jz      short loc_18002FC06
0x18002fbf0  mov     rcx, [rdi+30h]; P
0x18002fbf4  test    rcx, rcx
0x18002fbf7  jz      short loc_18002FBFE
0x18002fbf9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
  ... truncated ...
```
