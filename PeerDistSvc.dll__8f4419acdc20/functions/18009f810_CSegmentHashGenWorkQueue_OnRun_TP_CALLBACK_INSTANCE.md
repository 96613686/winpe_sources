# CSegmentHashGenWorkQueue::OnRun(_TP_CALLBACK_INSTANCE *)

- ea: `0x18009f810`
- end: `0x18009fa53`
- name: `?OnRun@CSegmentHashGenWorkQueue@@MEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `579`
- prototype: `void __fastcall(CSegmentHashGenWorkQueue *__hidden this, PTP_CALLBACK_INSTANCE pci)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x18002a878`
- `0x180051678`
- `0x18009ece0`
- `0x18009f810`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18009f8be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18009f95d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18009f8be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18009f95d`
- `KERNEL32!GetCurrentThread` at `0x18009f8b0`
- `KERNEL32!GetCurrentThread` at `0x18009f94f`
- `KERNEL32!GetCurrentThread` at `0x18009f8b0`
- `KERNEL32!GetCurrentThread` at `0x18009f94f`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18009f82a`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18009f82a`

## pseudocode

```c
void __fastcall CSegmentHashGenWorkQueue::OnRun(CSegmentHashGenWorkQueue *this, PTP_CALLBACK_INSTANCE pci)
{
  _QWORD *v3; // r15
  int v4; // edi
  HANDLE CurrentThread; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // r8
  __int64 v10; // r9
  HANDLE v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  void (__fastcall *v13)(_QWORD, __int64); // rax
  __int64 v14; // rdx
  _BYTE v15[40]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+48h] BYREF

  CallbackMayRunLong(pci);
  while ( 1 )
  {
    v16 = 0;
    InCritSec::InCritSec((InCritSec *)v15, (CSegmentHashGenWorkQueue *)((char *)this + 48), 1);
    if ( !*((_QWORD *)this + 15) )
      goto LABEL_20;
    v3 = *(_QWORD **)(**((_QWORD **)this + 14) + 16LL);
    std::list<CCacheReadWriteData *>::pop_front((char *)this + 112);
    if ( !v3 )
      break;
    if ( *((_BYTE *)this + 105) )
    {
      (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
      (*(void (__fastcall **)(_QWORD *, __int64))*v3)(v3, 1);
      CSegmentHashGenWorkQueue::CancelQueuedWorkItems(this);
LABEL_20:
      *((_BYTE *)this + 128) = 0;
      goto LABEL_21;
    }
    InCritSec::~InCritSec((InCritSec *)v15);
    InCritSec::InCritSec((InCritSec *)v15, (CSegmentHashGenWorkQueue *)((char *)this + 48), 1);
    v4 = *((_DWORD *)this + 38);
    InCritSec::~InCritSec((InCritSec *)v15);
    if ( v4 >= 0 )
    {
      if ( *((_BYTE *)this + 104) )
      {
        CurrentThread = GetCurrentThread();
        SetThreadPriority(CurrentThread, 0x10000);
      }
      InCritSec::InCritSec((InCritSec *)v15, (CSegmentHashGenWorkQueue *)((char *)this + 48), 1);
      v6 = *((_QWORD *)this + 18);
      InCritSec::~InCritSec((InCritSec *)v15);
      InCritSec::InCritSec((InCritSec *)v15, (CSegmentHashGenWorkQueue *)((char *)this + 48), 1);
      v7 = *((_QWORD *)this + 17);
      InCritSec::~InCritSec((InCritSec *)v15);
      v4 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, __int64 *))(*v3 + 8LL))(v3, v7, v6, &v16);
      v8 = v16;
      InCritSec::InCritSec((InCritSec *)v15, (CSegmentHashGenWorkQueue *)((char *)this + 48), 1);
      std::auto_ptr<TnoHashKey>::reset((char *)this + 144, v8, v9, v10);
      InCritSec::~InCritSec((InCritSec *)v15);
      if ( *((_BYTE *)this + 104) )
      {
        v11 = GetCurrentThread();
        SetThreadPriority(v11, 0x20000);
      }
    }
    v12 = (void (__fastcall ***)(_QWORD, __int64))v3[1];
    v3[1] = 0;
    v13 = (void (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 12);
    if ( v13 )
    {
      v14 = (unsigned int)v4;
    }
    else
    {
      if ( !v12 )
        goto LABEL_15;
      v14 = 1;
      v13 = **v12;
    }
    v13(v12, v14);
LABEL_15:
    InCritSec::InCritSec((InCritSec *)v15, (CSegmentHashGenWorkQueue *)((char *)this + 48), 1);
    if ( v4 < 0 && *((int *)this + 38) >= 0 )
      *((_DWORD *)this + 38) = v4;
    InCritSec::~InCritSec((InCritSec *)v15);
    (*(void (__fastcall **)(_QWORD *, __int64))*v3)(v3, 1);
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_4c871753081c3186d184f5bd8c859e5f_Traceguids);
  }
LABEL_21:
  InCritSec::~InCritSec((InCritSec *)v15);
}

```

## disassembly

```asm
0x18009f810  push    rbp
0x18009f812  push    rbx
0x18009f813  push    rsi
0x18009f814  push    rdi
0x18009f815  push    r12
0x18009f817  push    r13
0x18009f819  push    r14
0x18009f81b  push    r15
0x18009f81d  mov     rbp, rsp
0x18009f820  sub     rsp, 58h
0x18009f824  mov     r14, rcx
0x18009f827  mov     rcx, rdx; pci
0x18009f82a  call    cs:__imp_CallbackMayRunLong
0x18009f830  lea     r12, [r14+30h]
0x18009f834  xor     ebx, ebx
0x18009f836  mov     [rbp+arg_0], rbx
0x18009f83a  mov     r8b, 1; bool
0x18009f83d  mov     rdx, r12; struct CritSec *
0x18009f840  lea     rcx, [rbp+var_28]; this
0x18009f844  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18009f849  cmp     [r14+78h], rbx
0x18009f84d  jz      loc_18009F9FB
0x18009f853  mov     rax, [r14+70h]
0x18009f857  mov     rcx, [rax]
0x18009f85a  mov     r15, [rcx+10h]
0x18009f85e  lea     rcx, [r14+70h]
0x18009f862  call    ?pop_front@?$list@PEAVCCacheReadWriteData@@V?$allocator@PEAVCCacheReadWriteData@@@std@@@std@@QEAAXXZ; std::list<CCacheReadWriteData *>::pop_front(void)
0x18009f867  test    r15, r15
0x18009f86a  jz      loc_18009FA1D
0x18009f870  cmp     [r14+69h], bl
0x18009f874  jnz     loc_18009F9D1
0x18009f87a  lea     rcx, [rbp+var_28]; this
0x18009f87e  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009f883  mov     r8b, 1; bool
0x18009f886  mov     rdx, r12; struct CritSec *
0x18009f889  lea     rcx, [rbp+var_28]; this
0x18009f88d  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18009f892  mov     edi, [r14+98h]
0x18009f899  lea     rcx, [rbp+var_28]; this
0x18009f89d  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009f8a2  test    edi, edi
0x18009f8a4  js      loc_18009F963
0x18009f8aa  cmp     [r14+68h], bl
0x18009f8ae  jz      short loc_18009F8C4
0x18009f8b0  call    cs:__imp_GetCurrentThread
0x18009f8b6  mov     rcx, rax; hThread
0x18009f8b9  mov     edx, 10000h; nPriority
0x18009f8be  call    cs:__imp_SetThreadPriority
0x18009f8c4  mov     r8b, 1; bool
0x18009f8c7  mov     rdx, r12; struct CritSec *
0x18009f8ca  lea     rcx, [rbp+var_28]; this
0x18009f8ce  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18009f8d3  lea     rsi, [r14+90h]
0x18009f8da  mov     rdi, [rsi]
0x18009f8dd  lea     rcx, [rbp+var_28]; this
0x18009f8e1  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009f8e6  mov     r8b, 1; bool
0x18009f8e9  mov     rdx, r12; struct CritSec *
0x18009f8ec  lea     rcx, [rbp+var_28]; this
0x18009f8f0  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18009f8f5  mov     rbx, [r14+88h]
0x18009f8fc  lea     rcx, [rbp+var_28]; this
0x18009f900  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009f905  mov     rax, [r15]
0x18009f908  lea     r9, [rbp+arg_0]
0x18009f90c  mov     r8, rdi
0x18009f90f  mov     rdx, rbx
0x18009f912  mov     rcx, r15
0x18009f915  mov     rax, [rax+8]
0x18009f919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f91e  mov     edi, eax
0x18009f920  mov     rbx, [rbp+arg_0]
0x18009f924  mov     r8b, 1; bool
0x18009f927  mov     rdx, r12; struct CritSec *
0x18009f92a  lea     rcx, [rbp+var_28]; this
0x18009f92e  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18009f933  mov     rdx, rbx
0x18009f936  mov     rcx, rsi
0x18009f939  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x18009f93e  lea     rcx, [rbp+var_28]; this
0x18009f942  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009f947  xor     ebx, ebx
0x18009f949  cmp     [r14+68h], bl
0x18009f94d  jz      short loc_18009F963
0x18009f94f  call    cs:__imp_GetCurrentThread
0x18009f955  mov     rcx, rax; hThread
0x18009f958  mov     edx, 20000h; nPriority
0x18009f95d  call    cs:__imp_SetThreadPriority
0x18009f963  mov     rcx, [r15+8]
0x18009f967  mov     [r15+8], rbx
0x18009f96b  mov     rax, [r14+60h]
0x18009f96f  test    rax, rax
0x18009f972  jz      short loc_18009F978
0x18009f974  mov     edx, edi
0x18009f976  jmp     short loc_18009F988
0x18009f978  test    rcx, rcx
0x18009f97b  jz      short loc_18009F98D
0x18009f97d  mov     rax, [rcx]
0x18009f980  mov     edx, 1
0x18009f985  mov     rax, [rax]
0x18009f988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f98d  mov     r8b, 1; bool
0x18009f990  mov     rdx, r12; struct CritSec *
0x18009f993  lea     rcx, [rbp+var_28]; this
0x18009f997  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18009f99c  test    edi, edi
0x18009f99e  jns     short loc_18009F9B0
0x18009f9a0  cmp     [r14+98h], ebx
0x18009f9a7  jl      short loc_18009F9B0
0x18009f9a9  mov     [r14+98h], edi
0x18009f9b0  lea     rcx, [rbp+var_28]; this
0x18009f9b4  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009f9b9  mov     rax, [r15]
0x18009f9bc  mov     edx, 1
0x18009f9c1  mov     rcx, r15
0x18009f9c4  mov     rax, [rax]
0x18009f9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9cc  jmp     loc_18009F836
0x18009f9d1  mov     rax, [r15]
0x18009f9d4  mov     rcx, r15
0x18009f9d7  mov     rax, [rax+10h]
0x18009f9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9e0  mov     rax, [r15]
0x18009f9e3  mov     edx, 1
0x18009f9e8  mov     rcx, r15
0x18009f9eb  mov     rax, [rax]
0x18009f9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9f3  mov     rcx, r14; this
0x18009f9f6  call    ?CancelQueuedWorkItems@CSegmentHashGenWorkQueue@@QEAAXXZ; CSegmentHashGenWorkQueue::CancelQueuedWorkItems(void)
0x18009f9fb  mov     [r14+80h], bl
0x18009fa02  lea     rcx, [rbp+var_28]; this
0x18009fa06  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18009fa0b  nop
0x18009fa0c  add     rsp, 58h
0x18009fa10  pop     r15
0x18009fa12  pop     r14
0x18009fa14  pop     r13
0x18009fa16  pop     r12
0x18009fa18  pop     rdi
0x18009fa19  pop     rsi
0x18009fa1a  pop     rbx
0x18009fa1b  pop     rbp
0x18009fa1c  retn
0x18009fa1d  lea     rax, WPP_GLOBAL_Control
0x18009fa24  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fa2b  cmp     rcx, rax
0x18009fa2e  jz      short loc_18009FA02
0x18009fa30  test    byte ptr [rcx+6Ch], 1
0x18009fa34  jz      short loc_18009FA02
0x18009fa36  cmp     byte ptr [rcx+69h], 1
0x18009fa3a  jb      short loc_18009FA02
0x18009fa3c  mov     edx, 0Ch
0x18009fa41  lea     r8, WPP_4c871753081c3186d184f5bd8c859e5f_Traceguids
0x18009fa48  mov     rcx, [rcx+60h]
0x18009fa4c  call    WPP_SF_
0x18009fa51  jmp     short loc_18009FA02
```
