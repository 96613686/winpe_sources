# CMPEG2DemuxInputPin::CompleteConnect(IPin *)

- ea: `0x18001ac30`
- end: `0x18001ae8c`
- name: `?CompleteConnect@CMPEG2DemuxInputPin@@UEAAJPEAUIPin@@@Z`
- size: `604`
- prototype: `int(CMPEG2DemuxInputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180006f90`
- `0x18001376c`
- `0x180015260`
- `0x180016e80`
- `0x18001ac30`
- `0x18001ae94`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2DemuxInputPin::CompleteConnect(CMPEG2DemuxInputPin *this, struct IUnknown *a2)
{
  __int64 v2; // rax
  int inited; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  CAMThread *v8; // rax
  int *v9; // rdx
  CAMThread *v10; // rdi
  struct IMemAllocator *v11; // r8
  int v12; // r9d
  unsigned int v13; // eax
  unsigned int *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  CMPEG2Demultiplexer *v18; // rcx
  __int64 v19; // rax
  struct IAsyncReader *v21; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 10);
  v21 = 0;
  inited = 0;
  v6 = *(_QWORD *)(v2 + 336);
  if ( !v6
    || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 88LL))(v6)
    || ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IAsyncReader **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IAsyncReader,
         &v21) < 0 )
  {
    goto LABEL_12;
  }
  inited = CMPEG2Demultiplexer::InitPullModeStream(*((CMPEG2Demultiplexer **)this + 10), v21);
  ((void (__fastcall *)(struct IAsyncReader *))v21->lpVtbl->Release)(v21);
  if ( inited >= 0 )
  {
    v7 = *((_QWORD *)this + 38);
    if ( v7 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, 1);
    *((_QWORD *)this + 38) = 0;
    v8 = (CAMThread *)operator new(0xD0u);
    v10 = v8;
    if ( !v8 )
    {
      *((_QWORD *)this + 38) = 0;
      inited = -2147024882;
      goto LABEL_27;
    }
    CAMThread::CAMThread(v8, v9);
    *((_QWORD *)v10 + 15) = 0;
    *(_QWORD *)v10 = &CStreamPull::`vftable';
    *((_QWORD *)v10 + 19) = 0;
    *((_QWORD *)v10 + 24) = -1;
    *((_QWORD *)v10 + 25) = -1;
    *(_QWORD *)((char *)v10 + 164) = 0;
    *(_QWORD *)((char *)v10 + 172) = 0;
    *((_DWORD *)v10 + 45) = 2;
    *((_QWORD *)v10 + 23) = this;
    v11 = (struct IMemAllocator *)*((_QWORD *)this + 28);
    *((_QWORD *)this + 38) = v10;
    inited = CMp2PullPin::Connect(v10, a2, v11, v12);
    if ( inited >= 0 )
    {
LABEL_12:
      if ( *((_QWORD *)this + 13) == *(_QWORD *)&MEDIATYPE_Stream.Data1
        && *((_QWORD *)this + 14) == *(_QWORD *)MEDIATYPE_Stream.Data4
        && *((_QWORD *)this + 15) == *(_QWORD *)&MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE.Data1
        && *((_QWORD *)this + 16) == *(_QWORD *)MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE.Data4 )
      {
        if ( *((_QWORD *)this + 13) != *(_QWORD *)&MEDIATYPE_Stream.Data1
          || *((_QWORD *)this + 14) != *(_QWORD *)MEDIATYPE_Stream.Data4
          || *((_QWORD *)this + 15) != *(_QWORD *)&MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE.Data1
          || *((_QWORD *)this + 16) != *(_QWORD *)MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE.Data4 )
        {
          inited = -2147467259;
          goto LABEL_27;
        }
        v13 = *((_DWORD *)this + 44);
        if ( v13 )
        {
          if ( v13 < 0xC
            || (v14 = (unsigned int *)*((_QWORD *)this + 23), v15 = *v14, (int)v15 < 0)
            || (v16 = v14[2] - (unsigned int)v15 - 188, (int)v16 < 0) )
          {
            inited = -2147024809;
            goto LABEL_27;
          }
        }
        else
        {
          v15 = 0;
          v16 = 0;
        }
        inited = 0;
        v17 = *(_QWORD *)(*((_QWORD *)this + 10) + 336LL);
        if ( v17 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v17 + 80LL))(v17, v15, v16);
      }
    }
  }
LABEL_27:
  v18 = (CMPEG2Demultiplexer *)*((_QWORD *)this + 10);
  v19 = *((_QWORD *)v18 + 42);
  if ( !v19 || !*(_DWORD *)(v19 + 176) )
  {
    CMPEG2Demultiplexer::RegisterWithBDANetworkProvider(v18);
    CMPEG2Demultiplexer::ConnectESEvents(*((struct _RTL_CRITICAL_SECTION **)this + 10));
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001ac30  mov     [rsp+arg_8], rbx
0x18001ac35  mov     [rsp+arg_10], rsi
0x18001ac3a  push    rdi
0x18001ac3b  sub     rsp, 20h
0x18001ac3f  mov     rax, [rcx+50h]
0x18001ac43  mov     rbx, rcx
0x18001ac46  mov     [rsp+28h+arg_0], 0
0x18001ac4f  xor     edi, edi
0x18001ac51  mov     rsi, rdx
0x18001ac54  mov     rcx, [rax+150h]
0x18001ac5b  test    rcx, rcx
0x18001ac5e  jz      loc_18001AD82
0x18001ac64  mov     rax, [rcx]
0x18001ac67  mov     rax, [rax+58h]
0x18001ac6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac70  test    eax, eax
0x18001ac72  jz      loc_18001AD82
0x18001ac78  mov     rax, [rsi]
0x18001ac7b  lea     r8, [rsp+28h+arg_0]
0x18001ac80  lea     rdx, IID_IAsyncReader
0x18001ac87  mov     rcx, rsi
0x18001ac8a  mov     rax, [rax]
0x18001ac8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac92  test    eax, eax
0x18001ac94  js      loc_18001AD82
0x18001ac9a  mov     rdx, [rsp+28h+arg_0]; struct IAsyncReader *
0x18001ac9f  mov     rcx, [rbx+50h]; this
0x18001aca3  call    ?InitPullModeStream@CMPEG2Demultiplexer@@QEAAJPEAUIAsyncReader@@@Z; CMPEG2Demultiplexer::InitPullModeStream(IAsyncReader *)
0x18001aca8  mov     rcx, [rsp+28h+arg_0]
0x18001acad  mov     edi, eax
0x18001acaf  mov     rdx, [rcx]
0x18001acb2  mov     rax, [rdx+10h]
0x18001acb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acbb  test    edi, edi
0x18001acbd  js      loc_18001AE53
0x18001acc3  mov     rcx, [rbx+130h]
0x18001acca  test    rcx, rcx
0x18001accd  jz      short loc_18001ACE0
0x18001accf  mov     rax, [rcx]
0x18001acd2  mov     edx, 1
0x18001acd7  mov     rax, [rax+8]
0x18001acdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ace0  mov     ecx, 0D0h; Size
0x18001ace5  mov     qword ptr [rbx+130h], 0
0x18001acf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001acf5  mov     rdi, rax
0x18001acf8  test    rax, rax
0x18001acfb  jz      loc_18001AE17
0x18001ad01  mov     rcx, rax; this
0x18001ad04  call    ??0CAMThread@@QEAA@PEAJ@Z; CAMThread::CAMThread(long *)
0x18001ad09  mov     qword ptr [rdi+78h], 0
0x18001ad11  lea     rax, ??_7CStreamPull@@6B@; const CStreamPull::`vftable'
0x18001ad18  mov     [rdi], rax
0x18001ad1b  mov     rdx, rsi; struct IUnknown *
0x18001ad1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ad22  mov     qword ptr [rdi+98h], 0
0x18001ad2d  mov     [rdi+0C0h], rax
0x18001ad34  mov     rcx, rdi; this
0x18001ad37  mov     [rdi+0C8h], rax
0x18001ad3e  mov     qword ptr [rdi+0A4h], 0
0x18001ad49  mov     qword ptr [rdi+0ACh], 0
0x18001ad54  mov     dword ptr [rdi+0B4h], 2
0x18001ad5e  mov     [rdi+0B8h], rbx
0x18001ad65  mov     r8, [rbx+0E0h]; struct IMemAllocator *
0x18001ad6c  mov     [rbx+130h], rdi
0x18001ad73  call    ?Connect@CMp2PullPin@@QEAAJPEAUIUnknown@@PEAUIMemAllocator@@H@Z; CMp2PullPin::Connect(IUnknown *,IMemAllocator *,int)
0x18001ad78  mov     edi, eax
0x18001ad7a  test    eax, eax
0x18001ad7c  js      loc_18001AE53
0x18001ad82  mov     rax, qword ptr cs:MEDIATYPE_Stream.Data1
0x18001ad89  cmp     [rbx+68h], rax
0x18001ad8d  jnz     loc_18001AE53
0x18001ad93  mov     rdx, qword ptr cs:MEDIATYPE_Stream.Data4
0x18001ad9a  cmp     [rbx+70h], rdx
0x18001ad9e  jnz     loc_18001AE53
0x18001ada4  mov     r8, qword ptr cs:MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE.Data1
0x18001adab  cmp     [rbx+78h], r8
0x18001adaf  jnz     loc_18001AE53
0x18001adb5  mov     rcx, qword ptr cs:MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE.Data4
0x18001adbc  cmp     [rbx+80h], rcx
0x18001adc3  jnz     loc_18001AE53
0x18001adc9  cmp     [rbx+68h], rax
0x18001adcd  jnz     short loc_18001AE4E
0x18001adcf  cmp     [rbx+70h], rdx
0x18001add3  jnz     short loc_18001AE4E
0x18001add5  cmp     [rbx+78h], r8
0x18001add9  jnz     short loc_18001AE4E
0x18001addb  cmp     [rbx+80h], rcx
0x18001ade2  jnz     short loc_18001AE4E
0x18001ade4  mov     eax, [rbx+0B0h]
0x18001adea  test    eax, eax
0x18001adec  jz      short loc_18001AE29
0x18001adee  cmp     eax, 0Ch
0x18001adf1  jb      short loc_18001AE10
0x18001adf3  mov     rax, [rbx+0B8h]
0x18001adfa  mov     edx, [rax]
0x18001adfc  test    edx, edx
0x18001adfe  js      short loc_18001AE10
0x18001ae00  mov     r8d, [rax+8]
0x18001ae04  sub     r8d, edx
0x18001ae07  add     r8d, 0FFFFFF44h
0x18001ae0e  jns     short loc_18001AE2E
0x18001ae10  mov     edi, 80070057h
0x18001ae15  jmp     short loc_18001AE53
0x18001ae17  mov     qword ptr [rbx+130h], 0
0x18001ae22  mov     edi, 8007000Eh
0x18001ae27  jmp     short loc_18001AE53
0x18001ae29  xor     edx, edx
0x18001ae2b  xor     r8d, r8d
0x18001ae2e  mov     rax, [rbx+50h]
0x18001ae32  xor     edi, edi
0x18001ae34  mov     rcx, [rax+150h]
0x18001ae3b  test    rcx, rcx
0x18001ae3e  jz      short loc_18001AE53
0x18001ae40  mov     rax, [rcx]
0x18001ae43  mov     rax, [rax+50h]
0x18001ae47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae4c  jmp     short loc_18001AE53
0x18001ae4e  mov     edi, 80004005h
0x18001ae53  mov     rcx, [rbx+50h]; this
0x18001ae57  mov     rax, [rcx+150h]
0x18001ae5e  test    rax, rax
0x18001ae61  jz      short loc_18001AE6C
0x18001ae63  cmp     dword ptr [rax+0B0h], 0
0x18001ae6a  jnz     short loc_18001AE7A
0x18001ae6c  call    ?RegisterWithBDANetworkProvider@CMPEG2Demultiplexer@@QEAAXXZ; CMPEG2Demultiplexer::RegisterWithBDANetworkProvider(void)
0x18001ae71  mov     rcx, [rbx+50h]; this
0x18001ae75  call    ?ConnectESEvents@CMPEG2Demultiplexer@@QEAAXXZ; CMPEG2Demultiplexer::ConnectESEvents(void)
0x18001ae7a  mov     rbx, [rsp+28h+arg_8]
0x18001ae7f  mov     eax, edi
0x18001ae81  mov     rsi, [rsp+28h+arg_10]
0x18001ae86  add     rsp, 20h
0x18001ae8a  pop     rdi
0x18001ae8b  retn
```
