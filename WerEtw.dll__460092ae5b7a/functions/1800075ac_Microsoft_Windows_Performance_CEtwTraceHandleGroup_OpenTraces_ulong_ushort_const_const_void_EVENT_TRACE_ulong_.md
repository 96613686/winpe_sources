# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x1800075ac`
- end: `0x18000771b`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `367`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandleGroup *this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), ULONG)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800059a4`

## callees

- `0x180001870`
- `0x1800018e4`
- `0x1800018f0`
- `0x180002420`
- `0x180004500`
- `0x180004670`
- `0x1800075ac`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180007664`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180007664`

## pseudocode

```c
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
      operator delete[](v15);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800075ac  push    rbx
0x1800075ae  push    rbp
0x1800075af  push    rsi
0x1800075b0  push    rdi
0x1800075b1  push    r12
0x1800075b3  push    r13
0x1800075b5  push    r14
0x1800075b7  push    r15
0x1800075b9  sub     rsp, 208h
0x1800075c0  mov     rax, cs:__security_cookie
0x1800075c7  xor     rax, rsp
0x1800075ca  mov     [rsp+248h+var_58], rax
0x1800075d2  mov     [rsp+248h+var_228], r9
0x1800075d7  mov     r13, r8
0x1800075da  mov     r15d, edx
0x1800075dd  mov     r14, rcx
0x1800075e0  mov     rax, [rsp+248h+arg_20]
0x1800075e8  mov     [rsp+248h+var_220], rax
0x1800075ed  mov     edx, edx
0x1800075ef  call    ?Allocate@?$CAutoVectorPtr@VCEtwTraceHandle@Performance@Windows@Microsoft@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<Microsoft::Windows::Performance::CEtwTraceHandle>::Allocate(unsigned __int64)
0x1800075f4  test    al, al
0x1800075f6  jnz     short loc_180007602
0x1800075f8  mov     eax, 8007000Eh
0x1800075fd  jmp     loc_1800076B2
0x180007602  mov     [r14+8], r15d
0x180007606  xor     ebp, ebp
0x180007608  test    r15d, r15d
0x18000760b  jz      loc_1800076B0
0x180007611  mov     r12d, [rsp+248h+arg_28]
0x180007619  mov     esi, ebp
0x18000761b  add     rsi, rsi
0x18000761e  mov     rdi, [r14]
0x180007621  xor     edx, edx; Val
0x180007623  mov     r8d, 1C0h; Size
0x180007629  lea     rcx, [rsp+248h+Logfile]; void *
0x18000762e  call    memset_0
0x180007633  mov     rax, [r13+rbp*8+0]
0x180007638  mov     [rsp+248h+Logfile.LogFileName], rax
0x18000763d  mov     rax, [rsp+248h+var_228]
0x180007642  mov     qword ptr [rsp+248h+Logfile.1A8h], rax
0x18000764a  mov     rax, [rsp+248h+var_220]
0x18000764f  mov     [rsp+248h+Logfile.BufferCallback], rax
0x180007657  mov     [rsp+248h+Logfile.LogfileHeader.ReservedFlags], r12d
0x18000765f  lea     rcx, [rsp+248h+Logfile]; Logfile
0x180007664  call    cs:__imp_OpenTraceW
0x18000766a  mov     [rdi+rsi*8], rax
0x18000766e  movzx   edx, byte ptr [rsp+248h+Logfile.LogfileHeader.4+1]
0x180007676  shl     edx, 8
0x180007679  movzx   ecx, byte ptr [rsp+248h+Logfile.LogfileHeader.4]
0x180007681  or      edx, ecx
0x180007683  mov     [rdi+rsi*8+8], edx
0x180007687  mov     ecx, [rsp+248h+Logfile.LogfileHeader.BufferSize]
0x18000768e  mov     [rdi+rsi*8+0Ch], ecx
0x180007692  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007696  jnz     short loc_1800076A5
0x180007698  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000769d  mov     edi, eax
0x18000769f  xor     esi, esi
0x1800076a1  test    eax, eax
0x1800076a3  js      short loc_1800076D6
0x1800076a5  inc     ebp
0x1800076a7  cmp     ebp, r15d
0x1800076aa  jb      loc_180007619
0x1800076b0  xor     eax, eax
0x1800076b2  mov     rcx, [rsp+248h+var_58]
0x1800076ba  xor     rcx, rsp; StackCookie
0x1800076bd  call    __security_check_cookie
0x1800076c2  add     rsp, 208h
0x1800076c9  pop     r15
0x1800076cb  pop     r14
0x1800076cd  pop     r13
0x1800076cf  pop     r12
0x1800076d1  pop     rdi
0x1800076d2  pop     rsi
0x1800076d3  pop     rbp
0x1800076d4  pop     rbx
0x1800076d5  retn
0x1800076d6  cmp     [r14+8], esi
0x1800076da  jz      short loc_180007717
0x1800076dc  mov     rcx, [r14]; void *
0x1800076df  test    rcx, rcx
0x1800076e2  jz      short loc_180007710
0x1800076e4  lea     rbx, [rcx-8]
0x1800076e8  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x1800076ef  mov     r8, [rbx]; unsigned __int64
0x1800076f2  mov     edx, 10h; unsigned __int64
0x1800076f7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800076fc  mov     rdx, [rbx]
0x1800076ff  shl     rdx, 4
0x180007703  add     rdx, 8
0x180007707  mov     rcx, rbx; Block
0x18000770a  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18000770f  nop
0x180007710  mov     [r14], rsi
0x180007713  mov     [r14+8], esi
0x180007717  mov     eax, edi
0x180007719  jmp     short loc_1800076B2
```
