# GameInputClient::~GameInputClient(void)

- ea: `0x180003e28`
- end: `0x18000404a`
- name: `??1GameInputClient@@EEAA@XZ`
- size: `546`
- prototype: `void __fastcall(GameInputClient *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180004310`
- `0x180005854`
- `0x18000739c`

## callees

- `0x180003d5c`
- `0x180003e28`
- `0x180004124`
- `0x18000b6c8`
- `0x18000c11c`
- `0x18002bccc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003ea0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003ea0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ed2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ed2`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180003eb3`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180003eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003efe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003e6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003e6f`

## pseudocode

```c
void __fastcall GameInputClient::~GameInputClient(GameInputClient *this)
{
  void *v2; // rdi
  const struct std::nothrow_t *v3; // rdx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  GameInputClient ***v8; // rdi
  GameInputClient **v9; // rax
  GameInputClient *v10; // rcx
  __int64 **v11; // rdi
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 **v14; // rdi
  __int64 *v15; // rax
  __int64 v16; // rcx

  *(_QWORD *)this = &GameInputClient::`vftable';
  if ( GipRawDeviceIO::s_gipClientHandle != (HANDLE)-1LL )
  {
    CloseHandle(GipRawDeviceIO::s_gipClientHandle);
    GipRawDeviceIO::s_gipClientHandle = (HANDLE)-1LL;
  }
  *((_QWORD *)this + 34) = GetTickCount64();
  _mm_mfence();
  GameInputDispatcher::SignalThread((GameInputClient *)((char *)this + 208));
  v2 = (void *)_InterlockedExchange64((volatile __int64 *)this + 33, 0);
  if ( v2 )
  {
    if ( WaitForSingleObject(v2, 0x1388u) )
      SuspendThread(v2);
    CloseHandle(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  PixLogger::~PixLogger((GameInputClient *)((char *)this + 288));
  GameInputDispatcher::~GameInputDispatcher((GameInputClient *)((char *)this + 208));
  v4 = (void *)*((_QWORD *)this + 24);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 24) = 0;
  }
  v5 = *((_QWORD *)this + 23);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 23) = 0;
  }
  v6 = *((_QWORD *)this + 22);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 22) = 0;
  }
  v7 = *((_QWORD *)this + 21);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 21) = 0;
  }
  v8 = (GameInputClient ***)((char *)this + 128);
  v9 = (GameInputClient **)*((_QWORD *)this + 16);
  v10 = *v9;
  if ( v9[1] != (GameInputClient *)((char *)this + 128) )
LABEL_19:
    __fastfail(3u);
  while ( 1 )
  {
    if ( *((GameInputClient ***)v10 + 1) != v9 )
      goto LABEL_19;
    *v8 = (GameInputClient **)v10;
    *((_QWORD *)v10 + 1) = v8;
    if ( v9 == (GameInputClient **)v8 )
      break;
    operator delete(v9, v3);
    --*((_DWORD *)this + 36);
    v9 = *v8;
    v10 = **v8;
    if ( (*v8)[1] != (GameInputClient *)v8 )
      goto LABEL_19;
  }
  v11 = (__int64 **)((char *)this + 104);
  while ( 1 )
  {
    v12 = *v11;
    v13 = **v11;
    if ( (__int64 **)(*v11)[1] != v11 || *(__int64 **)(v13 + 8) != v12 )
      goto LABEL_19;
    *v11 = (__int64 *)v13;
    *(_QWORD *)(v13 + 8) = v11;
    if ( v12 == (__int64 *)v11 )
      break;
    operator delete(v12, v3);
    --*((_DWORD *)this + 30);
  }
  v14 = (__int64 **)((char *)this + 80);
  while ( 1 )
  {
    v15 = *v14;
    v16 = **v14;
    if ( (__int64 **)(*v14)[1] != v14 || *(__int64 **)(v16 + 8) != v15 )
      goto LABEL_19;
    *v14 = (__int64 *)v16;
    *(_QWORD *)(v16 + 8) = v14;
    if ( v15 == (__int64 *)v14 )
      break;
    operator delete(v15, v3);
    --*((_DWORD *)this + 24);
  }
  DeviceList::~DeviceList((GameInputClient *)((char *)this + 16));
  *(_QWORD *)this = &ClientObjectBase<InterfaceHierarchy<IGameInput,IGameInputPrivate>>::`vftable';
}

```

## disassembly

```asm
0x180003e28  mov     [rsp+arg_0], rbx
0x180003e2d  mov     [rsp+arg_8], rsi
0x180003e32  push    rdi
0x180003e33  sub     rsp, 20h
0x180003e37  lea     rax, ??_7GameInputClient@@6B@; const GameInputClient::`vftable'
0x180003e3e  mov     rbx, rcx
0x180003e41  mov     [rcx], rax
0x180003e44  mov     rcx, cs:?s_gipClientHandle@GipRawDeviceIO@@0PEAXEA; hObject
0x180003e4b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003e4f  jz      short loc_180003E68
0x180003e51  call    cs:__imp_CloseHandle
0x180003e58  nop     dword ptr [rax+rax+00h]
0x180003e5d  mov     cs:?s_gipClientHandle@GipRawDeviceIO@@0PEAXEA, 0FFFFFFFFFFFFFFFFh; void * GipRawDeviceIO::s_gipClientHandle
0x180003e68  lea     rsi, [rbx+0D0h]
0x180003e6f  call    cs:__imp_GetTickCount64
0x180003e76  nop     dword ptr [rax+rax+00h]
0x180003e7b  nop
0x180003e7c  mov     [rsi+40h], rax
0x180003e80  mfence
0x180003e83  mov     rcx, rsi; this
0x180003e86  call    ?SignalThread@GameInputDispatcher@@AEAAJXZ; GameInputDispatcher::SignalThread(void)
0x180003e8b  xor     edi, edi
0x180003e8d  nop
0x180003e8e  xchg    rdi, [rsi+38h]
0x180003e92  nop
0x180003e93  test    rdi, rdi
0x180003e96  jz      short loc_180003ECE
0x180003e98  mov     edx, 1388h; dwMilliseconds
0x180003e9d  mov     rcx, rdi; hHandle
0x180003ea0  call    cs:__imp_WaitForSingleObject
0x180003ea7  nop     dword ptr [rax+rax+00h]
0x180003eac  test    eax, eax
0x180003eae  jz      short loc_180003EBF
0x180003eb0  mov     rcx, rdi; hThread
0x180003eb3  call    cs:__imp_SuspendThread
0x180003eba  nop     dword ptr [rax+rax+00h]
0x180003ebf  mov     rcx, rdi; hObject
0x180003ec2  call    cs:__imp_CloseHandle
0x180003ec9  nop     dword ptr [rax+rax+00h]
0x180003ece  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003ed2  call    cs:__imp_DeleteCriticalSection
0x180003ed9  nop     dword ptr [rax+rax+00h]
0x180003ede  lea     rcx, [rbx+120h]; this
0x180003ee5  call    ??1PixLogger@@QEAA@XZ; PixLogger::~PixLogger(void)
0x180003eea  mov     rcx, rsi; this
0x180003eed  call    ??1GameInputDispatcher@@QEAA@XZ; GameInputDispatcher::~GameInputDispatcher(void)
0x180003ef2  mov     rcx, [rbx+0C0h]; hObject
0x180003ef9  test    rcx, rcx
0x180003efc  jz      short loc_180003F15
0x180003efe  call    cs:__imp_CloseHandle
0x180003f05  nop     dword ptr [rax+rax+00h]
0x180003f0a  mov     qword ptr [rbx+0C0h], 0
0x180003f15  mov     rcx, [rbx+0B8h]
0x180003f1c  test    rcx, rcx
0x180003f1f  jz      short loc_180003F38
0x180003f21  mov     rax, [rcx]
0x180003f24  mov     rax, [rax+10h]
0x180003f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2d  mov     qword ptr [rbx+0B8h], 0
0x180003f38  mov     rcx, [rbx+0B0h]
0x180003f3f  test    rcx, rcx
0x180003f42  jz      short loc_180003F5B
0x180003f44  mov     rax, [rcx]
0x180003f47  mov     rax, [rax+10h]
0x180003f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f50  mov     qword ptr [rbx+0B0h], 0
0x180003f5b  mov     rcx, [rbx+0A8h]
0x180003f62  test    rcx, rcx
0x180003f65  jz      short loc_180003F7E
0x180003f67  mov     rax, [rcx]
0x180003f6a  mov     rax, [rax+10h]
0x180003f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f73  mov     qword ptr [rbx+0A8h], 0
0x180003f7e  lea     rdi, [rbx+80h]
0x180003f85  mov     rax, [rdi]
0x180003f88  mov     rcx, [rax]
0x180003f8b  cmp     [rax+8], rdi
0x180003f8f  jnz     short loc_180003FBD
0x180003f91  or      esi, 0FFFFFFFFh
0x180003f94  cmp     [rcx+8], rax
0x180003f98  jnz     short loc_180003FBD
0x180003f9a  mov     [rdi], rcx
0x180003f9d  mov     [rcx+8], rdi
0x180003fa1  cmp     rax, rdi
0x180003fa4  jz      short loc_180003FC4
0x180003fa6  mov     rcx, rax; P
0x180003fa9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003fae  add     [rdi+10h], esi
0x180003fb1  mov     rax, [rdi]
0x180003fb4  mov     rcx, [rax]
0x180003fb7  cmp     [rax+8], rdi
0x180003fbb  jz      short loc_180003F94
0x180003fbd  mov     ecx, 3
0x180003fc2  int     29h; Win8: RtlFailFast(ecx)
0x180003fc4  lea     rdi, [rbx+68h]
0x180003fc8  jmp     short loc_180003FE7
0x180003fca  cmp     [rcx+8], rax
0x180003fce  jnz     short loc_180003FBD
0x180003fd0  mov     [rdi], rcx
0x180003fd3  mov     [rcx+8], rdi
0x180003fd7  cmp     rax, rdi
0x180003fda  jz      short loc_180003FF5
0x180003fdc  mov     rcx, rax; P
0x180003fdf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003fe4  add     [rdi+10h], esi
0x180003fe7  mov     rax, [rdi]
0x180003fea  mov     rcx, [rax]
0x180003fed  cmp     [rax+8], rdi
0x180003ff1  jz      short loc_180003FCA
0x180003ff3  jmp     short loc_180003FBD
0x180003ff5  lea     rdi, [rbx+50h]
0x180003ff9  jmp     short loc_180004018
0x180003ffb  cmp     [rcx+8], rax
0x180003fff  jnz     short loc_180003FBD
0x180004001  mov     [rdi], rcx
0x180004004  mov     [rcx+8], rdi
0x180004008  cmp     rax, rdi
0x18000400b  jz      short loc_180004026
0x18000400d  mov     rcx, rax; P
0x180004010  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004015  add     [rdi+10h], esi
0x180004018  mov     rax, [rdi]
0x18000401b  mov     rcx, [rax]
0x18000401e  cmp     [rax+8], rdi
0x180004022  jz      short loc_180003FFB
0x180004024  jmp     short loc_180003FBD
0x180004026  lea     rcx, [rbx+10h]; this
0x18000402a  call    ??1DeviceList@@QEAA@XZ; DeviceList::~DeviceList(void)
0x18000402f  mov     rsi, [rsp+28h+arg_8]
0x180004034  lea     rax, ??_7?$ClientObjectBase@U?$InterfaceHierarchy@UIGameInput@@UIGameInputPrivate@@@@@@6B@; const ClientObjectBase<InterfaceHierarchy<IGameInput,IGameInputPrivate>>::`vftable'
0x18000403b  mov     [rbx], rax
0x18000403e  mov     rbx, [rsp+28h+arg_0]
0x180004043  add     rsp, 20h
0x180004047  pop     rdi
0x180004048  retn
```
