# BrowserToolThread::CreateThread(HWND__ * &,ulong &,ATL::CHandle &,HWND__ * &)

- ea: `0x1800066d0`
- end: `0x1800069ae`
- name: `?CreateThread@BrowserToolThread@@CAJAEAPEAUHWND__@@AEAKAEAVCHandle@ATL@@0@Z`
- size: `734`
- prototype: `signed int __fastcall(HWND *, unsigned int *, HANDLE *, HWND *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180006230`

## callees

- `0x180001900`
- `0x18000193c`
- `0x1800058b4`
- `0x180005c00`
- `0x180005e44`
- `0x1800066d0`
- `0x180035010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800068e6`
- `KERNEL32!CloseHandle` at `0x18000698d`
- `KERNEL32!CloseHandle` at `0x1800068e6`
- `KERNEL32!CloseHandle` at `0x18000698d`
- `KERNEL32!CreateEventW` at `0x180006706`
- `KERNEL32!CreateEventW` at `0x180006706`
- `KERNEL32!CreateThread` at `0x180006844`
- `KERNEL32!CreateThread` at `0x180006844`
- `KERNEL32!WaitForSingleObject` at `0x180006878`
- `KERNEL32!WaitForSingleObject` at `0x180006878`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
signed int __fastcall BrowserToolThread::CreateThread(HWND *a1, unsigned int *a2, HANDLE *a3, HWND *a4)
{
  HANDLE EventW; // rbx
  signed int *v8; // r15
  void *v9; // rsi
  HWND *v10; // r12
  void *v11; // r14
  signed int *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // r12
  BrowserThreadParams *v15; // rdi
  HANDLE Thread; // rax
  signed int Error; // r15d
  DWORD v18; // eax
  BrowserThreadParams *v19; // rcx
  signed int *v20; // [rsp+30h] [rbp-40h]
  _QWORD v21[2]; // [rsp+38h] [rbp-38h] BYREF
  HWND *v22; // [rsp+48h] [rbp-28h]
  signed int *v23; // [rsp+50h] [rbp-20h] BYREF
  void *v24; // [rsp+58h] [rbp-18h]
  signed int *v25; // [rsp+60h] [rbp-10h]
  void *v26; // [rsp+68h] [rbp-8h]

  EventW = CreateEventW(0, 1, 0, 0);
  v21[0] = EventW;
  if ( !EventW )
    return ATL::AtlHresultFromLastError();
  v8 = (signed int *)operator new(4u);
  v20 = v8;
  *v8 = 0;
  v9 = operator new(0x18u);
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = &std::_Ref_count<long>::`vftable';
  *((_QWORD *)v9 + 2) = v8;
  v25 = v8;
  v26 = v9;
  operator delete(0);
  v10 = (HWND *)operator new(8u);
  v22 = v10;
  *v10 = 0;
  v11 = operator new(0x18u);
  *(_OWORD *)v11 = 0;
  *((_DWORD *)v11 + 2) = 1;
  *((_DWORD *)v11 + 3) = 1;
  *(_QWORD *)v11 = &std::_Ref_count<HWND__ *>::`vftable';
  *((_QWORD *)v11 + 2) = v10;
  v24 = v11;
  operator delete(0);
  v12 = (signed int *)operator new(0x30u);
  v23 = v12;
  v13 = (__int64)*a1;
  _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
  v21[0] = v10;
  v21[1] = v11;
  _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
  v23 = v8;
  v24 = v9;
  v14 = BrowserThreadParams::BrowserThreadParams(v12, (__int64)EventW, &v23, v21, v13);
  v15 = 0;
  Thread = CreateThread(0, 0, BrowserThreadProc, v14, 0, a2);
  v21[0] = Thread;
  if ( !Thread )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error )
    {
      if ( Error >= 0 )
        Error = -2147467259;
      if ( !v14 )
        goto LABEL_25;
      BrowserThreadParams::~BrowserThreadParams((BrowserThreadParams *)v14);
      v19 = (BrowserThreadParams *)v14;
      goto LABEL_24;
    }
    v15 = (BrowserThreadParams *)v14;
    v8 = v20;
    Thread = (HANDLE)v21[0];
  }
  *a3 = Thread;
  v18 = WaitForSingleObject(EventW, 0xFFFFFFFF);
  if ( v18 )
  {
    if ( v18 == 128 )
    {
      Error = -2147024768;
      goto LABEL_20;
    }
    if ( v18 == 258 )
    {
      Error = -2147024638;
      goto LABEL_20;
    }
    if ( v18 != -1 )
    {
      Error = -2147418113;
      goto LABEL_20;
    }
    Error = ATL::AtlHresultFromLastError();
  }
  else
  {
    Error = *v8;
  }
  if ( Error )
  {
LABEL_20:
    if ( *a3 )
    {
      CloseHandle(*a3);
      *a3 = 0;
    }
  }
  *a4 = *v22;
  if ( !v15 )
    goto LABEL_25;
  BrowserThreadParams::~BrowserThreadParams(v15);
  v19 = v15;
LABEL_24:
  operator delete(v19);
LABEL_25:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v11)(v11);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 8LL))(v11);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v9)(v9);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  CloseHandle(EventW);
  return Error;
}

```

## disassembly

```asm
0x1800066d0  mov     [rsp-38h+arg_0], rbx
0x1800066d5  mov     [rsp-38h+arg_18], r9
0x1800066da  mov     [rsp-38h+arg_8], rdx
0x1800066df  push    rbp
0x1800066e0  push    rsi
0x1800066e1  push    rdi
0x1800066e2  push    r12
0x1800066e4  push    r13
0x1800066e6  push    r14
0x1800066e8  push    r15
0x1800066ea  mov     rbp, rsp
0x1800066ed  sub     rsp, 70h
0x1800066f1  mov     r13, r8
0x1800066f4  mov     rdi, rcx
0x1800066f7  xor     r9d, r9d; lpName
0x1800066fa  xor     r8d, r8d; bInitialState
0x1800066fd  lea     r12d, [r9+1]
0x180006701  mov     edx, r12d; bManualReset
0x180006704  xor     ecx, ecx; lpEventAttributes
0x180006706  call    cs:__imp_CreateEventW
0x18000670c  mov     rbx, rax
0x18000670f  mov     [rbp+var_38], rax
0x180006713  test    rax, rax
0x180006716  jnz     short loc_180006723
0x180006718  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000671d  nop
0x18000671e  jmp     loc_180006996
0x180006723  mov     r14d, 4
0x180006729  mov     ecx, r14d; Size
0x18000672c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006731  mov     r15, rax
0x180006734  mov     [rbp+var_40], rax
0x180006738  mov     dword ptr [rax], 0
0x18000673e  mov     [rbp+var_28], rax
0x180006742  lea     ecx, [r14+14h]; Size
0x180006746  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000674b  mov     rsi, rax
0x18000674e  mov     [rbp+var_28], rax
0x180006752  xorps   xmm0, xmm0
0x180006755  movups  xmmword ptr [rax], xmm0
0x180006758  mov     [rax+8], r12d
0x18000675c  mov     [rax+0Ch], r12d
0x180006760  lea     rax, ??_7?$_Ref_count@J@std@@6B@; const std::_Ref_count<long>::`vftable'
0x180006767  mov     [rsi], rax
0x18000676a  mov     [rsi+10h], r15
0x18000676e  mov     [rbp+var_10], r15
0x180006772  mov     [rbp+var_8], rsi
0x180006776  mov     edx, r14d
0x180006779  xor     ecx, ecx; Block
0x18000677b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006780  nop
0x180006781  lea     ecx, [r14+4]; Size
0x180006785  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000678a  mov     r12, rax
0x18000678d  mov     [rbp+var_28], rax
0x180006791  mov     qword ptr [rax], 0
0x180006798  mov     [rbp+var_20], rax
0x18000679c  lea     ecx, [r14+14h]; Size
0x1800067a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800067a5  mov     r14, rax
0x1800067a8  mov     [rbp+var_20], rax
0x1800067ac  xorps   xmm0, xmm0
0x1800067af  movups  xmmword ptr [rax], xmm0
0x1800067b2  mov     eax, 1
0x1800067b7  mov     [r14+8], eax
0x1800067bb  mov     [r14+0Ch], eax
0x1800067bf  lea     rax, ??_7?$_Ref_count@PEAUHWND__@@@std@@6B@; const std::_Ref_count<HWND__ *>::`vftable'
0x1800067c6  mov     [r14], rax
0x1800067c9  mov     [r14+10h], r12
0x1800067cd  mov     [rbp+var_20], r12
0x1800067d1  mov     [rbp+var_18], r14
0x1800067d5  mov     edx, 8
0x1800067da  xor     ecx, ecx; Block
0x1800067dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800067e1  nop
0x1800067e2  mov     ecx, 30h ; '0'; Size
0x1800067e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800067ec  mov     [rbp+var_20], rax
0x1800067f0  mov     rcx, [rdi]
0x1800067f3  lock inc dword ptr [r14+8]
0x1800067f8  mov     [rbp+var_38], r12
0x1800067fc  mov     [rbp+var_30], r14
0x180006800  lock inc dword ptr [rsi+8]
0x180006804  mov     [rbp+var_20], r15
0x180006808  mov     [rbp+var_18], rsi
0x18000680c  mov     qword ptr [rsp+70h+dwCreationFlags], rcx
0x180006811  lea     r9, [rbp+var_38]
0x180006815  lea     r8, [rbp+var_20]
0x180006819  mov     rdx, rbx
0x18000681c  mov     rcx, rax
0x18000681f  call    ??0BrowserThreadParams@@QEAA@PEAXV?$shared_ptr@J@std@@V?$shared_ptr@PEAUHWND__@@@2@PEAUHWND__@@@Z; BrowserThreadParams::BrowserThreadParams(void *,std::shared_ptr<long>,std::shared_ptr<HWND__ *>,HWND__ *)
0x180006824  mov     r12, rax
0x180006827  xor     edi, edi
0x180006829  mov     rax, [rbp+arg_8]
0x18000682d  mov     [rsp+70h+lpThreadId], rax; lpThreadId
0x180006832  mov     [rsp+70h+dwCreationFlags], edi; dwCreationFlags
0x180006836  mov     r9, r12; lpParameter
0x180006839  lea     r8, BrowserThreadProc; lpStartAddress
0x180006840  xor     edx, edx; dwStackSize
0x180006842  xor     ecx, ecx; lpThreadAttributes
0x180006844  call    cs:__imp_CreateThread
0x18000684a  mov     [rbp+var_38], rax
0x18000684e  test    rax, rax
0x180006851  jnz     short loc_18000686A
0x180006853  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006858  mov     r15d, eax
0x18000685b  test    eax, eax
0x18000685d  jnz     short loc_18000689D
0x18000685f  mov     rdi, r12
0x180006862  mov     r15, [rbp+var_40]
0x180006866  mov     rax, [rbp+var_38]
0x18000686a  mov     [r13+0], rax
0x18000686e  or      r12d, 0FFFFFFFFh
0x180006872  mov     edx, r12d; dwMilliseconds
0x180006875  mov     rcx, rbx; hHandle
0x180006878  call    cs:__imp_WaitForSingleObject
0x18000687e  test    eax, eax
0x180006880  jz      short loc_1800068D5
0x180006882  cmp     eax, 80h
0x180006887  jz      short loc_1800068CD
0x180006889  cmp     eax, 102h
0x18000688e  jz      short loc_1800068C5
0x180006890  cmp     eax, r12d
0x180006893  jz      short loc_1800068BB
0x180006895  mov     r15d, 8000FFFFh
0x18000689b  jmp     short loc_1800068DD
0x18000689d  mov     eax, 80004005h
0x1800068a2  test    r15d, r15d
0x1800068a5  cmovns  r15d, eax
0x1800068a9  test    r12, r12
0x1800068ac  jz      short loc_18000691D
0x1800068ae  mov     rcx, r12; this
0x1800068b1  call    ??1BrowserThreadParams@@QEAA@XZ; BrowserThreadParams::~BrowserThreadParams(void)
0x1800068b6  mov     rcx, r12
0x1800068b9  jmp     short loc_180006912
0x1800068bb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800068c0  mov     r15d, eax
0x1800068c3  jmp     short loc_1800068D8
0x1800068c5  mov     r15d, 80070102h
0x1800068cb  jmp     short loc_1800068DD
0x1800068cd  mov     r15d, 80070080h
0x1800068d3  jmp     short loc_1800068DD
0x1800068d5  mov     r15d, [r15]
0x1800068d8  test    r15d, r15d
0x1800068db  jz      short loc_1800068F4
0x1800068dd  mov     rcx, [r13+0]; hObject
0x1800068e1  test    rcx, rcx
0x1800068e4  jz      short loc_1800068F4
0x1800068e6  call    cs:__imp_CloseHandle
0x1800068ec  mov     qword ptr [r13+0], 0
0x1800068f4  mov     rax, [rbp+var_28]
0x1800068f8  mov     rax, [rax]
0x1800068fb  mov     rcx, [rbp+arg_18]
0x1800068ff  mov     [rcx], rax
0x180006902  test    rdi, rdi
0x180006905  jz      short loc_18000691D
0x180006907  mov     rcx, rdi; this
0x18000690a  call    ??1BrowserThreadParams@@QEAA@XZ; BrowserThreadParams::~BrowserThreadParams(void)
0x18000690f  mov     rcx, rdi; Block
0x180006912  mov     edx, 30h ; '0'
0x180006917  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000691c  nop
0x18000691d  or      edi, 0FFFFFFFFh
0x180006920  mov     eax, edi
0x180006922  lock xadd [r14+8], eax
0x180006928  add     eax, edi
0x18000692a  jnz     short loc_180006956
0x18000692c  mov     rax, [r14]
0x18000692f  mov     rcx, r14
0x180006932  mov     rax, [rax]
0x180006935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693a  mov     eax, edi
0x18000693c  lock xadd [r14+0Ch], eax
0x180006942  add     eax, edi
0x180006944  jnz     short loc_180006956
0x180006946  mov     rax, [r14]
0x180006949  mov     rcx, r14
0x18000694c  mov     rax, [rax+8]
0x180006950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006955  nop
0x180006956  mov     eax, edi
0x180006958  lock xadd [rsi+8], eax
0x18000695d  add     eax, edi
0x18000695f  jnz     short loc_18000698A
0x180006961  mov     rax, [rsi]
0x180006964  mov     rcx, rsi
0x180006967  mov     rax, [rax]
0x18000696a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000696f  mov     eax, edi
0x180006971  lock xadd [rsi+0Ch], eax
0x180006976  add     eax, edi
0x180006978  jnz     short loc_18000698A
0x18000697a  mov     rax, [rsi]
0x18000697d  mov     rcx, rsi
0x180006980  mov     rax, [rax+8]
0x180006984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006989  nop
0x18000698a  mov     rcx, rbx; hObject
0x18000698d  call    cs:__imp_CloseHandle
0x180006993  mov     eax, r15d
0x180006996  mov     rbx, [rsp+70h+arg_0]
0x18000699e  add     rsp, 70h
0x1800069a2  pop     r15
0x1800069a4  pop     r14
0x1800069a6  pop     r13
0x1800069a8  pop     r12
0x1800069aa  pop     rdi
0x1800069ab  pop     rsi
0x1800069ac  pop     rbp
0x1800069ad  retn
```
