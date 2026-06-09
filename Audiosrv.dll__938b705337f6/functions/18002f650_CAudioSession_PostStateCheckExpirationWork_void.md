# CAudioSession::PostStateCheckExpirationWork(void)

- ea: `0x18002f650`
- end: `0x18002f9e4`
- name: `?PostStateCheckExpirationWork@CAudioSession@@AEAAXXZ`
- size: `916`
- prototype: `void __fastcall(CAudioSession *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18002d5a0`
- `0x18002e140`
- `0x18002f2cc`
- `0x180033bb8`

## callees

- `0x18002a04c`
- `0x18002f650`
- `0x180030b5c`
- `0x1800cdfbc`
- `0x1800cfd9c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f7e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f7e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f7f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f7f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f70f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f70f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f6eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f6eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002f8c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002f8c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f728`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f728`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f705`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f705`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f746`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f746`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f963`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002f963`

## string_xrefs

- `0x18002f9cd`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CAudioSession::PostStateCheckExpirationWork(CAudioSession *this)
{
  __int64 v2; // r14
  signed int v3; // ebx
  PTP_POOL Threadpool; // rax
  signed int v5; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 *v7; // rax
  unsigned int v8; // edx
  __int64 *v9; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // r15
  volatile signed __int32 *v13; // rbx
  __int64 v14; // r15
  _BYTE *v15; // rdx
  struct _TP_WORK *ThreadpoolWork; // r14
  _QWORD *v17; // rdx
  signed int v18; // eax
  signed int LastError; // eax
  signed int v20; // eax
  _BYTE *v21; // [rsp+20h] [rbp-69h]
  _QWORD v22[7]; // [rsp+28h] [rbp-61h] BYREF
  _QWORD *v23; // [rsp+60h] [rbp-29h]
  _DWORD *v24; // [rsp+68h] [rbp-21h]
  _BYTE v25[56]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE *v26; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( this )
    (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 8LL))(this);
  v2 = (*(__int64 (__fastcall **)(struct IAudioService *))(*(_QWORD *)g_AudioService + 120LL))(g_AudioService);
  if ( this )
    (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 8LL))(this);
  v22[0] = off_18016EB40;
  v22[1] = this;
  v23 = v22;
  v3 = 0;
  if ( !*(_BYTE *)(v2 + 80) )
  {
    if ( *(_QWORD *)v2 )
      goto LABEL_14;
    Threadpool = CreateThreadpool(0);
    *(_QWORD *)v2 = Threadpool;
    if ( Threadpool )
      goto LABEL_48;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_48:
      if ( SetThreadpoolThreadMinimum(*(PTP_POOL *)v2, 1u) )
        goto LABEL_56;
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_56:
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
        *(_QWORD *)(v2 + 168) = ThreadpoolCleanupGroup;
        if ( ThreadpoolCleanupGroup )
          goto LABEL_13;
        v20 = GetLastError();
        v3 = v20;
        if ( v20 > 0 )
          v3 = (unsigned __int16)v20 | 0x80070000;
        if ( v3 >= 0 )
        {
LABEL_13:
          SetThreadpoolThreadMaximum(*(PTP_POOL *)v2, 1u);
          *(_QWORD *)(v2 + 16) = *(_QWORD *)v2;
          *(_QWORD *)(v2 + 24) = *(_QWORD *)(v2 + 168);
          *(_QWORD *)(v2 + 32) = 0;
LABEL_14:
          v7 = (__int64 *)operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v9 = v7;
          if ( v7 )
          {
            *v7 = 0;
            v7[1] = 0;
            v7[2] = 0;
          }
          else
          {
            v9 = 0;
          }
          if ( v9 )
          {
            v26 = 0;
            if ( v23 )
              v26 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))*v23)(v23, v25);
            v21 = v25;
            v9[2] = v2;
            ProcessHeap = GetProcessHeap();
            v11 = HeapAlloc(ProcessHeap, 0, 0x50u);
            v12 = v11;
            v24 = v11;
            if ( v11 )
            {
              *(_OWORD *)v11 = 0;
              v11[2] = 1;
              v11[3] = 1;
              *(_QWORD *)v11 = &std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable';
              std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(v11 + 4, v25);
            }
            else
            {
              v12 = 0;
            }
            *v9 = (__int64)(v12 + 4);
            v13 = (volatile signed __int32 *)v9[1];
            v9[1] = (__int64)v12;
            if ( v13 )
            {
              if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
                if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
              }
            }
            v14 = *v9;
            v3 = *v9 == 0 ? 0x8007000E : 0;
            if ( v26 )
            {
              v15 = v25;
              LOBYTE(v15) = v26 != v25;
              (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v26 + 32LL))(v26, v15);
            }
            if ( !v14 )
              goto LABEL_31;
            ThreadpoolWork = CreateThreadpoolWork(CSerialWorkQueue::WorkCallback, v9, (PTP_CALLBACK_ENVIRON)(v2 + 8));
            if ( ThreadpoolWork )
            {
              v3 = 0;
            }
            else
            {
              v18 = GetLastError();
              v3 = v18;
              if ( v18 > 0 )
                v3 = (unsigned __int16)v18 | 0x80070000;
              if ( v3 < 0 )
                goto LABEL_31;
            }
            v9 = 0;
            SubmitThreadpoolWork(ThreadpoolWork);
          }
          else
          {
            v3 = -2147024882;
          }
LABEL_31:
          if ( v9 )
            _WorkTask::`scalar deleting destructor'((_WorkTask *)v9, v8);
        }
      }
    }
  }
  if ( v23 )
  {
    v17 = v22;
    LOBYTE(v17) = v23 != v22;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v17);
    v23 = 0;
  }
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD92,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
      (const char *)(unsigned int)v3,
      (int)v21);
  if ( this )
    (*(void (__fastcall **)(CAudioSession *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18002f650  push    rbp
0x18002f652  push    rbx
0x18002f653  push    rsi
0x18002f654  push    rdi
0x18002f655  push    r14
0x18002f657  push    r15
0x18002f659  lea     rbp, [rsp-2Fh]
0x18002f65e  sub     rsp, 0B8h
0x18002f665  mov     rsi, rcx
0x18002f668  mov     [rbp+57h+arg_0], rcx
0x18002f66c  test    rcx, rcx
0x18002f66f  jz      short loc_18002F67E
0x18002f671  mov     rax, [rcx]
0x18002f674  mov     rax, [rax+8]
0x18002f678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f67d  nop
0x18002f67e  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18002f685  mov     rax, [rcx]
0x18002f688  mov     rax, [rax+78h]
0x18002f68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f691  mov     r14, rax
0x18002f694  test    rsi, rsi
0x18002f697  jz      short loc_18002F6A9
0x18002f699  mov     rcx, [rsi]
0x18002f69c  mov     rax, [rcx+8]
0x18002f6a0  mov     rcx, rsi
0x18002f6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6a8  nop
0x18002f6a9  lea     rax, off_18016EB40
0x18002f6b0  mov     [rbp+57h+var_B8], rax
0x18002f6b4  mov     [rbp+57h+arg_8], 0
0x18002f6bc  mov     [rbp+57h+var_B0], rsi
0x18002f6c0  lea     rax, [rbp+57h+var_B8]
0x18002f6c4  mov     [rbp+57h+var_80], rax
0x18002f6c8  lea     rax, [rbp+57h+var_B8]
0x18002f6cc  mov     [rbp+57h+arg_10], rax
0x18002f6d0  xor     ebx, ebx
0x18002f6d2  mov     al, [r14+50h]
0x18002f6d6  nop
0x18002f6d7  test    al, al
0x18002f6d9  jnz     loc_18002F8EC
0x18002f6df  mov     edi, 80070000h
0x18002f6e4  cmp     [r14], rbx
0x18002f6e7  jnz     short loc_18002F766
0x18002f6e9  xor     ecx, ecx; reserved
0x18002f6eb  call    cs:__imp_CreateThreadpool
0x18002f6f1  mov     [r14], rax
0x18002f6f4  test    rax, rax
0x18002f6f7  jz      loc_18002F997
0x18002f6fd  mov     edx, 1; cthrdMic
0x18002f702  mov     rcx, [r14]; ptpp
0x18002f705  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002f70b  test    eax, eax
0x18002f70d  jnz     short loc_18002F728
0x18002f70f  call    cs:__imp_GetLastError
0x18002f715  mov     ebx, eax
0x18002f717  test    eax, eax
0x18002f719  jle     short loc_18002F720
0x18002f71b  movzx   ebx, ax
0x18002f71e  or      ebx, edi
0x18002f720  test    ebx, ebx
0x18002f722  js      loc_18002F8EC
0x18002f728  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002f72e  mov     [r14+0A8h], rax
0x18002f735  test    rax, rax
0x18002f738  jz      loc_18002F9AA
0x18002f73e  mov     edx, 1; cthrdMost
0x18002f743  mov     rcx, [r14]; ptpp
0x18002f746  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002f74c  mov     rax, [r14]
0x18002f74f  mov     [r14+10h], rax
0x18002f753  mov     rax, [r14+0A8h]
0x18002f75a  mov     [r14+18h], rax
0x18002f75e  mov     qword ptr [r14+20h], 0
0x18002f766  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f76d  mov     ecx, 18h; unsigned __int64
0x18002f772  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f777  mov     rdi, rax
0x18002f77a  mov     [rbp+57h+arg_18], rax
0x18002f77e  test    rax, rax
0x18002f781  jz      loc_18002F96E
0x18002f787  mov     qword ptr [rax], 0
0x18002f78e  mov     qword ptr [rax+8], 0
0x18002f796  mov     qword ptr [rax+10h], 0
0x18002f79e  mov     [rbp+57h+arg_18], rdi
0x18002f7a2  test    rdi, rdi
0x18002f7a5  jz      loc_18002F8DE
0x18002f7ab  lea     rax, [rbp+57h+var_70]
0x18002f7af  mov     [rbp+57h+var_C0], rax
0x18002f7b3  mov     [rbp+57h+var_38], 0
0x18002f7bb  mov     rcx, [rbp+57h+var_80]
0x18002f7bf  test    rcx, rcx
0x18002f7c2  jz      short loc_18002F7D7
0x18002f7c4  mov     rax, [rcx]
0x18002f7c7  lea     rdx, [rbp+57h+var_70]
0x18002f7cb  mov     rax, [rax]
0x18002f7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7d3  mov     [rbp+57h+var_38], rax
0x18002f7d7  lea     rax, [rbp+57h+var_70]
0x18002f7db  mov     [rbp+57h+var_C0], rax
0x18002f7df  mov     [rdi+10h], r14
0x18002f7e3  call    cs:__imp_GetProcessHeap
0x18002f7e9  mov     rcx, rax; hHeap
0x18002f7ec  xor     edx, edx; dwFlags
0x18002f7ee  lea     r8d, [rdx+50h]; dwBytes
0x18002f7f2  call    cs:__imp_HeapAlloc
0x18002f7f8  mov     r15, rax
0x18002f7fb  mov     [rbp+57h+var_78], rax
0x18002f7ff  test    rax, rax
0x18002f802  jz      loc_18002F975
0x18002f808  xorps   xmm0, xmm0
0x18002f80b  movups  xmmword ptr [rax], xmm0
0x18002f80e  mov     dword ptr [rax+8], 1
0x18002f815  mov     dword ptr [rax+0Ch], 1
0x18002f81c  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x18002f823  mov     [r15], rax
0x18002f826  lea     rcx, [r15+10h]
0x18002f82a  lea     rdx, [rbp+57h+var_70]
0x18002f82e  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x18002f833  nop
0x18002f834  lea     rax, [r15+10h]
0x18002f838  mov     [rdi], rax
0x18002f83b  mov     rbx, [rdi+8]
0x18002f83f  mov     [rdi+8], r15
0x18002f843  test    rbx, rbx
0x18002f846  jz      short loc_18002F883
0x18002f848  or      r15d, 0FFFFFFFFh
0x18002f84c  mov     eax, r15d
0x18002f84f  lock xadd [rbx+8], eax
0x18002f854  add     eax, r15d
0x18002f857  jnz     short loc_18002F883
0x18002f859  mov     rax, [rbx]
0x18002f85c  mov     rcx, rbx
0x18002f85f  mov     rax, [rax]
0x18002f862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f867  mov     eax, r15d
0x18002f86a  lock xadd [rbx+0Ch], eax
0x18002f86f  add     eax, r15d
0x18002f872  jnz     short loc_18002F883
0x18002f874  mov     rax, [rbx]
0x18002f877  mov     rcx, rbx
0x18002f87a  mov     rax, [rax+8]
0x18002f87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f883  mov     r15, [rdi]
0x18002f886  mov     rax, r15
0x18002f889  neg     rax
0x18002f88c  sbb     ecx, ecx
0x18002f88e  not     ecx
0x18002f890  mov     ebx, 8007000Eh
0x18002f895  and     ebx, ecx
0x18002f897  mov     rcx, [rbp+57h+var_38]
0x18002f89b  test    rcx, rcx
0x18002f89e  jz      short loc_18002F8B6
0x18002f8a0  mov     rax, [rcx]
0x18002f8a3  lea     rdx, [rbp+57h+var_70]
0x18002f8a7  cmp     rcx, rdx
0x18002f8aa  setnz   dl
0x18002f8ad  mov     rax, [rax+20h]
0x18002f8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8b6  test    r15, r15
0x18002f8b9  jz      short loc_18002F8E3
0x18002f8bb  lea     r8, [r14+8]; pcbe
0x18002f8bf  mov     rdx, rdi; pv
0x18002f8c2  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002f8c9  call    cs:__imp_CreateThreadpoolWork
0x18002f8cf  mov     r14, rax
0x18002f8d2  test    rax, rax
0x18002f8d5  jz      short loc_18002F944
0x18002f8d7  xor     ebx, ebx
0x18002f8d9  jmp     loc_18002F95E
0x18002f8de  mov     ebx, 8007000Eh
0x18002f8e3  test    rdi, rdi
0x18002f8e6  jnz     loc_18002F9BD
0x18002f8ec  mov     rcx, [rbp+57h+var_80]
0x18002f8f0  test    rcx, rcx
0x18002f8f3  jz      short loc_18002F913
0x18002f8f5  mov     rax, [rcx]
0x18002f8f8  lea     rdx, [rbp+57h+var_B8]
0x18002f8fc  cmp     rcx, rdx
0x18002f8ff  setnz   dl
0x18002f902  mov     rax, [rax+20h]
0x18002f906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f90b  mov     [rbp+57h+var_80], 0
0x18002f913  mov     rcx, [rbp+5Fh]; this
0x18002f917  test    ebx, ebx
0x18002f919  js      loc_18002F9CA
0x18002f91f  test    rsi, rsi
0x18002f922  jz      short loc_18002F934
0x18002f924  mov     rax, [rsi]
0x18002f927  mov     rcx, rsi
0x18002f92a  mov     rax, [rax+10h]
0x18002f92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f933  nop
0x18002f934  add     rsp, 0B8h
0x18002f93b  pop     r15
0x18002f93d  pop     r14
0x18002f93f  pop     rdi
0x18002f940  pop     rsi
0x18002f941  pop     rbx
0x18002f942  pop     rbp
0x18002f943  retn
0x18002f944  call    cs:__imp_GetLastError
0x18002f94a  nop
0x18002f94b  mov     ebx, eax
0x18002f94d  test    eax, eax
0x18002f94f  jle     short loc_18002F95A
0x18002f951  movzx   ebx, ax
0x18002f954  or      ebx, 80070000h
0x18002f95a  test    ebx, ebx
0x18002f95c  js      short loc_18002F8E3
0x18002f95e  xor     edi, edi
0x18002f960  mov     rcx, r14; pwk
0x18002f963  call    cs:__imp_SubmitThreadpoolWork
0x18002f969  jmp     loc_18002F8E3
0x18002f96e  xor     edi, edi
0x18002f970  jmp     loc_18002F79E
0x18002f975  xor     r15d, r15d
0x18002f978  jmp     loc_18002F834
0x18002f97d  test    ebx, ebx
0x18002f97f  js      loc_18002F8EC
0x18002f985  jmp     loc_18002F6FD
0x18002f98a  test    ebx, ebx
0x18002f98c  js      loc_18002F8EC
0x18002f992  jmp     loc_18002F73E
0x18002f997  call    cs:__imp_GetLastError
0x18002f99d  mov     ebx, eax
0x18002f99f  test    eax, eax
0x18002f9a1  jle     short loc_18002F97D
0x18002f9a3  movzx   ebx, ax
0x18002f9a6  or      ebx, edi
0x18002f9a8  jmp     short loc_18002F97D
0x18002f9aa  call    cs:__imp_GetLastError
0x18002f9b0  mov     ebx, eax
0x18002f9b2  test    eax, eax
0x18002f9b4  jle     short loc_18002F98A
0x18002f9b6  movzx   ebx, ax
0x18002f9b9  or      ebx, edi
0x18002f9bb  jmp     short loc_18002F98A
0x18002f9bd  mov     rcx, rdi; this
0x18002f9c0  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x18002f9c5  jmp     loc_18002F8EC
0x18002f9ca  mov     r9d, ebx; char *
0x18002f9cd  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002f9d4  mov     edx, 0D92h; void *
0x18002f9d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f9de  jmp     loc_18002F91F
```
