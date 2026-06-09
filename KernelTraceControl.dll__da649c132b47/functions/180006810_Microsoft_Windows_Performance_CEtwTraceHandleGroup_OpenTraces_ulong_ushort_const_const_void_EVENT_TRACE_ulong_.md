# Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(ulong,ushort const * const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x180006810`
- end: `0x180006960`
- name: `?OpenTraces@CEtwTraceHandleGroup@Performance@Windows@Microsoft@@QEAAJKPEBQEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `336`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandleGroup *__hidden this, unsigned int, const unsigned __int16 *const *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003024`

## callees

- `0x1800067f0`
- `0x180006810`
- `0x1800268f4`
- `0x180026e30`
- `0x180026f6c`
- `0x180027718`

## import_xrefs

- `ADVAPI32!OpenTraceW` at `0x1800068af`
- `ADVAPI32!OpenTraceW` at `0x1800068af`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandleGroup::OpenTraces(
        Microsoft::Windows::Performance::CEtwTraceHandleGroup *this,
        unsigned int a2,
        LPWSTR *a3,
        void (*a4)(struct _EVENT_TRACE *),
        unsigned int (*a5)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a6)
{
  unsigned int v6; // r14d
  void (__stdcall *v7)(PEVENT_TRACE); // rbp
  __int64 i; // rsi
  __int64 v12; // rbx
  TRACEHANDLE v13; // rax
  int Error; // ebp
  char *v16; // rcx
  char *v17; // rbx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-208h] BYREF

  v6 = 0;
  v7 = a4;
  *((_DWORD *)this + 2) = a2;
  if ( !a2 )
    return 0;
  for ( i = 0; ; i += 16 )
  {
    v12 = *(_QWORD *)this;
    memset_0(&Logfile.LoggerName, 0, 0x1B8u);
    Logfile.LogFileName = *a3;
    Logfile.BufferCallback = a5;
    Logfile.EventCallback = v7;
    Logfile.LogfileHeader.ReservedFlags = a6;
    v13 = OpenTraceW(&Logfile);
    *(_DWORD *)(i + v12 + 8) = Logfile.LogfileHeader.Version;
    *(_DWORD *)(i + v12 + 12) = Logfile.LogfileHeader.BufferSize;
    *(_QWORD *)(i + v12) = v13;
    if ( v13 == -1 )
      break;
LABEL_6:
    ++v6;
    ++a3;
    if ( v6 >= a2 )
      return 0;
  }
  Error = ATL::AtlHresultFromLastError();
  if ( Error >= 0 )
  {
    v7 = a4;
    goto LABEL_6;
  }
  if ( *((_DWORD *)this + 2) )
  {
    v16 = *(char **)this;
    if ( *(_QWORD *)this )
    {
      v17 = v16 - 8;
      `eh vector destructor iterator'(
        v16,
        0x10u,
        *((_QWORD *)v16 - 1),
        (void (*)(void *))Microsoft::Windows::Performance::CEtwTraceHandle::~CEtwTraceHandle);
      operator delete(v17);
    }
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180006810  mov     [rsp+arg_8], rbx
0x180006815  push    rbp
0x180006816  push    rsi
0x180006817  push    rdi
0x180006818  push    r12
0x18000681a  push    r13
0x18000681c  push    r14
0x18000681e  push    r15
0x180006820  sub     rsp, 200h
0x180006827  mov     rax, cs:__security_cookie
0x18000682e  xor     rax, rsp
0x180006831  mov     [rsp+238h+var_48], rax
0x180006839  mov     rax, [rsp+238h+arg_20]
0x180006841  xor     r14d, r14d
0x180006844  mov     [rsp+238h+var_210], r9
0x180006849  mov     rbp, r9
0x18000684c  mov     [rsp+238h+var_218], rax
0x180006851  mov     r12, r8
0x180006854  mov     [rcx+8], edx
0x180006857  mov     r15d, edx
0x18000685a  mov     rdi, rcx
0x18000685d  test    edx, edx
0x18000685f  jz      loc_1800068F9
0x180006865  mov     r13d, [rsp+238h+arg_28]
0x18000686d  xor     esi, esi
0x18000686f  mov     rbx, [rdi]
0x180006872  lea     rcx, [rsp+238h+Logfile.LoggerName]; void *
0x180006877  xor     edx, edx; Val
0x180006879  mov     r8d, 1B8h; Size
0x18000687f  call    memset_0
0x180006884  mov     rax, [r12]
0x180006888  lea     rcx, [rsp+238h+Logfile]; Logfile
0x18000688d  mov     [rsp+238h+Logfile.LogFileName], rax
0x180006892  mov     rax, [rsp+238h+var_218]
0x180006897  mov     [rsp+238h+Logfile.BufferCallback], rax
0x18000689f  mov     qword ptr [rsp+238h+Logfile.1A8h], rbp
0x1800068a7  mov     [rsp+238h+Logfile.LogfileHeader.ReservedFlags], r13d
0x1800068af  call    cs:__imp_OpenTraceW
0x1800068b5  mov     ecx, dword ptr [rsp+238h+Logfile.LogfileHeader.4]
0x1800068bc  mov     [rsi+rbx+8], ecx
0x1800068c0  mov     ecx, [rsp+238h+Logfile.LogfileHeader.BufferSize]
0x1800068c7  mov     [rsi+rbx+0Ch], ecx
0x1800068cb  mov     [rsi+rbx], rax
0x1800068cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800068d3  jnz     short loc_1800068E5
0x1800068d5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800068da  mov     ebp, eax
0x1800068dc  test    eax, eax
0x1800068de  js      short loc_180006926
0x1800068e0  mov     rbp, [rsp+238h+var_210]
0x1800068e5  inc     r14d
0x1800068e8  add     rsi, 10h
0x1800068ec  add     r12, 8
0x1800068f0  cmp     r14d, r15d
0x1800068f3  jb      loc_18000686F
0x1800068f9  xor     eax, eax
0x1800068fb  mov     rcx, [rsp+238h+var_48]
0x180006903  xor     rcx, rsp; StackCookie
0x180006906  call    __security_check_cookie
0x18000690b  mov     rbx, [rsp+238h+arg_8]
0x180006913  add     rsp, 200h
0x18000691a  pop     r15
0x18000691c  pop     r14
0x18000691e  pop     r13
0x180006920  pop     r12
0x180006922  pop     rdi
0x180006923  pop     rsi
0x180006924  pop     rbp
0x180006925  retn
0x180006926  cmp     dword ptr [rdi+8], 0
0x18000692a  jz      short loc_18000695C
0x18000692c  mov     rcx, [rdi]; void *
0x18000692f  test    rcx, rcx
0x180006932  jz      short loc_180006954
0x180006934  lea     rbx, [rcx-8]
0x180006938  mov     edx, 10h; unsigned __int64
0x18000693d  mov     r8, [rbx]; unsigned __int64
0x180006940  lea     r9, ??1CEtwTraceHandle@Performance@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x180006947  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000694c  mov     rcx, rbx; Block
0x18000694f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006954  and     qword ptr [rdi], 0
0x180006958  and     dword ptr [rdi+8], 0
0x18000695c  mov     eax, ebp
0x18000695e  jmp     short loc_1800068FB
```
