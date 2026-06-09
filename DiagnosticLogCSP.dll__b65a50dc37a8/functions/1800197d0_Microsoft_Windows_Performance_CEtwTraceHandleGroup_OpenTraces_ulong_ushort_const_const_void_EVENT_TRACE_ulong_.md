# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x1800197d0`
- end: `0x180019946`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `374`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandleGroup *__hidden this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017648`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x180002adc`
- `0x180002ae8`
- `0x180016100`
- `0x180016274`
- `0x1800197d0`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180019888`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180019888`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(
        Microsoft::Windows::Performance::CEtwTraceHandleGroup *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        void (*a4)(struct _EVENT_TRACE *),
        unsigned int (*a5)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a6)
{
  __int64 v10; // rbp
  __int64 v11; // rdi
  TRACEHANDLE v12; // rax
  int Error; // edi
  char *v14; // rcx
  char *v15; // rbx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-218h] BYREF

  if ( !(unsigned __int8)ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(this, a2) )
    return 2147942414LL;
  *((_DWORD *)this + 2) = a2;
  v10 = 0;
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    v11 = *(_QWORD *)this;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileName = (LPWSTR)a3[v10];
    Logfile.EventCallback = a4;
    Logfile.BufferCallback = a5;
    Logfile.LogfileHeader.ReservedFlags = a6;
    v12 = OpenTraceW(&Logfile);
    *(_QWORD *)(v11 + 16LL * (unsigned int)v10) = v12;
    *(_DWORD *)(v11 + 16LL * (unsigned int)v10 + 8) = LOWORD(Logfile.LogfileHeader.Version);
    *(_DWORD *)(v11 + 16LL * (unsigned int)v10 + 12) = Logfile.LogfileHeader.BufferSize;
    if ( v12 == -1 )
    {
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        break;
    }
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= a2 )
      return 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v14 = *(char **)this;
    if ( *(_QWORD *)this )
    {
      v15 = v14 - 8;
      `eh vector destructor iterator'(
        v14,
        0x10u,
        *((_QWORD *)v14 - 1),
        (void (*)(void *))Microsoft::Windows::Performance::CEtwTraceHandle::~CEtwTraceHandle);
      operator delete[](v15, 16LL * *(_QWORD *)v15 + 8);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800197d0  push    rbx
0x1800197d2  push    rbp
0x1800197d3  push    rsi
0x1800197d4  push    rdi
0x1800197d5  push    r12
0x1800197d7  push    r13
0x1800197d9  push    r14
0x1800197db  push    r15
0x1800197dd  sub     rsp, 208h
0x1800197e4  mov     rax, cs:__security_cookie
0x1800197eb  xor     rax, rsp
0x1800197ee  mov     [rsp+248h+var_58], rax
0x1800197f6  mov     [rsp+248h+var_228], r9
0x1800197fb  mov     r13, r8
0x1800197fe  mov     r15d, edx
0x180019801  mov     r14, rcx
0x180019804  mov     rax, [rsp+248h+arg_20]
0x18001980c  mov     [rsp+248h+var_220], rax
0x180019811  mov     edx, edx
0x180019813  call    ?Allocate@?$CAutoVectorPtr@VCEtwTraceHandle@Performance@Windows@Microsoft@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(unsigned __int64)
0x180019818  test    al, al
0x18001981a  jnz     short loc_180019826
0x18001981c  mov     eax, 8007000Eh
0x180019821  jmp     loc_1800198DC
0x180019826  mov     [r14+8], r15d
0x18001982a  xor     ebp, ebp
0x18001982c  test    r15d, r15d
0x18001982f  jz      loc_1800198DA
0x180019835  mov     r12d, [rsp+248h+arg_28]
0x18001983d  mov     esi, ebp
0x18001983f  add     rsi, rsi
0x180019842  mov     rdi, [r14]
0x180019845  xor     edx, edx; Val
0x180019847  mov     r8d, 1C0h; Size
0x18001984d  lea     rcx, [rsp+248h+Logfile]; void *
0x180019852  call    memset_0
0x180019857  mov     rax, [r13+rbp*8+0]
0x18001985c  mov     [rsp+248h+Logfile.LogFileName], rax
0x180019861  mov     rax, [rsp+248h+var_228]
0x180019866  mov     qword ptr [rsp+248h+Logfile.1A8h], rax
0x18001986e  mov     rax, [rsp+248h+var_220]
0x180019873  mov     [rsp+248h+Logfile.BufferCallback], rax
0x18001987b  mov     [rsp+248h+Logfile.LogfileHeader.ReservedFlags], r12d
0x180019883  lea     rcx, [rsp+248h+Logfile]; Logfile
0x180019888  call    cs:__imp_OpenTraceW
0x18001988f  nop     dword ptr [rax+rax+00h]
0x180019894  mov     [rdi+rsi*8], rax
0x180019898  movzx   edx, byte ptr [rsp+248h+Logfile.LogfileHeader.4+1]
0x1800198a0  shl     edx, 8
0x1800198a3  movzx   ecx, byte ptr [rsp+248h+Logfile.LogfileHeader.4]
0x1800198ab  or      edx, ecx
0x1800198ad  mov     [rdi+rsi*8+8], edx
0x1800198b1  mov     ecx, [rsp+248h+Logfile.LogfileHeader.BufferSize]
0x1800198b8  mov     [rdi+rsi*8+0Ch], ecx
0x1800198bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800198c0  jnz     short loc_1800198CF
0x1800198c2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800198c7  mov     edi, eax
0x1800198c9  xor     esi, esi
0x1800198cb  test    eax, eax
0x1800198cd  js      short loc_180019901
0x1800198cf  inc     ebp
0x1800198d1  cmp     ebp, r15d
0x1800198d4  jb      loc_18001983D
0x1800198da  xor     eax, eax
0x1800198dc  mov     rcx, [rsp+248h+var_58]
0x1800198e4  xor     rcx, rsp; StackCookie
0x1800198e7  call    __security_check_cookie
0x1800198ec  add     rsp, 208h
0x1800198f3  pop     r15
0x1800198f5  pop     r14
0x1800198f7  pop     r13
0x1800198f9  pop     r12
0x1800198fb  pop     rdi
0x1800198fc  pop     rsi
0x1800198fd  pop     rbp
0x1800198fe  pop     rbx
0x1800198ff  retn
0x180019901  cmp     [r14+8], esi
0x180019905  jz      short loc_180019942
0x180019907  mov     rcx, [r14]; void *
0x18001990a  test    rcx, rcx
0x18001990d  jz      short loc_18001993B
0x18001990f  lea     rbx, [rcx-8]
0x180019913  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001991a  mov     r8, [rbx]; unsigned __int64
0x18001991d  mov     edx, 10h; unsigned __int64
0x180019922  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180019927  mov     rdx, [rbx]
0x18001992a  shl     rdx, 4
0x18001992e  add     rdx, 8; unsigned __int64
0x180019932  mov     rcx, rbx; void *
0x180019935  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18001993a  nop
0x18001993b  mov     [r14], rsi
0x18001993e  mov     [r14+8], esi
0x180019942  mov     eax, edi
0x180019944  jmp     short loc_1800198DC
```
