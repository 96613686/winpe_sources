# CAudioSession::PostStateCheckExpirationWork(void)

- ea: `0x18002f7b0`
- end: `0x18002fb44`
- name: `?PostStateCheckExpirationWork@CAudioSession@@AEAAXXZ`
- size: `916`
- prototype: `void __fastcall(CAudioSession *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18002d700`
- `0x18002e2a0`
- `0x18002f42c`
- `0x180033d18`

## callees

- `0x18002a1ac`
- `0x18002f7b0`
- `0x180030cbc`
- `0x1800cbfcc`
- `0x1800cddac`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f943`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f952`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f84b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f84b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002fa29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002fa29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f888`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002f888`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f865`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f865`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f8a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f8a6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002fac3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002fac3`

## string_xrefs

- `0x18002fb2d`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

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
  v22[0] = off_18016FB40;
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
0x18002f7b0  push    rbp
0x18002f7b2  push    rbx
0x18002f7b3  push    rsi
0x18002f7b4  push    rdi
0x18002f7b5  push    r14
0x18002f7b7  push    r15
0x18002f7b9  lea     rbp, [rsp-2Fh]
0x18002f7be  sub     rsp, 0B8h
0x18002f7c5  mov     rsi, rcx
0x18002f7c8  mov     [rbp+57h+arg_0], rcx
0x18002f7cc  test    rcx, rcx
0x18002f7cf  jz      short loc_18002F7DE
0x18002f7d1  mov     rax, [rcx]
0x18002f7d4  mov     rax, [rax+8]
0x18002f7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7dd  nop
0x18002f7de  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18002f7e5  mov     rax, [rcx]
0x18002f7e8  mov     rax, [rax+78h]
0x18002f7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7f1  mov     r14, rax
0x18002f7f4  test    rsi, rsi
0x18002f7f7  jz      short loc_18002F809
0x18002f7f9  mov     rcx, [rsi]
0x18002f7fc  mov     rax, [rcx+8]
0x18002f800  mov     rcx, rsi
0x18002f803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f808  nop
0x18002f809  lea     rax, off_18016FB40
0x18002f810  mov     [rbp+57h+var_B8], rax
0x18002f814  mov     [rbp+57h+arg_8], 0
0x18002f81c  mov     [rbp+57h+var_B0], rsi
0x18002f820  lea     rax, [rbp+57h+var_B8]
0x18002f824  mov     [rbp+57h+var_80], rax
0x18002f828  lea     rax, [rbp+57h+var_B8]
0x18002f82c  mov     [rbp+57h+arg_10], rax
0x18002f830  xor     ebx, ebx
0x18002f832  mov     al, [r14+50h]
0x18002f836  nop
0x18002f837  test    al, al
0x18002f839  jnz     loc_18002FA4C
0x18002f83f  mov     edi, 80070000h
0x18002f844  cmp     [r14], rbx
0x18002f847  jnz     short loc_18002F8C6
0x18002f849  xor     ecx, ecx; reserved
0x18002f84b  call    cs:__imp_CreateThreadpool
0x18002f851  mov     [r14], rax
0x18002f854  test    rax, rax
0x18002f857  jz      loc_18002FAF7
0x18002f85d  mov     edx, 1; cthrdMic
0x18002f862  mov     rcx, [r14]; ptpp
0x18002f865  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002f86b  test    eax, eax
0x18002f86d  jnz     short loc_18002F888
0x18002f86f  call    cs:__imp_GetLastError
0x18002f875  mov     ebx, eax
0x18002f877  test    eax, eax
0x18002f879  jle     short loc_18002F880
0x18002f87b  movzx   ebx, ax
0x18002f87e  or      ebx, edi
0x18002f880  test    ebx, ebx
0x18002f882  js      loc_18002FA4C
0x18002f888  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002f88e  mov     [r14+0A8h], rax
0x18002f895  test    rax, rax
0x18002f898  jz      loc_18002FB0A
0x18002f89e  mov     edx, 1; cthrdMost
0x18002f8a3  mov     rcx, [r14]; ptpp
0x18002f8a6  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002f8ac  mov     rax, [r14]
0x18002f8af  mov     [r14+10h], rax
0x18002f8b3  mov     rax, [r14+0A8h]
0x18002f8ba  mov     [r14+18h], rax
0x18002f8be  mov     qword ptr [r14+20h], 0
0x18002f8c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f8cd  mov     ecx, 18h; unsigned __int64
0x18002f8d2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f8d7  mov     rdi, rax
0x18002f8da  mov     [rbp+57h+arg_18], rax
0x18002f8de  test    rax, rax
0x18002f8e1  jz      loc_18002FACE
0x18002f8e7  mov     qword ptr [rax], 0
0x18002f8ee  mov     qword ptr [rax+8], 0
0x18002f8f6  mov     qword ptr [rax+10h], 0
0x18002f8fe  mov     [rbp+57h+arg_18], rdi
0x18002f902  test    rdi, rdi
0x18002f905  jz      loc_18002FA3E
0x18002f90b  lea     rax, [rbp+57h+var_70]
0x18002f90f  mov     [rbp+57h+var_C0], rax
0x18002f913  mov     [rbp+57h+var_38], 0
0x18002f91b  mov     rcx, [rbp+57h+var_80]
0x18002f91f  test    rcx, rcx
0x18002f922  jz      short loc_18002F937
0x18002f924  mov     rax, [rcx]
0x18002f927  lea     rdx, [rbp+57h+var_70]
0x18002f92b  mov     rax, [rax]
0x18002f92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f933  mov     [rbp+57h+var_38], rax
0x18002f937  lea     rax, [rbp+57h+var_70]
0x18002f93b  mov     [rbp+57h+var_C0], rax
0x18002f93f  mov     [rdi+10h], r14
0x18002f943  call    cs:__imp_GetProcessHeap
0x18002f949  mov     rcx, rax; hHeap
0x18002f94c  xor     edx, edx; dwFlags
0x18002f94e  lea     r8d, [rdx+50h]; dwBytes
0x18002f952  call    cs:__imp_HeapAlloc
0x18002f958  mov     r15, rax
0x18002f95b  mov     [rbp+57h+var_78], rax
0x18002f95f  test    rax, rax
0x18002f962  jz      loc_18002FAD5
0x18002f968  xorps   xmm0, xmm0
0x18002f96b  movups  xmmword ptr [rax], xmm0
0x18002f96e  mov     dword ptr [rax+8], 1
0x18002f975  mov     dword ptr [rax+0Ch], 1
0x18002f97c  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x18002f983  mov     [r15], rax
0x18002f986  lea     rcx, [r15+10h]
0x18002f98a  lea     rdx, [rbp+57h+var_70]
0x18002f98e  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x18002f993  nop
0x18002f994  lea     rax, [r15+10h]
0x18002f998  mov     [rdi], rax
0x18002f99b  mov     rbx, [rdi+8]
0x18002f99f  mov     [rdi+8], r15
0x18002f9a3  test    rbx, rbx
0x18002f9a6  jz      short loc_18002F9E3
0x18002f9a8  or      r15d, 0FFFFFFFFh
0x18002f9ac  mov     eax, r15d
0x18002f9af  lock xadd [rbx+8], eax
0x18002f9b4  add     eax, r15d
0x18002f9b7  jnz     short loc_18002F9E3
0x18002f9b9  mov     rax, [rbx]
0x18002f9bc  mov     rcx, rbx
0x18002f9bf  mov     rax, [rax]
0x18002f9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9c7  mov     eax, r15d
0x18002f9ca  lock xadd [rbx+0Ch], eax
0x18002f9cf  add     eax, r15d
0x18002f9d2  jnz     short loc_18002F9E3
0x18002f9d4  mov     rax, [rbx]
0x18002f9d7  mov     rcx, rbx
0x18002f9da  mov     rax, [rax+8]
0x18002f9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9e3  mov     r15, [rdi]
0x18002f9e6  mov     rax, r15
0x18002f9e9  neg     rax
0x18002f9ec  sbb     ecx, ecx
0x18002f9ee  not     ecx
0x18002f9f0  mov     ebx, 8007000Eh
0x18002f9f5  and     ebx, ecx
0x18002f9f7  mov     rcx, [rbp+57h+var_38]
0x18002f9fb  test    rcx, rcx
0x18002f9fe  jz      short loc_18002FA16
0x18002fa00  mov     rax, [rcx]
0x18002fa03  lea     rdx, [rbp+57h+var_70]
0x18002fa07  cmp     rcx, rdx
0x18002fa0a  setnz   dl
0x18002fa0d  mov     rax, [rax+20h]
0x18002fa11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa16  test    r15, r15
0x18002fa19  jz      short loc_18002FA43
0x18002fa1b  lea     r8, [r14+8]; pcbe
0x18002fa1f  mov     rdx, rdi; pv
0x18002fa22  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002fa29  call    cs:__imp_CreateThreadpoolWork
0x18002fa2f  mov     r14, rax
0x18002fa32  test    rax, rax
0x18002fa35  jz      short loc_18002FAA4
0x18002fa37  xor     ebx, ebx
0x18002fa39  jmp     loc_18002FABE
0x18002fa3e  mov     ebx, 8007000Eh
0x18002fa43  test    rdi, rdi
0x18002fa46  jnz     loc_18002FB1D
0x18002fa4c  mov     rcx, [rbp+57h+var_80]
0x18002fa50  test    rcx, rcx
0x18002fa53  jz      short loc_18002FA73
0x18002fa55  mov     rax, [rcx]
0x18002fa58  lea     rdx, [rbp+57h+var_B8]
0x18002fa5c  cmp     rcx, rdx
0x18002fa5f  setnz   dl
0x18002fa62  mov     rax, [rax+20h]
0x18002fa66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa6b  mov     [rbp+57h+var_80], 0
0x18002fa73  mov     rcx, [rbp+5Fh]; this
0x18002fa77  test    ebx, ebx
0x18002fa79  js      loc_18002FB2A
0x18002fa7f  test    rsi, rsi
0x18002fa82  jz      short loc_18002FA94
0x18002fa84  mov     rax, [rsi]
0x18002fa87  mov     rcx, rsi
0x18002fa8a  mov     rax, [rax+10h]
0x18002fa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa93  nop
0x18002fa94  add     rsp, 0B8h
0x18002fa9b  pop     r15
0x18002fa9d  pop     r14
0x18002fa9f  pop     rdi
0x18002faa0  pop     rsi
0x18002faa1  pop     rbx
0x18002faa2  pop     rbp
0x18002faa3  retn
0x18002faa4  call    cs:__imp_GetLastError
0x18002faaa  nop
0x18002faab  mov     ebx, eax
0x18002faad  test    eax, eax
0x18002faaf  jle     short loc_18002FABA
0x18002fab1  movzx   ebx, ax
0x18002fab4  or      ebx, 80070000h
0x18002faba  test    ebx, ebx
0x18002fabc  js      short loc_18002FA43
0x18002fabe  xor     edi, edi
0x18002fac0  mov     rcx, r14; pwk
0x18002fac3  call    cs:__imp_SubmitThreadpoolWork
0x18002fac9  jmp     loc_18002FA43
0x18002face  xor     edi, edi
0x18002fad0  jmp     loc_18002F8FE
0x18002fad5  xor     r15d, r15d
0x18002fad8  jmp     loc_18002F994
0x18002fadd  test    ebx, ebx
0x18002fadf  js      loc_18002FA4C
0x18002fae5  jmp     loc_18002F85D
0x18002faea  test    ebx, ebx
0x18002faec  js      loc_18002FA4C
0x18002faf2  jmp     loc_18002F89E
0x18002faf7  call    cs:__imp_GetLastError
0x18002fafd  mov     ebx, eax
0x18002faff  test    eax, eax
0x18002fb01  jle     short loc_18002FADD
0x18002fb03  movzx   ebx, ax
0x18002fb06  or      ebx, edi
0x18002fb08  jmp     short loc_18002FADD
0x18002fb0a  call    cs:__imp_GetLastError
0x18002fb10  mov     ebx, eax
0x18002fb12  test    eax, eax
0x18002fb14  jle     short loc_18002FAEA
0x18002fb16  movzx   ebx, ax
0x18002fb19  or      ebx, edi
0x18002fb1b  jmp     short loc_18002FAEA
0x18002fb1d  mov     rcx, rdi; this
0x18002fb20  call    ??_G_WorkTask@@QEAAPEAXI@Z; _WorkTask::`scalar deleting destructor'(uint)
0x18002fb25  jmp     loc_18002FA4C
0x18002fb2a  mov     r9d, ebx; char *
0x18002fb2d  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18002fb34  mov     edx, 0D92h; void *
0x18002fb39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fb3e  jmp     loc_18002FA7F
```
