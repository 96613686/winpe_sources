# BrowserThreadProc

- ea: `0x180005e70`
- end: `0x180006228`
- name: `BrowserThreadProc`
- size: `952`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001900`
- `0x18000193c`
- `0x1800057a8`
- `0x180005c00`
- `0x180005d88`
- `0x180005e70`
- `0x180006b40`
- `0x180006c88`
- `0x180007064`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000608f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800060a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000608f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800060a6`
- `KERNEL32!EnterCriticalSection` at `0x180005fdb`
- `KERNEL32!EnterCriticalSection` at `0x180005fdb`
- `KERNEL32!LeaveCriticalSection` at `0x180006027`
- `KERNEL32!LeaveCriticalSection` at `0x180006027`
- `KERNEL32!GetCurrentThreadId` at `0x180005fed`
- `KERNEL32!GetCurrentThreadId` at `0x180005fed`
- `KERNEL32!SetEvent` at `0x180005fb6`
- `KERNEL32!SetEvent` at `0x180005fb6`
- `ole32!OleInitialize` at `0x180005eed`
- `ole32!OleInitialize` at `0x180005eed`
- `USER32!PostMessageW` at `0x18000607f`
- `USER32!PostMessageW` at `0x18000607f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall BrowserThreadProc(LPVOID lpThreadParameter)
{
  void *v2; // r12
  __int64 v3; // rax
  _DWORD *v4; // r15
  volatile signed __int32 *v5; // rdi
  __int64 v6; // rax
  _QWORD *v7; // r13
  volatile signed __int32 *v8; // rsi
  WTL::CAppModule *v9; // rcx
  volatile signed __int32 *v10; // r14
  BrowserToolThreadWindow *v11; // rax
  unsigned int v12; // r13d
  struct _RTL_CRITICAL_SECTION *v13; // r12
  _DWORD *v14; // r15
  DWORD CurrentThreadId; // r8d
  int v16; // edx
  volatile signed __int32 *v17; // r15
  volatile signed __int32 *v19; // [rsp+20h] [rbp-A9h] BYREF
  volatile signed __int32 *v20; // [rsp+28h] [rbp-A1h]
  HRESULT *v21; // [rsp+30h] [rbp-99h]
  BrowserToolThreadWindow **v22; // [rsp+38h] [rbp-91h]
  char v23; // [rsp+40h] [rbp-89h]
  void **v24; // [rsp+50h] [rbp-79h] BYREF
  void *v25; // [rsp+58h] [rbp-71h]
  __int64 v26; // [rsp+60h] [rbp-69h]
  void *Block; // [rsp+68h] [rbp-61h]
  __int64 v28; // [rsp+70h] [rbp-59h]
  _DWORD *v29; // [rsp+B0h] [rbp-19h]
  volatile signed __int32 *v30; // [rsp+B8h] [rbp-11h]
  _QWORD *v31; // [rsp+C0h] [rbp-9h]
  volatile signed __int32 *v32; // [rsp+C8h] [rbp-1h]
  HRESULT *v33; // [rsp+D0h] [rbp+7h]
  volatile signed __int32 *v34; // [rsp+D8h] [rbp+Fh]
  BrowserToolThreadWindow *v35; // [rsp+130h] [rbp+67h] BYREF
  HRESULT v36; // [rsp+138h] [rbp+6Fh] BYREF
  HWND hWnd; // [rsp+140h] [rbp+77h]
  __int64 v38; // [rsp+148h] [rbp+7Fh]

  v2 = *(void **)lpThreadParameter;
  v3 = *((_QWORD *)lpThreadParameter + 2);
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v4 = (_DWORD *)*((_QWORD *)lpThreadParameter + 1);
  v29 = v4;
  v5 = (volatile signed __int32 *)*((_QWORD *)lpThreadParameter + 2);
  v30 = v5;
  v6 = *((_QWORD *)lpThreadParameter + 4);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = (_QWORD *)*((_QWORD *)lpThreadParameter + 3);
  v31 = v7;
  v8 = (volatile signed __int32 *)*((_QWORD *)lpThreadParameter + 4);
  v32 = v8;
  hWnd = (HWND)*((_QWORD *)lpThreadParameter + 5);
  v38 = 0;
  BrowserThreadParams::~BrowserThreadParams((BrowserThreadParams *)lpThreadParameter);
  operator delete(lpThreadParameter);
  v36 = OleInitialize(0);
  LOBYTE(v35) = 0;
  v21 = &v36;
  v22 = &v35;
  v23 = 1;
  v10 = (volatile signed __int32 *)operator new(0x18u);
  v19 = v10;
  *(_OWORD *)v10 = 0;
  *((_DWORD *)v10 + 2) = 1;
  *((_DWORD *)v10 + 3) = 1;
  *(_QWORD *)v10 = &std::_Ref_count_resource<long *,_lambda_2e3c7c95411147240c3d85fe2e7843a4_>::`vftable';
  *((_QWORD *)v10 + 2) = &v36;
  v33 = &v36;
  v34 = v10;
  if ( v36 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v10)((void *)v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( v5 )
    {
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
    return 1;
  }
  else
  {
    v24 = &WTL::CMessageLoop::`vftable';
    v25 = 0;
    v26 = 0;
    Block = 0;
    v28 = 0;
    WTL::CAppModule::AddMessageLoop(v9, (struct WTL::CMessageLoop *)&v24);
    v35 = (BrowserToolThreadWindow *)operator new(0xA0u);
    v11 = BrowserToolThreadWindow::BrowserToolThreadWindow(v35);
    std::shared_ptr<BrowserToolThreadWindow>::shared_ptr<BrowserToolThreadWindow>(&v19, (__int64)v11);
    *v7 = *((_QWORD *)v19 + 1);
    *v4 = 0;
    SetEvent(v2);
    v12 = WTL::CMessageLoop::Run((WTL::CMessageLoop *)&v24);
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
    v21 = (HRESULT *)((char *)ATL::_pAtlModule + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
    LOBYTE(v22) = 1;
    v14 = qword_180050788;
    CurrentThreadId = GetCurrentThreadId();
    if ( (int)v14[4] > 0 )
    {
      v16 = 0;
      while ( *(_DWORD *)(*(_QWORD *)v14 + 4LL * v16) != CurrentThreadId )
      {
        if ( ++v16 >= v14[4] )
          goto LABEL_13;
      }
      if ( v16 != -1 )
        ATL::CSimpleMap<unsigned long,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<unsigned long,WTL::CMessageLoop *>>::RemoveAt(v14);
    }
LABEL_13:
    LeaveCriticalSection(v13);
    v17 = v20;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    PostMessageW(hWnd, 0x79Cu, 0, 0);
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    v28 = 0;
    if ( v25 )
    {
      free(v25);
      v25 = 0;
    }
    v26 = 0;
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v10)((void *)v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x180005e70  push    rbp
0x180005e72  push    rbx
0x180005e73  push    rsi
0x180005e74  push    rdi
0x180005e75  push    r12
0x180005e77  push    r13
0x180005e79  push    r14
0x180005e7b  push    r15
0x180005e7d  lea     rbp, [rsp-1Fh]
0x180005e82  sub     rsp, 0E8h
0x180005e89  mov     rbx, rcx
0x180005e8c  mov     r12, [rcx]
0x180005e8f  mov     rax, [rcx+10h]
0x180005e93  test    rax, rax
0x180005e96  jz      short loc_180005E9C
0x180005e98  lock inc dword ptr [rax+8]
0x180005e9c  mov     r15, [rcx+8]
0x180005ea0  mov     [rbp+57h+var_70], r15
0x180005ea4  mov     rdi, [rcx+10h]
0x180005ea8  mov     [rbp+57h+var_68], rdi
0x180005eac  mov     rax, [rcx+20h]
0x180005eb0  test    rax, rax
0x180005eb3  jz      short loc_180005EB9
0x180005eb5  lock inc dword ptr [rax+8]
0x180005eb9  mov     r13, [rcx+18h]
0x180005ebd  mov     [rbp+57h+var_60], r13
0x180005ec1  mov     rsi, [rcx+20h]
0x180005ec5  mov     [rbp+57h+var_58], rsi
0x180005ec9  mov     rax, [rcx+28h]
0x180005ecd  mov     [rbp+57h+hWnd], rax
0x180005ed1  mov     [rbp+57h+arg_18], 0
0x180005ed9  call    ??1BrowserThreadParams@@QEAA@XZ; BrowserThreadParams::~BrowserThreadParams(void)
0x180005ede  mov     edx, 30h ; '0'
0x180005ee3  mov     rcx, rbx; Block
0x180005ee6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005eeb  xor     ecx, ecx; pvReserved
0x180005eed  call    cs:__imp_OleInitialize
0x180005ef3  mov     [rbp+57h+arg_8], eax
0x180005ef6  xor     ebx, ebx
0x180005ef8  mov     byte ptr [rbp+57h+arg_0], bl
0x180005efb  lea     rax, [rbp+57h+arg_8]
0x180005eff  mov     [rsp+120h+var_F0], rax
0x180005f04  lea     rax, [rbp+57h+arg_0]
0x180005f08  mov     [rsp+120h+var_E8], rax
0x180005f0d  mov     [rsp+120h+var_E0], 1
0x180005f12  lea     ecx, [rbx+18h]; Size
0x180005f15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f1a  mov     r14, rax
0x180005f1d  mov     [rsp+120h+var_100], rax
0x180005f22  xorps   xmm0, xmm0
0x180005f25  movups  xmmword ptr [rax], xmm0
0x180005f28  lea     eax, [rbx+1]
0x180005f2b  mov     [r14+8], eax
0x180005f2f  mov     [r14+0Ch], eax
0x180005f33  lea     rax, ??_7?$_Ref_count_resource@PEAJV_lambda_2e3c7c95411147240c3d85fe2e7843a4_@@@std@@6B@; const std::_Ref_count_resource<long *,_lambda_2e3c7c95411147240c3d85fe2e7843a4_>::`vftable'
0x180005f3a  mov     [r14], rax
0x180005f3d  lea     rax, [rbp+57h+arg_8]
0x180005f41  mov     [r14+10h], rax
0x180005f45  lea     rax, [rbp+57h+arg_8]
0x180005f49  mov     [rbp+57h+var_50], rax
0x180005f4d  mov     [rbp+57h+var_48], r14
0x180005f51  cmp     [rbp+57h+arg_8], ebx
0x180005f54  jnz     loc_180006164
0x180005f5a  lea     rax, ??_7CMessageLoop@WTL@@6B@; const WTL::CMessageLoop::`vftable'
0x180005f61  mov     [rbp+57h+var_D0], rax
0x180005f65  mov     [rbp+57h+var_C8], rbx
0x180005f69  mov     [rbp+57h+var_C0], rbx
0x180005f6d  mov     [rbp+57h+Block], rbx
0x180005f71  mov     [rbp+57h+var_B0], rbx
0x180005f75  lea     rdx, [rbp+57h+var_D0]; struct WTL::CMessageLoop *
0x180005f79  call    ?AddMessageLoop@CAppModule@WTL@@QEAAHPEAVCMessageLoop@2@@Z; WTL::CAppModule::AddMessageLoop(WTL::CMessageLoop *)
0x180005f7e  mov     ecx, 0A0h; Size
0x180005f83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f88  mov     [rbp+57h+arg_0], rax
0x180005f8c  mov     rcx, rax; this
0x180005f8f  call    ??0BrowserToolThreadWindow@@QEAA@XZ; BrowserToolThreadWindow::BrowserToolThreadWindow(void)
0x180005f94  nop
0x180005f95  mov     rdx, rax
0x180005f98  lea     rcx, [rsp+120h+var_100]
0x180005f9d  call    ??$?0VBrowserToolThreadWindow@@$0A@@?$shared_ptr@VBrowserToolThreadWindow@@@std@@QEAA@PEAVBrowserToolThreadWindow@@@Z; std::shared_ptr<BrowserToolThreadWindow>::shared_ptr<BrowserToolThreadWindow>(BrowserToolThreadWindow *)
0x180005fa2  nop
0x180005fa3  mov     rax, [rsp+120h+var_100]
0x180005fa8  mov     rdx, [rax+8]
0x180005fac  mov     [r13+0], rdx
0x180005fb0  mov     [r15], ebx
0x180005fb3  mov     rcx, r12; hEvent
0x180005fb6  call    cs:__imp_SetEvent
0x180005fbc  lea     rcx, [rbp+57h+var_D0]; this
0x180005fc0  call    ?Run@CMessageLoop@WTL@@QEAAHXZ; WTL::CMessageLoop::Run(void)
0x180005fc5  mov     r13d, eax
0x180005fc8  mov     r12, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005fcf  add     r12, 18h
0x180005fd3  mov     [rsp+120h+var_F0], r12
0x180005fd8  mov     rcx, r12; lpCriticalSection
0x180005fdb  call    cs:__imp_EnterCriticalSection
0x180005fe1  mov     byte ptr [rsp+120h+var_E8], 1
0x180005fe6  mov     r15, cs:qword_180050788
0x180005fed  call    cs:__imp_GetCurrentThreadId
0x180005ff3  mov     r8d, eax
0x180005ff6  or      ebx, 0FFFFFFFFh
0x180005ff9  cmp     dword ptr [r15+10h], 0
0x180005ffe  jle     short loc_180006024
0x180006000  xor     edx, edx
0x180006002  mov     rcx, [r15]
0x180006005  movsxd  rax, edx
0x180006008  cmp     [rcx+rax*4], r8d
0x18000600c  jz      short loc_180006018
0x18000600e  inc     edx
0x180006010  cmp     edx, [r15+10h]
0x180006014  jl      short loc_180006005
0x180006016  jmp     short loc_180006024
0x180006018  cmp     edx, ebx
0x18000601a  jz      short loc_180006024
0x18000601c  mov     rcx, r15
0x18000601f  call    ?RemoveAt@?$CSimpleMap@KPEAVCMessageLoop@WTL@@V?$CSimpleMapEqualHelper@KPEAVCMessageLoop@WTL@@@ATL@@@ATL@@QEAAHH@Z; ATL::CSimpleMap<ulong,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<ulong,WTL::CMessageLoop *>>::RemoveAt(int)
0x180006024  mov     rcx, r12; lpCriticalSection
0x180006027  call    cs:__imp_LeaveCriticalSection
0x18000602d  nop
0x18000602e  mov     r15, [rsp+120h+var_F8]
0x180006033  xor     r12d, r12d
0x180006036  test    r15, r15
0x180006039  jz      short loc_180006070
0x18000603b  mov     eax, ebx
0x18000603d  lock xadd [r15+8], eax
0x180006043  add     eax, ebx
0x180006045  jnz     short loc_180006070
0x180006047  mov     rax, [r15]
0x18000604a  mov     rcx, r15
0x18000604d  mov     rax, [rax]
0x180006050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006055  mov     eax, ebx
0x180006057  lock xadd [r15+0Ch], eax
0x18000605d  add     eax, ebx
0x18000605f  jnz     short loc_180006070
0x180006061  mov     rax, [r15]
0x180006064  mov     rcx, r15
0x180006067  mov     rax, [rax+8]
0x18000606b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006070  xor     r9d, r9d; lParam
0x180006073  xor     r8d, r8d; wParam
0x180006076  mov     edx, 79Ch; Msg
0x18000607b  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18000607f  call    cs:__imp_PostMessageW
0x180006085  nop
0x180006086  mov     rcx, [rbp+57h+Block]; Block
0x18000608a  test    rcx, rcx
0x18000608d  jz      short loc_180006099
0x18000608f  call    cs:__imp_free
0x180006095  mov     [rbp+57h+Block], r12
0x180006099  mov     [rbp+57h+var_B0], r12
0x18000609d  mov     rcx, [rbp+57h+var_C8]; Block
0x1800060a1  test    rcx, rcx
0x1800060a4  jz      short loc_1800060B0
0x1800060a6  call    cs:__imp_free
0x1800060ac  mov     [rbp+57h+var_C8], r12
0x1800060b0  mov     [rbp+57h+var_C0], r12
0x1800060b4  mov     eax, ebx
0x1800060b6  lock xadd [r14+8], eax
0x1800060bc  add     eax, ebx
0x1800060be  jnz     short loc_1800060EA
0x1800060c0  mov     rax, [r14]
0x1800060c3  mov     rcx, r14
0x1800060c6  mov     rax, [rax]
0x1800060c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ce  mov     eax, ebx
0x1800060d0  lock xadd [r14+0Ch], eax
0x1800060d6  add     eax, ebx
0x1800060d8  jnz     short loc_1800060EA
0x1800060da  mov     rax, [r14]
0x1800060dd  mov     rcx, r14
0x1800060e0  mov     rax, [rax+8]
0x1800060e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e9  nop
0x1800060ea  test    rsi, rsi
0x1800060ed  jz      short loc_180006123
0x1800060ef  mov     eax, ebx
0x1800060f1  lock xadd [rsi+8], eax
0x1800060f6  add     eax, ebx
0x1800060f8  jnz     short loc_180006123
0x1800060fa  mov     rax, [rsi]
0x1800060fd  mov     rcx, rsi
0x180006100  mov     rax, [rax]
0x180006103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006108  mov     eax, ebx
0x18000610a  lock xadd [rsi+0Ch], eax
0x18000610f  add     eax, ebx
0x180006111  jnz     short loc_180006123
0x180006113  mov     rax, [rsi]
0x180006116  mov     rcx, rsi
0x180006119  mov     rax, [rax+8]
0x18000611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006122  nop
0x180006123  test    rdi, rdi
0x180006126  jz      short loc_18000615C
0x180006128  mov     eax, ebx
0x18000612a  lock xadd [rdi+8], eax
0x18000612f  add     eax, ebx
0x180006131  jnz     short loc_18000615C
0x180006133  mov     rax, [rdi]
0x180006136  mov     rcx, rdi
0x180006139  mov     rax, [rax]
0x18000613c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006141  mov     eax, ebx
0x180006143  lock xadd [rdi+0Ch], eax
0x180006148  add     eax, ebx
0x18000614a  jnz     short loc_18000615C
0x18000614c  mov     rax, [rdi]
0x18000614f  mov     rcx, rdi
0x180006152  mov     rax, [rax+8]
0x180006156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000615b  nop
0x18000615c  mov     eax, r13d
0x18000615f  jmp     loc_180006214
0x180006164  or      ebx, 0FFFFFFFFh
0x180006167  mov     eax, ebx
0x180006169  lock xadd [r14+8], eax
0x18000616f  add     eax, ebx
0x180006171  jnz     short loc_18000619D
0x180006173  mov     rax, [r14]
0x180006176  mov     rcx, r14
0x180006179  mov     rax, [rax]
0x18000617c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006181  mov     eax, ebx
0x180006183  lock xadd [r14+0Ch], eax
0x180006189  add     eax, ebx
0x18000618b  jnz     short loc_18000619D
0x18000618d  mov     rax, [r14]
0x180006190  mov     rcx, r14
0x180006193  mov     rax, [rax+8]
0x180006197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619c  nop
0x18000619d  test    rsi, rsi
0x1800061a0  jz      short loc_1800061D6
0x1800061a2  mov     eax, ebx
0x1800061a4  lock xadd [rsi+8], eax
0x1800061a9  add     eax, ebx
0x1800061ab  jnz     short loc_1800061D6
0x1800061ad  mov     rax, [rsi]
0x1800061b0  mov     rcx, rsi
0x1800061b3  mov     rax, [rax]
0x1800061b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061bb  mov     eax, ebx
0x1800061bd  lock xadd [rsi+0Ch], eax
0x1800061c2  add     eax, ebx
0x1800061c4  jnz     short loc_1800061D6
0x1800061c6  mov     rax, [rsi]
0x1800061c9  mov     rcx, rsi
0x1800061cc  mov     rax, [rax+8]
0x1800061d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d5  nop
0x1800061d6  test    rdi, rdi
0x1800061d9  jz      short loc_18000620F
0x1800061db  mov     eax, ebx
0x1800061dd  lock xadd [rdi+8], eax
0x1800061e2  add     eax, ebx
0x1800061e4  jnz     short loc_18000620F
0x1800061e6  mov     rax, [rdi]
0x1800061e9  mov     rcx, rdi
0x1800061ec  mov     rax, [rax]
0x1800061ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f4  mov     edx, ebx
0x1800061f6  lock xadd [rdi+0Ch], edx
0x1800061fb  add     edx, ebx
0x1800061fd  jnz     short loc_18000620F
0x1800061ff  mov     rdx, [rdi]
0x180006202  mov     rcx, rdi
0x180006205  mov     rax, [rdx+8]
0x180006209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000620e  nop
0x18000620f  mov     eax, 1
0x180006214  add     rsp, 0E8h
0x18000621b  pop     r15
0x18000621d  pop     r14
0x18000621f  pop     r13
0x180006221  pop     r12
0x180006223  pop     rdi
0x180006224  pop     rsi
0x180006225  pop     rbx
0x180006226  pop     rbp
0x180006227  retn
```
